---
title: CloudAppEvents-Tabelle im Advanced Hunting-Schema
description: Informationen zu Ereignissen in Cloud-apps und-Diensten in der CloudAppEvents-Tabelle des Advanced Hunting-Schemas
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, CloudAppEvents, Cloud-App-Sicherheit, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087766"
---
# <a name="cloudappevents"></a><span data-ttu-id="926ba-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="926ba-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="926ba-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="926ba-105">**Applies to:**</span></span>
- <span data-ttu-id="926ba-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="926ba-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="926ba-107">Derzeit in der Vorschau verfügbar, `CloudAppEvents` enthält die Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schemainformationen zu Aktivitäten in verschiedenen Cloud-apps und-Diensten, insbesondere Microsoft Teams und Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="926ba-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="926ba-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="926ba-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="926ba-109">Diese Tabelle wird erweitert, um weitere Aktivitäten einzubeziehen, die von Microsoft Cloud App Security überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="926ba-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="926ba-110">Schließlich enthält diese Tabelle die Dateiaktivität, die derzeit in der [AppFileEvents](advanced-hunting-appfileevents-table.md) -Tabelle gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="926ba-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="926ba-111">Microsoft stellt zusätzliche Anleitungen bereit, wenn mehr Daten in diese Tabelle verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="926ba-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="926ba-112">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="926ba-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="926ba-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="926ba-113">Column name</span></span> | <span data-ttu-id="926ba-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="926ba-114">Data type</span></span> | <span data-ttu-id="926ba-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="926ba-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="926ba-116">datetime</span><span class="sxs-lookup"><span data-stu-id="926ba-116">datetime</span></span> | <span data-ttu-id="926ba-117">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="926ba-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="926ba-118">string</span><span class="sxs-lookup"><span data-stu-id="926ba-118">string</span></span> | <span data-ttu-id="926ba-119">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="926ba-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="926ba-120">string</span><span class="sxs-lookup"><span data-stu-id="926ba-120">string</span></span> | <span data-ttu-id="926ba-121">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="926ba-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="926ba-122">string</span><span class="sxs-lookup"><span data-stu-id="926ba-122">string</span></span> | <span data-ttu-id="926ba-123">Eindeutiger Bezeichner für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="926ba-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="926ba-124">string</span><span class="sxs-lookup"><span data-stu-id="926ba-124">string</span></span> | <span data-ttu-id="926ba-125">Eindeutiger Bezeichner für das Konto in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="926ba-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="926ba-126">string</span><span class="sxs-lookup"><span data-stu-id="926ba-126">string</span></span> | <span data-ttu-id="926ba-127">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="926ba-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="926ba-128">Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="926ba-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="926ba-129">string</span><span class="sxs-lookup"><span data-stu-id="926ba-129">string</span></span> | <span data-ttu-id="926ba-130">Gibt an, ob die Aktivität von einem Administrator ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="926ba-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="926ba-131">string</span><span class="sxs-lookup"><span data-stu-id="926ba-131">string</span></span> | <span data-ttu-id="926ba-132">Gerätetyp basierend auf Zweck und Funktionalität, wie "Netzwerkgerät", "Workstation", "Server", "Mobil", "Spielekonsole" oder "Drucker"</span><span class="sxs-lookup"><span data-stu-id="926ba-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="926ba-133">string</span><span class="sxs-lookup"><span data-stu-id="926ba-133">string</span></span> | <span data-ttu-id="926ba-134">Plattform des auf dem Gerät ausgeführten Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="926ba-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="926ba-135">Diese Spalte gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie wie Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="926ba-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="926ba-136">string</span><span class="sxs-lookup"><span data-stu-id="926ba-136">string</span></span> | <span data-ttu-id="926ba-137">Dem Endpunkt zugewiesene IP-Adresse und wird während der zugehörigen Netzwerkkommunikation verwendet</span><span class="sxs-lookup"><span data-stu-id="926ba-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="926ba-138">string</span><span class="sxs-lookup"><span data-stu-id="926ba-138">string</span></span> | <span data-ttu-id="926ba-139">Gibt an, ob die IP-Adresse zu einem bekannten anonymen Proxy gehört.</span><span class="sxs-lookup"><span data-stu-id="926ba-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="926ba-140">string</span><span class="sxs-lookup"><span data-stu-id="926ba-140">string</span></span> | <span data-ttu-id="926ba-141">Code mit zwei Buchstaben, der das Land angibt, in dem sich die IP-Adresse des Clients befindet</span><span class="sxs-lookup"><span data-stu-id="926ba-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="926ba-142">string</span><span class="sxs-lookup"><span data-stu-id="926ba-142">string</span></span> | <span data-ttu-id="926ba-143">Ort, an dem die IP-Adresse des Clients geolokalisiert ist</span><span class="sxs-lookup"><span data-stu-id="926ba-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="926ba-144">string</span><span class="sxs-lookup"><span data-stu-id="926ba-144">string</span></span> | <span data-ttu-id="926ba-145">Internet Dienstanbieter (Internet Service Provider, ISP), der der IP-Adresse zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="926ba-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="926ba-146">string</span><span class="sxs-lookup"><span data-stu-id="926ba-146">string</span></span> | <span data-ttu-id="926ba-147">Informationen zum Benutzer-Agent über den Webbrowser oder eine andere Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="926ba-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="926ba-148">string</span><span class="sxs-lookup"><span data-stu-id="926ba-148">string</span></span> | <span data-ttu-id="926ba-149">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="926ba-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="926ba-150">string</span><span class="sxs-lookup"><span data-stu-id="926ba-150">string</span></span> | <span data-ttu-id="926ba-151">Liste der Objekte, wie Dateien oder Ordner, die an der aufgezeichneten Aktivität beteiligt waren</span><span class="sxs-lookup"><span data-stu-id="926ba-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="926ba-152">string</span><span class="sxs-lookup"><span data-stu-id="926ba-152">string</span></span> | <span data-ttu-id="926ba-153">Name des Objekts, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="926ba-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="926ba-154">string</span><span class="sxs-lookup"><span data-stu-id="926ba-154">string</span></span> | <span data-ttu-id="926ba-155">Typ des Objekts (beispielsweise eine Datei oder ein Ordner), auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="926ba-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="926ba-156">string</span><span class="sxs-lookup"><span data-stu-id="926ba-156">string</span></span> | <span data-ttu-id="926ba-157">Eindeutiger Bezeichner des Objekts, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="926ba-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="926ba-158">string</span><span class="sxs-lookup"><span data-stu-id="926ba-158">string</span></span> | <span data-ttu-id="926ba-159">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="926ba-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="926ba-160">string</span><span class="sxs-lookup"><span data-stu-id="926ba-160">string</span></span> | <span data-ttu-id="926ba-161">Rohdaten von Ereignisinformationen aus der Quellanwendung oder dem Dienst im JSON-Format</span><span class="sxs-lookup"><span data-stu-id="926ba-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="926ba-162">string</span><span class="sxs-lookup"><span data-stu-id="926ba-162">string</span></span> | <span data-ttu-id="926ba-163">Zusätzliche Informationen zur Entität oder zum Ereignis</span><span class="sxs-lookup"><span data-stu-id="926ba-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="926ba-164">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="926ba-164">Related topics</span></span>
- [<span data-ttu-id="926ba-165">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="926ba-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="926ba-166">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="926ba-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="926ba-167">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="926ba-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="926ba-168">Suchen auf Geräten, in E-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="926ba-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="926ba-169">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="926ba-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="926ba-170">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="926ba-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
