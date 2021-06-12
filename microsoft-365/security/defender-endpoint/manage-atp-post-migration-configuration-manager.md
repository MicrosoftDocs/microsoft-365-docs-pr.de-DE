---
title: Verwalten von Microsoft Defender für Endpunkt mit configuration Manager
description: Erfahren Sie, wie Sie Microsoft Defender für Endpunkt mit Configuration Manager verwalten
keywords: nach der Migration, verwalten, Vorgänge, Wartung, Nutzung, Configuration Manager, Microsoft Defender für Endpunkt, edr
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
ms.openlocfilehash: 5fde3bfad69a5851dd94b76afb262f8be12d0360
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908257"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Verwalten von Microsoft Defender für Endpunkt mit Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Es wird empfohlen, [Microsoft Endpoint Manager](/mem)zu verwenden, die [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) und [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) zum Verwalten der Bedrohungsschutzfeatures Ihrer Organisation für Geräte (auch als Endpunkte bezeichnet) umfasst. 
- [Weitere Informationen zu Endpoint Manager](/mem/endpoint-manager-overview)
- [Gemeinsame Verwaltung von Microsoft Defender für Endpunkt auf Windows 10 Geräten mit Configuration Manager und Intune](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Konfigurieren von Microsoft Defender für Endpunkt mit Configuration Manager

|Aufgabe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|**Installieren sie die Configuration Manager-Konsole,** wenn sie noch nicht vorhanden ist<br/><br/>*Wenn Sie noch nicht über die Configuration Manger-Konsole verfügen, verwenden Sie diese Ressourcen, um die Bits abzurufen und zu installieren.* |[Abrufen der Installationsmedien](/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Installieren der Configuration Manager-Konsole](/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Verwenden von Configuration Manager zum Onboarding von Geräten** in Microsoft Defender für Endpunkt <br/><br/> *Wenn Sie Geräte (oder Endpunkte) noch nicht in Microsoft Defender für Endpunkt integriert haben, können Sie dies mit Configuration Manager tun.*   |[Onboarding in Microsoft Defender für Endpunkt mit Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**Verwalten von Antischadsoftwarerichtlinien und Windows Firewallsicherheit** für Clientcomputer (Endpunkte)<br/><br/>*Konfigurieren Sie Endpunktschutzfeatures, einschließlich Microsoft Defender für Endpunkt, Exploit-Schutz, Anwendungssteuerung, Antischadsoftware, Firewalleinstellungen und mehr.*  |[Configuration Manager: Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**Auswählen von Methoden zum Aktualisieren von Antischadsoftwareupdates** auf den Geräten Ihrer Organisation <br/><br/>*Mit Endpoint Protection in Configuration Manager können Sie aus mehreren Methoden wählen, um Antischadsoftwaredefinitionen auf den Geräten Ihrer Organisation auf dem neuesten Stand zu halten.* |[Konfigurieren von Definitionsupdates für Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Verwenden von Configuration Manager zum Bereitstellen von Definitionsupdates](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**Aktivieren von Netzwerkschutz,** um zu verhindern, dass Mitarbeiter Apps verwenden, die schädliche Inhalte im Internet enthalten <br/><br/>*Es wird empfohlen, zunächst den [Überwachungsmodus](/microsoft-365/security/defender-endpoint/evaluate-network-protection) für den Netzwerkschutz in einer Testumgebung zu verwenden, um zu sehen, welche Apps vor dem Rollout blockiert werden.* |[Aktivieren des Netzwerkschutzes mit Configuration Manager](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**Konfigurieren des kontrollierten Ordnerzugriffs** zum Schutz vor Ransomware <br/><br/>*Der kontrollierte Ordnerzugriff wird auch als Antiransomware-Schutz bezeichnet.*   |[Endpunktschutz: Kontrollierter Ordnerzugriff](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Aktivieren des kontrollierten Ordnerzugriffs in microsoft Endpoint Configuration Manage](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurieren Ihrer Microsoft Defender Security Center

Wenn sie dies noch nicht getan haben, konfigurieren Sie Ihr Microsoft 365 Defender-Portal so, dass Warnungen angezeigt werden, Bedrohungsschutzfeatures konfiguriert und detaillierte Informationen zum allgemeinen Sicherheitsstatus Ihrer Organisation angezeigt werden. Siehe [Microsoft Defender Security Center](microsoft-defender-security-center.md). Sie können auch konfigurieren, ob und welche Features Endbenutzern im Microsoft 365 Defender-Portal angezeigt werden können.

- [Übersicht über die Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/use)

- [Endpunktschutz: Microsoft Defender Security Center](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Nächste Schritte

- [Übersicht über Bedrohungs- und Sicherheitsrisikomanagement](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besuchen Sie das Dashboard für Microsoft Defender Security Center Sicherheitsvorgänge.](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Verwalten von Microsoft Defender für Endpunkt mit Intune](manage-atp-post-migration-intune.md)
