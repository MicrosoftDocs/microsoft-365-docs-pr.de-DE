---
title: McAfee zu Microsoft Defender for Endpoint – Vorbereiten
description: Dies ist Phase 1, Prepare, für die Migration von McAfee zu Microsoft Defender for Endpoint.
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
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 05/10/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 357301bff92bb34b55630d3e699c86268fb0b6de
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327366"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a>Migrieren von McAfee – Phase 1: Vorbereiten der Migration

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Phase 1: Vorbereiten](images/phase-diagrams/prepare.png)<br/>Phase 1: Vorbereiten |[![Phase 2: Einrichten](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[Phase 2: Einrichten](mcafee-to-microsoft-defender-setup.md) |[![Phase 3: Onboarding](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[Phase 3: Onboarding](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|*Sie sind hier!*| | |


**Willkommen bei der Vorbereitungsphase der Migration von [McAfee Endpoint Security (McAfee) zu Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)**. 

Diese Migrationsphase umfasst die folgenden Schritte:
1. [Herunterladen und Bereitstellen von Updates auf den Geräten Ihrer Organisation](#get-and-deploy-updates-across-your-organizations-devices)
2. [Microsoft Defender for Endpoint .](#get-microsoft-defender-for-endpoint)
3. [Gewähren von Zugriff auf das Microsoft Defender Security Center](#grant-access-to-the-microsoft-defender-security-center).
4. [Konfigurieren von Geräteproxy- und Internetkonnektivitätseinstellungen](#configure-device-proxy-and-internet-connectivity-settings).

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Herunterladen und Bereitstellen von Updates auf den Geräten Ihrer Organisation

Als bewährte Methode sollten Sie die Geräte und Endpunkte Ihrer Organisation auf dem neuesten Stand halten. Stellen Sie sicher, dass Ihre McAfee Endpoint Security (McAfee)-Lösung auf dem neuesten Stand ist und dass die Betriebssysteme und Apps, die Ihre Organisation verwendet, auch über die neuesten Updates verfügen. Wenn Sie dies jetzt tun, können Sie Probleme später bei der Migration zu Microsoft Defender for Endpoint und Microsoft Defender Antivirus vermeiden.

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a>Stellen Sie sicher, dass Ihre McAfee-Lösung auf dem neuesten Stand ist.

Halten Sie McAfee auf dem neuesten Stand, und stellen Sie sicher, dass die Geräte Ihrer Organisation über die neuesten Sicherheitsupdates verfügen. Benötigen Sie Hilfe? Hier sind einige McAfee-Ressourcen:

- [McAfee Enterprise-Produktdokumentation: Funktionsweise der Endpunktsicherheit](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [McAfee Knowledge Center Technical Article: Windows Security Center meldet gelegentlich fälschlicherweise, dass Endpoint Security bei der Ausführung unter Windows 10 deaktiviert ist](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [McAfee Knowledge Center Technical Article: Windows Security Center meldet, dass Endpoint Security deaktiviert ist, wenn Endpoint Security ausgeführt wird](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

- Ihr McAfee Support ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) )

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>Stellen Sie sicher, dass die Geräte Ihrer Organisation auf dem neuesten Stand sind

Benötigen Sie Hilfe beim Aktualisieren der Geräte Ihrer Organisation? Informationen finden Sie in den folgenden Ressourcen:

|Betriebssystem | Ressource |
|:--|:--|
|Windows |[Microsoft Update](https://www.update.microsoft.com) |
|macOS | [Aktualisieren der Software auf Ihrem Mac](https://support.apple.com/HT201541)|
|iOS |[Aktualisieren Ihres iPhones, iPads oder iPod touch](https://support.apple.com/HT204204)|
|Android |[Überprüfen & Aktualisieren Ihrer Android-Version](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: Aktualisieren Ihres Systems](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint erhalten

Nachdem Sie nun die Geräte Ihrer Organisation aktualisiert haben, besteht der nächste Schritt in der Bereitstellung von Microsoft Defender for Endpoint, dem Zuweisen von Lizenzen und der Bereitstellung des Diensts.

1. Kaufen oder testen Sie Microsoft Defender for Endpoint noch heute. [Starten Sie eine kostenlose Testversion, oder fordern Sie ein Angebot an.](https://aka.ms/mdatp) 

2. Stellen Sie sicher, dass Ihre Lizenzen ordnungsgemäß bereitgestellt sind. [Überprüfen Sie den Lizenzstatus](production-deployment.md#check-license-state).

3. Richten Sie als globaler Administrator oder Sicherheitsadministrator Ihre dedizierte Cloudinstanz von Microsoft Defender for Endpoint ein. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint setup: Tenant configuration](production-deployment.md#tenant-configuration).

4. Wenn Endpunkte (z. B. Geräte) in Ihrer Organisation einen Proxy für den Zugriff auf das Internet verwenden, finden Sie weitere Informationen unter [Microsoft Defender for Endpoint setup: Network configuration](production-deployment.md#network-configuration).
 
An diesem Punkt sind Sie bereit, Ihren Sicherheitsadministratoren und Sicherheitsoperatoren, die das Microsoft Defender Security Center ( ) verwenden, Zugriff zu [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) gewähren. 

> [!NOTE]
> Das Microsoft Defender Security Center wird manchmal als Microsoft Defender for Endpoint-Portal bezeichnet. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Gewähren von Zugriff auf das Microsoft Defender Security Center

Im Microsoft Defender Security Center ( ) können Sie auf Features und Funktionen von Microsoft Defender for Endpoint zugreifen und [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) diese konfigurieren. Weitere Informationen finden Sie [unter Übersicht über das Microsoft Defender Security Center](use.md).

Berechtigungen für das Microsoft Defender Security Center können entweder mithilfe grundlegender Berechtigungen oder rollenbasierter Zugriffssteuerung (RBAC) erteilt werden. Es wird empfohlen, rbAC zu verwenden, damit Sie eine genauere Kontrolle über Berechtigungen haben.

1. Planen Sie die Rollen und Berechtigungen für Ihre Sicherheitsadministratoren und Sicherheitsoperatoren. Weitere Informationen finden Sie unter [Rollenbasierte Zugriffssteuerung](prepare-deployment.md#role-based-access-control).

2. Einrichten und Konfigurieren von RBAC. Es wird empfohlen, [Intune](/mem/intune/fundamentals/what-is-intune) zum Konfigurieren von RBAC zu verwenden, insbesondere wenn Ihre Organisation eine Kombination aus Windows 10-, macOS-, iOS- und Android-Geräten verwendet. Weitere [Informationen finden Sie unter Einrichten von RBAC mithilfe von Intune](/mem/intune/fundamentals/role-based-access-control).

    Wenn Ihre Organisation eine andere Methode als Intune erfordert, wählen Sie eine der folgenden Optionen aus:
    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Erweiterte Gruppenrichtlinienverwaltung](/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](/windows-server/manage/windows-admin-center/overview)

3. Gewähren sie Zugriff auf das Microsoft Defender Security Center. (Benötigen Sie Hilfe? Weitere [Informationen finden Sie unter Verwalten des Portalzugriffs mithilfe von RBAC](rbac.md)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Konfigurieren von Geräteproxy- und Internetkonnektivitätseinstellungen

Konfigurieren Sie Proxy- und Interneteinstellungen, um die Kommunikation zwischen Ihren Geräten und Microsoft Defender for Endpoint zu aktivieren. Die folgende Tabelle enthält Links zu Ressourcen, die Sie zum Konfigurieren ihrer Proxy- und Interneteinstellungen für verschiedene Betriebssysteme und Funktionen verwenden können:

|Funktionen  | Betriebssystem | Ressourcen |
|--|--|--|
|[Endpunkterkennung und -antwort](overview-endpoint-detection-response.md) (EDR) |- [Windows 10](/windows/release-health/release-information) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 oder höher](/windows-server/get-started/whats-new-in-windows-server-1803)  |[Konfigurieren von Computerproxy- und Internetkonnektivitätseinstellungen](configure-proxy-internet.md) |
|EDR |- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Konfigurieren von Proxy- und Internetkonnektivitätseinstellungen](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)  |[Microsoft Defender for Endpoint unter macOS: Netzwerkverbindungen](microsoft-defender-endpoint-mac.md#network-connections) |
|[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) |- [Windows 10](/windows/release-health/release-information) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 oder höher](/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Konfigurieren und Überprüfen von Microsoft Defender Antivirus-Netzwerkverbindungen](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
|Antivirus |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra) |[Microsoft Defender for Endpoint unter macOS: Netzwerkverbindungen](microsoft-defender-endpoint-mac.md#network-connections) |
|Antivirus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS oder höher LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender for Endpoint unter Linux: Netzwerkverbindungen](microsoft-defender-endpoint-linux.md#network-connections) 

## <a name="next-step"></a>Nächster Schritt

**Herzlichen Glückwunsch!** Sie haben die **Vorbereitungsphase** der Migration von [McAfee zu Microsoft Defender for Endpoint abgeschlossen.](mcafee-to-microsoft-defender-migration.md#the-migration-process)

- [Fahren Sie mit dem Einrichten von Microsoft Defender for Endpoint fort.](mcafee-to-microsoft-defender-setup.md)
