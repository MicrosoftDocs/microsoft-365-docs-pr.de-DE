---
title: 'Schritt 3: Vermeiden von Spitzkehren für Netzwerke'
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
description: Verstehen und entfernen Sie Spitzkehren für Netzwerke für eine bessere Leistung.
ms.openlocfilehash: b661b697d6c4294aefb95f1ce7c56f631ae36f81
ms.sourcegitcommit: 333005ce667ec339efcc2b64d2a342e34dc069d8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "25892285"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="61506-103">Schritt 3: Vermeiden von Spitzkehren für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="61506-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="61506-104">*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="61506-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="61506-p101">Eine [Spitzkehre für Netzwerke](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) tritt ein, wenn Datenverkehr für ein Ziel zunächst an ein anderes Zwischenziel geleitet wird, wie einen lokalen Sicherheitsstapel, einen Cloudzugriffsbroker oder ein cloudbasiertes Webgateway. Eine Spitzkehre für Netzwerke kann auch durch fehlerhaftes Routing im Internet aufgrund von Netzwerkdienstanbietern verursacht werden. Eine Spitzkehre sorgt für Latenz und kann Datenverkehr potenziell an ein geografisch entferntes Ziel umleiten.</span><span class="sxs-lookup"><span data-stu-id="61506-p101">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway. A network hairpin could also be caused by poor routing on the Internet due to network service providers. A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="61506-p102">Überprüfen Sie zum Optimieren der Leistung für den Datenverkehr zu cloudbasierten Microsoft 365-Diensten, ob der ISP, der die lokale Internetverbindung bereitstellt, über eine direkte Peering-Beziehung mit dem Microsoft Global Network in der Nähe dieses Ziels verfügt. Diese Verbindungen haben keine Spitzkehren.</span><span class="sxs-lookup"><span data-stu-id="61506-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="61506-p103">Wenn Sie cloudbasierte Netzwerk- oder Sicherheitsdienste für Microsoft 365-Datenverkehr verwenden, stellen Sie sicher, dass der Spitzkehreneffekt ausgewertet und die Auswirkung auf die Leistung verstanden wird. Überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="61506-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="61506-112">Anzahl und Ziele der Dienstanbieter, durch die der Datenverkehr in Beziehung zu Ihren Zweigstellen und Microsoft Global Network-Peering-Punkten weitergeleitet wird</span><span class="sxs-lookup"><span data-stu-id="61506-112">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="61506-113">Qualität der Netzwerk-Peering-Beziehung des Dienstanbieters mit Ihrem ISP und Microsoft</span><span class="sxs-lookup"><span data-stu-id="61506-113">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="61506-114">Leistungseinbußen von Backhauling in der Infrastruktur des Dienstanbieters</span><span class="sxs-lookup"><span data-stu-id="61506-114">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="61506-115">Wann immer möglich, konfigurieren Sie Ihre Edge-Router, um vertrauenswürdigen Microsoft 365-Datenverkehr direkt zu senden, statt ihn über eine Drittanbietercloud oder einen cloudbasierten Netzwerksicherheitsanbieterweiterzuleiten oder zu tunneln, der Ihren Internetdatenverkehr verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="61506-115">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

<span data-ttu-id="61506-116">Als Zwischenprüfung können Sie die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step3) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="61506-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="61506-117">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="61506-117">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="61506-118">Konfigurieren von Datenverkehrumgehungen</span><span class="sxs-lookup"><span data-stu-id="61506-118">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
