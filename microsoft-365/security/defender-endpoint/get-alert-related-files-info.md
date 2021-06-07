---
title: Abrufen von Informationen zu Warnungsdateien
description: Rufen Sie alle Dateien im Zusammenhang mit einer bestimmten Warnung mit Microsoft Defender für Endpunkt ab.
keywords: APIs, Graph-API, unterstützte APIs, Warnungsinformationen abrufen, Warnungsinformationen, zugehörige Dateien
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
ms.openlocfilehash: 369dd35c65094d5a5985b471bec506cb5d266e59
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772350"
---
# <a name="get-alert-related-files-information-api"></a><span data-ttu-id="4cffe-104">Api zum Abrufen von Informationen zu Warnungsdateien</span><span class="sxs-lookup"><span data-stu-id="4cffe-104">Get alert related files information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4cffe-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4cffe-105">**Applies to:**</span></span>
- [<span data-ttu-id="4cffe-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4cffe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4cffe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4cffe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
 
> <span data-ttu-id="4cffe-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="4cffe-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4cffe-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4cffe-109">Sign up for free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4cffe-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cffe-110">API description</span></span>
<span data-ttu-id="4cffe-111">Ruft alle Dateien im Zusammenhang mit einer bestimmten Warnung ab.</span><span class="sxs-lookup"><span data-stu-id="4cffe-111">Retrieves all files related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="4cffe-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="4cffe-112">Limitations</span></span>
1. <span data-ttu-id="4cffe-113">Sie können nach Warnungen abfragen, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="4cffe-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="4cffe-114">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="4cffe-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4cffe-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4cffe-115">Permissions</span></span>
<span data-ttu-id="4cffe-116">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4cffe-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4cffe-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4cffe-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4cffe-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="4cffe-118">Permission type</span></span> | <span data-ttu-id="4cffe-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4cffe-119">Permission</span></span> | <span data-ttu-id="4cffe-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4cffe-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4cffe-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="4cffe-121">Application</span></span> | <span data-ttu-id="4cffe-122">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="4cffe-122">File.Read.All</span></span> | <span data-ttu-id="4cffe-123">"Dateiprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="4cffe-123">'Read file profiles'</span></span>
<span data-ttu-id="4cffe-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="4cffe-124">Delegated (work or school account)</span></span> | <span data-ttu-id="4cffe-125">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="4cffe-125">File.Read.All</span></span> | <span data-ttu-id="4cffe-126">"Dateiprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="4cffe-126">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="4cffe-127">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="4cffe-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4cffe-128">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="4cffe-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4cffe-129">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben, das der Warnung zugeordnet ist (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4cffe-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4cffe-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="4cffe-130">HTTP request</span></span>
```
GET /api/alerts/{id}/files
```

## <a name="request-headers"></a><span data-ttu-id="4cffe-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="4cffe-131">Request headers</span></span>

<span data-ttu-id="4cffe-132">Name</span><span class="sxs-lookup"><span data-stu-id="4cffe-132">Name</span></span> | <span data-ttu-id="4cffe-133">Typ</span><span class="sxs-lookup"><span data-stu-id="4cffe-133">Type</span></span> | <span data-ttu-id="4cffe-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cffe-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="4cffe-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="4cffe-135">Authorization</span></span> | <span data-ttu-id="4cffe-136">String</span><span class="sxs-lookup"><span data-stu-id="4cffe-136">String</span></span> | <span data-ttu-id="4cffe-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4cffe-137">Bearer {token}.</span></span> <span data-ttu-id="4cffe-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="4cffe-138">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4cffe-139">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="4cffe-139">Request body</span></span>
<span data-ttu-id="4cffe-140">Empty</span><span class="sxs-lookup"><span data-stu-id="4cffe-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4cffe-141">Antwort</span><span class="sxs-lookup"><span data-stu-id="4cffe-141">Response</span></span>
<span data-ttu-id="4cffe-142">Wenn erfolgreich und Warnung und Dateien vorhanden – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="4cffe-142">If successful and alert and files exist - 200 OK.</span></span> <span data-ttu-id="4cffe-143">Wenn Warnung nicht gefunden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="4cffe-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="4cffe-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4cffe-144">Example</span></span>

<span data-ttu-id="4cffe-145">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="4cffe-145">**Request**</span></span>

<span data-ttu-id="4cffe-146">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4cffe-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/files
```

<span data-ttu-id="4cffe-147">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="4cffe-147">**Response**</span></span>

<span data-ttu-id="4cffe-148">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="4cffe-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files",
    "value": [
        {
            "sha1": "f2a00fd2f2de1be0214b8529f1e9f67096c1aa70",
            "sha256": "dcd71ef5fff4362a9f64cf3f96f14f2b11d6f428f3badbedcb9ff3361e7079aa",
            "md5": "8d5b7cc9a832e21d22503057e1fec8e9",
            "globalPrevalence": 29,
            "globalFirstObserved": "2019-03-23T23:54:06.0135204Z",
            "globalLastObserved": "2019-04-23T00:43:20.0489831Z",
            "size": 113984,
            "fileType": null,
            "isPeFile": true,
            "filePublisher": "Microsoft Corporation",
            "fileProductName": "Microsoft� Windows� Operating System",
            "signer": "Microsoft Corporation",
            "issuer": "Microsoft Code Signing PCA",
            "signerHash": "9dc17888b5cfad98b3cb35c1994e96227f061675",
            "isValidCertificate": true,
            "determinationType": "Unknown",
            "determinationValue": null
        }
        ...
    ]
}
```
