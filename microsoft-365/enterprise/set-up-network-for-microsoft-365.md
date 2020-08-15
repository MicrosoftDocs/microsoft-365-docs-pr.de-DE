---
title: Einrichten Ihres Netzwerks für Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Hier finden Sie Links zu Artikeln mit Informationen, die Sie beim Einrichten Ihres Netzwerks für Microsoft 365 unterstützen, einschließlich einer Übersicht über die Netzwerkkonnektivität und einer Liste der Endpunkte.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690342"
---
# <a name="set-up-your-network-for-microsoft-365"></a><span data-ttu-id="31e8e-103">Einrichten Ihres Netzwerks für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="31e8e-103">Set up your network for Microsoft 365</span></span>

<span data-ttu-id="31e8e-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="31e8e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="31e8e-105">Ein wichtiger Bestandteilihres Microsoft 365-onboardings besteht darin, sicherzustellen, dass Ihre Netzwerk-und Internet Verbindungen für einen optimierten Zugriff eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="31e8e-105">An important part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="31e8e-106">Das Konfigurieren Ihres lokalen Netzwerks für den Zugriff auf eine global verteilte Software-as-a-Service (SaaS)-Cloud unterscheidet sich von einem herkömmlichen Netzwerk, das für den Datenverkehr zu lokalen Rechenzentren und einer zentralen Internet Verbindung optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="31e8e-106">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="31e8e-107">Lesen Sie diese Artikel, um die wichtigsten Unterschiede zu verstehen und um Ihre Edgegeräte, Clientcomputer und lokalen Netzwerk zu ändern, um die beste Leistung für Ihre lokalen Benutzer zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="31e8e-107">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="how-microsoft-365-networking-works"></a><span data-ttu-id="31e8e-108">Funktionsweise von Microsoft 365-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="31e8e-108">How Microsoft 365 networking works</span></span>

<span data-ttu-id="31e8e-109">In diesen Artikeln finden Sie eine Übersicht über die Konnektivität für Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="31e8e-109">See these articles for an overview of connectivity for Microsoft 365:</span></span>

