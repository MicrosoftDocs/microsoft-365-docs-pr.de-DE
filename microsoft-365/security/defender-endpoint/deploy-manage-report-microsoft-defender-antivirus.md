---
title: Bereitstellen, Verwalten und Melden von Microsoft Defender Antivirus
description: Sie können Microsoft Defender Antivirus mit Intune, Microsoft Endpoint Configuration Manager, Gruppenrichtlinien, PowerShell oder WMI bereitstellen und verwalten.
keywords: bereitstellen, verwalten, aktualisieren, schützen, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 15fd70a2a60da7b0541446a98f0094c73c831d51
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289823"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Bereitstellen, Verwalten und Melden von Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können Microsoft Defender Antivirus auf verschiedene Arten bereitstellen, verwalten und berichten.

Da der Microsoft Defender Antivirus-Client als Kernteil der Windows 10 installiert ist, gilt die herkömmliche Bereitstellung eines Clients auf Ihren Endpunkten nicht.

In den meisten Fällen müssen Sie jedoch weiterhin den Schutzdienst auf Ihren Endpunkten mit Microsoft Intune- Microsoft Endpoint Configuration Manager-, Azure Defender- oder Gruppenrichtlinienobjekten aktivieren, was in der folgenden Tabelle beschrieben wird.

Außerdem werden zusätzliche Links für Folgendes angezeigt:

- Verwalten Microsoft Defender Antivirus Schutzes, einschließlich der Verwaltung von Produkt- und Schutzupdates
- Berichterstellung zum Microsoft Defender Antivirus-Schutz

> [!IMPORTANT]
> In den meisten Fällen deaktiviert Windows 10 Microsoft Defender Antivirus, wenn ein anderes Antivirenprodukt gefunden wird, das ausgeführt wird und auf dem neuesten Stand ist. Sie müssen Antivirenprodukte von Drittanbietern deaktivieren oder deinstallieren, bevor Microsoft Defender Antivirus funktioniert. Wenn Sie Antivirenprodukte von Drittanbietern erneut aktivieren oder installieren, deaktiviert Windows 10 automatisch Microsoft Defender Antivirus.

