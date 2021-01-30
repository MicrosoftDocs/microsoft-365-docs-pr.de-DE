---
title: Microsoft 365 Network Insights (Vorschau)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Insights (Vorschau)
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055473"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="a678c-103">Microsoft 365 Network Insights (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="a678c-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="a678c-104">**Netzwerkeinblicke** sind Leistungsmetriken, die von Ihrem Microsoft 365-Mandanten erfasst werden und nur von Administratorbenutzern in Ihrem Mandanten angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="a678c-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="a678c-105">Einblicke werden im Microsoft 365 Admin Center unter <https://portal.microsoft.com/adminportal/home#/networkperformance> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a678c-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="a678c-106">Einblicke sollen beim Entwerfen von Netzwerkperimetern für Ihre Bürostandorte helfen.</span><span class="sxs-lookup"><span data-stu-id="a678c-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="a678c-107">Jeder Einblick bietet Livedetails zu den Leistungsmerkmalen für ein bestimmtes häufiges Problem für jeden geografischen Standort, an dem Benutzer auf Ihren Mandanten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a678c-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="a678c-108">Es gibt sechs spezifische Netzwerkeinblicke, die für jeden Bürostandort angezeigt werden können:</span><span class="sxs-lookup"><span data-stu-id="a678c-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="a678c-109">Backhauled network egress</span><span class="sxs-lookup"><span data-stu-id="a678c-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="a678c-110">Netzwerkvermittlergerät</span><span class="sxs-lookup"><span data-stu-id="a678c-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="a678c-111">Bessere Leistung für Kunden in Ihrer Nähe erkannt</span><span class="sxs-lookup"><span data-stu-id="a678c-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="a678c-112">Verwenden einer nicht optimalen Front-Door des Exchange Online-Diensts</span><span class="sxs-lookup"><span data-stu-id="a678c-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="a678c-113">Verwenden einer nicht optimalen SharePoint Online-Dienst-Eingangstür</span><span class="sxs-lookup"><span data-stu-id="a678c-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="a678c-114">Niedrige Downloadgeschwindigkeit von der SharePoint-Front-Door</span><span class="sxs-lookup"><span data-stu-id="a678c-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="a678c-115">Optimaler Netzwerk-Ausgangs in China</span><span class="sxs-lookup"><span data-stu-id="a678c-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="a678c-116">Es gibt zwei Netzwerkeinblicke auf Mandantenebene, die für den Mandanten angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="a678c-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="a678c-117">Diese werden auch auf den Produkvitivy-Bewertungsseiten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a678c-117">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="a678c-118">Exchange-Beispielverbindungen, die von Konnektivitätsproblemen betroffen sind</span><span class="sxs-lookup"><span data-stu-id="a678c-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="a678c-119">Von Konnektivitätsproblemen betroffene In-SharePoint-Beispielverbindungen</span><span class="sxs-lookup"><span data-stu-id="a678c-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="a678c-120">Netzwerkeinblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und sind nur für Microsoft 365-Mandanten verfügbar, die für das Featurevorschauprogramm registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="a678c-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="a678c-121">Backhauled network egress</span><span class="sxs-lookup"><span data-stu-id="a678c-121">Backhauled network egress</span></span>

<span data-ttu-id="a678c-122">Dieser Einblick wird angezeigt, wenn der Netzwerkinblickedienst erkennt, dass der Abstand zwischen einem bestimmten Benutzerstandort und dem Netzwerkeinsprung größer als 500 Meilen (800 Kilometer) ist, was bedeutet, dass microsoft 365-Datenverkehr zu einem gemeinsamen Internetedgegerät oder -proxy zurückgestürzt wird.</span><span class="sxs-lookup"><span data-stu-id="a678c-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="a678c-123">Dieser Einblick wird in einigen Zusammenfassungsansichten als "Egress" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="a678c-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="a678c-125">Szenario</span><span class="sxs-lookup"><span data-stu-id="a678c-125">What does this mean?</span></span>

