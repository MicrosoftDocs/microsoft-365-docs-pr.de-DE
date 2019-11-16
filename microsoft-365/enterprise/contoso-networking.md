---
title: Netzwerkfunktionen für die Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen zur Contoso-Netzwerkinfrastruktur und dazu, wie die SD-WAN-Technologie für eine optimale Netzwerkleistung für cloudbasierte Microsoft 365 Enterprise-Dienste verwendet wird.
ms.openlocfilehash: 87584660805608c45b36e13804ca1dab6b8e7d17
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673171"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="d4363-103">Netzwerkfunktionen für die Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="d4363-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="d4363-p101">Zur Einführung einer cloudeinschließenden Infrastruktur erkannten die Netzwerktechniker bei Contoso die grundlegende Änderung in der Art und Weise, wie Netzwerkdatenverkehr zu Clouddiensten fließt. Anstelle eines internen Hub-and-Spoke-Modells, das sich auf die Netzwerkkonnektivität und -datenverkehr für die nächste Ebene der Contoso-Bürohierarchie konzentriert, wurden Benutzerstandorte lokalen Internetausgängen und lokale Verbindungen den nächstgelegenen Microsoft 365-Netzwerkspeicherorten im Internet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d4363-p101">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud services travels. Instead of an internal hub and spoke model that focusses network connectivity and traffic for the next level of the Contoso office hierarchy, they worked to map user locations to local Internet egress and local connections to the closest Microsoft 365 network location on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="d4363-106">Contosos Netzwerkinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="d4363-106">Contoso's networking infrastructure</span></span>

