---
title: File-Ressourcentyp
description: Rufen Sie aktuelle Microsoft Defender für Endpunkt-Warnungen im Zusammenhang mit Dateien ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnungen, zuletzt verwendet
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c4d392c9c7777a5ab5435d70e36822e11aa39dae
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771189"
---
# <a name="file-resource-type"></a><span data-ttu-id="57096-104">File-Ressourcentyp</span><span class="sxs-lookup"><span data-stu-id="57096-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="57096-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="57096-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="57096-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="57096-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="57096-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="57096-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="57096-108">Stellt eine Dateientität in Defender für Endpunkt dar.</span><span class="sxs-lookup"><span data-stu-id="57096-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="57096-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="57096-109">Methods</span></span>
<span data-ttu-id="57096-110">Methode</span><span class="sxs-lookup"><span data-stu-id="57096-110">Method</span></span>|<span data-ttu-id="57096-111">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="57096-111">Return Type</span></span> |<span data-ttu-id="57096-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57096-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="57096-113">Datei abrufen</span><span class="sxs-lookup"><span data-stu-id="57096-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="57096-114">file</span><span class="sxs-lookup"><span data-stu-id="57096-114">file</span></span>](files.md) | <span data-ttu-id="57096-115">Abrufen einer einzelnen Datei</span><span class="sxs-lookup"><span data-stu-id="57096-115">Get a single file</span></span> 
[<span data-ttu-id="57096-116">Dateibezogene Warnungen auflisten</span><span class="sxs-lookup"><span data-stu-id="57096-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="57096-117">[Warnung](alerts.md) Sammlung</span><span class="sxs-lookup"><span data-stu-id="57096-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="57096-118">Ruft [](alerts.md) die Warnungsentitäten ab, die der Datei zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="57096-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="57096-119">Dateibezogene Computer auflisten</span><span class="sxs-lookup"><span data-stu-id="57096-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="57096-120">[Computersammlung](machine.md)</span><span class="sxs-lookup"><span data-stu-id="57096-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="57096-121">Ruft [](machine.md) die Computerentitäten ab, die der Warnung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="57096-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="57096-122">Dateistatistiken</span><span class="sxs-lookup"><span data-stu-id="57096-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="57096-123">Statistikzusammenfassung</span><span class="sxs-lookup"><span data-stu-id="57096-123">Statistics summary</span></span> | <span data-ttu-id="57096-124">Ruft die Verbreitung für die angegebene Datei ab.</span><span class="sxs-lookup"><span data-stu-id="57096-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="57096-125">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="57096-125">Properties</span></span>
|<span data-ttu-id="57096-126">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="57096-126">Property</span></span> | <span data-ttu-id="57096-127">Typ</span><span class="sxs-lookup"><span data-stu-id="57096-127">Type</span></span>    |   <span data-ttu-id="57096-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57096-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="57096-129">sha1</span><span class="sxs-lookup"><span data-stu-id="57096-129">sha1</span></span> | <span data-ttu-id="57096-130">String</span><span class="sxs-lookup"><span data-stu-id="57096-130">String</span></span> | <span data-ttu-id="57096-131">Sha1-Hash des Dateiinhalts</span><span class="sxs-lookup"><span data-stu-id="57096-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="57096-132">sha256</span><span class="sxs-lookup"><span data-stu-id="57096-132">sha256</span></span> | <span data-ttu-id="57096-133">String</span><span class="sxs-lookup"><span data-stu-id="57096-133">String</span></span> | <span data-ttu-id="57096-134">Sha256-Hash des Dateiinhalts</span><span class="sxs-lookup"><span data-stu-id="57096-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="57096-135">globalPrevalence</span><span class="sxs-lookup"><span data-stu-id="57096-135">globalPrevalence</span></span> | <span data-ttu-id="57096-136">Nullable long</span><span class="sxs-lookup"><span data-stu-id="57096-136">Nullable long</span></span> | <span data-ttu-id="57096-137">Dateiprävalenz in der gesamten Organisation</span><span class="sxs-lookup"><span data-stu-id="57096-137">File prevalence across organization</span></span> |
|<span data-ttu-id="57096-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="57096-138">globalFirstObserved</span></span> | <span data-ttu-id="57096-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="57096-139">DateTimeOffset</span></span> | <span data-ttu-id="57096-140">Zeitpunkt, zu dem die Datei zum ersten Mal beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="57096-140">First time the file was observed</span></span> |
|<span data-ttu-id="57096-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="57096-141">globalLastObserved</span></span> | <span data-ttu-id="57096-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="57096-142">DateTimeOffset</span></span> | <span data-ttu-id="57096-143">Zeitpunkt, zu dem die Datei zuletzt beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="57096-143">Last time the file was observed</span></span> |
|<span data-ttu-id="57096-144">Größe</span><span class="sxs-lookup"><span data-stu-id="57096-144">size</span></span> | <span data-ttu-id="57096-145">Nullable long</span><span class="sxs-lookup"><span data-stu-id="57096-145">Nullable long</span></span> | <span data-ttu-id="57096-146">Größe der Datei</span><span class="sxs-lookup"><span data-stu-id="57096-146">Size of the file</span></span> |
|<span data-ttu-id="57096-147">Filetype</span><span class="sxs-lookup"><span data-stu-id="57096-147">fileType</span></span> | <span data-ttu-id="57096-148">String</span><span class="sxs-lookup"><span data-stu-id="57096-148">String</span></span> | <span data-ttu-id="57096-149">Typ der Datei</span><span class="sxs-lookup"><span data-stu-id="57096-149">Type of the file</span></span> |
|<span data-ttu-id="57096-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="57096-150">isPeFile</span></span> | <span data-ttu-id="57096-151">Boolesch</span><span class="sxs-lookup"><span data-stu-id="57096-151">Boolean</span></span> | <span data-ttu-id="57096-152">"true", wenn die Datei portierbar ist (z. B. "DLL", "EXE" usw.)</span><span class="sxs-lookup"><span data-stu-id="57096-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="57096-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="57096-153">filePublisher</span></span> | <span data-ttu-id="57096-154">String</span><span class="sxs-lookup"><span data-stu-id="57096-154">String</span></span> | <span data-ttu-id="57096-155">Dateiherausgeber</span><span class="sxs-lookup"><span data-stu-id="57096-155">File publisher</span></span> |
|<span data-ttu-id="57096-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="57096-156">fileProductName</span></span> | <span data-ttu-id="57096-157">String</span><span class="sxs-lookup"><span data-stu-id="57096-157">String</span></span> | <span data-ttu-id="57096-158">Produktname</span><span class="sxs-lookup"><span data-stu-id="57096-158">Product name</span></span> |
|<span data-ttu-id="57096-159">Signer</span><span class="sxs-lookup"><span data-stu-id="57096-159">signer</span></span> | <span data-ttu-id="57096-160">String</span><span class="sxs-lookup"><span data-stu-id="57096-160">String</span></span> | <span data-ttu-id="57096-161">Dateisignierer</span><span class="sxs-lookup"><span data-stu-id="57096-161">File signer</span></span> |
|<span data-ttu-id="57096-162">Emittenten</span><span class="sxs-lookup"><span data-stu-id="57096-162">issuer</span></span> | <span data-ttu-id="57096-163">String</span><span class="sxs-lookup"><span data-stu-id="57096-163">String</span></span> | <span data-ttu-id="57096-164">Dateiaussteller</span><span class="sxs-lookup"><span data-stu-id="57096-164">File issuer</span></span> |
|<span data-ttu-id="57096-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="57096-165">signerHash</span></span> | <span data-ttu-id="57096-166">String</span><span class="sxs-lookup"><span data-stu-id="57096-166">String</span></span> | <span data-ttu-id="57096-167">Hash des Signaturzertifikats</span><span class="sxs-lookup"><span data-stu-id="57096-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="57096-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="57096-168">isValidCertificate</span></span> | <span data-ttu-id="57096-169">Boolesch</span><span class="sxs-lookup"><span data-stu-id="57096-169">Boolean</span></span> | <span data-ttu-id="57096-170">Wurde das Signaturzertifikat vom Microsoft Defender für Endpunkt-Agent erfolgreich überprüft?</span><span class="sxs-lookup"><span data-stu-id="57096-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="57096-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="57096-171">determinationType</span></span> | <span data-ttu-id="57096-172">String</span><span class="sxs-lookup"><span data-stu-id="57096-172">String</span></span> | <span data-ttu-id="57096-173">Der Bestimmungstyp der Datei</span><span class="sxs-lookup"><span data-stu-id="57096-173">The determination type of the file</span></span> |
|<span data-ttu-id="57096-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="57096-174">determinationValue</span></span> | <span data-ttu-id="57096-175">String</span><span class="sxs-lookup"><span data-stu-id="57096-175">String</span></span> | <span data-ttu-id="57096-176">Ermittlungswert</span><span class="sxs-lookup"><span data-stu-id="57096-176">Determination value</span></span> |


## <a name="json-representation"></a><span data-ttu-id="57096-177">JSON-Darstellung</span><span class="sxs-lookup"><span data-stu-id="57096-177">Json representation</span></span>

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
