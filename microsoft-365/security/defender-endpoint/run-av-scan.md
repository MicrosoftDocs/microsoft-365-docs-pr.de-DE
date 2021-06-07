---
title: Ausführen der Antivirus-Scan-API
description: Verwenden Sie diese API, um Aufrufe im Zusammenhang mit der Ausführung eines Antivirenscans auf einem Gerät zu erstellen.
keywords: APIs, Graph-API, unterstützte APIs, Gerät aus Isolation entfernen
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
ms.openlocfilehash: 3df703fd84c87a2bd34bb2a81f8c83063e468b17
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771448"
---
# <a name="run-antivirus-scan-api"></a><span data-ttu-id="77d7b-104">Ausführen der Antivirus-Scan-API</span><span class="sxs-lookup"><span data-stu-id="77d7b-104">Run antivirus scan API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="77d7b-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="77d7b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="77d7b-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="77d7b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="77d7b-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="77d7b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="77d7b-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77d7b-108">API description</span></span>
<span data-ttu-id="77d7b-109">Initiieren sie Microsoft Defender Antivirus Überprüfung auf einem Gerät.</span><span class="sxs-lookup"><span data-stu-id="77d7b-109">Initiate Microsoft Defender Antivirus scan on a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="77d7b-110">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="77d7b-110">Limitations</span></span>
1. <span data-ttu-id="77d7b-111">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="77d7b-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="77d7b-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="77d7b-112">Permissions</span></span>
<span data-ttu-id="77d7b-113">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="77d7b-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="77d7b-114">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="77d7b-114">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="77d7b-115">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="77d7b-115">Permission type</span></span> |   <span data-ttu-id="77d7b-116">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="77d7b-116">Permission</span></span>  |   <span data-ttu-id="77d7b-117">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="77d7b-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="77d7b-118">Anwendung</span><span class="sxs-lookup"><span data-stu-id="77d7b-118">Application</span></span> |   <span data-ttu-id="77d7b-119">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="77d7b-119">Machine.Scan</span></span> |  <span data-ttu-id="77d7b-120">"Scancomputer"</span><span class="sxs-lookup"><span data-stu-id="77d7b-120">'Scan machine'</span></span>
<span data-ttu-id="77d7b-121">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="77d7b-121">Delegated (work or school account)</span></span> |    <span data-ttu-id="77d7b-122">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="77d7b-122">Machine.Scan</span></span> |  <span data-ttu-id="77d7b-123">"Scancomputer"</span><span class="sxs-lookup"><span data-stu-id="77d7b-123">'Scan machine'</span></span>

>[!Note]
> <span data-ttu-id="77d7b-124">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="77d7b-124">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="77d7b-125">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="77d7b-125">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="77d7b-126">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="77d7b-126">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="77d7b-127">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="77d7b-127">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a><span data-ttu-id="77d7b-128">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="77d7b-128">Request headers</span></span>

<span data-ttu-id="77d7b-129">Name</span><span class="sxs-lookup"><span data-stu-id="77d7b-129">Name</span></span> | <span data-ttu-id="77d7b-130">Typ</span><span class="sxs-lookup"><span data-stu-id="77d7b-130">Type</span></span> | <span data-ttu-id="77d7b-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77d7b-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="77d7b-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="77d7b-132">Authorization</span></span> | <span data-ttu-id="77d7b-133">String</span><span class="sxs-lookup"><span data-stu-id="77d7b-133">String</span></span> | <span data-ttu-id="77d7b-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="77d7b-134">Bearer {token}.</span></span> <span data-ttu-id="77d7b-135">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="77d7b-135">**Required**.</span></span>
<span data-ttu-id="77d7b-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="77d7b-136">Content-Type</span></span> | <span data-ttu-id="77d7b-137">string</span><span class="sxs-lookup"><span data-stu-id="77d7b-137">string</span></span> | <span data-ttu-id="77d7b-138">application/json</span><span class="sxs-lookup"><span data-stu-id="77d7b-138">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="77d7b-139">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="77d7b-139">Request body</span></span>
<span data-ttu-id="77d7b-140">Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:</span><span class="sxs-lookup"><span data-stu-id="77d7b-140">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="77d7b-141">Parameter</span><span class="sxs-lookup"><span data-stu-id="77d7b-141">Parameter</span></span> | <span data-ttu-id="77d7b-142">Typ</span><span class="sxs-lookup"><span data-stu-id="77d7b-142">Type</span></span>    | <span data-ttu-id="77d7b-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77d7b-143">Description</span></span>
:---|:---|:---
<span data-ttu-id="77d7b-144">Kommentar</span><span class="sxs-lookup"><span data-stu-id="77d7b-144">Comment</span></span> |   <span data-ttu-id="77d7b-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="77d7b-145">String</span></span> | <span data-ttu-id="77d7b-146">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="77d7b-146">Comment to associate with the action.</span></span> <span data-ttu-id="77d7b-147">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="77d7b-147">**Required**.</span></span>
<span data-ttu-id="77d7b-148">ScanType</span><span class="sxs-lookup"><span data-stu-id="77d7b-148">ScanType</span></span>|   <span data-ttu-id="77d7b-149">String</span><span class="sxs-lookup"><span data-stu-id="77d7b-149">String</span></span>  | <span data-ttu-id="77d7b-150">Definiert den Typ des Scans.</span><span class="sxs-lookup"><span data-stu-id="77d7b-150">Defines the type of the Scan.</span></span> <span data-ttu-id="77d7b-151">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="77d7b-151">**Required**.</span></span>

<span data-ttu-id="77d7b-152">**ScanType** steuert den typ des durchzuführenden Scans und kann eine der folgenden Sein:</span><span class="sxs-lookup"><span data-stu-id="77d7b-152">**ScanType** controls the type of scan to perform and can be one of the following:</span></span>

- <span data-ttu-id="77d7b-153">**Schnell** – Durchführen eines Schnellscans auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="77d7b-153">**Quick** – Perform quick scan on the device</span></span>
- <span data-ttu-id="77d7b-154">**Vollständig** – Vollständige Überprüfung auf dem Gerät durchführen</span><span class="sxs-lookup"><span data-stu-id="77d7b-154">**Full** – Perform full scan on the device</span></span>



## <a name="response"></a><span data-ttu-id="77d7b-155">Antwort</span><span class="sxs-lookup"><span data-stu-id="77d7b-155">Response</span></span>
<span data-ttu-id="77d7b-156">Wenn die Methode erfolgreich ist, werden der Antwortcode "201" und das MachineAction -Objekt im Antworttext zurückgegeben. </span><span class="sxs-lookup"><span data-stu-id="77d7b-156">If successful, this method returns 201, Created response code and _MachineAction_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="77d7b-157">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77d7b-157">Example</span></span>

<span data-ttu-id="77d7b-158">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="77d7b-158">**Request**</span></span>

<span data-ttu-id="77d7b-159">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="77d7b-159">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```

