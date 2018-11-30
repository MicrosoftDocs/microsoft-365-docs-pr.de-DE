---
title: Netzwerkfunktionen für die Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen zur Contoso-Netzwerkinfrastruktur und dazu, wie die SD-WAN-Technologie für eine optimale Netzwerkkonnektivität für cloudbasierte Microsoft 365 Enterprise-Dienste verwendet wird.
ms.openlocfilehash: 0ef9c37755927444276c83a2c5952b5cb96f22ed
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867553"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="9e39d-103">Netzwerkfunktionen für die Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="9e39d-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="9e39d-104">**Zusammenfassung:** Informationen zur Contoso-Netzwerkinfrastruktur und dazu, wie die SD-WAN-Technologie für eine optimale Netzwerkkonnektivität für cloudbasierte Microsoft 365 Enterprise-Dienste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e39d-104">**Summary:** Understand the Contoso networking infrastructure and how it uses its SD WAN technology for optimal performance network connectivity to Microsoft 365 Enterprise cloud based services.</span></span>

<span data-ttu-id="9e39d-p101">Zur Einführung einer cloudeinschließenden Infrastruktur erkannten die Netzwerktechniker bei Contoso die grundlegende Änderung in der Art und Weise, wie Netzwerkdatenverkehr zu cloudbasierten Diensten fließt. Anstelle eines Speichenmodells, das sich auf die Netzwerkkonnektivität am Hauptsitz konzentriert, wurden Benutzerstandorte lokalen Internetausgängen und lokale Verbindungen Microsoft-Netzwerkspeicherorten im Internet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9e39d-p101">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud-based services travels. Instead of a hub and spoke model that focusses network connectivity on the head office, they worked to map user locations to local Internet egress and local connections to Microsoft network locations on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="9e39d-107">Contosos Netzwerkinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="9e39d-107">Contoso's networking infrastructure</span></span>

<span data-ttu-id="9e39d-108">Die Büros von Contoso werden über die folgenden Elemente des Contoso-Netzwerks miteinander verbunden:</span><span class="sxs-lookup"><span data-stu-id="9e39d-108">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="9e39d-109">MPLS-WAN-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="9e39d-109">MPLS WAN network</span></span>

  <span data-ttu-id="9e39d-p102">Ein MPLS-WAN-Netzwerk verbindet die Zentrale in Paris mit regionalen Niederlassungen und regionale Niederlassungen mit Zweigstellen in einer Speichenkonfiguration. Auf diese Weise können Benutzer auf lokale Server zugreifen, aus denen Branchen-Apps im Pariser Büro bestehen. Außerdem wird der allgemeine Internetdatenverkehr an das Pariser Büro weitergeleitet, wenn Netzwerksicherheitsgeräte die Anforderungen bereinigen. In jedem Büro senden Router Datenverkehr an Hosts oder Funkzugriffspunkte in Subnetzen, für die der private IP-Adressraum verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e39d-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration. This is for users to access on-premises servers that make up line of business applications in the Paris office. It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests. Within each office, routers deliver traffic to hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="9e39d-114">Lokaler direkter Internetzugriff für Office 365-Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="9e39d-114">Local direct Internet access for Office 365 traffic</span></span>

  <span data-ttu-id="9e39d-p103">Jede Niederlassung verfügt über ein SD-WAN-Gerät mit einem oder mehreren ISP-Netzwerkschaltern mit eigener Internetverbindung über einen Proxyserver. Dies wird in der Regel als eine WAN-Verbindung zu einem lokalen ISP implementiert, der auch öffentliche IP-Adressen und IP-Adressen von lokalen DNS-Servern für den Proxyserver bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="9e39d-p103">Each office has an SD WAN device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and local DNS server IP addresses for the proxy server.</span></span>

