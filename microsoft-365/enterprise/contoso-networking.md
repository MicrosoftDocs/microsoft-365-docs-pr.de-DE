---
title: Netzwerkfunktionen für die Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Grundlegendes zur Contoso-Netzwerkinfrastruktur und dazu, wie das Unternehmen seine SD-WAN-Technologie für eine optimale Netzwerkleistung für Microsoft 365 für Enterprise-Cloud-Dienste verwendet.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754014"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="1ca19-103">Netzwerkfunktionen für die Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="1ca19-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="1ca19-p101">Um eine Cloud-inclusive-Infrastruktur einzusetzen, hat Contoso eine grundlegende Verschiebung des Netzwerkdatenverkehrs zu Cloud-Diensten entwickelt. Anstelle eines internen Hub-and-Spoke-Modells, das die Netzwerkkonnektivität und den Datenverkehr für die nächste Ebene der Office-Hierarchie konzentriert, haben Sie Benutzer Standorte dem lokalen Internet Ausstieg und lokalen Verbindungen mit dem nächstgelegenen Microsoft 365-Netzwerkspeicherort im Internet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1ca19-p101">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels. Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="1ca19-106">Netzwerkinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="1ca19-106">Networking infrastructure</span></span>

<span data-ttu-id="1ca19-107">Dies sind die Netzwerkelemente, die Contoso-Niederlassungen auf der ganzen Welt verknüpfen:</span><span class="sxs-lookup"><span data-stu-id="1ca19-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="1ca19-108">MPLS-WAN-Netzwerk (Multiprotocol Label Switching)</span><span class="sxs-lookup"><span data-stu-id="1ca19-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="1ca19-p102">Ein MPLS-WAN-Netzwerk verbindet das Pariser Hauptquartier mit regionalen Niederlassungen und regionalen Niederlassungen mit Satellitenbüros in einer Spoke-and-Hub-Konfiguration. Das Netzwerk ermöglicht Benutzern den Zugriff auf lokale Server, die Branchenanwendungen in der Pariser Hauptniederlassung bilden. Außerdem werden alle generischen Internetdatenverkehr an das Pariser Büro weitergeleitet, wo die Netzwerksicherheitsgeräte die Anforderungen Schrubben. In jedem Büro liefern Router Datenverkehr zu drahtgebundenen Hosts oder drahtlosen Zugriffspunkten in Subnetzen, die den privaten IP-Adressraum verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ca19-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration. The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters. It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="1ca19-113">Lokaler direkter Internetzugriff für Microsoft 365-Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="1ca19-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="1ca19-p103">Jedes Büro verfügt über ein softwaredefiniertes WAN (SD-WAN)-Gerät, das über einen oder mehrere lokale Internetdienstanbieter-Netzwerk Schaltkreise mit eigener Internetverbindung über einen Proxy Server verfügt. Dies wird in der Regel als WAN-Link zu einem lokalen ISP implementiert, der auch öffentliche IP-Adressen und einen lokalen DNS-Server bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1ca19-p103">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="1ca19-116">Internetauftritt</span><span class="sxs-lookup"><span data-stu-id="1ca19-116">Internet presence</span></span>

  <span data-ttu-id="1ca19-p104">Contoso ist Besitzer des \. com-namens der öffentlichen Domäne von contoso. Bei der öffentlichen Contoso-Website für die Bestellung von Produkten handelt es sich um eine Reihe von Servern in einem mit dem Internet verbundenen Rechenzentrum im Pariser Campus. Contoso verwendet einen/24 öffentlichen IP-Adressbereich im Internet.</span><span class="sxs-lookup"><span data-stu-id="1ca19-p104">Contoso owns the contoso\.com public domain name. The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="1ca19-120">Abbildung 1 zeigt die Contoso-Netzwerkinfrastruktur und ihre Verbindungen mit dem Internet.</span><span class="sxs-lookup"><span data-stu-id="1ca19-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Das Contoso-Netzwerk](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="1ca19-122">**Abbildung 1: das Contoso-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="1ca19-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="1ca19-123">Verwenden des SD-WAN für eine optimale Netzwerkkonnektivität mit Microsoft</span><span class="sxs-lookup"><span data-stu-id="1ca19-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="1ca19-124">Contoso folgte den folgenden [Prinzipien von Microsoft 365-Netzwerkverbindungen](microsoft-365-network-connectivity-principles.md) bei folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="1ca19-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="1ca19-125">Identifizieren und Unterscheiden von Microsoft 365-Netzwerkdatenverkehr</span><span class="sxs-lookup"><span data-stu-id="1ca19-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="1ca19-126">Lokaler Ausgang von Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="1ca19-126">Egress network connections locally</span></span>
