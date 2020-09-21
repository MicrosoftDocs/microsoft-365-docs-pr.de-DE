---
title: Microsoft 365 Network Insights (Vorschau)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
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
ms.openlocfilehash: 682c888fefb9bec9725e470d62019c857fc2de07
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171338"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="c872a-103">Microsoft 365 Network Insights (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c872a-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="c872a-104">**Netzwerk Einblicke** sind Leistungs Metriken, die von Ihrem Microsoft 365-Mandanten gesammelt werden und nur für administrative Benutzer in Ihrem Mandanten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c872a-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="c872a-105">Einblicke werden im Microsoft 365 Admin Center unter angezeigt <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="c872a-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="c872a-106">Mithilfe von Insights sollen Netzwerkperimeter für Ihre Office-Standorte entworfen werden.</span><span class="sxs-lookup"><span data-stu-id="c872a-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="c872a-107">Jede Insight enthält Live-Details zu den Leistungsmerkmalen eines bestimmten allgemeinen Problems für jeden geografischen Standort, auf den Benutzer auf ihren Mandanten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c872a-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="c872a-108">Es gibt sechs spezifische Netzwerk Einblicke, die für jeden Office-Standort angezeigt werden können:</span><span class="sxs-lookup"><span data-stu-id="c872a-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="c872a-109">Ausstieg aus dem backhauld-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="c872a-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="c872a-110">Bessere Leistung für Kunden in Ihrer Nähe erkannt</span><span class="sxs-lookup"><span data-stu-id="c872a-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="c872a-111">Verwenden eines nicht optimalen Exchange Online-Dienst-Front-Door</span><span class="sxs-lookup"><span data-stu-id="c872a-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="c872a-112">Verwenden eines nicht optimalen SharePoint Online-Dienst-Front-Door</span><span class="sxs-lookup"><span data-stu-id="c872a-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="c872a-113">Niedrige Downloadgeschwindigkeit von SharePoint-Haustür</span><span class="sxs-lookup"><span data-stu-id="c872a-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="c872a-114">China-Benutzer optimales Netzwerk Austritt</span><span class="sxs-lookup"><span data-stu-id="c872a-114">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="c872a-115">Es gibt zwei Netzwerk Einblicke auf Mandantenebene, die für den Mandanten angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="c872a-115">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="c872a-116">Diese werden auch auf den producvitivy-Ergebnisseiten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c872a-116">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="c872a-117">Auswirkungen von Verbindungsproblemen auf Exchange-Stichproben Verbindungen</span><span class="sxs-lookup"><span data-stu-id="c872a-117">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="c872a-118">Durch Verbindungsprobleme beeinträchtigte SharePoint-Stichproben Verbindungen</span><span class="sxs-lookup"><span data-stu-id="c872a-118">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="c872a-119">Netzwerk Einblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und stehen nur für Microsoft 365-Mandanten zur Verfügung, die im Feature Preview-Programm registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="c872a-119">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="c872a-120">Ausstieg aus dem backhauld-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="c872a-120">Backhauled network egress</span></span>

