---
title: Verwalten von Microsoft Defender for Endpoint mithilfe von Configuration Manager
description: Informationen zum Verwalten von Microsoft Defender for Endpoint mit Configuration Manager
keywords: nach der Migration, verwalten, Betrieb, Wartung, Auslastung, Configuration Manager, windows defender advanced threat protection, atp, edr
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
ms.openlocfilehash: bd6b6bd2721b686ab10922d09a9e94b9ebcce522
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185650"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Verwalten von Microsoft Defender for Endpoint mit Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Es wird empfohlen, [Microsoft Endpoint Manager](https://docs.microsoft.com/mem)zu verwenden, das Microsoft Intune [(Intune)](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) und Microsoft Endpoint Configuration Manager (Configuration [Manager)](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) umfasst, um die Bedrohungsschutzfeatures Ihrer Organisation für Geräte (auch als Endpunkte bezeichnet) zu verwalten. 
- [Weitere Informationen zu Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)
- [Co-manage Microsoft Defender for Endpoint auf Windows 10-Geräten mit Configuration Manager und Intune](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Konfigurieren von Microsoft Defender for Endpoint mit Configuration Manager

|Aufgabe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|**Installieren der Configuration Manager-Konsole,** wenn sie noch nicht vorhanden ist<br/><br/>*Wenn Sie noch nicht über die Configuration Manger-Konsole verfügen, verwenden Sie diese Ressourcen, um die Bits zu erhalten und zu installieren.* |[Installationsmedium erhalten](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Installieren der Configuration Manager-Konsole](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Verwenden von Configuration Manager zum Onboarding von Geräten** in Microsoft Defender for Endpoint <br/><br/> *Wenn Geräte (oder Endpunkte) noch nicht in Microsoft Defender for Endpoint onboarded sind, können Sie dies mit Configuration Manager tun.*   |[Onboarding bei Microsoft Defender for Endpoint mit Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**Verwalten von Antischalwarerichtlinien und Windows-Firewallsicherheit** für Clientcomputer (Endpunkte)<br/><br/>*Konfigurieren von Endpunktschutzfeatures, einschließlich Microsoft Defender for Endpoint, Exploit-Schutz, Anwendungssteuerung, Antischalware, Firewalleinstellungen und mehr.*  |[Configuration Manager: Endpoint Protection](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**Auswählen von Methoden zum Aktualisieren von Antischalwareupdates** auf den Geräten Ihrer Organisation <br/><br/>*Mit Endpoint Protection im Configuration Manager können Sie aus mehreren Methoden auswählen, um Antischalwaredefinitionen auf den Geräten Ihrer Organisation auf dem neuesten Stand zu halten.* |[Konfigurieren von Definitionsupdates für Endpoint Protection](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Bereitstellen von Definitionsupdates mithilfe von Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**Aktivieren von Netzwerkschutz,** um Zu verhindern, dass Mitarbeiter Apps verwenden, die schädliche Inhalte im Internet enthalten <br/><br/>*Es wird empfohlen, [zunächst den Überwachungsmodus](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) für den Netzwerkschutz in einer Testumgebung zu verwenden, um zu sehen, welche Apps vor dem Roll out blockiert werden.* |[Aktivieren des Netzwerkschutzes mit Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**Konfigurieren des kontrollierten Ordnerzugriffs** zum Schutz vor Ransomware <br/><br/>*Der kontrollierte Ordnerzugriff wird auch als Antiransomwareschutz bezeichnet.*   |[Endpunktschutz: Kontrollierter Ordnerzugriff](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Aktivieren des kontrollierten Ordnerzugriffs in Microsoft Endpoint Configuration Manage](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurieren Ihres Microsoft Defender Security Center

Wenn Sie dies noch nicht getan haben, konfigurieren Sie **Ihr Microsoft Defender Security Center** ( ) so, dass Warnungen angezeigt, Bedrohungsschutzfeatures konfiguriert und detaillierte Informationen zur allgemeinen Sicherheitslage Ihrer Organisation angezeigt [https://securitycenter.windows.com](https://securitycenter.windows.com) werden. 

Sie können auch konfigurieren, ob und welche Features Endbenutzer im Microsoft Defender Security Center sehen können.

- [Übersicht über das Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Endpunktschutz: Microsoft Defender Security Center](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Nächste Schritte

- [Verschaffen Sie sich einen Überblick über die Verwaltung von Bedrohungen und Sicherheitslücken](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besuchen Sie das Microsoft Defender Security Center Security Center Security Operations Dashboard](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Verwalten von Microsoft Defender for Endpoint mit Intune](manage-atp-post-migration-intune.md)
