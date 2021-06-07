---
title: Sicherheitsbewertung des Geräts erhalten
description: Ruft die Sicherheitsbewertung des Unternehmensgeräts ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnungen, zuletzt verwendet
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: dd9def688619b6079d947cb76069aa0f77d768de
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772305"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="cc540-104">Sicherheitsbewertung des Geräts erhalten</span><span class="sxs-lookup"><span data-stu-id="cc540-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cc540-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cc540-105">**Applies to:**</span></span>
- [<span data-ttu-id="cc540-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cc540-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cc540-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc540-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="cc540-108">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="cc540-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="cc540-109">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="cc540-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cc540-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cc540-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="cc540-111">Ruft Ihre [Microsoft-Sicherheitsbewertung für Geräte](tvm-microsoft-secure-score-devices.md)ab.</span><span class="sxs-lookup"><span data-stu-id="cc540-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="cc540-112">Eine höhere Microsoft-Sicherheitsbewertung für Geräte bedeutet, dass Ihre Endpunkte stabiler vor Angriffen auf Cybersicherheitsbedrohungen sind.</span><span class="sxs-lookup"><span data-stu-id="cc540-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="cc540-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cc540-113">Permissions</span></span>

<span data-ttu-id="cc540-114">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="cc540-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cc540-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cc540-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="cc540-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="cc540-116">Permission type</span></span> |   <span data-ttu-id="cc540-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="cc540-117">Permission</span></span>  |   <span data-ttu-id="cc540-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="cc540-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cc540-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="cc540-119">Application</span></span> |   <span data-ttu-id="cc540-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="cc540-120">Score.Read.Alll</span></span> |   <span data-ttu-id="cc540-121">"Bewertung der Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="cc540-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="cc540-122">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="cc540-122">Delegated (work or school account)</span></span> | <span data-ttu-id="cc540-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="cc540-123">Score.Read</span></span> | <span data-ttu-id="cc540-124">"Bewertung der Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="cc540-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="cc540-125">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="cc540-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="cc540-126">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="cc540-126">Request headers</span></span>

<span data-ttu-id="cc540-127">Name</span><span class="sxs-lookup"><span data-stu-id="cc540-127">Name</span></span> | <span data-ttu-id="cc540-128">Typ</span><span class="sxs-lookup"><span data-stu-id="cc540-128">Type</span></span> | <span data-ttu-id="cc540-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc540-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="cc540-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="cc540-130">Authorization</span></span> | <span data-ttu-id="cc540-131">String</span><span class="sxs-lookup"><span data-stu-id="cc540-131">String</span></span> | <span data-ttu-id="cc540-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="cc540-132">Bearer {token}.</span></span> <span data-ttu-id="cc540-133">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="cc540-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="cc540-134">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="cc540-134">Request body</span></span>

<span data-ttu-id="cc540-135">Empty</span><span class="sxs-lookup"><span data-stu-id="cc540-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cc540-136">Antwort</span><span class="sxs-lookup"><span data-stu-id="cc540-136">Response</span></span>

<span data-ttu-id="cc540-137">Wenn die Methode erfolgreich ist, wird 200 OK zurückgegeben, wobei die Daten der Geräte-Sicherheitsbewertung im Antworttext enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="cc540-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="cc540-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cc540-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="cc540-139">Anforderung</span><span class="sxs-lookup"><span data-stu-id="cc540-139">Request</span></span>

<span data-ttu-id="cc540-140">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cc540-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="cc540-141">Antwort</span><span class="sxs-lookup"><span data-stu-id="cc540-141">Response</span></span>

<span data-ttu-id="cc540-142">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="cc540-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="cc540-143">Die hier gezeigte Antwortliste ist möglicherweise aus Platzgründen abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="cc540-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="cc540-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc540-144">See also</span></span>

- [<span data-ttu-id="cc540-145">OData-Abfragen mit Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cc540-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
