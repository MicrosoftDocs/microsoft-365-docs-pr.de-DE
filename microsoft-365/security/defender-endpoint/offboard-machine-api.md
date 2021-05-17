---
title: Offboardcomputer-API
description: Erfahren Sie, wie Sie eine API verwenden, um ein Gerät von Microsoft Defender for Endpoint zu offboarden.
keywords: apis, graph api, supported apis, collect investigation package
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
ms.openlocfilehash: 03a1ef11224021703a6f33f82fa2c4f135a317a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934177"
---
# <a name="offboard-machine-api"></a><span data-ttu-id="5b2c2-104">Offboardcomputer-API</span><span class="sxs-lookup"><span data-stu-id="5b2c2-104">Offboard machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5b2c2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5b2c2-105">**Applies to:**</span></span>
- [<span data-ttu-id="5b2c2-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5b2c2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5b2c2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b2c2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5b2c2-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="5b2c2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5b2c2-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5b2c2-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b2c2-110">API description</span></span>
<span data-ttu-id="5b2c2-111">Offboardgerät von Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-111">Offboard device from Defender for Endpoint.</span></span>


## <a name="limitations"></a><span data-ttu-id="5b2c2-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5b2c2-112">Limitations</span></span>
 - <span data-ttu-id="5b2c2-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> <span data-ttu-id="5b2c2-114">Diese API wird auf Windows 10 Version 1703 und höher oder Windows Server 2019 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-114">This API is supported on Windows 10, version 1703 and later, or Windows Server 2019 and later.</span></span> <span data-ttu-id="5b2c2-115">Diese API wird auf MacOS- oder Linux-Geräten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-115">This API is not supported on MacOS or Linux devices.</span></span>

## <a name="permissions"></a><span data-ttu-id="5b2c2-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5b2c2-116">Permissions</span></span>
<span data-ttu-id="5b2c2-117">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5b2c2-118">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5b2c2-118">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5b2c2-119">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="5b2c2-119">Permission type</span></span> |   <span data-ttu-id="5b2c2-120">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="5b2c2-120">Permission</span></span>  |   <span data-ttu-id="5b2c2-121">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="5b2c2-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5b2c2-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="5b2c2-122">Application</span></span> |   <span data-ttu-id="5b2c2-123">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="5b2c2-123">Machine.Offboard</span></span> |  <span data-ttu-id="5b2c2-124">"Offboardcomputer"</span><span class="sxs-lookup"><span data-stu-id="5b2c2-124">'Offboard machine'</span></span>
<span data-ttu-id="5b2c2-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="5b2c2-125">Delegated (work or school account)</span></span> |    <span data-ttu-id="5b2c2-126">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="5b2c2-126">Machine.Offboard</span></span> |  <span data-ttu-id="5b2c2-127">"Offboardcomputer"</span><span class="sxs-lookup"><span data-stu-id="5b2c2-127">'Offboard machine'</span></span>

>[!Note]
> <span data-ttu-id="5b2c2-128">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="5b2c2-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5b2c2-129">Der Benutzer muss die AD-Rolle "Globaler Administrator"</span><span class="sxs-lookup"><span data-stu-id="5b2c2-129">The user needs to 'Global Admin' AD role</span></span>
>- <span data-ttu-id="5b2c2-130">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="5b2c2-130">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5b2c2-131">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="5b2c2-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a><span data-ttu-id="5b2c2-132">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="5b2c2-132">Request headers</span></span>

<span data-ttu-id="5b2c2-133">Name</span><span class="sxs-lookup"><span data-stu-id="5b2c2-133">Name</span></span> | <span data-ttu-id="5b2c2-134">Typ</span><span class="sxs-lookup"><span data-stu-id="5b2c2-134">Type</span></span> | <span data-ttu-id="5b2c2-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b2c2-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="5b2c2-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="5b2c2-136">Authorization</span></span> | <span data-ttu-id="5b2c2-137">String</span><span class="sxs-lookup"><span data-stu-id="5b2c2-137">String</span></span> | <span data-ttu-id="5b2c2-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-138">Bearer {token}.</span></span> <span data-ttu-id="5b2c2-139">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-139">**Required**.</span></span>
<span data-ttu-id="5b2c2-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="5b2c2-140">Content-Type</span></span> | <span data-ttu-id="5b2c2-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b2c2-141">string</span></span> | <span data-ttu-id="5b2c2-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-142">application/json.</span></span> <span data-ttu-id="5b2c2-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5b2c2-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="5b2c2-144">Request body</span></span>
<span data-ttu-id="5b2c2-145">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="5b2c2-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="5b2c2-146">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b2c2-146">Parameter</span></span> | <span data-ttu-id="5b2c2-147">Typ</span><span class="sxs-lookup"><span data-stu-id="5b2c2-147">Type</span></span>    | <span data-ttu-id="5b2c2-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b2c2-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="5b2c2-149">Kommentar</span><span class="sxs-lookup"><span data-stu-id="5b2c2-149">Comment</span></span> |   <span data-ttu-id="5b2c2-150">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b2c2-150">String</span></span> |    <span data-ttu-id="5b2c2-151">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-151">Comment to associate with the action.</span></span> <span data-ttu-id="5b2c2-152">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-152">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="5b2c2-153">Antwort</span><span class="sxs-lookup"><span data-stu-id="5b2c2-153">Response</span></span>
<span data-ttu-id="5b2c2-154">Wenn die Methode erfolgreich ist, wird 201 – Antwortcode erstellt und [Computeraktion](machineaction.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-154">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="5b2c2-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5b2c2-155">Example</span></span>

<span data-ttu-id="5b2c2-156">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="5b2c2-156">**Request**</span></span>

<span data-ttu-id="5b2c2-157">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="5b2c2-157">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
