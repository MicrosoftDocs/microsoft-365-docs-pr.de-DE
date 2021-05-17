---
title: Ausführen der Antivirusscan-API
description: Verwenden Sie diese API, um Aufrufe im Zusammenhang mit der Ausführung einer Antivirenscan auf einem Gerät zu erstellen.
keywords: apis, graph api, supported apis, remove device from isolation
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
ms.openlocfilehash: d0db45daa786c1a44272e4d02153af3fe658e781
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200209"
---
# <a name="run-antivirus-scan-api"></a><span data-ttu-id="cd503-104">Ausführen der Antivirusscan-API</span><span class="sxs-lookup"><span data-stu-id="cd503-104">Run antivirus scan API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cd503-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="cd503-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="cd503-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="cd503-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cd503-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cd503-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="cd503-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd503-108">API description</span></span>
<span data-ttu-id="cd503-109">Initiieren Microsoft Defender Antivirus Überprüfung auf einem Gerät.</span><span class="sxs-lookup"><span data-stu-id="cd503-109">Initiate Microsoft Defender Antivirus scan on a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="cd503-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="cd503-110">Limitations</span></span>
1. <span data-ttu-id="cd503-111">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="cd503-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="cd503-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cd503-112">Permissions</span></span>
<span data-ttu-id="cd503-113">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cd503-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cd503-114">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cd503-114">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="cd503-115">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="cd503-115">Permission type</span></span> |   <span data-ttu-id="cd503-116">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="cd503-116">Permission</span></span>  |   <span data-ttu-id="cd503-117">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="cd503-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cd503-118">Anwendung</span><span class="sxs-lookup"><span data-stu-id="cd503-118">Application</span></span> |   <span data-ttu-id="cd503-119">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="cd503-119">Machine.Scan</span></span> |  <span data-ttu-id="cd503-120">"Scancomputer"</span><span class="sxs-lookup"><span data-stu-id="cd503-120">'Scan machine'</span></span>
<span data-ttu-id="cd503-121">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="cd503-121">Delegated (work or school account)</span></span> |    <span data-ttu-id="cd503-122">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="cd503-122">Machine.Scan</span></span> |  <span data-ttu-id="cd503-123">"Scancomputer"</span><span class="sxs-lookup"><span data-stu-id="cd503-123">'Scan machine'</span></span>

>[!Note]
> <span data-ttu-id="cd503-124">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="cd503-124">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="cd503-125">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="cd503-125">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="cd503-126">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="cd503-126">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="cd503-127">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="cd503-127">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a><span data-ttu-id="cd503-128">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="cd503-128">Request headers</span></span>

<span data-ttu-id="cd503-129">Name</span><span class="sxs-lookup"><span data-stu-id="cd503-129">Name</span></span> | <span data-ttu-id="cd503-130">Typ</span><span class="sxs-lookup"><span data-stu-id="cd503-130">Type</span></span> | <span data-ttu-id="cd503-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd503-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="cd503-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="cd503-132">Authorization</span></span> | <span data-ttu-id="cd503-133">String</span><span class="sxs-lookup"><span data-stu-id="cd503-133">String</span></span> | <span data-ttu-id="cd503-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="cd503-134">Bearer {token}.</span></span> <span data-ttu-id="cd503-135">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="cd503-135">**Required**.</span></span>
<span data-ttu-id="cd503-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="cd503-136">Content-Type</span></span> | <span data-ttu-id="cd503-137">string</span><span class="sxs-lookup"><span data-stu-id="cd503-137">string</span></span> | <span data-ttu-id="cd503-138">application/json</span><span class="sxs-lookup"><span data-stu-id="cd503-138">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="cd503-139">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="cd503-139">Request body</span></span>
<span data-ttu-id="cd503-140">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="cd503-140">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="cd503-141">Parameter</span><span class="sxs-lookup"><span data-stu-id="cd503-141">Parameter</span></span> | <span data-ttu-id="cd503-142">Typ</span><span class="sxs-lookup"><span data-stu-id="cd503-142">Type</span></span>    | <span data-ttu-id="cd503-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd503-143">Description</span></span>
:---|:---|:---
<span data-ttu-id="cd503-144">Kommentar</span><span class="sxs-lookup"><span data-stu-id="cd503-144">Comment</span></span> |   <span data-ttu-id="cd503-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="cd503-145">String</span></span> | <span data-ttu-id="cd503-146">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd503-146">Comment to associate with the action.</span></span> <span data-ttu-id="cd503-147">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="cd503-147">**Required**.</span></span>
<span data-ttu-id="cd503-148">ScanType</span><span class="sxs-lookup"><span data-stu-id="cd503-148">ScanType</span></span>|   <span data-ttu-id="cd503-149">String</span><span class="sxs-lookup"><span data-stu-id="cd503-149">String</span></span>  | <span data-ttu-id="cd503-150">Definiert den Typ des Scans.</span><span class="sxs-lookup"><span data-stu-id="cd503-150">Defines the type of the Scan.</span></span> <span data-ttu-id="cd503-151">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="cd503-151">**Required**.</span></span>

<span data-ttu-id="cd503-152">**ScanType** steuert den typ der durchzuführende Überprüfung und kann einer der folgenden Sein:</span><span class="sxs-lookup"><span data-stu-id="cd503-152">**ScanType** controls the type of scan to perform and can be one of the following:</span></span>

- <span data-ttu-id="cd503-153">**Schnell** – Schnelle Überprüfung auf dem Gerät durchführen</span><span class="sxs-lookup"><span data-stu-id="cd503-153">**Quick** – Perform quick scan on the device</span></span>
- <span data-ttu-id="cd503-154">**Vollständig** – Ausführen einer vollständigen Überprüfung auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="cd503-154">**Full** – Perform full scan on the device</span></span>



## <a name="response"></a><span data-ttu-id="cd503-155">Antwort</span><span class="sxs-lookup"><span data-stu-id="cd503-155">Response</span></span>
<span data-ttu-id="cd503-156">Wenn die Methode erfolgreich ist, werden 201, der Antwortcode erstellt und _das MachineAction-Objekt_ im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cd503-156">If successful, this method returns 201, Created response code and _MachineAction_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="cd503-157">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd503-157">Example</span></span>

<span data-ttu-id="cd503-158">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="cd503-158">**Request**</span></span>

<span data-ttu-id="cd503-159">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cd503-159">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```

