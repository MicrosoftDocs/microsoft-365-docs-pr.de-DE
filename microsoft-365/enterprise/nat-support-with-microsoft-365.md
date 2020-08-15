---
title: NAT-Unterstützung mit Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: In diesem Artikel erfahren Sie, wie Sie die Anzahl der Clients, die pro IP-Adresse in Ihrer Organisation verwendet werden können, mithilfe von NAT annähernd annähern.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690280"
---
# <a name="nat-support-with-office-365"></a><span data-ttu-id="2dfd4-103">NAT-Unterstützung mit Office 365</span><span class="sxs-lookup"><span data-stu-id="2dfd4-103">NAT support with Office 365</span></span>

<span data-ttu-id="2dfd4-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2dfd4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2dfd4-105">Früher wurde vorgeschlagen, dass die maximale Anzahl von Exchange-Clients, die Sie pro IP-Adresse verwenden sollten, zum Herstellen einer Verbindung mit Office 365 etwa 2.000 Clients pro Netzwerkport war.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-105">Previously, guidance suggested that the maximum number of Exchange clients you should use per IP address to connect to Office 365 was about 2,000 clients per network port.</span></span>
  
## <a name="why-use-nat"></a><span data-ttu-id="2dfd4-106">Gründe für die Verwendung von NAT</span><span class="sxs-lookup"><span data-stu-id="2dfd4-106">Why use NAT?</span></span>

<span data-ttu-id="2dfd4-107">Durch die Verwendung von NAT können Tausende von Personen in einem Unternehmensnetzwerk einige öffentlich routingfähige IP-Adressen "freigeben".</span><span class="sxs-lookup"><span data-stu-id="2dfd4-107">By using NAT, thousands of people on a corporate network can "share" a few publicly routable IP addresses.</span></span>
  
<span data-ttu-id="2dfd4-108">Die meisten Unternehmensnetzwerke verwenden privaten (RFC1918)-IP-Adressraum.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-108">Most corporate networks use private (RFC1918) IP address space.</span></span> <span data-ttu-id="2dfd4-109">Privater Adressraum wird von der IANA (Internet Assigned Numbers Authority) zugewiesen und ausschließlich für Netzwerke bestimmt, die nicht direkt ins und aus dem globalen Internet weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-109">Private address space is allocated by the Internet Assigned Numbers Authority (IANA) and intended solely for networks that do not route directly to and from the global Internet.</span></span>
  
<span data-ttu-id="2dfd4-110">Um Internet Zugriff auf Geräte in einem privaten IP-Adressraum bereitzustellen, verwenden Organisationen Gateway-Technologien wie Firewalls und Proxys, die Netzwerkadressübersetzung (NAT) oder Pat-Dienste (Port Address Translation) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-110">To provide Internet access to devices on a private IP address space, organizations use gateway technologies like firewalls and proxies that provide network address translation (NAT) or port address translation (PAT) services.</span></span> <span data-ttu-id="2dfd4-111">Diese Gateways führen dazu, dass der Datenverkehr von internen Geräten zum Internet (einschließlich Office 365) von einer oder mehreren öffentlich routingfähigen IP-Adressen stammt.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-111">These gateways make traffic from internal devices to the Internet (including Office 365) appear to be coming from one or more publicly routable IP addresses.</span></span> <span data-ttu-id="2dfd4-112">Jede ausgehende Verbindung von einem internen Gerät wird in einen anderen Quell-TCP-Port für die öffentliche IP-Adresse übersetzt.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-112">Each outbound connection from an internal device translates to a different source TCP port on the public IP address.</span></span> 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a><span data-ttu-id="2dfd4-113">Warum müssen so viele Verbindungen für Office 365 gleichzeitig geöffnet sein?</span><span class="sxs-lookup"><span data-stu-id="2dfd4-113">Why do you need to have so many connections open to Office 365 at the same time?</span></span>

