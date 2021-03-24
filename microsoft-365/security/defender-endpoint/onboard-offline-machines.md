---
title: Onboarding von Geräten ohne Internetzugriff auf Microsoft Defender for Endpoint
ms.reviewer: ''
description: Onboarding von Geräten ohne Internetverbindung, sodass sie Sensordaten an den Microsoft Defender ATP-Sensor senden können
keywords: onboard, server, vm, on-premise, oms gateway, log analytics, azure log analytics, mma
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: daf766113baf6c7a9b0a4649afdae8f88dacfd41
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061095"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Onboarding von Geräten ohne Internetzugriff auf Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Um Geräte ohne Internetzugriff zu integrieren, müssen Sie die folgenden allgemeinen Schritte ausführen:

> [!IMPORTANT] 
> Die folgenden Schritte gelten nur für Geräte mit früheren Versionen von Windows, z. B.: Windows Server 2016 und früher oder Windows 8.1 und früher.

> [!NOTE]
> - Ein OMS-Gatewayserver kann nicht als Proxy für getrennte Windows 10- oder Windows Server 2019-Geräte verwendet werden, wenn er über die TelemetryProxyServer-Registrierung oder das Gruppenrichtlinienobjekt konfiguriert wird.
> - Für Windows 10 oder Windows Server 2019 – Während Sie TelemetryProxyServer verwenden können, muss es auf ein Standardproxygerät oder eine Standardproxy-Appliance verweisen.
> - Darüber hinaus müssen Windows 10 oder Windows Server 2019 in getrennten Umgebungen in der Lage sein, Zertifikatvertrauenslisten offline über eine interne Datei oder einen Webserver zu aktualisieren.
> - Weitere Informationen zum Aktualisieren von CTLs im Offlinemodus finden Sie unter [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).

Weitere Informationen zu Onboardingmethoden finden Sie in den folgenden Artikeln:
- [Onboarding früherer Versionen von Windows](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Onboarding von Servern in den Microsoft Defender for Endpoint-Dienst](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a>Lokale Geräte

- Richten Sie Azure Log Analytics (früher als OMS-Gateway bekannt) ein, um als Proxy oder Hub zu fungieren:
  - [Azure Log Analytics Agent](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) zeigen auf Defender for Endpoint Workspace key & ID

- Offlinegeräte im gleichen Netzwerk von Azure Log Analytics
  -  Konfigurieren Sie MMA so, dass es auf:
     - Azure Log Analytics IP als Proxy
     - Defender for Endpoint workspace key & ID

## <a name="azure-virtual-machines"></a>Virtuelle Azure-Computer
- Konfigurieren und Aktivieren des [Azure Log Analytics-Arbeitsbereichs](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)

    - Richten Sie Azure Log Analytics Gateway (früher als OMS-Gateway bekannt) ein, um als Proxy oder Hub zu fungieren:
      - [Azure Log Analytics Gateway](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - [Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) zeigen auf Defender for Endpoint Workspace key & ID
    - Offline-Azure-VMs im gleichen Netzwerk des OMS-Gateways
      - Konfigurieren der Azure Log Analytics-IP als Proxy
      - Azure Log Analytics Workspace Key & ID

    - Azure Security Center (ASC)
      - [Security Policy \> Log Analytics Workspace](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [\>Bedrohungserkennung Ermöglichen des Zugriffs auf meine Daten durch Defender for Endpoint](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        Weitere Informationen finden Sie unter [Arbeiten mit Sicherheitsrichtlinien](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).
