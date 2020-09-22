---
title: IdentityInfo-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über Benutzerkontoinformationen in der IdentityInfo-Tabelle des Advanced Hunting-Schemas.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, accountinfo, IdentityInfo, Konto
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
ms.openlocfilehash: 6922f50906013cfbfa3bd63c69fff3e89ed46cd5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196821"
---
# <a name="identityinfo"></a><span data-ttu-id="27d73-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="27d73-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="27d73-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="27d73-105">**Applies to:**</span></span>
- <span data-ttu-id="27d73-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="27d73-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="27d73-107">Die `IdentityInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Benutzerkonten, die von verschiedenen Diensten abgerufen wurden, einschließlich Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="27d73-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="27d73-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="27d73-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="27d73-109">Diese Tabelle wurde umbenannt aus `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="27d73-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="27d73-110">Während der Namensänderung werden alle im Portal gespeicherten Abfragen automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="27d73-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="27d73-111">Überprüfen Sie Abfragen, die Sie an einer anderen Stelle gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="27d73-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="27d73-112">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="27d73-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="27d73-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="27d73-113">Column name</span></span> | <span data-ttu-id="27d73-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="27d73-114">Data type</span></span> | <span data-ttu-id="27d73-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27d73-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="27d73-116">string</span><span class="sxs-lookup"><span data-stu-id="27d73-116">string</span></span> | <span data-ttu-id="27d73-117">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="27d73-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="27d73-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-118">string</span></span> | <span data-ttu-id="27d73-119">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="27d73-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="27d73-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-120">string</span></span> | <span data-ttu-id="27d73-121">Lokale Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="27d73-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="27d73-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-122">string</span></span> | <span data-ttu-id="27d73-123">Cloud-Sicherheits-ID des Kontos</span><span class="sxs-lookup"><span data-stu-id="27d73-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="27d73-124">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-124">string</span></span> | <span data-ttu-id="27d73-125">Vorname oder Vorname des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="27d73-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="27d73-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-126">string</span></span> | <span data-ttu-id="27d73-127">Nachname, Familienname oder Nachname des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="27d73-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="27d73-128">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-128">string</span></span> | <span data-ttu-id="27d73-129">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="27d73-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="27d73-130">Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="27d73-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="27d73-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-131">string</span></span> | <span data-ttu-id="27d73-132">Name der Abteilung, zu der der Benutzer des Kontos gehört</span><span class="sxs-lookup"><span data-stu-id="27d73-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="27d73-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-133">string</span></span> | <span data-ttu-id="27d73-134">Position des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="27d73-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="27d73-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-135">string</span></span> | <span data-ttu-id="27d73-136">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="27d73-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="27d73-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-137">string</span></span> | <span data-ttu-id="27d73-138">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="27d73-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="27d73-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-139">string</span></span> | <span data-ttu-id="27d73-140">SMTP-Adresse des Kontos</span><span class="sxs-lookup"><span data-stu-id="27d73-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="27d73-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-141">string</span></span> | <span data-ttu-id="27d73-142">SIP-Adresse (Voice over IP, VoIP) des Sitzungs Initiierungs Protokolls des Kontos</span><span class="sxs-lookup"><span data-stu-id="27d73-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="27d73-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-143">string</span></span> | <span data-ttu-id="27d73-144">Ort, an dem sich der Benutzer des Kontos befindet</span><span class="sxs-lookup"><span data-stu-id="27d73-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="27d73-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="27d73-145">string</span></span> | <span data-ttu-id="27d73-146">Land/Region, in dem sich der Benutzer des Kontos befindet</span><span class="sxs-lookup"><span data-stu-id="27d73-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="27d73-147">boolean</span><span class="sxs-lookup"><span data-stu-id="27d73-147">boolean</span></span> | <span data-ttu-id="27d73-148">Gibt an, ob das Konto aktiviert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="27d73-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="27d73-149">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="27d73-149">Related topics</span></span>
- [<span data-ttu-id="27d73-150">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="27d73-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="27d73-151">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="27d73-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="27d73-152">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="27d73-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="27d73-153">Suchen auf Geräten, in E-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="27d73-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="27d73-154">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="27d73-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="27d73-155">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="27d73-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
