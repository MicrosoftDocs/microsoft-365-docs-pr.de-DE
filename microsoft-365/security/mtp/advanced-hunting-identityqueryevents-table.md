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
ms.openlocfilehash: bec7f13d49e2ccf4e3a9121d5e5a2fecd1b10aa2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899113"
---
# <a name="identityqueryevents"></a><span data-ttu-id="a7e6d-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="a7e6d-104">IdentityQueryEvents</span></span>

<span data-ttu-id="a7e6d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a7e6d-105">**Applies to:**</span></span>
- <span data-ttu-id="a7e6d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a7e6d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a7e6d-107">Die `IdentityQueryEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Abfragen, die für Active Directory-Objekte wie Benutzer, Gruppen, Geräte und Domänen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="a7e6d-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a7e6d-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a7e6d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a7e6d-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="a7e6d-110">Column name</span></span> | <span data-ttu-id="a7e6d-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a7e6d-111">Data type</span></span> | <span data-ttu-id="a7e6d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7e6d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a7e6d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="a7e6d-113">datetime</span></span> | <span data-ttu-id="a7e6d-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a7e6d-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="a7e6d-115">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-115">string</span></span> | <span data-ttu-id="a7e6d-116">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="a7e6d-117">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-117">string</span></span> | <span data-ttu-id="a7e6d-118">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="a7e6d-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="a7e6d-119">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-119">string</span></span> | <span data-ttu-id="a7e6d-120">Typ der Abfrage: querygroup, QueryUser oder EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="a7e6d-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="a7e6d-121">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-121">string</span></span> | <span data-ttu-id="a7e6d-122">Name des Benutzers, der Gruppe, des Geräts, der Domäne oder eines beliebigen anderen Entitätstyps, der abgefragt wird</span><span class="sxs-lookup"><span data-stu-id="a7e6d-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="a7e6d-123">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-123">string</span></span> | <span data-ttu-id="a7e6d-124">Während der Kommunikation verwendete Protokolle</span><span class="sxs-lookup"><span data-stu-id="a7e6d-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="a7e6d-125">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-125">string</span></span> | <span data-ttu-id="a7e6d-126">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="a7e6d-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="a7e6d-127">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-127">string</span></span> | <span data-ttu-id="a7e6d-128">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="a7e6d-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="a7e6d-129">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-129">string</span></span> | <span data-ttu-id="a7e6d-130">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="a7e6d-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="a7e6d-131">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-131">string</span></span> | <span data-ttu-id="a7e6d-132">Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="a7e6d-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="a7e6d-133">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-133">string</span></span> | <span data-ttu-id="a7e6d-134">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="a7e6d-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="a7e6d-135">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-135">string</span></span> | <span data-ttu-id="a7e6d-136">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="a7e6d-137">Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="a7e6d-138">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-138">string</span></span> | <span data-ttu-id="a7e6d-139">Vollqualifizierter Domänenname (FQDN) des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="a7e6d-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="a7e6d-140">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-140">string</span></span> | <span data-ttu-id="a7e6d-141">Dem Endpunkt zugewiesene IP-Adresse und wird während der zugehörigen Netzwerkkommunikation verwendet</span><span class="sxs-lookup"><span data-stu-id="a7e6d-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="a7e6d-142">string</span><span class="sxs-lookup"><span data-stu-id="a7e6d-142">string</span></span> | <span data-ttu-id="a7e6d-143">Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="a7e6d-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a7e6d-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a7e6d-144">Related topics</span></span>
- [<span data-ttu-id="a7e6d-145">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="a7e6d-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a7e6d-146">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="a7e6d-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a7e6d-147">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="a7e6d-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a7e6d-148">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="a7e6d-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a7e6d-149">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="a7e6d-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a7e6d-150">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="a7e6d-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
