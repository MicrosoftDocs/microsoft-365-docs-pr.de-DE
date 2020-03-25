---
title: AccountInfo-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über Benutzerkontoinformationen in der accountinfo-Tabelle des Advanced Hunting-Schemas.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, alertinfo, Warnung, Entitäten, Evidence, File, IP-Adresse, Gerät, Computer, Benutzer, Konto
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929528"
---
# <a name="accountinfo"></a><span data-ttu-id="58336-104">AccountInfo</span><span class="sxs-lookup"><span data-stu-id="58336-104">AccountInfo</span></span>

<span data-ttu-id="58336-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="58336-105">**Applies to:**</span></span>
- <span data-ttu-id="58336-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="58336-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="58336-107">Die `AccountInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Benutzerkonten, die von verschiedenen Diensten abgerufen wurden, einschließlich Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="58336-107">The `AccountInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="58336-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="58336-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="58336-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="58336-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="58336-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="58336-110">Column name</span></span> | <span data-ttu-id="58336-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="58336-111">Data type</span></span> | <span data-ttu-id="58336-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58336-112">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="58336-113">string</span><span class="sxs-lookup"><span data-stu-id="58336-113">string</span></span> | <span data-ttu-id="58336-114">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="58336-114">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="58336-115">string</span><span class="sxs-lookup"><span data-stu-id="58336-115">string</span></span> | <span data-ttu-id="58336-116">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="58336-116">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="58336-117">string</span><span class="sxs-lookup"><span data-stu-id="58336-117">string</span></span> | <span data-ttu-id="58336-118">Lokale Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="58336-118">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="58336-119">string</span><span class="sxs-lookup"><span data-stu-id="58336-119">string</span></span> | <span data-ttu-id="58336-120">Cloud-Sicherheits-ID des Kontos</span><span class="sxs-lookup"><span data-stu-id="58336-120">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="58336-121">string</span><span class="sxs-lookup"><span data-stu-id="58336-121">string</span></span> | <span data-ttu-id="58336-122">Vorname oder Vorname des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="58336-122">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="58336-123">string</span><span class="sxs-lookup"><span data-stu-id="58336-123">string</span></span> | <span data-ttu-id="58336-124">Nachname, Familienname oder Nachname des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="58336-124">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="58336-125">string</span><span class="sxs-lookup"><span data-stu-id="58336-125">string</span></span> | <span data-ttu-id="58336-126">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="58336-126">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="58336-127">Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="58336-127">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="58336-128">string</span><span class="sxs-lookup"><span data-stu-id="58336-128">string</span></span> | <span data-ttu-id="58336-129">Name der Abteilung, zu der der Benutzer des Kontos gehört</span><span class="sxs-lookup"><span data-stu-id="58336-129">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="58336-130">string</span><span class="sxs-lookup"><span data-stu-id="58336-130">string</span></span> | <span data-ttu-id="58336-131">Position des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="58336-131">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="58336-132">string</span><span class="sxs-lookup"><span data-stu-id="58336-132">string</span></span> | <span data-ttu-id="58336-133">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="58336-133">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="58336-134">string</span><span class="sxs-lookup"><span data-stu-id="58336-134">string</span></span> | <span data-ttu-id="58336-135">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="58336-135">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="58336-136">string</span><span class="sxs-lookup"><span data-stu-id="58336-136">string</span></span> | <span data-ttu-id="58336-137">SMTP-Adresse des Kontos</span><span class="sxs-lookup"><span data-stu-id="58336-137">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="58336-138">string</span><span class="sxs-lookup"><span data-stu-id="58336-138">string</span></span> | <span data-ttu-id="58336-139">SIP-Adresse (Voice of over IP (VoIP) Session Initiation Protocol) des Kontos</span><span class="sxs-lookup"><span data-stu-id="58336-139">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="58336-140">string</span><span class="sxs-lookup"><span data-stu-id="58336-140">string</span></span> | <span data-ttu-id="58336-141">Ort, an dem sich der Benutzer des Kontos befindet</span><span class="sxs-lookup"><span data-stu-id="58336-141">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="58336-142">string</span><span class="sxs-lookup"><span data-stu-id="58336-142">string</span></span> | <span data-ttu-id="58336-143">Land/Region, in dem sich der Benutzer des Kontos befindet</span><span class="sxs-lookup"><span data-stu-id="58336-143">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="58336-144">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="58336-144">boolean</span></span> | <span data-ttu-id="58336-145">Gibt an, ob das Konto aktiviert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="58336-145">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="58336-146">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="58336-146">Related topics</span></span>
- [<span data-ttu-id="58336-147">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="58336-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="58336-148">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="58336-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="58336-149">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="58336-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="58336-150">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="58336-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="58336-151">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="58336-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="58336-152">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="58336-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
