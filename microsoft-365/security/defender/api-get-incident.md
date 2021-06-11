---
title: Vorfall-API abrufen
description: Erfahren Sie, wie Sie die API zum Abrufen von Vorfällen verwenden, um einen einzelnen Vorfall in Microsoft 365 Defender abzurufen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Datei, Hash
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
ms.openlocfilehash: c578a353501ac7b38ac541b0200ffaad1d6743e1
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888448"
---
# <a name="get-incident-information-api"></a><span data-ttu-id="b0eac-104">Api zum Abrufen von Vorfallinformationen</span><span class="sxs-lookup"><span data-stu-id="b0eac-104">Get incident information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b0eac-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b0eac-105">**Applies to:**</span></span>
- [<span data-ttu-id="b0eac-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0eac-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b0eac-107">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="b0eac-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b0eac-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b0eac-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b0eac-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0eac-109">API description</span></span>
<span data-ttu-id="b0eac-110">Ruft einen bestimmten Vorfall anhand seiner ID ab.</span><span class="sxs-lookup"><span data-stu-id="b0eac-110">Retrieves a specific incident by its ID</span></span>


## <a name="limitations"></a><span data-ttu-id="b0eac-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b0eac-111">Limitations</span></span>
1. <span data-ttu-id="b0eac-112">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="b0eac-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="b0eac-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b0eac-113">Permissions</span></span>
<span data-ttu-id="b0eac-114">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b0eac-114">One of the following permissions is required to call this API.</span></span> 

<span data-ttu-id="b0eac-115">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="b0eac-115">Permission type</span></span> |   <span data-ttu-id="b0eac-116">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b0eac-116">Permission</span></span>  |   <span data-ttu-id="b0eac-117">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b0eac-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b0eac-118">Anwendung</span><span class="sxs-lookup"><span data-stu-id="b0eac-118">Application</span></span> |   <span data-ttu-id="b0eac-119">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="b0eac-119">Incident.Read.All</span></span> | <span data-ttu-id="b0eac-120">"Alle Vorfälle lesen"</span><span class="sxs-lookup"><span data-stu-id="b0eac-120">'Read all Incidents'</span></span>
<span data-ttu-id="b0eac-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="b0eac-121">Application</span></span> |   <span data-ttu-id="b0eac-122">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b0eac-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="b0eac-123">"Alle Vorfälle lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="b0eac-123">'Read and write all Incidents'</span></span>
<span data-ttu-id="b0eac-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="b0eac-124">Delegated (work or school account)</span></span> | <span data-ttu-id="b0eac-125">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="b0eac-125">Incident.Read</span></span> | <span data-ttu-id="b0eac-126">"Vorfälle lesen"</span><span class="sxs-lookup"><span data-stu-id="b0eac-126">'Read Incidents'</span></span>
<span data-ttu-id="b0eac-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="b0eac-127">Delegated (work or school account)</span></span> | <span data-ttu-id="b0eac-128">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b0eac-128">Incident.ReadWrite</span></span> | <span data-ttu-id="b0eac-129">"Vorfälle lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="b0eac-129">'Read and write Incidents'</span></span>

>[!Note]
> <span data-ttu-id="b0eac-130">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="b0eac-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b0eac-131">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen".</span><span class="sxs-lookup"><span data-stu-id="b0eac-131">The user needs to have at least the following role permission: 'View Data'</span></span>
>- <span data-ttu-id="b0eac-132">Die Antwort enthält nur Vorfälle, denen der Benutzer ausgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="b0eac-132">The response will only include incidents that the user is exposed to</span></span>

## <a name="http-request"></a><span data-ttu-id="b0eac-133">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="b0eac-133">HTTP request</span></span>

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a><span data-ttu-id="b0eac-134">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="b0eac-134">Request headers</span></span>

<span data-ttu-id="b0eac-135">Name</span><span class="sxs-lookup"><span data-stu-id="b0eac-135">Name</span></span> | <span data-ttu-id="b0eac-136">Typ</span><span class="sxs-lookup"><span data-stu-id="b0eac-136">Type</span></span> | <span data-ttu-id="b0eac-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0eac-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="b0eac-138">Authorization</span><span class="sxs-lookup"><span data-stu-id="b0eac-138">Authorization</span></span> | <span data-ttu-id="b0eac-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b0eac-139">String</span></span> | <span data-ttu-id="b0eac-140">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b0eac-140">Bearer {token}.</span></span> <span data-ttu-id="b0eac-141">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b0eac-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b0eac-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="b0eac-142">Request body</span></span>
<span data-ttu-id="b0eac-143">Empty</span><span class="sxs-lookup"><span data-stu-id="b0eac-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b0eac-144">Antwort</span><span class="sxs-lookup"><span data-stu-id="b0eac-144">Response</span></span>

<span data-ttu-id="b0eac-145">Wenn die Methode erfolgreich ist, werden 200 OK und die Vorfallentität im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b0eac-145">If successful, this method returns 200 OK, and the incident entity in the response body.</span></span> <span data-ttu-id="b0eac-146">Wenn ein Vorfall mit der angegebenen ID nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="b0eac-146">If incident with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="b0eac-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0eac-147">Example</span></span>

<span data-ttu-id="b0eac-148">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="b0eac-148">**Request**</span></span>

<span data-ttu-id="b0eac-149">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="b0eac-149">Here is an example of the request.</span></span>

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