Tool|Bereitstellungsoptionen (<a href="#fn2" id="ref2">2</a>)|Verwaltungsoptionen (netzwerkweite Konfiguration und Richtlinie oder Basisplanbereitstellung) ([3](#fn3))|Berichtsoptionen  
---|---|---|---  
Microsoft Intune|[Hinzufügen von Endpunktschutzeinstellungen in Intune](/intune/endpoint-protection-configure)|[Konfigurieren von Geräteeinschränkungseinstellungen in Intune](/intune/device-restrictions-configure)| [Verwenden der Intune-Konsole zum Verwalten von Geräten](/intune/device-management)  
Microsoft Endpoint Manager ([1](#fn1))|Verwenden Sie die Endpoint Protection Rolle des [Punktwebsite-Systems,][] und [aktivieren Sie Endpoint Protection mit benutzerdefinierten Clienteinstellungen.][]|Mit [standardmäßigen und angepassten Richtlinien für Antischadsoftware][] und [Clientverwaltung][]|Mit dem standardmäßigen [Configuration Manager Monitoring-Arbeitsbereich][] und [E-Mail-Benachrichtigungen][]  
Gruppenrichtlinie und Active Directory (domänenverbunden)|Verwenden Sie ein Gruppenrichtlinienobjekt, um Konfigurationsänderungen bereitzustellen und sicherzustellen, dass Microsoft Defender Antivirus aktiviert ist.|Verwenden von Gruppenrichtlinienobjekten (Group Policy Objects, GPOs) zum [Konfigurieren von Updateoptionen für Microsoft Defender Antivirus][] und Konfigurieren Windows Defender [Features][]|Endpunktberichte sind mit Gruppenrichtlinien nicht verfügbar. Sie können eine Liste von [Gruppenrichtlinien generieren, um festzustellen, ob Einstellungen oder Richtlinien nicht angewendet werden.][]
PowerShell|Bereitstellen mit Gruppenrichtlinie, Microsoft Endpoint Configuration Manager oder manuell auf einzelnen Endpunkten.|Verwenden Sie die Cmdlets ["Set-MpPreference"] und ["Update-MpSignature",] die im Defender-Modul verfügbar sind.|Verwenden der entsprechenden [Get-Cmdlets, die im Defender-Modul verfügbar sind][]
Windows Windows-Verwaltungsinstrumentation|Bereitstellen mit Gruppenrichtlinie, Microsoft Endpoint Configuration Manager oder manuell auf einzelnen Endpunkten.|Verwenden Sie die [Set-Methode der MSFT_MpPreference-Klasse][] und die [Update-Methode der MSFT_MpSignature-Klasse.][]|Verwenden Sie die [MSFT_MpComputerStatus][] Klasse und die Get-Methode der zugeordneten Klassen im [Windows Defender WMIv2-Anbieter.][]
Microsoft Azure|Stellen Sie Microsoft Antimalware für Azure im [Azure-Portal bereit, indem Sie Visual Studio Konfiguration virtueller Computer oder Azure PowerShell Cmdlets verwenden.](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios) Sie können endpunktschutz auch [in Azure Defender* installieren.](/azure/security-center/security-center-install-endpoint-protection)|Konfigurieren [Microsoft Antimalware für virtuelle Computer und Clouddienste mit Azure PowerShell Cmdlets](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) oder Verwenden von [Codebeispielen](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|Verwenden Sie [Microsoft Antimalware für virtuelle Computer und Clouddienste mit Azure PowerShell Cmdlets,](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) um die Überwachung zu aktivieren. Sie können auch Nutzungsberichte in Azure Active Directory überprüfen, um verdächtige Aktivitäten zu ermitteln, einschließlich des Berichts [über möglicherweise infizierte Geräte,][] und ein SIEM-Tool konfigurieren, um [über Microsoft Defender Antivirus Ereignisse][] zu berichten und dieses Tool als App in AAD hinzuzufügen.

1. <span id="fn1" />Die Verfügbarkeit einiger Funktionen und Features, insbesondere im Zusammenhang mit dem über die Cloud bereitgestellten Schutz, unterscheidet sich zwischen Microsoft Endpoint Manager (Current Branch) und System Center 2012 Configuration Manager. In dieser Bibliothek haben wir uns auf Windows 10, Windows Server 2016 und Microsoft Endpoint Manager (Current Branch) konzentriert. Eine Tabelle, in der die wichtigsten Unterschiede beschrieben werden, finden Sie unter "Verwenden des in der [Cloud bereitgestellten Schutzes](cloud-protection-microsoft-defender-antivirus.md) von Microsoft in Microsoft Defender Antivirus". [(Zurück zur Tabelle)](#ref2)
  
2. <span id="fn2" />In Windows 10 ist Microsoft Defender Antivirus eine Komponente, die ohne Installation oder Bereitstellung eines zusätzlichen Clients oder Diensts verfügbar ist. Es wird automatisch aktiviert, wenn Antivirenprodukte von Drittanbietern entweder deinstalliert oder veraltet sind[(außer bei Windows Server 2016).](microsoft-defender-antivirus-on-windows-server.md) Die herkömmliche Bereitstellung ist daher nicht erforderlich. Die Bereitstellung bezieht sich hier darauf, sicherzustellen, dass die Microsoft Defender Antivirus Komponente auf Endpunkten oder Servern verfügbar und aktiviert ist. [(Zurück zur Tabelle)](#ref2)

3. <span id="fn3" />Die Konfiguration der Features und des Schutzes, einschließlich der Konfiguration von Produkt- und Schutzupdates, wird im Abschnitt ["Konfigurieren Microsoft Defender Antivirus Features"](configure-notifications-microsoft-defender-antivirus.md) in dieser Bibliothek weiter beschrieben. [(Zurück zur Tabelle)](#ref2)

[Endpoint Protection Rolle des Punktwebsitesystems]: /configmgr/protect/deploy-use/endpoint-protection-site-role
[Standardmäßige und angepasste Antischadsoftwarerichtlinien]:  /configmgr/protect/deploy-use/endpoint-antimalware-policies
[Clientverwaltung]:  /configmgr/core/clients/manage/manage-clients
[Aktivieren Endpoint Protection mit benutzerdefinierten Clienteinstellungen]:  /configmgr/protect/deploy-use/endpoint-protection-configure-client
[Configuration Manager Monitoring Workspace]:  /configmgr/protect/deploy-use/monitor-endpoint-protection
[E-Mail-Benachrichtigungen]:  /configmgr/protect/deploy-use/endpoint-configure-alerts
[Deploy the Microsoft Intune client to endpoints]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune
[custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection
 [custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection 
[manage tasks]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#choose-management-tasks-for-endpoint-protection
[Monitor endpoint protection in the Microsoft Intune administration console]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#monitor-endpoint-protection
[Set-Methode der MSFT_MpPreference-Klasse]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[Update-Methode der MSFT_MpSignature-Klasse]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[MSFT_MpComputerStatus]:  /previous-versions/windows/desktop/defender/msft-mpcomputerstatus
[Windows Defender WMIv2-Anbieter]: /previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal
[Set-MpPreference]:  https://technet.microsoft.com/itpro/powershell/windows/defender/set-mppreference.md
[Update-MpSignature]: /powershell/module/defender/update-mpsignature
[Get- Cmdlets, die im Defender-Modul verfügbar sind]: /powershell/module/defender/
[Konfigurieren von Updateoptionen für Microsoft Defender Antivirus]: manage-updates-baselines-microsoft-defender-antivirus.md
[Konfigurieren Windows Defender Features]: configure-microsoft-defender-antivirus-features.md
[Gruppenrichtlinien, um zu bestimmen, ob Einstellungen oder Richtlinien nicht angewendet werden]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[Möglicherweise infizierte Geräte]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[Microsoft Defender Antivirus-Ereignisse]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Thema | Beschreibung
---|---
[Bereitstellen und Aktivieren Microsoft Defender Antivirus Schutzes](deploy-microsoft-defender-antivirus.md) | Während der Client als Kernteil von Windows 10 installiert ist und die herkömmliche Bereitstellung nicht zutrifft, müssen Sie den Client auf Ihren Endpunkten mit Microsoft Endpoint Configuration Manager-, Microsoft Intune- oder Gruppenrichtlinienobjekten aktivieren. 
[Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen](manage-updates-baselines-microsoft-defender-antivirus.md) | Das Aktualisieren von Microsoft Defender Antivirus besteht aus zwei Teilen: Aktualisieren des Clients auf Endpunkten (Produktupdates) und Aktualisieren von Security Intelligence (Schutzupdates). Sie können die Security Intelligence auf verschiedene Arten aktualisieren, indem Sie Microsoft Endpoint Configuration Manager, Gruppenrichtlinien, PowerShell und WMI verwenden.
[Überwachen und Melden des Microsoft Defender Antivirus Schutzes](report-monitor-microsoft-defender-antivirus.md) | Sie können Microsoft Intune, Microsoft Endpoint Configuration Manager, das Updatecompliance-Add-In für Microsoft Operations Management Suite oder ein SIEM-Produkt eines Drittanbieters verwenden (indem Sie Windows Ereignisprotokolle verwenden), um den Schutzstatus zu überwachen und Berichte zum Endpunktschutz zu erstellen.