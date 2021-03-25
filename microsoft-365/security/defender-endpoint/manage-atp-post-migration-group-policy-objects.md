---
title: Verwalten von Microsoft Defender for Endpoint mithilfe von Gruppenrichtlinienobjekten
description: Informationen zum Verwalten von Microsoft Defender for Endpoint mit Gruppenrichtlinienobjekten
keywords: nach der Migration, verwalten, Betrieb, Wartung, Auslastung, PowerShell, windows defender advanced threat protection, atp, edr
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
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: c21ac21f4369934375d44f5792afb874070ab074
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068543"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Verwalten von Microsoft Defender for Endpoint mit Gruppenrichtlinienobjekten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> Wir empfehlen die [Verwendung von Microsoft Endpoint Manager](https://docs.microsoft.com/mem) zum Verwalten der Bedrohungsschutzfeatures Ihrer Organisation für Geräte (auch als Endpunkte bezeichnet). Endpoint Manager umfasst [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) und Microsoft Endpoint [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction). **[Erfahren Sie mehr über Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)**. 

Sie können Gruppenrichtlinienobjekte in Azure Active Directory Domain Services verwenden, um einige Einstellungen in Microsoft Defender for Endpoint zu verwalten.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Konfigurieren von Microsoft Defender for Endpoint mit Gruppenrichtlinienobjekten

In der folgenden Tabelle sind verschiedene Aufgaben aufgeführt, die Sie zum Konfigurieren von Microsoft Defender for Endpoint mit Gruppenrichtlinienobjekten ausführen können.

|Aufgabe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|**Verwalten von Einstellungen für Benutzer- und Computerobjekte** <br/><br/>*Passen Sie integrierte Gruppenrichtlinienobjekte an, oder erstellen Sie benutzerdefinierte Gruppenrichtlinienobjekte und Organisationseinheiten, die Ihren Organisatorischen Anforderungen entsprechen.*     |[Verwalten von Gruppenrichtlinien in einer verwalteten Azure Active Directory Domain Services-Domäne](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)   |
|**Konfigurieren von Microsoft Defender Antivirus** <br/><br/>*Konfigurieren Von Antivirusfeatures & Funktionen, einschließlich Richtlinieneinstellungen, Ausschlüssen, Korrekturen und geplanten Scans auf den Geräten Ihrer Organisation (auch als Endpunkte bezeichnet).*   |[Konfigurieren und Verwalten von Microsoft Defender Antivirus mithilfe von Gruppenrichtlinieneinstellungen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[Verwenden von Gruppenrichtlinien zum Aktivieren des in der Cloud übermittelten Schutzes](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**Verwalten der Regeln zur Reduzierung der Angriffsfläche In Ihrer Organisation** <br/><br/>*Passen Sie Ihre Regeln für die Reduzierung der Angriffsfläche an, indem Sie Dateien & oder benutzerdefinierten Text zu Benachrichtigungsbenachrichtigungen hinzufügen, die auf den Geräten der Benutzer angezeigt werden.* |[Anpassen von Regeln zur Reduzierung der Angriffsfläche mit Gruppenrichtlinienobjekten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**Verwalten von Exploitschutzeinstellungen**<br/><br/>*Sie können Ihre Exploitschutzeinstellungen anpassen, eine Konfigurationsdatei importieren und dann gruppenrichtlinien zum Bereitstellen dieser Konfigurationsdatei verwenden.*  |[Anpassen der Einstellungen für den Exploitschutz](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[Importieren, Exportieren und Bereitstellen von Exploitschutzkonfigurationen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[Verwenden von Gruppenrichtlinien zum Verteilen der Konfiguration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**Aktivieren von Netzwerkschutz,** um Zu verhindern, dass Mitarbeiter Apps verwenden, die schädliche Inhalte im Internet enthalten <br/><br/>*Es wird empfohlen, [zunächst den Überwachungsmodus](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) für den Netzwerkschutz in einer Testumgebung zu verwenden, um zu sehen, welche Apps vor dem Roll out blockiert werden.* |[Aktivieren des Netzwerkschutzes mithilfe von Gruppenrichtlinien](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**Konfigurieren des kontrollierten Ordnerzugriffs** zum Schutz vor Ransomware <br/><br/>*[Der kontrollierte Ordnerzugriff](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) wird auch als Antiransomwareschutz bezeichnet.*  |[Aktivieren des kontrollierten Ordnerzugriffs mithilfe von Gruppenrichtlinien](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**Konfigurieren Sie Microsoft Defender SmartScreen** zum Schutz vor schädlichen Websites und Dateien im Internet.  |[Konfigurieren von Microsoft Defender SmartScreen-Gruppenrichtlinien und Einstellungen für die mobile Geräteverwaltung (Mobile Device Management, MDM) mithilfe von Gruppenrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**Konfigurieren von Verschlüsselung und BitLocker** zum Schutz von Informationen auf den Geräten Ihrer Organisation unter Windows |[BitLocker-Gruppenrichtlinieneinstellungen](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**Konfigurieren von Microsoft Defender Credential Guard** zum Schutz vor Angriffen auf den Diebstahl von Anmeldeinformationen |[Aktivieren Windows Defender Credential Guard mithilfe von Gruppenrichtlinien](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurieren Ihres Microsoft Defender Security Center

Wenn Sie dies noch nicht getan haben, konfigurieren Sie **Ihr Microsoft Defender Security Center** ( ) so, dass Warnungen angezeigt, Bedrohungsschutzfeatures konfiguriert und detaillierte Informationen zur allgemeinen Sicherheitslage Ihrer Organisation angezeigt [https://securitycenter.windows.com](https://securitycenter.windows.com) werden. 

Sie können auch konfigurieren, ob und welche Features Endbenutzer im Microsoft Defender Security Center sehen können.

- [Übersicht über das Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Endpunktschutz: Microsoft Defender Security Center](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Nächste Schritte

- [Verschaffen Sie sich einen Überblick über die Verwaltung von Bedrohungen und Sicherheitslücken](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besuchen Sie das Microsoft Defender Security Center Security Center Security Operations Dashboard](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Verwalten von Microsoft Defender for Endpoint mit Intune](manage-atp-post-migration-intune.md)
