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
description: Dieser Artikel enthält Details zur Ungefährung der Anzahl der Clients, die Sie pro IP-Adresse in Ihrer Organisation mithilfe von NAT verwenden können.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690280"
---
# <a name="nat-support-with-office-365"></a><span data-ttu-id="1a660-103">NAT-Unterstützung mit Office 365</span><span class="sxs-lookup"><span data-stu-id="1a660-103">NAT support with Office 365</span></span>

<span data-ttu-id="1a660-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1a660-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1a660-105">Zuvor wurde empfohlen, dass die maximale Anzahl von Exchange Clients, die Sie pro IP-Adresse verwenden sollten, um eine Verbindung mit Office 365 herzustellen, ca. 2.000 Clients pro Netzwerkport war.</span><span class="sxs-lookup"><span data-stu-id="1a660-105">Previously, guidance suggested that the maximum number of Exchange clients you should use per IP address to connect to Office 365 was about 2,000 clients per network port.</span></span>
  
## <a name="why-use-nat"></a><span data-ttu-id="1a660-106">Warum NAT verwenden?</span><span class="sxs-lookup"><span data-stu-id="1a660-106">Why use NAT?</span></span>

<span data-ttu-id="1a660-107">Mithilfe von NAT können Tausende von Personen in einem Unternehmensnetzwerk einige öffentlich routingfähige IP-Adressen "freigeben".</span><span class="sxs-lookup"><span data-stu-id="1a660-107">By using NAT, thousands of people on a corporate network can "share" a few publicly routable IP addresses.</span></span>
  
<span data-ttu-id="1a660-108">Die meisten Unternehmensnetzwerke verwenden privaten (RFC1918)-IP-Adressraum.</span><span class="sxs-lookup"><span data-stu-id="1a660-108">Most corporate networks use private (RFC1918) IP address space.</span></span> <span data-ttu-id="1a660-109">Der private Adressraum wird von der IANA (Internet Assigned Numbers Authority) zugewiesen und ist ausschließlich für Netzwerke vorgesehen, die nicht direkt zum und vom globalen Internet geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="1a660-109">Private address space is allocated by the Internet Assigned Numbers Authority (IANA) and intended solely for networks that do not route directly to and from the global Internet.</span></span>
  
<span data-ttu-id="1a660-110">Um Den Internetzugriff auf Geräte in einem privaten IP-Adressraum zu ermöglichen, verwenden Organisationen Gatewaytechnologien wie Firewalls und Proxys, die Netzwerkadressenübersetzungsdienste (Network Address Translation, NAT) oder Portadressenübersetzungsdienste (Port Address Translation, PAT) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1a660-110">To provide Internet access to devices on a private IP address space, organizations use gateway technologies like firewalls and proxies that provide network address translation (NAT) or port address translation (PAT) services.</span></span> <span data-ttu-id="1a660-111">Diese Gateways sorgen dafür, dass Datenverkehr von internen Geräten zum Internet (einschließlich Office 365) von einer oder mehreren öffentlich routingbaren IP-Adressen kommt.</span><span class="sxs-lookup"><span data-stu-id="1a660-111">These gateways make traffic from internal devices to the Internet (including Office 365) appear to be coming from one or more publicly routable IP addresses.</span></span> <span data-ttu-id="1a660-112">Jede ausgehende Verbindung von einem internen Gerät wird in einen anderen Quell-TCP-Port für die öffentliche IP-Adresse übersetzt.</span><span class="sxs-lookup"><span data-stu-id="1a660-112">Each outbound connection from an internal device translates to a different source TCP port on the public IP address.</span></span> 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a><span data-ttu-id="1a660-113">Warum müssen so viele Verbindungen gleichzeitig für Office 365 geöffnet sein?</span><span class="sxs-lookup"><span data-stu-id="1a660-113">Why do you need to have so many connections open to Office 365 at the same time?</span></span>

