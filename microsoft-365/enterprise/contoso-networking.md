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
description: Erfahren Sie mehr über die Contoso-Netzwerkinfrastruktur und darüber, wie das Unternehmen seine SD-WAN-Technologie für eine optimale Netzwerkleistung verwendet, um Microsoft 365 Enterprise Cloud Services zu verbessern.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754014"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="50b47-103">Netzwerkfunktionen für die Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="50b47-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="50b47-104">Um eine cloud-inklusive Infrastruktur zu übernehmen, hat Contoso eine grundlegende Verschiebung in der Art und Weise des Datenverkehrs von Netzwerkdatenverkehr zu Clouddiensten entwickelt.</span><span class="sxs-lookup"><span data-stu-id="50b47-104">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels.</span></span> <span data-ttu-id="50b47-105">Anstelle eines internen Hub- und Sprachmodells, das die Netzwerkkonnektivität und den Datenverkehr für die nächste Ebene der Bürohierarchie konzentriert, wurden Benutzerstandorte lokalen Internetanschlüssen und lokalen Verbindungen zum nächstgelegenen Microsoft 365-Netzwerkspeicherort im Internet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="50b47-105">Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="50b47-106">Netzwerkinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="50b47-106">Networking infrastructure</span></span>

<span data-ttu-id="50b47-107">Dies sind die Netzwerkelemente, die Contoso-Niederlassungen auf der ganzen Welt verbinden:</span><span class="sxs-lookup"><span data-stu-id="50b47-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="50b47-108">MPLS-WAN-Netzwerk (Multiprotocol Label Switching)</span><span class="sxs-lookup"><span data-stu-id="50b47-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="50b47-109">Ein MPLS-WAN-Netzwerk verbindet die Pariser Zentrale mit Regionalbüros und Regionalbüros mit Satellitenbüros in einer Spoke-and-Hub-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="50b47-109">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration.</span></span> <span data-ttu-id="50b47-110">Das Netzwerk ermöglicht Benutzern den Zugriff auf lokale Server, die In-Business-Anwendungen in der Pariser Zentrale sind.</span><span class="sxs-lookup"><span data-stu-id="50b47-110">The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters.</span></span> <span data-ttu-id="50b47-111">Außerdem werden alle generischen Internetdatenverkehre an das Pariser Büro weiter geroutet, in dem Netzwerksicherheitsgeräte die Anforderungen bereinigungen.</span><span class="sxs-lookup"><span data-stu-id="50b47-111">It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests.</span></span> <span data-ttu-id="50b47-112">In jedem Büro liefern Router Datenverkehr an verkabelte Hosts oder Funkzugriffspunkte in Subnetzen, die den privaten IP-Adressraum verwenden.</span><span class="sxs-lookup"><span data-stu-id="50b47-112">Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="50b47-113">Lokaler direkter Internetzugriff für Microsoft 365 Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="50b47-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="50b47-114">Jedes Büro verfügt über ein softwaredefiniertes WAN (SD-WAN)-Gerät, das über mindestens einen lokalen Internet-ISP-Netzwerkkreis mit eigener Internetverbindung über einen Proxyserver verfügt.</span><span class="sxs-lookup"><span data-stu-id="50b47-114">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server.</span></span> <span data-ttu-id="50b47-115">Dies wird in der Regel als WAN-Verbindung zu einem lokalen ISP implementiert, der auch öffentliche IP-Adressen und einen lokalen DNS-Server bietet.</span><span class="sxs-lookup"><span data-stu-id="50b47-115">This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="50b47-116">Internetauftritt</span><span class="sxs-lookup"><span data-stu-id="50b47-116">Internet presence</span></span>

  <span data-ttu-id="50b47-117">Contoso besitzt den öffentlichen Domänennamen contoso \. com.</span><span class="sxs-lookup"><span data-stu-id="50b47-117">Contoso owns the contoso\.com public domain name.</span></span> <span data-ttu-id="50b47-118">Die öffentliche Contoso-Website zum Bestellen von Produkten ist eine Reihe von Servern in einem mit dem Internet verbundenen Rechenzentrum auf dem Pariser Campus.</span><span class="sxs-lookup"><span data-stu-id="50b47-118">The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus.</span></span> <span data-ttu-id="50b47-119">Contoso verwendet einen öffentlichen /24-IP-Adressbereich im Internet.</span><span class="sxs-lookup"><span data-stu-id="50b47-119">Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="50b47-120">Abbildung 1 zeigt die Contoso-Netzwerkinfrastruktur und ihre Verbindungen mit dem Internet.</span><span class="sxs-lookup"><span data-stu-id="50b47-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Das Contoso-Netzwerk](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="50b47-122">**Abbildung 1: Das Contoso-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="50b47-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="50b47-123">Verwenden des SD-WAN für eine optimale Netzwerkkonnektivität mit Microsoft</span><span class="sxs-lookup"><span data-stu-id="50b47-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="50b47-124">Contoso folgte den folgenden [Prinzipien von Microsoft 365-Netzwerkverbindungen](microsoft-365-network-connectivity-principles.md) bei folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="50b47-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="50b47-125">Identifizieren und Unterscheiden von Microsoft 365-Netzwerkdatenverkehr</span><span class="sxs-lookup"><span data-stu-id="50b47-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="50b47-126">Lokaler Ausgang von Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="50b47-126">Egress network connections locally</span></span>
