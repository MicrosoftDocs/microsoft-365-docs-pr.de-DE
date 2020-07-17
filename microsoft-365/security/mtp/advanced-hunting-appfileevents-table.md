---
title: AppFileEvents-Tabelle im Advanced Hunting-Schema
description: Informationen zu dateibezogenen Ereignissen im Zusammenhang mit Cloud-apps und-Diensten in der AppFileEvents-Tabelle des Advanced Hunting-Schemas
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AppFileEvents, Cloud-App-Sicherheit, MCAS
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
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899339"
---
# <a name="appfileevents"></a><span data-ttu-id="49bfa-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="49bfa-104">AppFileEvents</span></span>

<span data-ttu-id="49bfa-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="49bfa-105">**Applies to:**</span></span>
- <span data-ttu-id="49bfa-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="49bfa-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="49bfa-107">Die `AppFileEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu dateibezogenen Aktivitäten in Cloud-apps und-Diensten, die von Microsoft Cloud App Security überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="49bfa-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="49bfa-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="49bfa-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="49bfa-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="49bfa-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="49bfa-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="49bfa-110">Column name</span></span> | <span data-ttu-id="49bfa-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="49bfa-111">Data type</span></span> | <span data-ttu-id="49bfa-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49bfa-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="49bfa-113">datetime</span><span class="sxs-lookup"><span data-stu-id="49bfa-113">datetime</span></span> | <span data-ttu-id="49bfa-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="49bfa-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="49bfa-115">string</span><span class="sxs-lookup"><span data-stu-id="49bfa-115">string</span></span> | <span data-ttu-id="49bfa-116">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="49bfa-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="49bfa-117">string</span><span class="sxs-lookup"><span data-stu-id="49bfa-117">string</span></span> | <span data-ttu-id="49bfa-118">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="49bfa-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="49bfa-119">string</span><span class="sxs-lookup"><span data-stu-id="49bfa-119">string</span></span> | <span data-ttu-id="49bfa-120">Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="49bfa-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="49bfa-121">string</span><span class="sxs-lookup"><span data-stu-id="49bfa-121">string</span></span> | <span data-ttu-id="49bfa-122">Ordner mit der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="49bfa-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="49bfa-123">string</span><span class="sxs-lookup"><span data-stu-id="49bfa-123">string</span></span> | <span data-ttu-id="49bfa-124">Ursprünglicher Name der Datei, die als Ergebnis der Aktion umbenannt wurde</span><span class="sxs-lookup"><span data-stu-id="49bfa-124">Original name of the file that was renamed as a result of the action</span></span> |
| `AccountName` | <span data-ttu-id="49bfa-125">string</span><span class="sxs-lookup"><span data-stu-id="49bfa-125">string</span></span> | <span data-ttu-id="49bfa-126">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="49bfa-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="49bfa-127">string</span><span class="sxs-lookup"><span data-stu-id="49bfa-127">string</span></span> | <span data-ttu-id="49bfa-128">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="49bfa-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="49bfa-129">string</span><span class="sxs-lookup"><span data-stu-id="49bfa-129">string</span></span> | <span data-ttu-id="49bfa-130">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="49bfa-130">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="49bfa-131">string</span><span class="sxs-lookup"><span data-stu-id="49bfa-131">string</span></span> | <span data-ttu-id="49bfa-132">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="49bfa-132">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="49bfa-133">string</span><span class="sxs-lookup"><span data-stu-id="49bfa-133">string</span></span> | <span data-ttu-id="49bfa-134">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="49bfa-134">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="49bfa-135">Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="49bfa-135">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IPAddress` | <span data-ttu-id="49bfa-136">string</span><span class="sxs-lookup"><span data-stu-id="49bfa-136">string</span></span> | <span data-ttu-id="49bfa-137">Dem Endpunkt zugewiesene IP-Adresse und wird während der zugehörigen Netzwerkkommunikation verwendet</span><span class="sxs-lookup"><span data-stu-id="49bfa-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="49bfa-138">string</span><span class="sxs-lookup"><span data-stu-id="49bfa-138">string</span></span> | <span data-ttu-id="49bfa-139">Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="49bfa-139">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="49bfa-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="49bfa-140">Related topics</span></span>
- [<span data-ttu-id="49bfa-141">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="49bfa-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="49bfa-142">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="49bfa-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="49bfa-143">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="49bfa-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="49bfa-144">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="49bfa-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="49bfa-145">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="49bfa-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="49bfa-146">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="49bfa-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
