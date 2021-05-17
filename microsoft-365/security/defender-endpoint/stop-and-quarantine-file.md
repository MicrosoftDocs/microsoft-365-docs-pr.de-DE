---
title: Api zum Beenden und Isolieren von Dateien
description: Erfahren Sie, wie Sie die Ausführung einer Datei auf einem Gerät beenden und die Datei in Microsoft Defender for Endpoint löschen. Sehen Sie sich das Beispiel an.
keywords: apis, graph api, supported apis, stop and quarantine file
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
ms.openlocfilehash: 670282f0f87092437bb1f3c6bf7be908e4649042
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199729"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="b61c3-105">Api zum Beenden und Isolieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="b61c3-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b61c3-106">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b61c3-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b61c3-107">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b61c3-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b61c3-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b61c3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b61c3-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b61c3-109">API description</span></span>
<span data-ttu-id="b61c3-110">Beenden Sie die Ausführung einer Datei auf einem Gerät, und löschen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="b61c3-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="b61c3-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b61c3-111">Limitations</span></span>
1. <span data-ttu-id="b61c3-112">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="b61c3-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="b61c3-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b61c3-113">Permissions</span></span>
<span data-ttu-id="b61c3-114">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b61c3-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b61c3-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b61c3-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b61c3-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="b61c3-116">Permission type</span></span> |   <span data-ttu-id="b61c3-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b61c3-117">Permission</span></span>  |   <span data-ttu-id="b61c3-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b61c3-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b61c3-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="b61c3-119">Application</span></span> |   <span data-ttu-id="b61c3-120">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="b61c3-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="b61c3-121">"Stop and Quarantine"</span><span class="sxs-lookup"><span data-stu-id="b61c3-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="b61c3-122">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="b61c3-122">Delegated (work or school account)</span></span> | <span data-ttu-id="b61c3-123">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="b61c3-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="b61c3-124">"Stop and Quarantine"</span><span class="sxs-lookup"><span data-stu-id="b61c3-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="b61c3-125">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="b61c3-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b61c3-126">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="b61c3-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b61c3-127">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="b61c3-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b61c3-128">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="b61c3-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="b61c3-129">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="b61c3-129">Request headers</span></span>

<span data-ttu-id="b61c3-130">Name</span><span class="sxs-lookup"><span data-stu-id="b61c3-130">Name</span></span> | <span data-ttu-id="b61c3-131">Typ</span><span class="sxs-lookup"><span data-stu-id="b61c3-131">Type</span></span> | <span data-ttu-id="b61c3-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b61c3-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="b61c3-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="b61c3-133">Authorization</span></span> | <span data-ttu-id="b61c3-134">String</span><span class="sxs-lookup"><span data-stu-id="b61c3-134">String</span></span> | <span data-ttu-id="b61c3-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b61c3-135">Bearer {token}.</span></span> <span data-ttu-id="b61c3-136">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b61c3-136">**Required**.</span></span>
<span data-ttu-id="b61c3-137">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b61c3-137">Content-Type</span></span> | <span data-ttu-id="b61c3-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b61c3-138">string</span></span> | <span data-ttu-id="b61c3-139">application/json.</span><span class="sxs-lookup"><span data-stu-id="b61c3-139">application/json.</span></span> <span data-ttu-id="b61c3-140">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b61c3-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b61c3-141">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="b61c3-141">Request body</span></span>
<span data-ttu-id="b61c3-142">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b61c3-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="b61c3-143">Parameter</span><span class="sxs-lookup"><span data-stu-id="b61c3-143">Parameter</span></span> | <span data-ttu-id="b61c3-144">Typ</span><span class="sxs-lookup"><span data-stu-id="b61c3-144">Type</span></span>    | <span data-ttu-id="b61c3-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b61c3-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="b61c3-146">Kommentar</span><span class="sxs-lookup"><span data-stu-id="b61c3-146">Comment</span></span> |   <span data-ttu-id="b61c3-147">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b61c3-147">String</span></span> |    <span data-ttu-id="b61c3-148">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b61c3-148">Comment to associate with the action.</span></span> <span data-ttu-id="b61c3-149">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b61c3-149">**Required**.</span></span>
<span data-ttu-id="b61c3-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="b61c3-150">Sha1</span></span> |  <span data-ttu-id="b61c3-151">String</span><span class="sxs-lookup"><span data-stu-id="b61c3-151">String</span></span>   | <span data-ttu-id="b61c3-152">Sha1 der Datei, die auf dem Gerät beendet und isoliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b61c3-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="b61c3-153">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b61c3-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="b61c3-154">Antwort</span><span class="sxs-lookup"><span data-stu-id="b61c3-154">Response</span></span>
<span data-ttu-id="b61c3-155">Wenn die Methode erfolgreich ist, wird 201 – Antwortcode erstellt und [Computeraktion](machineaction.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b61c3-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="b61c3-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b61c3-156">Example</span></span>

<span data-ttu-id="b61c3-157">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="b61c3-157">**Request**</span></span>

<span data-ttu-id="b61c3-158">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="b61c3-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
