---
title: Abrufen von Computerinformationen zu Warnungen
description: Rufen Sie alle Geräte im Zusammenhang mit einer bestimmten Warnung mit Microsoft Defender für Endpunkt ab.
keywords: APIs, Graph-API, unterstützte APIs, Warnungsinformationen abrufen, Warnungsinformationen, verwandtes Gerät
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
ms.openlocfilehash: ef10d2bd7193fc7b4a1604658f496ef38ef33555
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772341"
---
# <a name="get-alert-related-machine-information-api"></a><span data-ttu-id="c002e-104">Api zum Abrufen von Computerinformationen zu Warnungen</span><span class="sxs-lookup"><span data-stu-id="c002e-104">Get alert related machine information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c002e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c002e-105">**Applies to:**</span></span>
- [<span data-ttu-id="c002e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c002e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c002e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c002e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="c002e-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="c002e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c002e-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c002e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c002e-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c002e-110">API description</span></span>
<span data-ttu-id="c002e-111">Ruft [das Gerät](machine.md) ab, das sich auf eine bestimmte Warnung bezieht.</span><span class="sxs-lookup"><span data-stu-id="c002e-111">Retrieves [Device](machine.md) related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="c002e-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="c002e-112">Limitations</span></span>
1. <span data-ttu-id="c002e-113">Sie können nach Warnungen abfragen, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c002e-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="c002e-114">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="c002e-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="c002e-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c002e-115">Permissions</span></span>
<span data-ttu-id="c002e-116">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c002e-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c002e-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c002e-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c002e-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="c002e-118">Permission type</span></span> |   <span data-ttu-id="c002e-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c002e-119">Permission</span></span>  |   <span data-ttu-id="c002e-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c002e-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c002e-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="c002e-121">Application</span></span> |   <span data-ttu-id="c002e-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="c002e-122">Machine.Read.All</span></span> |  <span data-ttu-id="c002e-123">"Alle Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="c002e-123">'Read all machine information'</span></span>
<span data-ttu-id="c002e-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="c002e-124">Application</span></span> |   <span data-ttu-id="c002e-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c002e-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="c002e-126">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="c002e-126">'Read and write all machine information'</span></span>
<span data-ttu-id="c002e-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="c002e-127">Delegated (work or school account)</span></span> | <span data-ttu-id="c002e-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="c002e-128">Machine.Read</span></span> | <span data-ttu-id="c002e-129">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="c002e-129">'Read machine information'</span></span>
<span data-ttu-id="c002e-130">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="c002e-130">Delegated (work or school account)</span></span> | <span data-ttu-id="c002e-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c002e-131">Machine.ReadWrite</span></span> | <span data-ttu-id="c002e-132">"Lesen und Schreiben von Computerinformationen"</span><span class="sxs-lookup"><span data-stu-id="c002e-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="c002e-133">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="c002e-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c002e-134">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c002e-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="c002e-135">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben, das der Warnung zugeordnet ist (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="c002e-135">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c002e-136">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="c002e-136">HTTP request</span></span>

```http
GET /api/alerts/{id}/machine
```

## <a name="request-headers"></a><span data-ttu-id="c002e-137">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="c002e-137">Request headers</span></span>

<span data-ttu-id="c002e-138">Name</span><span class="sxs-lookup"><span data-stu-id="c002e-138">Name</span></span> | <span data-ttu-id="c002e-139">Typ</span><span class="sxs-lookup"><span data-stu-id="c002e-139">Type</span></span> | <span data-ttu-id="c002e-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c002e-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="c002e-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="c002e-141">Authorization</span></span> | <span data-ttu-id="c002e-142">String</span><span class="sxs-lookup"><span data-stu-id="c002e-142">String</span></span> | <span data-ttu-id="c002e-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c002e-143">Bearer {token}.</span></span> <span data-ttu-id="c002e-144">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="c002e-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="c002e-145">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="c002e-145">Request body</span></span>
<span data-ttu-id="c002e-146">Empty</span><span class="sxs-lookup"><span data-stu-id="c002e-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c002e-147">Antwort</span><span class="sxs-lookup"><span data-stu-id="c002e-147">Response</span></span>
<span data-ttu-id="c002e-148">Wenn erfolgreich und Warnung und Gerät vorhanden – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="c002e-148">If successful and alert and device exist - 200 OK.</span></span> <span data-ttu-id="c002e-149">Wenn Warnung nicht gefunden oder Gerät nicht gefunden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="c002e-149">If alert not found or device not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="c002e-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c002e-150">Example</span></span>

<span data-ttu-id="c002e-151">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="c002e-151">**Request**</span></span>

<span data-ttu-id="c002e-152">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="c002e-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/machine
```

<span data-ttu-id="c002e-153">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="c002e-153">**Response**</span></span>

<span data-ttu-id="c002e-154">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="c002e-154">Here is an example of the response.</span></span>


```json
{
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2021-01-25T07:27:36.052313Z",
    "osPlatform": "Windows10",
    "osProcessor": "x64",
    "version": "1901",
    "lastIpAddress": "10.166.113.46",
    "lastExternalIpAddress": "167.220.203.175",
    "osBuild": 19042,
    "healthStatus": "Active",
    "deviceValue": "Normal",
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Low",
    "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
    "machineTags": [
        "Tag1",
        "Tag2"
    ],
    "ipAddresses": [
        {
            "ipAddress": "10.166.113.47",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        },
        {
            "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        }
    ]
}
```
