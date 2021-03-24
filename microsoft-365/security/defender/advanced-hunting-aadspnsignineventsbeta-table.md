---
title: AADSpnSignInEventsBeta-Tabelle im schema der erweiterten Suche
description: Informationen zu Informationen zum Azure Active Directory-Dienstprinzipal und zur Ereignistabelle für verwaltete Identitäts anmeldungen des erweiterten Schemas für die Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
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
ms.openlocfilehash: 64f3e1d51f94c4cd2578a1d512115aa717c3eaa8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063615"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="93496-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="93496-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="93496-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="93496-105">**Applies to:**</span></span>

- <span data-ttu-id="93496-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93496-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="93496-107">Die Tabelle befindet sich derzeit in der Betaversion und wird kurzfristig angeboten, damit Sie Azure Active Directory (AAD)-Dienstprinzipal- und verwaltete Identitäts-Anmeldeereignisse überprüfen `AADSpnSignInEventsBeta` können.</span><span class="sxs-lookup"><span data-stu-id="93496-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="93496-108">Wir verschieben schließlich alle Anmeldeschemainformationen in die `IdentityLogonEvents` Tabelle.</span><span class="sxs-lookup"><span data-stu-id="93496-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="93496-109">Kunden, die über die integrierte Microsoft Defender for Endpoint-Lösung des Azure Security Centers auf Microsoft 365 Defender zugreifen können, aber keine Lizenzen für Microsoft Defender for Office, Microsoft Defender for Identity oder Microsoft Cloud App Security besitzen, können dieses Schema nicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="93496-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="93496-110">Die Tabelle im Schema der erweiterten Suche `AADSpnSignInEventsBeta` enthält Informationen zu Azure Active Directory-Dienstprinzipal und verwalteten Identitäts-Anmeldungen. Weitere Informationen zu den verschiedenen Arten von Anmeldungen finden Sie in [Azure Active Directory-Anmeldeaktivitätsberichte – Vorschau](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span><span class="sxs-lookup"><span data-stu-id="93496-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="93496-111">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="93496-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="93496-112">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="93496-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="93496-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="93496-113">Column name</span></span>     | <span data-ttu-id="93496-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="93496-114">Data type</span></span> | <span data-ttu-id="93496-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93496-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="93496-116">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="93496-116">datetime</span></span>      | <span data-ttu-id="93496-117">Datum und Uhrzeit, wann der Datensatz generiert wurde</span><span class="sxs-lookup"><span data-stu-id="93496-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="93496-118">string</span><span class="sxs-lookup"><span data-stu-id="93496-118">string</span></span>        | <span data-ttu-id="93496-119">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="93496-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="93496-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-120">string</span></span>        | <span data-ttu-id="93496-121">Eindeutige ID für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="93496-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="93496-122">boolean</span><span class="sxs-lookup"><span data-stu-id="93496-122">boolean</span></span>       | <span data-ttu-id="93496-123">Gibt an, ob die Anmeldung von einer verwalteten Identität initiiert wurde</span><span class="sxs-lookup"><span data-stu-id="93496-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="93496-124">int</span><span class="sxs-lookup"><span data-stu-id="93496-124">int</span></span>        | <span data-ttu-id="93496-125">Enthält den Fehlercode, wenn ein Anmeldefehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="93496-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="93496-126">Eine Beschreibung eines bestimmten Fehlercodes finden Sie unter <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="93496-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="93496-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-127">string</span></span>        | <span data-ttu-id="93496-128">Eindeutiger Bezeichner des Anmeldeereigniss</span><span class="sxs-lookup"><span data-stu-id="93496-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="93496-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-129">string</span></span>        | <span data-ttu-id="93496-130">Name des Dienstprinzipal, der die Anmeldung initiiert hat</span><span class="sxs-lookup"><span data-stu-id="93496-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="93496-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-131">string</span></span>        | <span data-ttu-id="93496-132">Eindeutiger Bezeichner des Dienstprinzipal, der die Anmeldung initiiert hat</span><span class="sxs-lookup"><span data-stu-id="93496-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="93496-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-133">string</span></span>        | <span data-ttu-id="93496-134">Anzeigename der Ressource, auf die zugegriffen wird</span><span class="sxs-lookup"><span data-stu-id="93496-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="93496-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-135">string</span></span>        | <span data-ttu-id="93496-136">Eindeutiger Bezeichner der Ressource, auf die zugegriffen wird</span><span class="sxs-lookup"><span data-stu-id="93496-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="93496-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-137">string</span></span>        | <span data-ttu-id="93496-138">Eindeutiger Bezeichner des Mandanten der Ressource, auf die zugegriffen wird</span><span class="sxs-lookup"><span data-stu-id="93496-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="93496-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-139">string</span></span>        | <span data-ttu-id="93496-140">DEM Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="93496-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="93496-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-141">string</span></span>        | <span data-ttu-id="93496-142">Zwei-Buchstaben-Code, der das Land angibt, in dem die Client-IP-Adresse geolokaliert ist</span><span class="sxs-lookup"><span data-stu-id="93496-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="93496-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-143">string</span></span>        | <span data-ttu-id="93496-144">Status, in dem die Anmeldung erfolgt ist( sofern verfügbar)</span><span class="sxs-lookup"><span data-stu-id="93496-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="93496-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-145">string</span></span>        | <span data-ttu-id="93496-146">Ort, in dem sich der Kontobenutzer befindet</span><span class="sxs-lookup"><span data-stu-id="93496-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="93496-147">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-147">string</span></span>        | <span data-ttu-id="93496-148">Die Nord-Süd-Koordinaten des Anmeldestandorts</span><span class="sxs-lookup"><span data-stu-id="93496-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="93496-149">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-149">string</span></span>        | <span data-ttu-id="93496-150">Die Ost-West-Koordinaten der Anmeldeposition</span><span class="sxs-lookup"><span data-stu-id="93496-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="93496-151">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-151">string</span></span>        | <span data-ttu-id="93496-152">Eindeutiger Bezeichner der Anforderung</span><span class="sxs-lookup"><span data-stu-id="93496-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="93496-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="93496-153">string</span></span> | <span data-ttu-id="93496-154">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="93496-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="93496-155">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="93496-155">Related articles</span></span>

-   [<span data-ttu-id="93496-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="93496-156">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="93496-157">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="93496-157">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="93496-158">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="93496-158">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="93496-159">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="93496-159">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)