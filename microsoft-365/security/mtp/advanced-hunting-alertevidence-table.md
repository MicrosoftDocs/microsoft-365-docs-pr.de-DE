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
ms.openlocfilehash: 1a58d1e5db2ea8689d4909e6e9c47b08a6e94d34
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929146"
---
# <a name="alertevidence"></a><span data-ttu-id="df55b-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="df55b-104">AlertEvidence</span></span>

<span data-ttu-id="df55b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="df55b-105">**Applies to:**</span></span>
- <span data-ttu-id="df55b-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="df55b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="df55b-107">Die `AlertEvidence` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu verschiedenen Entitäten – Dateien, IP-Adressen, URLs, Benutzer oder Geräte –, die Warnungen von Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security und Azure ATP zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="df55b-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="df55b-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="df55b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="df55b-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="df55b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="df55b-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="df55b-110">Column name</span></span> | <span data-ttu-id="df55b-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="df55b-111">Data type</span></span> | <span data-ttu-id="df55b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df55b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="df55b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="df55b-113">datetime</span></span> | <span data-ttu-id="df55b-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="df55b-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="df55b-115">string</span><span class="sxs-lookup"><span data-stu-id="df55b-115">string</span></span> | <span data-ttu-id="df55b-116">Eindeutiger Bezeichner der Warnung</span><span class="sxs-lookup"><span data-stu-id="df55b-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="df55b-117">string</span><span class="sxs-lookup"><span data-stu-id="df55b-117">string</span></span> | <span data-ttu-id="df55b-118">Objekttyp, beispielsweise eine Datei, ein Prozess, ein Gerät oder ein Benutzer</span><span class="sxs-lookup"><span data-stu-id="df55b-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="df55b-119">string</span><span class="sxs-lookup"><span data-stu-id="df55b-119">string</span></span> | <span data-ttu-id="df55b-120">Wie die Entität an einer Warnung beteiligt ist und angibt, ob Sie betroffen ist oder lediglich mit ihr zusammenhängen soll</span><span class="sxs-lookup"><span data-stu-id="df55b-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="df55b-121">string</span><span class="sxs-lookup"><span data-stu-id="df55b-121">string</span></span> | <span data-ttu-id="df55b-122">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="df55b-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="df55b-123">string</span><span class="sxs-lookup"><span data-stu-id="df55b-123">string</span></span> | <span data-ttu-id="df55b-124">SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="df55b-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="df55b-125">Dieses Feld wird in der Regel nicht aufgefüllt, wenn es verfügbar ist, verwenden Sie die SHA1-Spalte.</span><span class="sxs-lookup"><span data-stu-id="df55b-125">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="df55b-126">string</span><span class="sxs-lookup"><span data-stu-id="df55b-126">string</span></span> | <span data-ttu-id="df55b-127">IP-Adresse, mit der eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="df55b-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="df55b-128">string</span><span class="sxs-lookup"><span data-stu-id="df55b-128">string</span></span> | <span data-ttu-id="df55b-129">URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="df55b-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="df55b-130">string</span><span class="sxs-lookup"><span data-stu-id="df55b-130">string</span></span> | <span data-ttu-id="df55b-131">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="df55b-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="df55b-132">string</span><span class="sxs-lookup"><span data-stu-id="df55b-132">string</span></span> | <span data-ttu-id="df55b-133">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="df55b-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="df55b-134">string</span><span class="sxs-lookup"><span data-stu-id="df55b-134">string</span></span> | <span data-ttu-id="df55b-135">Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="df55b-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="df55b-136">string</span><span class="sxs-lookup"><span data-stu-id="df55b-136">string</span></span> | <span data-ttu-id="df55b-137">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="df55b-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="df55b-138">string</span><span class="sxs-lookup"><span data-stu-id="df55b-138">string</span></span> | <span data-ttu-id="df55b-139">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="df55b-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="df55b-140">string</span><span class="sxs-lookup"><span data-stu-id="df55b-140">string</span></span> | <span data-ttu-id="df55b-141">Schadsoftware-Familie, unter der die verdächtige oder böswillige Datei oder der Prozess klassifiziert wurde</span><span class="sxs-lookup"><span data-stu-id="df55b-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="df55b-142">string</span><span class="sxs-lookup"><span data-stu-id="df55b-142">string</span></span> | <span data-ttu-id="df55b-143">Gibt an, ob es sich bei der Entität um die Quelle oder das Ziel einer Netzwerkverbindung handelt.</span><span class="sxs-lookup"><span data-stu-id="df55b-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="df55b-144">string</span><span class="sxs-lookup"><span data-stu-id="df55b-144">string</span></span> | <span data-ttu-id="df55b-145">Weitere Informationen zum Ereignis im JSON-Array Format</span><span class="sxs-lookup"><span data-stu-id="df55b-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="df55b-146">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="df55b-146">Related topics</span></span>
- [<span data-ttu-id="df55b-147">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="df55b-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="df55b-148">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="df55b-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="df55b-149">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="df55b-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="df55b-150">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="df55b-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="df55b-151">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="df55b-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="df55b-152">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="df55b-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
