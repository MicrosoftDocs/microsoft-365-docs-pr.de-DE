---
title: IdentityInfo-Tabelle im schema der erweiterten Suche
description: Informationen zu Benutzerkonteninformationen in der IdentityInfo-Tabelle des schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AccountInfo, IdentityInfo, Konto
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
ms.openlocfilehash: d7e1ad4d10c3b71a04421d92304dc2bfcb6147da
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498200"
---
# <a name="identityinfo"></a><span data-ttu-id="505e0-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="505e0-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="505e0-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="505e0-105">**Applies to:**</span></span>
- <span data-ttu-id="505e0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="505e0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="505e0-107">Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Benutzerkonten, die von verschiedenen `IdentityInfo` Diensten, einschließlich Azure Active Directory, [](advanced-hunting-overview.md) erhalten wurden.</span><span class="sxs-lookup"><span data-stu-id="505e0-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="505e0-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="505e0-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="505e0-109">Diese Tabelle wurde von `AccountInfo` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="505e0-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="505e0-110">Während der Umbenennung werden alle im Portal gespeicherten Abfragen automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="505e0-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="505e0-111">Überprüfen Sie Abfragen, die Sie an anderer Stelle gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="505e0-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="505e0-112">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="505e0-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="505e0-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="505e0-113">Column name</span></span> | <span data-ttu-id="505e0-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="505e0-114">Data type</span></span> | <span data-ttu-id="505e0-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="505e0-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="505e0-116">string</span><span class="sxs-lookup"><span data-stu-id="505e0-116">string</span></span> | <span data-ttu-id="505e0-117">Eindeutige ID für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="505e0-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="505e0-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-118">string</span></span> | <span data-ttu-id="505e0-119">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="505e0-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="505e0-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-120">string</span></span> | <span data-ttu-id="505e0-121">Lokale Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="505e0-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="505e0-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-122">string</span></span> | <span data-ttu-id="505e0-123">Cloudsicherheits-ID des Kontos</span><span class="sxs-lookup"><span data-stu-id="505e0-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="505e0-124">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-124">string</span></span> | <span data-ttu-id="505e0-125">Vorname oder Vorname des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="505e0-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="505e0-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-126">string</span></span> | <span data-ttu-id="505e0-127">Nachname, Familienname oder Nachname des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="505e0-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="505e0-128">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-128">string</span></span> | <span data-ttu-id="505e0-129">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="505e0-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="505e0-130">In der Regel eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="505e0-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="505e0-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-131">string</span></span> | <span data-ttu-id="505e0-132">Name der Abteilung, zu der der Kontobenutzer gehört</span><span class="sxs-lookup"><span data-stu-id="505e0-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="505e0-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-133">string</span></span> | <span data-ttu-id="505e0-134">Auftragstitel des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="505e0-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="505e0-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-135">string</span></span> | <span data-ttu-id="505e0-136">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="505e0-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="505e0-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-137">string</span></span> | <span data-ttu-id="505e0-138">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="505e0-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="505e0-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-139">string</span></span> | <span data-ttu-id="505e0-140">SMTP-Adresse des Kontos</span><span class="sxs-lookup"><span data-stu-id="505e0-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="505e0-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-141">string</span></span> | <span data-ttu-id="505e0-142">Voice over IP (VOIP) Session Initiation Protocol (SIP)-Adresse des Kontos</span><span class="sxs-lookup"><span data-stu-id="505e0-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="505e0-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-143">string</span></span> | <span data-ttu-id="505e0-144">Ort, in dem sich der Kontobenutzer befindet</span><span class="sxs-lookup"><span data-stu-id="505e0-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="505e0-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="505e0-145">string</span></span> | <span data-ttu-id="505e0-146">Land/Region, in dem sich der Kontobenutzer befindet</span><span class="sxs-lookup"><span data-stu-id="505e0-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="505e0-147">boolean</span><span class="sxs-lookup"><span data-stu-id="505e0-147">boolean</span></span> | <span data-ttu-id="505e0-148">Gibt an, ob das Konto aktiviert ist oder nicht</span><span class="sxs-lookup"><span data-stu-id="505e0-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="505e0-149">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="505e0-149">Related topics</span></span>
- [<span data-ttu-id="505e0-150">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="505e0-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="505e0-151">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="505e0-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="505e0-152">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="505e0-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="505e0-153">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="505e0-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="505e0-154">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="505e0-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="505e0-155">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="505e0-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