<span data-ttu-id="2dfd4-114">Outlook kann acht oder mehr Verbindungen öffnen (in Situationen, in denen Add-Ins, freigegebene Kalender, Postfächer usw. vorhanden sind).</span><span class="sxs-lookup"><span data-stu-id="2dfd4-114">Outlook may open eight or more connections (in situations where there are add-ins, shared calendars, mailboxes, etc.).</span></span> <span data-ttu-id="2dfd4-115">Da auf einem Windows-basierten NAT-Gerät maximal 64.000 Ports verfügbar sind, können maximal 8.000 Benutzer hinter einer IP-Adresse stehen, bevor die Ports erschöpft sind.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-115">Because there are a maximum of 64,000 ports available on a Windows-based NAT device, there can be a maximum of 8,000 users behind an IP address before the ports are exhausted.</span></span> <span data-ttu-id="2dfd4-116">Beachten Sie, dass die verfügbaren Ports je nachdem, welche NAT-Geräte oder-Software verwendet wird, wenn Kunden nicht-Windows-Betriebssystembasierte Geräte für NAT verwenden.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-116">Note that if customers are using non-Windows OS-based devices for NAT, the total available ports are dependent on what NAT device or software is being used.</span></span> <span data-ttu-id="2dfd4-117">In diesem Szenario kann die maximale Anzahl von Ports kleiner als 64.000 sein.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-117">In this scenario, the maximum number of ports could be less than 64,000.</span></span> <span data-ttu-id="2dfd4-118">Die Verfügbarkeit von Ports ist auch von anderen Faktoren betroffen, beispielsweise von Windows, die 4.000-Ports für die eigene Verwendung einschränken, wodurch die Gesamtzahl der verfügbaren Ports auf 60.000 reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-118">Availability of ports is also affected by other factors such as Windows restricting 4,000 ports for its own use, which reduces the total number of available ports to 60,000.</span></span> <span data-ttu-id="2dfd4-119">Es gibt möglicherweise andere Anwendungen wie Internet Explorer, die gleichzeitig eine Verbindung herstellen können und zusätzliche Ports erfordern.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-119">There may be other applications, such as Internet Explorer, that could connect at the same time, requiring additional ports.</span></span>
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a><span data-ttu-id="2dfd4-120">Berechnen der maximal unterstützten Geräte hinter einer einzelnen öffentlichen IP-Adresse mit Office 365</span><span class="sxs-lookup"><span data-stu-id="2dfd4-120">Calculating maximum supported devices behind a single public IP address with Office 365</span></span>

<span data-ttu-id="2dfd4-121">Um die maximale Anzahl von Geräten hinter einer einzelnen öffentlichen IP-Adresse zu ermitteln, sollten Sie den Netzwerkdatenverkehr überwachen, um den maximalen Port Verbrauch pro Client zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-121">To determine the maximum number of devices behind a single public IP address, you should monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="2dfd4-122">Außerdem sollte ein Spitzen Faktor für die Port Nutzung (mindestens 4) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-122">Also, a peak factor should be used for the port usage (minimum 4).</span></span> 
  
 <span data-ttu-id="2dfd4-123">**Verwenden Sie die folgende Formel, um die Anzahl unterstützter Geräte pro IP-Adresse zu berechnen:**</span><span class="sxs-lookup"><span data-stu-id="2dfd4-123">**Use the following formula to calculate the number of supported devices per IP address:**</span></span>
  
<span data-ttu-id="2dfd4-124">Maximal unterstützte Geräte hinter einer einzelnen öffentlichen IP-Adresse = (64.000-eingeschränkte Ports)/(Spitzen Port Verbrauch + Spitzen Faktor)</span><span class="sxs-lookup"><span data-stu-id="2dfd4-124">Maximum supported devices behind a single public IP address = (64,000 - restricted ports)/(Peak port consumption + peak factor)</span></span>
  
 <span data-ttu-id="2dfd4-125">**Wenn beispielsweise Folgendes zutrifft:**</span><span class="sxs-lookup"><span data-stu-id="2dfd4-125">**For example, if the following were true:**</span></span>
  
- <span data-ttu-id="2dfd4-126">**Eingeschränkte Ports:** 4.000 für das Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="2dfd4-126">**Restricted ports:** 4,000 for the operating system</span></span>

- <span data-ttu-id="2dfd4-127">**Maximaler Port Verbrauch:** 6 pro Gerät</span><span class="sxs-lookup"><span data-stu-id="2dfd4-127">**Peak port consumption:** 6 per device</span></span>

- <span data-ttu-id="2dfd4-128">**Spitzen Faktor:** 4</span><span class="sxs-lookup"><span data-stu-id="2dfd4-128">**Peak factor:** 4</span></span>

<span data-ttu-id="2dfd4-129">Anschließend werden die maximal unterstützten Geräte hinter einer einzelnen öffentlichen IP-Adresse = (64.000-4000)/(6 + 4) = 6.000</span><span class="sxs-lookup"><span data-stu-id="2dfd4-129">Then, the maximum supported devices behind a single public IP address = (64,000 - 4,000)/(6 + 4) = 6,000</span></span>
  
