---
title: Symantec to Microsoft Defender for Endpoint – Phase 1, Preparing
description: Dies ist Phase 1, Prepare, der Migration von Symantec zu Microsoft Defender for Endpoint.
keywords: Migration, windows defender advanced threat protection, atp, edr
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 8c8f91448415bc1e9490706ee23bd8cae7f51a63
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698244"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>Migrieren von Symantec – Phase 1: Vorbereiten der Migration

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Phase 1: Vorbereiten](images/phase-diagrams/prepare.png)<br/>Phase 1: Vorbereiten |[![Phase 2: Einrichten](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Phase 2: Einrichten](symantec-to-microsoft-defender-atp-setup.md) |[![Phase 3: Onboarding](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Phase 3: Onboarding](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*Sie sind hier!*| | |


**Willkommen bei der Vorbereitungsphase der [Migration von Symantec zu Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**. 

Diese Migrationsphase umfasst die folgenden Schritte:
1. [Microsoft Defender for Endpoint .](#get-microsoft-defender-for-endpoint)
2. [Gewähren von Zugriff auf das Microsoft Defender Security Center](#grant-access-to-the-microsoft-defender-security-center).
3. [Konfigurieren von Geräteproxy- und Internetkonnektivitätseinstellungen](#configure-device-proxy-and-internet-connectivity-settings).

## <a name="get-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint erhalten

Für die ersten Schritte müssen Sie Microsoft Defender for Endpoint mit zugewiesenen und bereitgestellten Lizenzen haben.

1. Kaufen oder testen Sie Microsoft Defender for Endpoint noch heute. [Besuchen Sie Microsoft Defender for Endpoint, um eine kostenlose Testversion zu starten oder ein Angebot an.](https://aka.ms/mdatp) 
2. Stellen Sie sicher, dass Ihre Lizenzen ordnungsgemäß bereitgestellt sind. [Überprüfen Sie den Lizenzstatus](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state).
3. Richten Sie als globaler Administrator oder Sicherheitsadministrator Ihre dedizierte Cloudinstanz von Microsoft Defender for Endpoint ein. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint setup: Tenant configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration).
4. Wenn Endpunkte (z. B. Geräte) in Ihrer Organisation einen Proxy für den Zugriff auf das Internet verwenden, finden Sie weitere Informationen unter [Microsoft Defender for Endpoint setup: Network configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration).
 
An diesem Punkt sind Sie bereit, Ihren Sicherheitsadministratoren und Sicherheitsoperatoren, die das Microsoft Defender Security Center ( ) verwenden, Zugriff zu [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) gewähren. 

> [!NOTE]
> Das Microsoft Defender Security Center wird manchmal als Microsoft Defender for Endpoint-Portal bezeichnet. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Gewähren von Zugriff auf das Microsoft Defender Security Center

Im Microsoft Defender Security Center ( ) können Sie auf Features und Funktionen von Microsoft Defender for Endpoint zugreifen und [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) diese konfigurieren. Weitere Informationen finden Sie [unter Übersicht über das Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use).

Berechtigungen für das Microsoft Defender Security Center können entweder mithilfe grundlegender Berechtigungen oder rollenbasierter Zugriffssteuerung (RBAC) erteilt werden. Es wird empfohlen, rbAC zu verwenden, damit Sie eine genauere Kontrolle über Berechtigungen haben.

1. Planen Sie die Rollen und Berechtigungen für Ihre Sicherheitsadministratoren und Sicherheitsoperatoren. Weitere Informationen finden Sie unter [Rollenbasierte Zugriffssteuerung](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control).
2. Einrichten und Konfigurieren von RBAC. Es wird empfohlen, [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) zum Konfigurieren von RBAC zu verwenden, insbesondere wenn Ihre Organisation eine Kombination aus Windows 10-, macOS-, iOS- und Android-Geräten verwendet. Weitere [Informationen finden Sie unter Einrichten von RBAC mithilfe von Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).<br/>
   Wenn Ihre Organisation eine andere Methode als Intune erfordert, wählen Sie eine der folgenden Optionen aus:
    - [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Erweiterte Gruppenrichtlinienverwaltung](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)
3. Gewähren sie Zugriff auf das Microsoft Defender Security Center. (Benötigen Sie Hilfe? Weitere [Informationen finden Sie unter Verwalten des Portalzugriffs mithilfe von RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Konfigurieren von Geräteproxy- und Internetkonnektivitätseinstellungen

Konfigurieren Sie Proxy- und Interneteinstellungen, um die Kommunikation zwischen Ihren Geräten und Microsoft Defender for Endpoint zu aktivieren. Die folgende Tabelle enthält Links zu Ressourcen, die Sie zum Konfigurieren ihrer Proxy- und Interneteinstellungen für verschiedene Betriebssysteme und Funktionen verwenden können:

|Funktionen  | Betriebssystem | Ressourcen |
|:----|:----|:---|
|[Endpunkterkennung und -antwort](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 oder höher](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[Konfigurieren von Computerproxy- und Internetkonnektivitätseinstellungen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Konfigurieren von Proxy- und Internetkonnektivitätseinstellungen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra)  |[Microsoft Defender for Endpoint unter macOS: Netzwerkverbindungen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 oder höher](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[Konfigurieren und Validieren von Microsoft Defender Antivirus-Netzwerkverbindungen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|Antivirus |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra) |[Microsoft Defender for Endpoint auf Mac: Netzwerkverbindungen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|Antivirus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS oder höher LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender for Endpoint unter Linux: Netzwerkverbindungen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections)  |

## <a name="next-step"></a>Nächster Schritt

**Herzlichen Glückwunsch!** Sie haben die **Vorbereitungsphase** der [Migration von Symantec zu Microsoft Defender for Endpoint abgeschlossen.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)
- [Fahren Sie mit dem Einrichten von Microsoft Defender for Endpoint fort.](symantec-to-microsoft-defender-atp-setup.md)
