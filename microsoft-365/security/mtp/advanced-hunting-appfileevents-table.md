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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 663dc2a3de676fa2daeab3d9621254e956d42fc4
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204755"
---
# <a name="appfileevents"></a><span data-ttu-id="93071-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="93071-104">AppFileEvents</span></span>

<span data-ttu-id="93071-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="93071-105">**Applies to:**</span></span>
- <span data-ttu-id="93071-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="93071-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="93071-107">Die `AppFileEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu dateibezogenen Aktivitäten in Cloud-apps und-Diensten, die von Microsoft Cloud App Security überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="93071-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="93071-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="93071-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="93071-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="93071-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="93071-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="93071-110">Column name</span></span> | <span data-ttu-id="93071-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="93071-111">Data type</span></span> | <span data-ttu-id="93071-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93071-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="93071-113">datetime</span><span class="sxs-lookup"><span data-stu-id="93071-113">datetime</span></span> | <span data-ttu-id="93071-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="93071-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="93071-115">string</span><span class="sxs-lookup"><span data-stu-id="93071-115">string</span></span> | <span data-ttu-id="93071-116">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="93071-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="93071-117">string</span><span class="sxs-lookup"><span data-stu-id="93071-117">string</span></span> | <span data-ttu-id="93071-118">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="93071-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="93071-119">string</span><span class="sxs-lookup"><span data-stu-id="93071-119">string</span></span> | <span data-ttu-id="93071-120">Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="93071-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="93071-121">string</span><span class="sxs-lookup"><span data-stu-id="93071-121">string</span></span> | <span data-ttu-id="93071-122">Ordner mit der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="93071-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="93071-123">string</span><span class="sxs-lookup"><span data-stu-id="93071-123">string</span></span> | <span data-ttu-id="93071-124">Ursprünglicher Name der Datei, die als Ergebnis der Aktion umbenannt wurde</span><span class="sxs-lookup"><span data-stu-id="93071-124">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="93071-125">string</span><span class="sxs-lookup"><span data-stu-id="93071-125">string</span></span> | <span data-ttu-id="93071-126">Ursprünglicher Ordner, der die Datei enthält, bevor die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="93071-126">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="93071-127">string</span><span class="sxs-lookup"><span data-stu-id="93071-127">string</span></span> | <span data-ttu-id="93071-128">Verwendetes Netzwerkprotokoll</span><span class="sxs-lookup"><span data-stu-id="93071-128">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="93071-129">string</span><span class="sxs-lookup"><span data-stu-id="93071-129">string</span></span> | <span data-ttu-id="93071-130">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="93071-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="93071-131">string</span><span class="sxs-lookup"><span data-stu-id="93071-131">string</span></span> | <span data-ttu-id="93071-132">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="93071-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="93071-133">string</span><span class="sxs-lookup"><span data-stu-id="93071-133">string</span></span> | <span data-ttu-id="93071-134">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="93071-134">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="93071-135">string</span><span class="sxs-lookup"><span data-stu-id="93071-135">string</span></span> | <span data-ttu-id="93071-136">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="93071-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="93071-137">string</span><span class="sxs-lookup"><span data-stu-id="93071-137">string</span></span> | <span data-ttu-id="93071-138">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="93071-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="93071-139">Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="93071-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="93071-140">string</span><span class="sxs-lookup"><span data-stu-id="93071-140">string</span></span> | <span data-ttu-id="93071-141">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="93071-141">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="93071-142">string</span><span class="sxs-lookup"><span data-stu-id="93071-142">string</span></span> | <span data-ttu-id="93071-143">Gerätetyp</span><span class="sxs-lookup"><span data-stu-id="93071-143">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="93071-144">string</span><span class="sxs-lookup"><span data-stu-id="93071-144">string</span></span> | <span data-ttu-id="93071-145">Plattform des auf dem Gerät ausgeführten Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="93071-145">Platform of the operating system running on the device.</span></span> <span data-ttu-id="93071-146">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="93071-146">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="93071-147">string</span><span class="sxs-lookup"><span data-stu-id="93071-147">string</span></span> | <span data-ttu-id="93071-148">Dem Endpunkt zugewiesene IP-Adresse und wird während der zugehörigen Netzwerkkommunikation verwendet</span><span class="sxs-lookup"><span data-stu-id="93071-148">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="93071-149">string</span><span class="sxs-lookup"><span data-stu-id="93071-149">string</span></span> | <span data-ttu-id="93071-150">Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="93071-150">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="93071-151">string</span><span class="sxs-lookup"><span data-stu-id="93071-151">string</span></span> | <span data-ttu-id="93071-152">IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="93071-152">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="93071-153">string</span><span class="sxs-lookup"><span data-stu-id="93071-153">string</span></span> | <span data-ttu-id="93071-154">Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="93071-154">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="93071-155">string</span><span class="sxs-lookup"><span data-stu-id="93071-155">string</span></span> | <span data-ttu-id="93071-156">Internet Dienstanbieter (Internet Service Provider, ISP), der der IP-Endpunktadresse zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="93071-156">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="93071-157">long</span><span class="sxs-lookup"><span data-stu-id="93071-157">long</span></span> | <span data-ttu-id="93071-158">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="93071-158">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="93071-159">string</span><span class="sxs-lookup"><span data-stu-id="93071-159">string</span></span> | <span data-ttu-id="93071-160">Zusätzliche Informationen zur Entität oder zum Ereignis</span><span class="sxs-lookup"><span data-stu-id="93071-160">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="93071-161">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="93071-161">Related topics</span></span>
- [<span data-ttu-id="93071-162">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="93071-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="93071-163">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="93071-163">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="93071-164">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="93071-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="93071-165">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="93071-165">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="93071-166">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="93071-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="93071-167">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="93071-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
