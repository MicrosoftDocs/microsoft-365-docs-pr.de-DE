---
title: File-Ressourcentyp
description: Abrufen der letzten Microsoft Defender for Endpoint-Warnungen im Zusammenhang mit Dateien.
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.technology: mde
ms.openlocfilehash: 9079a47dcc078b582586370b322502b74ce3838c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199981"
---
# <a name="file-resource-type"></a><span data-ttu-id="d93d9-104">File-Ressourcentyp</span><span class="sxs-lookup"><span data-stu-id="d93d9-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d93d9-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d93d9-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="d93d9-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d93d9-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d93d9-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d93d9-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="d93d9-108">Stellen Sie eine Dateientität in Defender for Endpoint dar.</span><span class="sxs-lookup"><span data-stu-id="d93d9-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="d93d9-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="d93d9-109">Methods</span></span>
<span data-ttu-id="d93d9-110">Methode</span><span class="sxs-lookup"><span data-stu-id="d93d9-110">Method</span></span>|<span data-ttu-id="d93d9-111">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="d93d9-111">Return Type</span></span> |<span data-ttu-id="d93d9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d93d9-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="d93d9-113">Datei herunterladen</span><span class="sxs-lookup"><span data-stu-id="d93d9-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="d93d9-114">file</span><span class="sxs-lookup"><span data-stu-id="d93d9-114">file</span></span>](files.md) | <span data-ttu-id="d93d9-115">Herunterladen einer einzelnen Datei</span><span class="sxs-lookup"><span data-stu-id="d93d9-115">Get a single file</span></span> 
[<span data-ttu-id="d93d9-116">Auflisten dateibezogener Warnungen</span><span class="sxs-lookup"><span data-stu-id="d93d9-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="d93d9-117">[Warnung](alerts.md) Sammlung</span><span class="sxs-lookup"><span data-stu-id="d93d9-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="d93d9-118">Get the [alert](alerts.md) entities that are associated with the file.</span><span class="sxs-lookup"><span data-stu-id="d93d9-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="d93d9-119">Auflisten dateibezogener Computer</span><span class="sxs-lookup"><span data-stu-id="d93d9-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="d93d9-120">[Computersammlung](machine.md)</span><span class="sxs-lookup"><span data-stu-id="d93d9-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="d93d9-121">Get the [machine](machine.md) entities associated with the alert.</span><span class="sxs-lookup"><span data-stu-id="d93d9-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="d93d9-122">Dateistatistiken</span><span class="sxs-lookup"><span data-stu-id="d93d9-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="d93d9-123">Zusammenfassung der Statistik</span><span class="sxs-lookup"><span data-stu-id="d93d9-123">Statistics summary</span></span> | <span data-ttu-id="d93d9-124">Ruft die Verbreitung für die angegebene Datei ab.</span><span class="sxs-lookup"><span data-stu-id="d93d9-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="d93d9-125">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d93d9-125">Properties</span></span>
|<span data-ttu-id="d93d9-126">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d93d9-126">Property</span></span> | <span data-ttu-id="d93d9-127">Typ</span><span class="sxs-lookup"><span data-stu-id="d93d9-127">Type</span></span>    |   <span data-ttu-id="d93d9-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d93d9-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="d93d9-129">sha1</span><span class="sxs-lookup"><span data-stu-id="d93d9-129">sha1</span></span> | <span data-ttu-id="d93d9-130">String</span><span class="sxs-lookup"><span data-stu-id="d93d9-130">String</span></span> | <span data-ttu-id="d93d9-131">Sha1-Hash des Dateiinhalts</span><span class="sxs-lookup"><span data-stu-id="d93d9-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="d93d9-132">sha256</span><span class="sxs-lookup"><span data-stu-id="d93d9-132">sha256</span></span> | <span data-ttu-id="d93d9-133">String</span><span class="sxs-lookup"><span data-stu-id="d93d9-133">String</span></span> | <span data-ttu-id="d93d9-134">Sha256-Hash des Dateiinhalts</span><span class="sxs-lookup"><span data-stu-id="d93d9-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="d93d9-135">globalPrevalence</span><span class="sxs-lookup"><span data-stu-id="d93d9-135">globalPrevalence</span></span> | <span data-ttu-id="d93d9-136">Nullable long</span><span class="sxs-lookup"><span data-stu-id="d93d9-136">Nullable long</span></span> | <span data-ttu-id="d93d9-137">Dateiprävalenz in der gesamten Organisation</span><span class="sxs-lookup"><span data-stu-id="d93d9-137">File prevalence across organization</span></span> |
|<span data-ttu-id="d93d9-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="d93d9-138">globalFirstObserved</span></span> | <span data-ttu-id="d93d9-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d93d9-139">DateTimeOffset</span></span> | <span data-ttu-id="d93d9-140">Erstes Mal, wenn die Datei beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="d93d9-140">First time the file was observed</span></span> |
|<span data-ttu-id="d93d9-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="d93d9-141">globalLastObserved</span></span> | <span data-ttu-id="d93d9-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d93d9-142">DateTimeOffset</span></span> | <span data-ttu-id="d93d9-143">Letztes Mal, wenn die Datei beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="d93d9-143">Last time the file was observed</span></span> |
|<span data-ttu-id="d93d9-144">Größe</span><span class="sxs-lookup"><span data-stu-id="d93d9-144">size</span></span> | <span data-ttu-id="d93d9-145">Nullable long</span><span class="sxs-lookup"><span data-stu-id="d93d9-145">Nullable long</span></span> | <span data-ttu-id="d93d9-146">Größe der Datei</span><span class="sxs-lookup"><span data-stu-id="d93d9-146">Size of the file</span></span> |
|<span data-ttu-id="d93d9-147">fileType</span><span class="sxs-lookup"><span data-stu-id="d93d9-147">fileType</span></span> | <span data-ttu-id="d93d9-148">String</span><span class="sxs-lookup"><span data-stu-id="d93d9-148">String</span></span> | <span data-ttu-id="d93d9-149">Dateityp</span><span class="sxs-lookup"><span data-stu-id="d93d9-149">Type of the file</span></span> |
|<span data-ttu-id="d93d9-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="d93d9-150">isPeFile</span></span> | <span data-ttu-id="d93d9-151">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="d93d9-151">Boolean</span></span> | <span data-ttu-id="d93d9-152">true, wenn die Datei portierbar ist (z. B. "DLL", "EXE"usw.)</span><span class="sxs-lookup"><span data-stu-id="d93d9-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="d93d9-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="d93d9-153">filePublisher</span></span> | <span data-ttu-id="d93d9-154">String</span><span class="sxs-lookup"><span data-stu-id="d93d9-154">String</span></span> | <span data-ttu-id="d93d9-155">Dateiherausgeber</span><span class="sxs-lookup"><span data-stu-id="d93d9-155">File publisher</span></span> |
|<span data-ttu-id="d93d9-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="d93d9-156">fileProductName</span></span> | <span data-ttu-id="d93d9-157">String</span><span class="sxs-lookup"><span data-stu-id="d93d9-157">String</span></span> | <span data-ttu-id="d93d9-158">Produktname</span><span class="sxs-lookup"><span data-stu-id="d93d9-158">Product name</span></span> |
|<span data-ttu-id="d93d9-159">Signer</span><span class="sxs-lookup"><span data-stu-id="d93d9-159">signer</span></span> | <span data-ttu-id="d93d9-160">String</span><span class="sxs-lookup"><span data-stu-id="d93d9-160">String</span></span> | <span data-ttu-id="d93d9-161">Datei signer</span><span class="sxs-lookup"><span data-stu-id="d93d9-161">File signer</span></span> |
|<span data-ttu-id="d93d9-162">Issuer</span><span class="sxs-lookup"><span data-stu-id="d93d9-162">issuer</span></span> | <span data-ttu-id="d93d9-163">String</span><span class="sxs-lookup"><span data-stu-id="d93d9-163">String</span></span> | <span data-ttu-id="d93d9-164">Dateiherausgeber</span><span class="sxs-lookup"><span data-stu-id="d93d9-164">File issuer</span></span> |
|<span data-ttu-id="d93d9-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="d93d9-165">signerHash</span></span> | <span data-ttu-id="d93d9-166">String</span><span class="sxs-lookup"><span data-stu-id="d93d9-166">String</span></span> | <span data-ttu-id="d93d9-167">Hash des Signaturzertifikats</span><span class="sxs-lookup"><span data-stu-id="d93d9-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="d93d9-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="d93d9-168">isValidCertificate</span></span> | <span data-ttu-id="d93d9-169">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="d93d9-169">Boolean</span></span> | <span data-ttu-id="d93d9-170">Wurde das Signaturzertifikat vom Microsoft Defender for Endpoint-Agent erfolgreich überprüft</span><span class="sxs-lookup"><span data-stu-id="d93d9-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="d93d9-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="d93d9-171">determinationType</span></span> | <span data-ttu-id="d93d9-172">String</span><span class="sxs-lookup"><span data-stu-id="d93d9-172">String</span></span> | <span data-ttu-id="d93d9-173">Der Bestimmungstyp der Datei</span><span class="sxs-lookup"><span data-stu-id="d93d9-173">The determination type of the file</span></span> |
|<span data-ttu-id="d93d9-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="d93d9-174">determinationValue</span></span> | <span data-ttu-id="d93d9-175">String</span><span class="sxs-lookup"><span data-stu-id="d93d9-175">String</span></span> | <span data-ttu-id="d93d9-176">Ermittlungswert</span><span class="sxs-lookup"><span data-stu-id="d93d9-176">Determination value</span></span> |


## <a name="json-representation"></a><span data-ttu-id="d93d9-177">Json-Darstellung</span><span class="sxs-lookup"><span data-stu-id="d93d9-177">Json representation</span></span>

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
