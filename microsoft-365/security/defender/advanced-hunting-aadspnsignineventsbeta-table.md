---
title: AADSpnSignInEventsBeta-Tabelle im schema der erweiterten Suche
description: Informationen zu Informationen, die Azure Active Directory Dienstprinzipal und der Ereignistabelle für verwaltete Identitätsidentitätsereignisse des erweiterten Schemas für die Suche zugeordnet sind
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
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
ms.openlocfilehash: f74972bcd5d0ddaab58d82b72a55991fda44e3b1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583544"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="0ec47-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="0ec47-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="0ec47-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0ec47-105">**Applies to:**</span></span>

- <span data-ttu-id="0ec47-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ec47-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="0ec47-107">Die Tabelle befindet sich derzeit in der Betaversion und wird kurzfristig angeboten, um die Suche durch Azure Active Directory (AAD)-Dienstprinzipal- und verwaltete Identitäts-Anmeldeereignisse `AADSpnSignInEventsBeta` zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0ec47-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="0ec47-108">Wir verschieben schließlich alle Anmeldeschemainformationen in die `IdentityLogonEvents` Tabelle.</span><span class="sxs-lookup"><span data-stu-id="0ec47-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="0ec47-109">Die Tabelle im Schema der erweiterten Suche enthält Informationen Azure Active Directory `AADSpnSignInEventsBeta` Dienstprinzipal und verwaltete Identitäts-Anmeldungen. Weitere Informationen zu den verschiedenen Arten von Anmeldungen finden Sie in Azure Active Directory [- Vorschau](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span><span class="sxs-lookup"><span data-stu-id="0ec47-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="0ec47-110">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0ec47-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="0ec47-111">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="0ec47-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="0ec47-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0ec47-112">Column name</span></span>     | <span data-ttu-id="0ec47-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="0ec47-113">Data type</span></span> | <span data-ttu-id="0ec47-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ec47-114">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="0ec47-115">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="0ec47-115">datetime</span></span>      | <span data-ttu-id="0ec47-116">Datum und Uhrzeit, wann der Datensatz generiert wurde</span><span class="sxs-lookup"><span data-stu-id="0ec47-116">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="0ec47-117">string</span><span class="sxs-lookup"><span data-stu-id="0ec47-117">string</span></span>        | <span data-ttu-id="0ec47-118">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="0ec47-118">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="0ec47-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-119">string</span></span>        | <span data-ttu-id="0ec47-120">Eindeutige ID für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="0ec47-120">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="0ec47-121">boolean</span><span class="sxs-lookup"><span data-stu-id="0ec47-121">boolean</span></span>       | <span data-ttu-id="0ec47-122">Gibt an, ob die Anmeldung von einer verwalteten Identität initiiert wurde</span><span class="sxs-lookup"><span data-stu-id="0ec47-122">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="0ec47-123">int</span><span class="sxs-lookup"><span data-stu-id="0ec47-123">int</span></span>        | <span data-ttu-id="0ec47-124">Enthält den Fehlercode, wenn ein Anmeldefehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="0ec47-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="0ec47-125">Eine Beschreibung eines bestimmten Fehlercodes finden Sie unter <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="0ec47-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="0ec47-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-126">string</span></span>        | <span data-ttu-id="0ec47-127">Eindeutiger Bezeichner des Anmeldeereigniss</span><span class="sxs-lookup"><span data-stu-id="0ec47-127">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="0ec47-128">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-128">string</span></span>        | <span data-ttu-id="0ec47-129">Name des Dienstprinzipal, der die Anmeldung initiiert hat</span><span class="sxs-lookup"><span data-stu-id="0ec47-129">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="0ec47-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-130">string</span></span>        | <span data-ttu-id="0ec47-131">Eindeutiger Bezeichner des Dienstprinzipal, der die Anmeldung initiiert hat</span><span class="sxs-lookup"><span data-stu-id="0ec47-131">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="0ec47-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-132">string</span></span>        | <span data-ttu-id="0ec47-133">Anzeigename der Ressource, auf die zugegriffen wird</span><span class="sxs-lookup"><span data-stu-id="0ec47-133">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="0ec47-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-134">string</span></span>        | <span data-ttu-id="0ec47-135">Eindeutiger Bezeichner der Ressource, auf die zugegriffen wird</span><span class="sxs-lookup"><span data-stu-id="0ec47-135">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="0ec47-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-136">string</span></span>        | <span data-ttu-id="0ec47-137">Eindeutiger Bezeichner des Mandanten der Ressource, auf die zugegriffen wird</span><span class="sxs-lookup"><span data-stu-id="0ec47-137">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="0ec47-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-138">string</span></span>        | <span data-ttu-id="0ec47-139">DEM Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="0ec47-139">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="0ec47-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-140">string</span></span>        | <span data-ttu-id="0ec47-141">Zwei-Buchstaben-Code, der das Land angibt, in dem die Client-IP-Adresse geolokaliert ist</span><span class="sxs-lookup"><span data-stu-id="0ec47-141">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="0ec47-142">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-142">string</span></span>        | <span data-ttu-id="0ec47-143">Status, in dem die Anmeldung erfolgt ist( sofern verfügbar)</span><span class="sxs-lookup"><span data-stu-id="0ec47-143">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="0ec47-144">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-144">string</span></span>        | <span data-ttu-id="0ec47-145">Ort, in dem sich der Kontobenutzer befindet</span><span class="sxs-lookup"><span data-stu-id="0ec47-145">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="0ec47-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-146">string</span></span>        | <span data-ttu-id="0ec47-147">Die Nord-Süd-Koordinaten des Anmeldestandorts</span><span class="sxs-lookup"><span data-stu-id="0ec47-147">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="0ec47-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-148">string</span></span>        | <span data-ttu-id="0ec47-149">Die Ost-West-Koordinaten der Anmeldeposition</span><span class="sxs-lookup"><span data-stu-id="0ec47-149">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="0ec47-150">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-150">string</span></span>        | <span data-ttu-id="0ec47-151">Eindeutiger Bezeichner der Anforderung</span><span class="sxs-lookup"><span data-stu-id="0ec47-151">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="0ec47-152">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0ec47-152">string</span></span> | <span data-ttu-id="0ec47-153">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="0ec47-153">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="0ec47-154">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="0ec47-154">Related articles</span></span>

-   [<span data-ttu-id="0ec47-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="0ec47-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="0ec47-156">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="0ec47-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="0ec47-157">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="0ec47-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="0ec47-158">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="0ec47-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)