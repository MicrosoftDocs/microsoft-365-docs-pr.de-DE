---
title: Tabelle "AlertEvidence" im Schema "Erweiterte Suche"
description: Informationen zu Warnungen in der Tabelle "AlertEvidence" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AlertInfo, Warnung, Entitäten, Nachweis, Datei, IP-Adresse, Gerät, Computer, Benutzer, Konto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c01b0aae1eff3d9b4add632aff0f13cb56941a30
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932304"
---
# <a name="alertevidence"></a><span data-ttu-id="6b05d-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="6b05d-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6b05d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6b05d-105">**Applies to:**</span></span>
- <span data-ttu-id="6b05d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b05d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6b05d-107">Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu verschiedenen Entitäten – Dateien, IP-Adressen, URLs, Benutzer oder Geräte – die Warnungen von `AlertEvidence` Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity zugeordnet sind. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6b05d-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="6b05d-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6b05d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6b05d-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6b05d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6b05d-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="6b05d-110">Column name</span></span> | <span data-ttu-id="6b05d-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6b05d-111">Data type</span></span> | <span data-ttu-id="6b05d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b05d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6b05d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="6b05d-113">datetime</span></span> | <span data-ttu-id="6b05d-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="6b05d-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="6b05d-115">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-115">string</span></span> | <span data-ttu-id="6b05d-116">Eindeutiger Bezeichner der Warnung</span><span class="sxs-lookup"><span data-stu-id="6b05d-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="6b05d-117">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-117">string</span></span> | <span data-ttu-id="6b05d-118">Produkt oder Dienst, das die Warnungsinformationen bereitgestellt hat</span><span class="sxs-lookup"><span data-stu-id="6b05d-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="6b05d-119">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-119">string</span></span> | <span data-ttu-id="6b05d-120">Objekttyp, z. B. eine Datei, ein Prozess, ein Gerät oder ein Benutzer</span><span class="sxs-lookup"><span data-stu-id="6b05d-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="6b05d-121">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-121">string</span></span> | <span data-ttu-id="6b05d-122">Wie die Entität an einer Warnung beteiligt ist, die angibt, ob sie betroffen ist oder lediglich in Beziehung steht</span><span class="sxs-lookup"><span data-stu-id="6b05d-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="6b05d-123">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-123">string</span></span> | <span data-ttu-id="6b05d-124">Gibt an, ob die Entität die Quelle oder das Ziel einer Netzwerkverbindung ist.</span><span class="sxs-lookup"><span data-stu-id="6b05d-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="6b05d-125">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-125">string</span></span> | <span data-ttu-id="6b05d-126">Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="6b05d-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="6b05d-127">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-127">string</span></span> | <span data-ttu-id="6b05d-128">Ordner mit der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="6b05d-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="6b05d-129">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-129">string</span></span> | <span data-ttu-id="6b05d-130">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="6b05d-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="6b05d-131">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-131">string</span></span> | <span data-ttu-id="6b05d-132">SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6b05d-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="6b05d-133">Dieses Feld ist in der Regel nicht aufgefüllt– verwenden Sie die SHA1-Spalte, wenn verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6b05d-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="6b05d-134">int</span><span class="sxs-lookup"><span data-stu-id="6b05d-134">int</span></span> | <span data-ttu-id="6b05d-135">Größe der Datei in Byte</span><span class="sxs-lookup"><span data-stu-id="6b05d-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="6b05d-136">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-136">string</span></span> | <span data-ttu-id="6b05d-137">Schadsoftwarefamilie, unter der die verdächtige oder schädliche Datei oder der Prozess klassifiziert wurde</span><span class="sxs-lookup"><span data-stu-id="6b05d-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="6b05d-138">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-138">string</span></span> | <span data-ttu-id="6b05d-139">IP-Adresse, mit der eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="6b05d-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="6b05d-140">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-140">string</span></span> | <span data-ttu-id="6b05d-141">URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="6b05d-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="6b05d-142">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-142">string</span></span> | <span data-ttu-id="6b05d-143">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="6b05d-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="6b05d-144">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-144">string</span></span> | <span data-ttu-id="6b05d-145">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="6b05d-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="6b05d-146">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-146">string</span></span> | <span data-ttu-id="6b05d-147">Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="6b05d-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="6b05d-148">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-148">string</span></span> | <span data-ttu-id="6b05d-149">Eindeutige ID für das Konto in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6b05d-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="6b05d-150">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-150">string</span></span> | <span data-ttu-id="6b05d-151">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="6b05d-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6b05d-152">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-152">string</span></span> | <span data-ttu-id="6b05d-153">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="6b05d-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="6b05d-154">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-154">string</span></span> | <span data-ttu-id="6b05d-155">DIE IP-Adresse, die dem lokalen Gerät zugewiesen ist, das während der Kommunikation verwendet wird</span><span class="sxs-lookup"><span data-stu-id="6b05d-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="6b05d-156">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-156">string</span></span> | <span data-ttu-id="6b05d-157">Eindeutiger Bezeichner für die von Office 365 generierte E-Mail</span><span class="sxs-lookup"><span data-stu-id="6b05d-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="6b05d-158">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-158">string</span></span> | <span data-ttu-id="6b05d-159">Betreff der E-Mail</span><span class="sxs-lookup"><span data-stu-id="6b05d-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="6b05d-160">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-160">string</span></span> | <span data-ttu-id="6b05d-161">Eindeutiger Bezeichner für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="6b05d-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="6b05d-162">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-162">string</span></span> | <span data-ttu-id="6b05d-163">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="6b05d-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="6b05d-164">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-164">string</span></span> | <span data-ttu-id="6b05d-165">Befehlszeile zum Erstellen des neuen Prozesses</span><span class="sxs-lookup"><span data-stu-id="6b05d-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="6b05d-166">string</span><span class="sxs-lookup"><span data-stu-id="6b05d-166">string</span></span> | <span data-ttu-id="6b05d-167">Zusätzliche Informationen zu dem Ereignis im JSON-Array-Format</span><span class="sxs-lookup"><span data-stu-id="6b05d-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6b05d-168">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6b05d-168">Related topics</span></span>
- [<span data-ttu-id="6b05d-169">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="6b05d-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6b05d-170">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="6b05d-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6b05d-171">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="6b05d-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6b05d-172">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="6b05d-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6b05d-173">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="6b05d-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6b05d-174">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="6b05d-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
