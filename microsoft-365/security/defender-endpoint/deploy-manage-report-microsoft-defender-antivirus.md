---
title: Bereitstellen, Verwalten und Melden von Microsoft Defender Antivirus
description: Sie können Microsoft Defender Antivirus mit Intune, Microsoft Endpoint Configuration Manager, Gruppenrichtlinie, PowerShell oder WMI bereitstellen und verwalten.
keywords: Bereitstellen, Verwalten, Aktualisieren, Schutz, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b44bc529a14d12d2be49854c31a4ea11cdabc7d1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764843"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Bereitstellen, Verwalten und Melden von Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können Microsoft Defender Antivirus auf verschiedene Weise bereitstellen, verwalten und melden.

Da der Microsoft Defender Antivirus-Client als Kernteil von Windows 10 installiert ist, gilt die herkömmliche Bereitstellung eines Clients für Ihre Endpunkte nicht.

In den meisten Fällen müssen Sie jedoch weiterhin den Schutzdienst auf Ihren Endpunkten mit Microsoft Intune, Microsoft Endpoint Configuration Manager, Azure Defender oder Gruppenrichtlinienobjekten aktivieren, was in der folgenden Tabelle beschrieben wird.

Außerdem werden weitere Links zu folgenden Informationen zu sehen sein:

- Verwalten des Microsoft Defender Antivirus-Schutzes, einschließlich der Verwaltung von Produkt- und Schutzupdates
- Berichterstellung zum Microsoft Defender Antivirus-Schutz

> [!IMPORTANT]
> In den meisten Fällen wird Microsoft Defender Antivirus von Windows 10 deaktiviert, wenn ein anderes Antivirenprodukt gefunden wird, das ausgeführt wird und auf dem neuesten Stand ist. Sie müssen Antivirenprodukte von Drittanbietern deaktivieren oder deinstallieren, bevor Microsoft Defender Antivirus funktioniert. Wenn Sie Antivirenprodukte von Drittanbietern erneut aktivieren oder installieren, wird Microsoft Defender Antivirus von Windows 10 automatisch deaktiviert.

