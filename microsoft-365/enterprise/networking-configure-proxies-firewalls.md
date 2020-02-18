---
title: 'Schritt 4: Konfigurieren von Datenverkehrumgehungen'
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
description: Verstehen und Konfigurieren von Webbrowsern und Edge-Geräten für Datenverkehrumgehungen zu vertrauenswürdigen Office 365-Speicherorten.
ms.openlocfilehash: 71f62c5e245962f3514c49477e3cdeda17cb6397
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066686"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="58aef-103">Schritt 4: Konfigurieren von Datenverkehrumgehungen</span><span class="sxs-lookup"><span data-stu-id="58aef-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="58aef-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="58aef-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Phase 1: Vernetzung](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="58aef-106">Da allgemeiner Internetdatenverkehr riskant sein kann, erzwingen typische Organisationsnetzwerke Sicherheit über Edge-Geräte wie Proxyserver, SSL Break and Inspect, Paketüberprüfungsgeräte sowie Systeme zur Verhinderung von Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="58aef-106">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="58aef-107">Unter [Verwenden von Netzwerkgeräten oder -lösungen von Drittanbietern für Office 365-Datenverkehr](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365) finden Sie einige Probleme mit Netzwerk-Abfanggeräten.</span><span class="sxs-lookup"><span data-stu-id="58aef-107">Read about some of the issues with network interception devices at [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span></span>

<span data-ttu-id="58aef-p102">Die DNS-Domänennamen und IP-Adressen, die von cloudbasierten Microsoft 365-Diensten verwendet werden, sind bekannt. Zudem sind Datenverkehr und Dienste selbst durch viele Sicherheitsfeatures geschützt. Durch diese Sicherheit und diesen Schutz müssen Ihre Edge-Geräte dies nicht duplizieren. Zwischenziele und doppelte Sicherheitsverarbeitung für Microsoft 365-Datenverkehr können die Leistung erheblich senken.</span><span class="sxs-lookup"><span data-stu-id="58aef-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="58aef-p103">Der erste Schritt zur Eliminierung von Zwischenzielen und doppelter Sicherheitsverarbeitung ist die Identifizierung von Microsoft 365-Datenverkehr. Microsoft hat die folgenden Typen von DNS-Domänennamen und IP-Adressbereichen, bekannt als Endpunkte, definiert:</span><span class="sxs-lookup"><span data-stu-id="58aef-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="58aef-114">**Optimieren** – erforderlich für Verbindungen zu jedem Office 365-Dienst, repräsentiert mehr als 75 % der Microsoft 365-Bandbreite, -Verbindungen und -Datenmenge.</span><span class="sxs-lookup"><span data-stu-id="58aef-114">**Optimize** - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data.</span></span> <span data-ttu-id="58aef-115">Diese Endpunkte bilden Microsoft 365-Szenarien ab, die am sensibelsten in Bezug auf Leistung, Latenz und Verfügbarkeit im Netzwerk sind.</span><span class="sxs-lookup"><span data-stu-id="58aef-115">These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency, and availability.</span></span>
- <span data-ttu-id="58aef-116">**Zulassen** – erforderlich für Konnektivität zu speziellen Microsoft 365-Diensten und -Features, die jedoch in Bezug auf Leistung und Latenz im Netzwerk nicht so sensibel sind wie die in der Kategorie „Optimieren“.</span><span class="sxs-lookup"><span data-stu-id="58aef-116">**Allow** - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="58aef-117">**Standard** – repräsentiert Microsoft 365-Dienste und -Abhängigkeiten, für die keine Optimierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="58aef-117">**Default** - Represent Microsoft 365 services and dependencies that do not require any optimization.</span></span> <span data-ttu-id="58aef-118">Sie können standardmäßige Kategorie-Endpunkte als normalen Internetdatenverkehr behandeln.</span><span class="sxs-lookup"><span data-stu-id="58aef-118">You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="58aef-119">Sie finden die DNS-Domänennamen und IP-Adressbereiche unter [ https://aka.ms/o365endpoints ](https://aka.ms/o365endpoints).</span><span class="sxs-lookup"><span data-stu-id="58aef-119">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="58aef-120">Microsoft empfiehlt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="58aef-120">Microsoft recommends that you:</span></span>

- <span data-ttu-id="58aef-121">Verwenden Sie Proxy Automatic Configuration(PAC)-Skripts für die Internetbrowser Ihrer lokalen Computer, um Ihre Proxyserver für die DNS-Domänennamen cloudbasierter Microsoft 365-Dienste zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="58aef-121">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services.</span></span> <span data-ttu-id="58aef-122">Das aktuelle Microsoft 365-PAC-Skript finden Sie im [Get-Pacfile-PowerShell-Skript](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span><span class="sxs-lookup"><span data-stu-id="58aef-122">For the latest Microsoft 365 PAC script, see the [Get-Pacfile PowerShell script](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

- <span data-ttu-id="58aef-p107">Analysieren Sie Ihre Edge-Geräte, um die doppelte Verarbeitung zu bestimmen, und konfigurieren Sie sie dann zum Weiterleiten von Datenverkehr an Optimieren- und Zulassen-Endpunkte ohne Verarbeitung. Dies wird als Umgehung des Datenverkehrs bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="58aef-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 

<span data-ttu-id="58aef-125">Hier sind die Empfehlungen in Ihrer Netzwerkinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="58aef-125">Here are these recommendations in your network infrastructure.</span></span>

![Empfehlungen zur Optimierung des lokalen Datenverkehrs](../media/networking-configure-proxies-firewalls/bypassing-edge-devices.png)

<span data-ttu-id="58aef-127">Zu den Edgegeräten gehören Firewalls, SSL Break and Inspect, Paketüberprüfungsgeräte sowie Systeme zur Verhinderung von Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="58aef-127">Edge devices include firewalls, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="58aef-128">Zum Konfigurieren und Aktualisieren der Konfigurationen von Edgegeräten können Sie ein Skript oder einen REST-Aufruf verwenden, um eine strukturierte Liste der Endpunkte vom Office 365-Endpunkte-Webdienst zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="58aef-128">To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service.</span></span> <span data-ttu-id="58aef-129">Weitere Informationen finden Sie unter [Office 365-IP-Adresse und -URL-Webdienst](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span><span class="sxs-lookup"><span data-stu-id="58aef-129">For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="58aef-p109">Sie umgehen nur die normale Proxy- und Netzwerksicherheitsverarbeitung für Datenverkehr zu Microsoft 365-Endpunkten der Kategorie „Optimieren“ und „Zulassen“. Der andere allgemeine Internetdatenverkehr wird weitergeleitet und unterliegt Ihrer vorhandenen Netzwerksicherheitsverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="58aef-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="58aef-132">Als Zwischenprüfung können Sie die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step4) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="58aef-132">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="58aef-133">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="58aef-133">Next step</span></span>

|||
|:-------|:-----|
|![Schritt 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="58aef-135">Optimieren der Leistung des Clients und des Office 365-Diensts</span><span class="sxs-lookup"><span data-stu-id="58aef-135">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



