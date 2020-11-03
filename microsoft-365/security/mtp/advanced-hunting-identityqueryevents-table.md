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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 2b163dc39e56c82ef177b71d197c431c744b12d7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847404"
---
# <a name="identityqueryevents"></a><span data-ttu-id="c4c87-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="c4c87-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c4c87-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c4c87-105">**Applies to:**</span></span>
- <span data-ttu-id="c4c87-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4c87-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c4c87-107">Die `IdentityQueryEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Abfragen, die für Active Directory-Objekte wie Benutzer, Gruppen, Geräte und Domänen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c4c87-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="c4c87-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c4c87-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="c4c87-109">Ausführliche Informationen zu den `ActionType` von einer Tabelle unterstützten Ereignistypen (Values) finden Sie in der [integrierten Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) , die im Sicherheitscenter verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c4c87-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="c4c87-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c4c87-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c4c87-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c4c87-111">Column name</span></span> | <span data-ttu-id="c4c87-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c4c87-112">Data type</span></span> | <span data-ttu-id="c4c87-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4c87-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c4c87-114">datetime</span><span class="sxs-lookup"><span data-stu-id="c4c87-114">datetime</span></span> | <span data-ttu-id="c4c87-115">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="c4c87-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="c4c87-116">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-116">string</span></span> | <span data-ttu-id="c4c87-117">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="c4c87-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="c4c87-118">Details finden Sie [in der in-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) .</span><span class="sxs-lookup"><span data-stu-id="c4c87-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="c4c87-119">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-119">string</span></span> | <span data-ttu-id="c4c87-120">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="c4c87-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="c4c87-121">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-121">string</span></span> | <span data-ttu-id="c4c87-122">Typ der Abfrage, wie Abfragegruppe, QueryUser oder EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="c4c87-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="c4c87-123">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-123">string</span></span> | <span data-ttu-id="c4c87-124">Name des Benutzers, der Gruppe, des Geräts, der Domäne oder eines beliebigen anderen Entitätstyps, der abgefragt wird</span><span class="sxs-lookup"><span data-stu-id="c4c87-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="c4c87-125">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-125">string</span></span> | <span data-ttu-id="c4c87-126">Zum Ausführen der Abfrage verwendete Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c4c87-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="c4c87-127">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-127">string</span></span> | <span data-ttu-id="c4c87-128">Während der Kommunikation verwendete Protokolle</span><span class="sxs-lookup"><span data-stu-id="c4c87-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="c4c87-129">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-129">string</span></span> | <span data-ttu-id="c4c87-130">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="c4c87-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="c4c87-131">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-131">string</span></span> | <span data-ttu-id="c4c87-132">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="c4c87-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="c4c87-133">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-133">string</span></span> | <span data-ttu-id="c4c87-134">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="c4c87-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="c4c87-135">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-135">string</span></span> | <span data-ttu-id="c4c87-136">Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="c4c87-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="c4c87-137">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-137">string</span></span> | <span data-ttu-id="c4c87-138">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="c4c87-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="c4c87-139">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-139">string</span></span> | <span data-ttu-id="c4c87-140">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c4c87-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="c4c87-141">Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="c4c87-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="c4c87-142">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-142">string</span></span> | <span data-ttu-id="c4c87-143">Vollqualifizierter Domänenname (FQDN) des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="c4c87-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="c4c87-144">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-144">string</span></span> | <span data-ttu-id="c4c87-145">Dem Endpunkt zugewiesene IP-Adresse und wird während der zugehörigen Netzwerkkommunikation verwendet</span><span class="sxs-lookup"><span data-stu-id="c4c87-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="c4c87-146">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-146">string</span></span> | <span data-ttu-id="c4c87-147">Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="c4c87-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="c4c87-148">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-148">string</span></span> | <span data-ttu-id="c4c87-149">IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="c4c87-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="c4c87-150">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-150">string</span></span> | <span data-ttu-id="c4c87-151">Vollqualifizierter Domänenname (FQDN) des Geräts, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="c4c87-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="c4c87-152">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-152">string</span></span> | <span data-ttu-id="c4c87-153">Benutzerprinzipalname (User Principal Name, UPN) des Kontos, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="c4c87-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="c4c87-154">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-154">string</span></span> | <span data-ttu-id="c4c87-155">Anzeigename des Kontos, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="c4c87-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="c4c87-156">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-156">string</span></span> | <span data-ttu-id="c4c87-157">Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="c4c87-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="c4c87-158">long</span><span class="sxs-lookup"><span data-stu-id="c4c87-158">long</span></span> | <span data-ttu-id="c4c87-159">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="c4c87-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="c4c87-160">string</span><span class="sxs-lookup"><span data-stu-id="c4c87-160">string</span></span> | <span data-ttu-id="c4c87-161">Zusätzliche Informationen zur Entität oder zum Ereignis</span><span class="sxs-lookup"><span data-stu-id="c4c87-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c4c87-162">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c4c87-162">Related topics</span></span>
- [<span data-ttu-id="c4c87-163">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="c4c87-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c4c87-164">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="c4c87-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c4c87-165">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="c4c87-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c4c87-166">Suchen auf Geräten, in E-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="c4c87-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c4c87-167">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="c4c87-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c4c87-168">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="c4c87-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
