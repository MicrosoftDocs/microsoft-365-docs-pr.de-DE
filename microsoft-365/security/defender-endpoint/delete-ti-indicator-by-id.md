---
title: Indikator-API löschen.
description: Erfahren Sie, wie Sie die Indikator-API zum Löschen einer Indikatorentität nach ID in Microsoft Defender für Endpunkt verwenden.
keywords: APIs, öffentliche API, unterstützte APIs, löschen, TI-Indikator, Entität, ID
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
ms.openlocfilehash: 1541e1d6e177416d77d768cef04d2524e6907ab5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289919"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="f4006-104">Indikator-API löschen</span><span class="sxs-lookup"><span data-stu-id="f4006-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f4006-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f4006-105">**Applies to:**</span></span>
- [<span data-ttu-id="f4006-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f4006-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f4006-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4006-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f4006-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="f4006-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f4006-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="f4006-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f4006-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4006-110">API description</span></span>

<span data-ttu-id="f4006-111">Löscht eine [](ti-indicator.md) Indikatorentität nach ID.</span><span class="sxs-lookup"><span data-stu-id="f4006-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="f4006-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f4006-112">Limitations</span></span>

<span data-ttu-id="f4006-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="f4006-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="f4006-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f4006-114">Permissions</span></span>

<span data-ttu-id="f4006-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f4006-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f4006-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter ["Erste Schritte".](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f4006-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="f4006-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="f4006-117">Permission type</span></span> | <span data-ttu-id="f4006-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f4006-118">Permission</span></span> | <span data-ttu-id="f4006-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f4006-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f4006-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f4006-120">Application</span></span> | <span data-ttu-id="f4006-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f4006-121">Ti.ReadWrite</span></span> | <span data-ttu-id="f4006-122">"TI-Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="f4006-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="f4006-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f4006-123">Application</span></span> | <span data-ttu-id="f4006-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4006-124">Ti.ReadWrite.All</span></span> | <span data-ttu-id="f4006-125">"Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="f4006-125">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="f4006-126">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="f4006-126">HTTP request</span></span>

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="f4006-127">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="f4006-127">Request headers</span></span>

<span data-ttu-id="f4006-128">Name</span><span class="sxs-lookup"><span data-stu-id="f4006-128">Name</span></span> | <span data-ttu-id="f4006-129">Typ</span><span class="sxs-lookup"><span data-stu-id="f4006-129">Type</span></span> | <span data-ttu-id="f4006-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4006-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="f4006-131">Authorization</span><span class="sxs-lookup"><span data-stu-id="f4006-131">Authorization</span></span> | <span data-ttu-id="f4006-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4006-132">String</span></span> | <span data-ttu-id="f4006-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f4006-133">Bearer {token}.</span></span> <span data-ttu-id="f4006-134">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="f4006-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f4006-135">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="f4006-135">Request body</span></span>

<span data-ttu-id="f4006-136">Empty</span><span class="sxs-lookup"><span data-stu-id="f4006-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f4006-137">Antwort</span><span class="sxs-lookup"><span data-stu-id="f4006-137">Response</span></span>

<span data-ttu-id="f4006-138">Wenn Indikator vorhanden und erfolgreich gelöscht – 204 OK ohne Inhalt.</span><span class="sxs-lookup"><span data-stu-id="f4006-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>

<span data-ttu-id="f4006-139">Wenn indikator mit der angegebenen ID nicht gefunden wurde - 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="f4006-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="f4006-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f4006-140">Example</span></span>

### <a name="request"></a><span data-ttu-id="f4006-141">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f4006-141">Request</span></span>

<span data-ttu-id="f4006-142">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="f4006-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