- <span data-ttu-id="50b47-127">Vermeiden von Spitzkehren für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="50b47-127">Avoid network hairpins</span></span>
- <span data-ttu-id="50b47-128">Umgehen von doppelten Netzwerksicherheitsgeräten</span><span class="sxs-lookup"><span data-stu-id="50b47-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="50b47-129">Es gibt drei Kategorien von Netzwerkdatenverkehr für Microsoft 365: *Optimize*, *Allow* und *Default*.</span><span class="sxs-lookup"><span data-stu-id="50b47-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="50b47-130">Optimieren und Zulassen von Datenverkehr ist vertrauenswürdiger Netzwerkdatenverkehr, der an den Endpunkten verschlüsselt und gesichert ist und für das Netzwerk Microsoft 365 ist.</span><span class="sxs-lookup"><span data-stu-id="50b47-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="50b47-131">Contoso hat Folgendes beschlossen:</span><span class="sxs-lookup"><span data-stu-id="50b47-131">Contoso decided to:</span></span>

- <span data-ttu-id="50b47-132">Verwenden Sie den direkten Interneteinzug zum Optimieren und Zulassen von Kategoriedatenverkehr und zum Weiterleiten des Datenverkehrs der Standardkategorie an die zentrale Internetverbindung in Paris.</span><span class="sxs-lookup"><span data-stu-id="50b47-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="50b47-133">Stellen Sie SD-WAN-Geräte in jedem Büro auf einfache Weise zur Verfügung, um diese Prinzipien zu befolgen und eine optimale Netzwerkleistung für Microsoft 365 cloudbasierte Dienste zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="50b47-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="50b47-134">Die SD-WAN-Geräte weisen einen LAN-Port für das lokale Netzwerk und mehrere WAN-Ports auf.</span><span class="sxs-lookup"><span data-stu-id="50b47-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="50b47-135">Ein WAN-Port verbindet sich mit dem MPLS-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="50b47-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="50b47-136">Ein anderer stellt eine Verbindung mit einer lokalen ISP-Schaltung ein.</span><span class="sxs-lookup"><span data-stu-id="50b47-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="50b47-137">Die SD-WAN-Geräte leiten Netzwerkdatenverkehr der Kategorie "Optimize" und "Allow" über die ISP-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="50b47-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="50b47-138">Die Contoso Line-of-Business-App-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="50b47-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="50b47-139">Contoso hat seine Anwendungs- und Serverintranetinfrastruktur für Folgendes entworfen:</span><span class="sxs-lookup"><span data-stu-id="50b47-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="50b47-140">Zweigstellen verwenden lokale Cacheserver, um Dokumente und interne Websites zu speichern, auf die häufig zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="50b47-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="50b47-p107">Regionalstellen verwenden regionale Anwendungsserver für die Regional- und Zweigstellenbüros. Diese Server werden mit den Servern in der Pariser Zentrale synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="50b47-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="50b47-143">Die Pariser Campus-Rechenzentren enthalten zentrale Anwendungsserver, die der gesamten Organisation dienen.</span><span class="sxs-lookup"><span data-stu-id="50b47-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="50b47-144">Abbildung 2 zeigt den Prozentsatz der Netzwerkdatenverkehrkapazität, die beim Zugriff auf Server über das Contoso-Intranet verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="50b47-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![Die Contoso-Infrastruktur für interne Anwendungen](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="50b47-146">**Abbildung 2: Die Contoso-Infrastruktur für interne Anwendungen**</span><span class="sxs-lookup"><span data-stu-id="50b47-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="50b47-147">Für die Büros für Satelliten- oder Regionale Hubs können 60 Prozent der von Mitarbeitern benötigten Ressourcen von Satelliten- und Regionalhubbüros bedient werden.</span><span class="sxs-lookup"><span data-stu-id="50b47-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="50b47-148">Die zusätzlichen 40 Prozent der Ressourcenanforderungen müssen über die WAN-Verbindung zum Pariser Campus gehen.</span><span class="sxs-lookup"><span data-stu-id="50b47-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="50b47-149">Netzwerkanalyse und Vorbereitung Microsoft 365 Unternehmens</span><span class="sxs-lookup"><span data-stu-id="50b47-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="50b47-150">Die erfolgreiche Einführung von Microsoft 365 für Unternehmensdienste durch Contoso-Benutzer hängt von einer hochverf nen verfügbaren und performanten Konnektivität mit dem Internet oder direkt mit Microsoft Cloud Services ab.</span><span class="sxs-lookup"><span data-stu-id="50b47-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="50b47-151">Contoso hat die folgenden Schritte zum Planen und Implementieren einer optimierten Konnektivität Microsoft 365 Enterprise Cloud Services unternommen:</span><span class="sxs-lookup"><span data-stu-id="50b47-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="50b47-152">Erstellen eines Unternehmens-WAN-Netzwerkdiagramms zur Unterstützung der Planung</span><span class="sxs-lookup"><span data-stu-id="50b47-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="50b47-153">Zum Starten der Netzwerkplanung hat Contoso ein Diagramm erstellt, in dem die Bürostandorte, die vorhandene Netzwerkkonnektivität, vorhandene Netzwerkperimetergeräte und Dienstklassen angezeigt werden, die im Netzwerk verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="50b47-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="50b47-154">Dieses Diagramm wurde für jeden nachfolgenden Schritt bei der Planung und Implementierung der Netzwerkkonnektivität verwendet.</span><span class="sxs-lookup"><span data-stu-id="50b47-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="50b47-155">Erstellen eines Plans für Microsoft 365 unternehmensweite Netzwerkkonnektivität</span><span class="sxs-lookup"><span data-stu-id="50b47-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="50b47-156">Contoso verwendete die [Microsoft 365 netzwerkkonnektivitätsprinzipien](microsoft-365-network-connectivity-principles.md) und Beispielreferenznetzwerkarchitekturen, um SD-WAN als bevorzugte Topologie für Microsoft 365 identifizieren.</span><span class="sxs-lookup"><span data-stu-id="50b47-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="50b47-157">Analysieren der Internetverbindungsauslastung und der MPLS-WAN-Bandbreite in jedem Büro und Erhöhen der Bandbreite nach Bedarf</span><span class="sxs-lookup"><span data-stu-id="50b47-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="50b47-158">Die aktuelle Nutzung jedes Büros wurde analysiert, und die Schaltungen wurden erhöht, sodass der vorhergesagte Microsoft 365 cloudbasierten Datenverkehr mit einer durchschnittlichen nicht genutzten Kapazität von 20 Prozent funktionieren würde.</span><span class="sxs-lookup"><span data-stu-id="50b47-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="50b47-159">Optimieren der Leistung für Microsoft-Netzwerkdienste</span><span class="sxs-lookup"><span data-stu-id="50b47-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="50b47-160">Contoso hat die Gruppe der Office 365, Intune und Azure-Endpunkte sowie konfigurierte Firewalls, Sicherheitsgeräte und andere Systeme im Internetpfad für eine optimale Leistung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="50b47-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="50b47-161">Endpunkte für Office 365 Optimize- und Allow-Kategoriedatenverkehr wurden für das Routing über die ISP-Schaltung in die SD-WAN-Geräte konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="50b47-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="50b47-162">Konfigurieren von internem DNS</span><span class="sxs-lookup"><span data-stu-id="50b47-162">Configure internal DNS</span></span>

   <span data-ttu-id="50b47-163">Das DNS muss betriebsbereit sein und für Microsoft 365-Datenverkehr lokal nachgeschlagen werden.</span><span class="sxs-lookup"><span data-stu-id="50b47-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="50b47-164">Überprüfen der Netzwerkendpunkt- und Portkonnektivität</span><span class="sxs-lookup"><span data-stu-id="50b47-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="50b47-165">Contoso hat Microsoft-Netzwerkverbindungstesttools zur Überprüfung der Konnektivität für Microsoft 365 Enterprise-Clouddienste verwendet.</span><span class="sxs-lookup"><span data-stu-id="50b47-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="50b47-166">Optimieren der Mitarbeitercomputer für die Netzwerkkonnektivität</span><span class="sxs-lookup"><span data-stu-id="50b47-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="50b47-167">Einzelne Computer wurden überprüft, um sicherzustellen, dass die neuesten Betriebssystemupdates installiert wurden und dass die Überwachung der Endpunktsicherheit auf allen Clients aktiv war.</span><span class="sxs-lookup"><span data-stu-id="50b47-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="50b47-168">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="50b47-168">Next step</span></span>

<span data-ttu-id="50b47-169">Erfahren Sie, wie Contoso seine lokalen [Active Directory-Domänendienste in](contoso-identity.md) der Cloud für Mitarbeiter und die Verbundauthentifizierung für Kunden und Geschäftspartner nutzt.</span><span class="sxs-lookup"><span data-stu-id="50b47-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="50b47-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50b47-170">See also</span></span>

[<span data-ttu-id="50b47-171">Netzwerk-Roadmap für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="50b47-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="50b47-172">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="50b47-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="50b47-173">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="50b47-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
