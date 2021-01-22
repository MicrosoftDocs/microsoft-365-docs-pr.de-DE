---
title: FileProfile()-Funktion bei der erweiterten Suche nach Microsoft 365 Defender
description: Erfahren Sie, wie Sie FileProfile() verwenden, um Informationen zu Dateien in den Abfrageergebnissen für die erweiterte Suche zu erweitern.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, FileProfile, Dateiprofil, Funktion, Anreicherung
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
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929550"
---
# <a name="fileprofile"></a><span data-ttu-id="b0e15-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="b0e15-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b0e15-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b0e15-105">**Applies to:**</span></span>
- <span data-ttu-id="b0e15-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0e15-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b0e15-107">Die `FileProfile()` Funktion ist eine Anreicherungsfunktion bei der erweiterten [Suche,](advanced-hunting-overview.md) die den von der Abfrage gefundenen Dateien die folgenden Daten hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="b0e15-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="b0e15-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="b0e15-108">Column</span></span> | <span data-ttu-id="b0e15-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b0e15-109">Data type</span></span> | <span data-ttu-id="b0e15-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0e15-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="b0e15-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="b0e15-111">SHA1</span></span> | <span data-ttu-id="b0e15-112">string</span><span class="sxs-lookup"><span data-stu-id="b0e15-112">string</span></span> | <span data-ttu-id="b0e15-113">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="b0e15-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="b0e15-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="b0e15-114">SHA256</span></span> | <span data-ttu-id="b0e15-115">string</span><span class="sxs-lookup"><span data-stu-id="b0e15-115">string</span></span> | <span data-ttu-id="b0e15-116">SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="b0e15-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="b0e15-117">MD5</span><span class="sxs-lookup"><span data-stu-id="b0e15-117">MD5</span></span> | <span data-ttu-id="b0e15-118">string</span><span class="sxs-lookup"><span data-stu-id="b0e15-118">string</span></span> | <span data-ttu-id="b0e15-119">#A0 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="b0e15-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="b0e15-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="b0e15-120">FileSize</span></span> | <span data-ttu-id="b0e15-121">int</span><span class="sxs-lookup"><span data-stu-id="b0e15-121">int</span></span> | <span data-ttu-id="b0e15-122">Größe der Datei in Byte</span><span class="sxs-lookup"><span data-stu-id="b0e15-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="b0e15-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="b0e15-123">GlobalPrevalence</span></span> | <span data-ttu-id="b0e15-124">int</span><span class="sxs-lookup"><span data-stu-id="b0e15-124">int</span></span> | <span data-ttu-id="b0e15-125">Anzahl der Instanzen der Entität, die von Microsoft global beobachtet werden</span><span class="sxs-lookup"><span data-stu-id="b0e15-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="b0e15-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="b0e15-126">GlobalFirstSeen</span></span> | <span data-ttu-id="b0e15-127">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="b0e15-127">datetime</span></span> | <span data-ttu-id="b0e15-128">Datum und Uhrzeit der ersten globalen Beobachtung der Entität durch Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0e15-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="b0e15-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="b0e15-129">GlobalLastSeen</span></span> | <span data-ttu-id="b0e15-130">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="b0e15-130">datetime</span></span> | <span data-ttu-id="b0e15-131">Datum und Uhrzeit der letzten globalen Beobachtung der Entität durch Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0e15-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="b0e15-132">Signer</span><span class="sxs-lookup"><span data-stu-id="b0e15-132">Signer</span></span> | <span data-ttu-id="b0e15-133">string</span><span class="sxs-lookup"><span data-stu-id="b0e15-133">string</span></span> | <span data-ttu-id="b0e15-134">Informationen zum Signier der Datei</span><span class="sxs-lookup"><span data-stu-id="b0e15-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="b0e15-135">Aussteller</span><span class="sxs-lookup"><span data-stu-id="b0e15-135">Issuer</span></span> | <span data-ttu-id="b0e15-136">string</span><span class="sxs-lookup"><span data-stu-id="b0e15-136">string</span></span> | <span data-ttu-id="b0e15-137">Informationen zur ausstellenden Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="b0e15-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="b0e15-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="b0e15-138">SignerHash</span></span> | <span data-ttu-id="b0e15-139">string</span><span class="sxs-lookup"><span data-stu-id="b0e15-139">string</span></span> | <span data-ttu-id="b0e15-140">Eindeutiger Hashwert, der den Signier identifiziert</span><span class="sxs-lookup"><span data-stu-id="b0e15-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="b0e15-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="b0e15-141">IsCertificateValid</span></span> | <span data-ttu-id="b0e15-142">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="b0e15-142">boolean</span></span> | <span data-ttu-id="b0e15-143">Gibt an, ob das zum Signieren der Datei verwendete Zertifikat gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b0e15-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="b0e15-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="b0e15-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="b0e15-145">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="b0e15-145">boolean</span></span> | <span data-ttu-id="b0e15-146">Gibt an, ob der Signier des Stammzertifikats Microsoft ist.</span><span class="sxs-lookup"><span data-stu-id="b0e15-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="b0e15-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="b0e15-147">IsExecutable</span></span> | <span data-ttu-id="b0e15-148">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="b0e15-148">boolean</span></span> | <span data-ttu-id="b0e15-149">Gibt an, ob es sich bei der Datei um eine portable ausführbare Datei (Portable Executable, PE) handelt.</span><span class="sxs-lookup"><span data-stu-id="b0e15-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="b0e15-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="b0e15-150">ThreatName</span></span> | <span data-ttu-id="b0e15-151">string</span><span class="sxs-lookup"><span data-stu-id="b0e15-151">string</span></span> | <span data-ttu-id="b0e15-152">Erkennungsname für schadsoftware- oder andere gefundene Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="b0e15-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="b0e15-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="b0e15-153">Publisher</span></span> | <span data-ttu-id="b0e15-154">string</span><span class="sxs-lookup"><span data-stu-id="b0e15-154">string</span></span> | <span data-ttu-id="b0e15-155">Name der Organisation, die die Datei veröffentlicht hat</span><span class="sxs-lookup"><span data-stu-id="b0e15-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="b0e15-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="b0e15-156">SoftwareName</span></span> | <span data-ttu-id="b0e15-157">string</span><span class="sxs-lookup"><span data-stu-id="b0e15-157">string</span></span> | <span data-ttu-id="b0e15-158">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="b0e15-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="b0e15-159">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0e15-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="b0e15-160">Argumente</span><span class="sxs-lookup"><span data-stu-id="b0e15-160">Arguments</span></span>

- <span data-ttu-id="b0e15-161">**x**– zu verwendende Datei-ID-Spalte: , , oder ; Wird bei nicht `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` angegebener Funktion verwendet</span><span class="sxs-lookup"><span data-stu-id="b0e15-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="b0e15-162">**y**– Grenzwert für die Anzahl der datensätze, die anreichert werden soll, 1-1000; funktion verwendet 100, wenn nicht angegeben</span><span class="sxs-lookup"><span data-stu-id="b0e15-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="b0e15-163">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b0e15-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="b0e15-164">Nur die Spalte "SHA1" projekten und erweitern</span><span class="sxs-lookup"><span data-stu-id="b0e15-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="b0e15-165">Anreichern der ersten 500 Datensätze und Listendateien mit niedriger Verbreitung</span><span class="sxs-lookup"><span data-stu-id="b0e15-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="b0e15-166">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b0e15-166">Related topics</span></span>
- [<span data-ttu-id="b0e15-167">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="b0e15-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b0e15-168">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="b0e15-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b0e15-169">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="b0e15-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b0e15-170">Weitere Abfragebeispiele erhalten</span><span class="sxs-lookup"><span data-stu-id="b0e15-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
