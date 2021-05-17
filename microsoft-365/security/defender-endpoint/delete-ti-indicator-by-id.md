---
title: Indikator-API löschen.
description: Erfahren Sie, wie Sie die Delete Indicator-API verwenden, um eine Indicator-Entität nach ID in Microsoft Defender for Endpoint zu löschen.
keywords: apis, public api, supported apis, delete, ti indicator, entity, id
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
ms.openlocfilehash: 1305be897dff6932713cf294eb4e5cd53692681c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166692"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="e3dc5-104">Indikator-API löschen</span><span class="sxs-lookup"><span data-stu-id="e3dc5-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e3dc5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e3dc5-105">**Applies to:**</span></span>
- [<span data-ttu-id="e3dc5-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e3dc5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e3dc5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3dc5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e3dc5-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="e3dc5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e3dc5-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e3dc5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e3dc5-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3dc5-110">API description</span></span>
<span data-ttu-id="e3dc5-111">Löscht eine [Indicator-Entität](ti-indicator.md) nach ID.</span><span class="sxs-lookup"><span data-stu-id="e3dc5-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="e3dc5-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e3dc5-112">Limitations</span></span>
1. <span data-ttu-id="e3dc5-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="e3dc5-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="e3dc5-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e3dc5-114">Permissions</span></span>
<span data-ttu-id="e3dc5-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e3dc5-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e3dc5-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Erste Schritte](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e3dc5-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="e3dc5-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="e3dc5-117">Permission type</span></span> |   <span data-ttu-id="e3dc5-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e3dc5-118">Permission</span></span>  |   <span data-ttu-id="e3dc5-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e3dc5-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e3dc5-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="e3dc5-120">Application</span></span> |   <span data-ttu-id="e3dc5-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e3dc5-121">Ti.ReadWrite</span></span> |  <span data-ttu-id="e3dc5-122">"LESE- und Schreibzugriffsindikatoren"</span><span class="sxs-lookup"><span data-stu-id="e3dc5-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="e3dc5-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="e3dc5-123">Application</span></span> |   <span data-ttu-id="e3dc5-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e3dc5-124">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="e3dc5-125">"Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="e3dc5-125">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="e3dc5-126">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="e3dc5-126">HTTP request</span></span>
```
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="e3dc5-127">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="e3dc5-127">Request headers</span></span>

<span data-ttu-id="e3dc5-128">Name</span><span class="sxs-lookup"><span data-stu-id="e3dc5-128">Name</span></span> | <span data-ttu-id="e3dc5-129">Typ</span><span class="sxs-lookup"><span data-stu-id="e3dc5-129">Type</span></span> | <span data-ttu-id="e3dc5-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3dc5-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="e3dc5-131">Authorization</span><span class="sxs-lookup"><span data-stu-id="e3dc5-131">Authorization</span></span> | <span data-ttu-id="e3dc5-132">String</span><span class="sxs-lookup"><span data-stu-id="e3dc5-132">String</span></span> | <span data-ttu-id="e3dc5-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e3dc5-133">Bearer {token}.</span></span> <span data-ttu-id="e3dc5-134">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="e3dc5-134">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e3dc5-135">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="e3dc5-135">Request body</span></span>
<span data-ttu-id="e3dc5-136">Empty</span><span class="sxs-lookup"><span data-stu-id="e3dc5-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e3dc5-137">Antwort</span><span class="sxs-lookup"><span data-stu-id="e3dc5-137">Response</span></span>
<span data-ttu-id="e3dc5-138">If Indicator exist and deleted successfully - 204 OK without content.</span><span class="sxs-lookup"><span data-stu-id="e3dc5-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>
<span data-ttu-id="e3dc5-139">If Indicator with the specified id was not found - 404 Not Found.</span><span class="sxs-lookup"><span data-stu-id="e3dc5-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="e3dc5-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e3dc5-140">Example</span></span>

<span data-ttu-id="e3dc5-141">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="e3dc5-141">**Request**</span></span>

<span data-ttu-id="e3dc5-142">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="e3dc5-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
