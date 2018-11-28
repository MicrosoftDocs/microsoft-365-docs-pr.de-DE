---
title: 'Schritt 2: Konfigurieren von lokalen Internetverbindungen für jedes Büro'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Für eine bessere Leistung müssen Sie Ihre DNS-Auflösung nachvollziehen und konfigurieren können.
ms.openlocfilehash: 6087a5a8e9ff6c3f93a25725f8d2077f2c4f81e3
ms.sourcegitcommit: 333005ce667ec339efcc2b64d2a342e34dc069d8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "25890305"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="fe3fc-103">Schritt 2: Konfigurieren von lokalen Internetverbindungen für jedes Büro</span><span class="sxs-lookup"><span data-stu-id="fe3fc-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="fe3fc-104">*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fe3fc-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="fe3fc-p101">Stellen Sie in Schritt 2 sicher, dass jedes Ihrer Büros über eine lokale Internetverbindung verfügt und lokale DNS-Server verwendet. Beides ist erforderlich, um Verbindungslatenz zu reduzieren und sicherzustellen, dass lokale Clientcomputer Verbindungen zum nächsten Einstiegspunkt für cloudbasierte Microsoft 365-Dienste herstellen.</span><span class="sxs-lookup"><span data-stu-id="fe3fc-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="fe3fc-p102">In herkömmlichen Netzwerken für große Organisationen läuft der Internetdatenverkehr über das Netzwerk-Backbone zu einer zentralen Internetverbindung. Dies funktioniert nicht gut, um die Leistung auf eine global verteilte Software-as-a-Service-Infrastruktur (SaaS) zu optimieren, die die Office 365- und Enterprise Mobility + Security(EMS)-Produkte in Microsoft 365 enthält.</span><span class="sxs-lookup"><span data-stu-id="fe3fc-p102">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection. This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Enterprise Mobility + Security (EMS) products in Microsoft 365.</span></span>

<span data-ttu-id="fe3fc-p103">Das Microsoft Global Network beinhaltet Front-End-Server zu den Clouddiensten für Microsoft 365 weltweit. Die beste Leistung wird erzielt, wenn lokale Clients auf einen Front-End-Server zugreifen, der ihnen geografisch am nächsten ist, statt Datenverkehr über ein Netzwerk-Backbone und zum Front-End-Server zu senden, der am nächsten zur zentralen Internetverbindung der Organisation ist.</span><span class="sxs-lookup"><span data-stu-id="fe3fc-p103">The Microsoft Global Network includes front end servers to the set of cloud services for Microsoft 365 all over the world. For the best performance, on-premises clients should access a front-end server that is geographically closest to them, rather than sending the traffic over a network backbone and to the front-end server that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="fe3fc-p104">Um eine Clientanforderung an den geografisch nächsten Front-End-Server zu leiten, verwenden die DNS-Server von Microsoft die DNS-Abfragen, die der anfänglichen Verbindungsanforderung des Clients entsprechen. Daher gilt für die niedrigste Netzwerklatenz Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fe3fc-p104">To direct a client request to the geographically nearest front-end server, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request. Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="fe3fc-113">Alle Büros Ihrer Organisation sollten eine lokale Internetverbindung für den Netzwerkdatenverkehr der Kategorie [Optimieren](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) haben.</span><span class="sxs-lookup"><span data-stu-id="fe3fc-113">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="fe3fc-114">Jede lokale Internetverbindung sollte einen regionalen DNS-Server für ausgehenden Internetdatenverkehr von diesem Ort verwenden.</span><span class="sxs-lookup"><span data-stu-id="fe3fc-114">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="fe3fc-115">Weitere Informationen finden Sie unter [Lokaler Ausgang von Netzwerkverbindungen](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span><span class="sxs-lookup"><span data-stu-id="fe3fc-115">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="fe3fc-116">Als Zwischenprüfung können Sie die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step2) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="fe3fc-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="fe3fc-117">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="fe3fc-117">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="fe3fc-118">Vermeiden von Spitzkehren für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="fe3fc-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
