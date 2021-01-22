---
title: Tabelle "CloudAppEvents" im Schema "Erweiterte Suche"
description: Informationen zu Ereignissen von Cloud-Apps und -Diensten in der Tabelle "CloudAppEvents" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, CloudAppEvents, Cloud App Security, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928453"
---
# <a name="cloudappevents"></a><span data-ttu-id="a4037-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="a4037-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a4037-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a4037-105">**Applies to:**</span></span>
- <span data-ttu-id="a4037-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4037-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a4037-107">Derzeit in der Vorschau verfügbar, enthält die Tabelle im Schema für die erweiterte Suche Informationen zu Aktivitäten in verschiedenen Cloud-Apps und -Diensten, insbesondere `CloudAppEvents` Microsoft Teams und Exchange Online. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a4037-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="a4037-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a4037-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a4037-109">Diese Tabelle wird erweitert, um weitere Aktivitäten zu enthalten, die von Microsoft Cloud App Security überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="a4037-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="a4037-110">Schließlich enthält diese Tabelle Dateiaktivität, die derzeit in der Tabelle ["AppFileEvents" gespeichert](advanced-hunting-appfileevents-table.md) ist.</span><span class="sxs-lookup"><span data-stu-id="a4037-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="a4037-111">Microsoft stellt zusätzliche Anleitungen zur Verfügung, wenn mehr Daten zu dieser Tabelle bewegt werden.</span><span class="sxs-lookup"><span data-stu-id="a4037-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="a4037-112">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a4037-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a4037-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="a4037-113">Column name</span></span> | <span data-ttu-id="a4037-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a4037-114">Data type</span></span> | <span data-ttu-id="a4037-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4037-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a4037-116">datetime</span><span class="sxs-lookup"><span data-stu-id="a4037-116">datetime</span></span> | <span data-ttu-id="a4037-117">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4037-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="a4037-118">string</span><span class="sxs-lookup"><span data-stu-id="a4037-118">string</span></span> | <span data-ttu-id="a4037-119">Aktivitätstyp, der das Ereignis ausgelöst hat</span><span class="sxs-lookup"><span data-stu-id="a4037-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="a4037-120">string</span><span class="sxs-lookup"><span data-stu-id="a4037-120">string</span></span> | <span data-ttu-id="a4037-121">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="a4037-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="a4037-122">string</span><span class="sxs-lookup"><span data-stu-id="a4037-122">string</span></span> | <span data-ttu-id="a4037-123">Eindeutiger Bezeichner für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="a4037-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="a4037-124">string</span><span class="sxs-lookup"><span data-stu-id="a4037-124">string</span></span> | <span data-ttu-id="a4037-125">Eindeutige ID für das Konto in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a4037-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="a4037-126">string</span><span class="sxs-lookup"><span data-stu-id="a4037-126">string</span></span> | <span data-ttu-id="a4037-127">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a4037-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="a4037-128">In der Regel eine Kombination aus einem Vor- oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="a4037-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="a4037-129">string</span><span class="sxs-lookup"><span data-stu-id="a4037-129">string</span></span> | <span data-ttu-id="a4037-130">Gibt an, ob die Aktivität von einem Administrator ausgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="a4037-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="a4037-131">string</span><span class="sxs-lookup"><span data-stu-id="a4037-131">string</span></span> | <span data-ttu-id="a4037-132">Gerätetyp basierend auf Zweck und Funktionalität, z. B. "Netzwerkgerät", "Arbeitsstation", "Server", "Mobil", "Spielekonsole" oder "Drucker"</span><span class="sxs-lookup"><span data-stu-id="a4037-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="a4037-133">string</span><span class="sxs-lookup"><span data-stu-id="a4037-133">string</span></span> | <span data-ttu-id="a4037-134">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a4037-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="a4037-135">Diese Spalte gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="a4037-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="a4037-136">string</span><span class="sxs-lookup"><span data-stu-id="a4037-136">string</span></span> | <span data-ttu-id="a4037-137">Dem Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="a4037-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="a4037-138">string</span><span class="sxs-lookup"><span data-stu-id="a4037-138">string</span></span> | <span data-ttu-id="a4037-139">Gibt an, ob die IP-Adresse zu einem bekannten anonymen Proxy gehört</span><span class="sxs-lookup"><span data-stu-id="a4037-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="a4037-140">string</span><span class="sxs-lookup"><span data-stu-id="a4037-140">string</span></span> | <span data-ttu-id="a4037-141">Aus zwei Buchstaben bestehter Code, der das Land angibt, in dem die Client-IP-Adresse geolokaliert ist</span><span class="sxs-lookup"><span data-stu-id="a4037-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="a4037-142">string</span><span class="sxs-lookup"><span data-stu-id="a4037-142">string</span></span> | <span data-ttu-id="a4037-143">Ort, in dem die Client-IP-Adresse geolokaliert ist</span><span class="sxs-lookup"><span data-stu-id="a4037-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="a4037-144">string</span><span class="sxs-lookup"><span data-stu-id="a4037-144">string</span></span> | <span data-ttu-id="a4037-145">Internetdienstanbieter (Internet Service Provider, ISP), der der IP-Adresse zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="a4037-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="a4037-146">string</span><span class="sxs-lookup"><span data-stu-id="a4037-146">string</span></span> | <span data-ttu-id="a4037-147">Benutzer-Agent-Informationen aus dem Webbrowser oder einer anderen Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="a4037-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="a4037-148">string</span><span class="sxs-lookup"><span data-stu-id="a4037-148">string</span></span> | <span data-ttu-id="a4037-149">Aktivitätstyp, der das Ereignis ausgelöst hat</span><span class="sxs-lookup"><span data-stu-id="a4037-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="a4037-150">string</span><span class="sxs-lookup"><span data-stu-id="a4037-150">string</span></span> | <span data-ttu-id="a4037-151">Liste der Objekte, z. B. Dateien oder Ordner, die an der aufgezeichneten Aktivität beteiligt waren</span><span class="sxs-lookup"><span data-stu-id="a4037-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="a4037-152">string</span><span class="sxs-lookup"><span data-stu-id="a4037-152">string</span></span> | <span data-ttu-id="a4037-153">Name des Objekts, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="a4037-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="a4037-154">string</span><span class="sxs-lookup"><span data-stu-id="a4037-154">string</span></span> | <span data-ttu-id="a4037-155">Objekttyp, z. B. eine Datei oder ein Ordner, auf den die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="a4037-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="a4037-156">string</span><span class="sxs-lookup"><span data-stu-id="a4037-156">string</span></span> | <span data-ttu-id="a4037-157">Eindeutiger Bezeichner des Objekts, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="a4037-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="a4037-158">string</span><span class="sxs-lookup"><span data-stu-id="a4037-158">string</span></span> | <span data-ttu-id="a4037-159">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4037-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="a4037-160">string</span><span class="sxs-lookup"><span data-stu-id="a4037-160">string</span></span> | <span data-ttu-id="a4037-161">Unformatierte Ereignisinformationen aus der Quellanwendung oder dem Quelldienst im JSON-Format</span><span class="sxs-lookup"><span data-stu-id="a4037-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="a4037-162">string</span><span class="sxs-lookup"><span data-stu-id="a4037-162">string</span></span> | <span data-ttu-id="a4037-163">Zusätzliche Informationen über die Entität oder das Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4037-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a4037-164">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a4037-164">Related topics</span></span>
- [<span data-ttu-id="a4037-165">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="a4037-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a4037-166">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="a4037-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a4037-167">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="a4037-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a4037-168">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="a4037-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a4037-169">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="a4037-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a4037-170">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="a4037-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
