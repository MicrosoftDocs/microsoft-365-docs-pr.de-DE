---
title: Tabelle "IdentityInfo" im Schema "Erweiterte Suche"
description: Informationen zu Benutzerkontoinformationen in der Tabelle "IdentityInfo" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AccountInfo, IdentityInfo, Konto
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
ms.openlocfilehash: 6604e6d48e277e840b87ddc461580bcb69dd1bc7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929910"
---
# <a name="identityinfo"></a><span data-ttu-id="fda3e-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="fda3e-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fda3e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fda3e-105">**Applies to:**</span></span>
- <span data-ttu-id="fda3e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fda3e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fda3e-107">Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Benutzerkonten, die von verschiedenen `IdentityInfo` Diensten, einschließlich Azure Active Directory, [](advanced-hunting-overview.md) erhalten wurden.</span><span class="sxs-lookup"><span data-stu-id="fda3e-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="fda3e-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="fda3e-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="fda3e-109">Diese Tabelle wurde umbenannt von `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="fda3e-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="fda3e-110">Während der Umbenennung werden alle im Portal gespeicherten Abfragen automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="fda3e-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="fda3e-111">Überprüfen Sie Abfragen, die Sie an anderer Stelle gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="fda3e-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="fda3e-112">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="fda3e-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="fda3e-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="fda3e-113">Column name</span></span> | <span data-ttu-id="fda3e-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="fda3e-114">Data type</span></span> | <span data-ttu-id="fda3e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fda3e-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="fda3e-116">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-116">string</span></span> | <span data-ttu-id="fda3e-117">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="fda3e-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="fda3e-118">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-118">string</span></span> | <span data-ttu-id="fda3e-119">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="fda3e-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="fda3e-120">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-120">string</span></span> | <span data-ttu-id="fda3e-121">Lokale Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="fda3e-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="fda3e-122">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-122">string</span></span> | <span data-ttu-id="fda3e-123">Cloudsicherheits-ID des Kontos</span><span class="sxs-lookup"><span data-stu-id="fda3e-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="fda3e-124">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-124">string</span></span> | <span data-ttu-id="fda3e-125">Vorname oder Vorname des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="fda3e-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="fda3e-126">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-126">string</span></span> | <span data-ttu-id="fda3e-127">Nachname, Familienname oder Nachname des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="fda3e-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="fda3e-128">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-128">string</span></span> | <span data-ttu-id="fda3e-129">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fda3e-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="fda3e-130">In der Regel eine Kombination aus einem Vor- oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="fda3e-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="fda3e-131">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-131">string</span></span> | <span data-ttu-id="fda3e-132">Name der Abteilung, der der Kontobenutzer angehört</span><span class="sxs-lookup"><span data-stu-id="fda3e-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="fda3e-133">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-133">string</span></span> | <span data-ttu-id="fda3e-134">Job title of the account user</span><span class="sxs-lookup"><span data-stu-id="fda3e-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="fda3e-135">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-135">string</span></span> | <span data-ttu-id="fda3e-136">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="fda3e-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="fda3e-137">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-137">string</span></span> | <span data-ttu-id="fda3e-138">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="fda3e-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="fda3e-139">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-139">string</span></span> | <span data-ttu-id="fda3e-140">Die SMTP-Adresse des Kontos</span><span class="sxs-lookup"><span data-stu-id="fda3e-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="fda3e-141">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-141">string</span></span> | <span data-ttu-id="fda3e-142">Voice over IP (VOIP)-SIP-Adresse (Session Initiation Protocol) des Kontos</span><span class="sxs-lookup"><span data-stu-id="fda3e-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="fda3e-143">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-143">string</span></span> | <span data-ttu-id="fda3e-144">Ort, in dem sich der Kontobenutzer befindet</span><span class="sxs-lookup"><span data-stu-id="fda3e-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="fda3e-145">string</span><span class="sxs-lookup"><span data-stu-id="fda3e-145">string</span></span> | <span data-ttu-id="fda3e-146">Land/Region, in dem sich der Kontobenutzer befindet</span><span class="sxs-lookup"><span data-stu-id="fda3e-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="fda3e-147">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="fda3e-147">boolean</span></span> | <span data-ttu-id="fda3e-148">Gibt an, ob das Konto aktiviert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="fda3e-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="fda3e-149">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fda3e-149">Related topics</span></span>
- [<span data-ttu-id="fda3e-150">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="fda3e-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fda3e-151">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="fda3e-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fda3e-152">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="fda3e-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fda3e-153">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="fda3e-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fda3e-154">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="fda3e-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fda3e-155">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="fda3e-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
