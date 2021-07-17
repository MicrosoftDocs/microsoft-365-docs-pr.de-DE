---
title: Aktivieren der Evaluierungsumgebung für Microsoft Cloud App Security
description: Lernen Sie die Architektur von MCAS in Microsoft Defender für Office 365 kennen und verstehen Sie die Interaktionen zwischen den Microsoft 365 Defender Produkten.
keywords: Microsoft 365 Defender Testversion, testen Sie Microsoft 365 Defender, bewerten Sie Microsoft 365 Defender, Microsoft 365 Defender Evaluierungslabor, Microsoft 365 Defender Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458049"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a><span data-ttu-id="bf4ec-104">Aktivieren der Evaluierungsumgebung für Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bf4ec-104">Enable the evaluation environment for Microsoft Cloud App Security</span></span>


<span data-ttu-id="bf4ec-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bf4ec-105">**Applies to:**</span></span>

- <span data-ttu-id="bf4ec-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf4ec-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bf4ec-107">Dieser Artikel ist [Schritt 2 von 2](eval-defender-mcas-overview.md) beim Einrichten der Evaluierungsumgebung für Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-107">This article is [Step 2 of 2](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="bf4ec-108">Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bf4ec-108">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="bf4ec-109">Dieser Artikel führt Sie durch den Prozess des Zugriffs auf das Cloud App Security-Portal und der Konfiguration der erforderlichen Integration zum Sammeln von Datenverkehrsdaten für Cloud-Apps.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-109">This article walks you through the process of accessing the Cloud App Security portal and configuring the necessary integration to collect cloud app traffic data.</span></span>

<span data-ttu-id="bf4ec-110">Um die in Ihrer Umgebung verwendeten Cloud-Apps zu ermitteln, können Sie eine oder beide der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="bf4ec-110">To discover cloud apps used in your environment, you can do one or both of the following:</span></span>

- <span data-ttu-id="bf4ec-111">Beginnen Sie schnell mit Cloud Discovery, indem Sie sich in Microsoft Defender für Endpunkt integrieren.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-111">Get up and running quickly with Cloud Discovery by integrating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bf4ec-112">Diese systemeigene Integration ermöglicht es Ihnen, sofort mit der Erfassung von Daten im Clouddatenverkehr über Ihre Windows 10 Geräte hinweg, in und außerhalb Ihres Netzwerks zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-112">This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.</span></span>
- <span data-ttu-id="bf4ec-113">Um alle Cloud-Apps zu ermitteln, auf die von allen Geräten zugegriffen wird, die mit Ihrem Netzwerk verbunden sind, stellen Sie den Cloud App Security Protokollsammler in Ihren Firewalls und anderen Proxys bereit.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-113">To discover all cloud apps accessed by all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies.</span></span> <span data-ttu-id="bf4ec-114">Dadurch werden Daten von Ihren Endpunkten gesammelt und zur Analyse an Cloud App Security gesendet.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-114">This collects data from your endpoints and sends it to Cloud App Security for analysis.</span></span> <span data-ttu-id="bf4ec-115">Cloud App Security kann nativ in einige Proxys von Drittanbietern integriert werden, um noch mehr Funktionen zu bieten.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-115">Cloud App Security natively integrates with some third-party proxies for even more capabilities.</span></span>

<span data-ttu-id="bf4ec-116">Dieser Artikel enthält Anleitungen für beide Methoden.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-116">This article includes guidance for both methods.</span></span>

<span data-ttu-id="bf4ec-117">Führen Sie die folgenden Schritte aus, um Microsoft Cloud App Security einzurichten.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-117">Use the following steps to set up Microsoft Cloud App Security.</span></span>

