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
ms.openlocfilehash: 2e051803a4cd228e3b455ec08b30e5c2197ca9a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289607"
---
# <a name="get-incident-information-api"></a><span data-ttu-id="67ffb-104">Api zum Abrufen von Vorfallinformationen</span><span class="sxs-lookup"><span data-stu-id="67ffb-104">Get incident information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="67ffb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="67ffb-105">**Applies to:**</span></span>
- [<span data-ttu-id="67ffb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67ffb-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="67ffb-107">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="67ffb-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="67ffb-108">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="67ffb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="67ffb-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67ffb-109">API description</span></span>

<span data-ttu-id="67ffb-110">Ruft einen bestimmten Vorfall anhand seiner ID ab.</span><span class="sxs-lookup"><span data-stu-id="67ffb-110">Retrieves a specific incident by its ID</span></span>

## <a name="limitations"></a><span data-ttu-id="67ffb-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="67ffb-111">Limitations</span></span>

1. <span data-ttu-id="67ffb-112">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="67ffb-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="67ffb-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="67ffb-113">Permissions</span></span>

<span data-ttu-id="67ffb-114">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="67ffb-114">One of the following permissions is required to call this API.</span></span> 

<span data-ttu-id="67ffb-115">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="67ffb-115">Permission type</span></span> | <span data-ttu-id="67ffb-116">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="67ffb-116">Permission</span></span> | <span data-ttu-id="67ffb-117">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="67ffb-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="67ffb-118">Anwendung</span><span class="sxs-lookup"><span data-stu-id="67ffb-118">Application</span></span> | <span data-ttu-id="67ffb-119">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="67ffb-119">Incident.Read.All</span></span> | <span data-ttu-id="67ffb-120">"Alle Vorfälle lesen"</span><span class="sxs-lookup"><span data-stu-id="67ffb-120">'Read all Incidents'</span></span>
<span data-ttu-id="67ffb-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="67ffb-121">Application</span></span> | <span data-ttu-id="67ffb-122">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="67ffb-122">Incident.ReadWrite.All</span></span> | <span data-ttu-id="67ffb-123">"Alle Vorfälle lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="67ffb-123">'Read and write all Incidents'</span></span>
<span data-ttu-id="67ffb-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="67ffb-124">Delegated (work or school account)</span></span> | <span data-ttu-id="67ffb-125">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="67ffb-125">Incident.Read</span></span> | <span data-ttu-id="67ffb-126">"Vorfälle lesen"</span><span class="sxs-lookup"><span data-stu-id="67ffb-126">'Read Incidents'</span></span>
<span data-ttu-id="67ffb-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="67ffb-127">Delegated (work or school account)</span></span> | <span data-ttu-id="67ffb-128">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="67ffb-128">Incident.ReadWrite</span></span> | <span data-ttu-id="67ffb-129">"Vorfälle lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="67ffb-129">'Read and write Incidents'</span></span>

> [!NOTE]
>
> <span data-ttu-id="67ffb-130">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="67ffb-130">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="67ffb-131">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen".</span><span class="sxs-lookup"><span data-stu-id="67ffb-131">The user needs to have at least the following role permission: 'View Data'</span></span>
> - <span data-ttu-id="67ffb-132">Die Antwort enthält nur Vorfälle, denen der Benutzer ausgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="67ffb-132">The response will only include incidents that the user is exposed to</span></span>

## <a name="http-request"></a><span data-ttu-id="67ffb-133">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="67ffb-133">HTTP request</span></span>

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a><span data-ttu-id="67ffb-134">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="67ffb-134">Request headers</span></span>

<span data-ttu-id="67ffb-135">Name</span><span class="sxs-lookup"><span data-stu-id="67ffb-135">Name</span></span> | <span data-ttu-id="67ffb-136">Typ</span><span class="sxs-lookup"><span data-stu-id="67ffb-136">Type</span></span> | <span data-ttu-id="67ffb-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67ffb-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="67ffb-138">Authorization</span><span class="sxs-lookup"><span data-stu-id="67ffb-138">Authorization</span></span> | <span data-ttu-id="67ffb-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="67ffb-139">String</span></span> | <span data-ttu-id="67ffb-140">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="67ffb-140">Bearer {token}.</span></span> <span data-ttu-id="67ffb-141">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="67ffb-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="67ffb-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="67ffb-142">Request body</span></span>

<span data-ttu-id="67ffb-143">Empty</span><span class="sxs-lookup"><span data-stu-id="67ffb-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="67ffb-144">Antwort</span><span class="sxs-lookup"><span data-stu-id="67ffb-144">Response</span></span>

<span data-ttu-id="67ffb-145">Wenn die Methode erfolgreich ist, werden 200 OK und die Vorfallentität im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="67ffb-145">If successful, this method returns 200 OK, and the incident entity in the response body.</span></span> <span data-ttu-id="67ffb-146">Wenn ein Vorfall mit der angegebenen ID nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="67ffb-146">If incident with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="67ffb-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67ffb-147">Example</span></span>

<span data-ttu-id="67ffb-148">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="67ffb-148">**Request**</span></span>

<span data-ttu-id="67ffb-149">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="67ffb-149">Here is an example of the request.</span></span>

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
