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
ms.openlocfilehash: b2fc94d6ac6606c97b4824bc556b7299a2bd8ec7
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929164"
---
# <a name="identityqueryevents"></a><span data-ttu-id="cc666-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="cc666-104">IdentityQueryEvents</span></span>

<span data-ttu-id="cc666-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cc666-105">**Applies to:**</span></span>
- <span data-ttu-id="cc666-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cc666-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="cc666-107">Die `IdentityQueryEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Abfragen, die für Active Directory-Objekte wie Benutzer, Gruppen, Geräte und Domänen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cc666-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="cc666-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="cc666-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="cc666-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="cc666-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="cc666-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="cc666-110">Column name</span></span> | <span data-ttu-id="cc666-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="cc666-111">Data type</span></span> | <span data-ttu-id="cc666-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc666-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="cc666-113">datetime</span><span class="sxs-lookup"><span data-stu-id="cc666-113">datetime</span></span> | <span data-ttu-id="cc666-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="cc666-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="cc666-115">string</span><span class="sxs-lookup"><span data-stu-id="cc666-115">string</span></span> | <span data-ttu-id="cc666-116">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="cc666-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="cc666-117">string</span><span class="sxs-lookup"><span data-stu-id="cc666-117">string</span></span> | <span data-ttu-id="cc666-118">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="cc666-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="cc666-119">string</span><span class="sxs-lookup"><span data-stu-id="cc666-119">string</span></span> | <span data-ttu-id="cc666-120">Typ der Abfrage: querygroup, QueryUser oder EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="cc666-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="cc666-121">string</span><span class="sxs-lookup"><span data-stu-id="cc666-121">string</span></span> | <span data-ttu-id="cc666-122">Name des Benutzers, der Gruppe, des Geräts, der Domäne oder eines beliebigen anderen Entitätstyps, der abgefragt wird</span><span class="sxs-lookup"><span data-stu-id="cc666-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="cc666-123">string</span><span class="sxs-lookup"><span data-stu-id="cc666-123">string</span></span> | <span data-ttu-id="cc666-124">Während der Kommunikation verwendete Protokolle</span><span class="sxs-lookup"><span data-stu-id="cc666-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="cc666-125">string</span><span class="sxs-lookup"><span data-stu-id="cc666-125">string</span></span> | <span data-ttu-id="cc666-126">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="cc666-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="cc666-127">string</span><span class="sxs-lookup"><span data-stu-id="cc666-127">string</span></span> | <span data-ttu-id="cc666-128">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="cc666-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="cc666-129">string</span><span class="sxs-lookup"><span data-stu-id="cc666-129">string</span></span> | <span data-ttu-id="cc666-130">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="cc666-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="cc666-131">string</span><span class="sxs-lookup"><span data-stu-id="cc666-131">string</span></span> | <span data-ttu-id="cc666-132">Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="cc666-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="cc666-133">string</span><span class="sxs-lookup"><span data-stu-id="cc666-133">string</span></span> | <span data-ttu-id="cc666-134">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="cc666-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="cc666-135">string</span><span class="sxs-lookup"><span data-stu-id="cc666-135">string</span></span> | <span data-ttu-id="cc666-136">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cc666-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="cc666-137">Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="cc666-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="cc666-138">string</span><span class="sxs-lookup"><span data-stu-id="cc666-138">string</span></span> | <span data-ttu-id="cc666-139">Vollqualifizierter Domänenname (FQDN) des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="cc666-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="cc666-140">string</span><span class="sxs-lookup"><span data-stu-id="cc666-140">string</span></span> | <span data-ttu-id="cc666-141">Dem Endpunkt zugewiesene IP-Adresse und wird während der zugehörigen Netzwerkkommunikation verwendet</span><span class="sxs-lookup"><span data-stu-id="cc666-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="cc666-142">string</span><span class="sxs-lookup"><span data-stu-id="cc666-142">string</span></span> | <span data-ttu-id="cc666-143">Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="cc666-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="cc666-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cc666-144">Related topics</span></span>
- [<span data-ttu-id="cc666-145">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="cc666-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cc666-146">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="cc666-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cc666-147">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="cc666-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cc666-148">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="cc666-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cc666-149">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="cc666-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cc666-150">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="cc666-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
