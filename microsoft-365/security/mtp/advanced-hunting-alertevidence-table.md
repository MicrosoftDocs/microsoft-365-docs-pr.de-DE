---
title: AlertEvidence-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über Datei-, Netzwerkadresse, Benutzer-oder Geräteinformationen, die mit generierten Warnungen in der AlertEvidence-Tabelle des Advanced Hunting-Schemas verknüpft sind.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, alertinfo, Warnung, Entitäten, Evidence, File, IP-Adresse, Gerät, Computer, Benutzer, Konto
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
ms.openlocfilehash: 8fc713db33b0e40adcd0975d26c10daece636ab1
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649511"
---
# <a name="alertevidence"></a><span data-ttu-id="98ca0-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="98ca0-104">AlertEvidence</span></span>

<span data-ttu-id="98ca0-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="98ca0-105">**Applies to:**</span></span>
- <span data-ttu-id="98ca0-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="98ca0-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="98ca0-107">Die `AlertEvidence` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu verschiedenen Entitäten – Dateien, IP-Adressen, URLs, Benutzer oder Geräte –, die Warnungen von Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security und Azure ATP zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="98ca0-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="98ca0-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="98ca0-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="98ca0-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="98ca0-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="98ca0-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="98ca0-110">Column name</span></span> | <span data-ttu-id="98ca0-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="98ca0-111">Data type</span></span> | <span data-ttu-id="98ca0-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98ca0-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="98ca0-113">datetime</span><span class="sxs-lookup"><span data-stu-id="98ca0-113">datetime</span></span> | <span data-ttu-id="98ca0-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="98ca0-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="98ca0-115">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-115">string</span></span> | <span data-ttu-id="98ca0-116">Eindeutiger Bezeichner der Warnung</span><span class="sxs-lookup"><span data-stu-id="98ca0-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="98ca0-117">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-117">string</span></span> | <span data-ttu-id="98ca0-118">Objekttyp, beispielsweise eine Datei, ein Prozess, ein Gerät oder ein Benutzer</span><span class="sxs-lookup"><span data-stu-id="98ca0-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="98ca0-119">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-119">string</span></span> | <span data-ttu-id="98ca0-120">Wie die Entität an einer Warnung beteiligt ist und angibt, ob Sie betroffen ist oder lediglich mit ihr zusammenhängen soll</span><span class="sxs-lookup"><span data-stu-id="98ca0-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="98ca0-121">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-121">string</span></span> | <span data-ttu-id="98ca0-122">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="98ca0-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="98ca0-123">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-123">string</span></span> | <span data-ttu-id="98ca0-124">SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="98ca0-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="98ca0-125">Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar.</span><span class="sxs-lookup"><span data-stu-id="98ca0-125">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="98ca0-126">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-126">string</span></span> | <span data-ttu-id="98ca0-127">IP-Adresse, mit der eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="98ca0-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="98ca0-128">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-128">string</span></span> | <span data-ttu-id="98ca0-129">URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="98ca0-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="98ca0-130">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-130">string</span></span> | <span data-ttu-id="98ca0-131">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="98ca0-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="98ca0-132">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-132">string</span></span> | <span data-ttu-id="98ca0-133">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="98ca0-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="98ca0-134">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-134">string</span></span> | <span data-ttu-id="98ca0-135">Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="98ca0-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="98ca0-136">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-136">string</span></span> | <span data-ttu-id="98ca0-137">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="98ca0-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="98ca0-138">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-138">string</span></span> | <span data-ttu-id="98ca0-139">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="98ca0-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="98ca0-140">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-140">string</span></span> | <span data-ttu-id="98ca0-141">Schadsoftware-Familie, unter der die verdächtige oder böswillige Datei oder der Prozess klassifiziert wurde</span><span class="sxs-lookup"><span data-stu-id="98ca0-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="98ca0-142">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-142">string</span></span> | <span data-ttu-id="98ca0-143">Gibt an, ob es sich bei der Entität um die Quelle oder das Ziel einer Netzwerkverbindung handelt.</span><span class="sxs-lookup"><span data-stu-id="98ca0-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="98ca0-144">string</span><span class="sxs-lookup"><span data-stu-id="98ca0-144">string</span></span> | <span data-ttu-id="98ca0-145">Weitere Informationen zum Ereignis im JSON-Array Format</span><span class="sxs-lookup"><span data-stu-id="98ca0-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="98ca0-146">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="98ca0-146">Related topics</span></span>
- [<span data-ttu-id="98ca0-147">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="98ca0-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="98ca0-148">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="98ca0-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="98ca0-149">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="98ca0-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="98ca0-150">Jagd auf Geräte, e-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="98ca0-150">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="98ca0-151">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="98ca0-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="98ca0-152">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="98ca0-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