- <span data-ttu-id="9e39d-117">Internetauftritt</span><span class="sxs-lookup"><span data-stu-id="9e39d-117">Internet presence</span></span>

  <span data-ttu-id="9e39d-p104">Contoso ist im Besitz des öffentlichen Domänennamens „contoso.com“. Die öffentliche Contoso-Website zum Bestellen von Produkten besteht aus einer Gruppe von Servern in einem mit dem Internet verbundenen Rechenzentrum auf dem Pariser Campus. Contoso verwendet einen öffentlichen /24-IP-Adressbereich im Internet.</span><span class="sxs-lookup"><span data-stu-id="9e39d-p104">Contoso owns the contoso.com public domain name. The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="9e39d-121">Abbildung 1 zeigt die Contoso-Netzwerkinfrastruktur und die dazugehörigen Verbindungen mit dem Internet.</span><span class="sxs-lookup"><span data-stu-id="9e39d-121">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![](./media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="9e39d-122">**Abbildung 1: Contoso-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="9e39d-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="9e39d-123">Verwenden des SD-WAN für eine optimale Netzwerkkonnektivität mit Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e39d-123">Use of SD WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="9e39d-124">Contoso folgte den folgenden [Prinzipien von Office 365-Netzwerkverbindungen](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles):</span><span class="sxs-lookup"><span data-stu-id="9e39d-124">Contoso followed [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles):</span></span>

1. <span data-ttu-id="9e39d-125">Identifizieren und Unterscheiden von Office 365-Netzwerkdatenverkehr</span><span class="sxs-lookup"><span data-stu-id="9e39d-125">Identify and differentiate Office 365 network traffic</span></span>
2. <span data-ttu-id="9e39d-126">Lokaler Ausgang von Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="9e39d-126">Egress network connections locally</span></span>
3. <span data-ttu-id="9e39d-127">Vermeiden von Spitzkehren für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="9e39d-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="9e39d-128">Umgehen von doppelten Netzwerksicherheitsgeräten</span><span class="sxs-lookup"><span data-stu-id="9e39d-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="9e39d-p105">Es gibt drei Kategorien von Netzwerkdatenverkehr für Office 365: „Optimize“, „Allow“ und „Default“. Bei „Optimize“ und „Allow“ handelt es sich um vertrauenswürdigen Netzwerkdatenverkehr, der verschlüsselt und an den Endpunkten geschützt ist und an Microsoft-Rechenzentren gerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="9e39d-p105">There are three categories of network traffic for Office 365: Optimize, Allow, and Default. Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for Microsoft datacenters.</span></span>

<span data-ttu-id="9e39d-131">Contoso hat beschlossen, den direkten Internetausgang für Datenverkehr der Kategorie „Optimize“ und „Allow“ zu verwenden und den gesamten Datenverkehr der Kategorie „Default“ an die zentrale Internetverbindung in Paris weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="9e39d-131">Contoso decided to use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

<span data-ttu-id="9e39d-132">An jedem Standort wurden SD-WAN-Geräte bereitgestellt, damit diese Prinzipien problemlos umgesetzt werden konnten und eine optimale Netzwerkleistung für cloudbasierte Microsoft 365-Dienste erzielt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9e39d-132">They decided to deploy SD WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="9e39d-p106">Die SD-WAN-Geräte verfügen über einen LAN-Port für das lokale Niederlassungsnetzwerk und über mehrere WAN-Ports. Ein WAN-Port stellt eine Verbindung zu dem MPLS-Netzwerk her, und andere WAN-Ports stellen eine Verbindung zu lokalen ISP-Schaltungen her. Das SD-WAN-Gerät leitet den Netzwerkdatenverkehr der Kategorie „Optimize“ und „Allow“ an die ISP-Links um.</span><span class="sxs-lookup"><span data-stu-id="9e39d-p106">The SD WAN devices have a LAN port for the local office network and multiple WAN ports. One WAN port connects to their MPLS network and other WAN ports connect to local ISP circuits. The SD WAN device routes Optimize and Allow category network traffic to the ISP links.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="9e39d-136">Contosos Infrastruktur für Branchen-Apps</span><span class="sxs-lookup"><span data-stu-id="9e39d-136">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="9e39d-137">Contoso hat seine Infrastruktur für Branchen-Apps und Server für Folgendes konzipiert:</span><span class="sxs-lookup"><span data-stu-id="9e39d-137">Contoso has architected its line of business application and server infrastructure for the following:</span></span>

- <span data-ttu-id="9e39d-138">Zweigstellen verwenden lokale Cacheserver, um Dokumente und interne Websites zu speichern, auf die häufig zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="9e39d-138">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="9e39d-p107">Regionalstellen verwenden regionale Anwendungsserver für die Regional- und Zweigstellenbüros. Diese Server werden mit den Servern in der Pariser Zentrale synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="9e39d-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="9e39d-141">Auf dem Pariser Campus befinden sich die Rechenzentren mit den zentralen-Anwendungsservern, die das gesamte Unternehmen bedienen.</span><span class="sxs-lookup"><span data-stu-id="9e39d-141">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="9e39d-142">Abbildung 2 zeigt den Prozentsatz des Netzwerkdatenverkehrs beim Zugriff auf Server im Intranet von Contoso.</span><span class="sxs-lookup"><span data-stu-id="9e39d-142">Figure 1 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![](./media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="9e39d-143">**Abbildung 2: Contoso-Infrastruktur für die interne Anwendung**</span><span class="sxs-lookup"><span data-stu-id="9e39d-143">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="9e39d-p108">Für Benutzer in Zweigstellen- oder Regionalbüros können 60 % der von ihnen benötigten Ressourcen von den Zweigstellen- oder Regionalbüroservern bereitgestellt werden.
 Die weiteren 40 % der Ressourcenanforderungen werden über die WAN-Verbindung mit dem Pariser Campus abgedeckt.</span><span class="sxs-lookup"><span data-stu-id="9e39d-p108">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers. The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a><span data-ttu-id="9e39d-146">Netzwerkanalyse und Vorbereitung des Netzwerks auf Microsoft 365 Enterprise bei Contoso</span><span class="sxs-lookup"><span data-stu-id="9e39d-146">Contoso's network analysis and preparation of their network for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="9e39d-p109">Eine erfolgreiche Einführung von Microsoft 365 Enterprise-Diensten bei den Benutzern von Contoso ist von einer hochverfügbaren und leistungsstarken Verbindung zum Internet oder von einer Verbindung direkt mit Microsoft-Clouddiensten abhängig. Contoso hat diese Schritte bei der Planung und Implementierung einer optimierten Verbindung mit Microsoft 365 Enterprise-Clouddiensten berücksichtigt:</span><span class="sxs-lookup"><span data-stu-id="9e39d-p109">Successful adoption of Microsoft 365 Enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services. Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 Enterprise cloud services:</span></span>

1. <span data-ttu-id="9e39d-149">Es wurde ein WAN-Netzwerkdiagramm für das Unternehmen zur Unterstützung der Planung erstellt.</span><span class="sxs-lookup"><span data-stu-id="9e39d-149">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="9e39d-p110">Contoso startete die Netzwerkplanung durch Erstellung eines Diagramms, in dem die Standorte, die vorhandene Netzwerkverbindung, die vorhandenen Netzwerkumkreisgeräte sowie die Dienstklassen dargestellt wurden, die im Netzwerk verwaltet werden. Dieses Diagramm wurde für alle nachfolgenden Schritte bei der Planung und Implementierung der Netzwerkkonnektivität verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e39d-p110">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network. They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="9e39d-152">Es wurde ein Plan für die Microsoft 365 Enterprise-Netzwerkkonnektivität erstellt.</span><span class="sxs-lookup"><span data-stu-id="9e39d-152">Created a plan for Microsoft 365 Enterprise network connectivity</span></span>

   <span data-ttu-id="9e39d-153">Contoso verwendete die [Prinzipien von Office 365-Netzwerkverbindungen](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) und stellte Referenznetzwerkarchitekturen bereit, um SD-WAN als bevorzugte Topologie für Office 365-Konnektivität zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="9e39d-153">Contoso used the [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) and provided reference network architectures to determine SD WAN as their preferred topology for Office 365 connectivity.</span></span>

3. <span data-ttu-id="9e39d-154">In jeder Niederlassung wurde die Auslastung der Internetverbindung und die MPLS-WAN-Bandbreite analysiert und bei Bedarf erhöht.</span><span class="sxs-lookup"><span data-stu-id="9e39d-154">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="9e39d-155">In jeder Niederlassung wurde die aktuelle Nutzung analysiert, und Schaltungen wurden so erhöht, dass der vorhergesagte cloudbasierte Microsoft 365-Datenverkehr mit durchschnittlich 20 % nicht genutzter Kapazität ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="9e39d-155">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="9e39d-156">Optimierte Leistung für Microsoft-Netzwerkdienste</span><span class="sxs-lookup"><span data-stu-id="9e39d-156">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="9e39d-p111">Contoso bestimmte die Gruppe von Office 365-, Intune- und Azure-Endpunkten, konfigurierte Firewalls, Sicherheitsgeräte und andere System im Internetpfad für optimale Leistung. Endpunkte für Office 365-Datenverkehr der Kategorie „Optimize“ und „Allow“ wurden in den SD-WAN-Geräten konfiguriert, die direkten Internetzugriff boten.</span><span class="sxs-lookup"><span data-stu-id="9e39d-p111">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance. Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD WAN devices that provided direct Internet access.</span></span>

5. <span data-ttu-id="9e39d-159">Es wurde ein internes DNS konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9e39d-159">Configured internal DNS</span></span>

   <span data-ttu-id="9e39d-160">Das DNS muss betriebsbereit sein und für Office 365-Datenverkehr lokal nachgeschlagen werden.</span><span class="sxs-lookup"><span data-stu-id="9e39d-160">DNS is required to be functional and to be looked up locally for Office 365 traffic.</span></span>

6. <span data-ttu-id="9e39d-161">Netzwerkendpunkt und Portkonnektivität wurden überprüft.</span><span class="sxs-lookup"><span data-stu-id="9e39d-161">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="9e39d-162">Contoso führte Testtools für die Netzwerkkonnektivität aus, die von Microsoft zur Überprüfung der Konnektivität für Microsoft 365 Enterprise-Clouddienste bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9e39d-162">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 Enterprise cloud services.</span></span>

7. <span data-ttu-id="9e39d-163">Die Netzwerkverbindungen der Computer der Mitarbeiter wurden optimiert.</span><span class="sxs-lookup"><span data-stu-id="9e39d-163">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="9e39d-164">Einzelne Computer wurden überprüft, um sicherzustellen, dass die neuesten Betriebssystemupdates installiert wurden und dass die Endpunkt-Sicherheitsüberwachung auf allen Clients aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="9e39d-164">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="9e39d-165">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="9e39d-165">Next step</span></span>

<span data-ttu-id="9e39d-166">[Erfahren Sie](contoso-identity.md), wie Contoso seine lokalen Identitätsanbieter in der Cloud für Mitarbeiter und Verbundauthentifizierung für Kunden und Geschäftspartner nutzt.</span><span class="sxs-lookup"><span data-stu-id="9e39d-166">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises identity provider in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e39d-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e39d-167">See also</span></span>

[<span data-ttu-id="9e39d-168">Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9e39d-168">Networking for Microsoft 365 Enterprise</span></span>](networking-infrastructure.md)

[<span data-ttu-id="9e39d-169">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="9e39d-169">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9e39d-170">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="9e39d-170">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
