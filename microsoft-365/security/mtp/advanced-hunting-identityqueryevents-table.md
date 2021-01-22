---
title: Tabelle "IdentityQueryEvents" im Schema "Erweiterte Suche"
description: Informationen zu Active Directory-Abfrageereignissen in der Tabelle "IdentityQueryEvents" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, Identitäten, LDAP-Abfragen
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
ms.openlocfilehash: 7016127a75bca48103f5325ce169faa3d7c31c85
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929814"
---
# <a name="identityqueryevents"></a><span data-ttu-id="59680-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="59680-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="59680-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="59680-105">**Applies to:**</span></span>
- <span data-ttu-id="59680-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59680-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="59680-107">Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Abfragen, die für Active Directory-Objekte ausgeführt werden, z. B. `IdentityQueryEvents` Benutzer, Gruppen, Geräte [](advanced-hunting-overview.md) und Domänen.</span><span class="sxs-lookup"><span data-stu-id="59680-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="59680-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="59680-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="59680-109">Ausführliche Informationen zu den Ereignistypen (Werten), die von einer Tabelle unterstützt werden, finden Sie in der integrierten Schemareferenz, die im `ActionType` Security Center verfügbar ist. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="59680-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="59680-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="59680-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="59680-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="59680-111">Column name</span></span> | <span data-ttu-id="59680-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="59680-112">Data type</span></span> | <span data-ttu-id="59680-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59680-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="59680-114">datetime</span><span class="sxs-lookup"><span data-stu-id="59680-114">datetime</span></span> | <span data-ttu-id="59680-115">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="59680-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="59680-116">string</span><span class="sxs-lookup"><span data-stu-id="59680-116">string</span></span> | <span data-ttu-id="59680-117">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="59680-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="59680-118">Details finden Sie in der [In-Portal-Schemareferenz.](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="59680-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="59680-119">string</span><span class="sxs-lookup"><span data-stu-id="59680-119">string</span></span> | <span data-ttu-id="59680-120">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="59680-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="59680-121">string</span><span class="sxs-lookup"><span data-stu-id="59680-121">string</span></span> | <span data-ttu-id="59680-122">Abfragetyp, z. B. QueryGroup, QueryUser oder EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="59680-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="59680-123">string</span><span class="sxs-lookup"><span data-stu-id="59680-123">string</span></span> | <span data-ttu-id="59680-124">Name des Benutzers, der Gruppe, des Geräts, der Domäne oder eines anderen Entitätstyps, der abgefragt wird</span><span class="sxs-lookup"><span data-stu-id="59680-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="59680-125">string</span><span class="sxs-lookup"><span data-stu-id="59680-125">string</span></span> | <span data-ttu-id="59680-126">Zum Ausführen der Abfrage verwendete Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="59680-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="59680-127">string</span><span class="sxs-lookup"><span data-stu-id="59680-127">string</span></span> | <span data-ttu-id="59680-128">Protokoll, das während der Kommunikation verwendet wird</span><span class="sxs-lookup"><span data-stu-id="59680-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="59680-129">string</span><span class="sxs-lookup"><span data-stu-id="59680-129">string</span></span> | <span data-ttu-id="59680-130">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="59680-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="59680-131">string</span><span class="sxs-lookup"><span data-stu-id="59680-131">string</span></span> | <span data-ttu-id="59680-132">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="59680-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="59680-133">string</span><span class="sxs-lookup"><span data-stu-id="59680-133">string</span></span> | <span data-ttu-id="59680-134">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="59680-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="59680-135">string</span><span class="sxs-lookup"><span data-stu-id="59680-135">string</span></span> | <span data-ttu-id="59680-136">Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="59680-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="59680-137">string</span><span class="sxs-lookup"><span data-stu-id="59680-137">string</span></span> | <span data-ttu-id="59680-138">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="59680-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="59680-139">string</span><span class="sxs-lookup"><span data-stu-id="59680-139">string</span></span> | <span data-ttu-id="59680-140">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="59680-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="59680-141">In der Regel eine Kombination aus einem Vor- oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="59680-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="59680-142">string</span><span class="sxs-lookup"><span data-stu-id="59680-142">string</span></span> | <span data-ttu-id="59680-143">Vollqualifizierter Domänenname (FQDN) des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="59680-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="59680-144">string</span><span class="sxs-lookup"><span data-stu-id="59680-144">string</span></span> | <span data-ttu-id="59680-145">Dem Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="59680-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="59680-146">string</span><span class="sxs-lookup"><span data-stu-id="59680-146">string</span></span> | <span data-ttu-id="59680-147">Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="59680-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="59680-148">string</span><span class="sxs-lookup"><span data-stu-id="59680-148">string</span></span> | <span data-ttu-id="59680-149">Die IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="59680-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="59680-150">string</span><span class="sxs-lookup"><span data-stu-id="59680-150">string</span></span> | <span data-ttu-id="59680-151">Vollqualifizierter Domänenname (FQDN) des Geräts, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="59680-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="59680-152">string</span><span class="sxs-lookup"><span data-stu-id="59680-152">string</span></span> | <span data-ttu-id="59680-153">Benutzerprinzipalname (UPN) des Kontos, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="59680-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="59680-154">string</span><span class="sxs-lookup"><span data-stu-id="59680-154">string</span></span> | <span data-ttu-id="59680-155">Anzeigename des Kontos, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="59680-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="59680-156">string</span><span class="sxs-lookup"><span data-stu-id="59680-156">string</span></span> | <span data-ttu-id="59680-157">Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="59680-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="59680-158">long</span><span class="sxs-lookup"><span data-stu-id="59680-158">long</span></span> | <span data-ttu-id="59680-159">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="59680-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="59680-160">string</span><span class="sxs-lookup"><span data-stu-id="59680-160">string</span></span> | <span data-ttu-id="59680-161">Zusätzliche Informationen über die Entität oder das Ereignis</span><span class="sxs-lookup"><span data-stu-id="59680-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="59680-162">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="59680-162">Related topics</span></span>
- [<span data-ttu-id="59680-163">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="59680-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="59680-164">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="59680-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="59680-165">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="59680-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="59680-166">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="59680-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="59680-167">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="59680-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="59680-168">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="59680-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
