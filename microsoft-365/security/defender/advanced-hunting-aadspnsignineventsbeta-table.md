---
title: AADSpnSignInEventsBeta-Tabelle im Schema für die erweiterte Suche
description: Erfahren Sie mehr über Informationen im Zusammenhang mit Azure Active Directory Anmeldeereignistabelle für dienstprinzipale und verwaltete Identitäten des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, Microsoft 365 Defender, Microsoft 365, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AlertInfo, Warnung, Entitäten, Nachweis, Datei, IP-Adresse, Gerät, Computer, Benutzer, Konto, Identität, AAD
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
ms.openlocfilehash: 6aa709fe4534bf049c6f8c097bc4bd85a9d6793b
ms.sourcegitcommit: 93eeaefc0d509c75e4c2210029155298ecca7583
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53347907"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="ea688-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="ea688-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="ea688-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ea688-105">**Applies to:**</span></span>

- <span data-ttu-id="ea688-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea688-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="ea688-107">Die `AADSpnSignInEventsBeta` Tabelle befindet sich derzeit in der Betaversion und wird kurzfristig angeboten, damit Sie Azure Active Directory (AAD)-Dienstprinzipal- und verwaltete Identitätsanmeldungsereignisse durchsuchen können.</span><span class="sxs-lookup"><span data-stu-id="ea688-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="ea688-108">Wir werden schließlich alle Anmeldeschemainformationen in die `IdentityLogonEvents` Tabelle verschieben.</span><span class="sxs-lookup"><span data-stu-id="ea688-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="ea688-109">Die `AADSpnSignInEventsBeta` Tabelle im Schema für die erweiterte Suche enthält Informationen zu Azure Active Directory Dienstprinzipal- und verwalteten Identitätsanmeldungen. Weitere Informationen zu den verschiedenen Arten von Anmeldungen finden Sie in [Azure Active Directory Anmeldeaktivitätsberichten – Vorschau.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="ea688-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="ea688-110">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ea688-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="ea688-111">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="ea688-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="ea688-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ea688-112">Column name</span></span> | <span data-ttu-id="ea688-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ea688-113">Data type</span></span> | <span data-ttu-id="ea688-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea688-114">Description</span></span> |
|-----|-----|-----|
| `Timestamp` | <span data-ttu-id="ea688-115">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ea688-115">datetime</span></span> | <span data-ttu-id="ea688-116">Datum und Uhrzeit, wann der Datensatz generiert wurde</span><span class="sxs-lookup"><span data-stu-id="ea688-116">Date and time when the record was generated</span></span> |
| `Application` | <span data-ttu-id="ea688-117">string</span><span class="sxs-lookup"><span data-stu-id="ea688-117">string</span></span> | <span data-ttu-id="ea688-118">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="ea688-118">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="ea688-119">string</span><span class="sxs-lookup"><span data-stu-id="ea688-119">string</span></span> | <span data-ttu-id="ea688-120">Eindeutiger Bezeichner für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="ea688-120">Unique identifier for the application</span></span> |
| `IsManagedIdentity`    | <span data-ttu-id="ea688-121">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="ea688-121">boolean</span></span>       | <span data-ttu-id="ea688-122">Gibt an, ob die Anmeldung durch eine verwaltete Identität initiiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ea688-122">Indicates whether the sign-in was initiated by a managed identity</span></span> |
| `ErrorCode`    | <span data-ttu-id="ea688-123">Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="ea688-123">int</span></span> | <span data-ttu-id="ea688-124">Enthält den Fehlercode, wenn ein Anmeldefehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="ea688-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="ea688-125">Eine Beschreibung eines bestimmten Fehlercodes finden Sie unter <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="ea688-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="ea688-126">string</span><span class="sxs-lookup"><span data-stu-id="ea688-126">string</span></span>        | <span data-ttu-id="ea688-127">Eindeutiger Bezeichner des Anmeldeereignisses</span><span class="sxs-lookup"><span data-stu-id="ea688-127">Unique identifier of the sign-in event</span></span> |
| `ServicePrincipalName` | <span data-ttu-id="ea688-128">string</span><span class="sxs-lookup"><span data-stu-id="ea688-128">string</span></span>        | <span data-ttu-id="ea688-129">Name des Dienstprinzipals, der die Anmeldung initiiert hat</span><span class="sxs-lookup"><span data-stu-id="ea688-129">Name of the service principal that initiated the sign-in</span></span>  |
| `ServicePrincipalId`   | <span data-ttu-id="ea688-130">string</span><span class="sxs-lookup"><span data-stu-id="ea688-130">string</span></span>        | <span data-ttu-id="ea688-131">Eindeutiger Bezeichner des Dienstprinzipals, der die Anmeldung initiiert hat</span><span class="sxs-lookup"><span data-stu-id="ea688-131">Unique identifier of the service principal that initiated the sign-in</span></span>  |
| `ResourceDisplayName`  | <span data-ttu-id="ea688-132">string</span><span class="sxs-lookup"><span data-stu-id="ea688-132">string</span></span>        | <span data-ttu-id="ea688-133">Anzeigename der Ressource, auf die zugegriffen wird</span><span class="sxs-lookup"><span data-stu-id="ea688-133">Display name of the resource accessed</span></span>  |
| `ResourceId`           | <span data-ttu-id="ea688-134">string</span><span class="sxs-lookup"><span data-stu-id="ea688-134">string</span></span>        | <span data-ttu-id="ea688-135">Eindeutiger Bezeichner der Ressource, auf die zugegriffen wird</span><span class="sxs-lookup"><span data-stu-id="ea688-135">Unique identifier of the resource accessed</span></span>  |
| `ResourceTenantId`     | <span data-ttu-id="ea688-136">string</span><span class="sxs-lookup"><span data-stu-id="ea688-136">string</span></span>        | <span data-ttu-id="ea688-137">Eindeutiger Bezeichner des Mandanten der Ressource, auf die zugegriffen wird</span><span class="sxs-lookup"><span data-stu-id="ea688-137">Unique identifier of the tenant of the resource accessed</span></span> |
| `IPAddress`            | <span data-ttu-id="ea688-138">string</span><span class="sxs-lookup"><span data-stu-id="ea688-138">string</span></span>        | <span data-ttu-id="ea688-139">Ip-Adresse, die dem Endpunkt zugewiesen und während der zugehörigen Netzwerkkommunikation verwendet wird</span><span class="sxs-lookup"><span data-stu-id="ea688-139">IP address assigned to the endpoint and used during related network communications</span></span>  |
| `Country`          | <span data-ttu-id="ea688-140">string</span><span class="sxs-lookup"><span data-stu-id="ea688-140">string</span></span>        | <span data-ttu-id="ea688-141">Aus zwei Buchstaben bestehender Code, der das Land angibt, in dem die Client-IP-Adresse geolokal ist</span><span class="sxs-lookup"><span data-stu-id="ea688-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `State`                | <span data-ttu-id="ea688-142">string</span><span class="sxs-lookup"><span data-stu-id="ea688-142">string</span></span>        | <span data-ttu-id="ea688-143">Status, in dem die Anmeldung stattgefunden hat, sofern verfügbar</span><span class="sxs-lookup"><span data-stu-id="ea688-143">State where the sign-in occurred, if available</span></span> |
| `City`                 | <span data-ttu-id="ea688-144">string</span><span class="sxs-lookup"><span data-stu-id="ea688-144">string</span></span>        | <span data-ttu-id="ea688-145">Ort, in dem sich der Kontobenutzer befindet</span><span class="sxs-lookup"><span data-stu-id="ea688-145">City where the account user is located</span></span>  |
| `Latitude`             | <span data-ttu-id="ea688-146">string</span><span class="sxs-lookup"><span data-stu-id="ea688-146">string</span></span>        | <span data-ttu-id="ea688-147">Die Nord-Nach-Süd-Koordinaten des Anmeldestandorts</span><span class="sxs-lookup"><span data-stu-id="ea688-147">The north to south coordinates of the sign-in location</span></span> |
| `Longitude`            | <span data-ttu-id="ea688-148">string</span><span class="sxs-lookup"><span data-stu-id="ea688-148">string</span></span>        | <span data-ttu-id="ea688-149">Die Ost-Nach-West-Koordinaten des Anmeldestandorts</span><span class="sxs-lookup"><span data-stu-id="ea688-149">The east to west coordinates of the sign-in location</span></span> |
| `RequestId`            | <span data-ttu-id="ea688-150">string</span><span class="sxs-lookup"><span data-stu-id="ea688-150">string</span></span>        | <span data-ttu-id="ea688-151">Eindeutiger Bezeichner der Anforderung</span><span class="sxs-lookup"><span data-stu-id="ea688-151">Unique identifier of the request</span></span> |
|`ReportId` | <span data-ttu-id="ea688-152">string</span><span class="sxs-lookup"><span data-stu-id="ea688-152">string</span></span> | <span data-ttu-id="ea688-153">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="ea688-153">Unique identifier for the event</span></span> |

 

## <a name="related-articles"></a><span data-ttu-id="ea688-154">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="ea688-154">Related articles</span></span>

-   [<span data-ttu-id="ea688-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="ea688-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="ea688-156">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="ea688-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="ea688-157">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="ea688-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="ea688-158">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="ea688-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
