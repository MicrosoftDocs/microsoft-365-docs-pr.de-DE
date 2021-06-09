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
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="b9207-104">Onboarding von Geräten ohne Internetzugriff auf Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b9207-104">Onboard devices without Internet access to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b9207-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b9207-105">**Applies to:**</span></span>
- [<span data-ttu-id="b9207-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b9207-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b9207-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9207-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b9207-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="b9207-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b9207-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b9207-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="b9207-110">Um Geräte ohne Internetzugriff zu integrieren, müssen Sie die folgenden allgemeinen Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="b9207-110">To onboard devices without Internet access, you'll need to take the following general steps:</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="b9207-111">Die folgenden Schritte gelten nur für Geräte, auf denen frühere Versionen von Windows ausgeführt werden, z. B.: Windows Server 2016 und früher oder Windows 8.1 und früher.</span><span class="sxs-lookup"><span data-stu-id="b9207-111">The steps below are applicable only to devices running previous versions of Windows such as: Windows Server 2016 and earlier or Windows 8.1 and earlier.</span></span>

> [!NOTE]
> - <span data-ttu-id="b9207-112">Ein OMS-Gatewayserver kann nicht als Proxy für getrennte Windows 10- oder Windows Server 2019-Geräte verwendet werden, wenn er über die Registrierung oder das Gruppenrichtlinienobjekt "TelemetryProxyServer" konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="b9207-112">An OMS gateway server cannot be used as proxy for disconnected Windows 10 or Windows Server 2019 devices when configured via 'TelemetryProxyServer' registry or GPO.</span></span>
> - <span data-ttu-id="b9207-113">Für Windows 10 oder Windows Server 2019 – obwohl Sie TelemetryProxyServer verwenden können, muss es auf ein Standardproxygerät oder eine Standardanwendung verweisen.</span><span class="sxs-lookup"><span data-stu-id="b9207-113">For Windows 10 or Windows Server 2019 - while you may use TelemetryProxyServer, it must point to a standard proxy device or appliance.</span></span>
> - <span data-ttu-id="b9207-114">Darüber hinaus müssen Windows 10 oder Windows Server 2019 in getrennten Umgebungen Zertifikatvertrauenslisten offline über eine interne Datei oder einen Webserver aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="b9207-114">In addition, Windows 10 or Windows Server 2019 in disconnected environments must be able to update Certificate Trust Lists offline via an internal file or web server.</span></span>
> - <span data-ttu-id="b9207-115">Weitere Informationen zum Offlineaktualisierung von CTLs finden Sie unter [Konfigurieren einer Datei oder eines Webservers zum Herunterladen der CTL-Dateien.](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)</span><span class="sxs-lookup"><span data-stu-id="b9207-115">For more information about updating CTLs offline, see [Configure a file or web server to download the CTL files](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span></span>

<span data-ttu-id="b9207-116">Weitere Informationen zu Onboardingmethoden finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="b9207-116">For more information about onboarding methods, see the following articles:</span></span>
- [<span data-ttu-id="b9207-117">Onboarding von früheren Windows-Versionen</span><span class="sxs-lookup"><span data-stu-id="b9207-117">Onboard previous versions of Windows</span></span>](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [<span data-ttu-id="b9207-118">Integrieren von Servern in den Microsoft Defender für Endpunktdienst</span><span class="sxs-lookup"><span data-stu-id="b9207-118">Onboard servers to the Microsoft Defender for Endpoint service</span></span>](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [<span data-ttu-id="b9207-119">Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="b9207-119">Configure device proxy and Internet connectivity settings</span></span>](/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a><span data-ttu-id="b9207-120">Lokale Geräte</span><span class="sxs-lookup"><span data-stu-id="b9207-120">On-premise devices</span></span>

- <span data-ttu-id="b9207-121">Richten Sie Azure Log Analytics (früher ALS OMS-Gateway bezeichnet) als Proxy oder Hub ein:</span><span class="sxs-lookup"><span data-stu-id="b9207-121">Setup Azure Log Analytics (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
  - [<span data-ttu-id="b9207-122">Azure Log Analytics-Agent</span><span class="sxs-lookup"><span data-stu-id="b9207-122">Azure Log Analytics Agent</span></span>](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - <span data-ttu-id="b9207-123">[Installieren und Konfigurieren Microsoft Monitoring Agent (MMA)-Point](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) to Defender for Endpoint Workspace key & ID</span><span class="sxs-lookup"><span data-stu-id="b9207-123">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>

- <span data-ttu-id="b9207-124">Offlinegeräte im selben Netzwerk von Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="b9207-124">Offline devices in the same network of Azure Log Analytics</span></span>
  -  <span data-ttu-id="b9207-125">Konfigurieren Sie MMA so, dass es auf Folgendes verweist:</span><span class="sxs-lookup"><span data-stu-id="b9207-125">Configure MMA to point to:</span></span>
     - <span data-ttu-id="b9207-126">Azure Log Analytics-IP als Proxy</span><span class="sxs-lookup"><span data-stu-id="b9207-126">Azure Log Analytics IP as a proxy</span></span>
     - <span data-ttu-id="b9207-127">Defender für Endpunkt-Arbeitsbereichsschlüssel &-ID</span><span class="sxs-lookup"><span data-stu-id="b9207-127">Defender for Endpoint workspace key & ID</span></span>

## <a name="azure-virtual-machines"></a><span data-ttu-id="b9207-128">Virtuelle Azure-Computer</span><span class="sxs-lookup"><span data-stu-id="b9207-128">Azure virtual machines</span></span>
- <span data-ttu-id="b9207-129">Konfigurieren und Aktivieren des [Azure Log Analytics-Arbeitsbereichs](/azure/azure-monitor/platform/gateway)</span><span class="sxs-lookup"><span data-stu-id="b9207-129">Configure and enable [Azure Log Analytics workspace](/azure/azure-monitor/platform/gateway)</span></span>

    - <span data-ttu-id="b9207-130">Richten Sie das Azure Log Analytics-Gateway (früher ALS OMS-Gateway bezeichnet) als Proxy oder Hub ein:</span><span class="sxs-lookup"><span data-stu-id="b9207-130">Setup Azure Log Analytics Gateway (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
      - [<span data-ttu-id="b9207-131">Azure Log Analytics-Gateway</span><span class="sxs-lookup"><span data-stu-id="b9207-131">Azure Log Analytics Gateway</span></span>](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - <span data-ttu-id="b9207-132">[Installieren und Konfigurieren Microsoft Monitoring Agent (MMA)-Point](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) to Defender for Endpoint Workspace key & ID</span><span class="sxs-lookup"><span data-stu-id="b9207-132">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>
    - <span data-ttu-id="b9207-133">Offline-Azure-VMs im selben Netzwerk des OMS-Gateways</span><span class="sxs-lookup"><span data-stu-id="b9207-133">Offline Azure VMs in the same network of OMS Gateway</span></span>
      - <span data-ttu-id="b9207-134">Konfigurieren der Azure Log Analytics-IP als Proxy</span><span class="sxs-lookup"><span data-stu-id="b9207-134">Configure Azure Log Analytics IP as a proxy</span></span>
      - <span data-ttu-id="b9207-135">Azure Log Analytics Workspace Key & ID</span><span class="sxs-lookup"><span data-stu-id="b9207-135">Azure Log Analytics Workspace Key & ID</span></span>

    - <span data-ttu-id="b9207-136">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="b9207-136">Azure Defender</span></span>
      - [<span data-ttu-id="b9207-137">Log Analytics-Arbeitsbereich für Sicherheitsrichtlinien \></span><span class="sxs-lookup"><span data-stu-id="b9207-137">Security Policy \> Log Analytics Workspace</span></span>](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [<span data-ttu-id="b9207-138">\>Bedrohungserkennung ermöglicht Defender für Endpunkt den Zugriff auf meine Daten</span><span class="sxs-lookup"><span data-stu-id="b9207-138">Threat Detection \> Allow Defender for Endpoint to access my data</span></span>](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        <span data-ttu-id="b9207-139">Weitere Informationen finden Sie unter [Arbeiten mit Sicherheitsrichtlinien.](/azure/security-center/tutorial-security-policy)</span><span class="sxs-lookup"><span data-stu-id="b9207-139">For more information, see [Working with security policies](/azure/security-center/tutorial-security-policy).</span></span>
