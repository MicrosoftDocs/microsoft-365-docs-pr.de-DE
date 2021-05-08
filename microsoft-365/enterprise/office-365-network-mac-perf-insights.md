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
ms.openlocfilehash: ca665f4e492b071e5a387ffde0efae8336bd96bc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245780"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="1cacf-103">Microsoft 365 Network Insights (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1cacf-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="1cacf-104">**Netzwerkeinblicke** sind Leistungsmetriken, die von Ihrem mandanten Microsoft 365 erfasst werden und nur von administrativen Benutzern in Ihrem Mandanten angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="1cacf-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="1cacf-105">Einblicke werden im Microsoft 365 Admin Center unter <https://portal.microsoft.com/adminportal/home#/networkperformance> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1cacf-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="1cacf-106">Einblicke sollen beim Entwerfen von Netzwerkperimetern für Ihre Bürostandorte helfen.</span><span class="sxs-lookup"><span data-stu-id="1cacf-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="1cacf-107">Jeder Einblick enthält Livedetails zu den Leistungsmerkmalen für ein bestimmtes häufiges Problem für jeden geografischen Standort, an dem Benutzer auf Ihren Mandanten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1cacf-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="1cacf-108">Es gibt sechs spezifische Netzwerkeinblicke, die für jeden Bürostandort angezeigt werden können:</span><span class="sxs-lookup"><span data-stu-id="1cacf-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="1cacf-109">Backhauled network egress</span><span class="sxs-lookup"><span data-stu-id="1cacf-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="1cacf-110">Netzwerkvermittlergerät</span><span class="sxs-lookup"><span data-stu-id="1cacf-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="1cacf-111">Bessere Leistung für Kunden in Ihrer Nähe erkannt</span><span class="sxs-lookup"><span data-stu-id="1cacf-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="1cacf-112">Verwenden einer nicht optimalen Exchange Online-Service-Eingangstür</span><span class="sxs-lookup"><span data-stu-id="1cacf-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="1cacf-113">Verwenden einer nicht optimalen SharePoint Onlinedienst-Eingangstür</span><span class="sxs-lookup"><span data-stu-id="1cacf-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="1cacf-114">Niedrige Downloadgeschwindigkeit SharePoint Eingangstür</span><span class="sxs-lookup"><span data-stu-id="1cacf-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="1cacf-115">Optimaler Netzwerk-Abgress für China-Benutzer</span><span class="sxs-lookup"><span data-stu-id="1cacf-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="1cacf-116">Es gibt zwei Netzwerkeinblicke auf Mandantenebene, die für den Mandanten angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="1cacf-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="1cacf-117">Diese werden auch auf den Seiten für Produktivitätsergebnis angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1cacf-117">These also appear in the productivity score pages:</span></span>

