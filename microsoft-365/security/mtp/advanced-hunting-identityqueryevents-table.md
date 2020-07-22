---
title: IdentityQueryEvents-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über Active Directory Abfrage Ereignisse in der IdentityQueryEvents-Tabelle des Advanced Hunting-Schemas.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, Identitäten, LDAP-Abfragen
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
ms.openlocfilehash: 436c4d7306f9f5febd614489090a0a10929ba3c9
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204875"
---
# <a name="identityqueryevents"></a><span data-ttu-id="30434-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="30434-104">IdentityQueryEvents</span></span>

<span data-ttu-id="30434-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="30434-105">**Applies to:**</span></span>
- <span data-ttu-id="30434-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="30434-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="30434-107">Die `IdentityQueryEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Abfragen, die für Active Directory-Objekte wie Benutzer, Gruppen, Geräte und Domänen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="30434-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="30434-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="30434-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="30434-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="30434-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="30434-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="30434-110">Column name</span></span> | <span data-ttu-id="30434-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="30434-111">Data type</span></span> | <span data-ttu-id="30434-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30434-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="30434-113">datetime</span><span class="sxs-lookup"><span data-stu-id="30434-113">datetime</span></span> | <span data-ttu-id="30434-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="30434-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="30434-115">string</span><span class="sxs-lookup"><span data-stu-id="30434-115">string</span></span> | <span data-ttu-id="30434-116">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="30434-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="30434-117">string</span><span class="sxs-lookup"><span data-stu-id="30434-117">string</span></span> | <span data-ttu-id="30434-118">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="30434-118">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="30434-119">string</span><span class="sxs-lookup"><span data-stu-id="30434-119">string</span></span> | <span data-ttu-id="30434-120">Typ der Abfrage, wie Abfragegruppe, QueryUser oder EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="30434-120">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="30434-121">string</span><span class="sxs-lookup"><span data-stu-id="30434-121">string</span></span> | <span data-ttu-id="30434-122">Name des Benutzers, der Gruppe, des Geräts, der Domäne oder eines beliebigen anderen Entitätstyps, der abgefragt wird</span><span class="sxs-lookup"><span data-stu-id="30434-122">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="30434-123">string</span><span class="sxs-lookup"><span data-stu-id="30434-123">string</span></span> | <span data-ttu-id="30434-124">Zum Ausführen der Abfrage verwendete Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="30434-124">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="30434-125">string</span><span class="sxs-lookup"><span data-stu-id="30434-125">string</span></span> | <span data-ttu-id="30434-126">Während der Kommunikation verwendete Protokolle</span><span class="sxs-lookup"><span data-stu-id="30434-126">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="30434-127">string</span><span class="sxs-lookup"><span data-stu-id="30434-127">string</span></span> | <span data-ttu-id="30434-128">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="30434-128">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="30434-129">string</span><span class="sxs-lookup"><span data-stu-id="30434-129">string</span></span> | <span data-ttu-id="30434-130">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="30434-130">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="30434-131">string</span><span class="sxs-lookup"><span data-stu-id="30434-131">string</span></span> | <span data-ttu-id="30434-132">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="30434-132">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="30434-133">string</span><span class="sxs-lookup"><span data-stu-id="30434-133">string</span></span> | <span data-ttu-id="30434-134">Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="30434-134">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="30434-135">string</span><span class="sxs-lookup"><span data-stu-id="30434-135">string</span></span> | <span data-ttu-id="30434-136">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="30434-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="30434-137">string</span><span class="sxs-lookup"><span data-stu-id="30434-137">string</span></span> | <span data-ttu-id="30434-138">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="30434-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="30434-139">Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="30434-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="30434-140">string</span><span class="sxs-lookup"><span data-stu-id="30434-140">string</span></span> | <span data-ttu-id="30434-141">Vollqualifizierter Domänenname (FQDN) des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="30434-141">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="30434-142">string</span><span class="sxs-lookup"><span data-stu-id="30434-142">string</span></span> | <span data-ttu-id="30434-143">Dem Endpunkt zugewiesene IP-Adresse und wird während der zugehörigen Netzwerkkommunikation verwendet</span><span class="sxs-lookup"><span data-stu-id="30434-143">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="30434-144">string</span><span class="sxs-lookup"><span data-stu-id="30434-144">string</span></span> | <span data-ttu-id="30434-145">Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="30434-145">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="30434-146">string</span><span class="sxs-lookup"><span data-stu-id="30434-146">string</span></span> | <span data-ttu-id="30434-147">IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="30434-147">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="30434-148">string</span><span class="sxs-lookup"><span data-stu-id="30434-148">string</span></span> | <span data-ttu-id="30434-149">Vollqualifizierter Domänenname (FQDN) des Geräts, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="30434-149">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="30434-150">string</span><span class="sxs-lookup"><span data-stu-id="30434-150">string</span></span> | <span data-ttu-id="30434-151">Benutzerprinzipalname (User Principal Name, UPN) des Kontos, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="30434-151">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="30434-152">string</span><span class="sxs-lookup"><span data-stu-id="30434-152">string</span></span> | <span data-ttu-id="30434-153">Anzeigename des Kontos, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="30434-153">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="30434-154">string</span><span class="sxs-lookup"><span data-stu-id="30434-154">string</span></span> | <span data-ttu-id="30434-155">Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="30434-155">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="30434-156">long</span><span class="sxs-lookup"><span data-stu-id="30434-156">long</span></span> | <span data-ttu-id="30434-157">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="30434-157">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="30434-158">string</span><span class="sxs-lookup"><span data-stu-id="30434-158">string</span></span> | <span data-ttu-id="30434-159">Zusätzliche Informationen zur Entität oder zum Ereignis</span><span class="sxs-lookup"><span data-stu-id="30434-159">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="30434-160">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="30434-160">Related topics</span></span>
- [<span data-ttu-id="30434-161">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="30434-161">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="30434-162">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="30434-162">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="30434-163">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="30434-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="30434-164">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="30434-164">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="30434-165">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="30434-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="30434-166">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="30434-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
