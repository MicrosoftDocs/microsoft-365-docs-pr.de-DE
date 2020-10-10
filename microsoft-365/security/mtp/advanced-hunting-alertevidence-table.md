---
title: AlertEvidence-Tabelle im Advanced Hunting-Schema
description: Informationen zu den Warnungen in der AlertEvidence-Tabelle des erweiterten Jagd Schemas finden Sie hier.
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ec6fe3d080efb396ce0ecacadd3d5d9a8fa9f8d1
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413198"
---
# <a name="alertevidence"></a><span data-ttu-id="c7154-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="c7154-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c7154-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c7154-105">**Applies to:**</span></span>
- <span data-ttu-id="c7154-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c7154-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c7154-107">Die `AlertEvidence` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu verschiedenen Entitäten – Dateien, IP-Adressen, URLs, Benutzer oder Geräte –, die Warnungen von Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security und Azure ATP zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c7154-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="c7154-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c7154-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c7154-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c7154-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c7154-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c7154-110">Column name</span></span> | <span data-ttu-id="c7154-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c7154-111">Data type</span></span> | <span data-ttu-id="c7154-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7154-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c7154-113">datetime</span><span class="sxs-lookup"><span data-stu-id="c7154-113">datetime</span></span> | <span data-ttu-id="c7154-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="c7154-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="c7154-115">string</span><span class="sxs-lookup"><span data-stu-id="c7154-115">string</span></span> | <span data-ttu-id="c7154-116">Eindeutiger Bezeichner der Warnung</span><span class="sxs-lookup"><span data-stu-id="c7154-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="c7154-117">string</span><span class="sxs-lookup"><span data-stu-id="c7154-117">string</span></span> | <span data-ttu-id="c7154-118">Produkt oder Dienst, der die Warnungsinformationen bereitgestellt hat</span><span class="sxs-lookup"><span data-stu-id="c7154-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="c7154-119">string</span><span class="sxs-lookup"><span data-stu-id="c7154-119">string</span></span> | <span data-ttu-id="c7154-120">Objekttyp, beispielsweise eine Datei, ein Prozess, ein Gerät oder ein Benutzer</span><span class="sxs-lookup"><span data-stu-id="c7154-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="c7154-121">string</span><span class="sxs-lookup"><span data-stu-id="c7154-121">string</span></span> | <span data-ttu-id="c7154-122">Wie die Entität an einer Warnung beteiligt ist und angibt, ob Sie betroffen ist oder lediglich mit ihr zusammenhängen soll</span><span class="sxs-lookup"><span data-stu-id="c7154-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="c7154-123">string</span><span class="sxs-lookup"><span data-stu-id="c7154-123">string</span></span> | <span data-ttu-id="c7154-124">Gibt an, ob es sich bei der Entität um die Quelle oder das Ziel einer Netzwerkverbindung handelt.</span><span class="sxs-lookup"><span data-stu-id="c7154-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="c7154-125">string</span><span class="sxs-lookup"><span data-stu-id="c7154-125">string</span></span> | <span data-ttu-id="c7154-126">Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="c7154-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="c7154-127">string</span><span class="sxs-lookup"><span data-stu-id="c7154-127">string</span></span> | <span data-ttu-id="c7154-128">Ordner mit der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="c7154-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="c7154-129">string</span><span class="sxs-lookup"><span data-stu-id="c7154-129">string</span></span> | <span data-ttu-id="c7154-130">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="c7154-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="c7154-131">string</span><span class="sxs-lookup"><span data-stu-id="c7154-131">string</span></span> | <span data-ttu-id="c7154-132">SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c7154-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="c7154-133">Dieses Feld wird in der Regel nicht aufgefüllt, wenn es verfügbar ist, verwenden Sie die SHA1-Spalte.</span><span class="sxs-lookup"><span data-stu-id="c7154-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="c7154-134">int</span><span class="sxs-lookup"><span data-stu-id="c7154-134">int</span></span> | <span data-ttu-id="c7154-135">Größe der Datei in Bytes</span><span class="sxs-lookup"><span data-stu-id="c7154-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="c7154-136">string</span><span class="sxs-lookup"><span data-stu-id="c7154-136">string</span></span> | <span data-ttu-id="c7154-137">Schadsoftware-Familie, unter der die verdächtige oder böswillige Datei oder der Prozess klassifiziert wurde</span><span class="sxs-lookup"><span data-stu-id="c7154-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="c7154-138">string</span><span class="sxs-lookup"><span data-stu-id="c7154-138">string</span></span> | <span data-ttu-id="c7154-139">IP-Adresse, mit der eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="c7154-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="c7154-140">string</span><span class="sxs-lookup"><span data-stu-id="c7154-140">string</span></span> | <span data-ttu-id="c7154-141">URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="c7154-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="c7154-142">string</span><span class="sxs-lookup"><span data-stu-id="c7154-142">string</span></span> | <span data-ttu-id="c7154-143">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="c7154-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="c7154-144">string</span><span class="sxs-lookup"><span data-stu-id="c7154-144">string</span></span> | <span data-ttu-id="c7154-145">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="c7154-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="c7154-146">string</span><span class="sxs-lookup"><span data-stu-id="c7154-146">string</span></span> | <span data-ttu-id="c7154-147">Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="c7154-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="c7154-148">string</span><span class="sxs-lookup"><span data-stu-id="c7154-148">string</span></span> | <span data-ttu-id="c7154-149">Eindeutiger Bezeichner für das Konto in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c7154-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="c7154-150">string</span><span class="sxs-lookup"><span data-stu-id="c7154-150">string</span></span> | <span data-ttu-id="c7154-151">Eindeutiger Bezeichner für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="c7154-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c7154-152">string</span><span class="sxs-lookup"><span data-stu-id="c7154-152">string</span></span> | <span data-ttu-id="c7154-153">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="c7154-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="c7154-154">string</span><span class="sxs-lookup"><span data-stu-id="c7154-154">string</span></span> | <span data-ttu-id="c7154-155">IP-Adresse, die dem lokalen Gerät zugewiesen ist, das während der Kommunikation verwendet wird</span><span class="sxs-lookup"><span data-stu-id="c7154-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="c7154-156">string</span><span class="sxs-lookup"><span data-stu-id="c7154-156">string</span></span> | <span data-ttu-id="c7154-157">Eindeutiger Bezeichner für die von Office 365 generierte E-Mail</span><span class="sxs-lookup"><span data-stu-id="c7154-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="c7154-158">string</span><span class="sxs-lookup"><span data-stu-id="c7154-158">string</span></span> | <span data-ttu-id="c7154-159">Betreff der E-Mail</span><span class="sxs-lookup"><span data-stu-id="c7154-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="c7154-160">string</span><span class="sxs-lookup"><span data-stu-id="c7154-160">string</span></span> | <span data-ttu-id="c7154-161">Eindeutiger Bezeichner für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="c7154-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="c7154-162">string</span><span class="sxs-lookup"><span data-stu-id="c7154-162">string</span></span> | <span data-ttu-id="c7154-163">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="c7154-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="c7154-164">string</span><span class="sxs-lookup"><span data-stu-id="c7154-164">string</span></span> | <span data-ttu-id="c7154-165">Befehlszeile, die zum Erstellen des neuen Prozesses verwendet wird</span><span class="sxs-lookup"><span data-stu-id="c7154-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="c7154-166">string</span><span class="sxs-lookup"><span data-stu-id="c7154-166">string</span></span> | <span data-ttu-id="c7154-167">Weitere Informationen zum Ereignis im JSON-Array Format</span><span class="sxs-lookup"><span data-stu-id="c7154-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c7154-168">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c7154-168">Related topics</span></span>
- [<span data-ttu-id="c7154-169">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="c7154-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c7154-170">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="c7154-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c7154-171">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="c7154-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c7154-172">Suchen auf Geräten, in E-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="c7154-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c7154-173">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="c7154-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c7154-174">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="c7154-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