<span data-ttu-id="a678c-126">Dies gibt an, dass der Abstand zwischen Bürostandort und Netzwerk aus dem Netzwerk mehr als 500 Meilen (800 Kilometer) beträgt.</span><span class="sxs-lookup"><span data-stu-id="a678c-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="a678c-127">Der Bürostandort wird durch einen verschleierten Standort des Clientcomputers identifiziert, und der Netzwerk-Ausgangsstandort wird mithilfe der umgekehrten IP-Adresse für Standortdatenbanken identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a678c-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="a678c-128">Der Bürostandort ist möglicherweise ungenau, wenn die Windows Location Services auf Computern deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="a678c-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="a678c-129">Der Netzwerk-Ausgangsspeicherort ist möglicherweise ungenau, wenn die Informationen der Reverse-IP-Adressdatenbank ungenau sind.</span><span class="sxs-lookup"><span data-stu-id="a678c-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="a678c-130">Zu den Details für diesen Einblick gehören der Bürostandort, der geschätzte Prozentsatz des gesamten Mandantenbenutzers am Standort, der aktuelle Netzwerk-Ausgangsstandort, die Relevanz des Ausgangspunkts, der Abstand zwischen dem Standort und dem aktuellen Ausgangspunkt, das Datum, an dem die Bedingung zum ersten Mal erkannt wurde, und das Datum, an dem die Bedingung aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="a678c-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a678c-131">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="a678c-131">What should I do?</span></span>

