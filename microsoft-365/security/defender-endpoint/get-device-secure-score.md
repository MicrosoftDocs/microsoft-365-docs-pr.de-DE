---
title: Sichern der Gerätepunktzahl
description: Ruft die sicherheitse Bewertung des Organisationsgeräts ab.
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 921334c937e3f211b032a5d24d4244d9a6fb3d61
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166579"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="c6714-104">Sichern der Gerätepunktzahl</span><span class="sxs-lookup"><span data-stu-id="c6714-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c6714-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c6714-105">**Applies to:**</span></span>
- [<span data-ttu-id="c6714-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c6714-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c6714-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6714-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c6714-108">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c6714-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="c6714-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="c6714-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c6714-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c6714-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="c6714-111">Ruft Ihre [Microsoft Secure Score für Geräte ab.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="c6714-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="c6714-112">Eine höhere Microsoft Secure Score für Geräte bedeutet, dass Ihre Endpunkte widerstandsfähiger gegen Cybersicherheitsangriffe sind.</span><span class="sxs-lookup"><span data-stu-id="c6714-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="c6714-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c6714-113">Permissions</span></span>

<span data-ttu-id="c6714-114">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c6714-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c6714-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.</span><span class="sxs-lookup"><span data-stu-id="c6714-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="c6714-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="c6714-116">Permission type</span></span> |   <span data-ttu-id="c6714-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c6714-117">Permission</span></span>  |   <span data-ttu-id="c6714-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c6714-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c6714-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="c6714-119">Application</span></span> |   <span data-ttu-id="c6714-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="c6714-120">Score.Read.Alll</span></span> |   <span data-ttu-id="c6714-121">"Bewertung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="c6714-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="c6714-122">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="c6714-122">Delegated (work or school account)</span></span> | <span data-ttu-id="c6714-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="c6714-123">Score.Read</span></span> | <span data-ttu-id="c6714-124">"Bewertung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="c6714-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="c6714-125">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="c6714-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="c6714-126">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="c6714-126">Request headers</span></span>

<span data-ttu-id="c6714-127">Name</span><span class="sxs-lookup"><span data-stu-id="c6714-127">Name</span></span> | <span data-ttu-id="c6714-128">Typ</span><span class="sxs-lookup"><span data-stu-id="c6714-128">Type</span></span> | <span data-ttu-id="c6714-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6714-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="c6714-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="c6714-130">Authorization</span></span> | <span data-ttu-id="c6714-131">String</span><span class="sxs-lookup"><span data-stu-id="c6714-131">String</span></span> | <span data-ttu-id="c6714-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c6714-132">Bearer {token}.</span></span> <span data-ttu-id="c6714-133">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="c6714-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c6714-134">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="c6714-134">Request body</span></span>

<span data-ttu-id="c6714-135">Empty</span><span class="sxs-lookup"><span data-stu-id="c6714-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c6714-136">Antwort</span><span class="sxs-lookup"><span data-stu-id="c6714-136">Response</span></span>

<span data-ttu-id="c6714-137">Wenn die Methode erfolgreich ist, gibt sie 200 OK zurück, und das Gerät enthält sichere Bewertungsdaten im Antworttext.</span><span class="sxs-lookup"><span data-stu-id="c6714-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="c6714-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c6714-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="c6714-139">Anforderung</span><span class="sxs-lookup"><span data-stu-id="c6714-139">Request</span></span>

<span data-ttu-id="c6714-140">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="c6714-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="c6714-141">Antwort</span><span class="sxs-lookup"><span data-stu-id="c6714-141">Response</span></span>

<span data-ttu-id="c6714-142">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="c6714-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="c6714-143">Die hier gezeigte Antwortliste kann aus Kürze gekürzt werden.</span><span class="sxs-lookup"><span data-stu-id="c6714-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="c6714-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6714-144">See also</span></span>

- [<span data-ttu-id="c6714-145">OData-Abfragen mit Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c6714-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
