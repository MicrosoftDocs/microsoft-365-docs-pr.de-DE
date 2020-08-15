---
title: Roadmap für Netzwerke für Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Die Roadmap für die Implementierung von Microsoft 365 Networking.
ms.openlocfilehash: 93d0f253e098815139b431a826f7e5e7a0410b37
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690578"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="5026f-103">Roadmap für Netzwerke für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5026f-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="5026f-104">Microsoft 365 für Unternehmen enthält Cloud-Dienste für Zusammenarbeit und Produktivität, Microsoft InTune und viele Identitäts-und Sicherheitsdienste von Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="5026f-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="5026f-105">Alle cloudbasierten Dienste basieren auf der Sicherheit, Leistung und Zuverlässigkeit der Verbindungen von Clientgeräten über das Internet oder dedizierte Leitungen.</span><span class="sxs-lookup"><span data-stu-id="5026f-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="5026f-106">Um diese Dienste zu hosten und sie für Kunden auf der ganzen Welt verfügbar zu machen, hat Microsoft eine Netzwerkinfrastruktur entwickelt, deren Fokus auf Leistung und Integration liegt.</span><span class="sxs-lookup"><span data-stu-id="5026f-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="5026f-107">Ein wichtiger Bestandteilihres Microsoft 365-onboardings besteht darin, sicherzustellen, dass Ihre Netzwerk-und Internet Verbindungen für einen optimierten Zugriff eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="5026f-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="5026f-108">Das Konfigurieren Ihres lokalen Netzwerks für den Zugriff auf eine global verteilte Software-as-a-Service (SaaS)-Cloud unterscheidet sich von einem herkömmlichen Netzwerk, das für den Datenverkehr zu lokalen Rechenzentren und einer zentralen Internet Verbindung optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="5026f-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="5026f-109">Lesen Sie diese Artikel, um die wichtigsten Unterschiede zu verstehen und um Ihre Edgegeräte, Clientcomputer und lokalen Netzwerk zu ändern, um die beste Leistung für Ihre lokalen Benutzer zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="5026f-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="5026f-110">Plan</span><span class="sxs-lookup"><span data-stu-id="5026f-110">Plan</span></span>

<span data-ttu-id="5026f-111">In der Planungsphase Ihrer Netzwerkimplementierung:</span><span class="sxs-lookup"><span data-stu-id="5026f-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="5026f-112">Grundlegendes zur Funktionsweise von Microsoft 365 Networking</span><span class="sxs-lookup"><span data-stu-id="5026f-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="5026f-113">Bewerten Ihrer aktuellen Netzwerkkonnektivität</span><span class="sxs-lookup"><span data-stu-id="5026f-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="5026f-114">Ermitteln, ob Express Route für Ihre Organisation geeignet ist</span><span class="sxs-lookup"><span data-stu-id="5026f-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="5026f-115">Planen der Netzwerkgeräte</span><span class="sxs-lookup"><span data-stu-id="5026f-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="5026f-116">Einrichten des Netzwerks für die Migration</span><span class="sxs-lookup"><span data-stu-id="5026f-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="5026f-117">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="5026f-117">Deploy</span></span>

<span data-ttu-id="5026f-118">In der Bereitstellungsphase Ihrer Netzwerkimplementierung:</span><span class="sxs-lookup"><span data-stu-id="5026f-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="5026f-119">Stellen Sie sicher, dass Ihr Unternehmensnetzwerk für Microsoft 365-Konnektivität optimiert ist</span><span class="sxs-lookup"><span data-stu-id="5026f-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="5026f-120">Hinzufügen der DNS-Domänen für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="5026f-120">Add the DNS domains for your organization</span></span>](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [<span data-ttu-id="5026f-121">Optimieren der Konnektivität mit Microsoft 365-Endpunkten</span><span class="sxs-lookup"><span data-stu-id="5026f-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="5026f-122">Optimieren der Konnektivität für Remotemitarbeiter</span><span class="sxs-lookup"><span data-stu-id="5026f-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="5026f-123">Konfigurieren Sie bei Bedarf [Express Route](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="5026f-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="5026f-124">Verwalten</span><span class="sxs-lookup"><span data-stu-id="5026f-124">Manage</span></span>

<span data-ttu-id="5026f-125">In der Verwaltungsphase Ihrer Netzwerkimplementierung:</span><span class="sxs-lookup"><span data-stu-id="5026f-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="5026f-126">Stellen Sie sicher, dass ihre Netzwerkgeräte die neuesten Office 365 Endpunkte verwenden.</span><span class="sxs-lookup"><span data-stu-id="5026f-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="5026f-127">Überwachen und Optimieren der Netzwerkleistung</span><span class="sxs-lookup"><span data-stu-id="5026f-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="5026f-128">Überwachen der Express Route-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="5026f-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="5026f-129">Hersteller von Netzwerkgeräten</span><span class="sxs-lookup"><span data-stu-id="5026f-129">Network equipment vendors</span></span>

<span data-ttu-id="5026f-130">Wenn Sie ein Netzwerkgeräte Anbieter sind, nehmen Sie am [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md)Teil.</span><span class="sxs-lookup"><span data-stu-id="5026f-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="5026f-131">Registrieren Sie sich für das Programm, um Microsoft 365-Netzwerk Verbindungs Prinzipien in Ihre Produkte und Lösungen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="5026f-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="5026f-132">So hat Contoso das Netzwerk für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5026f-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="5026f-133">Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber repräsentatives multinationales Unternehmen, [seine Netzwerkgeräte und Internetverbindungen für Microsoft 365-Clouddienste optimiert hat](contoso-networking.md).</span><span class="sxs-lookup"><span data-stu-id="5026f-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Die Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="5026f-135">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="5026f-135">Next step</span></span>

<span data-ttu-id="5026f-136">Starten Sie Ihre Netzwerkplanung mit der [Übersicht über die Microsoft 365-Netzwerkkonnektivität](microsoft-365-networking-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5026f-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>