![Schritte zum Aktivieren von Microsoft Microsoft Cloud App Security in der Microsoft Defender-Evaluierungsumgebung](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [<span data-ttu-id="bf4ec-119">Schritt 1. Verbinden zum Cloud App Security-Portal</span><span class="sxs-lookup"><span data-stu-id="bf4ec-119">Step 1. Connect to the Cloud App Security portal</span></span>](#step-1-connect-to-the-cloud-app-security-portal)
- [<span data-ttu-id="bf4ec-120">Schritt 2. Integration in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bf4ec-120">Step 2. Integrate with Microsoft Defender for Endpoint</span></span>](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [<span data-ttu-id="bf4ec-121">Schritt 3. Bereitstellen des Cloud App Security Protokollsammlers in Ihren Firewalls und anderen Proxys</span><span class="sxs-lookup"><span data-stu-id="bf4ec-121">Step 3. Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [<span data-ttu-id="bf4ec-122">Schritt 4. Anzeigen des Cloud Discovery-Dashboards, um zu sehen, welche Apps in Ihrer Organisation verwendet werden</span><span class="sxs-lookup"><span data-stu-id="bf4ec-122">Step 4. View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a><span data-ttu-id="bf4ec-123">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-123">Step 1.</span></span> <span data-ttu-id="bf4ec-124">Verbinden zum Cloud App Security-Portal</span><span class="sxs-lookup"><span data-stu-id="bf4ec-124">Connect to the Cloud App Security portal</span></span>

<span data-ttu-id="bf4ec-125">Informationen zum Überprüfen der Lizenzierung und zum Herstellen einer Verbindung mit dem Cloud App Security-Portal finden Sie unter [Schnellstart: Erste Schritte mit Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="bf4ec-125">To verify licensing and to connect to the Cloud App Security portal, see [Quickstart: Get started with Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security).</span></span> 

<span data-ttu-id="bf4ec-126">Wenn Sie nicht sofort eine Verbindung mit dem Portal herstellen können, müssen Sie möglicherweise die IP-Adresse zur Zulassungsliste Ihrer Firewall hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-126">If you're not immediately able to connect to the portal, you might need to add the IP address to the allow list of your firewall.</span></span> <span data-ttu-id="bf4ec-127">Grundlegendes [Setup für Cloud App Security](/cloud-app-security/general-setup).</span><span class="sxs-lookup"><span data-stu-id="bf4ec-127">See [Basic setup for Cloud App Security](/cloud-app-security/general-setup).</span></span>

<span data-ttu-id="bf4ec-128">Wenn Sie weiterhin Probleme haben, überprüfen Sie die [Netzwerkanforderungen.](/cloud-app-security/network-requirements)</span><span class="sxs-lookup"><span data-stu-id="bf4ec-128">If you're still having trouble, review [Network requirements](/cloud-app-security/network-requirements).</span></span>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="bf4ec-129">Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-129">Step 2.</span></span> <span data-ttu-id="bf4ec-130">Integration in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bf4ec-130">Integrate with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="bf4ec-131">Microsoft Cloud App Security kann systemintern in Microsoft Defender für Endpunkt integriert werden.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-131">Microsoft Cloud App Security integrates with Microsoft Defender for Endpoint natively.</span></span> <span data-ttu-id="bf4ec-132">Die Integration vereinfacht den Rollout von Cloud Discovery, erweitert die Cloud Discovery-Funktionen über Ihr Unternehmensnetzwerk hinaus und ermöglicht die gerätebasierte Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-132">The integration simplifies roll out of Cloud Discovery, extends Cloud Discovery capabilities beyond your corporate network, and enables device-based investigation.</span></span> <span data-ttu-id="bf4ec-133">Diese Integration zeigt, dass auf Cloud-Apps und -Dienste von IT-verwalteten Windows 10 Geräten zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-133">This integration reveals cloud apps and services being accessed from IT-managed Windows 10 devices.</span></span> 

<span data-ttu-id="bf4ec-134">Wenn Sie Microsoft Defender für Endpunkt bereits eingerichtet haben, ist das Konfigurieren der Integration mit Cloud App Security ein Umschalter in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-134">If you've already set up Microsoft Defender for Endpoint, configuring integration with Cloud App Security is a toggle in Microsoft 365 Defender.</span></span> <span data-ttu-id="bf4ec-135">Nachdem die Integration aktiviert ist, können Sie zum Cloud App Security-Portal zurückkehren und umfangreiche Daten im Cloud Discovery-Dashboard anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-135">After integration is turned on, you can return to the Cloud App Security portal and view rich data in the Cloud Discovery Dashboard.</span></span>

<span data-ttu-id="bf4ec-136">Informationen zum Ausführen dieser Aufgaben finden Sie unter [Microsoft Defender für Endpunkt-Integration in Microsoft Cloud App Security.](/cloud-app-security/mde-integration)</span><span class="sxs-lookup"><span data-stu-id="bf4ec-136">To accomplish these tasks, see [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration).</span></span> 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a><span data-ttu-id="bf4ec-137">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="bf4ec-137">Step 3.</span></span> <span data-ttu-id="bf4ec-138">Bereitstellen des Cloud App Security Protokollsammlers in Ihren Firewalls und anderen Proxys</span><span class="sxs-lookup"><span data-stu-id="bf4ec-138">Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>

<span data-ttu-id="bf4ec-139">Um die Abdeckung auf allen Geräten zu gewährleisten, die mit Ihrem Netzwerk verbunden sind, stellen Sie den Cloud App Security Protokollsammler in Ihren Firewalls und anderen Proxys bereit, um Daten von Ihren Endpunkten zu sammeln und zur Analyse an Cloud App Security zu senden.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-139">For coverage on all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies to collect data from your endpoints and send it to Cloud App Security for analysis.</span></span> 

<span data-ttu-id="bf4ec-140">Wenn Sie eines der folgenden Secure Web Gateways (SWG) verwenden, bietet Cloud App Security eine nahtlose Bereitstellung und Integration:</span><span class="sxs-lookup"><span data-stu-id="bf4ec-140">If you're using one of the following Secure Web Gateways (SWG), Cloud App Security provides seamless deployment and integration:</span></span>
- <span data-ttu-id="bf4ec-141">Zscaler</span><span class="sxs-lookup"><span data-stu-id="bf4ec-141">Zscaler</span></span>
- <span data-ttu-id="bf4ec-142">iboss</span><span class="sxs-lookup"><span data-stu-id="bf4ec-142">iboss</span></span>
- <span data-ttu-id="bf4ec-143">Corrata</span><span class="sxs-lookup"><span data-stu-id="bf4ec-143">Corrata</span></span>
- <span data-ttu-id="bf4ec-144">Menlo Security</span><span class="sxs-lookup"><span data-stu-id="bf4ec-144">Menlo Security</span></span>

<span data-ttu-id="bf4ec-145">Weitere Informationen zur Integration in diese Netzwerkgeräte finden Sie unter ["Einrichten von Cloud Discovery".](/cloud-app-security/set-up-cloud-discovery)</span><span class="sxs-lookup"><span data-stu-id="bf4ec-145">For more information on integrating with these network devices, see [Set up Cloud Discovery](/cloud-app-security/set-up-cloud-discovery).</span></span> 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a><span data-ttu-id="bf4ec-146">Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-146">Step 4.</span></span> <span data-ttu-id="bf4ec-147">Anzeigen des Cloud Discovery-Dashboards, um zu sehen, welche Apps in Ihrer Organisation verwendet werden</span><span class="sxs-lookup"><span data-stu-id="bf4ec-147">View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>

<span data-ttu-id="bf4ec-148">Das Cloud Discovery-Dashboard ist so konzipiert, dass Sie mehr Einblick in die Verwendung von Cloud-Apps in Ihrer Organisation erhalten.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-148">The Cloud Discovery dashboard is designed to give you more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="bf4ec-149">Es bietet einen Überblick darüber, welche Arten von Apps verwendet werden, welche warnungen geöffnet werden und welche Risikostufen apps in Ihrer Organisation aufweisen.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-149">It provides an at-a-glance overview of what kinds of apps are being used, your open alerts, and the risk levels of apps in your organization.</span></span> 

<span data-ttu-id="bf4ec-150">Informationen zu den ersten Schritten mit dem Cloud Discovery-Dashboard finden Sie unter [Arbeiten mit ermittelten Apps.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="bf4ec-150">To get started using the Cloud Discovery dashboard, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="next-steps"></a><span data-ttu-id="bf4ec-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="bf4ec-151">Next steps</span></span>

<span data-ttu-id="bf4ec-152">Schritt 3 von 3: [Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="bf4ec-152">Step 3 of 3: [Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span></span>

<span data-ttu-id="bf4ec-153">Kehren Sie zur Übersicht für ["Auswerten Microsoft Cloud App Security"](eval-defender-mcas-overview.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="bf4ec-153">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="bf4ec-154">Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bf4ec-154">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>