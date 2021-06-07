---
title: Api zum Abrufen von Dateiinformationen
description: Erfahren Sie, wie Sie die API zum Abrufen von Dateiinformationen verwenden, um eine Datei nach Sha1, Sha256 oder MD5-Bezeichner in Microsoft Defender für Endpunkt abzurufen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Datei, Informationen, sha1, sha256, md5
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
ms.openlocfilehash: b7877fb2d9b616b487d23befd0f0af35ce2c0753
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770291"
---
# <a name="get-file-information-api"></a><span data-ttu-id="1adff-104">Api zum Abrufen von Dateiinformationen</span><span class="sxs-lookup"><span data-stu-id="1adff-104">Get file information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1adff-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1adff-105">**Applies to:**</span></span>
- [<span data-ttu-id="1adff-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1adff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1adff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1adff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1adff-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="1adff-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1adff-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="1adff-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1adff-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1adff-110">API description</span></span>
<span data-ttu-id="1adff-111">Ruft eine [Datei](files.md) anhand des Bezeichners "Sha1" oder "Sha256" ab.</span><span class="sxs-lookup"><span data-stu-id="1adff-111">Retrieves a [File](files.md) by identifier Sha1, or Sha256</span></span>


## <a name="limitations"></a><span data-ttu-id="1adff-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="1adff-112">Limitations</span></span>
1. <span data-ttu-id="1adff-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="1adff-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1adff-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1adff-114">Permissions</span></span>
<span data-ttu-id="1adff-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1adff-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1adff-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1adff-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1adff-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="1adff-117">Permission type</span></span> |   <span data-ttu-id="1adff-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1adff-118">Permission</span></span>  |   <span data-ttu-id="1adff-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1adff-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1adff-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="1adff-120">Application</span></span> |   <span data-ttu-id="1adff-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="1adff-121">File.Read.All</span></span> | <span data-ttu-id="1adff-122">"Alle Dateiprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="1adff-122">'Read all file profiles'</span></span>
<span data-ttu-id="1adff-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="1adff-123">Delegated (work or school account)</span></span> | <span data-ttu-id="1adff-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="1adff-124">File.Read.All</span></span> |    <span data-ttu-id="1adff-125">"Alle Dateiprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="1adff-125">'Read all file profiles'</span></span>

>[!Note]
> <span data-ttu-id="1adff-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="1adff-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="1adff-127">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="1adff-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1adff-128">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="1adff-128">HTTP request</span></span>
```
GET /api/files/{id}
```

## <a name="request-headers"></a><span data-ttu-id="1adff-129">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="1adff-129">Request headers</span></span>

<span data-ttu-id="1adff-130">Name</span><span class="sxs-lookup"><span data-stu-id="1adff-130">Name</span></span> | <span data-ttu-id="1adff-131">Typ</span><span class="sxs-lookup"><span data-stu-id="1adff-131">Type</span></span> | <span data-ttu-id="1adff-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1adff-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="1adff-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="1adff-133">Authorization</span></span> | <span data-ttu-id="1adff-134">String</span><span class="sxs-lookup"><span data-stu-id="1adff-134">String</span></span> | <span data-ttu-id="1adff-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1adff-135">Bearer {token}.</span></span> <span data-ttu-id="1adff-136">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="1adff-136">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1adff-137">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="1adff-137">Request body</span></span>
<span data-ttu-id="1adff-138">Empty</span><span class="sxs-lookup"><span data-stu-id="1adff-138">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1adff-139">Antwort</span><span class="sxs-lookup"><span data-stu-id="1adff-139">Response</span></span>
<span data-ttu-id="1adff-140">Wenn erfolgreich und Datei vorhanden – 200 OK mit der [Dateientität](files.md) im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="1adff-140">If successful and file exists - 200 OK with the [file](files.md) entity in the body.</span></span> <span data-ttu-id="1adff-141">Wenn datei nicht vorhanden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="1adff-141">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="1adff-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1adff-142">Example</span></span>

<span data-ttu-id="1adff-143">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="1adff-143">**Request**</span></span>

<span data-ttu-id="1adff-144">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="1adff-144">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/4388963aaa83afe2042a46a3c017ad50bdcdafb3
```

<span data-ttu-id="1adff-145">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="1adff-145">**Response**</span></span>

<span data-ttu-id="1adff-146">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="1adff-146">Here is an example of the response.</span></span>


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
