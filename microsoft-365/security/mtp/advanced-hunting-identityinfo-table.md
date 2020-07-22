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
ms.openlocfilehash: e922fc7930d645a7024a0ffc73359277c4b637e4
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204923"
---
# <a name="identityinfo"></a><span data-ttu-id="90171-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="90171-104">IdentityInfo</span></span>

<span data-ttu-id="90171-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="90171-105">**Applies to:**</span></span>
- <span data-ttu-id="90171-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90171-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="90171-107">Die `IdentityInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Benutzerkonten, die von verschiedenen Diensten abgerufen wurden, einschließlich Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="90171-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="90171-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="90171-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="90171-109">Diese Tabelle wurde umbenannt aus `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="90171-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="90171-110">Während der Namensänderung werden alle im Portal gespeicherten Abfragen automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="90171-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="90171-111">Überprüfen Sie Abfragen, die Sie an einer anderen Stelle gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="90171-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="90171-112">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="90171-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="90171-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="90171-113">Column name</span></span> | <span data-ttu-id="90171-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="90171-114">Data type</span></span> | <span data-ttu-id="90171-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90171-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="90171-116">string</span><span class="sxs-lookup"><span data-stu-id="90171-116">string</span></span> | <span data-ttu-id="90171-117">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="90171-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="90171-118">string</span><span class="sxs-lookup"><span data-stu-id="90171-118">string</span></span> | <span data-ttu-id="90171-119">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="90171-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="90171-120">string</span><span class="sxs-lookup"><span data-stu-id="90171-120">string</span></span> | <span data-ttu-id="90171-121">Lokale Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="90171-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="90171-122">string</span><span class="sxs-lookup"><span data-stu-id="90171-122">string</span></span> | <span data-ttu-id="90171-123">Cloud-Sicherheits-ID des Kontos</span><span class="sxs-lookup"><span data-stu-id="90171-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="90171-124">string</span><span class="sxs-lookup"><span data-stu-id="90171-124">string</span></span> | <span data-ttu-id="90171-125">Vorname oder Vorname des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="90171-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="90171-126">string</span><span class="sxs-lookup"><span data-stu-id="90171-126">string</span></span> | <span data-ttu-id="90171-127">Nachname, Familienname oder Nachname des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="90171-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="90171-128">string</span><span class="sxs-lookup"><span data-stu-id="90171-128">string</span></span> | <span data-ttu-id="90171-129">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="90171-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="90171-130">Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="90171-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="90171-131">string</span><span class="sxs-lookup"><span data-stu-id="90171-131">string</span></span> | <span data-ttu-id="90171-132">Name der Abteilung, zu der der Benutzer des Kontos gehört</span><span class="sxs-lookup"><span data-stu-id="90171-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="90171-133">string</span><span class="sxs-lookup"><span data-stu-id="90171-133">string</span></span> | <span data-ttu-id="90171-134">Position des Kontobenutzers</span><span class="sxs-lookup"><span data-stu-id="90171-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="90171-135">string</span><span class="sxs-lookup"><span data-stu-id="90171-135">string</span></span> | <span data-ttu-id="90171-136">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="90171-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="90171-137">string</span><span class="sxs-lookup"><span data-stu-id="90171-137">string</span></span> | <span data-ttu-id="90171-138">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="90171-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="90171-139">string</span><span class="sxs-lookup"><span data-stu-id="90171-139">string</span></span> | <span data-ttu-id="90171-140">SMTP-Adresse des Kontos</span><span class="sxs-lookup"><span data-stu-id="90171-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="90171-141">string</span><span class="sxs-lookup"><span data-stu-id="90171-141">string</span></span> | <span data-ttu-id="90171-142">SIP-Adresse (Voice over IP, VoIP) des Sitzungs Initiierungs Protokolls des Kontos</span><span class="sxs-lookup"><span data-stu-id="90171-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="90171-143">string</span><span class="sxs-lookup"><span data-stu-id="90171-143">string</span></span> | <span data-ttu-id="90171-144">Ort, an dem sich der Benutzer des Kontos befindet</span><span class="sxs-lookup"><span data-stu-id="90171-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="90171-145">string</span><span class="sxs-lookup"><span data-stu-id="90171-145">string</span></span> | <span data-ttu-id="90171-146">Land/Region, in dem sich der Benutzer des Kontos befindet</span><span class="sxs-lookup"><span data-stu-id="90171-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="90171-147">boolean</span><span class="sxs-lookup"><span data-stu-id="90171-147">boolean</span></span> | <span data-ttu-id="90171-148">Gibt an, ob das Konto aktiviert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="90171-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="90171-149">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="90171-149">Related topics</span></span>
- [<span data-ttu-id="90171-150">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="90171-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="90171-151">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="90171-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="90171-152">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="90171-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="90171-153">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="90171-153">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="90171-154">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="90171-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="90171-155">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="90171-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
