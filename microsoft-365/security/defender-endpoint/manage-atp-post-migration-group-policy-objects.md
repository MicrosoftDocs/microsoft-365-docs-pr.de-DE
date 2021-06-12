---
title: Verwalten von Microsoft Defender für Endpunkt mithilfe von Gruppenrichtlinienobjekten
description: Erfahren Sie, wie Sie Microsoft Defender für Endpunkt mit Gruppenrichtlinienobjekten verwalten
keywords: nach der Migration, verwalten, Vorgänge, Wartung, Nutzung, PowerShell, Microsoft Defender für Endpunkt, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: ce204c1a90e57a651cf9c97974a8b35d405878cc
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908292"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Verwalten von Microsoft Defender für Endpunkt mit Gruppenrichtlinienobjekten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> Es wird empfohlen, [Microsoft Endpoint Manager](/mem) zu verwenden, um die Bedrohungsschutzfeatures Ihrer Organisation für Geräte (auch als Endpunkte bezeichnet) zu verwalten. Endpoint Manager enthält [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) und [Microsoft Endpoint Configuration Manager.](/mem/configmgr/core/understand/introduction) **[Weitere Informationen zu Endpoint Manager](/mem/endpoint-manager-overview)**. 

Sie können Gruppenrichtlinienobjekte in Azure Active Directory Domänendiensten verwenden, um einige Einstellungen in Microsoft Defender für Endpunkt zu verwalten.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Konfigurieren von Microsoft Defender für Endpunkt mit Gruppenrichtlinienobjekten

In der folgenden Tabelle sind verschiedene Aufgaben aufgeführt, die Sie ausführen können, um Microsoft Defender für Endpunkt mit Gruppenrichtlinienobjekten zu konfigurieren.

|Aufgabe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|**Verwalten von Einstellungen für Benutzer- und Computerobjekte** <br/><br/>*Passen Sie integrierte Gruppenrichtlinienobjekte an, oder erstellen Sie benutzerdefinierte Gruppenrichtlinienobjekte und Organisationseinheiten, die Ihren Organisatorischen Anforderungen entsprechen.*     |[Verwalten von Gruppenrichtlinien in einer Azure Active Directory verwalteten Domäne der Domänendienste](/azure/active-directory-domain-services/manage-group-policy)   |
|**Konfigurieren Microsoft Defender Antivirus** <br/><br/>*Konfigurieren Sie Antivirenfeatures & Funktionen, einschließlich Richtlinieneinstellungen, Ausschlüssen, Korrekturen und geplanten Scans auf den Geräten Ihrer Organisation (auch als Endpunkte bezeichnet).*   |[Verwenden von Gruppenrichtlinieneinstellungen zum Konfigurieren und Verwalten von Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[Verwenden von Gruppenrichtlinien zum Aktivieren des über die Cloud bereitgestellten Schutzes](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**Verwalten der Regeln zur Verringerung der Angriffsfläche In Ihrer Organisation** <br/><br/>*Passen Sie die Regeln zur Verringerung der Angriffsfläche an, indem Sie Dateien & Ordner ausschließen oder Benachrichtigungen, die auf den Geräten der Benutzer angezeigt werden, benutzerdefinierten Text hinzufügen.* |[Anpassen von Regeln zur Verringerung der Angriffsfläche mit Gruppenrichtlinienobjekten](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**Verwalten von Exploit-Schutzeinstellungen**<br/><br/>*Sie können Ihre Exploit-Schutzeinstellungen anpassen, eine Konfigurationsdatei importieren und dann gruppenrichtlinien verwenden, um diese Konfigurationsdatei bereitzustellen.*  |[Anpassen von Exploit-Schutzeinstellungen](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[Importieren, Exportieren und Bereitstellen von Konfigurationen für Exploit-Schutz](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[Verwenden von Gruppenrichtlinien zum Verteilen der Konfiguration](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**Aktivieren von Netzwerkschutz,** um zu verhindern, dass Mitarbeiter Apps verwenden, die schädliche Inhalte im Internet enthalten <br/><br/>*Es wird empfohlen, zunächst den [Überwachungsmodus](/microsoft-365/security/defender-endpoint/evaluate-network-protection) für den Netzwerkschutz in einer Testumgebung zu verwenden, um zu sehen, welche Apps vor dem Rollout blockiert werden.* |[Aktivieren des Netzwerkschutzes mithilfe von Gruppenrichtlinien](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**Konfigurieren des kontrollierten Ordnerzugriffs** zum Schutz vor Ransomware <br/><br/>*[Der kontrollierte Ordnerzugriff](/microsoft-365/security/defender-endpoint/controlled-folders) wird auch als Antiransomware-Schutz bezeichnet.*  |[Aktivieren des kontrollierten Ordnerzugriffs mithilfe von Gruppenrichtlinien](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**Konfigurieren Sie Microsoft Defender SmartScreen,** um vor schädlichen Websites und Dateien im Internet zu schützen.  |[Konfigurieren Microsoft Defender SmartScreen Gruppenrichtlinien und Einstellungen für die mobile Geräteverwaltung (Mobile Device Management, MDM) mithilfe von Gruppenrichtlinien](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**Konfigurieren von Verschlüsselung und BitLocker** zum Schutz von Informationen auf den Geräten Ihrer Organisation, auf denen Windows |[BitLocker Gruppenrichtlinieneinstellungen](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**Konfigurieren von Microsoft Defender Credential Guard** zum Schutz vor Angriffen durch Diebstahl von Anmeldeinformationen |[Aktivieren Windows Defender Credential Guard mithilfe von Gruppenrichtlinien](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurieren Ihrer Microsoft Defender Security Center

Wenn sie dies noch nicht getan haben, konfigurieren Sie Ihr Microsoft 365 Defender-Portal so, dass Warnungen angezeigt werden, Bedrohungsschutzfeatures konfiguriert und detaillierte Informationen zum allgemeinen Sicherheitsstatus Ihrer Organisation angezeigt werden. Siehe [Microsoft Defender Security Center](microsoft-defender-security-center.md). Sie können auch konfigurieren, ob und welche Features Endbenutzern im Microsoft 365 Defender-Portal angezeigt werden können.

- [Übersicht über die Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/use)

- [Endpunktschutz: Microsoft Defender Security Center](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Nächste Schritte

- [Übersicht über Bedrohungs- und Sicherheitsrisikomanagement](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besuchen Sie das Dashboard für Microsoft Defender Security Center Sicherheitsvorgänge.](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Verwalten von Microsoft Defender für Endpunkt mit Intune](manage-atp-post-migration-intune.md)
