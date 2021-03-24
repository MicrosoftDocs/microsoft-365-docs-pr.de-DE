---
title: FileProfile()-Funktion bei der erweiterten Suche für Microsoft 365 Defender
description: Erfahren Sie, wie Sie FileProfile() zum Anreichern von Informationen zu Dateien in Ihren erweiterten Suchergebnissen verwenden.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, FileProfile, Dateiprofil, Funktion, Bereicherung
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e511c12240512af772b3552f63ad9ed98ff105af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062080"
---
# <a name="fileprofile"></a><span data-ttu-id="57f5e-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="57f5e-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="57f5e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="57f5e-105">**Applies to:**</span></span>
- <span data-ttu-id="57f5e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57f5e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="57f5e-107">Die `FileProfile()` Funktion ist eine Anreicherungsfunktion bei der erweiterten [Suche,](advanced-hunting-overview.md) die dateien, die von der Abfrage gefunden werden, die folgenden Daten hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="57f5e-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="57f5e-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="57f5e-108">Column</span></span> | <span data-ttu-id="57f5e-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="57f5e-109">Data type</span></span> | <span data-ttu-id="57f5e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57f5e-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="57f5e-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="57f5e-111">SHA1</span></span> | <span data-ttu-id="57f5e-112">string</span><span class="sxs-lookup"><span data-stu-id="57f5e-112">string</span></span> | <span data-ttu-id="57f5e-113">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="57f5e-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="57f5e-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="57f5e-114">SHA256</span></span> | <span data-ttu-id="57f5e-115">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57f5e-115">string</span></span> | <span data-ttu-id="57f5e-116">SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="57f5e-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="57f5e-117">MD5</span><span class="sxs-lookup"><span data-stu-id="57f5e-117">MD5</span></span> | <span data-ttu-id="57f5e-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57f5e-118">string</span></span> | <span data-ttu-id="57f5e-119">MD5-Hash der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="57f5e-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="57f5e-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="57f5e-120">FileSize</span></span> | <span data-ttu-id="57f5e-121">int</span><span class="sxs-lookup"><span data-stu-id="57f5e-121">int</span></span> | <span data-ttu-id="57f5e-122">Größe der Datei in Bytes</span><span class="sxs-lookup"><span data-stu-id="57f5e-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="57f5e-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="57f5e-123">GlobalPrevalence</span></span> | <span data-ttu-id="57f5e-124">int</span><span class="sxs-lookup"><span data-stu-id="57f5e-124">int</span></span> | <span data-ttu-id="57f5e-125">Anzahl der Instanzen der Entität, die von Microsoft global beobachtet werden</span><span class="sxs-lookup"><span data-stu-id="57f5e-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="57f5e-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="57f5e-126">GlobalFirstSeen</span></span> | <span data-ttu-id="57f5e-127">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="57f5e-127">datetime</span></span> | <span data-ttu-id="57f5e-128">Datum und Uhrzeit, zu dem die Entität erstmals von Microsoft global beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="57f5e-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="57f5e-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="57f5e-129">GlobalLastSeen</span></span> | <span data-ttu-id="57f5e-130">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="57f5e-130">datetime</span></span> | <span data-ttu-id="57f5e-131">Datum und Uhrzeit, zu dem die Entität zuletzt von Microsoft global beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="57f5e-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="57f5e-132">Signer</span><span class="sxs-lookup"><span data-stu-id="57f5e-132">Signer</span></span> | <span data-ttu-id="57f5e-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57f5e-133">string</span></span> | <span data-ttu-id="57f5e-134">Informationen zum Signier der Datei</span><span class="sxs-lookup"><span data-stu-id="57f5e-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="57f5e-135">Aussteller</span><span class="sxs-lookup"><span data-stu-id="57f5e-135">Issuer</span></span> | <span data-ttu-id="57f5e-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57f5e-136">string</span></span> | <span data-ttu-id="57f5e-137">Informationen zur ausstellenden Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="57f5e-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="57f5e-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="57f5e-138">SignerHash</span></span> | <span data-ttu-id="57f5e-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57f5e-139">string</span></span> | <span data-ttu-id="57f5e-140">Eindeutiger Hashwert, der den Signier identifiziert</span><span class="sxs-lookup"><span data-stu-id="57f5e-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="57f5e-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="57f5e-141">IsCertificateValid</span></span> | <span data-ttu-id="57f5e-142">boolean</span><span class="sxs-lookup"><span data-stu-id="57f5e-142">boolean</span></span> | <span data-ttu-id="57f5e-143">Gibt an, ob das zum Signieren der Datei verwendete Zertifikat gültig ist</span><span class="sxs-lookup"><span data-stu-id="57f5e-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="57f5e-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="57f5e-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="57f5e-145">boolean</span><span class="sxs-lookup"><span data-stu-id="57f5e-145">boolean</span></span> | <span data-ttu-id="57f5e-146">Gibt an, ob der Signier des Stammzertifikats Microsoft ist</span><span class="sxs-lookup"><span data-stu-id="57f5e-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="57f5e-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="57f5e-147">IsExecutable</span></span> | <span data-ttu-id="57f5e-148">boolean</span><span class="sxs-lookup"><span data-stu-id="57f5e-148">boolean</span></span> | <span data-ttu-id="57f5e-149">Gibt an, ob es sich bei der Datei um eine portable ausführbare Datei (Portable Executable, PE) handelt</span><span class="sxs-lookup"><span data-stu-id="57f5e-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="57f5e-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="57f5e-150">ThreatName</span></span> | <span data-ttu-id="57f5e-151">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57f5e-151">string</span></span> | <span data-ttu-id="57f5e-152">Erkennungsname für gefundene Schadsoftware oder andere Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="57f5e-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="57f5e-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="57f5e-153">Publisher</span></span> | <span data-ttu-id="57f5e-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57f5e-154">string</span></span> | <span data-ttu-id="57f5e-155">Name der Organisation, die die Datei veröffentlicht hat</span><span class="sxs-lookup"><span data-stu-id="57f5e-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="57f5e-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="57f5e-156">SoftwareName</span></span> | <span data-ttu-id="57f5e-157">string</span><span class="sxs-lookup"><span data-stu-id="57f5e-157">string</span></span> | <span data-ttu-id="57f5e-158">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="57f5e-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="57f5e-159">Syntax</span><span class="sxs-lookup"><span data-stu-id="57f5e-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="57f5e-160">Argumente</span><span class="sxs-lookup"><span data-stu-id="57f5e-160">Arguments</span></span>

