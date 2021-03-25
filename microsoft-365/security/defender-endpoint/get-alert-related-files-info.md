---
title: Informationen zu Benachrichtigungsdateien
description: Rufen Sie alle Dateien im Zusammenhang mit einer bestimmten Warnung mithilfe von Microsoft Defender for Endpoint ab.
keywords: apis, graph api, supported apis, get alert information, alert information, related files
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
ms.openlocfilehash: 31cbbaee9a97c061b61cc9f7ecc71bb759aea081
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166633"
---
# <a name="get-alert-related-files-information-api"></a><span data-ttu-id="569cb-104">Abrufen der Api für Benachrichtigungsdateien</span><span class="sxs-lookup"><span data-stu-id="569cb-104">Get alert related files information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="569cb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="569cb-105">**Applies to:**</span></span>
- [<span data-ttu-id="569cb-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="569cb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="569cb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="569cb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
 
> <span data-ttu-id="569cb-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="569cb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="569cb-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="569cb-109">Sign up for free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="569cb-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="569cb-110">API description</span></span>
<span data-ttu-id="569cb-111">Ruft alle Dateien im Zusammenhang mit einer bestimmten Warnung ab.</span><span class="sxs-lookup"><span data-stu-id="569cb-111">Retrieves all files related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="569cb-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="569cb-112">Limitations</span></span>
1. <span data-ttu-id="569cb-113">Sie können Warnungen abfragen, die zuletzt entsprechend ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="569cb-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="569cb-114">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="569cb-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="569cb-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="569cb-115">Permissions</span></span>
<span data-ttu-id="569cb-116">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="569cb-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="569cb-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="569cb-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="569cb-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="569cb-118">Permission type</span></span> | <span data-ttu-id="569cb-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="569cb-119">Permission</span></span> | <span data-ttu-id="569cb-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="569cb-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="569cb-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="569cb-121">Application</span></span> | <span data-ttu-id="569cb-122">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="569cb-122">File.Read.All</span></span> | <span data-ttu-id="569cb-123">"Dateiprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="569cb-123">'Read file profiles'</span></span>
<span data-ttu-id="569cb-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="569cb-124">Delegated (work or school account)</span></span> | <span data-ttu-id="569cb-125">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="569cb-125">File.Read.All</span></span> | <span data-ttu-id="569cb-126">"Dateiprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="569cb-126">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="569cb-127">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="569cb-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="569cb-128">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="569cb-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="569cb-129">Der Benutzer muss auf das Gerät zugreifen können, das der Warnung zugeordnet ist, basierend auf den Gerätegruppeneinstellungen (Weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen)</span><span class="sxs-lookup"><span data-stu-id="569cb-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="569cb-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="569cb-130">HTTP request</span></span>
```
GET /api/alerts/{id}/files
```

## <a name="request-headers"></a><span data-ttu-id="569cb-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="569cb-131">Request headers</span></span>

<span data-ttu-id="569cb-132">Name</span><span class="sxs-lookup"><span data-stu-id="569cb-132">Name</span></span> | <span data-ttu-id="569cb-133">Typ</span><span class="sxs-lookup"><span data-stu-id="569cb-133">Type</span></span> | <span data-ttu-id="569cb-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="569cb-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="569cb-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="569cb-135">Authorization</span></span> | <span data-ttu-id="569cb-136">String</span><span class="sxs-lookup"><span data-stu-id="569cb-136">String</span></span> | <span data-ttu-id="569cb-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="569cb-137">Bearer {token}.</span></span> <span data-ttu-id="569cb-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="569cb-138">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="569cb-139">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="569cb-139">Request body</span></span>
<span data-ttu-id="569cb-140">Empty</span><span class="sxs-lookup"><span data-stu-id="569cb-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="569cb-141">Antwort</span><span class="sxs-lookup"><span data-stu-id="569cb-141">Response</span></span>
<span data-ttu-id="569cb-142">Wenn erfolgreich und Warnung und Dateien vorhanden sind – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="569cb-142">If successful and alert and files exist - 200 OK.</span></span> <span data-ttu-id="569cb-143">Wenn die Warnung nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="569cb-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="569cb-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="569cb-144">Example</span></span>

<span data-ttu-id="569cb-145">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="569cb-145">**Request**</span></span>

<span data-ttu-id="569cb-146">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="569cb-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/files
```

<span data-ttu-id="569cb-147">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="569cb-147">**Response**</span></span>

<span data-ttu-id="569cb-148">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="569cb-148">Here is an example of the response.</span></span>


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
