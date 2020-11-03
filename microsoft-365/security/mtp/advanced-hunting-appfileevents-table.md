---
title: AppFileEvents-Tabelle im Advanced Hunting-Schema
description: Informationen zu dateibezogenen Ereignissen im Zusammenhang mit Cloud-apps und-Diensten in der AppFileEvents-Tabelle des Advanced Hunting-Schemas
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AppFileEvents, Cloud-App-Sicherheit, MCAS
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
ms.openlocfilehash: 1a7f523e96c0a46c29098f7e5bb2fbb83a4db4bb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847656"
---
# <a name="appfileevents"></a><span data-ttu-id="9587c-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="9587c-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9587c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9587c-105">**Applies to:**</span></span>
- <span data-ttu-id="9587c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9587c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9587c-107">Die `AppFileEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu dateibezogenen Aktivitäten in Cloud-apps und-Diensten, die von Microsoft Cloud App Security überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="9587c-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="9587c-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="9587c-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="9587c-109">Ausführliche Informationen zu den `ActionType` von einer Tabelle unterstützten Ereignistypen (Values) finden Sie in der [integrierten Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) , die im Sicherheitscenter verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9587c-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="9587c-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9587c-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9587c-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="9587c-111">Column name</span></span> | <span data-ttu-id="9587c-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9587c-112">Data type</span></span> | <span data-ttu-id="9587c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9587c-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9587c-114">datetime</span><span class="sxs-lookup"><span data-stu-id="9587c-114">datetime</span></span> | <span data-ttu-id="9587c-115">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9587c-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="9587c-116">string</span><span class="sxs-lookup"><span data-stu-id="9587c-116">string</span></span> | <span data-ttu-id="9587c-117">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="9587c-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="9587c-118">Details finden Sie [in der in-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) .</span><span class="sxs-lookup"><span data-stu-id="9587c-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="9587c-119">string</span><span class="sxs-lookup"><span data-stu-id="9587c-119">string</span></span> | <span data-ttu-id="9587c-120">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="9587c-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="9587c-121">string</span><span class="sxs-lookup"><span data-stu-id="9587c-121">string</span></span> | <span data-ttu-id="9587c-122">Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="9587c-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="9587c-123">string</span><span class="sxs-lookup"><span data-stu-id="9587c-123">string</span></span> | <span data-ttu-id="9587c-124">Ordner mit der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="9587c-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="9587c-125">string</span><span class="sxs-lookup"><span data-stu-id="9587c-125">string</span></span> | <span data-ttu-id="9587c-126">Ursprünglicher Name der Datei, die als Ergebnis der Aktion umbenannt wurde</span><span class="sxs-lookup"><span data-stu-id="9587c-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="9587c-127">string</span><span class="sxs-lookup"><span data-stu-id="9587c-127">string</span></span> | <span data-ttu-id="9587c-128">Ursprünglicher Ordner, der die Datei enthält, bevor die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="9587c-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="9587c-129">string</span><span class="sxs-lookup"><span data-stu-id="9587c-129">string</span></span> | <span data-ttu-id="9587c-130">Verwendetes Netzwerkprotokoll</span><span class="sxs-lookup"><span data-stu-id="9587c-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="9587c-131">string</span><span class="sxs-lookup"><span data-stu-id="9587c-131">string</span></span> | <span data-ttu-id="9587c-132">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="9587c-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9587c-133">string</span><span class="sxs-lookup"><span data-stu-id="9587c-133">string</span></span> | <span data-ttu-id="9587c-134">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="9587c-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="9587c-135">string</span><span class="sxs-lookup"><span data-stu-id="9587c-135">string</span></span> | <span data-ttu-id="9587c-136">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="9587c-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="9587c-137">string</span><span class="sxs-lookup"><span data-stu-id="9587c-137">string</span></span> | <span data-ttu-id="9587c-138">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="9587c-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9587c-139">string</span><span class="sxs-lookup"><span data-stu-id="9587c-139">string</span></span> | <span data-ttu-id="9587c-140">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9587c-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9587c-141">Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="9587c-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="9587c-142">string</span><span class="sxs-lookup"><span data-stu-id="9587c-142">string</span></span> | <span data-ttu-id="9587c-143">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="9587c-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="9587c-144">string</span><span class="sxs-lookup"><span data-stu-id="9587c-144">string</span></span> | <span data-ttu-id="9587c-145">Gerätetyp</span><span class="sxs-lookup"><span data-stu-id="9587c-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="9587c-146">string</span><span class="sxs-lookup"><span data-stu-id="9587c-146">string</span></span> | <span data-ttu-id="9587c-147">Plattform des auf dem Gerät ausgeführten Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="9587c-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="9587c-148">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="9587c-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="9587c-149">string</span><span class="sxs-lookup"><span data-stu-id="9587c-149">string</span></span> | <span data-ttu-id="9587c-150">Dem Endpunkt zugewiesene IP-Adresse und wird während der zugehörigen Netzwerkkommunikation verwendet</span><span class="sxs-lookup"><span data-stu-id="9587c-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="9587c-151">string</span><span class="sxs-lookup"><span data-stu-id="9587c-151">string</span></span> | <span data-ttu-id="9587c-152">Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="9587c-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="9587c-153">string</span><span class="sxs-lookup"><span data-stu-id="9587c-153">string</span></span> | <span data-ttu-id="9587c-154">IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="9587c-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="9587c-155">string</span><span class="sxs-lookup"><span data-stu-id="9587c-155">string</span></span> | <span data-ttu-id="9587c-156">Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="9587c-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="9587c-157">string</span><span class="sxs-lookup"><span data-stu-id="9587c-157">string</span></span> | <span data-ttu-id="9587c-158">Internet Dienstanbieter (Internet Service Provider, ISP), der der IP-Endpunktadresse zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="9587c-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="9587c-159">long</span><span class="sxs-lookup"><span data-stu-id="9587c-159">long</span></span> | <span data-ttu-id="9587c-160">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="9587c-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="9587c-161">string</span><span class="sxs-lookup"><span data-stu-id="9587c-161">string</span></span> | <span data-ttu-id="9587c-162">Zusätzliche Informationen zur Entität oder zum Ereignis</span><span class="sxs-lookup"><span data-stu-id="9587c-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9587c-163">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9587c-163">Related topics</span></span>
- [<span data-ttu-id="9587c-164">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="9587c-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9587c-165">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="9587c-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9587c-166">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="9587c-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9587c-167">Suchen auf Geräten, in E-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="9587c-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9587c-168">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="9587c-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9587c-169">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="9587c-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
