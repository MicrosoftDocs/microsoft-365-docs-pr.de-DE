---
title: FileProfile()-Funktion bei der erweiterten Suche für Microsoft 365 Defender
description: Erfahren Sie, wie Sie FileProfile() zum Anreichern von Informationen zu Dateien in Ihren erweiterten Suchergebnissen verwenden.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
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
ms.openlocfilehash: 67295529cdb7b8a3e93e663f2a8a28d27a8f6737
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935845"
---
# <a name="fileprofile"></a><span data-ttu-id="6b179-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="6b179-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6b179-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6b179-105">**Applies to:**</span></span>
- <span data-ttu-id="6b179-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b179-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6b179-107">Die `FileProfile()` Funktion ist eine Anreicherungsfunktion bei der erweiterten [Suche,](advanced-hunting-overview.md) die dateien, die von der Abfrage gefunden werden, die folgenden Daten hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="6b179-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="6b179-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="6b179-108">Column</span></span> | <span data-ttu-id="6b179-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6b179-109">Data type</span></span> | <span data-ttu-id="6b179-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b179-110">Description</span></span> |
|------------|---------------|-------------|
| `SHA1` | <span data-ttu-id="6b179-111">string</span><span class="sxs-lookup"><span data-stu-id="6b179-111">string</span></span> | <span data-ttu-id="6b179-112">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="6b179-112">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="6b179-113">string</span><span class="sxs-lookup"><span data-stu-id="6b179-113">string</span></span> | <span data-ttu-id="6b179-114">SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="6b179-114">SHA-256 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="6b179-115">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6b179-115">string</span></span> | <span data-ttu-id="6b179-116">MD5-Hash der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="6b179-116">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileSize` | <span data-ttu-id="6b179-117">int</span><span class="sxs-lookup"><span data-stu-id="6b179-117">int</span></span> | <span data-ttu-id="6b179-118">Größe der Datei in Bytes</span><span class="sxs-lookup"><span data-stu-id="6b179-118">Size of the file in bytes</span></span> |
| `GlobalPrevalence` | <span data-ttu-id="6b179-119">int</span><span class="sxs-lookup"><span data-stu-id="6b179-119">int</span></span> | <span data-ttu-id="6b179-120">Anzahl der Instanzen der Entität, die von Microsoft global beobachtet werden</span><span class="sxs-lookup"><span data-stu-id="6b179-120">Number of instances of the entity observed by Microsoft globally</span></span> |
| `GlobalFirstSeen` | <span data-ttu-id="6b179-121">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="6b179-121">datetime</span></span> | <span data-ttu-id="6b179-122">Datum und Uhrzeit, zu dem die Entität erstmals von Microsoft global beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="6b179-122">Date and time when the entity was first observed by Microsoft globally</span></span> |
| `GlobalLastSeen` | <span data-ttu-id="6b179-123">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="6b179-123">datetime</span></span> | <span data-ttu-id="6b179-124">Datum und Uhrzeit, zu dem die Entität zuletzt von Microsoft global beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="6b179-124">Date and time when the entity was last observed by Microsoft globally</span></span> |
| `Signer` | <span data-ttu-id="6b179-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6b179-125">string</span></span> | <span data-ttu-id="6b179-126">Informationen zum Signier der Datei</span><span class="sxs-lookup"><span data-stu-id="6b179-126">Information about the signer of the file</span></span> |
| `Issuer` | <span data-ttu-id="6b179-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6b179-127">string</span></span> | <span data-ttu-id="6b179-128">Informationen zur ausstellenden Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="6b179-128">Information about the issuing certificate authority (CA)</span></span> |
| `SignerHash` | <span data-ttu-id="6b179-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6b179-129">string</span></span> | <span data-ttu-id="6b179-130">Eindeutiger Hashwert, der den Signier identifiziert</span><span class="sxs-lookup"><span data-stu-id="6b179-130">Unique hash value identifying the signer</span></span> |
| `IsCertificateValid` | <span data-ttu-id="6b179-131">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="6b179-131">boolean</span></span> | <span data-ttu-id="6b179-132">Gibt an, ob das zum Signieren der Datei verwendete Zertifikat gültig ist</span><span class="sxs-lookup"><span data-stu-id="6b179-132">Whether the certificate used to sign the file is valid</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="6b179-133">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="6b179-133">boolean</span></span> | <span data-ttu-id="6b179-134">Gibt an, ob der Signier des Stammzertifikats Microsoft ist</span><span class="sxs-lookup"><span data-stu-id="6b179-134">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `SignatureState` | <span data-ttu-id="6b179-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6b179-135">string</span></span> | <span data-ttu-id="6b179-136">Status der Dateisignatur: SignedValid - die Datei ist mit einer gültigen Signatur signiert, SignedInvalid - die Datei ist signiert, aber das Zertifikat ist ungültig, Unsigned - die Datei ist nicht signiert, unbekannt - Informationen zur Datei können nicht abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="6b179-136">State of the file signature: SignedValid - the file is signed with a valid signature, SignedInvalid - the file is signed but the certificate is invalid, Unsigned - the file is not signed, Unknown - information about the file cannot be retrieved</span></span>
| `IsExecutable` | <span data-ttu-id="6b179-137">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="6b179-137">boolean</span></span> | <span data-ttu-id="6b179-138">Gibt an, ob es sich bei der Datei um eine portable ausführbare Datei (Portable Executable, PE) handelt</span><span class="sxs-lookup"><span data-stu-id="6b179-138">Whether the file is a Portable Executable (PE) file</span></span> |
| `ThreatName` | <span data-ttu-id="6b179-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6b179-139">string</span></span> | <span data-ttu-id="6b179-140">Erkennungsname für gefundene Schadsoftware oder andere Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="6b179-140">Detection name for any malware or other threats found</span></span> |
| `Publisher` | <span data-ttu-id="6b179-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6b179-141">string</span></span> | <span data-ttu-id="6b179-142">Name der Organisation, die die Datei veröffentlicht hat</span><span class="sxs-lookup"><span data-stu-id="6b179-142">Name of the organization that published the file</span></span> |
| `SoftwareName` | <span data-ttu-id="6b179-143">string</span><span class="sxs-lookup"><span data-stu-id="6b179-143">string</span></span> | <span data-ttu-id="6b179-144">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="6b179-144">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="6b179-145">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b179-145">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="6b179-146">Argumente</span><span class="sxs-lookup"><span data-stu-id="6b179-146">Arguments</span></span>