- <span data-ttu-id="57f5e-161">**x**–Datei-ID-Spalte, die verwendet werden soll: , , , oder ; -Funktion wird `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` verwendet, wenn nicht angegeben</span><span class="sxs-lookup"><span data-stu-id="57f5e-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="57f5e-162">**y**– Grenzwert für die Anzahl der datensätze, die bereichert werden müssen, 1-1000; -Funktion verwendet 100, wenn nicht angegeben</span><span class="sxs-lookup"><span data-stu-id="57f5e-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="57f5e-163">Anreicherungsfunktionen zeigen ergänzende Informationen nur an, wenn sie verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="57f5e-163">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="57f5e-164">Die Verfügbarkeit von Informationen ist unterschiedlich und hängt von vielen Faktoren ab.</span><span class="sxs-lookup"><span data-stu-id="57f5e-164">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="57f5e-165">Achten Sie darauf, dies bei der Verwendung von FileProfile() in Ihren Abfragen oder beim Erstellen benutzerdefinierter Erkennungen zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="57f5e-165">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="57f5e-166">Für optimale Ergebnisse empfehlen wir die Verwendung der FileProfile()-Funktion mit SHA1.</span><span class="sxs-lookup"><span data-stu-id="57f5e-166">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="57f5e-167">Beispiele</span><span class="sxs-lookup"><span data-stu-id="57f5e-167">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="57f5e-168">Nur die SPALTE "SHA1" projekt- und bereichern</span><span class="sxs-lookup"><span data-stu-id="57f5e-168">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="57f5e-169">Anreichern der ersten 500 Datensätze und Auflisten von Dateien mit niedriger Verbreitung</span><span class="sxs-lookup"><span data-stu-id="57f5e-169">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="57f5e-170">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="57f5e-170">Related topics</span></span>
- [<span data-ttu-id="57f5e-171">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="57f5e-171">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="57f5e-172">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="57f5e-172">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="57f5e-173">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="57f5e-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="57f5e-174">Weitere Abfragebeispiele erhalten</span><span class="sxs-lookup"><span data-stu-id="57f5e-174">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
