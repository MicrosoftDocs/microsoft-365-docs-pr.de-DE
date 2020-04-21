---
title: 'Schritt 3: Vermeiden von Spitzkehren für Netzwerke'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und entfernen Sie Spitzkehren für Netzwerke für eine bessere Leistung.
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583425"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="a5244-103">Schritt 3: Vermeiden von Spitzkehren für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="a5244-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="a5244-104">*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a5244-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Phase 1: Vernetzung](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="a5244-106">Eine [Netzwerkhaarnadel](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) liegt vor, wenn der an ein Ziel gerichtete Datenverkehr zuerst an einen weiteren Zwischenstandort umgeleitet wird, z. B. an einen lokalen Sicherheitsstapel, einen Cloudzugriffsbroker oder ein cloudbasiertes Webgateway.</span><span class="sxs-lookup"><span data-stu-id="a5244-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="a5244-107">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a5244-107">Here is an example.</span></span>

![Beispiel für eine Netzwerkhaarnadel](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="a5244-109">Eine Netzwerkhaarnadel kann auch durch unzureichendes Routing im Internet durch Netzwerkdienstanbieter verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="a5244-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="a5244-110">Eine Haarnadel fügt Latenz hinzu und kann potenziell den Datenverkehr an einen geografisch entfernten Standort umleiten.</span><span class="sxs-lookup"><span data-stu-id="a5244-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="a5244-p102">Überprüfen Sie zum Optimieren der Leistung für den Datenverkehr zu cloudbasierten Microsoft 365-Diensten, ob der ISP, der die lokale Internetverbindung bereitstellt, über eine direkte Peering-Beziehung mit dem Microsoft Global Network in der Nähe dieses Ziels verfügt. Diese Verbindungen haben keine Spitzkehren.</span><span class="sxs-lookup"><span data-stu-id="a5244-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="a5244-p103">Wenn Sie cloudbasierte Netzwerk- oder Sicherheitsdienste für Microsoft 365-Datenverkehr verwenden, stellen Sie sicher, dass der Spitzkehreneffekt ausgewertet und die Auswirkung auf die Leistung verstanden wird. Überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a5244-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="a5244-115">Anzahl und Ziele der Dienstanbieter, durch die der Datenverkehr in Beziehung zu Ihren Zweigstellen und Microsoft Global Network-Peering-Punkten weitergeleitet wird</span><span class="sxs-lookup"><span data-stu-id="a5244-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="a5244-116">Qualität der Netzwerk-Peering-Beziehung des Dienstanbieters mit Ihrem ISP und Microsoft</span><span class="sxs-lookup"><span data-stu-id="a5244-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="a5244-117">Leistungseinbußen von Backhauling in der Infrastruktur des Dienstanbieters</span><span class="sxs-lookup"><span data-stu-id="a5244-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="a5244-118">Wann immer möglich, konfigurieren Sie Ihre Edge-Router, um vertrauenswürdigen Microsoft 365-Datenverkehr direkt zu senden, statt ihn über eine Drittanbietercloud oder einen cloudbasierten Netzwerksicherheitsanbieterweiterzuleiten oder zu tunneln, der Ihren Internetdatenverkehr verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a5244-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![Beispiel für die Umgehung einer Netzwerkhaarnadel](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="a5244-120">Um zu testen, wie nahe Sie sich an einem Einstiegspunkt zum globalen Microsoft-Netzwerk befinden, und wie nahe Sie sich an dem Punkt befinden, an dem das Netzwerk Ihrer Organisation mit Ihrem ISP verbunden ist, verwenden Sie das [Office 365 Network Onboarding-Tool](https://connectivity.office.com/).</span><span class="sxs-lookup"><span data-stu-id="a5244-120">To test how close you are to an entry point for Microsoft’s global network and how close you are to the point where your organization network connects to your ISP, use the [Office 365 Network Onboarding tool](https://connectivity.office.com/).</span></span>

<span data-ttu-id="a5244-121">Als Zwischenprüfung können Sie die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step3) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="a5244-121">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a5244-122">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="a5244-122">Next step</span></span>

|||
|:-------|:-----|
|![Schritt 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="a5244-124">Konfigurieren von Datenverkehrumgehungen</span><span class="sxs-lookup"><span data-stu-id="a5244-124">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
