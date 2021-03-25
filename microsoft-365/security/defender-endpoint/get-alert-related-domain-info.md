---
title: Informationen zu Benachrichtigungsdomänen
description: Rufen Sie alle Domänen im Zusammenhang mit einer bestimmten Warnung mithilfe von Microsoft Defender for Endpoint ab.
keywords: apis, graph api, supported apis, get alert information, alert information, related domain
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
ms.openlocfilehash: 0cb09b23df8243d970069d087976ddc79394b67d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200413"
---
# <a name="get-alert-related-domain-information-api"></a><span data-ttu-id="d0650-104">Abrufen der Benachrichtigungsdomäneninformations-API</span><span class="sxs-lookup"><span data-stu-id="d0650-104">Get alert related domain information API</span></span>

<span data-ttu-id="d0650-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d0650-105">**Applies to:**</span></span> 
- [<span data-ttu-id="d0650-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d0650-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="d0650-107">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d0650-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d0650-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d0650-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d0650-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0650-109">API description</span></span>
<span data-ttu-id="d0650-110">Ruft alle Domänen im Zusammenhang mit einer bestimmten Warnung ab.</span><span class="sxs-lookup"><span data-stu-id="d0650-110">Retrieves all domains related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="d0650-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d0650-111">Limitations</span></span>
1. <span data-ttu-id="d0650-112">Sie können Warnungen abfragen, die zuletzt entsprechend ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d0650-112">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="d0650-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="d0650-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="d0650-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d0650-114">Permissions</span></span>
<span data-ttu-id="d0650-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d0650-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d0650-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d0650-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d0650-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="d0650-117">Permission type</span></span> | <span data-ttu-id="d0650-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="d0650-118">Permission</span></span> | <span data-ttu-id="d0650-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="d0650-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d0650-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="d0650-120">Application</span></span> | <span data-ttu-id="d0650-121">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="d0650-121">URL.Read.All</span></span> | <span data-ttu-id="d0650-122">'UrLs lesen'</span><span class="sxs-lookup"><span data-stu-id="d0650-122">'Read URLs'</span></span>
<span data-ttu-id="d0650-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="d0650-123">Delegated (work or school account)</span></span> | <span data-ttu-id="d0650-124">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="d0650-124">URL.Read.All</span></span> | <span data-ttu-id="d0650-125">'UrLs lesen'</span><span class="sxs-lookup"><span data-stu-id="d0650-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="d0650-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="d0650-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d0650-127">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="d0650-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="d0650-128">Der Benutzer muss auf das Gerät zugreifen können, das der Warnung zugeordnet ist, basierend auf den Gerätegruppeneinstellungen (Weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen)</span><span class="sxs-lookup"><span data-stu-id="d0650-128">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d0650-129">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="d0650-129">HTTP request</span></span>
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a><span data-ttu-id="d0650-130">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="d0650-130">Request headers</span></span>

<span data-ttu-id="d0650-131">Name</span><span class="sxs-lookup"><span data-stu-id="d0650-131">Name</span></span> | <span data-ttu-id="d0650-132">Typ</span><span class="sxs-lookup"><span data-stu-id="d0650-132">Type</span></span> | <span data-ttu-id="d0650-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0650-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="d0650-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="d0650-134">Authorization</span></span> | <span data-ttu-id="d0650-135">String</span><span class="sxs-lookup"><span data-stu-id="d0650-135">String</span></span> | <span data-ttu-id="d0650-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d0650-136">Bearer {token}.</span></span> <span data-ttu-id="d0650-137">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="d0650-137">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d0650-138">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="d0650-138">Request body</span></span>
<span data-ttu-id="d0650-139">Empty</span><span class="sxs-lookup"><span data-stu-id="d0650-139">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d0650-140">Antwort</span><span class="sxs-lookup"><span data-stu-id="d0650-140">Response</span></span>
<span data-ttu-id="d0650-141">Wenn erfolgreich und Warnung und Domäne vorhanden sind – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="d0650-141">If successful and alert and domain exist - 200 OK.</span></span> <span data-ttu-id="d0650-142">Wenn die Warnung nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="d0650-142">If alert not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="d0650-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0650-143">Example</span></span>

<span data-ttu-id="d0650-144">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="d0650-144">**Request**</span></span>

<span data-ttu-id="d0650-145">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="d0650-145">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

<span data-ttu-id="d0650-146">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="d0650-146">**Response**</span></span>

<span data-ttu-id="d0650-147">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="d0650-147">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Domains",
    "value": [
        {
            "host": "www.example.com"
        },
        {
            "host": "www.example2.com"
        }
        ...
    ]
}

```