<span data-ttu-id="1a660-114">Outlook können acht oder mehr Verbindungen öffnen (in Situationen, in denen Add-Ins, freigegebene Kalender, Postfächer usw. enthalten sind).</span><span class="sxs-lookup"><span data-stu-id="1a660-114">Outlook may open eight or more connections (in situations where there are add-ins, shared calendars, mailboxes, etc.).</span></span> <span data-ttu-id="1a660-115">Da auf einem Windows-basierten NAT-Gerät maximal 64.000 Ports verfügbar sind, können maximal 8.000 Benutzer hinter einer IP-Adresse stehen, bevor die Ports ausgeschöpft sind.</span><span class="sxs-lookup"><span data-stu-id="1a660-115">Because there are a maximum of 64,000 ports available on a Windows-based NAT device, there can be a maximum of 8,000 users behind an IP address before the ports are exhausted.</span></span> <span data-ttu-id="1a660-116">Beachten Sie, dass, wenn Kunden nicht Windows betriebssystembasierte Geräte für NAT verwenden, die insgesamt verfügbaren Ports davon abhängen, welches NAT-Gerät oder welche Software verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1a660-116">Note that if customers are using non-Windows OS-based devices for NAT, the total available ports are dependent on what NAT device or software is being used.</span></span> <span data-ttu-id="1a660-117">In diesem Szenario kann die maximale Anzahl von Ports unter 64.000 sein.</span><span class="sxs-lookup"><span data-stu-id="1a660-117">In this scenario, the maximum number of ports could be less than 64,000.</span></span> <span data-ttu-id="1a660-118">Die Verfügbarkeit von Ports wird auch durch andere Faktoren beeinflusst, z. B. Windows die Beschränkung von 4.000 Ports für die eigene Verwendung, wodurch die Gesamtzahl der verfügbaren Ports auf 60.000 reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="1a660-118">Availability of ports is also affected by other factors such as Windows restricting 4,000 ports for its own use, which reduces the total number of available ports to 60,000.</span></span> <span data-ttu-id="1a660-119">Möglicherweise gibt es andere Anwendungen, z. B. Internet Explorer, die gleichzeitig eine Verbindung herstellen können, was zusätzliche Ports erfordert.</span><span class="sxs-lookup"><span data-stu-id="1a660-119">There may be other applications, such as Internet Explorer, that could connect at the same time, requiring additional ports.</span></span>
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a><span data-ttu-id="1a660-120">Berechnen der maximal unterstützten Geräte hinter einer einzelnen öffentlichen IP-Adresse mit Office 365</span><span class="sxs-lookup"><span data-stu-id="1a660-120">Calculating maximum supported devices behind a single public IP address with Office 365</span></span>

<span data-ttu-id="1a660-121">Um die maximale Anzahl von Geräten hinter einer einzelnen öffentlichen IP-Adresse zu ermitteln, sollten Sie den Netzwerkdatenverkehr überwachen, um den Spitzenportverbrauch pro Client zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="1a660-121">To determine the maximum number of devices behind a single public IP address, you should monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="1a660-122">Außerdem sollte ein Spitzenfaktor für die Portnutzung (mindestens 4) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a660-122">Also, a peak factor should be used for the port usage (minimum 4).</span></span> 
  
 <span data-ttu-id="1a660-123">**Verwenden Sie die folgende Formel, um die Anzahl der unterstützten Geräte pro IP-Adresse zu berechnen:**</span><span class="sxs-lookup"><span data-stu-id="1a660-123">**Use the following formula to calculate the number of supported devices per IP address:**</span></span>
  
<span data-ttu-id="1a660-124">Maximal unterstützte Geräte hinter einer einzelnen öffentlichen IP-Adresse = (64.000 - eingeschränkte Ports)/(Spitzenportverbrauch + Spitzenfaktor)</span><span class="sxs-lookup"><span data-stu-id="1a660-124">Maximum supported devices behind a single public IP address = (64,000 - restricted ports)/(Peak port consumption + peak factor)</span></span>
  
 <span data-ttu-id="1a660-125">**Wenn beispielsweise Folgendes zutrifft:**</span><span class="sxs-lookup"><span data-stu-id="1a660-125">**For example, if the following were true:**</span></span>
  
- <span data-ttu-id="1a660-126">**Eingeschränkte Ports:** 4.000 für das Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="1a660-126">**Restricted ports:** 4,000 for the operating system</span></span>

- <span data-ttu-id="1a660-127">**Spitzenportverbrauch:** 6 pro Gerät</span><span class="sxs-lookup"><span data-stu-id="1a660-127">**Peak port consumption:** 6 per device</span></span>

- <span data-ttu-id="1a660-128">**Spitzenfaktor:** 4</span><span class="sxs-lookup"><span data-stu-id="1a660-128">**Peak factor:** 4</span></span>

<span data-ttu-id="1a660-129">Dann werden die maximal unterstützten Geräte hinter einer einzelnen öffentlichen IP-Adresse = (64.000 - 4.000)/(6 + 4) = 6.000</span><span class="sxs-lookup"><span data-stu-id="1a660-129">Then, the maximum supported devices behind a single public IP address = (64,000 - 4,000)/(6 + 4) = 6,000</span></span>
  
