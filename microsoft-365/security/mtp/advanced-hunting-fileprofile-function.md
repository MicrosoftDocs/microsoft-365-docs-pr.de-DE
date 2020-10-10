---
title: Fileprofile ()-Funktion im Advanced Hunting for Microsoft Threat Protection
description: Hier erfahren Sie, wie Sie mithilfe des Datei Profils () Informationen zu Dateien in ihren erweiterten Suchabfrageergebnissen bereichern.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Datei Profil, Datei Profil, Funktion, Bereicherung
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
ms.openlocfilehash: a89622206917c6b343ce47638c443b789513367b
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412178"
---
# <a name="fileprofile"></a><span data-ttu-id="1e20a-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="1e20a-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1e20a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1e20a-105">**Applies to:**</span></span>
- <span data-ttu-id="1e20a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1e20a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="1e20a-107">Die `FileProfile()` Funktion ist eine Anreicherungs Funktion in [Advanced Hunting](advanced-hunting-overview.md) , die die folgenden Daten zu Dateien hinzufügt, die von der Abfrage gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="1e20a-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="1e20a-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="1e20a-108">Column</span></span> | <span data-ttu-id="1e20a-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="1e20a-109">Data type</span></span> | <span data-ttu-id="1e20a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e20a-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="1e20a-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="1e20a-111">SHA1</span></span> | <span data-ttu-id="1e20a-112">string</span><span class="sxs-lookup"><span data-stu-id="1e20a-112">string</span></span> | <span data-ttu-id="1e20a-113">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="1e20a-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="1e20a-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="1e20a-114">SHA256</span></span> | <span data-ttu-id="1e20a-115">string</span><span class="sxs-lookup"><span data-stu-id="1e20a-115">string</span></span> | <span data-ttu-id="1e20a-116">SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="1e20a-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="1e20a-117">MD5</span><span class="sxs-lookup"><span data-stu-id="1e20a-117">MD5</span></span> | <span data-ttu-id="1e20a-118">string</span><span class="sxs-lookup"><span data-stu-id="1e20a-118">string</span></span> | <span data-ttu-id="1e20a-119">MD5-Hash der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="1e20a-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="1e20a-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="1e20a-120">FileSize</span></span> | <span data-ttu-id="1e20a-121">int</span><span class="sxs-lookup"><span data-stu-id="1e20a-121">int</span></span> | <span data-ttu-id="1e20a-122">Größe der Datei in Bytes</span><span class="sxs-lookup"><span data-stu-id="1e20a-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="1e20a-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="1e20a-123">GlobalPrevalence</span></span> | <span data-ttu-id="1e20a-124">int</span><span class="sxs-lookup"><span data-stu-id="1e20a-124">int</span></span> | <span data-ttu-id="1e20a-125">Anzahl der Instanzen der Entität, die von Microsoft Global beobachtet wurden</span><span class="sxs-lookup"><span data-stu-id="1e20a-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="1e20a-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="1e20a-126">GlobalFirstSeen</span></span> | <span data-ttu-id="1e20a-127">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1e20a-127">datetime</span></span> | <span data-ttu-id="1e20a-128">Datum und Uhrzeit, zu der die Entität erstmals von Microsoft Global beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="1e20a-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="1e20a-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="1e20a-129">GlobalLastSeen</span></span> | <span data-ttu-id="1e20a-130">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1e20a-130">datetime</span></span> | <span data-ttu-id="1e20a-131">Datum und Uhrzeit, zu der die Entität zuletzt von Microsoft Global beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="1e20a-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="1e20a-132">Signierers</span><span class="sxs-lookup"><span data-stu-id="1e20a-132">Signer</span></span> | <span data-ttu-id="1e20a-133">string</span><span class="sxs-lookup"><span data-stu-id="1e20a-133">string</span></span> | <span data-ttu-id="1e20a-134">Informationen über den unterschreibenden der Datei</span><span class="sxs-lookup"><span data-stu-id="1e20a-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="1e20a-135">Aussteller</span><span class="sxs-lookup"><span data-stu-id="1e20a-135">Issuer</span></span> | <span data-ttu-id="1e20a-136">string</span><span class="sxs-lookup"><span data-stu-id="1e20a-136">string</span></span> | <span data-ttu-id="1e20a-137">Informationen zur ausstellenden Zertifizierungsstelle (Certification Authority, ca)</span><span class="sxs-lookup"><span data-stu-id="1e20a-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="1e20a-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="1e20a-138">SignerHash</span></span> | <span data-ttu-id="1e20a-139">string</span><span class="sxs-lookup"><span data-stu-id="1e20a-139">string</span></span> | <span data-ttu-id="1e20a-140">Eindeutiger Hashwert zur Identifizierung der signierenden</span><span class="sxs-lookup"><span data-stu-id="1e20a-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="1e20a-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="1e20a-141">IsCertificateValid</span></span> | <span data-ttu-id="1e20a-142">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="1e20a-142">boolean</span></span> | <span data-ttu-id="1e20a-143">Gibt an, ob das zum Signieren der Datei verwendete Zertifikat gültig ist.</span><span class="sxs-lookup"><span data-stu-id="1e20a-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="1e20a-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="1e20a-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="1e20a-145">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="1e20a-145">boolean</span></span> | <span data-ttu-id="1e20a-146">Gibt an, ob die Signatur des Stammzertifikats Microsoft lautet.</span><span class="sxs-lookup"><span data-stu-id="1e20a-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="1e20a-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="1e20a-147">IsExecutable</span></span> | <span data-ttu-id="1e20a-148">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="1e20a-148">boolean</span></span> | <span data-ttu-id="1e20a-149">Gibt an, ob es sich bei der Datei um eine PE-Datei (Portable Executable) handelt</span><span class="sxs-lookup"><span data-stu-id="1e20a-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="1e20a-150">Bedrohungsname</span><span class="sxs-lookup"><span data-stu-id="1e20a-150">ThreatName</span></span> | <span data-ttu-id="1e20a-151">string</span><span class="sxs-lookup"><span data-stu-id="1e20a-151">string</span></span> | <span data-ttu-id="1e20a-152">Erkennungsname für Schadsoftware oder andere gefundene Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="1e20a-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="1e20a-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="1e20a-153">Publisher</span></span> | <span data-ttu-id="1e20a-154">string</span><span class="sxs-lookup"><span data-stu-id="1e20a-154">string</span></span> | <span data-ttu-id="1e20a-155">Name der Organisation, die die Datei veröffentlicht hat</span><span class="sxs-lookup"><span data-stu-id="1e20a-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="1e20a-156">Software Name</span><span class="sxs-lookup"><span data-stu-id="1e20a-156">SoftwareName</span></span> | <span data-ttu-id="1e20a-157">string</span><span class="sxs-lookup"><span data-stu-id="1e20a-157">string</span></span> | <span data-ttu-id="1e20a-158">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="1e20a-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="1e20a-159">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e20a-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="1e20a-160">Argumente</span><span class="sxs-lookup"><span data-stu-id="1e20a-160">Arguments</span></span>

- <span data-ttu-id="1e20a-161">**x**– zu verwendende Datei-ID-Spalte: `SHA1` , `SHA256` , `InitiatingProcessSHA1` , oder `InitiatingProcessSHA256` ; Funktion verwendet, `SHA1` Wenn nicht angegeben</span><span class="sxs-lookup"><span data-stu-id="1e20a-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="1e20a-162">**y**– Grenzwert für die Anzahl der zu bereichenden Datensätze, 1-1000; Funktion verwendet 100, wenn nicht angegeben</span><span class="sxs-lookup"><span data-stu-id="1e20a-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="1e20a-163">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1e20a-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="1e20a-164">Projizieren Sie nur die SHA1-Spalte und bereichern Sie Sie</span><span class="sxs-lookup"><span data-stu-id="1e20a-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="1e20a-165">Bereichern der ersten 500-Datensätze und Auflisten von Dateien mit niedriger Prävalenz</span><span class="sxs-lookup"><span data-stu-id="1e20a-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="1e20a-166">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1e20a-166">Related topics</span></span>
- [<span data-ttu-id="1e20a-167">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="1e20a-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1e20a-168">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="1e20a-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1e20a-169">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="1e20a-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1e20a-170">Abrufen weiterer Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="1e20a-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