- <span data-ttu-id="1ca19-127">Vermeiden von Spitzkehren für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="1ca19-127">Avoid network hairpins</span></span>
- <span data-ttu-id="1ca19-128">Umgehen von doppelten Netzwerksicherheitsgeräten</span><span class="sxs-lookup"><span data-stu-id="1ca19-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="1ca19-129">Für Microsoft 365 gibt es drei Kategorien von Netzwerkdatenverkehr: *optimieren*, *zulassen*und *Standard*.</span><span class="sxs-lookup"><span data-stu-id="1ca19-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="1ca19-130">Optimieren und zulassen der Datenverkehr ist vertrauenswürdiger Netzwerkdatenverkehr, der an den Endpunkten verschlüsselt und gesichert ist und für das Microsoft 365-Netzwerk bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="1ca19-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="1ca19-131">Contoso hat Folgendes beschlossen:</span><span class="sxs-lookup"><span data-stu-id="1ca19-131">Contoso decided to:</span></span>

- <span data-ttu-id="1ca19-132">Verwenden Sie Direct Internet Ausstieg zum Optimieren und zulassen des Kategorie-Datenverkehrs sowie zum Weiterleiten aller standardmäßigen Kategorie-Datenverkehr an die in Paris ansässige zentrale Internetverbindung.</span><span class="sxs-lookup"><span data-stu-id="1ca19-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="1ca19-133">Stellen Sie SD-WAN-Geräte in jedem Büro als einfache Möglichkeit zur Verfügung, um diese Prinzipien zu befolgen und eine optimale Netzwerkleistung für Microsoft 365 Cloud-basierte Dienste zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="1ca19-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="1ca19-134">Die SD-WAN-Geräte weisen einen LAN-Port für das lokale Netzwerk und mehrere WAN-Ports auf.</span><span class="sxs-lookup"><span data-stu-id="1ca19-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="1ca19-135">Ein WAN-Port stellt eine Verbindung mit dem MPLS-Netzwerk her.</span><span class="sxs-lookup"><span data-stu-id="1ca19-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="1ca19-136">Eine andere stellt eine Verbindung zu einer lokalen ISP-Schaltung her.</span><span class="sxs-lookup"><span data-stu-id="1ca19-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="1ca19-137">Die SD-WAN-Geräte leiten Netzwerkdatenverkehr der Kategorie "Optimize" und "Allow" über die ISP-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="1ca19-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="1ca19-138">Die Contoso-Branchen-App-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="1ca19-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="1ca19-139">Contoso hat die Infrastruktur für Branchenanwendungen und Server Netzwerke für Folgendes entworfen:</span><span class="sxs-lookup"><span data-stu-id="1ca19-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="1ca19-140">Zweigstellen verwenden lokale Cacheserver, um Dokumente und interne Websites zu speichern, auf die häufig zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="1ca19-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="1ca19-p107">Regionalstellen verwenden regionale Anwendungsserver für die Regional- und Zweigstellenbüros. Diese Server werden mit den Servern in der Pariser Zentrale synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="1ca19-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="1ca19-143">Die Pariser Campus-Rechenzentren enthalten zentralisierte Anwendungsserver, die der gesamten Organisation dienen.</span><span class="sxs-lookup"><span data-stu-id="1ca19-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="1ca19-144">Abbildung 2 zeigt den Prozentsatz der Netzwerkdatenverkehr-Kapazität, die beim Zugriff auf Server im Intranet von Contoso verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1ca19-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![Die Contoso-Infrastruktur für interne Anwendungen](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="1ca19-146">**Abbildung 2: die Contoso-Infrastruktur für interne Anwendungen**</span><span class="sxs-lookup"><span data-stu-id="1ca19-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="1ca19-147">Für die Satelliten-oder regionalen Hub-Büros können 60 Prozent der von Mitarbeitern benötigten Ressourcen über Satelliten-und regionale Hub-Office-Server bedient werden.</span><span class="sxs-lookup"><span data-stu-id="1ca19-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="1ca19-148">Die zusätzlichen 40 Prozent der Ressourcenanforderungen müssen über die WAN-Verbindung mit dem Pariser Campus gehen.</span><span class="sxs-lookup"><span data-stu-id="1ca19-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="1ca19-149">Netzwerkanalyse und Vorbereitung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="1ca19-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="1ca19-150">Die erfolgreiche Einführung von Microsoft 365 für Enterprise-Dienste durch Contoso-Benutzer hängt von der hochgradig verfügbaren und leistungsfähigen Konnektivität mit dem Internet oder direkt mit Microsoft Cloud Services ab.</span><span class="sxs-lookup"><span data-stu-id="1ca19-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="1ca19-151">Contoso hat diese Schritte zur Planung und Implementierung einer optimierten Konnektivität mit Microsoft 365 für Enterprise-Cloud-Dienste ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="1ca19-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="1ca19-152">Erstellen eines WAN-Netzplandiagramms für Unternehmen zur Unterstützung bei der Planung</span><span class="sxs-lookup"><span data-stu-id="1ca19-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="1ca19-153">Um Ihre Netzwerkplanung zu starten, hat Contoso ein Diagramm mit seinen Bürostandorten, vorhandenen Netzwerkverbindungen, vorhandenen Netzwerkperimeter-Geräten und Dienstklassen erstellt, die im Netzwerk verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="1ca19-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="1ca19-154">Dieses Diagramm wurde für jeden nachfolgenden Schritt bei der Planung und Implementierung von Netzwerkkonnektivität verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ca19-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="1ca19-155">Erstellen eines Plans für Microsoft 365 für die unternehmensweite Netzwerkkonnektivität</span><span class="sxs-lookup"><span data-stu-id="1ca19-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="1ca19-156">Contoso hat die [Microsoft 365-Netzwerk Verbindungs Prinzipien](microsoft-365-network-connectivity-principles.md) und Beispielreferenz-Netzwerkarchitekturen verwendet, um SD-WAN als bevorzugte Topologie für die Microsoft 365-Konnektivität zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1ca19-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="1ca19-157">Analysieren der Auslastung der Internetverbindung und der MPLS-WAN-Bandbreite in jedem Büro und erhöhte Bandbreite bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="1ca19-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="1ca19-158">Die aktuelle Auslastung jedes Büros wurde analysiert, und die Schaltkreise wurden erhöht, sodass der vorhergesagte Microsoft 365 Cloud-basierter Datenverkehr mit durchschnittlich 20 Prozent nicht genutzter Kapazität betrieben würde.</span><span class="sxs-lookup"><span data-stu-id="1ca19-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="1ca19-159">Optimieren der Leistung für Microsoft-Netzwerkdienste</span><span class="sxs-lookup"><span data-stu-id="1ca19-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="1ca19-160">Contoso hat die Gruppe der Office 365-, InTune-und Azure-Endpunkte und konfigurierter Firewalls, Sicherheitsgeräte und anderer Systeme im Internetpfad für eine optimale Leistung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="1ca19-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="1ca19-161">Endpunkte für Office 365 optimieren und zulassen des Kategorie-Datenverkehrs wurden in die SD-WAN-Geräte für das Routing über die ISP-Schaltung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="1ca19-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="1ca19-162">Konfigurieren von internem DNS</span><span class="sxs-lookup"><span data-stu-id="1ca19-162">Configure internal DNS</span></span>

   <span data-ttu-id="1ca19-163">Das DNS muss betriebsbereit sein und für Microsoft 365-Datenverkehr lokal nachgeschlagen werden.</span><span class="sxs-lookup"><span data-stu-id="1ca19-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="1ca19-164">Überprüfen der Netzwerkendpunkt-und Port Konnektivität</span><span class="sxs-lookup"><span data-stu-id="1ca19-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="1ca19-165">Contoso hat Microsoft Network Connectivity Test Tools zum Überprüfen der Konnektivität für Microsoft 365 für Enterprise-Cloud-Dienste ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1ca19-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="1ca19-166">Optimieren der Mitarbeiter Computer für die Netzwerkkonnektivität</span><span class="sxs-lookup"><span data-stu-id="1ca19-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="1ca19-167">Einzelne Computer wurden überprüft, um sicherzustellen, dass die neuesten Betriebssystemupdates installiert wurden und dass die Endpunkt Sicherheitsüberwachung auf allen Clients aktiv war.</span><span class="sxs-lookup"><span data-stu-id="1ca19-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="1ca19-168">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="1ca19-168">Next step</span></span>

<span data-ttu-id="1ca19-169">Erfahren Sie, wie Contoso [seine lokalen Active Directory-Domänendienste in der Cloud](contoso-identity.md) für Mitarbeiter und Verbundauthentifizierung für Kunden und Geschäftspartner nutzt.</span><span class="sxs-lookup"><span data-stu-id="1ca19-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ca19-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ca19-170">See also</span></span>

[<span data-ttu-id="1ca19-171">Roadmap für Netzwerke für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1ca19-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="1ca19-172">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1ca19-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="1ca19-173">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="1ca19-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