- <span data-ttu-id="6b179-147">**x**–Datei-ID-Spalte, die verwendet werden soll: , , , oder ; -Funktion wird `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` verwendet, wenn nicht angegeben</span><span class="sxs-lookup"><span data-stu-id="6b179-147">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="6b179-148">**y**– Grenzwert für die Anzahl der datensätze, die bereichert werden müssen, 1-1000; -Funktion verwendet 100, wenn nicht angegeben</span><span class="sxs-lookup"><span data-stu-id="6b179-148">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="6b179-149">Anreicherungsfunktionen zeigen ergänzende Informationen nur an, wenn sie verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6b179-149">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="6b179-150">Die Verfügbarkeit von Informationen ist unterschiedlich und hängt von vielen Faktoren ab.</span><span class="sxs-lookup"><span data-stu-id="6b179-150">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="6b179-151">Achten Sie darauf, dies bei der Verwendung von FileProfile() in Ihren Abfragen oder beim Erstellen benutzerdefinierter Erkennungen zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="6b179-151">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="6b179-152">Für optimale Ergebnisse empfehlen wir die Verwendung der FileProfile()-Funktion mit SHA1.</span><span class="sxs-lookup"><span data-stu-id="6b179-152">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="6b179-153">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6b179-153">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="6b179-154">Nur die SPALTE "SHA1" projekt- und bereichern</span><span class="sxs-lookup"><span data-stu-id="6b179-154">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="6b179-155">Anreichern der ersten 500 Datensätze und Auflisten von Dateien mit niedriger Verbreitung</span><span class="sxs-lookup"><span data-stu-id="6b179-155">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="6b179-156">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6b179-156">Related topics</span></span>
- [<span data-ttu-id="6b179-157">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="6b179-157">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6b179-158">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="6b179-158">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6b179-159">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="6b179-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6b179-160">Weitere Abfragebeispiele erhalten</span><span class="sxs-lookup"><span data-stu-id="6b179-160">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
