---
title: Onboarding von Geräten ohne Internetzugriff auf Microsoft Defender für Endpunkt
ms.reviewer: ''
description: Integrieren von Geräten ohne Internetzugriff, sodass sie Sensordaten an den Microsoft Defender für Endpunkt-Sensor senden können
keywords: Onboarding, Server, vm, lokal, OMS-Gateway, Protokollanalyse, Azure-Protokollanalyse, mma
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
ms.openlocfilehash: ed33f67695fddc78c0bac646f72ca0c48887bb04
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844418"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Onboarding von Geräten ohne Internetzugriff auf Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Um Geräte ohne Internetzugriff zu integrieren, müssen Sie die folgenden allgemeinen Schritte ausführen:

> [!IMPORTANT] 
> Die folgenden Schritte gelten nur für Geräte, auf denen frühere Versionen von Windows ausgeführt werden, z. B.: Windows Server 2016 und früher oder Windows 8.1 und früher.

> [!NOTE]
> - Ein OMS-Gatewayserver kann nicht als Proxy für getrennte Windows 10- oder Windows Server 2019-Geräte verwendet werden, wenn er über die Registrierung oder das Gruppenrichtlinienobjekt "TelemetryProxyServer" konfiguriert wird.
> - Für Windows 10 oder Windows Server 2019 – obwohl Sie TelemetryProxyServer verwenden können, muss es auf ein Standardproxygerät oder eine Standardanwendung verweisen.
> - Darüber hinaus müssen Windows 10 oder Windows Server 2019 in getrennten Umgebungen Zertifikatvertrauenslisten offline über eine interne Datei oder einen Webserver aktualisieren können.
> - Weitere Informationen zum Offlineaktualisierung von CTLs finden Sie unter [Konfigurieren einer Datei oder eines Webservers zum Herunterladen der CTL-Dateien.](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)

Weitere Informationen zu Onboardingmethoden finden Sie in den folgenden Artikeln:
- [Onboarding von früheren Windows-Versionen](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Integrieren von Servern in den Microsoft Defender für Endpunktdienst](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen](/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a>Lokale Geräte

- Richten Sie Azure Log Analytics (früher ALS OMS-Gateway bezeichnet) als Proxy oder Hub ein:
  - [Azure Log Analytics-Agent](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [Installieren und Konfigurieren Microsoft Monitoring Agent (MMA)-Point](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) to Defender for Endpoint Workspace key & ID

- Offlinegeräte im selben Netzwerk von Azure Log Analytics
  -  Konfigurieren Sie MMA so, dass es auf Folgendes verweist:
     - Azure Log Analytics-IP als Proxy
     - Defender für Endpunkt-Arbeitsbereichsschlüssel &-ID

## <a name="azure-virtual-machines"></a>Virtuelle Azure-Computer
- Konfigurieren und Aktivieren des [Azure Log Analytics-Arbeitsbereichs](/azure/azure-monitor/platform/gateway)

    - Richten Sie das Azure Log Analytics-Gateway (früher ALS OMS-Gateway bezeichnet) als Proxy oder Hub ein:
      - [Azure Log Analytics-Gateway](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - [Installieren und Konfigurieren Microsoft Monitoring Agent (MMA)-Point](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) to Defender for Endpoint Workspace key & ID
    - Offline-Azure-VMs im selben Netzwerk des OMS-Gateways
      - Konfigurieren der Azure Log Analytics-IP als Proxy
      - Azure Log Analytics Workspace Key & ID

    - Azure Defender
      - [Log Analytics-Arbeitsbereich für Sicherheitsrichtlinien \>](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [\>Bedrohungserkennung ermöglicht Defender für Endpunkt den Zugriff auf meine Daten](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        Weitere Informationen finden Sie unter [Arbeiten mit Sicherheitsrichtlinien.](/azure/security-center/tutorial-security-policy)
