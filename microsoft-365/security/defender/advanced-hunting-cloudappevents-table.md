---
title: CloudAppEvents-Tabelle im schema der erweiterten Suche
description: Erfahren Sie mehr über Ereignisse aus Cloud-Apps und -Diensten in der CloudAppEvents-Tabelle des schemas für erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, CloudAppEvents, Cloud App Security, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 83b9eec37648ba48aa8e6931e836e8a5e22458c8
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760026"
---
# <a name="cloudappevents"></a><span data-ttu-id="dae2c-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="dae2c-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dae2c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="dae2c-105">**Applies to:**</span></span>
- <span data-ttu-id="dae2c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dae2c-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="dae2c-107">Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Aktivitäten in verschiedenen Cloud-Apps und -Diensten, die `CloudAppEvents` von Microsoft Cloud App Security abgedeckt werden. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="dae2c-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="dae2c-108">Eine vollständige Liste finden Sie unter [Apps and services covered](#apps-and-services-covered).</span><span class="sxs-lookup"><span data-stu-id="dae2c-108">For a complete list, jump to [Apps and services covered](#apps-and-services-covered).</span></span> <span data-ttu-id="dae2c-109">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="dae2c-109">Use this reference to construct queries that return information from this table.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="dae2c-110">Diese Tabelle enthält Informationen, die früher in der Tabelle verfügbar `AppFileEvents` waren.</span><span class="sxs-lookup"><span data-stu-id="dae2c-110">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="dae2c-111">Ab dem 7. März 2021 sollten Benutzer, die dateibezogene Aktivitäten in Clouddiensten an und über dieses Datum hinaus durchsuchen, stattdessen die `CloudAppEvents` Tabelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="dae2c-111">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="dae2c-112">Achten Sie darauf, nach Abfragen und benutzerdefinierten Erkennungsregeln zu suchen, die weiterhin die Tabelle verwenden, und bearbeiten Sie `AppFileEvents` sie, um die Tabelle zu `CloudAppEvents` verwenden.</span><span class="sxs-lookup"><span data-stu-id="dae2c-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="dae2c-113">Weitere Anleitungen zum Konvertieren betroffener Abfragen finden Sie unter [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span><span class="sxs-lookup"><span data-stu-id="dae2c-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="dae2c-114">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="dae2c-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="dae2c-115">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="dae2c-115">Column name</span></span> | <span data-ttu-id="dae2c-116">Datentyp</span><span class="sxs-lookup"><span data-stu-id="dae2c-116">Data type</span></span> | <span data-ttu-id="dae2c-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dae2c-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="dae2c-118">datetime</span><span class="sxs-lookup"><span data-stu-id="dae2c-118">datetime</span></span> | <span data-ttu-id="dae2c-119">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="dae2c-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="dae2c-120">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-120">string</span></span> | <span data-ttu-id="dae2c-121">Typ der Aktivität, die das Ereignis ausgelöst hat</span><span class="sxs-lookup"><span data-stu-id="dae2c-121">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="dae2c-122">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-122">string</span></span> | <span data-ttu-id="dae2c-123">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="dae2c-123">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="dae2c-124">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-124">string</span></span> | <span data-ttu-id="dae2c-125">Eindeutige ID für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="dae2c-125">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="dae2c-126">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-126">string</span></span> | <span data-ttu-id="dae2c-127">Eindeutige ID für das Konto in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="dae2c-127">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="dae2c-128">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-128">string</span></span> | <span data-ttu-id="dae2c-129">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dae2c-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="dae2c-130">In der Regel eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="dae2c-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="dae2c-131">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-131">string</span></span> | <span data-ttu-id="dae2c-132">Gibt an, ob die Aktivität von einem Administrator ausgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="dae2c-132">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="dae2c-133">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-133">string</span></span> | <span data-ttu-id="dae2c-134">Gerätetyp basierend auf Zweck und Funktionalität, z. B. "Netzwerkgerät", "Workstation", "Server", "Mobile", "Spielekonsole" oder "Drucker"</span><span class="sxs-lookup"><span data-stu-id="dae2c-134">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="dae2c-135">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-135">string</span></span> | <span data-ttu-id="dae2c-136">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dae2c-136">Platform of the operating system running on the device.</span></span> <span data-ttu-id="dae2c-137">Diese Spalte gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="dae2c-137">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="dae2c-138">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-138">string</span></span> | <span data-ttu-id="dae2c-139">DEM Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="dae2c-139">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="dae2c-140">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-140">string</span></span> | <span data-ttu-id="dae2c-141">Gibt an, ob die IP-Adresse zu einem bekannten anonymen Proxy gehört</span><span class="sxs-lookup"><span data-stu-id="dae2c-141">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="dae2c-142">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-142">string</span></span> | <span data-ttu-id="dae2c-143">Zwei-Buchstaben-Code, der das Land angibt, in dem die Client-IP-Adresse geolokaliert ist</span><span class="sxs-lookup"><span data-stu-id="dae2c-143">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="dae2c-144">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-144">string</span></span> | <span data-ttu-id="dae2c-145">Ort, in dem die Client-IP-Adresse geolokaliert ist</span><span class="sxs-lookup"><span data-stu-id="dae2c-145">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="dae2c-146">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-146">string</span></span> | <span data-ttu-id="dae2c-147">Internetdienstanbieter (Internet Service Provider, ISP), der der IP-Adresse zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="dae2c-147">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="dae2c-148">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-148">string</span></span> | <span data-ttu-id="dae2c-149">Benutzer-Agent-Informationen aus dem Webbrowser oder einer anderen Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="dae2c-149">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="dae2c-150">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-150">string</span></span> | <span data-ttu-id="dae2c-151">Typ der Aktivität, die das Ereignis ausgelöst hat</span><span class="sxs-lookup"><span data-stu-id="dae2c-151">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="dae2c-152">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-152">string</span></span> | <span data-ttu-id="dae2c-153">Liste der Objekte, z. B. Dateien oder Ordner, die an der aufgezeichneten Aktivität beteiligt waren</span><span class="sxs-lookup"><span data-stu-id="dae2c-153">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="dae2c-154">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-154">string</span></span> | <span data-ttu-id="dae2c-155">Name des Objekts, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="dae2c-155">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="dae2c-156">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-156">string</span></span> | <span data-ttu-id="dae2c-157">Objekttyp, z. B. eine Datei oder ein Ordner, auf den die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="dae2c-157">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="dae2c-158">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-158">string</span></span> | <span data-ttu-id="dae2c-159">Eindeutiger Bezeichner des Objekts, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="dae2c-159">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="dae2c-160">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-160">string</span></span> | <span data-ttu-id="dae2c-161">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="dae2c-161">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="dae2c-162">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-162">string</span></span> | <span data-ttu-id="dae2c-163">Unformatierte Ereignisinformationen aus der Quellanwendung oder dem Quelldienst im JSON-Format</span><span class="sxs-lookup"><span data-stu-id="dae2c-163">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="dae2c-164">string</span><span class="sxs-lookup"><span data-stu-id="dae2c-164">string</span></span> | <span data-ttu-id="dae2c-165">Zusätzliche Informationen zur Entität oder zum Ereignis</span><span class="sxs-lookup"><span data-stu-id="dae2c-165">Additional information about the entity or event</span></span> |

## <a name="apps-and-services-covered"></a><span data-ttu-id="dae2c-166">Abgedeckte Apps und Dienste</span><span class="sxs-lookup"><span data-stu-id="dae2c-166">Apps and services covered</span></span>

- <span data-ttu-id="dae2c-167">Dropbox</span><span class="sxs-lookup"><span data-stu-id="dae2c-167">Dropbox</span></span>
- <span data-ttu-id="dae2c-168">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="dae2c-168">Dynamics 365</span></span>
- <span data-ttu-id="dae2c-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dae2c-169">Exchange Online</span></span>
- <span data-ttu-id="dae2c-170">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dae2c-170">Microsoft Teams</span></span>
- <span data-ttu-id="dae2c-171">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="dae2c-171">OneDrive for Business</span></span>
- <span data-ttu-id="dae2c-172">Power Automate</span><span class="sxs-lookup"><span data-stu-id="dae2c-172">Power Automate</span></span>
- <span data-ttu-id="dae2c-173">Power BI</span><span class="sxs-lookup"><span data-stu-id="dae2c-173">Power BI</span></span>
- <span data-ttu-id="dae2c-174">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="dae2c-174">SharePoint Online</span></span>
- <span data-ttu-id="dae2c-175">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="dae2c-175">Skype for Business</span></span>
- <span data-ttu-id="dae2c-176">Office 365</span><span class="sxs-lookup"><span data-stu-id="dae2c-176">Office 365</span></span>
- <span data-ttu-id="dae2c-177">Yammer</span><span class="sxs-lookup"><span data-stu-id="dae2c-177">Yammer</span></span> 

## <a name="related-topics"></a><span data-ttu-id="dae2c-178">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="dae2c-178">Related topics</span></span>
- [<span data-ttu-id="dae2c-179">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="dae2c-179">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dae2c-180">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="dae2c-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="dae2c-181">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="dae2c-181">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="dae2c-182">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="dae2c-182">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="dae2c-183">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="dae2c-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="dae2c-184">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="dae2c-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
