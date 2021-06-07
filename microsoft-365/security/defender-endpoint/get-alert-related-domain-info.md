---
title: Erhalten von Informationen zu Benachrichtigungen zu Domänen
description: Rufen Sie alle Domänen im Zusammenhang mit einer bestimmten Warnung mit Microsoft Defender für Endpunkt ab.
keywords: APIs, Graph-API, unterstützte APIs, Warnungsinformationen abrufen, Warnungsinformationen, verwandte Domäne
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
ms.openlocfilehash: a5f3db65b42d8dc98c11f2ef2c3c5d509340e386
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771261"
---
# <a name="get-alert-related-domain-information-api"></a><span data-ttu-id="6cbfe-104">Api zum Abrufen von Domäneninformationen zu Warnungen</span><span class="sxs-lookup"><span data-stu-id="6cbfe-104">Get alert related domain information API</span></span>

<span data-ttu-id="6cbfe-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6cbfe-105">**Applies to:**</span></span> 
- [<span data-ttu-id="6cbfe-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6cbfe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="6cbfe-107">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="6cbfe-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6cbfe-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="6cbfe-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="6cbfe-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6cbfe-109">API description</span></span>
<span data-ttu-id="6cbfe-110">Ruft alle Domänen im Zusammenhang mit einer bestimmten Warnung ab.</span><span class="sxs-lookup"><span data-stu-id="6cbfe-110">Retrieves all domains related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="6cbfe-111">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="6cbfe-111">Limitations</span></span>
1. <span data-ttu-id="6cbfe-112">Sie können nach Warnungen abfragen, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6cbfe-112">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="6cbfe-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="6cbfe-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="6cbfe-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6cbfe-114">Permissions</span></span>
<span data-ttu-id="6cbfe-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6cbfe-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6cbfe-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6cbfe-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="6cbfe-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="6cbfe-117">Permission type</span></span> | <span data-ttu-id="6cbfe-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6cbfe-118">Permission</span></span> | <span data-ttu-id="6cbfe-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6cbfe-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6cbfe-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="6cbfe-120">Application</span></span> | <span data-ttu-id="6cbfe-121">Url. Read.All</span><span class="sxs-lookup"><span data-stu-id="6cbfe-121">URL.Read.All</span></span> | <span data-ttu-id="6cbfe-122">"Lese-URLs"</span><span class="sxs-lookup"><span data-stu-id="6cbfe-122">'Read URLs'</span></span>
<span data-ttu-id="6cbfe-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="6cbfe-123">Delegated (work or school account)</span></span> | <span data-ttu-id="6cbfe-124">Url. Read.All</span><span class="sxs-lookup"><span data-stu-id="6cbfe-124">URL.Read.All</span></span> | <span data-ttu-id="6cbfe-125">"Lese-URLs"</span><span class="sxs-lookup"><span data-stu-id="6cbfe-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="6cbfe-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="6cbfe-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="6cbfe-127">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="6cbfe-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="6cbfe-128">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben, das der Warnung zugeordnet ist (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="6cbfe-128">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="6cbfe-129">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="6cbfe-129">HTTP request</span></span>
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a><span data-ttu-id="6cbfe-130">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="6cbfe-130">Request headers</span></span>

<span data-ttu-id="6cbfe-131">Name</span><span class="sxs-lookup"><span data-stu-id="6cbfe-131">Name</span></span> | <span data-ttu-id="6cbfe-132">Typ</span><span class="sxs-lookup"><span data-stu-id="6cbfe-132">Type</span></span> | <span data-ttu-id="6cbfe-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6cbfe-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="6cbfe-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="6cbfe-134">Authorization</span></span> | <span data-ttu-id="6cbfe-135">String</span><span class="sxs-lookup"><span data-stu-id="6cbfe-135">String</span></span> | <span data-ttu-id="6cbfe-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6cbfe-136">Bearer {token}.</span></span> <span data-ttu-id="6cbfe-137">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="6cbfe-137">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6cbfe-138">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="6cbfe-138">Request body</span></span>
<span data-ttu-id="6cbfe-139">Empty</span><span class="sxs-lookup"><span data-stu-id="6cbfe-139">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6cbfe-140">Antwort</span><span class="sxs-lookup"><span data-stu-id="6cbfe-140">Response</span></span>
<span data-ttu-id="6cbfe-141">Wenn erfolgreich und Warnung und Domäne vorhanden – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="6cbfe-141">If successful and alert and domain exist - 200 OK.</span></span> <span data-ttu-id="6cbfe-142">Wenn Warnung nicht gefunden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="6cbfe-142">If alert not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="6cbfe-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6cbfe-143">Example</span></span>

<span data-ttu-id="6cbfe-144">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="6cbfe-144">**Request**</span></span>

<span data-ttu-id="6cbfe-145">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="6cbfe-145">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

<span data-ttu-id="6cbfe-146">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="6cbfe-146">**Response**</span></span>

<span data-ttu-id="6cbfe-147">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="6cbfe-147">Here is an example of the response.</span></span>

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