<span data-ttu-id="1a660-130">Mit der Veröffentlichung von Office 365 Hosting Pack, die in den Updates von September 2011 für Microsoft Office Outlook 2007 oder November 2011 für Microsoft Outlook 2010 oder einem späteren Update enthalten ist, kann die Anzahl der Verbindungen von Outlook (beide Office Outlook 2007 mit Service Pack 2 und Outlook 2010) bis Exchange bis zu 2 sein.</span><span class="sxs-lookup"><span data-stu-id="1a660-130">With the release of Office 365 hosting pack, included in the updates from September 2011 for Microsoft Office Outlook 2007, or November 2011 for Microsoft Outlook 2010, or a later update, the number of connections from Outlook (both Office Outlook 2007 with Service Pack 2 and Outlook 2010) to Exchange can be as few as 2.</span></span> <span data-ttu-id="1a660-131">Sie müssen die verschiedenen Betriebssysteme, Benutzerverhaltensmuster und so weiter einbezahlen, um die minimale und maximale Anzahl von Ports zu ermitteln, die Ihr Netzwerk in Spitzenzeiten benötigt.</span><span class="sxs-lookup"><span data-stu-id="1a660-131">You'll need to factor in the different operating systems, user behaviors, and so on to determine the minimum and maximum number of ports that your network will require at peak.</span></span>
  
<span data-ttu-id="1a660-132">Wenn Sie mehr Geräte hinter einer einzelnen öffentlichen IP-Adresse unterstützen möchten, führen Sie die beschriebenen Schritte aus, um die maximale Anzahl unterstützter Geräte zu bewerten:</span><span class="sxs-lookup"><span data-stu-id="1a660-132">If you want to support more devices behind a single public IP address, follow the steps outlined to assess the maximum number of devices that can be supported:</span></span>
  
<span data-ttu-id="1a660-133">Überwachen Sie den Netzwerkdatenverkehr, um den Spitzenportverbrauch pro Client zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="1a660-133">Monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="1a660-134">Sie sollten diese Daten sammeln:</span><span class="sxs-lookup"><span data-stu-id="1a660-134">You should collect this data:</span></span>
  
- <span data-ttu-id="1a660-135">Von mehreren Standorten</span><span class="sxs-lookup"><span data-stu-id="1a660-135">From multiple locations</span></span>
    
- <span data-ttu-id="1a660-136">Von mehreren Geräten</span><span class="sxs-lookup"><span data-stu-id="1a660-136">From multiple devices</span></span>
    
- <span data-ttu-id="1a660-137">Mehrmals</span><span class="sxs-lookup"><span data-stu-id="1a660-137">At multiple times</span></span>
    
<span data-ttu-id="1a660-138">Verwenden Sie die vorstehende Formel, um die maximalen Benutzer pro IP-Adresse zu berechnen, die in ihrer Umgebung unterstützt werden können.</span><span class="sxs-lookup"><span data-stu-id="1a660-138">Use the preceding formula to calculate the maximum users per IP address that can be supported in their environment.</span></span>
  
<span data-ttu-id="1a660-139">Es gibt verschiedene Methoden zum Verteilen der Clientlast über zusätzliche öffentliche IP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="1a660-139">There are various methods for distributing client load across additional public IP addresses.</span></span> <span data-ttu-id="1a660-140">Verfügbare Strategien hängen von den Funktionen der Unternehmensgatewaylösung ab.</span><span class="sxs-lookup"><span data-stu-id="1a660-140">Strategies available depend on the capabilities of the corporate gateway solution.</span></span> <span data-ttu-id="1a660-141">Die einfachste Lösung besteht in der Segmentierung des Benutzeradressenraums und dem statischen "Zuweisen" einer Reihe von IP-Adressen zu jedem Gateway.</span><span class="sxs-lookup"><span data-stu-id="1a660-141">The simplest solution is to segment your user address space and statically "assign" a number of IP addresses to each gateway.</span></span> <span data-ttu-id="1a660-142">Eine weitere Alternative, die viele Gatewaygeräte bieten, ist die Möglichkeit, einen Pool mit IP-Adressen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a660-142">Another alternative that many gateway devices offer is the ability to use a pool of IP addresses.</span></span> <span data-ttu-id="1a660-143">Der Vorteil des Adresspools ist, dass er wesentlich dynamischer ist und weniger Wahrscheinlichkeit eine Anpassung erfordert, wenn Ihre Benutzerbasis wächst.</span><span class="sxs-lookup"><span data-stu-id="1a660-143">The benefit of the address pool is that it is much more dynamic and less likely to require adjustment as your user base grows.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1a660-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a660-144">See also</span></span>

[<span data-ttu-id="1a660-145">Verwalten von Office 365-Endpunkten</span><span class="sxs-lookup"><span data-stu-id="1a660-145">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[<span data-ttu-id="1a660-146">Häufig gestellte Fragen zu Office 365-Endpunkten</span><span class="sxs-lookup"><span data-stu-id="1a660-146">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