- [<span data-ttu-id="1cacf-118">Exchange verbindungen, die von Konnektivitätsproblemen betroffen sind</span><span class="sxs-lookup"><span data-stu-id="1cacf-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="1cacf-119">SharePoint von Konnektivitätsproblemen betroffener Beispielverbindungen</span><span class="sxs-lookup"><span data-stu-id="1cacf-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="1cacf-120">Netzwerkeinblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und sind nur für Microsoft 365-Mandanten verfügbar, die im Featurevorschauprogramm registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="1cacf-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="1cacf-121">Backhauled network egress</span><span class="sxs-lookup"><span data-stu-id="1cacf-121">Backhauled network egress</span></span>

<span data-ttu-id="1cacf-122">Diese Einsicht wird angezeigt, wenn der Netzwerkeinblickdienst erkennt, dass der Abstand zwischen einem bestimmten Benutzerstandort und dem Netzwerkeinsprung größer als 800 Kilometer ist, was darauf hinweist, dass Microsoft 365-Datenverkehr zu einem gängigen Internet-Edgegerät oder -proxy zurückgehauen wird.</span><span class="sxs-lookup"><span data-stu-id="1cacf-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="1cacf-123">Diese Einsicht wird in einigen Zusammenfassungsansichten Egress als "Egress" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="1cacf-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1cacf-124">![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span><span class="sxs-lookup"><span data-stu-id="1cacf-124">![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1cacf-125">Szenario</span><span class="sxs-lookup"><span data-stu-id="1cacf-125">What does this mean?</span></span>

<span data-ttu-id="1cacf-126">Dies gibt an, dass der Abstand zwischen dem Bürostandort und dem Netzwerkress mehr als 800 Kilometer beträgt.</span><span class="sxs-lookup"><span data-stu-id="1cacf-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="1cacf-127">Der Bürostandort wird durch einen verschleierten Clientcomputerspeicherort identifiziert, und der Netzwerk-Ausgangsspeicherort wird mithilfe der Reverse-IP-Adresse für Standortdatenbanken identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1cacf-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="1cacf-128">Der Bürostandort kann ungenau sein, Windows Standortdienste auf Computern deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="1cacf-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="1cacf-129">Der Standort des Netzwerk-Ausgangs kann ungenau sein, wenn die Reverse-IP-Adressdatenbankinformationen ungenau sind.</span><span class="sxs-lookup"><span data-stu-id="1cacf-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="1cacf-130">Details für diese Einblicke umfassen den Standort des Büros, den geschätzten Prozentsatz des gesamten Mandantenbenutzers am Standort, den aktuellen Standort für den Netzwerkbezug, die Relevanz des Ausgangsstandorts, den Abstand zwischen dem Standort und dem aktuellen Ausgangspunkt, das Datum, an dem die Bedingung zum ersten Mal erkannt wurde, und das Datum, an dem die Bedingung aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="1cacf-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1cacf-131">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="1cacf-131">What should I do?</span></span>

<span data-ttu-id="1cacf-132">Für diesen Einblick empfehlen wir, dass das Netzwerk näher an den Bürostandort rückt, damit die Konnektivität optimal zum globalen Netzwerk von Microsoft und zur nächsten Microsoft 365-Service-Eingangstüre geroutet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1cacf-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="1cacf-133">Die Enge des Netzwerkeinschlusses zu den Bürostandorten der Benutzer ermöglicht auch in Zukunft eine verbesserte Leistung, da Microsoft sowohl Netzwerkstandorte als auch Microsoft 365-Fronttüren erweitert.</span><span class="sxs-lookup"><span data-stu-id="1cacf-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="1cacf-134">Weitere Informationen zum Beheben dieses Problems finden Sie unter [Egress netzwerkverbindungen lokal](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="1cacf-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="1cacf-135">Netzwerkvermittlergerät</span><span class="sxs-lookup"><span data-stu-id="1cacf-135">Network intermediary device</span></span>

<span data-ttu-id="1cacf-136">Diese Einsicht wird angezeigt, wenn wir Geräte zwischen Ihren Benutzern und dem Netzwerk von Microsoft erkannt haben, die sich auf die Office 365 auswirken können.</span><span class="sxs-lookup"><span data-stu-id="1cacf-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="1cacf-137">Es wird empfohlen, diese für bestimmte Netzwerkdatenverkehr Microsoft 365, der für Microsoft-Rechenzentren bestimmt ist, zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="1cacf-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="1cacf-138">Diese Empfehlung wird zusätzlich unter Microsoft 365 [Network Connectivity Principles beschrieben.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="1cacf-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span> 

<span data-ttu-id="1cacf-139">Eine der Erkenntnisse des Netzwerkvermittlers ist die SSL-Unterbrechung und -Überprüfung, wenn kritische Office 365 Netzwerkendpunkte für Exchange, SharePoint und Teams von netzwerkvermittlern Geräten abgefangen und entschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="1cacf-139">One network intermediary insight we show is SSL break and inspection when critical Office 365 network endpoints for Exchange, SharePoint and Teams are intercepted and decrypted by network intermediary devices.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1cacf-140">Szenario</span><span class="sxs-lookup"><span data-stu-id="1cacf-140">What does this mean?</span></span>

<span data-ttu-id="1cacf-141">Netzwerkvermittlergeräte wie Proxyserver, VPNs und Verhinderung von Datenverlust können sich auf die Leistung und Stabilität Microsoft 365 Clients auswirken, auf denen Datenverkehr zwischengeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="1cacf-141">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1cacf-142">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="1cacf-142">What should I do?</span></span>

<span data-ttu-id="1cacf-143">Konfigurieren Sie das netzwerkvermittlere Gerät, das erkannt wurde, um die Verarbeitung für Microsoft 365 zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="1cacf-143">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="1cacf-144">Bessere Leistung für Kunden in Ihrer Nähe erkannt</span><span class="sxs-lookup"><span data-stu-id="1cacf-144">Better performance detected for customers near you</span></span>

<span data-ttu-id="1cacf-145">Diese Einsicht wird angezeigt, wenn der Netzwerk-Einblicke-Dienst erkennt, dass eine erhebliche Anzahl von Kunden in Ihrem U-Bahn-Bereich eine bessere Leistung als Benutzer in Ihrer Organisation an diesem Bürostandort hat.</span><span class="sxs-lookup"><span data-stu-id="1cacf-145">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="1cacf-146">Diese Einsicht wird in einigen Zusammenfassungsansichten als "Peers" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="1cacf-146">This insight is abbreviated as "Peers" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1cacf-147">![Relative Netzwerkleistung](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span><span class="sxs-lookup"><span data-stu-id="1cacf-147">![Relative network performance](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1cacf-148">Szenario</span><span class="sxs-lookup"><span data-stu-id="1cacf-148">What does this mean?</span></span>

<span data-ttu-id="1cacf-149">Dieser Einblick untersucht die Gesamtleistung Microsoft 365 Kunden in derselben Stadt wie dieser Bürostandort.</span><span class="sxs-lookup"><span data-stu-id="1cacf-149">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="1cacf-150">Diese Einsicht wird angezeigt, wenn die durchschnittliche Wartezeit Ihrer Benutzer um 10 % größer ist als die durchschnittliche Latenz der benachbarten Mandanten.</span><span class="sxs-lookup"><span data-stu-id="1cacf-150">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1cacf-151">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="1cacf-151">What should I do?</span></span>

<span data-ttu-id="1cacf-152">Es kann viele Gründe für diese Bedingung geben, z. B. Wartezeiten in Ihrem Unternehmensnetzwerk oder Internetdienstanbieter, Engpässe oder Architekturdesignprobleme.</span><span class="sxs-lookup"><span data-stu-id="1cacf-152">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="1cacf-153">Untersuchen Sie die Wartezeit zwischen jedem Hop in der Route zwischen Ihrem Büronetzwerk und dem Microsoft 365 Eingangstür.</span><span class="sxs-lookup"><span data-stu-id="1cacf-153">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="1cacf-154">Weitere Informationen finden Sie unter [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="1cacf-154">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="1cacf-155">Verwenden einer nicht optimalen Exchange Online-Service-Eingangstür</span><span class="sxs-lookup"><span data-stu-id="1cacf-155">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="1cacf-156">Diese Einsicht wird angezeigt, wenn der Netzwerk-Einblicke-Dienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit einer optimalen Exchange Online herstellen.</span><span class="sxs-lookup"><span data-stu-id="1cacf-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="1cacf-157">Diese Einsicht wird in einigen Zusammenfassungsansichten als "Routing" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="1cacf-157">This insight is abbreviated as "Routing" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1cacf-158">![Nicht optimale EXO-Fronttür](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span><span class="sxs-lookup"><span data-stu-id="1cacf-158">![Non-optimal EXO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1cacf-159">Szenario</span><span class="sxs-lookup"><span data-stu-id="1cacf-159">What does this mean?</span></span>

<span data-ttu-id="1cacf-160">Wir listet Exchange Online,die für die Verwendung aus der Bürostandortstadt mit guter Leistung geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="1cacf-160">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="1cacf-161">Wenn der aktuelle Test die Verwendung eines Exchange Online, der nicht in dieser Liste enthalten ist, wird diese Empfehlung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1cacf-161">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1cacf-162">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="1cacf-162">What should I do?</span></span>

<span data-ttu-id="1cacf-163">Die Verwendung einer nicht optimalen Exchange Online-Fronttür des Diensts kann durch netzwerk backhaul verursacht werden, bevor das Unternehmensnetzwerk abfresst. In diesem Fall wird der lokale und direkte Netzwerkeinschwung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="1cacf-163">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="1cacf-164">Dies kann auch durch die Verwendung eines Remote-DNS-Recursive Resolver-Servers verursacht werden. In diesem Fall wird empfohlen, den DNS-Rekursiven Resolver-Server am Netzwerkress auszurichten.</span><span class="sxs-lookup"><span data-stu-id="1cacf-164">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="1cacf-165">Verwenden einer nicht optimalen SharePoint Onlinedienst-Eingangstür</span><span class="sxs-lookup"><span data-stu-id="1cacf-165">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="1cacf-166">Diese Einsicht wird angezeigt, wenn der Netzwerkeinblickdienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit der SharePoint Onlinedienst-Eingangstür herstellen.</span><span class="sxs-lookup"><span data-stu-id="1cacf-166">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="1cacf-167">Diese Einsicht wird in einigen Zusammenfassungsansichten als "Afd" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="1cacf-167">This insight is abbreviated as "Afd" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1cacf-168">![Nicht optimale SPO-Eingangstür](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span><span class="sxs-lookup"><span data-stu-id="1cacf-168">![Non-optimal SPO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1cacf-169">Szenario</span><span class="sxs-lookup"><span data-stu-id="1cacf-169">What does this mean?</span></span>

<span data-ttu-id="1cacf-170">Wir identifizieren die SharePoint Onlinedienst-Eingangstür, mit der der Testclient eine Verbindung herstellen soll.</span><span class="sxs-lookup"><span data-stu-id="1cacf-170">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="1cacf-171">Anschließend vergleichen wir dies für die Bürostandortstadt mit der erwarteten SharePoint Online-Service-Eingangstür für diese Stadt.</span><span class="sxs-lookup"><span data-stu-id="1cacf-171">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="1cacf-172">Wenn sie nicht übereinstimmen, wird diese Empfehlung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="1cacf-172">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1cacf-173">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="1cacf-173">What should I do?</span></span>

<span data-ttu-id="1cacf-174">Die Verwendung einer nicht optimalen SharePoint Online-Dienst-Eingangstür könnte durch Netzwerkhull vor dem Unternehmensnetzwerkeinziehen verursacht werden. In diesem Fall wird der lokale und direkte Netzwerkeinschwung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="1cacf-174">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="1cacf-175">Dies kann auch durch die Verwendung eines Remote-DNS-Recursive Resolver-Servers verursacht werden. In diesem Fall wird empfohlen, den DNS-Rekursiven Resolver-Server am Netzwerkress auszurichten.</span><span class="sxs-lookup"><span data-stu-id="1cacf-175">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="1cacf-176">Niedrige Downloadgeschwindigkeit SharePoint Eingangstür</span><span class="sxs-lookup"><span data-stu-id="1cacf-176">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="1cacf-177">Diese Einsicht wird angezeigt, wenn der Netzwerkeinblickdienst erkennt, dass die Bandbreite zwischen dem jeweiligen Bürostandort und SharePoint Online kleiner als 1 MBps ist.</span><span class="sxs-lookup"><span data-stu-id="1cacf-177">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="1cacf-178">Diese Einsicht wird in einigen Zusammenfassungsansichten als "Durchsatz" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="1cacf-178">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1cacf-179">Szenario</span><span class="sxs-lookup"><span data-stu-id="1cacf-179">What does this mean?</span></span>

<span data-ttu-id="1cacf-180">Die Downloadgeschwindigkeit, die ein Benutzer von SharePoint Online- und OneDrive for Business-Service-Eingangstüren erhalten kann, wird in Megabyte pro Sekunde (MBps) gemessen.</span><span class="sxs-lookup"><span data-stu-id="1cacf-180">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="1cacf-181">Wenn dieser Wert kleiner als 1 MBps ist, geben wir diese Einsicht.</span><span class="sxs-lookup"><span data-stu-id="1cacf-181">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1cacf-182">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="1cacf-182">What should I do?</span></span>

<span data-ttu-id="1cacf-183">Um die Downloadgeschwindigkeit zu verbessern, muss möglicherweise die Bandbreite erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="1cacf-183">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="1cacf-184">Alternativ kann es zu Netzwerküberlastungen zwischen Denkautomaten am Bürostandort und der SharePoint Onlinedienst-Eingangstür kommen.</span><span class="sxs-lookup"><span data-stu-id="1cacf-184">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="1cacf-185">Dies wird manchmal als verlustreich bezeichnet und schränkt die Downloadgeschwindigkeit ein, die Benutzern zur Verfügung steht, auch wenn genügend Bandbreite verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1cacf-185">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="1cacf-186">Optimaler Netzwerk-Abgress für China-Benutzer</span><span class="sxs-lookup"><span data-stu-id="1cacf-186">China user optimal network egress</span></span>

<span data-ttu-id="1cacf-187">Dieser Einblick wird angezeigt, wenn Ihre Organisation Benutzer in China hat, die eine Verbindung zu Microsoft 365 an anderen geografischen Standorten herstellen.</span><span class="sxs-lookup"><span data-stu-id="1cacf-187">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="1cacf-188">Szenario</span><span class="sxs-lookup"><span data-stu-id="1cacf-188">What does this mean?</span></span>

<span data-ttu-id="1cacf-189">Wenn Ihre Organisation über private WAN-Verbindungen verfügt, wird empfohlen, eine Netzwerk-WAN-Schaltung von Ihren Bürostandorten in China aus zu konfigurieren, die an einem der folgenden Speicherorte über eine Netzwerkverbindung zum Internet verfügen:</span><span class="sxs-lookup"><span data-stu-id="1cacf-189">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="1cacf-190">Hongkong</span><span class="sxs-lookup"><span data-stu-id="1cacf-190">Hong Kong</span></span>
- <span data-ttu-id="1cacf-191">Japan</span><span class="sxs-lookup"><span data-stu-id="1cacf-191">Japan</span></span>
- <span data-ttu-id="1cacf-192">Taiwan</span><span class="sxs-lookup"><span data-stu-id="1cacf-192">Taiwan</span></span>
- <span data-ttu-id="1cacf-193">Südkorea</span><span class="sxs-lookup"><span data-stu-id="1cacf-193">South Korea</span></span>
- <span data-ttu-id="1cacf-194">Singapur</span><span class="sxs-lookup"><span data-stu-id="1cacf-194">Singapore</span></span>
- <span data-ttu-id="1cacf-195">Malaysia</span><span class="sxs-lookup"><span data-stu-id="1cacf-195">Malaysia</span></span>

<span data-ttu-id="1cacf-196">Der Internetaustritt von Benutzern als diese Standorte führt zu leistungsbehinderndern, und ein Austritt in China kann aufgrund der grenzüberschreitenden Überlastung zu hohen Wartezeiten und Konnektivitätsproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="1cacf-196">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1cacf-197">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="1cacf-197">What should I do?</span></span>

<span data-ttu-id="1cacf-198">Weitere Informationen zum Beheben von Leistungsproblemen im Zusammenhang mit dieser Einsicht finden Sie unter Microsoft 365 optimierung der globalen Mandantenleistung [für Chinesische Benutzer](microsoft-365-networking-china.md).</span><span class="sxs-lookup"><span data-stu-id="1cacf-198">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="1cacf-199">Exchange verbindungen, die von Konnektivitätsproblemen betroffen sind</span><span class="sxs-lookup"><span data-stu-id="1cacf-199">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="1cacf-200">Diese Einsicht zeigt, wann 50 % oder mehr der in der Stichprobe verwendeten Verbindungen betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="1cacf-200">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="1cacf-201">Die Auswirkung wird durch die Exchange, die für jede Stichprobe unter 60 % liegt.</span><span class="sxs-lookup"><span data-stu-id="1cacf-201">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1cacf-202">Szenario</span><span class="sxs-lookup"><span data-stu-id="1cacf-202">What does this mean?</span></span>

<span data-ttu-id="1cacf-203">Dies ist ein Hinweis darauf, dass bei der Mehrzahl der Benutzer Probleme mit der Benutzererfahrung auftreten, wenn Outlook Verbindung mit Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1cacf-203">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="1cacf-204">Der Prozentsatz der Stichproben stellt wahrscheinlich den Prozentsatz der Benutzer dar, die unter 60 Punkt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1cacf-204">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="1cacf-205">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="1cacf-205">What should I do?</span></span>

<span data-ttu-id="1cacf-206">Aktivieren Sie die Sichtbarkeit der Netzwerkkonnektivität für Office-Standorte, wenn Sie dies noch nicht getan haben.</span><span class="sxs-lookup"><span data-stu-id="1cacf-206">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="1cacf-207">Sie möchten ermitteln, welche Büros von einer schlechten Netzwerkkonnektivität betroffen sind, die sich auf Exchange auswirken, und nach Möglichkeiten suchen, um den Netzwerkperimeter zu verbessern, der die Benutzer mit dem Netzwerk von Microsoft verbindet.</span><span class="sxs-lookup"><span data-stu-id="1cacf-207">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="1cacf-208">SharePoint von Konnektivitätsproblemen betroffener Beispielverbindungen</span><span class="sxs-lookup"><span data-stu-id="1cacf-208">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="1cacf-209">Diese Einsicht zeigt, wann 50 % oder mehr der in der Stichprobe verwendeten Verbindungen betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="1cacf-209">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="1cacf-210">Die Auswirkung wird durch die SharePoint, die für jede Stichprobe unter 40 % liegt.</span><span class="sxs-lookup"><span data-stu-id="1cacf-210">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1cacf-211">Szenario</span><span class="sxs-lookup"><span data-stu-id="1cacf-211">What does this mean?</span></span>

<span data-ttu-id="1cacf-212">Dies ist ein Hinweis darauf, dass bei der Mehrzahl Ihrer Benutzer wahrscheinlich Probleme mit der Benutzererfahrung SharePoint und OneDrive.</span><span class="sxs-lookup"><span data-stu-id="1cacf-212">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="1cacf-213">Der Prozentsatz der Stichproben stellt wahrscheinlich den Prozentsatz der Benutzer dar, die unter 40 Punkt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1cacf-213">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="1cacf-214">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="1cacf-214">What should I do?</span></span>

<span data-ttu-id="1cacf-215">Aktivieren Sie die Sichtbarkeit der Netzwerkkonnektivität für Office-Standorte, wenn Sie dies noch nicht getan haben.</span><span class="sxs-lookup"><span data-stu-id="1cacf-215">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="1cacf-216">Sie möchten ermitteln, welche Büros von einer schlechten Netzwerkkonnektivität betroffen sind, die sich auf SharePoint auswirken, und nach Möglichkeiten suchen, um den Netzwerkperimeter zu verbessern, der die Benutzer mit dem Netzwerk von Microsoft verbindet.</span><span class="sxs-lookup"><span data-stu-id="1cacf-216">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1cacf-217">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1cacf-217">Related topics</span></span>

[<span data-ttu-id="1cacf-218">Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1cacf-218">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="1cacf-219">Microsoft 365 Netzwerkbewertung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1cacf-219">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="1cacf-220">Microsoft 365 Netzwerkverbindungstesttool (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1cacf-220">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="1cacf-221">Microsoft 365 Network Connectivity Location Services (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1cacf-221">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
