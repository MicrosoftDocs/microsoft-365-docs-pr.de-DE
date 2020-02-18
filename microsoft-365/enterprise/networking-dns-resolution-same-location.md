---
title: 'Schritt 2: Konfigurieren von lokalen Internetverbindungen für jedes Büro'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Für eine bessere Leistung müssen Sie Ihre DNS-Auflösung nachvollziehen und konfigurieren können.
ms.openlocfilehash: 8b4302c06e75c59a1b99eb60399c9df897ad17ea
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066660"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="1ec77-103">Schritt 2: Konfigurieren von lokalen Internetverbindungen für jedes Büro</span><span class="sxs-lookup"><span data-stu-id="1ec77-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="1ec77-104">*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1ec77-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Phase 1 – Netzwerken](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="1ec77-p101">Stellen Sie in Schritt 2 sicher, dass jedes Ihrer Büros über eine lokale Internetverbindung verfügt und lokale DNS-Server verwendet. Beides ist erforderlich, um Verbindungslatenz zu reduzieren und sicherzustellen, dass lokale Clientcomputer Verbindungen zum nächsten Einstiegspunkt für cloudbasierte Microsoft 365-Dienste herstellen.</span><span class="sxs-lookup"><span data-stu-id="1ec77-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="1ec77-108">In herkömmlichen Netzwerken für große Organisationen wird der Internetdatenverkehr über das Netzwerkbackbone zu einer zentralen Internetverbindung geleitet.</span><span class="sxs-lookup"><span data-stu-id="1ec77-108">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection.</span></span> <span data-ttu-id="1ec77-109">Dies eignet sich nicht gut zur Optimierung der Leistung für eine global verteilte SaaS-Infrastruktur (Software-as-a-Service), die die Office 365- und Intune-Produkte in Microsoft 365 umfasst.</span><span class="sxs-lookup"><span data-stu-id="1ec77-109">This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Intune products in Microsoft 365.</span></span>

<span data-ttu-id="1ec77-110">Das globale Microsoft-Netzwerk umfasst eine *Distributed Service Frontdoor-Infrastruktur*, ein hochgradig verfügbares und skalierbares Netzwerk-Edge mit geografisch verteilten Standorten.</span><span class="sxs-lookup"><span data-stu-id="1ec77-110">The Microsoft Global Network includes a *Distributed Service Front Door* infrastructure, a highly available and scalable network edge with geographically distributed locations.</span></span> <span data-ttu-id="1ec77-111">Es beendet die Endbenutzerverbindungen auf einem Frontdoor-Server und leitet den Endbenutzerdatenverkehr innerhalb des globalen Microsoft-Netzwerks effizient weiter.</span><span class="sxs-lookup"><span data-stu-id="1ec77-111">It terminates end user connections at a front door server and efficiently routes end user traffic within the Microsoft Global Network.</span></span>

![Das Globale Microsoft-Netzwerk](../media/networking-dns-resolution-same-location/microsoft-global-network.png)

<span data-ttu-id="1ec77-113">Die beste Leistung wird erzielt, wenn lokale Clients auf einen Frontdoor-Standort zugreifen, der ihnen geografisch am nächsten ist, statt Datenverkehr über ein Netzwerk-Backbone und zum Frontdoor-Server zu senden, der der zentralen Internetverbindung der Organisation am nächsten ist.</span><span class="sxs-lookup"><span data-stu-id="1ec77-113">For the best performance, on-premises clients should access a front door location that is geographically closest to them, rather than sending the traffic over a network backbone and to the front door that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="1ec77-114">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1ec77-114">Here’s an example.</span></span>

![Beispiel für das Globale Microsoft-Netzwerk](../media/networking-dns-resolution-same-location/microsoft-global-network-example.png)

<span data-ttu-id="1ec77-116">Ein Benutzer in der Pariser Zweigniederlassung möchte auf eine SharePoint Online-Website zugreifen:</span><span class="sxs-lookup"><span data-stu-id="1ec77-116">When a user in the Paris branch office wants to access a SharePoint Online site:</span></span>

1. <span data-ttu-id="1ec77-117">Er sendet eine DNS-Abfrage, um einen Namen aufzulösen, z. B. "contoso.sharepoint.com".</span><span class="sxs-lookup"><span data-stu-id="1ec77-117">It sends a DNS query to resolve a name, such as contoso.sharepoint.com.</span></span> 
2. <span data-ttu-id="1ec77-118">Der vom Internetdienstanbieter bereitgestellte DNS-Server leitet diese Abfrage an einen Microsoft-DNS-Server weiter.</span><span class="sxs-lookup"><span data-stu-id="1ec77-118">The DNS server provided by the ISP forwards that query to a Microsoft DNS server.</span></span>
3. <span data-ttu-id="1ec77-119">Die Microsoft-DNS-Server gleichen die Quell-IP-Adresse der weitergeleiteten DNS-Abfrage mit der Region der Welt ab, der diese Adresse zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1ec77-119">Microsoft’s DNS servers match the source IP address of the forwarded DNS query to the region of the world assigned that address.</span></span> <span data-ttu-id="1ec77-120">Der Microsoft-DNS-Server antwortet mit der IP-Adresse der nächstgelegenen Frontdoor des Microsoft-Netzwerks in Europa.</span><span class="sxs-lookup"><span data-stu-id="1ec77-120">The Microsoft DNS server responds with the IP address of the nearest Microsoft Network front door in Europe.</span></span>
4. <span data-ttu-id="1ec77-121">Der ISP-DNS-Server sendet diese IP-Adresse an den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1ec77-121">The ISP DNS server sends that IP address to the user.</span></span>
5. <span data-ttu-id="1ec77-122">Der Benutzer initiiert eine Verbindung mit dem SharePoint-Server über die Europa-Frontdoor.</span><span class="sxs-lookup"><span data-stu-id="1ec77-122">The user initiates a connection to the SharePoint server through the Europe front door.</span></span>

<span data-ttu-id="1ec77-123">Um eine Clientanforderung an den geografisch nächsten Frontdoor-Server zu leiten, verwenden die DNS-Server von Microsoft die DNS-Abfragen, die der anfänglichen Verbindungsanforderung des Clients entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1ec77-123">To direct a client request to the geographically nearest front door, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request.</span></span> <span data-ttu-id="1ec77-124">Daher gilt für die niedrigste Netzwerklatenz Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1ec77-124">Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="1ec77-125">Alle Büros Ihrer Organisation sollten eine lokale Internetverbindung für den Netzwerkdatenverkehr der Kategorie [Optimieren](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) haben.</span><span class="sxs-lookup"><span data-stu-id="1ec77-125">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="1ec77-126">Jede lokale Internetverbindung sollte einen regionalen DNS-Server für ausgehenden Internetdatenverkehr von diesem Ort verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ec77-126">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="1ec77-127">Weitere Informationen finden Sie unter [Lokaler Ausgang von Netzwerkverbindungen](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span><span class="sxs-lookup"><span data-stu-id="1ec77-127">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="1ec77-128">Als Zwischenprüfung können Sie die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step2) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="1ec77-128">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="1ec77-129">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="1ec77-129">Next step</span></span>

|||
|:-------|:-----|
|![Schritt 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="1ec77-131">Vermeiden von Spitzkehren für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="1ec77-131">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
