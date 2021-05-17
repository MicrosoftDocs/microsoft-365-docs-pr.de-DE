---
title: Sammeln der Untersuchungspaket-API
description: Verwenden Sie diese API, um Aufrufe im Zusammenhang mit dem Sammeln eines Untersuchungspakets von einem Gerät zu erstellen.
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
ms.openlocfilehash: 1e24236aae1922705c1711042f0426251a979ede
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166680"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="37034-104">Sammeln der Untersuchungspaket-API</span><span class="sxs-lookup"><span data-stu-id="37034-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="37034-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="37034-105">**Applies to:**</span></span>
- [<span data-ttu-id="37034-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="37034-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="37034-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37034-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="37034-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="37034-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="37034-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="37034-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="37034-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37034-110">API description</span></span>
<span data-ttu-id="37034-111">Erfassen sie das Untersuchungspaket von einem Gerät.</span><span class="sxs-lookup"><span data-stu-id="37034-111">Collect investigation package from a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="37034-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="37034-112">Limitations</span></span>
1. <span data-ttu-id="37034-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="37034-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="37034-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="37034-114">Permissions</span></span>
<span data-ttu-id="37034-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="37034-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="37034-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="37034-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="37034-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="37034-117">Permission type</span></span> |   <span data-ttu-id="37034-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="37034-118">Permission</span></span>  |   <span data-ttu-id="37034-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="37034-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="37034-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="37034-120">Application</span></span> |   <span data-ttu-id="37034-121">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="37034-121">Machine.CollectForensics</span></span> |  <span data-ttu-id="37034-122">"Forensik sammeln"</span><span class="sxs-lookup"><span data-stu-id="37034-122">'Collect forensics'</span></span>
<span data-ttu-id="37034-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="37034-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="37034-124">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="37034-124">Machine.CollectForensics</span></span> |  <span data-ttu-id="37034-125">"Forensik sammeln"</span><span class="sxs-lookup"><span data-stu-id="37034-125">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="37034-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="37034-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="37034-127">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Warnungsuntersuchung" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="37034-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="37034-128">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="37034-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="37034-129">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="37034-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="37034-130">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="37034-130">Request headers</span></span>

<span data-ttu-id="37034-131">Name</span><span class="sxs-lookup"><span data-stu-id="37034-131">Name</span></span> | <span data-ttu-id="37034-132">Typ</span><span class="sxs-lookup"><span data-stu-id="37034-132">Type</span></span> | <span data-ttu-id="37034-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37034-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="37034-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="37034-134">Authorization</span></span> | <span data-ttu-id="37034-135">String</span><span class="sxs-lookup"><span data-stu-id="37034-135">String</span></span> | <span data-ttu-id="37034-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="37034-136">Bearer {token}.</span></span> <span data-ttu-id="37034-137">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="37034-137">**Required**.</span></span>
<span data-ttu-id="37034-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="37034-138">Content-Type</span></span> | <span data-ttu-id="37034-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="37034-139">string</span></span> | <span data-ttu-id="37034-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="37034-140">application/json.</span></span> <span data-ttu-id="37034-141">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="37034-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="37034-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="37034-142">Request body</span></span>
<span data-ttu-id="37034-143">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="37034-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="37034-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="37034-144">Parameter</span></span> | <span data-ttu-id="37034-145">Typ</span><span class="sxs-lookup"><span data-stu-id="37034-145">Type</span></span>    | <span data-ttu-id="37034-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37034-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="37034-147">Kommentar</span><span class="sxs-lookup"><span data-stu-id="37034-147">Comment</span></span> |   <span data-ttu-id="37034-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="37034-148">String</span></span> |    <span data-ttu-id="37034-149">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="37034-149">Comment to associate with the action.</span></span> <span data-ttu-id="37034-150">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="37034-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="37034-151">Antwort</span><span class="sxs-lookup"><span data-stu-id="37034-151">Response</span></span>
<span data-ttu-id="37034-152">Wenn die Methode erfolgreich ist, wird 201 – Antwortcode erstellt und [Computeraktion](machineaction.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="37034-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="37034-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37034-153">Example</span></span>

<span data-ttu-id="37034-154">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="37034-154">**Request**</span></span>

<span data-ttu-id="37034-155">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="37034-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
