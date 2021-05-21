---
title: Wechseln zu Microsoft Defender for Endpoint – Vorbereiten
description: Dies ist Phase 1, Prepare, für die Migration zu Microsoft Defender for Endpoint.
keywords: migration, Microsoft Defender for Endpoint, edr
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
ms.topic: article
ms.custom: migrationguides
ms.date: 05/20/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 92dfc279344b003ab651110375982b0f065dfb0d
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594169"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>Wechseln zu Microsoft Defender for Endpoint – Phase 1: Vorbereiten

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![Phase 1: Vorbereiten](images/phase-diagrams/prepare.png)<br/>Phase 1: Vorbereiten | [![Phase 2: Einrichten](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Phase 2: Einrichten](switch-to-microsoft-defender-setup.md) | [![Phase 3: Onboarding](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Phase 3: Onboarding](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
|*Sie sind hier!*| | |

**Willkommen bei der Vorbereitungsphase des [Wechsels zu Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)**. 

Diese Migrationsphase umfasst die folgenden Schritte:

1. [Herunterladen und Bereitstellen von Updates auf den Geräten Ihrer Organisation](#get-and-deploy-updates-across-your-organizations-devices)
2. [Get Defender for Endpoint](#get-microsoft-defender-for-endpoint).
3. [Gewähren von Zugriff auf Microsoft Defender Security Center](#grant-access-to-the-microsoft-defender-security-center).
4. [Konfigurieren von Geräteproxy- und Internetkonnektivitätseinstellungen](#configure-device-proxy-and-internet-connectivity-settings).

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Herunterladen und Bereitstellen von Updates auf den Geräten Ihrer Organisation

Als bewährte Methode sollten Sie die Geräte und Endpunkte Ihrer Organisation auf dem neuesten Stand halten. Stellen Sie sicher, dass Ihre vorhandene Endpunktschutz- und Antivirenlösung auf dem neuesten Stand ist und dass die Betriebssysteme und Apps, die Ihre Organisation installiert hat, auch über die neuesten Updates verfügen. Wenn Sie dies jetzt tun, können Sie Probleme später bei der Migration zu Defender for Endpoint und Microsoft Defender Antivirus.

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>Stellen Sie sicher, dass Ihre vorhandene Lösung auf dem neuesten Stand ist.

Halten Sie Ihre vorhandene Endpunktschutzlösung auf dem neuesten Stand, und stellen Sie sicher, dass die Geräte Ihrer Organisation über die neuesten Sicherheitsupdates verfügen. 

Benötigen Sie Hilfe? Weitere Informationen finden Sie in der Dokumentation Ihres Lösungsanbieters.

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>Stellen Sie sicher, dass die Geräte Ihrer Organisation auf dem neuesten Stand sind

Benötigen Sie Hilfe beim Aktualisieren der Geräte Ihrer Organisation? Informationen finden Sie in den folgenden Ressourcen:

|Betriebssystem | Ressource |
|:--|:--|
|Windows |[Microsoft Update](https://www.update.microsoft.com) |
|macOS | [Aktualisieren der Software auf Ihrem Mac](https://support.apple.com/HT201541)|
|iOS |[Aktualisieren von iPhone, iPad oder iPod touch](https://support.apple.com/HT204204)|
|Android |[Überprüfen & Aktualisieren Ihrer Android-Version](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: Aktualisieren Ihres Systems](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint erhalten

Nachdem Sie nun die Geräte Ihrer Organisation aktualisiert haben, besteht der nächste Schritt in der Bereitstellung von Defender for Endpoint, dem Zuweisen von Lizenzen und der Bereitstellung des Diensts.

1. Kaufen oder testen Sie Defender for Endpoint noch heute. [Starten Sie eine kostenlose Testversion, oder fordern Sie ein Angebot an.](https://aka.ms/mdatp) 

2. Stellen Sie sicher, dass Ihre Lizenzen ordnungsgemäß bereitgestellt sind. [Überprüfen Sie den Lizenzstatus](production-deployment.md#check-license-state).

3. Richten Sie als globaler Administrator oder Sicherheitsadministrator Ihre dedizierte Cloudinstanz von Defender for Endpoint ein. Weitere [Informationen finden Sie unter Defender for Endpoint setup: Tenant configuration](production-deployment.md#tenant-configuration).

4. Wenn Endpunkte (z. B. Geräte) in Ihrer Organisation einen Proxy für den Zugriff auf das Internet verwenden, finden Sie weitere Informationen unter [Defender for Endpoint setup: Network configuration](production-deployment.md#network-configuration).
 
An diesem Punkt sind Sie bereit, Ihren Sicherheitsadministratoren und Sicherheitsoperatoren Zugriff zu gewähren, die die Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) verwenden. 

> [!NOTE]
> Die Microsoft Defender Security Center wird manchmal als Defender for Endpoint-Portal bezeichnet und kann unter zugegriffen [https://securitycenter.windows.com](https://securitycenter.windows.com) werden. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Gewähren von Zugriff auf Microsoft Defender Security Center

Im Microsoft Defender Security Center ( ) können Sie auf Features und Funktionen von [https://securitycenter.windows.com](https://securitycenter.windows.com) Defender for Endpoint zugreifen und diese konfigurieren. Weitere Informationen finden Sie unter [Overview of the Microsoft Defender Security Center](use.md).

Berechtigungen für die Microsoft Defender Security Center können entweder mithilfe grundlegender Berechtigungen oder rollenbasierter Zugriffssteuerung (RBAC) erteilt werden. Es wird empfohlen, rbAC zu verwenden, damit Sie eine genauere Kontrolle über Berechtigungen haben.

1. Planen Sie die Rollen und Berechtigungen für Ihre Sicherheitsadministratoren und Sicherheitsoperatoren. Weitere Informationen finden Sie unter [Rollenbasierte Zugriffssteuerung](prepare-deployment.md#role-based-access-control).

2. Einrichten und Konfigurieren von RBAC. Es wird empfohlen, [Intune](/mem/intune/fundamentals/what-is-intune) zum Konfigurieren von RBAC zu verwenden, insbesondere wenn Ihre Organisation eine Kombination aus Windows 10,macOS-, iOS- und Android-Geräten verwendet. Weitere [Informationen finden Sie unter Einrichten von RBAC mithilfe von Intune](/mem/intune/fundamentals/role-based-access-control).

    Wenn Ihre Organisation eine andere Methode als Intune erfordert, wählen Sie eine der folgenden Optionen aus:

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Erweiterte Gruppenrichtlinienverwaltung](/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](/windows-server/manage/windows-admin-center/overview)

3. Gewähren sie Zugriff auf Microsoft Defender Security Center. (Benötigen Sie Hilfe? Weitere [Informationen finden Sie unter Verwalten des Portalzugriffs mithilfe von RBAC](rbac.md)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Konfigurieren von Geräteproxy- und Internetkonnektivitätseinstellungen

Konfigurieren Sie Proxy- und Interneteinstellungen, um die Kommunikation zwischen Ihren Geräten und Defender for Endpoint zu aktivieren. Die folgende Tabelle enthält Links zu Ressourcen, die Sie zum Konfigurieren ihrer Proxy- und Interneteinstellungen für verschiedene Betriebssysteme und Funktionen verwenden können:

| Funktionen  | Betriebssystem | Ressourcen |
|:--|:--|:--|
| [Endpunkterkennung und -antwort](overview-endpoint-detection-response.md) (EDR) | [Windows 10](/windows/release-health/release-information) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Server 1803 oder höher](/windows-server/get-started/whats-new-in-windows-server-1803)  | [Konfigurieren von Computerproxy- und Internetkonnektivitätseinstellungen](configure-proxy-internet.md) |
| EDR | [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Konfigurieren von Proxy- und Internetkonnektivitätseinstellungen](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
| EDR  | macOS:<p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave)   | [Defender for Endpoint unter macOS: Netzwerkverbindungen](microsoft-defender-endpoint-mac.md#network-connections)  |
| [Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) | [Windows 10](/windows/release-health/release-information) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Server 1803 oder höher](/windows-server/get-started/whats-new-in-windows-server-1803) <p>[Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) | [Konfigurieren und Überprüfen von Microsoft Defender Antivirus-Netzwerkverbindungen](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
| Antivirus | macOS:<p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave) | [Defender for Endpoint unter macOS: Netzwerkverbindungen](microsoft-defender-endpoint-mac.md#network-connections) |
| Antivirus | Linux: <p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS oder höher LTS<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 | [Defender for Endpoint unter Linux: Netzwerkverbindungen](microsoft-defender-endpoint-linux.md#network-connections) |

## <a name="next-step"></a>Nächster Schritt

**Herzlichen Glückwunsch!** Sie haben die **Vorbereitungsphase des** [Wechsels zu Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)! abgeschlossen.

- [Fahren Sie mit dem Einrichten von Defender for Endpoint fort.](switch-to-microsoft-defender-setup.md)
