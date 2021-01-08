---
title: Tabelle "AADSpnSignInEventsBeta" im Schema "Erweiterte Suche"
description: Informationen zu Informationen zu Azure Active Directory-Dienstprinzipal- und verwalteten Identitäts-Anmeldeereignissen– Tabelle des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AlertInfo, Warnung, Entitäten, Nachweis, Datei, IP-Adresse, Gerät, Computer, Benutzer, Konto, Identität, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 42acf24ce9b941fffb1ce0ed4b67216bd8c1de47
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784299"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="3e206-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="3e206-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="3e206-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3e206-105">**Applies to:**</span></span>

- <span data-ttu-id="3e206-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3e206-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="3e206-107">Die Tabelle befindet sich derzeit in der Betaversion und wird kurzfristig angeboten, damit Sie durch Azure Active Directory (AAD)-Dienstprinzipal- und verwaltete Identitäts-Anmeldeereignisse suchen `AADSpnSignInEventsBeta` können.</span><span class="sxs-lookup"><span data-stu-id="3e206-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="3e206-108">Schließlich werden wir alle Anmeldeschemainformationen in die Tabelle `IdentityLogonEvents` verschieben.</span><span class="sxs-lookup"><span data-stu-id="3e206-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="3e206-109">Kunden, die über die integrierte Microsoft Defender for Endpoint-Lösung des Azure Security Center auf Microsoft 365 Defender zugreifen können, aber nicht über Lizenzen für Microsoft Defender für Office, Microsoft Defender for Identity oder Microsoft Cloud App Security verfügen, können dieses Schema nicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3e206-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="3e206-110">Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Azure Active Directory-Dienstprinzipal- und `AADSpnSignInEventsBeta` verwalteten Identitäts-Anmeldungen. Weitere Informationen zu den verschiedenen Arten von Anmeldungen finden Sie in Azure Active Directory-Anmeldeaktivitätsberichten [– Vorschau.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="3e206-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="3e206-111">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="3e206-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="3e206-112">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="3e206-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="3e206-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3e206-113">Column name</span></span>     | <span data-ttu-id="3e206-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="3e206-114">Data type</span></span> | <span data-ttu-id="3e206-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e206-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="3e206-116">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="3e206-116">datetime</span></span>      | <span data-ttu-id="3e206-117">Datum und Uhrzeit, wann der Datensatz generiert wurde</span><span class="sxs-lookup"><span data-stu-id="3e206-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="3e206-118">string</span><span class="sxs-lookup"><span data-stu-id="3e206-118">string</span></span>        | <span data-ttu-id="3e206-119">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="3e206-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="3e206-120">string</span><span class="sxs-lookup"><span data-stu-id="3e206-120">string</span></span>        | <span data-ttu-id="3e206-121">Eindeutiger Bezeichner für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="3e206-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="3e206-122">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="3e206-122">boolean</span></span>       | <span data-ttu-id="3e206-123">Gibt an, ob die Anmeldung von einer verwalteten Identität initiiert wurde</span><span class="sxs-lookup"><span data-stu-id="3e206-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="3e206-124">int</span><span class="sxs-lookup"><span data-stu-id="3e206-124">int</span></span>        | <span data-ttu-id="3e206-125">Enthält den Fehlercode, wenn ein Anmeldefehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="3e206-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="3e206-126">Eine Beschreibung eines bestimmten Fehlercodes finden Sie unter <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="3e206-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="3e206-127">string</span><span class="sxs-lookup"><span data-stu-id="3e206-127">string</span></span>        | <span data-ttu-id="3e206-128">Eindeutiger Bezeichner des Anmeldeereigniss</span><span class="sxs-lookup"><span data-stu-id="3e206-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="3e206-129">string</span><span class="sxs-lookup"><span data-stu-id="3e206-129">string</span></span>        | <span data-ttu-id="3e206-130">Name des Dienstprinzipal, der die Anmeldung initiiert hat</span><span class="sxs-lookup"><span data-stu-id="3e206-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="3e206-131">string</span><span class="sxs-lookup"><span data-stu-id="3e206-131">string</span></span>        | <span data-ttu-id="3e206-132">Eindeutiger Bezeichner des Dienstprinzipal, der die Anmeldung initiiert hat</span><span class="sxs-lookup"><span data-stu-id="3e206-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="3e206-133">string</span><span class="sxs-lookup"><span data-stu-id="3e206-133">string</span></span>        | <span data-ttu-id="3e206-134">Anzeigename der Ressource, auf die zugegriffen wird</span><span class="sxs-lookup"><span data-stu-id="3e206-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="3e206-135">string</span><span class="sxs-lookup"><span data-stu-id="3e206-135">string</span></span>        | <span data-ttu-id="3e206-136">Eindeutiger Bezeichner der Ressource, auf die zugegriffen wird</span><span class="sxs-lookup"><span data-stu-id="3e206-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="3e206-137">string</span><span class="sxs-lookup"><span data-stu-id="3e206-137">string</span></span>        | <span data-ttu-id="3e206-138">Eindeutiger Bezeichner des Mandanten der Ressource, auf die zugegriffen wird</span><span class="sxs-lookup"><span data-stu-id="3e206-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="3e206-139">string</span><span class="sxs-lookup"><span data-stu-id="3e206-139">string</span></span>        | <span data-ttu-id="3e206-140">Dem Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="3e206-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `CountryCode`          | <span data-ttu-id="3e206-141">string</span><span class="sxs-lookup"><span data-stu-id="3e206-141">string</span></span>        | <span data-ttu-id="3e206-142">Aus zwei Buchstaben bestehter Code, der das Land angibt, in dem die Client-IP-Adresse geolokaliert ist</span><span class="sxs-lookup"><span data-stu-id="3e206-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="3e206-143">string</span><span class="sxs-lookup"><span data-stu-id="3e206-143">string</span></span>        | <span data-ttu-id="3e206-144">Status, in dem die Anmeldung erfolgt ist( sofern verfügbar)</span><span class="sxs-lookup"><span data-stu-id="3e206-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="3e206-145">string</span><span class="sxs-lookup"><span data-stu-id="3e206-145">string</span></span>        | <span data-ttu-id="3e206-146">Ort, in dem sich der Kontobenutzer befindet</span><span class="sxs-lookup"><span data-stu-id="3e206-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="3e206-147">string</span><span class="sxs-lookup"><span data-stu-id="3e206-147">string</span></span>        | <span data-ttu-id="3e206-148">Die Koordinaten von Nord nach Süd des Anmeldestandorts</span><span class="sxs-lookup"><span data-stu-id="3e206-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="3e206-149">string</span><span class="sxs-lookup"><span data-stu-id="3e206-149">string</span></span>        | <span data-ttu-id="3e206-150">Die Ost-West-Koordinaten des Anmeldestandorts</span><span class="sxs-lookup"><span data-stu-id="3e206-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="3e206-151">string</span><span class="sxs-lookup"><span data-stu-id="3e206-151">string</span></span>        | <span data-ttu-id="3e206-152">Eindeutiger Bezeichner der Anforderung</span><span class="sxs-lookup"><span data-stu-id="3e206-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="3e206-153">string</span><span class="sxs-lookup"><span data-stu-id="3e206-153">string</span></span> | <span data-ttu-id="3e206-154">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="3e206-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="3e206-155">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="3e206-155">Related articles</span></span>

-   [<span data-ttu-id="3e206-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="3e206-156">AADSignInEventsBeta</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [<span data-ttu-id="3e206-157">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="3e206-157">Advanced hunting overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="3e206-158">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="3e206-158">Learn the query language</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="3e206-159">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="3e206-159">Understand the schema</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

