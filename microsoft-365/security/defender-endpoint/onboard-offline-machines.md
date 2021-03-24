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
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="76a08-104">Onboarding von Geräten ohne Internetzugriff auf Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="76a08-104">Onboard devices without Internet access to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="76a08-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="76a08-105">**Applies to:**</span></span>
- [<span data-ttu-id="76a08-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="76a08-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="76a08-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76a08-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="76a08-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="76a08-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="76a08-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="76a08-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="76a08-110">Um Geräte ohne Internetzugriff zu integrieren, müssen Sie die folgenden allgemeinen Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="76a08-110">To onboard devices without Internet access, you'll need to take the following general steps:</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="76a08-111">Die folgenden Schritte gelten nur für Geräte mit früheren Versionen von Windows, z. B.: Windows Server 2016 und früher oder Windows 8.1 und früher.</span><span class="sxs-lookup"><span data-stu-id="76a08-111">The steps below are applicable only to devices running previous versions of Windows such as: Windows Server 2016 and earlier or Windows 8.1 and earlier.</span></span>

> [!NOTE]
> - <span data-ttu-id="76a08-112">Ein OMS-Gatewayserver kann nicht als Proxy für getrennte Windows 10- oder Windows Server 2019-Geräte verwendet werden, wenn er über die TelemetryProxyServer-Registrierung oder das Gruppenrichtlinienobjekt konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="76a08-112">An OMS gateway server cannot be used as proxy for disconnected Windows 10 or Windows Server 2019 devices when configured via 'TelemetryProxyServer' registry or GPO.</span></span>
> - <span data-ttu-id="76a08-113">Für Windows 10 oder Windows Server 2019 – Während Sie TelemetryProxyServer verwenden können, muss es auf ein Standardproxygerät oder eine Standardproxy-Appliance verweisen.</span><span class="sxs-lookup"><span data-stu-id="76a08-113">For Windows 10 or Windows Server 2019 - while you may use TelemetryProxyServer, it must point to a standard proxy device or appliance.</span></span>
> - <span data-ttu-id="76a08-114">Darüber hinaus müssen Windows 10 oder Windows Server 2019 in getrennten Umgebungen in der Lage sein, Zertifikatvertrauenslisten offline über eine interne Datei oder einen Webserver zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="76a08-114">In addition, Windows 10 or Windows Server 2019 in disconnected environments must be able to update Certificate Trust Lists offline via an internal file or web server.</span></span>
> - <span data-ttu-id="76a08-115">Weitere Informationen zum Aktualisieren von CTLs im Offlinemodus finden Sie unter [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span><span class="sxs-lookup"><span data-stu-id="76a08-115">For more information about updating CTLs offline, see [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span></span>

<span data-ttu-id="76a08-116">Weitere Informationen zu Onboardingmethoden finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="76a08-116">For more information about onboarding methods, see the following articles:</span></span>
- [<span data-ttu-id="76a08-117">Onboarding früherer Versionen von Windows</span><span class="sxs-lookup"><span data-stu-id="76a08-117">Onboard previous versions of Windows</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [<span data-ttu-id="76a08-118">Onboarding von Servern in den Microsoft Defender for Endpoint-Dienst</span><span class="sxs-lookup"><span data-stu-id="76a08-118">Onboard servers to the Microsoft Defender for Endpoint service</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [<span data-ttu-id="76a08-119">Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="76a08-119">Configure device proxy and Internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a><span data-ttu-id="76a08-120">Lokale Geräte</span><span class="sxs-lookup"><span data-stu-id="76a08-120">On-premise devices</span></span>

- <span data-ttu-id="76a08-121">Richten Sie Azure Log Analytics (früher als OMS-Gateway bekannt) ein, um als Proxy oder Hub zu fungieren:</span><span class="sxs-lookup"><span data-stu-id="76a08-121">Setup Azure Log Analytics (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
  - [<span data-ttu-id="76a08-122">Azure Log Analytics Agent</span><span class="sxs-lookup"><span data-stu-id="76a08-122">Azure Log Analytics Agent</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - <span data-ttu-id="76a08-123">[Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) zeigen auf Defender for Endpoint Workspace key & ID</span><span class="sxs-lookup"><span data-stu-id="76a08-123">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>

- <span data-ttu-id="76a08-124">Offlinegeräte im gleichen Netzwerk von Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="76a08-124">Offline devices in the same network of Azure Log Analytics</span></span>
  -  <span data-ttu-id="76a08-125">Konfigurieren Sie MMA so, dass es auf:</span><span class="sxs-lookup"><span data-stu-id="76a08-125">Configure MMA to point to:</span></span>
     - <span data-ttu-id="76a08-126">Azure Log Analytics IP als Proxy</span><span class="sxs-lookup"><span data-stu-id="76a08-126">Azure Log Analytics IP as a proxy</span></span>
     - <span data-ttu-id="76a08-127">Defender for Endpoint workspace key & ID</span><span class="sxs-lookup"><span data-stu-id="76a08-127">Defender for Endpoint workspace key & ID</span></span>

## <a name="azure-virtual-machines"></a><span data-ttu-id="76a08-128">Virtuelle Azure-Computer</span><span class="sxs-lookup"><span data-stu-id="76a08-128">Azure virtual machines</span></span>
- <span data-ttu-id="76a08-129">Konfigurieren und Aktivieren des [Azure Log Analytics-Arbeitsbereichs](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span><span class="sxs-lookup"><span data-stu-id="76a08-129">Configure and enable [Azure Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span></span>

    - <span data-ttu-id="76a08-130">Richten Sie Azure Log Analytics Gateway (früher als OMS-Gateway bekannt) ein, um als Proxy oder Hub zu fungieren:</span><span class="sxs-lookup"><span data-stu-id="76a08-130">Setup Azure Log Analytics Gateway (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
      - [<span data-ttu-id="76a08-131">Azure Log Analytics Gateway</span><span class="sxs-lookup"><span data-stu-id="76a08-131">Azure Log Analytics Gateway</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - <span data-ttu-id="76a08-132">[Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) zeigen auf Defender for Endpoint Workspace key & ID</span><span class="sxs-lookup"><span data-stu-id="76a08-132">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>
    - <span data-ttu-id="76a08-133">Offline-Azure-VMs im gleichen Netzwerk des OMS-Gateways</span><span class="sxs-lookup"><span data-stu-id="76a08-133">Offline Azure VMs in the same network of OMS Gateway</span></span>
      - <span data-ttu-id="76a08-134">Konfigurieren der Azure Log Analytics-IP als Proxy</span><span class="sxs-lookup"><span data-stu-id="76a08-134">Configure Azure Log Analytics IP as a proxy</span></span>
      - <span data-ttu-id="76a08-135">Azure Log Analytics Workspace Key & ID</span><span class="sxs-lookup"><span data-stu-id="76a08-135">Azure Log Analytics Workspace Key & ID</span></span>

    - <span data-ttu-id="76a08-136">Azure Security Center (ASC)</span><span class="sxs-lookup"><span data-stu-id="76a08-136">Azure Security Center (ASC)</span></span>
      - [<span data-ttu-id="76a08-137">Security Policy \> Log Analytics Workspace</span><span class="sxs-lookup"><span data-stu-id="76a08-137">Security Policy \> Log Analytics Workspace</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [<span data-ttu-id="76a08-138">\>Bedrohungserkennung Ermöglichen des Zugriffs auf meine Daten durch Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="76a08-138">Threat Detection \> Allow Defender for Endpoint to access my data</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        <span data-ttu-id="76a08-139">Weitere Informationen finden Sie unter [Arbeiten mit Sicherheitsrichtlinien](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).</span><span class="sxs-lookup"><span data-stu-id="76a08-139">For more information, see [Working with security policies](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).</span></span>
