---
title: Neuerungen in Microsoft 365 Defender
description: Listet die neuen Features und Funktionen in Microsoft 365 Defender auf.
keywords: Neuerungen in Microsoft Threat Protection, GA, allgemein verfügbar, Funktionen, verfügbar, neu
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 5214f7c399ab511ec16231e4dda97a2c33b37668
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844704"
---
# <a name="whats-new-in-microsoft-365-defender"></a><span data-ttu-id="9b622-104">Neuerungen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b622-104">What's new in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9b622-105">Die folgenden Features sind allgemein verfügbar (GA) in der neuesten Version von Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9b622-105">The following features are generally available (GA) in the latest release of Microsoft 365 Defender.</span></span>

<span data-ttu-id="9b622-106">RSS-Feed: erhalten Sie benachrichtigt, wenn diese Seite aktualisiert wird, indem Sie die folgende URL in Ihren Feed-Reader kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="9b622-106">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="september-2020"></a><span data-ttu-id="9b622-107">September 2020</span><span class="sxs-lookup"><span data-stu-id="9b622-107">September 2020</span></span>
- [<span data-ttu-id="9b622-108">IdentityDirectoryEvents-Tabelle</span><span class="sxs-lookup"><span data-stu-id="9b622-108">IdentityDirectoryEvents table</span></span>](advanced-hunting-identitydirectoryevents-table.md) <br> <span data-ttu-id="9b622-109">Suchen Sie nach Ereignissen, die einen lokalen Domänencontroller mit Active Directory (AD) umfassen.</span><span class="sxs-lookup"><span data-stu-id="9b622-109">Find events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="9b622-110">Diese [Erweiterte Jagd](advanced-hunting-overview.md) Schematabelle umfasst eine Reihe von identitätsbezogenen Ereignissen und Systemereignissen auf dem Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="9b622-110">This [advanced hunting](advanced-hunting-overview.md) schema table covers a range of identity-related events and system events on the domain controller.</span></span>
- [<span data-ttu-id="9b622-111">AssignedIPAddresses ()-Funktion</span><span class="sxs-lookup"><span data-stu-id="9b622-111">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="9b622-112">Verwenden Sie diese Funktion in ihren erweiterten Suchabfragen, um schnell die neuesten IP-Adressen zu erhalten, die einem Gerät zugewiesen sind, oder die aktuellen IP-Adressen aus einer bestimmten Zeit.</span><span class="sxs-lookup"><span data-stu-id="9b622-112">Use this function in your advanced hunting queries to quickly obtain the latest IP addresses assigned to a device or the most recent IP addresses from a specific time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="9b622-113">Juli 2020</span><span class="sxs-lookup"><span data-stu-id="9b622-113">July 2020</span></span>
- [<span data-ttu-id="9b622-114">Fileprofile ()-Funktion</span><span class="sxs-lookup"><span data-stu-id="9b622-114">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="9b622-115">Verwenden Sie diese Funktion in ihren erweiterten Jagd Abfragen, um Ergebnisse mit umfassenden Dateiinformationen zu bereichern.</span><span class="sxs-lookup"><span data-stu-id="9b622-115">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="9b622-116">Identitäts-und App-Tabellen</span><span class="sxs-lookup"><span data-stu-id="9b622-116">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="9b622-117">Erhalten Sie Einblick in Authentifizierungsereignisse, Active Directory Abfragen und App-bezogene Aktivitäten mit den Tabellen [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)und [AppFileEvents](advanced-hunting-appfileevents-table.md) im erweiterten Jagd Schema.</span><span class="sxs-lookup"><span data-stu-id="9b622-117">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="9b622-118">Suche starten</span><span class="sxs-lookup"><span data-stu-id="9b622-118">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="9b622-119">Schnelles pivotieren von der Untersuchung eines Vorfalls bis hin zur Prüfung eines bestimmten Ereignisses, eines Benutzers, eines Geräts oder anderer Entitätstypen auf Erweiterter Suche.</span><span class="sxs-lookup"><span data-stu-id="9b622-119">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types on advanced hunting.</span></span>

## <a name="june-2020"></a><span data-ttu-id="9b622-120">Juni 2020</span><span class="sxs-lookup"><span data-stu-id="9b622-120">June 2020</span></span>
- <span data-ttu-id="9b622-121">Twitter-Feed</span><span class="sxs-lookup"><span data-stu-id="9b622-121">Twitter feed</span></span> <br> <span data-ttu-id="9b622-122">Holen Sie sich die neuesten Sicherheitsforschung, Threat Intelligence, Produktneuigkeiten und vieles mehr-direkt im Dashboard.</span><span class="sxs-lookup"><span data-stu-id="9b622-122">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="9b622-123">EmailPostDeliveryEvents-Schematabelle</span><span class="sxs-lookup"><span data-stu-id="9b622-123">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="9b622-124">Integrieren Sie Informationen zu Post Zustellungs Aktionen, die in e-Mail-Nachrichten in ihren erweiterten Jagd Abfragen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9b622-124">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="9b622-125">Untersuchen von Datensätzen in Advanced Hunting</span><span class="sxs-lookup"><span data-stu-id="9b622-125">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="9b622-126">Untersuchen Sie schnell Datensätze in den Abfrageergebnissen mit dem neuen Bereich Details.</span><span class="sxs-lookup"><span data-stu-id="9b622-126">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="9b622-127">Mai 2020</span><span class="sxs-lookup"><span data-stu-id="9b622-127">May 2020</span></span>
- [<span data-ttu-id="9b622-128">Benutzerdefinierte Erkennungen</span><span class="sxs-lookup"><span data-stu-id="9b622-128">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="9b622-129">Verwenden Sie erweiterte Jagd Abfragen, um benutzerdefinierte Erkennungsregeln zu erstellen, die Sicherheitsereignisse und Systemzustände automatisch überwachen und darauf reagieren.</span><span class="sxs-lookup"><span data-stu-id="9b622-129">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="9b622-130">Februar 2020</span><span class="sxs-lookup"><span data-stu-id="9b622-130">February 2020</span></span>
- [<span data-ttu-id="9b622-131">Vorfälle</span><span class="sxs-lookup"><span data-stu-id="9b622-131">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="9b622-132">Genau wissen, wo ein Angriff gestartet wurde, und andere Details, die Ihnen helfen, den Umfang des Angriffs zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="9b622-132">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="9b622-133">Automatische Untersuchung und Reaktion</span><span class="sxs-lookup"><span data-stu-id="9b622-133">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="9b622-134">Mit AIR können Ihre Sicherheitsteams die Kapazität Ihrer Organisation im Umgang mit Sicherheitswarnungen und Vorfällen erheblich verbessern.</span><span class="sxs-lookup"><span data-stu-id="9b622-134">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="9b622-135">Erweiterte Jagd Verbesserungen</span><span class="sxs-lookup"><span data-stu-id="9b622-135">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="9b622-136">Proaktive Suche nach Bedrohungen durch den modernen Arbeitsbereich mit Kusto-Abfragesprache und einem sicherheitsoptimierten Schema.</span><span class="sxs-lookup"><span data-stu-id="9b622-136">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="9b622-137">März 2019</span><span class="sxs-lookup"><span data-stu-id="9b622-137">March 2019</span></span>
- <span data-ttu-id="9b622-138">Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="9b622-138">Advanced hunting</span></span> <br> <span data-ttu-id="9b622-139">Zielseite mit verschiedenen Jagd Funktionen, mit denen Sie Bedrohungen proaktiv finden können, die sich auf e-Mails und Daten, Geräte und Identitäten auswirken.</span><span class="sxs-lookup"><span data-stu-id="9b622-139">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="9b622-140">Microsoft-Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="9b622-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="9b622-141">Messung der Sicherheitslage einer Organisation mit einer höheren Zahl, die mehr Verbesserungs Aktionen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="9b622-141">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="9b622-142">Wenn Sie den Empfehlungen der Sicherheitsbewertung folgen, können Sie Ihre Organisation vor Bedrohungen schützen.</span><span class="sxs-lookup"><span data-stu-id="9b622-142">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="9b622-143">Berichte</span><span class="sxs-lookup"><span data-stu-id="9b622-143">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="9b622-144">Verfügt über eine Reihe von Karten, die eine Vielzahl von Bereichen abdecken, die Sicherheitsanalysten und Administratoren im Rahmen ihres täglichen Betriebs verfolgen.</span><span class="sxs-lookup"><span data-stu-id="9b622-144">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