<span data-ttu-id="a678c-132">Für diesen Einblick empfehlen wir, den Netzwerkeingang näher am Bürostandort zu verwenden, damit die Konnektivität optimal zum globalen Netzwerk von Microsoft und zur nächstgelegenen Microsoft 365-Dienst-Front-Door geroutet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a678c-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="a678c-133">Ein enger Netzwerkeinschluss zu den Bürostandorten der Benutzer ermöglicht auch in Zukunft eine bessere Leistung, da Microsoft in Zukunft sowohl netzwerkstandorte als auch Microsoft 365-Dienst-Front-Doors erweitert.</span><span class="sxs-lookup"><span data-stu-id="a678c-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="a678c-134">Weitere Informationen zur Behebung dieses Problems [](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) finden Sie unter "Prinzipien von Netzwerkverbindungen in [Office 365 Network Connectivity".](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="a678c-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="a678c-135">Netzwerkvermittlergerät</span><span class="sxs-lookup"><span data-stu-id="a678c-135">Network intermediary device</span></span>

<span data-ttu-id="a678c-136">Dieser Einblick wird angezeigt, wenn wir Geräte zwischen Ihren Benutzern und dem Netzwerk von Microsoft erkannt haben, die sich auf die Office 365-Benutzeroberfläche auswirken können.</span><span class="sxs-lookup"><span data-stu-id="a678c-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="a678c-137">Es wird empfohlen, diese für bestimmten Microsoft 365-Netzwerkdatenverkehr zu umgehen, der für Microsoft-Rechenzentren bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="a678c-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="a678c-138">Diese Empfehlung wird zusätzlich in den Prinzipien der [Microsoft 365-Netzwerkkonnektivität beschrieben.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="a678c-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="a678c-139">Szenario</span><span class="sxs-lookup"><span data-stu-id="a678c-139">What does this mean?</span></span>

<span data-ttu-id="a678c-140">Zwischengeschaltete Netzwerkgeräte wie Proxyserver, VPNs und Geräte zur Verhinderung von Datenverlusten können sich auf die Leistung und Stabilität von Microsoft 365-Clients auswirken, bei denen Datenverkehr zwischengeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="a678c-140">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a678c-141">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="a678c-141">What should I do?</span></span>

<span data-ttu-id="a678c-142">Konfigurieren Sie das Netzwerkvermittlergerät, das erkannt wurde, um die Verarbeitung für Microsoft 365-Netzwerkdatenverkehr zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="a678c-142">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="a678c-143">Bessere Leistung für Kunden in Ihrer Nähe erkannt</span><span class="sxs-lookup"><span data-stu-id="a678c-143">Better performance detected for customers near you</span></span>

<span data-ttu-id="a678c-144">Dieser Einblick wird angezeigt, wenn der Netzwerkinblickedienst erkennt, dass eine erhebliche Anzahl von Kunden in Ihrer Region in Ihrer Region eine bessere Leistung hat als Benutzer in Ihrer Organisation an diesem Bürostandort.</span><span class="sxs-lookup"><span data-stu-id="a678c-144">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="a678c-145">Dieser Einblick wird in einigen Zusammenfassungsansichten als "Peers" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="a678c-145">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Relative Netzwerkleistung](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="a678c-147">Szenario</span><span class="sxs-lookup"><span data-stu-id="a678c-147">What does this mean?</span></span>

<span data-ttu-id="a678c-148">Dieser Einblick untersucht die Gesamtleistung von Microsoft 365-Kunden in derselben Stadt wie dieser Bürostandort.</span><span class="sxs-lookup"><span data-stu-id="a678c-148">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="a678c-149">Dieser Einblick wird angezeigt, wenn die durchschnittliche Wartezeit Ihrer Benutzer um 10 % über der durchschnittlichen Wartezeit benachbarter Mandanten liegt.</span><span class="sxs-lookup"><span data-stu-id="a678c-149">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a678c-150">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="a678c-150">What should I do?</span></span>

<span data-ttu-id="a678c-151">Es kann viele Gründe für diese Bedingung geben, z. B. Wartezeiten in Ihrem Unternehmensnetzwerk oder Internetdienstanbieter, Engpässe oder Architekturentwurfsprobleme.</span><span class="sxs-lookup"><span data-stu-id="a678c-151">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="a678c-152">Überprüfen Sie die Wartezeit zwischen jedem Hop in der Route zwischen Ihrem Büronetzwerk und der aktuellen Microsoft 365-Eingangstür.</span><span class="sxs-lookup"><span data-stu-id="a678c-152">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="a678c-153">Weitere Informationen finden Sie unter ["Prinzipien der Microsoft 365-Netzwerkkonnektivität".](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="a678c-153">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="a678c-154">Verwenden eines nicht optimalen Front-Door-Diensts für den Exchange Online-Dienst</span><span class="sxs-lookup"><span data-stu-id="a678c-154">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="a678c-155">Dieser Einblick wird angezeigt, wenn der Netzwerkinblickedienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit einer optimalen Front-Door des Exchange Online-Diensts herstellen.</span><span class="sxs-lookup"><span data-stu-id="a678c-155">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="a678c-156">Dieser Einblick wird in einigen Zusammenfassungsansichten als "Routing" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="a678c-156">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Nicht optimale EXO-Front-Door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="a678c-158">Szenario</span><span class="sxs-lookup"><span data-stu-id="a678c-158">What does this mean?</span></span>

<span data-ttu-id="a678c-159">Wir listen die Front-Doors des Exchange Online-Diensts auf, die sich für die Verwendung in der Stadt am Bürostandort mit guter Leistung eignen.</span><span class="sxs-lookup"><span data-stu-id="a678c-159">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="a678c-160">Wenn der aktuelle Test die Verwendung einer Front-Door eines Exchange Online-Diensts zeigt, die nicht in dieser Liste enthalten ist, wird diese Empfehlung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a678c-160">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a678c-161">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="a678c-161">What should I do?</span></span>

<span data-ttu-id="a678c-162">Die Verwendung einer nicht optimalen Front-Door des Exchange Online-Diensts kann durch eine Netzwerk-Backhaul vor dem Auskommen des Unternehmensnetzwerks verursacht werden. In diesem Fall wird ein lokaler und direkter Netzwerkein-/-abgress empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a678c-162">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="a678c-163">Es kann auch durch die Verwendung eines DNS-Rekursiven Resolver-Remoteservers verursacht werden. In diesem Fall wird empfohlen, den DNS-Rekursiven Resolverserver an den Netzwerkentress auszurichten.</span><span class="sxs-lookup"><span data-stu-id="a678c-163">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="a678c-164">Verwenden einer nicht optimalen SharePoint Online-Dienst-Eingangstür</span><span class="sxs-lookup"><span data-stu-id="a678c-164">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="a678c-165">Dieser Einblick wird angezeigt, wenn der Netzwerkinblickedienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit der nächstgelegenen SharePoint Online -Dienst-Front-Door herstellen.</span><span class="sxs-lookup"><span data-stu-id="a678c-165">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="a678c-166">Dieser Einblick wird in einigen Zusammenfassungsansichten als "Afd" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="a678c-166">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Nicht optimaler SPO-Front-Door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="a678c-168">Szenario</span><span class="sxs-lookup"><span data-stu-id="a678c-168">What does this mean?</span></span>

<span data-ttu-id="a678c-169">Wir identifizieren die Front-Door des SharePoint Online-Diensts, mit der der Testclient eine Verbindung herstellen soll.</span><span class="sxs-lookup"><span data-stu-id="a678c-169">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="a678c-170">Für die Bürostandort-Stadt vergleichen wir dies dann mit dem erwarteten SharePoint Online-Service-Eingangstor für diese Stadt.</span><span class="sxs-lookup"><span data-stu-id="a678c-170">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="a678c-171">Wenn sie nicht übereinstimmen, wird diese Empfehlung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a678c-171">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a678c-172">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="a678c-172">What should I do?</span></span>

<span data-ttu-id="a678c-173">Die Verwendung einer nicht optimalen SharePoint Online -Dienst-Front-Door kann durch eine Netzwerk-Backhaul vor dem Auskommen des Unternehmensnetzwerks verursacht werden. In diesem Fall empfehlen wir lokalen und direkten Netzwerkein- und -abgress.</span><span class="sxs-lookup"><span data-stu-id="a678c-173">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="a678c-174">Es kann auch durch die Verwendung eines DNS-Rekursiven Resolver-Remoteservers verursacht werden. In diesem Fall wird empfohlen, den DNS-Rekursiven Resolverserver an den Netzwerkentress auszurichten.</span><span class="sxs-lookup"><span data-stu-id="a678c-174">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="a678c-175">Geringe Downloadgeschwindigkeit von der SharePoint-Front-Door</span><span class="sxs-lookup"><span data-stu-id="a678c-175">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="a678c-176">Dieser Einblick wird angezeigt, wenn der Netzwerkinblickedienst erkennt, dass die Bandbreite zwischen dem bestimmten Bürostandort und SharePoint Online weniger als 1 MBps beträgt.</span><span class="sxs-lookup"><span data-stu-id="a678c-176">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="a678c-177">Dieser Einblick wird in einigen Zusammenfassungsansichten als "Durchsatz" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="a678c-177">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="a678c-178">Szenario</span><span class="sxs-lookup"><span data-stu-id="a678c-178">What does this mean?</span></span>

<span data-ttu-id="a678c-179">Die Downloadgeschwindigkeit, die ein Benutzer von SharePoint Online und OneDrive for #A0 erhalten kann, wird in Megabyte pro Sekunde (MBIT/s) gemessen.</span><span class="sxs-lookup"><span data-stu-id="a678c-179">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="a678c-180">Wenn dieser Wert kleiner als 1 MBps ist, geben wir diesen Einblick.</span><span class="sxs-lookup"><span data-stu-id="a678c-180">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a678c-181">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="a678c-181">What should I do?</span></span>

<span data-ttu-id="a678c-182">Um die Downloadgeschwindigkeit zu verbessern, muss die Bandbreite möglicherweise erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="a678c-182">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="a678c-183">Alternativ kann es zu Netzwerküberlastungen zwischen Benutzergeräten am Bürostandort und der Fronttür des SharePoint Online-Diensts kommen.</span><span class="sxs-lookup"><span data-stu-id="a678c-183">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="a678c-184">Dies wird manchmal als überlastet bezeichnet und schränkt die Downloadgeschwindigkeit ein, die Benutzern zur Verfügung steht, auch wenn ausreichend Bandbreite verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a678c-184">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="a678c-185">Optimaler Netzwerk-Ausgangs in China</span><span class="sxs-lookup"><span data-stu-id="a678c-185">China user optimal network egress</span></span>

<span data-ttu-id="a678c-186">Dieser Einblick wird angezeigt, wenn Ihre Organisation Benutzer in China hat, die sich mit Ihrem Microsoft 365-Mandanten an anderen geografischen Standorten verbinden.</span><span class="sxs-lookup"><span data-stu-id="a678c-186">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="a678c-187">Szenario</span><span class="sxs-lookup"><span data-stu-id="a678c-187">What does this mean?</span></span>

<span data-ttu-id="a678c-188">Wenn Ihre Organisation über private WAN-Verbindungen verfügt, wird empfohlen, eine Netzwerk-WAN-Leitung von Ihren Niederlassungen in China aus zu konfigurieren, die an einem der folgenden Standorte über einen Netzwerkentgang zum Internet verfügt:</span><span class="sxs-lookup"><span data-stu-id="a678c-188">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="a678c-189">Hongkong</span><span class="sxs-lookup"><span data-stu-id="a678c-189">Hong Kong</span></span>
- <span data-ttu-id="a678c-190">Japan</span><span class="sxs-lookup"><span data-stu-id="a678c-190">Japan</span></span>
- <span data-ttu-id="a678c-191">Taiwan</span><span class="sxs-lookup"><span data-stu-id="a678c-191">Taiwan</span></span>
- <span data-ttu-id="a678c-192">Südkorea</span><span class="sxs-lookup"><span data-stu-id="a678c-192">South Korea</span></span>
- <span data-ttu-id="a678c-193">Singapur</span><span class="sxs-lookup"><span data-stu-id="a678c-193">Singapore</span></span>
- <span data-ttu-id="a678c-194">Malaysia</span><span class="sxs-lookup"><span data-stu-id="a678c-194">Malaysia</span></span>

<span data-ttu-id="a678c-195">Der Internetaustritt von Benutzern als diese Standorte wird die Leistung beeinträchtigen, und ein Abgang in China kann aufgrund von überlastungsübergreifenden Verbindungen zu hohen Wartezeiten und Konnektivitätsproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="a678c-195">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a678c-196">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="a678c-196">What should I do?</span></span>

<span data-ttu-id="a678c-197">Weitere Informationen zum Beheben von Leistungsproblemen im Zusammenhang mit diesem Einblick finden Sie unter [Microsoft 365 globale](microsoft-365-networking-china.md)Mandantenleistungsoptimierung für Benutzer in China.</span><span class="sxs-lookup"><span data-stu-id="a678c-197">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="a678c-198">Exchange-Beispielverbindungen, die von Konnektivitätsproblemen betroffen sind</span><span class="sxs-lookup"><span data-stu-id="a678c-198">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="a678c-199">Dieser Einblick wird angezeigt, wenn 50 % oder mehr der in der Stichprobe verwendeten Verbindungen betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="a678c-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="a678c-200">Die Auswirkung wird durch die Exchange-Bewertung definiert, die für jede Stichprobe unter 60 % liegt.</span><span class="sxs-lookup"><span data-stu-id="a678c-200">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="a678c-201">Szenario</span><span class="sxs-lookup"><span data-stu-id="a678c-201">What does this mean?</span></span>

<span data-ttu-id="a678c-202">Dies ist ein Hinweis darauf, dass bei der Mehrzahl der Benutzer wahrscheinlich Probleme mit der Benutzererfahrung auftreten, wenn Outlook eine Verbindung mit Exchange Online herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="a678c-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="a678c-203">Der Prozentsatz der Stichproben stellt wahrscheinlich den Prozentsatz der Benutzer dar, die weniger als 60 Punkte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a678c-203">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="a678c-204">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="a678c-204">What should I do?</span></span>

<span data-ttu-id="a678c-205">Aktivieren Sie die Sichtbarkeit der Netzwerkkonnektivität des Bürostandorts, wenn Sie dies noch nicht getan haben.</span><span class="sxs-lookup"><span data-stu-id="a678c-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="a678c-206">Sie möchten ermitteln, welche Büros von einer schlechten Netzwerkkonnektivität betroffen sind, die Sich auf Exchange ausdingt, und nach Möglichkeiten suchen, den Netzwerkperimeter zu verbessern, der die Benutzer mit dem Netzwerk von Microsoft verbindet.</span><span class="sxs-lookup"><span data-stu-id="a678c-206">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="a678c-207">Von Konnektivitätsproblemen betroffene In-SharePoint-Beispielverbindungen</span><span class="sxs-lookup"><span data-stu-id="a678c-207">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="a678c-208">Dieser Einblick wird angezeigt, wenn 50 % oder mehr der in der Stichprobe verwendeten Verbindungen betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="a678c-208">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="a678c-209">Die Auswirkung wird durch die SharePoint-Bewertung definiert, die für jede Stichprobe unter 40 % liegt.</span><span class="sxs-lookup"><span data-stu-id="a678c-209">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="a678c-210">Szenario</span><span class="sxs-lookup"><span data-stu-id="a678c-210">What does this mean?</span></span>

<span data-ttu-id="a678c-211">Es ist ein Hinweis darauf, dass die Mehrzahl Ihrer Benutzer wahrscheinlich Probleme mit Der Benutzererfahrung mit SharePoint und OneDrive haben.</span><span class="sxs-lookup"><span data-stu-id="a678c-211">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="a678c-212">Der Prozentsatz der Stichproben stellt wahrscheinlich den Prozentsatz der Benutzer dar, die weniger als 40 Punkte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a678c-212">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="a678c-213">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="a678c-213">What should I do?</span></span>

<span data-ttu-id="a678c-214">Aktivieren Sie die Sichtbarkeit der Netzwerkkonnektivität des Bürostandorts, wenn Sie dies noch nicht getan haben.</span><span class="sxs-lookup"><span data-stu-id="a678c-214">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="a678c-215">Sie möchten ermitteln, welche Büros von einer schlechten Netzwerkkonnektivität betroffen sind, die Sich auf SharePoint auswirken, und nach Möglichkeiten suchen, den Netzwerkperimeter zu verbessern, der die Benutzer mit dem Netzwerk von Microsoft verbindet.</span><span class="sxs-lookup"><span data-stu-id="a678c-215">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a678c-216">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a678c-216">Related topics</span></span>

[<span data-ttu-id="a678c-217">Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="a678c-217">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="a678c-218">Microsoft 365-Netzwerkbewertung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="a678c-218">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="a678c-219">Microsoft 365-Tool zum Testen der Netzwerkkonnektivität (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="a678c-219">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="a678c-220">Microsoft 365 Network Connectivity Location Services (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="a678c-220">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
