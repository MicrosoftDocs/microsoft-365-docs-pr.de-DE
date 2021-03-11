---
title: IdentityQueryEvents-Tabelle im schema der erweiterten Suche
description: Informationen zu Active Directory-Abfrageereignissen in der IdentityQueryEvents-Tabelle des erweiterten Suchschemas
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, Identitäten, LDAP-Abfragen
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
ms.openlocfilehash: eb1f408b61444771f5d450b46dbc9c2b4a009e4c
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712330"
---
# <a name="identityqueryevents"></a><span data-ttu-id="c0008-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="c0008-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c0008-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c0008-105">**Applies to:**</span></span>
- <span data-ttu-id="c0008-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0008-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c0008-107">Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Abfragen, die für Active Directory-Objekte ausgeführt werden, z. B. `IdentityQueryEvents` Benutzer, Gruppen, Geräte [](advanced-hunting-overview.md) und Domänen.</span><span class="sxs-lookup"><span data-stu-id="c0008-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="c0008-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c0008-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="c0008-109">Ausführliche Informationen zu den von einer Tabelle unterstützten Ereignistypen ( Werte) finden Sie unter Verwendung der integrierten Schemareferenz, die `ActionType` im Security Center verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c0008-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="c0008-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c0008-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c0008-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c0008-111">Column name</span></span> | <span data-ttu-id="c0008-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c0008-112">Data type</span></span> | <span data-ttu-id="c0008-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0008-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c0008-114">datetime</span><span class="sxs-lookup"><span data-stu-id="c0008-114">datetime</span></span> | <span data-ttu-id="c0008-115">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="c0008-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="c0008-116">string</span><span class="sxs-lookup"><span data-stu-id="c0008-116">string</span></span> | <span data-ttu-id="c0008-117">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="c0008-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="c0008-118">Weitere Informationen [finden Sie in der In-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="c0008-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="c0008-119">string</span><span class="sxs-lookup"><span data-stu-id="c0008-119">string</span></span> | <span data-ttu-id="c0008-120">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="c0008-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="c0008-121">string</span><span class="sxs-lookup"><span data-stu-id="c0008-121">string</span></span> | <span data-ttu-id="c0008-122">Abfragetyp, z. B. QueryGroup, QueryUser oder EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="c0008-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="c0008-123">string</span><span class="sxs-lookup"><span data-stu-id="c0008-123">string</span></span> | <span data-ttu-id="c0008-124">Name des benutzers, der Gruppe, des Geräts, der Domäne oder eines anderen Entitätstyps, der abgefragt wird</span><span class="sxs-lookup"><span data-stu-id="c0008-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="c0008-125">string</span><span class="sxs-lookup"><span data-stu-id="c0008-125">string</span></span> | <span data-ttu-id="c0008-126">Zeichenfolge zum Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0008-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="c0008-127">string</span><span class="sxs-lookup"><span data-stu-id="c0008-127">string</span></span> | <span data-ttu-id="c0008-128">Während der Kommunikation verwendetes Protokoll</span><span class="sxs-lookup"><span data-stu-id="c0008-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="c0008-129">string</span><span class="sxs-lookup"><span data-stu-id="c0008-129">string</span></span> | <span data-ttu-id="c0008-130">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="c0008-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="c0008-131">string</span><span class="sxs-lookup"><span data-stu-id="c0008-131">string</span></span> | <span data-ttu-id="c0008-132">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="c0008-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="c0008-133">string</span><span class="sxs-lookup"><span data-stu-id="c0008-133">string</span></span> | <span data-ttu-id="c0008-134">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="c0008-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="c0008-135">string</span><span class="sxs-lookup"><span data-stu-id="c0008-135">string</span></span> | <span data-ttu-id="c0008-136">Security Identifier (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="c0008-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="c0008-137">string</span><span class="sxs-lookup"><span data-stu-id="c0008-137">string</span></span> | <span data-ttu-id="c0008-138">Eindeutige ID für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="c0008-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="c0008-139">string</span><span class="sxs-lookup"><span data-stu-id="c0008-139">string</span></span> | <span data-ttu-id="c0008-140">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c0008-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="c0008-141">In der Regel eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="c0008-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="c0008-142">string</span><span class="sxs-lookup"><span data-stu-id="c0008-142">string</span></span> | <span data-ttu-id="c0008-143">Vollqualifizierter Domänenname (FQDN) des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="c0008-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="c0008-144">string</span><span class="sxs-lookup"><span data-stu-id="c0008-144">string</span></span> | <span data-ttu-id="c0008-145">DEM Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c0008-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="c0008-146">string</span><span class="sxs-lookup"><span data-stu-id="c0008-146">string</span></span> | <span data-ttu-id="c0008-147">WÄHREND der Kommunikation verwendeter TCP-Port</span><span class="sxs-lookup"><span data-stu-id="c0008-147">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="c0008-148">string</span><span class="sxs-lookup"><span data-stu-id="c0008-148">string</span></span> | <span data-ttu-id="c0008-149">Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="c0008-149">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="c0008-150">string</span><span class="sxs-lookup"><span data-stu-id="c0008-150">string</span></span> | <span data-ttu-id="c0008-151">IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="c0008-151">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="c0008-152">string</span><span class="sxs-lookup"><span data-stu-id="c0008-152">string</span></span> | <span data-ttu-id="c0008-153">Zielport der zugehörigen Netzwerkkommunikation</span><span class="sxs-lookup"><span data-stu-id="c0008-153">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="c0008-154">string</span><span class="sxs-lookup"><span data-stu-id="c0008-154">string</span></span> | <span data-ttu-id="c0008-155">Vollqualifizierter Domänenname (FQDN) des Geräts, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="c0008-155">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="c0008-156">string</span><span class="sxs-lookup"><span data-stu-id="c0008-156">string</span></span> | <span data-ttu-id="c0008-157">Benutzerprinzipalname (UPN) des Kontos, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="c0008-157">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="c0008-158">string</span><span class="sxs-lookup"><span data-stu-id="c0008-158">string</span></span> | <span data-ttu-id="c0008-159">Anzeigename des Kontos, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="c0008-159">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="c0008-160">string</span><span class="sxs-lookup"><span data-stu-id="c0008-160">string</span></span> | <span data-ttu-id="c0008-161">Stadt, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="c0008-161">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="c0008-162">long</span><span class="sxs-lookup"><span data-stu-id="c0008-162">long</span></span> | <span data-ttu-id="c0008-163">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="c0008-163">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="c0008-164">string</span><span class="sxs-lookup"><span data-stu-id="c0008-164">string</span></span> | <span data-ttu-id="c0008-165">Zusätzliche Informationen zur Entität oder zum Ereignis</span><span class="sxs-lookup"><span data-stu-id="c0008-165">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c0008-166">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c0008-166">Related topics</span></span>
- [<span data-ttu-id="c0008-167">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="c0008-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c0008-168">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="c0008-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c0008-169">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="c0008-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c0008-170">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="c0008-170">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c0008-171">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="c0008-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c0008-172">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="c0008-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
