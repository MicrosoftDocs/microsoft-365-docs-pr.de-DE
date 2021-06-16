---
title: Wechseln zu Microsoft Defender für Endpunkt – Vorbereiten
description: Dies ist Phase 1, Vorbereitung, für die Migration zu Microsoft Defender für Endpunkt.
keywords: Migration, Microsoft Defender für Endpunkt, edr
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
- m365solution-migratetomdatp
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: article
ms.custom: migrationguides
ms.date: 06/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 56a63c09690e28f0ca4990dcbcbcb6cfff7d5eef
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929503"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>Wechseln zu Microsoft Defender für Endpunkt – Phase 1: Vorbereiten

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![Phase 1: Vorbereiten](images/phase-diagrams/prepare.png)<br/>Phase 1: Vorbereiten | [![Phase 2: Einrichten](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Phase 2: Einrichten](switch-to-microsoft-defender-setup.md) | [![Phase 3: Onboarding](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Phase 3: Onboarding](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
|*Sie sind hier!*| | |

**Willkommen bei der Vorbereitungsphase des [Wechsels zu Defender für Endpunkt.](switch-to-microsoft-defender-migration.md#the-migration-process)** 

Diese Migrationsphase umfasst die folgenden Schritte:

1. [Abrufen und Bereitstellen von Updates auf den Geräten Ihrer Organisation](#get-and-deploy-updates-across-your-organizations-devices)
2. [Abrufen von Defender für Endpunkt](#get-microsoft-defender-for-endpoint).
3. [Gewähren Des Zugriffs auf die Microsoft Defender Security Center](#grant-access-to-the-microsoft-defender-security-center).
4. [Konfigurieren von Einstellungen für Geräteproxy und Internetverbindung.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Abrufen und Bereitstellen von Updates auf den Geräten Ihrer Organisation

Als bewährte Methode sollten Sie die Geräte und Endpunkte Ihrer Organisation auf dem neuesten Stand halten. Stellen Sie sicher, dass Ihre vorhandene Endpunktschutz- und Antivirenlösung auf dem neuesten Stand ist und dass die Betriebssysteme und Apps Ihrer Organisation ebenfalls über die neuesten Updates verfügen. Dadurch können Sie Probleme später während der Migration zu Defender für Endpunkt und Microsoft Defender Antivirus verhindern.

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>Stellen Sie sicher, dass Ihre vorhandene Lösung auf dem neuesten Stand ist.

Halten Sie Ihre vorhandene Endpunktschutzlösung auf dem neuesten Stand, und stellen Sie sicher, dass die Geräte Ihrer Organisation über die neuesten Sicherheitsupdates verfügen. 

Benötigen Sie Hilfe? Weitere Informationen finden Sie in der Dokumentation Ihres Lösungsanbieters.

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>Stellen Sie sicher, dass die Geräte Ihrer Organisation auf dem neuesten Stand sind.

Benötigen Sie Hilfe beim Aktualisieren der Geräte Ihrer Organisation? Informationen finden Sie in den folgenden Ressourcen:

|Os | Ressource |
|:--|:--|
|Windows |[Microsoft Update](https://www.update.microsoft.com) |
|macOS | [So aktualisieren Sie die Software auf Ihrem Mac](https://support.apple.com/HT201541)|
|iOS |[Aktualisieren der iPhone, iPad oder iPod-Toucheingabe](https://support.apple.com/HT204204)|
|Android |[Überprüfen & Aktualisieren Ihrer Android-Version](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: Aktualisieren des Systems](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>Abrufen von Microsoft Defender für Endpunkt

Nachdem Sie die Geräte Ihrer Organisation aktualisiert haben, besteht der nächste Schritt darin, Defender für Endpunkt abzurufen, Lizenzen zuzuweisen und sicherzustellen, dass der Dienst bereitgestellt wird.

1. Kaufen oder testen Sie Defender für Endpunkt noch heute. [Starten Sie eine kostenlose Testversion, oder fordern Sie ein Angebot an.](https://aka.ms/mdatp) 

2. Stellen Sie sicher, dass Ihre Lizenzen ordnungsgemäß bereitgestellt sind. [Überprüfen Sie Ihren Lizenzstatus.](production-deployment.md#check-license-state)

3. Richten Sie als globaler Administrator oder Sicherheitsadministrator Ihre dedizierte Cloudinstanz von Defender für Endpunkt ein. Siehe [Defender für Endpunkt-Setup: Mandantenkonfiguration.](production-deployment.md#tenant-configuration)

4. Wenn Endpunkte (z. B. Geräte) in Ihrer Organisation einen Proxy für den Zugriff auf das Internet verwenden, finden Sie weitere Informationen unter [Defender für Endpunkteinrichtung: Netzwerkkonfiguration.](production-deployment.md#network-configuration)
 
An diesem Punkt können Sie Ihren Sicherheitsadministratoren und Sicherheitsoperatoren Zugriff gewähren, die die Microsoft Defender Security Center ( ) verwenden. [https://securitycenter.windows.com](https://securitycenter.windows.com) 

> [!NOTE]
> Die Microsoft Defender Security Center wird manchmal als Defender für Endpunkt-Portal bezeichnet und kann unter aufgerufen [https://securitycenter.windows.com](https://securitycenter.windows.com) werden. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Gewähren des Zugriffs auf die Microsoft Defender Security Center

Die Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) ist der Ort, an dem Sie auf Features und Funktionen von Defender für Endpunkt zugreifen und diese konfigurieren. Weitere Informationen finden Sie unter [Übersicht über die Microsoft Defender Security Center](use.md).

Berechtigungen für die Microsoft Defender Security Center können mithilfe von Einfachberechtigungen oder rollenbasierter Zugriffssteuerung (Role-Based Access Control, RBAC) erteilt werden. Es wird empfohlen, RBAC zu verwenden, damit Sie eine präzisere Kontrolle über Berechtigungen haben.

1. Planen Sie die Rollen und Berechtigungen für Ihre Sicherheitsadministratoren und Sicherheitsoperatoren. Siehe [rollenbasierte Zugriffssteuerung.](prepare-deployment.md#role-based-access-control)

2. Einrichten und Konfigurieren von RBAC. Es wird empfohlen, [Intune](/mem/intune/fundamentals/what-is-intune) zum Konfigurieren von RBAC zu verwenden, insbesondere, wenn Ihre Organisation eine Kombination aus Windows 10-, macOS-, iOS- und Android-Geräten verwendet. Weitere Informationen finden Sie [unter Einrichten von RBAC mit Intune.](/mem/intune/fundamentals/role-based-access-control)

    Wenn Ihre Organisation eine andere Methode als Intune erfordert, wählen Sie eine der folgenden Optionen aus:

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Erweiterte Gruppenrichtlinienverwaltung](/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](/windows-server/manage/windows-admin-center/overview)

3. Gewähren sie Zugriff auf die Microsoft Defender Security Center. (Benötigen Sie Hilfe? Siehe ["Verwalten des Portalzugriffs mithilfe von RBAC").](rbac.md)

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Konfigurieren von Einstellungen für Geräteproxy und Internetverbindung

Um die Kommunikation zwischen Ihren Geräten und Defender für Endpunkt zu ermöglichen, konfigurieren Sie Proxy- und Interneteinstellungen. Die folgende Tabelle enthält Links zu Ressourcen, mit denen Sie Ihre Proxy- und Interneteinstellungen für verschiedene Betriebssysteme und Funktionen konfigurieren können:

| Funktionen  | Betriebssystem | Ressourcen |
|:--|:--|:--|
| [Endpunkterkennung und -antwort](overview-endpoint-detection-response.md) (EDR) | [Windows 10](/windows/release-health/release-information) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Server 1803 oder höher](/windows-server/get-started/whats-new-in-windows-server-1803)  | [Konfigurieren von Einstellungen für Computerproxys und Internetverbindung](configure-proxy-internet.md) |
| EDR | [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Konfigurieren von Proxy- und Internetverbindungseinstellungen](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
| EDR  | Macos:<p>11.3.1 (Big Sur)<p>10.15 (Git)<p>10.14 (Mojave)   | [Defender für Endpunkt unter macOS: Netzwerkverbindungen](microsoft-defender-endpoint-mac.md#network-connections)  |
| [Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) | [Windows 10](/windows/release-health/release-information) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Server 1803 oder höher](/windows-server/get-started/whats-new-in-windows-server-1803) <p>[Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) | [Konfigurieren und Überprüfen von Microsoft Defender Antivirus-Netzwerkverbindungen](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
| Antivirus | Macos:<p>11.3.1 (Big Sur)<p>10.15 (Git)<p>10.14 (Mojave) | [Defender für Endpunkt unter macOS: Netzwerkverbindungen](microsoft-defender-endpoint-mac.md#network-connections) |
| Antivirus | Linux: <p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS oder höher LTS<p>SLES ab 12 Jahren<p>Ubuntu 9+<p>Oracle Linux 7.2 | [Defender für Endpunkt unter Linux: Netzwerkverbindungen](microsoft-defender-endpoint-linux.md#network-connections) |

## <a name="next-step"></a>Nächster Schritt

**Herzlichen Glückwunsch!** Sie haben die **Vorbereitungsphase** des [Wechsels zu Defender für Endpunkt](switch-to-microsoft-defender-migration.md#the-migration-process)abgeschlossen!

- [Fahren Sie mit der Einrichtung von Defender für Endpunkt fort.](switch-to-microsoft-defender-setup.md)
