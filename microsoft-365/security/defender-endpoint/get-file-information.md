---
title: Abrufen der Dateiinformations-API
description: Erfahren Sie, wie Sie die API Dateiinformationen abrufen verwenden, um eine Datei nach Sha1- oder Sha256- oder MD5-ID in Microsoft Defender for Endpoint zu erhalten.
keywords: apis, graph api, supported apis, get, file, information, sha1, sha256, md5
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
ms.openlocfilehash: 181d808b465bfbf26eeff48a564e231b00a9a77f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166566"
---
# <a name="get-file-information-api"></a><span data-ttu-id="9e691-104">Abrufen der Dateiinformations-API</span><span class="sxs-lookup"><span data-stu-id="9e691-104">Get file information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9e691-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9e691-105">**Applies to:**</span></span>
- [<span data-ttu-id="9e691-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9e691-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9e691-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e691-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9e691-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9e691-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9e691-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9e691-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9e691-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e691-110">API description</span></span>
<span data-ttu-id="9e691-111">Ruft eine [Datei nach bezeichner](files.md) Sha1 oder Sha256 ab</span><span class="sxs-lookup"><span data-stu-id="9e691-111">Retrieves a [File](files.md) by identifier Sha1, or Sha256</span></span>


## <a name="limitations"></a><span data-ttu-id="9e691-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="9e691-112">Limitations</span></span>
1. <span data-ttu-id="9e691-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="9e691-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="9e691-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9e691-114">Permissions</span></span>
<span data-ttu-id="9e691-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9e691-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9e691-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9e691-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9e691-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="9e691-117">Permission type</span></span> |   <span data-ttu-id="9e691-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9e691-118">Permission</span></span>  |   <span data-ttu-id="9e691-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9e691-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9e691-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="9e691-120">Application</span></span> |   <span data-ttu-id="9e691-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="9e691-121">File.Read.All</span></span> | <span data-ttu-id="9e691-122">"Alle Dateiprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="9e691-122">'Read all file profiles'</span></span>
<span data-ttu-id="9e691-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="9e691-123">Delegated (work or school account)</span></span> | <span data-ttu-id="9e691-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="9e691-124">File.Read.All</span></span> |    <span data-ttu-id="9e691-125">"Alle Dateiprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="9e691-125">'Read all file profiles'</span></span>

>[!Note]
> <span data-ttu-id="9e691-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="9e691-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9e691-127">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="9e691-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9e691-128">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="9e691-128">HTTP request</span></span>
```
GET /api/files/{id}
```

## <a name="request-headers"></a><span data-ttu-id="9e691-129">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="9e691-129">Request headers</span></span>

<span data-ttu-id="9e691-130">Name</span><span class="sxs-lookup"><span data-stu-id="9e691-130">Name</span></span> | <span data-ttu-id="9e691-131">Typ</span><span class="sxs-lookup"><span data-stu-id="9e691-131">Type</span></span> | <span data-ttu-id="9e691-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e691-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="9e691-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="9e691-133">Authorization</span></span> | <span data-ttu-id="9e691-134">String</span><span class="sxs-lookup"><span data-stu-id="9e691-134">String</span></span> | <span data-ttu-id="9e691-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="9e691-135">Bearer {token}.</span></span> <span data-ttu-id="9e691-136">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="9e691-136">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9e691-137">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="9e691-137">Request body</span></span>
<span data-ttu-id="9e691-138">Empty</span><span class="sxs-lookup"><span data-stu-id="9e691-138">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9e691-139">Antwort</span><span class="sxs-lookup"><span data-stu-id="9e691-139">Response</span></span>
<span data-ttu-id="9e691-140">Wenn erfolgreich und Datei vorhanden ist – 200 OK mit der [Dateientität](files.md) im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="9e691-140">If successful and file exists - 200 OK with the [file](files.md) entity in the body.</span></span> <span data-ttu-id="9e691-141">Wenn die Datei nicht vorhanden ist – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="9e691-141">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="9e691-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9e691-142">Example</span></span>

<span data-ttu-id="9e691-143">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="9e691-143">**Request**</span></span>

<span data-ttu-id="9e691-144">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="9e691-144">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/4388963aaa83afe2042a46a3c017ad50bdcdafb3
```

<span data-ttu-id="9e691-145">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="9e691-145">**Response**</span></span>

<span data-ttu-id="9e691-146">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="9e691-146">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files/$entity",
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