Tool|Bereitstellungsoptionen (<a href="#fn2" id="ref2">2</a>)|Verwaltungsoptionen (netzwerkweite Konfiguration und Richtlinie oder Basisbereitstellung) ([3](#fn3))|Berichterstellungsoptionen  
---|---|---|---  
Microsoft Intune|[Hinzufügen von Endpunktschutzeinstellungen in Intune](/intune/endpoint-protection-configure)|[Konfigurieren von Einstellungen für Geräteeinschränkungen in Intune](/intune/device-restrictions-configure)| [Verwenden der Intune-Konsole zum Verwalten von Geräten](/intune/device-management)  
Microsoft Endpoint Manager ([1](#fn1))|Verwenden der [Endpoint Protection-Punktwebsitesystemrolle][] und [Aktivieren von Endpoint Protection mit benutzerdefinierten Clienteinstellungen][]|Mit [standardmäßigen und angepassten Antischantischungsrichtlinien][] [und Clientverwaltung][]|Mit dem standardmäßigen [Configuration Manager Monitoring Arbeitsbereich und][] [E-Mail-Benachrichtigungen][]  
Gruppenrichtlinie und Active Directory (in der Domäne)|Verwenden Sie ein Gruppenrichtlinienobjekt, um Konfigurationsänderungen zu bereitstellen und sicherzustellen, dass Microsoft Defender Antivirus aktiviert ist.|Verwenden von Gruppenrichtlinienobjekten (GpOs) zum [Konfigurieren von Updateoptionen][] für Microsoft Defender Antivirus und [Konfigurieren Windows Defender Features][]|Die Endpunktberichterstellung ist mit Gruppenrichtlinien nicht verfügbar. Sie können eine Liste von [Gruppenrichtlinien generieren,][] um zu ermitteln, ob Einstellungen oder Richtlinien nicht angewendet werden.
PowerShell|Bereitstellen mit Gruppenrichtlinie, Microsoft Endpoint Configuration Manager oder manuell auf einzelnen Endpunkten.|Verwenden Sie [die Cmdlets Set-MpPreference] und [Update-MpSignature,] die im Defender-Modul verfügbar sind.|Verwenden der entsprechenden [Get-Cmdlets, die im Defender-Modul verfügbar sind][]
Windows Windows-Verwaltungsinstrumentation|Bereitstellen mit Gruppenrichtlinie, Microsoft Endpoint Configuration Manager oder manuell auf einzelnen Endpunkten.|Verwenden der [Set-Methode der MSFT_MpPreference-Klasse][] und der [Update-Methode der MSFT_MpSignature-Klasse][]|Verwenden der [MSFT_MpComputerStatus-Klasse][] und der get-Methode der zugeordneten Klassen im [Windows Defender WMIv2-Anbieter][]
Microsoft Azure|Stellen Sie Microsoft Anmalware für Azure im Azure-Portal bereit, indem Sie Visual Studio Konfiguration virtueller Computer oder [Azure PowerShell-Cmdlets verwenden.](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios) Sie können den [Endpunktschutz auch in Azure Defender* installieren.](/azure/security-center/security-center-install-endpoint-protection)|Konfigurieren [von Microsoft Antischalware für virtuelle Computer und Clouddienste mit Azure PowerShell-Cmdlets](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) oder Verwenden [von Codebeispielen](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|Verwenden [Sie Microsoft Anmalware für virtuelle Computer und CloudDienste mit Azure PowerShell-Cmdlets,](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) um die Überwachung zu aktivieren. Sie können auch Verwendungsberichte in Azure Active Directory [][] überprüfen, um verdächtige Aktivitäten zu ermitteln, einschließlich des Berichts möglicherweise infizierter Geräte, und ein SIEM-Tool zum Melden von [Microsoft Defender Antivirus-Ereignissen][] konfigurieren und dieses Tool als App in AAD hinzufügen.

1. <span id="fn1" />Die Verfügbarkeit einiger Funktionen und Features, insbesondere im Zusammenhang mit cloudbasiertem Schutz, unterscheidet sich zwischen Microsoft Endpoint Manager (Current Branch) und System Center 2012 Configuration Manager. In dieser Bibliothek haben wir uns auf Windows 10, Windows Server 2016 und Microsoft Endpoint Manager (Current Branch) konzentriert. Eine Tabelle, in der die wichtigsten Unterschiede beschrieben werden, finden Sie [unter Use Microsoft cloud-provided protection in Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md) [(Zurück zur Tabelle)](#ref2)
  
2.  <span id="fn2" />In Windows 10 ist Microsoft Defender Antivirus eine Komponente, die ohne Installation oder Bereitstellung eines zusätzlichen Clients oder Diensts verfügbar ist. Sie wird automatisch aktiviert, wenn Antivirenprodukte von Drittanbietern entweder deinstalliert oder veraltet sind (mit Ausnahme[von Windows Server 2016](microsoft-defender-antivirus-on-windows-server.md)). Die herkömmliche Bereitstellung ist daher nicht erforderlich. Die Bereitstellung bezieht sich hier auf die Sicherstellung, dass die Microsoft Defender Antivirus-Komponente auf Endpunkten oder Servern verfügbar und aktiviert ist. [(Zurück zur Tabelle)](#ref2)

3. <span id="fn3" />Die Konfiguration von Features und Schutz, einschließlich der Konfiguration von Produkt- und Schutzupdates, wird im Abschnitt Konfigurieren von [Microsoft Defender Antivirus-Features](configure-notifications-microsoft-defender-antivirus.md) in dieser Bibliothek weiter beschrieben. [(Zurück zur Tabelle)](#ref2)

[Endpunktschutzpunkt-Standortsystemrolle]: /configmgr/protect/deploy-use/endpoint-protection-site-role
[Standardmäßige und angepasste Antischantischungsrichtlinien]:  /configmgr/protect/deploy-use/endpoint-antimalware-policies
[Clientverwaltung]:  /configmgr/core/clients/manage/manage-clients
[Aktivieren von Endpoint Protection mit benutzerdefinierten Clienteinstellungen]:  /configmgr/protect/deploy-use/endpoint-protection-configure-client
[Configuration Manager Monitoring Workspace]:  /configmgr/protect/deploy-use/monitor-endpoint-protection
[E-Mail-Benachrichtigungen]:  /configmgr/protect/deploy-use/endpoint-configure-alerts
[Deploy the Microsoft Intune client to endpoints]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune
[custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection
 [custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection 
[manage tasks]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#choose-management-tasks-for-endpoint-protection
[Monitor endpoint protection in the Microsoft Intune administration console]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#monitor-endpoint-protection
[Set-Methode der MSFT_MpPreference-Klasse]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[Updatemethode der MSFT_MpSignature-Klasse]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[MSFT_MpComputerStatus]:  /previous-versions/windows/desktop/defender/msft-mpcomputerstatus
[Windows Defender WMIv2-Anbieter]: /previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal
[Set-MpPreference]:  https://technet.microsoft.com/itpro/powershell/windows/defender/set-mppreference.md
[Update-MpSignature]: /powershell/module/defender/update-mpsignature
[Get-Cmdlets, die im Defender-Modul verfügbar sind]: /powershell/module/defender/
[Konfigurieren von Updateoptionen für Microsoft Defender Antivirus]: manage-updates-baselines-microsoft-defender-antivirus.md
[Konfigurieren Windows Defender Features]: configure-microsoft-defender-antivirus-features.md
[Gruppenrichtlinien zum Ermitteln, ob Einstellungen oder Richtlinien nicht angewendet werden]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[Möglicherweise infizierte Geräte]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[Microsoft Defender Antivirus-Ereignisse]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Thema | Beschreibung
---|---
[Bereitstellen und Aktivieren des Microsoft Defender Antivirus-Schutzes](deploy-microsoft-defender-antivirus.md) | Während der Client als Kernteil von Windows 10 installiert ist und die herkömmliche Bereitstellung nicht gilt, müssen Sie den Client auf Ihren Endpunkten weiterhin mit Microsoft Endpoint Configuration Manager, Microsoft Intune oder Gruppenrichtlinienobjekten aktivieren. 
[Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Basiswerten](manage-updates-baselines-microsoft-defender-antivirus.md) | Es gibt zwei Teile zum Aktualisieren von Microsoft Defender Antivirus: Aktualisieren des Clients auf Endpunkten (Produktupdates) und Aktualisieren der Sicherheitsintelligenz (Schutzupdates). Sie können Security Intelligence auf verschiedene Weise aktualisieren, indem Sie Microsoft Endpoint Configuration Manager, Gruppenrichtlinien, PowerShell und WMI verwenden.
[Überwachen und Melden des Microsoft Defender Antivirus-Schutzes](report-monitor-microsoft-defender-antivirus.md) | Sie können Microsoft Intune, Microsoft Endpoint Configuration Manager, das Update Compliance-Add-In für Microsoft Operations Management Suite oder ein SIEM-Produkt eines Drittanbieters (indem Sie Windows-Ereignisprotokolle verwenden) verwenden, um den Schutzstatus zu überwachen und Berichte zum Endpunktschutz zu erstellen.