<span data-ttu-id="2dfd4-130">Mit der Veröffentlichung von Office 365 Hosting Pack, das in den Updates vom September 2011 für Microsoft Office Outlook 2007 oder November 2011 für Microsoft Outlook 2010 oder ein höheres Update enthalten ist, kann die Anzahl der Verbindungen von Outlook (beide Office Outlook 2007 mit Service Pack 2 und Outlook 2010) so gering wie 2 sein.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-130">With the release of Office 365 hosting pack, included in the updates from September 2011 for Microsoft Office Outlook 2007, or November 2011 for Microsoft Outlook 2010, or a later update, the number of connections from Outlook (both Office Outlook 2007 with Service Pack 2 and Outlook 2010) to Exchange can be as few as 2.</span></span> <span data-ttu-id="2dfd4-131">Sie müssen die unterschiedlichen Betriebssysteme, Benutzerverhalten usw. berücksichtigen, um die Mindest-und Höchstzahl der Ports zu ermitteln, die für Ihr Netzwerk am Höhepunkt benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-131">You'll need to factor in the different operating systems, user behaviors, and so on to determine the minimum and maximum number of ports that your network will require at peak.</span></span>
  
<span data-ttu-id="2dfd4-132">Wenn Sie weitere Geräte hinter einer einzelnen öffentlichen IP-Adresse unterstützen möchten, führen Sie die folgenden Schritte aus, um die maximale Anzahl von Geräten zu bewerten, die unterstützt werden können:</span><span class="sxs-lookup"><span data-stu-id="2dfd4-132">If you want to support more devices behind a single public IP address, follow the steps outlined to assess the maximum number of devices that can be supported:</span></span>
  
<span data-ttu-id="2dfd4-133">Überwachen Sie den Netzwerkdatenverkehr, um den maximalen Port Verbrauch pro Client zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-133">Monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="2dfd4-134">Sie sollten diese Daten sammeln:</span><span class="sxs-lookup"><span data-stu-id="2dfd4-134">You should collect this data:</span></span>
  
- <span data-ttu-id="2dfd4-135">Von mehreren Standorten</span><span class="sxs-lookup"><span data-stu-id="2dfd4-135">From multiple locations</span></span>
    
- <span data-ttu-id="2dfd4-136">Von mehreren Geräten</span><span class="sxs-lookup"><span data-stu-id="2dfd4-136">From multiple devices</span></span>
    
- <span data-ttu-id="2dfd4-137">Mehrmals</span><span class="sxs-lookup"><span data-stu-id="2dfd4-137">At multiple times</span></span>
    
<span data-ttu-id="2dfd4-138">Verwenden Sie die obige Formel, um die maximalen Benutzer pro IP-Adresse zu berechnen, die in Ihrer Umgebung unterstützt werden können.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-138">Use the preceding formula to calculate the maximum users per IP address that can be supported in their environment.</span></span>
  
<span data-ttu-id="2dfd4-139">Es gibt verschiedene Methoden für die Verteilung der Clientlast auf zusätzliche öffentliche IP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-139">There are various methods for distributing client load across additional public IP addresses.</span></span> <span data-ttu-id="2dfd4-140">Verfügbare Strategien hängen von den Funktionen der Unternehmens Gateway-Lösung ab.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-140">Strategies available depend on the capabilities of the corporate gateway solution.</span></span> <span data-ttu-id="2dfd4-141">Die einfachste Lösung besteht darin, den Benutzeradressraum zu segmentieren und jedem Gateway statisch eine Reihe von IP-Adressen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-141">The simplest solution is to segment your user address space and statically "assign" a number of IP addresses to each gateway.</span></span> <span data-ttu-id="2dfd4-142">Eine andere Alternative, die viele Gateway-Geräte bieten, ist die Möglichkeit, einen Pool von IP-Adressen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-142">Another alternative that many gateway devices offer is the ability to use a pool of IP addresses.</span></span> <span data-ttu-id="2dfd4-143">Der Vorteil des Adresspools liegt darin, dass er viel dynamischer ist und bei steigender Benutzerbasis weniger wahrscheinlich Anpassungen erfordert.</span><span class="sxs-lookup"><span data-stu-id="2dfd4-143">The benefit of the address pool is that it is much more dynamic and less likely to require adjustment as your user base grows.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2dfd4-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2dfd4-144">See also</span></span>

[<span data-ttu-id="2dfd4-145">Verwalten von Office 365-Endpunkten</span><span class="sxs-lookup"><span data-stu-id="2dfd4-145">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[<span data-ttu-id="2dfd4-146">Häufig gestellte Fragen zu Office 365-Endpunkten</span><span class="sxs-lookup"><span data-stu-id="2dfd4-146">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
