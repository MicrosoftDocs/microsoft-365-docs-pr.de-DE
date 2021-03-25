---
title: Offboardcomputer-API
description: Erfahren Sie, wie Sie eine API zum Offboarden eines Geräts von Windows Defender Advanced Threat Protection (WDATP) verwenden.
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
ms.openlocfilehash: 0b3fa5a5daba1aa09eef0f733c7439848ce66a2c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187238"
---
# <a name="offboard-machine-api"></a><span data-ttu-id="7ca60-104">Offboardcomputer-API</span><span class="sxs-lookup"><span data-stu-id="7ca60-104">Offboard machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7ca60-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7ca60-105">**Applies to:**</span></span>
- [<span data-ttu-id="7ca60-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7ca60-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7ca60-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ca60-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7ca60-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="7ca60-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7ca60-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="7ca60-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="7ca60-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ca60-110">API description</span></span>
<span data-ttu-id="7ca60-111">Offboardgerät von Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7ca60-111">Offboard device from Defender for Endpoint.</span></span>


## <a name="limitations"></a><span data-ttu-id="7ca60-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7ca60-112">Limitations</span></span>
 - <span data-ttu-id="7ca60-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="7ca60-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> <span data-ttu-id="7ca60-114">Diese API wird unter Windows 10, Version 1703 und höher oder Windows Server 2019 und höher, unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7ca60-114">This API is supported on Windows 10, version 1703 and later, or Windows Server 2019 and later.</span></span> <span data-ttu-id="7ca60-115">Diese API wird auf MacOS- oder Linux-Geräten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7ca60-115">This API is not supported on MacOS or Linux devices.</span></span>

## <a name="permissions"></a><span data-ttu-id="7ca60-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7ca60-116">Permissions</span></span>
<span data-ttu-id="7ca60-117">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7ca60-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7ca60-118">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7ca60-118">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="7ca60-119">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="7ca60-119">Permission type</span></span> |   <span data-ttu-id="7ca60-120">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="7ca60-120">Permission</span></span>  |   <span data-ttu-id="7ca60-121">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="7ca60-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7ca60-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="7ca60-122">Application</span></span> |   <span data-ttu-id="7ca60-123">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="7ca60-123">Machine.Offboard</span></span> |  <span data-ttu-id="7ca60-124">"Offboardcomputer"</span><span class="sxs-lookup"><span data-stu-id="7ca60-124">'Offboard machine'</span></span>
<span data-ttu-id="7ca60-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="7ca60-125">Delegated (work or school account)</span></span> |    <span data-ttu-id="7ca60-126">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="7ca60-126">Machine.Offboard</span></span> |  <span data-ttu-id="7ca60-127">"Offboardcomputer"</span><span class="sxs-lookup"><span data-stu-id="7ca60-127">'Offboard machine'</span></span>

>[!Note]
> <span data-ttu-id="7ca60-128">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="7ca60-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="7ca60-129">Der Benutzer muss die AD-Rolle "Globaler Administrator"</span><span class="sxs-lookup"><span data-stu-id="7ca60-129">The user needs to 'Global Admin' AD role</span></span>
>- <span data-ttu-id="7ca60-130">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="7ca60-130">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="7ca60-131">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="7ca60-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a><span data-ttu-id="7ca60-132">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="7ca60-132">Request headers</span></span>

<span data-ttu-id="7ca60-133">Name</span><span class="sxs-lookup"><span data-stu-id="7ca60-133">Name</span></span> | <span data-ttu-id="7ca60-134">Typ</span><span class="sxs-lookup"><span data-stu-id="7ca60-134">Type</span></span> | <span data-ttu-id="7ca60-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ca60-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="7ca60-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="7ca60-136">Authorization</span></span> | <span data-ttu-id="7ca60-137">String</span><span class="sxs-lookup"><span data-stu-id="7ca60-137">String</span></span> | <span data-ttu-id="7ca60-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="7ca60-138">Bearer {token}.</span></span> <span data-ttu-id="7ca60-139">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="7ca60-139">**Required**.</span></span>
<span data-ttu-id="7ca60-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="7ca60-140">Content-Type</span></span> | <span data-ttu-id="7ca60-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ca60-141">string</span></span> | <span data-ttu-id="7ca60-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="7ca60-142">application/json.</span></span> <span data-ttu-id="7ca60-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="7ca60-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="7ca60-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="7ca60-144">Request body</span></span>
<span data-ttu-id="7ca60-145">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="7ca60-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="7ca60-146">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ca60-146">Parameter</span></span> | <span data-ttu-id="7ca60-147">Typ</span><span class="sxs-lookup"><span data-stu-id="7ca60-147">Type</span></span>    | <span data-ttu-id="7ca60-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ca60-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="7ca60-149">Kommentar</span><span class="sxs-lookup"><span data-stu-id="7ca60-149">Comment</span></span> |   <span data-ttu-id="7ca60-150">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ca60-150">String</span></span> |    <span data-ttu-id="7ca60-151">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ca60-151">Comment to associate with the action.</span></span> <span data-ttu-id="7ca60-152">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="7ca60-152">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="7ca60-153">Antwort</span><span class="sxs-lookup"><span data-stu-id="7ca60-153">Response</span></span>
<span data-ttu-id="7ca60-154">Wenn die Methode erfolgreich ist, wird 201 – Antwortcode erstellt und [Computeraktion](machineaction.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7ca60-154">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="7ca60-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7ca60-155">Example</span></span>

<span data-ttu-id="7ca60-156">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="7ca60-156">**Request**</span></span>

<span data-ttu-id="7ca60-157">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="7ca60-157">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
