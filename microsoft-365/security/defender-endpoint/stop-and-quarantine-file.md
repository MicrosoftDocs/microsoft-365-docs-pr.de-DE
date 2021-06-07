---
title: Beenden und Isolieren der Datei-API
description: Erfahren Sie, wie Sie die Ausführung einer Datei auf einem Gerät beenden und die Datei in Microsoft Defender für Endpunkt löschen. Sehen Sie sich das Beispiel an.
keywords: APIs, Graph-API, unterstützte APIs, Stopp- und Quarantänedatei
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
ms.openlocfilehash: ac14f1ecda2b6256dc19223869b8878e6e725b96
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771404"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="0299a-105">Beenden und Isolieren der Datei-API</span><span class="sxs-lookup"><span data-stu-id="0299a-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0299a-106">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0299a-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="0299a-107">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="0299a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0299a-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0299a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="0299a-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0299a-109">API description</span></span>
<span data-ttu-id="0299a-110">Beenden Sie die Ausführung einer Datei auf einem Gerät, und löschen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="0299a-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="0299a-111">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="0299a-111">Limitations</span></span>
1. <span data-ttu-id="0299a-112">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="0299a-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="0299a-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0299a-113">Permissions</span></span>
<span data-ttu-id="0299a-114">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0299a-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0299a-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0299a-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="0299a-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="0299a-116">Permission type</span></span> |   <span data-ttu-id="0299a-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0299a-117">Permission</span></span>  |   <span data-ttu-id="0299a-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0299a-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0299a-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="0299a-119">Application</span></span> |   <span data-ttu-id="0299a-120">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="0299a-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="0299a-121">"Beenden und Isolieren"</span><span class="sxs-lookup"><span data-stu-id="0299a-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="0299a-122">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="0299a-122">Delegated (work or school account)</span></span> | <span data-ttu-id="0299a-123">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="0299a-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="0299a-124">"Beenden und Isolieren"</span><span class="sxs-lookup"><span data-stu-id="0299a-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="0299a-125">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="0299a-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="0299a-126">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0299a-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="0299a-127">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="0299a-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="0299a-128">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="0299a-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="0299a-129">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="0299a-129">Request headers</span></span>

<span data-ttu-id="0299a-130">Name</span><span class="sxs-lookup"><span data-stu-id="0299a-130">Name</span></span> | <span data-ttu-id="0299a-131">Typ</span><span class="sxs-lookup"><span data-stu-id="0299a-131">Type</span></span> | <span data-ttu-id="0299a-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0299a-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="0299a-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="0299a-133">Authorization</span></span> | <span data-ttu-id="0299a-134">String</span><span class="sxs-lookup"><span data-stu-id="0299a-134">String</span></span> | <span data-ttu-id="0299a-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="0299a-135">Bearer {token}.</span></span> <span data-ttu-id="0299a-136">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0299a-136">**Required**.</span></span>
<span data-ttu-id="0299a-137">Content-Type</span><span class="sxs-lookup"><span data-stu-id="0299a-137">Content-Type</span></span> | <span data-ttu-id="0299a-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0299a-138">string</span></span> | <span data-ttu-id="0299a-139">application/json.</span><span class="sxs-lookup"><span data-stu-id="0299a-139">application/json.</span></span> <span data-ttu-id="0299a-140">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0299a-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="0299a-141">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="0299a-141">Request body</span></span>
<span data-ttu-id="0299a-142">Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:</span><span class="sxs-lookup"><span data-stu-id="0299a-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="0299a-143">Parameter</span><span class="sxs-lookup"><span data-stu-id="0299a-143">Parameter</span></span> | <span data-ttu-id="0299a-144">Typ</span><span class="sxs-lookup"><span data-stu-id="0299a-144">Type</span></span>    | <span data-ttu-id="0299a-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0299a-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="0299a-146">Kommentar</span><span class="sxs-lookup"><span data-stu-id="0299a-146">Comment</span></span> |   <span data-ttu-id="0299a-147">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0299a-147">String</span></span> |    <span data-ttu-id="0299a-148">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0299a-148">Comment to associate with the action.</span></span> <span data-ttu-id="0299a-149">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0299a-149">**Required**.</span></span>
<span data-ttu-id="0299a-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="0299a-150">Sha1</span></span> |  <span data-ttu-id="0299a-151">String</span><span class="sxs-lookup"><span data-stu-id="0299a-151">String</span></span>   | <span data-ttu-id="0299a-152">Sha1 der Datei, die auf dem Gerät beendet und isoliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0299a-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="0299a-153">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0299a-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="0299a-154">Antwort</span><span class="sxs-lookup"><span data-stu-id="0299a-154">Response</span></span>
<span data-ttu-id="0299a-155">Bei erfolgreicher Ausführung gibt die Methode den Antwortcode 201 – Erstellt und die [Computeraktion](machineaction.md) im Antworttext zurück.</span><span class="sxs-lookup"><span data-stu-id="0299a-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="0299a-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0299a-156">Example</span></span>

<span data-ttu-id="0299a-157">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="0299a-157">**Request**</span></span>

<span data-ttu-id="0299a-158">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="0299a-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