<span data-ttu-id="d4363-107">Die Büros von Contoso werden über die folgenden Elemente des Contoso-Netzwerks miteinander verbunden:</span><span class="sxs-lookup"><span data-stu-id="d4363-107">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="d4363-108">MPLS-WAN-Netzwerk (Multiprotocol Label Switching)</span><span class="sxs-lookup"><span data-stu-id="d4363-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="d4363-p102">Ein MPLS-WAN-Netzwerk verbindet die Zentrale in Paris mit regionalen Niederlassungen und regionale Niederlassungen mit Zweigstellen in einer Hub-and-Spoke-Konfiguration. Auf diese Weise können Benutzer auf lokale Server zugreifen, aus denen Branchen-Apps im Pariser Büro bestehen. Außerdem wird der allgemeine Internetdatenverkehr an das Pariser Büro weitergeleitet, wenn Netzwerksicherheitsgeräte die Anforderungen bereinigen. In jedem Büro senden Router Datenverkehr an kabelgebundene Hosts oder Funkzugriffspunkte in Subnetzen, für die der private IP-Adressraum verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4363-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration. This is for users to access on-premises servers that make up line of business applications in the Paris office. It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="d4363-113">Lokaler direkter Internetzugriff für Microsoft 365-Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="d4363-113">Local direct Internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="d4363-p103">Jede Niederlassung verfügt über ein Software-Defined-WAN (SD-WAN)-Gerät mit einem oder mehreren ISP-Netzwerkschaltern mit eigener Internetverbindung über einen Proxyserver. Dies wird in der Regel als eine WAN-Verbindung zu einem lokalen ISP implementiert, der auch öffentliche IP-Adressen und einen lokalen DNS-Server bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d4363-p103">Each office has a Software-Defined WAN (SD-WAN) device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="d4363-116">Internetauftritt</span><span class="sxs-lookup"><span data-stu-id="d4363-116">Internet presence</span></span>

  <span data-ttu-id="d4363-p104">Contoso ist im Besitz des öffentlichen Domänennamens „contoso.com“. Die öffentliche Contoso-Website zum Bestellen von Produkten besteht aus einer Gruppe von Servern in einem mit dem Internet verbundenen Rechenzentrum auf dem Pariser Campus. Contoso verwendet einen öffentlichen /24-IP-Adressbereich im Internet.</span><span class="sxs-lookup"><span data-stu-id="d4363-p104">Contoso owns the contoso.com public domain name. The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="d4363-120">Abbildung 1 zeigt die Contoso-Netzwerkinfrastruktur und die dazugehörigen Verbindungen mit dem Internet.</span><span class="sxs-lookup"><span data-stu-id="d4363-120">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![Contoso-Netzwerk](./media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="d4363-122">**Abbildung 1: Contoso-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="d4363-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="d4363-123">Verwenden des SD-WAN für eine optimale Netzwerkkonnektivität mit Microsoft</span><span class="sxs-lookup"><span data-stu-id="d4363-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="d4363-124">Contoso folgte den folgenden [Prinzipien von Office 365-Netzwerkverbindungen](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) bei folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="d4363-124">Contoso followed [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) to:</span></span>

1. <span data-ttu-id="d4363-125">Identifizieren und Unterscheiden von Office 365-Netzwerkdatenverkehr</span><span class="sxs-lookup"><span data-stu-id="d4363-125">Identify and differentiate Office 365 network traffic</span></span>
2. <span data-ttu-id="d4363-126">Lokaler Ausgang von Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="d4363-126">Egress network connections locally</span></span>
3. <span data-ttu-id="d4363-127">Vermeiden von Spitzkehren für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="d4363-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="d4363-128">Umgehen von doppelten Netzwerksicherheitsgeräten</span><span class="sxs-lookup"><span data-stu-id="d4363-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="d4363-129">Es gibt drei Kategorien von Netzwerkdatenverkehr für Office 365: "Optimize", "Allow" und "Default".</span><span class="sxs-lookup"><span data-stu-id="d4363-129">There are three categories of network traffic for Office 365: Optimize, Allow, and Default.</span></span> <span data-ttu-id="d4363-130">Bei "Optimize" und "Allow" handelt es sich um vertrauenswürdigen Netzwerkdatenverkehr, der verschlüsselt und an den Endpunkten geschützt und an das Microsoft 365-Netzwerk gerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="d4363-130">Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="d4363-131">Contoso hat Folgendes beschlossen:</span><span class="sxs-lookup"><span data-stu-id="d4363-131">Contoso decided to:</span></span>

- <span data-ttu-id="d4363-132">Der direkte Internetausgang für Datenverkehr der Kategorie "Optimize" und "Allow" wird verwendet und der gesamte Datenverkehr der Kategorie "Default" wird an die zentrale Internetverbindung in Paris weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="d4363-132">Use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

- <span data-ttu-id="d4363-133">An jedem Standort wurden SD-WAN-Geräte bereitgestellt, damit diese Prinzipien problemlos umgesetzt werden konnten und eine optimale Netzwerkleistung für cloudbasierte Microsoft 365-Dienste erzielt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d4363-133">Deploy SD-WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="d4363-134">Die SD-WAN-Geräte weisen einen LAN-Port für das lokale Netzwerk und mehrere WAN-Ports auf.</span><span class="sxs-lookup"><span data-stu-id="d4363-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="d4363-135">Ein WAN-Port stellt eine Verbindung mit dem MPLS-Netzwerk her, und ein weiterer WAN-Port stellt eine Verbindung mit einem lokalen ISP-Schaltkreis her.</span><span class="sxs-lookup"><span data-stu-id="d4363-135">One WAN port connects to their MPLS network and another WAN port connects to a local ISP circuit.</span></span> <span data-ttu-id="d4363-136">Die SD-WAN-Geräte leiten Netzwerkdatenverkehr der Kategorie "Optimize" und "Allow" über die ISP-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="d4363-136">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="d4363-137">Contosos Infrastruktur für Branchen-Apps</span><span class="sxs-lookup"><span data-stu-id="d4363-137">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="d4363-138">Contoso hat seine Intranetinfrastruktur für Branchen-Apps und Server für Folgendes konzipiert:</span><span class="sxs-lookup"><span data-stu-id="d4363-138">Contoso has architected its line of business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="d4363-139">Zweigstellen verwenden lokale Cacheserver, um Dokumente und interne Websites zu speichern, auf die häufig zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="d4363-139">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="d4363-p107">Regionalstellen verwenden regionale Anwendungsserver für die Regional- und Zweigstellenbüros. Diese Server werden mit den Servern in der Pariser Zentrale synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="d4363-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="d4363-142">Auf dem Pariser Campus befinden sich die Rechenzentren mit den zentralen-Anwendungsservern, die das gesamte Unternehmen bedienen.</span><span class="sxs-lookup"><span data-stu-id="d4363-142">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="d4363-143">Abbildung 2 zeigt den Prozentsatz des Netzwerkdatenverkehrs beim Zugriff auf Server im Intranet von Contoso.</span><span class="sxs-lookup"><span data-stu-id="d4363-143">Figure 2 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![Contosos Infrastruktur für die interne Anwendung](./media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="d4363-145">**Abbildung 2: Contoso-Infrastruktur für die interne Anwendung**</span><span class="sxs-lookup"><span data-stu-id="d4363-145">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="d4363-p108">Für Benutzer in Zweigstellen- oder Regionalbüros können 60 % der von ihnen benötigten Ressourcen von den Zweigstellen- oder Regionalbüroservern bereitgestellt werden.
 Die weiteren 40 % der Ressourcenanforderungen werden über die WAN-Verbindung mit dem Pariser Campus abgedeckt.</span><span class="sxs-lookup"><span data-stu-id="d4363-p108">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers. The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a><span data-ttu-id="d4363-148">Netzwerkanalyse und Vorbereitung des Netzwerks auf Microsoft 365 Enterprise bei Contoso</span><span class="sxs-lookup"><span data-stu-id="d4363-148">Contoso's network analysis and preparation of their network for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d4363-p109">Eine erfolgreiche Einführung von Microsoft 365 Enterprise-Diensten bei den Benutzern von Contoso ist von einer hochverfügbaren und leistungsstarken Verbindung zum Internet oder von einer Verbindung direkt mit Microsoft-Clouddiensten abhängig. Contoso hat diese Schritte bei der Planung und Implementierung einer optimierten Verbindung mit Microsoft 365 Enterprise-Clouddiensten berücksichtigt:</span><span class="sxs-lookup"><span data-stu-id="d4363-p109">Successful adoption of Microsoft 365 Enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services. Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 Enterprise cloud services:</span></span>

1. <span data-ttu-id="d4363-151">Es wurde ein WAN-Netzwerkdiagramm für das Unternehmen zur Unterstützung der Planung erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4363-151">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="d4363-p110">Contoso startete die Netzwerkplanung durch Erstellung eines Diagramms, in dem die Standorte, die vorhandene Netzwerkverbindung, die vorhandenen Netzwerkumkreisgeräte sowie die Dienstklassen dargestellt wurden, die im Netzwerk verwaltet werden. Dieses Diagramm wurde für alle nachfolgenden Schritte bei der Planung und Implementierung der Netzwerkkonnektivität verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4363-p110">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network. They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="d4363-154">Es wurde ein Plan für die Microsoft 365 Enterprise-Netzwerkkonnektivität erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4363-154">Created a plan for Microsoft 365 Enterprise network connectivity</span></span>

   <span data-ttu-id="d4363-155">Contoso verwendete die [Prinzipien von Office 365-Netzwerkverbindungen](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) und stellte Referenznetzwerkarchitekturen bereit, um SD-WAN als bevorzugte Topologie für Office 365-Konnektivität zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="d4363-155">Contoso used the [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) and provided reference network architectures to determine SD-WAN as their preferred topology for Office 365 connectivity.</span></span>

3. <span data-ttu-id="d4363-156">In jeder Niederlassung wurde die Auslastung der Internetverbindung und die MPLS-WAN-Bandbreite analysiert und bei Bedarf erhöht.</span><span class="sxs-lookup"><span data-stu-id="d4363-156">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="d4363-157">In jeder Niederlassung wurde die aktuelle Nutzung analysiert, und Schaltungen wurden so erhöht, dass der vorhergesagte cloudbasierte Microsoft 365-Datenverkehr mit durchschnittlich 20 % nicht genutzter Kapazität ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d4363-157">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="d4363-158">Optimierte Leistung für Microsoft-Netzwerkdienste</span><span class="sxs-lookup"><span data-stu-id="d4363-158">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="d4363-159">Contoso bestimmte die Gruppe von Office 365-, Intune- und Azure-Endpunkten, konfigurierte Firewalls, Sicherheitsgeräte und andere Systeme im Internetpfad für optimale Leistung.</span><span class="sxs-lookup"><span data-stu-id="d4363-159">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance.</span></span> <span data-ttu-id="d4363-160">Endpunkte für Office 365-Datenverkehr der Kategorie "Optimize" und "Allow" wurden in den SD-WAN-Geräten für das Routing über den ISP-Schaltkreis konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d4363-160">Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="d4363-161">Es wurde ein internes DNS konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d4363-161">Configured internal DNS</span></span>

   <span data-ttu-id="d4363-162">Das DNS muss betriebsbereit sein und für Office 365-Datenverkehr lokal nachgeschlagen werden.</span><span class="sxs-lookup"><span data-stu-id="d4363-162">DNS is required to be functional and to be looked up locally for Office 365 traffic.</span></span>

6. <span data-ttu-id="d4363-163">Netzwerkendpunkt und Portkonnektivität wurden überprüft.</span><span class="sxs-lookup"><span data-stu-id="d4363-163">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="d4363-164">Contoso führte Testtools für die Netzwerkkonnektivität aus, die von Microsoft zur Überprüfung der Konnektivität für Microsoft 365 Enterprise-Clouddienste bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="d4363-164">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 Enterprise cloud services.</span></span>

7. <span data-ttu-id="d4363-165">Die Netzwerkverbindungen der Computer der Mitarbeiter wurden optimiert.</span><span class="sxs-lookup"><span data-stu-id="d4363-165">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="d4363-166">Einzelne Computer wurden überprüft, um sicherzustellen, dass die neuesten Betriebssystemupdates installiert wurden und dass die Endpunkt-Sicherheitsüberwachung auf allen Clients aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="d4363-166">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="d4363-167">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d4363-167">Next step</span></span>

<span data-ttu-id="d4363-168">[Erfahren Sie](contoso-identity.md), wie Contoso seine lokalen Active Directory Domain Services (AD DS) in der Cloud für Mitarbeiter und Verbundauthentifizierung für Kunden und Geschäftspartner nutzt.</span><span class="sxs-lookup"><span data-stu-id="d4363-168">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises Active Directory Domain Services (AD DS) in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4363-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4363-169">See also</span></span>

[<span data-ttu-id="d4363-170">Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d4363-170">Networking for Microsoft 365 Enterprise</span></span>](networking-infrastructure.md)

[<span data-ttu-id="d4363-171">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="d4363-171">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d4363-172">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="d4363-172">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