<span data-ttu-id="c872a-121">Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass der Abstand zwischen einem bestimmten Benutzerstandort und dem Netzwerk Ausgang größer als 500 Meilen (800 Kilometer) ist und angibt, dass der Microsoft 365-Datenverkehr zu einem gemeinsamen Internet-Edge-Gerät oder-Proxy zurückgezogen wird.</span><span class="sxs-lookup"><span data-stu-id="c872a-121">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="c872a-122">Diese Einblicke wird in einigen zusammenfassungsansichten als "Ausstieg" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="c872a-122">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Ausstieg aus dem backhauld-Netzwerk](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="c872a-124">Szenario</span><span class="sxs-lookup"><span data-stu-id="c872a-124">What does this mean?</span></span>

<span data-ttu-id="c872a-125">Dadurch wird feststellen, dass der Abstand zwischen dem Bürostandort und dem Netzwerk Ausstieg mehr als 500 Meilen (800 Kilometer) beträgt.</span><span class="sxs-lookup"><span data-stu-id="c872a-125">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="c872a-126">Der Standort des Büros wird durch einen verborgenen Clientcomputer Speicherort identifiziert, und der Netzwerk Ausgangsspeicherort wird mithilfe von Reverse IP Address to Location Databases identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c872a-126">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="c872a-127">Der Office-Standort ist möglicherweise ungenau, wenn Windows-Ortungsdienste auf Computern deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="c872a-127">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="c872a-128">Der Netzwerk Ausgangsspeicherort ist möglicherweise ungenau, wenn die Datenbankinformationen der Reverse-IP-Adresse ungenau sind.</span><span class="sxs-lookup"><span data-stu-id="c872a-128">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="c872a-129">Details für diese Einblicke sind der Office-Standort, der geschätzte Prozentsatz des Gesamt Mandanten Benutzers am Standort, der aktuelle Netzwerk Ausgangsstandort, die Relevanz des Ausgangs Standorts, der Abstand zwischen dem Standort und dem aktuellen Ausgangspunkt, das Datum, an dem die Bedingung erstmals erkannt wurde, und das Datum, an dem die Bedingung aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="c872a-129">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="c872a-130">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="c872a-130">What should I do?</span></span>

<span data-ttu-id="c872a-131">Für diese Einblicke empfehlen wir den Netzwerk Ausstieg näher am Office-Standort, damit die Konnektivität optimal zum globalen Microsoft-Netzwerk und zur nächsten Microsoft 365-Dienst Haustür weitergeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c872a-131">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="c872a-132">Das Schließen des Netzwerk Ausstiegs für Benutzer in Office-Standorten ermöglicht auch in Zukunft eine verbesserte Leistung, da Microsoft in Zukunft sowohl Netzwerk Points of Presence als auch Microsoft 365 Service-Front-Doors erweitert.</span><span class="sxs-lookup"><span data-stu-id="c872a-132">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="c872a-133">Weitere Informationen zum Beheben dieses Problems finden Sie unter Ausgangs [Netzwerkverbindungen lokal](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Netzwerk Verbindungs Prinzipien](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="c872a-133">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="c872a-134">Bessere Leistung für Kunden in Ihrer Nähe erkannt</span><span class="sxs-lookup"><span data-stu-id="c872a-134">Better performance detected for customers near you</span></span>

<span data-ttu-id="c872a-135">Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass eine beträchtliche Anzahl von Kunden in Ihrem Metro-Bereich eine bessere Leistung hat als Benutzer in Ihrer Organisation an diesem Standort.</span><span class="sxs-lookup"><span data-stu-id="c872a-135">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="c872a-136">Diese Einblicke wird in einigen zusammenfassungsansichten als "Peers" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="c872a-136">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Relative Netzwerkleistung](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="c872a-138">Szenario</span><span class="sxs-lookup"><span data-stu-id="c872a-138">What does this mean?</span></span>

<span data-ttu-id="c872a-139">In dieser Einblicke wird die Gesamtleistung von Microsoft 365-Kunden in derselben Stadt wie dieser Standort untersucht.</span><span class="sxs-lookup"><span data-stu-id="c872a-139">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="c872a-140">Diese Einblicke wird angezeigt, wenn die durchschnittliche Wartezeit Ihrer Benutzer 10% über der durchschnittlichen Wartezeit von benachbarten Mandanten liegt.</span><span class="sxs-lookup"><span data-stu-id="c872a-140">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="c872a-141">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="c872a-141">What should I do?</span></span>

<span data-ttu-id="c872a-142">Es kann viele Gründe für diese Bedingung geben, einschließlich Wartezeit in Ihrem Unternehmensnetzwerk oder ISP, Engpässe oder Architektur Designprobleme.</span><span class="sxs-lookup"><span data-stu-id="c872a-142">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="c872a-143">Überprüfen Sie die Wartezeit zwischen den einzelnen Hops in der Route zwischen Ihrem Office-Netzwerk und der aktuellen Microsoft 365-Haustür.</span><span class="sxs-lookup"><span data-stu-id="c872a-143">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="c872a-144">Weitere Informationen finden Sie unter [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="c872a-144">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="c872a-145">Verwenden eines nicht optimalen Exchange Online-Dienst-Front-Door</span><span class="sxs-lookup"><span data-stu-id="c872a-145">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="c872a-146">Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit einer optimalen Exchange Online Dienst-Haustür herstellen.</span><span class="sxs-lookup"><span data-stu-id="c872a-146">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="c872a-147">Diese Einblicke wird in einigen zusammenfassungsansichten als "Routing" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="c872a-147">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Nicht optimale Exo-Haustür](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="c872a-149">Szenario</span><span class="sxs-lookup"><span data-stu-id="c872a-149">What does this mean?</span></span>

<span data-ttu-id="c872a-150">Wir führen Exchange Online Service-Fronttüren auf, die für die Verwendung aus der Office-Standort Stadt mit guter Leistung geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="c872a-150">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="c872a-151">Wenn der aktuelle Test die Verwendung eines Exchange Online-Dienst-Front-Doors nicht in dieser Liste zeigt, wird diese Empfehlung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c872a-151">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="c872a-152">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="c872a-152">What should I do?</span></span>

<span data-ttu-id="c872a-153">Die Verwendung eines nicht optimalen Exchange Online Dienst-Front-Door könnte durch Netzwerk Backhaul vor dem Ausstieg des Unternehmensnetzwerks verursacht werden, in diesem Fall empfehlen wir den Ausstieg aus dem lokalen und direkten Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="c872a-153">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="c872a-154">Es kann auch durch die Verwendung eines Remote-DNS-rekursive Auflösungs Servers verursacht werden, in dem der Fall empfohlen wird, den DNS-rekursive Auflösungs Server mit dem Netzwerk Ausstieg auszurichten.</span><span class="sxs-lookup"><span data-stu-id="c872a-154">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="c872a-155">Verwenden eines nicht optimalen SharePoint Online-Dienst-Front-Door</span><span class="sxs-lookup"><span data-stu-id="c872a-155">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="c872a-156">Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit der nächstgelegenen SharePoint Online Dienst-Haustür herstellen.</span><span class="sxs-lookup"><span data-stu-id="c872a-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="c872a-157">Diese Einblicke wird in einigen zusammenfassungsansichten als "ausschließend" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="c872a-157">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Nicht optimale SPO-Haustür](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="c872a-159">Szenario</span><span class="sxs-lookup"><span data-stu-id="c872a-159">What does this mean?</span></span>

<span data-ttu-id="c872a-160">Wir identifizieren die SharePoint Online-Dienst-Haustür, mit der der Testclient eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="c872a-160">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="c872a-161">Für die Office-Standort Stadt vergleichen wir dies mit der erwarteten SharePoint Online-Service-Haustür für diese Stadt.</span><span class="sxs-lookup"><span data-stu-id="c872a-161">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="c872a-162">Wenn er nicht übereinstimmt, machen wir diese Empfehlung.</span><span class="sxs-lookup"><span data-stu-id="c872a-162">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="c872a-163">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="c872a-163">What should I do?</span></span>

<span data-ttu-id="c872a-164">Die Verwendung eines nicht optimalen SharePoint Online Dienst-Front-Door könnte durch Netzwerk Backhaul vor dem Ausstieg des Unternehmensnetzwerks verursacht werden, in diesem Fall empfehlen wir den Ausstieg aus dem lokalen und direkten Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="c872a-164">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="c872a-165">Es kann auch durch die Verwendung eines Remote-DNS-rekursive Auflösungs Servers verursacht werden, in dem der Fall empfohlen wird, den DNS-rekursive Auflösungs Server mit dem Netzwerk Ausstieg auszurichten.</span><span class="sxs-lookup"><span data-stu-id="c872a-165">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="c872a-166">Niedrige Downloadgeschwindigkeit von SharePoint-Haustür</span><span class="sxs-lookup"><span data-stu-id="c872a-166">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="c872a-167">Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass die Bandbreite zwischen dem jeweiligen Office-Standort und SharePoint Online kleiner als 1 Mbit/s ist.</span><span class="sxs-lookup"><span data-stu-id="c872a-167">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="c872a-168">Diese Einblicke wird in einigen zusammenfassungsansichten als "Durchsatz" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="c872a-168">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="c872a-169">Szenario</span><span class="sxs-lookup"><span data-stu-id="c872a-169">What does this mean?</span></span>

<span data-ttu-id="c872a-170">Die Downloadgeschwindigkeit, die ein Benutzer von SharePoint Online-und OneDrive für Unternehmen-Dienst-Fronttüren erhalten kann, wird in Megabytes pro Sekunde (Mbps) gemessen.</span><span class="sxs-lookup"><span data-stu-id="c872a-170">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="c872a-171">Wenn dieser Wert kleiner als 1 Mbit/s ist, stellen wir diese Einblicke bereit.</span><span class="sxs-lookup"><span data-stu-id="c872a-171">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="c872a-172">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="c872a-172">What should I do?</span></span>

<span data-ttu-id="c872a-173">Um die Downloadgeschwindigkeit zu verbessern, muss die Bandbreite möglicherweise erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="c872a-173">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="c872a-174">Alternativ kann es zu Netzwerküberlastung zwischen Benutzercomputern am Office-Standort und der Front-Door-SharePoint Online Dienst geben.</span><span class="sxs-lookup"><span data-stu-id="c872a-174">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="c872a-175">Dies wird manchmal als Überlastungs Verlust bezeichnet und schränkt die Downloadgeschwindigkeit ein, die Benutzern zur Verfügung steht, auch wenn genügend Bandbreite zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="c872a-175">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="c872a-176">China-Benutzer optimales Netzwerk Austritt</span><span class="sxs-lookup"><span data-stu-id="c872a-176">China user optimal network egress</span></span>

<span data-ttu-id="c872a-177">Diese Einblicke werden angezeigt, wenn Ihre Organisation über Benutzer in China verfügt, die sich mit Ihrem Microsoft 365-Mandanten an anderen geografischen Standorten verbinden.</span><span class="sxs-lookup"><span data-stu-id="c872a-177">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="c872a-178">Szenario</span><span class="sxs-lookup"><span data-stu-id="c872a-178">What does this mean?</span></span>

<span data-ttu-id="c872a-179">Wenn Ihre Organisation über private WAN-Konnektivität verfügt, wird empfohlen, eine Netzwerk-WAN-Schaltung von Ihren Office-Standorten in China aus zu konfigurieren, die über einen Netzwerk Austritt mit dem Internet an einem der folgenden Standorte verfügt:</span><span class="sxs-lookup"><span data-stu-id="c872a-179">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="c872a-180">Hongkong (SAR)</span><span class="sxs-lookup"><span data-stu-id="c872a-180">Hong Kong</span></span>
- <span data-ttu-id="c872a-181">Japan</span><span class="sxs-lookup"><span data-stu-id="c872a-181">Japan</span></span>
- <span data-ttu-id="c872a-182">Taiwan</span><span class="sxs-lookup"><span data-stu-id="c872a-182">Taiwan</span></span>
- <span data-ttu-id="c872a-183">Südkorea</span><span class="sxs-lookup"><span data-stu-id="c872a-183">South Korea</span></span>
- <span data-ttu-id="c872a-184">Singapur</span><span class="sxs-lookup"><span data-stu-id="c872a-184">Singapore</span></span>
- <span data-ttu-id="c872a-185">Malaysia</span><span class="sxs-lookup"><span data-stu-id="c872a-185">Malaysia</span></span>

<span data-ttu-id="c872a-186">Internet Ausstieg weiter Weg von Benutzern als diese Standorte verringern die Leistung, und der Ausstieg in China kann aufgrund von grenzüberschreitender Überlastung zu hohen Latenz-und Verbindungsproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="c872a-186">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="c872a-187">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="c872a-187">What should I do?</span></span>

<span data-ttu-id="c872a-188">Weitere Informationen zum Minimieren von Leistungsproblemen im Zusammenhang mit dieser Einblicke finden Sie unter [Office 365 Global Tenant Performance Optimization for China users](microsoft-365-networking-china.md).</span><span class="sxs-lookup"><span data-stu-id="c872a-188">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="c872a-189">Auswirkungen von Verbindungsproblemen auf Exchange-Stichproben Verbindungen</span><span class="sxs-lookup"><span data-stu-id="c872a-189">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="c872a-190">In dieser Erkenntnis wird angezeigt, wenn 50% oder mehr der Stichproben Verbindungen betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="c872a-190">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="c872a-191">Die Auswirkungen werden durch die Exchange-Bewertung für jedes Beispiel unter 60% definiert.</span><span class="sxs-lookup"><span data-stu-id="c872a-191">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="c872a-192">Szenario</span><span class="sxs-lookup"><span data-stu-id="c872a-192">What does this mean?</span></span>

<span data-ttu-id="c872a-193">Dies deutet darauf hin, dass bei der Mehrzahl Ihrer Benutzer wahrscheinlich Probleme mit der Benutzerfreundlichkeit auftreten, wenn Outlook eine Verbindung mit Exchange Online herstellt.</span><span class="sxs-lookup"><span data-stu-id="c872a-193">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="c872a-194">Der Prozentsatz der Beispiele stellt wahrscheinlich den Prozentsatz der Benutzer dar, die unter 60 Punkten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c872a-194">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="c872a-195">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="c872a-195">What should I do?</span></span>

<span data-ttu-id="c872a-196">Aktivieren Sie die Sichtbarkeit der Office-standortnetzwerk Konnektivität, falls noch nicht geschehen.</span><span class="sxs-lookup"><span data-stu-id="c872a-196">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="c872a-197">Sie möchten ermitteln, welche Büros von einer schlechten Netzwerkverbindung betroffen sind, die sich auf Exchange auswirkt, und Wege finden, um den Netzwerkperimeter bei jedem zu verbessern, der die Benutzer mit dem Netzwerk von Microsoft verbindet.</span><span class="sxs-lookup"><span data-stu-id="c872a-197">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="c872a-198">Durch Verbindungsprobleme beeinträchtigte SharePoint-Stichproben Verbindungen</span><span class="sxs-lookup"><span data-stu-id="c872a-198">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="c872a-199">In dieser Erkenntnis wird angezeigt, wenn 50% oder mehr der Stichproben Verbindungen betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="c872a-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="c872a-200">Die Auswirkungen werden durch die SharePoint-Bewertung unter 40% für jedes Beispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="c872a-200">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="c872a-201">Szenario</span><span class="sxs-lookup"><span data-stu-id="c872a-201">What does this mean?</span></span>

<span data-ttu-id="c872a-202">Dies deutet darauf hin, dass die Mehrzahl der Benutzer wahrscheinlich Probleme mit der Benutzerfreundlichkeit bei SharePoint und OneDrive auftreten.</span><span class="sxs-lookup"><span data-stu-id="c872a-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="c872a-203">Der Prozentsatz der Beispiele stellt wahrscheinlich den Prozentsatz der Benutzer dar, die unter 40 Punkten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c872a-203">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="c872a-204">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="c872a-204">What should I do?</span></span>

<span data-ttu-id="c872a-205">Aktivieren Sie die Sichtbarkeit der Office-standortnetzwerk Konnektivität, falls noch nicht geschehen.</span><span class="sxs-lookup"><span data-stu-id="c872a-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="c872a-206">Sie möchten ermitteln, welche Büros von einer schlechten Netzwerkkonnektivität betroffen sind, die sich auf SharePoint auswirkt, und Wege finden, um den Netzwerkperimeter bei jedem zu verbessern, der die Benutzer mit dem Netzwerk von Microsoft verbindet.</span><span class="sxs-lookup"><span data-stu-id="c872a-206">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c872a-207">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c872a-207">Related topics</span></span>

[<span data-ttu-id="c872a-208">Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c872a-208">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="c872a-209">Microsoft 365 Netzwerkbewertung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c872a-209">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="c872a-210">Microsoft 365 Network Connectivity Test Tool (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c872a-210">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="c872a-211">Microsoft 365 Network Connectivity Location Services (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c872a-211">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
