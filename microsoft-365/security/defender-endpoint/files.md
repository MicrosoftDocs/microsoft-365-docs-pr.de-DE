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
ms.openlocfilehash: 83a011e649a7289f62acd6a8d985f020b27b1e10
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290015"
---
# <a name="file-resource-type"></a><span data-ttu-id="4a48e-104">File-Ressourcentyp</span><span class="sxs-lookup"><span data-stu-id="4a48e-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4a48e-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4a48e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="4a48e-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="4a48e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4a48e-107">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="4a48e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="4a48e-108">Stellt eine Dateientität in Defender für Endpunkt dar.</span><span class="sxs-lookup"><span data-stu-id="4a48e-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="4a48e-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="4a48e-109">Methods</span></span>

<span data-ttu-id="4a48e-110">Methode</span><span class="sxs-lookup"><span data-stu-id="4a48e-110">Method</span></span>|<span data-ttu-id="4a48e-111">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="4a48e-111">Return Type</span></span> |<span data-ttu-id="4a48e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a48e-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="4a48e-113">Datei abrufen</span><span class="sxs-lookup"><span data-stu-id="4a48e-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="4a48e-114">file</span><span class="sxs-lookup"><span data-stu-id="4a48e-114">file</span></span>](files.md) | <span data-ttu-id="4a48e-115">Abrufen einer einzelnen Datei</span><span class="sxs-lookup"><span data-stu-id="4a48e-115">Get a single file</span></span> 
[<span data-ttu-id="4a48e-116">Dateibezogene Warnungen auflisten</span><span class="sxs-lookup"><span data-stu-id="4a48e-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="4a48e-117">[Warnung](alerts.md) Sammlung</span><span class="sxs-lookup"><span data-stu-id="4a48e-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="4a48e-118">Ruft [](alerts.md) die Warnungsentitäten ab, die der Datei zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4a48e-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="4a48e-119">Dateibezogene Computer auflisten</span><span class="sxs-lookup"><span data-stu-id="4a48e-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="4a48e-120">[Computersammlung](machine.md)</span><span class="sxs-lookup"><span data-stu-id="4a48e-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="4a48e-121">Ruft [](machine.md) die Computerentitäten ab, die der Warnung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4a48e-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="4a48e-122">Dateistatistiken</span><span class="sxs-lookup"><span data-stu-id="4a48e-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="4a48e-123">Statistikzusammenfassung</span><span class="sxs-lookup"><span data-stu-id="4a48e-123">Statistics summary</span></span> | <span data-ttu-id="4a48e-124">Ruft die Verbreitung für die angegebene Datei ab.</span><span class="sxs-lookup"><span data-stu-id="4a48e-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="4a48e-125">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4a48e-125">Properties</span></span>

|<span data-ttu-id="4a48e-126">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4a48e-126">Property</span></span> | <span data-ttu-id="4a48e-127">Typ</span><span class="sxs-lookup"><span data-stu-id="4a48e-127">Type</span></span> | <span data-ttu-id="4a48e-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a48e-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="4a48e-129">sha1</span><span class="sxs-lookup"><span data-stu-id="4a48e-129">sha1</span></span> | <span data-ttu-id="4a48e-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4a48e-130">String</span></span> | <span data-ttu-id="4a48e-131">Sha1-Hash des Dateiinhalts</span><span class="sxs-lookup"><span data-stu-id="4a48e-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="4a48e-132">sha256</span><span class="sxs-lookup"><span data-stu-id="4a48e-132">sha256</span></span> | <span data-ttu-id="4a48e-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4a48e-133">String</span></span> | <span data-ttu-id="4a48e-134">Sha256-Hash des Dateiinhalts</span><span class="sxs-lookup"><span data-stu-id="4a48e-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="4a48e-135">globalPrevalence</span><span class="sxs-lookup"><span data-stu-id="4a48e-135">globalPrevalence</span></span> | <span data-ttu-id="4a48e-136">Nullable long</span><span class="sxs-lookup"><span data-stu-id="4a48e-136">Nullable long</span></span> | <span data-ttu-id="4a48e-137">Dateiprävalenz in der gesamten Organisation</span><span class="sxs-lookup"><span data-stu-id="4a48e-137">File prevalence across organization</span></span> |
|<span data-ttu-id="4a48e-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="4a48e-138">globalFirstObserved</span></span> | <span data-ttu-id="4a48e-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="4a48e-139">DateTimeOffset</span></span> | <span data-ttu-id="4a48e-140">Zeitpunkt, zu dem die Datei zum ersten Mal beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="4a48e-140">First time the file was observed</span></span> |
|<span data-ttu-id="4a48e-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="4a48e-141">globalLastObserved</span></span> | <span data-ttu-id="4a48e-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="4a48e-142">DateTimeOffset</span></span> | <span data-ttu-id="4a48e-143">Zeitpunkt, zu dem die Datei zuletzt beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="4a48e-143">Last time the file was observed</span></span> |
|<span data-ttu-id="4a48e-144">Größe</span><span class="sxs-lookup"><span data-stu-id="4a48e-144">size</span></span> | <span data-ttu-id="4a48e-145">Nullable long</span><span class="sxs-lookup"><span data-stu-id="4a48e-145">Nullable long</span></span> | <span data-ttu-id="4a48e-146">Größe der Datei</span><span class="sxs-lookup"><span data-stu-id="4a48e-146">Size of the file</span></span> |
|<span data-ttu-id="4a48e-147">Filetype</span><span class="sxs-lookup"><span data-stu-id="4a48e-147">fileType</span></span> | <span data-ttu-id="4a48e-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4a48e-148">String</span></span> | <span data-ttu-id="4a48e-149">Typ der Datei</span><span class="sxs-lookup"><span data-stu-id="4a48e-149">Type of the file</span></span> |
|<span data-ttu-id="4a48e-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="4a48e-150">isPeFile</span></span> | <span data-ttu-id="4a48e-151">Boolesch</span><span class="sxs-lookup"><span data-stu-id="4a48e-151">Boolean</span></span> | <span data-ttu-id="4a48e-152">"true", wenn die Datei portierbar ist (z. B. "DLL", "EXE" usw.)</span><span class="sxs-lookup"><span data-stu-id="4a48e-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="4a48e-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="4a48e-153">filePublisher</span></span> | <span data-ttu-id="4a48e-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4a48e-154">String</span></span> | <span data-ttu-id="4a48e-155">Dateiherausgeber</span><span class="sxs-lookup"><span data-stu-id="4a48e-155">File publisher</span></span> |
|<span data-ttu-id="4a48e-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="4a48e-156">fileProductName</span></span> | <span data-ttu-id="4a48e-157">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4a48e-157">String</span></span> | <span data-ttu-id="4a48e-158">Produktname</span><span class="sxs-lookup"><span data-stu-id="4a48e-158">Product name</span></span> |
|<span data-ttu-id="4a48e-159">Signer</span><span class="sxs-lookup"><span data-stu-id="4a48e-159">signer</span></span> | <span data-ttu-id="4a48e-160">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4a48e-160">String</span></span> | <span data-ttu-id="4a48e-161">Dateisignierer</span><span class="sxs-lookup"><span data-stu-id="4a48e-161">File signer</span></span> |
|<span data-ttu-id="4a48e-162">Emittenten</span><span class="sxs-lookup"><span data-stu-id="4a48e-162">issuer</span></span> | <span data-ttu-id="4a48e-163">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4a48e-163">String</span></span> | <span data-ttu-id="4a48e-164">Dateiaussteller</span><span class="sxs-lookup"><span data-stu-id="4a48e-164">File issuer</span></span> |
|<span data-ttu-id="4a48e-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="4a48e-165">signerHash</span></span> | <span data-ttu-id="4a48e-166">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4a48e-166">String</span></span> | <span data-ttu-id="4a48e-167">Hash des Signaturzertifikats</span><span class="sxs-lookup"><span data-stu-id="4a48e-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="4a48e-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="4a48e-168">isValidCertificate</span></span> | <span data-ttu-id="4a48e-169">Boolesch</span><span class="sxs-lookup"><span data-stu-id="4a48e-169">Boolean</span></span> | <span data-ttu-id="4a48e-170">Wurde das Signaturzertifikat vom Microsoft Defender für Endpunkt-Agent erfolgreich überprüft?</span><span class="sxs-lookup"><span data-stu-id="4a48e-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="4a48e-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="4a48e-171">determinationType</span></span> | <span data-ttu-id="4a48e-172">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4a48e-172">String</span></span> | <span data-ttu-id="4a48e-173">Der Bestimmungstyp der Datei</span><span class="sxs-lookup"><span data-stu-id="4a48e-173">The determination type of the file</span></span> |
|<span data-ttu-id="4a48e-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="4a48e-174">determinationValue</span></span> | <span data-ttu-id="4a48e-175">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4a48e-175">String</span></span> | <span data-ttu-id="4a48e-176">Ermittlungswert</span><span class="sxs-lookup"><span data-stu-id="4a48e-176">Determination value</span></span> |

## <a name="json-representation"></a><span data-ttu-id="4a48e-177">JSON-Darstellung</span><span class="sxs-lookup"><span data-stu-id="4a48e-177">Json representation</span></span>

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