- [<span data-ttu-id="31e8e-110">Microsoft 365 – Überblick über die Netzwerkkonnektivität</span><span class="sxs-lookup"><span data-stu-id="31e8e-110">Microsoft 365 networking connectivity overview</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="31e8e-111">Microsoft 365-Prinzipien für die Netzwerkkonnektivität</span><span class="sxs-lookup"><span data-stu-id="31e8e-111">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)
- [<span data-ttu-id="31e8e-112">Bewerten der Microsoft 365-Netzwerkkonnektivität</span><span class="sxs-lookup"><span data-stu-id="31e8e-112">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

<span data-ttu-id="31e8e-113">Ratschläge zur Verbesserung der Leistung finden Sie unter [Netzwerkplanung und Leistungsoptimierung für Microsoft 365](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="31e8e-113">For advice on enhancing performance, see [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span></span>

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a><span data-ttu-id="31e8e-114">Unterstützung von Microsoft 365 Networking als Netzwerkgeräte Anbieter</span><span class="sxs-lookup"><span data-stu-id="31e8e-114">Support Microsoft 365 networking as a network equipment vendor</span></span>

<span data-ttu-id="31e8e-p102">Wenn Sie ein Lieferant von Netzwerkgeräten sind, treten Sie dem [Office 365-Netzwerk-Partnerprogramm](microsoft-365-networking-partner-program.md) bei. Registrieren Sie sich für das Programm, um Kennektivitätsprinzipien von Office 365-Netzwerken in Ihre Produkte und Lösungen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="31e8e-p102">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md). Enroll in the program to build Office 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="office-365-endpoints"></a><span data-ttu-id="31e8e-117">Office 365-Endpunkte</span><span class="sxs-lookup"><span data-stu-id="31e8e-117">Office 365 endpoints</span></span>

<span data-ttu-id="31e8e-118">Endpunkte sind die Gruppe von Ziel-IP-Adressen, DNS-Domänennamen und URLs für Office 365-Datenverkehr über das Internet.</span><span class="sxs-lookup"><span data-stu-id="31e8e-118">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Office 365 traffic on the Internet.</span></span> 

<span data-ttu-id="31e8e-p103">Zum Optimieren der Leistung von auf Office 365-Cloud basierten Diensten benötigen einige Endpunkte besondere Behandlung durch Ihre Clientbrowser und die Geräte in Ihrem Umkreisnetzwerk. Diese Geräten umfassen Firewalls, SSL Unterbrechung und Überprüfung, Paketüberprüfungsgeräte und Datensysteme Schutz vor Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="31e8e-p103">To optimize performance to Office 365 cloud-based services, some endpoints need special handling by your client browsers and the devices in your edge network. These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="31e8e-121">Weitere Details finden Sie unter [ Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="31e8e-121">See [Managing Office 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="31e8e-p104">Es gibt derzeit fünf verschiedene Office 365-Clouds. Über diese Tabelle gelangen Sie zur Liste der jeweiligen Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="31e8e-p104">There are currently five different Office 365 clouds. This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="31e8e-124">Endpunkte</span><span class="sxs-lookup"><span data-stu-id="31e8e-124">Endpoints</span></span> | <span data-ttu-id="31e8e-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31e8e-125">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="31e8e-126">Weltweite Endpunkte</span><span class="sxs-lookup"><span data-stu-id="31e8e-126">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="31e8e-127">Die Endpunkte für weltweite Office 365-Abonnements, welche die United States Government Community Cloud (GCC) umfassen.</span><span class="sxs-lookup"><span data-stu-id="31e8e-127">The endpoints for worldwide Office 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="31e8e-128">DoD-Endpunkte für US Government</span><span class="sxs-lookup"><span data-stu-id="31e8e-128">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="31e8e-129">Die Endpunkte für United States Department of Defense (DoD)-Abonnements.</span><span class="sxs-lookup"><span data-stu-id="31e8e-129">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="31e8e-130">GCC High-Endpunkte für US Government</span><span class="sxs-lookup"><span data-stu-id="31e8e-130">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="31e8e-131">Die Endpunkte für United States Government Community Cloud High (GCC High)-Abonnements.</span><span class="sxs-lookup"><span data-stu-id="31e8e-131">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="31e8e-132">Endpunkte von Office 365, betrieben von 21Vianet</span><span class="sxs-lookup"><span data-stu-id="31e8e-132">Office 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="31e8e-133">Die Endpunkte für Office 365 betrieben von 21Vianet, das darauf ausgelegt ist, den Anforderungen für Office 365 in China zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="31e8e-133">The endpoints for Office 365 operated by 21Vianet, which is designed to meet the needs for Office 365 in China.</span></span> |
| [<span data-ttu-id="31e8e-134">Endpunkte für Office 365 Deutschland</span><span class="sxs-lookup"><span data-stu-id="31e8e-134">Office 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="31e8e-135">Die Endpunkte für eine separate Cloud in Europa für die meisten regulierten Kunden in Deutschland, der Europäischen Union (EU) und der Europäischen Freihandelszone (EFTA).</span><span class="sxs-lookup"><span data-stu-id="31e8e-135">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="31e8e-136">Informationen über das automatische Abrufen der neuesten Liste der Endpunkte für Ihre Office 365-Cloud finden Sie unter [Office 365-IP-Adresse und URL-Web-Dienst](microsoft-365-ip-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="31e8e-136">To automate getting the latest list of endpoints for your Office 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="31e8e-137">Weitere Informationen über zusätzliche Endpunkte finden Sie in folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="31e8e-137">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="31e8e-138">Zusätzliche, nicht in den Webdiensten enthaltene Endpunkte</span><span class="sxs-lookup"><span data-stu-id="31e8e-138">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="31e8e-139">Netzwerkanforderungen in Office 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="31e8e-139">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a><span data-ttu-id="31e8e-140">Weitere Themen für Microsoft 365 Networking</span><span class="sxs-lookup"><span data-stu-id="31e8e-140">Additional topics for Microsoft 365 networking</span></span>

<span data-ttu-id="31e8e-141">In diesen Artikeln finden Sie spezielle Themen in Microsoft 365 Networking:</span><span class="sxs-lookup"><span data-stu-id="31e8e-141">See these articles for specialized topics in Microsoft 365 networking:</span></span>

- [<span data-ttu-id="31e8e-142">Netzwerke für die Inhaltsübermittlung</span><span class="sxs-lookup"><span data-stu-id="31e8e-142">Content delivery networks</span></span>](content-delivery-networks.md)
- [<span data-ttu-id="31e8e-143">IPv6-Unterstützung in Office 365-Diensten</span><span class="sxs-lookup"><span data-stu-id="31e8e-143">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
- [<span data-ttu-id="31e8e-144">NAT-Unterstützung bei Office 365</span><span class="sxs-lookup"><span data-stu-id="31e8e-144">NAT support with Office 365</span></span>](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a><span data-ttu-id="31e8e-145">ExpressRoute für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="31e8e-145">ExpressRoute for Microsoft 365</span></span>

<span data-ttu-id="31e8e-146">In den folgenden Artikeln finden Sie Informationen über die Verwendung von ExpressRoute für Office 365-Datenverkehr:</span><span class="sxs-lookup"><span data-stu-id="31e8e-146">See these articles for information on the use of ExpressRoute for Office 365 traffic:</span></span>

- [<span data-ttu-id="31e8e-147">Azure ExpressRoute für Office 365</span><span class="sxs-lookup"><span data-stu-id="31e8e-147">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
- [<span data-ttu-id="31e8e-148">Implementierung von ExpressRoute für Office 365</span><span class="sxs-lookup"><span data-stu-id="31e8e-148">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)
- [<span data-ttu-id="31e8e-149">Netzwerkplanung mit ExpressRoute für Office 365</span><span class="sxs-lookup"><span data-stu-id="31e8e-149">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="31e8e-150">Routing mit ExpressRoute für Office 365</span><span class="sxs-lookup"><span data-stu-id="31e8e-150">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
