---
title: IdentityInfo-Tabelle im schema der erweiterten Suche
description: Informationen zu Benutzerkonteninformationen in der IdentityInfo-Tabelle des schemas für die erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AccountInfo, IdentityInfo, account
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ce1a3d5153d324d008d2d46048838351eb7bc047
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935821"
---
# <a name="identityinfo"></a><span data-ttu-id="c595e-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="c595e-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c595e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c595e-105">**Applies to:**</span></span>
- <span data-ttu-id="c595e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c595e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c595e-107">Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Benutzerkonten, die von verschiedenen `IdentityInfo` Diensten, einschließlich Azure Active Directory, [](advanced-hunting-overview.md) erhalten wurden.</span><span class="sxs-lookup"><span data-stu-id="c595e-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="c595e-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c595e-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="c595e-109">Diese Tabelle wurde von `AccountInfo` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="c595e-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="c595e-110">Während der Umbenennung werden alle im Portal gespeicherten Abfragen automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c595e-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="c595e-111">Überprüfen Sie Abfragen, die Sie an anderer Stelle gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="c595e-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="c595e-112">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c595e-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c595e-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c595e-113">Column name</span></span> | <span data-ttu-id="c595e-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c595e-114">Data type</span></span> | <span data-ttu-id="c595e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c595e-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="c595e-116">string</span><span class="sxs-lookup"><span data-stu-id="c595e-116">string</span></span> | <span data-ttu-id="c595e-117">Eindeutige ID für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="c595e-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="c595e-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-118">string</span></span> | <span data-ttu-id="c595e-119">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="c595e-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="c595e-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-120">string</span></span> | <span data-ttu-id="c595e-121">Lokale Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="c595e-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="c595e-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-122">string</span></span> | <span data-ttu-id="c595e-123">Cloudsicherheits-ID des Kontos</span><span class="sxs-lookup"><span data-stu-id="c595e-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="c595e-124">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-124">string</span></span> | <span data-ttu-id="c595e-125">Vorname oder Vorname des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="c595e-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="c595e-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-126">string</span></span> | <span data-ttu-id="c595e-127">Nachname, Familienname oder Nachname des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="c595e-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="c595e-128">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-128">string</span></span> | <span data-ttu-id="c595e-129">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c595e-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="c595e-130">In der Regel eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="c595e-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="c595e-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-131">string</span></span> | <span data-ttu-id="c595e-132">Name der Abteilung, zu der der Kontobenutzer gehört</span><span class="sxs-lookup"><span data-stu-id="c595e-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="c595e-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-133">string</span></span> | <span data-ttu-id="c595e-134">Auftragstitel des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="c595e-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="c595e-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-135">string</span></span> | <span data-ttu-id="c595e-136">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="c595e-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="c595e-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-137">string</span></span> | <span data-ttu-id="c595e-138">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="c595e-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="c595e-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-139">string</span></span> | <span data-ttu-id="c595e-140">SMTP-Adresse des Kontos</span><span class="sxs-lookup"><span data-stu-id="c595e-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="c595e-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-141">string</span></span> | <span data-ttu-id="c595e-142">Voice over IP (VOIP) Session Initiation Protocol (SIP)-Adresse des Kontos</span><span class="sxs-lookup"><span data-stu-id="c595e-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="c595e-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-143">string</span></span> | <span data-ttu-id="c595e-144">Ort, in dem sich der Kontobenutzer befindet</span><span class="sxs-lookup"><span data-stu-id="c595e-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="c595e-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c595e-145">string</span></span> | <span data-ttu-id="c595e-146">Land/Region, in dem sich der Kontobenutzer befindet</span><span class="sxs-lookup"><span data-stu-id="c595e-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="c595e-147">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="c595e-147">boolean</span></span> | <span data-ttu-id="c595e-148">Gibt an, ob das Konto aktiviert ist oder nicht</span><span class="sxs-lookup"><span data-stu-id="c595e-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c595e-149">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c595e-149">Related topics</span></span>
- [<span data-ttu-id="c595e-150">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="c595e-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c595e-151">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="c595e-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c595e-152">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="c595e-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c595e-153">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="c595e-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c595e-154">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="c595e-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c595e-155">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="c595e-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
