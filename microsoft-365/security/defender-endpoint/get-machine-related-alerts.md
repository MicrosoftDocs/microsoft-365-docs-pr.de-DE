---
title: Abrufen der computerbezogenen Warnungen-API
description: Erfahren Sie, wie Sie die API Computerbezogene Warnungen abrufen verwenden, um alle Warnungen im Zusammenhang mit einem bestimmten Gerät in Microsoft Defender for Endpoint abzurufen.
keywords: apis, graph api, supported apis, get, devices, related, alerts
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 837643bf5793437380a6f33c0eeca55ccef2100b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199251"
---
# <a name="get-machine-related-alerts--api"></a><span data-ttu-id="b5066-104">Abrufen der computerbezogenen Warnungen-API</span><span class="sxs-lookup"><span data-stu-id="b5066-104">Get machine related alerts  API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b5066-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b5066-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b5066-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b5066-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b5066-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b5066-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="b5066-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5066-108">API description</span></span>
<span data-ttu-id="b5066-109">Ruft alle [Warnungen im](alerts.md) Zusammenhang mit einem bestimmten Gerät ab.</span><span class="sxs-lookup"><span data-stu-id="b5066-109">Retrieves all [Alerts](alerts.md) related to a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="b5066-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b5066-110">Limitations</span></span>
1. <span data-ttu-id="b5066-111">Sie können auf Geräten abfragen, die zuletzt entsprechend Ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b5066-111">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="b5066-112">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="b5066-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


<span data-ttu-id="b5066-113">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="b5066-113">Permission type</span></span> |   <span data-ttu-id="b5066-114">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b5066-114">Permission</span></span>  |   <span data-ttu-id="b5066-115">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b5066-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b5066-116">Anwendung</span><span class="sxs-lookup"><span data-stu-id="b5066-116">Application</span></span> |   <span data-ttu-id="b5066-117">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="b5066-117">Alert.Read.All</span></span> |    <span data-ttu-id="b5066-118">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="b5066-118">'Read all alerts'</span></span>
<span data-ttu-id="b5066-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="b5066-119">Application</span></span> |   <span data-ttu-id="b5066-120">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b5066-120">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="b5066-121">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="b5066-121">'Read and write all alerts'</span></span>
<span data-ttu-id="b5066-122">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="b5066-122">Delegated (work or school account)</span></span> | <span data-ttu-id="b5066-123">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="b5066-123">Alert.Read</span></span> | <span data-ttu-id="b5066-124">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="b5066-124">'Read alerts'</span></span>
<span data-ttu-id="b5066-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="b5066-125">Delegated (work or school account)</span></span> | <span data-ttu-id="b5066-126">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b5066-126">Alert.ReadWrite</span></span> | <span data-ttu-id="b5066-127">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="b5066-127">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="b5066-128">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="b5066-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b5066-129">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="b5066-129">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b5066-130">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="b5066-130">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b5066-131">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="b5066-131">HTTP request</span></span>
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="b5066-132">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="b5066-132">Request headers</span></span>

<span data-ttu-id="b5066-133">Name</span><span class="sxs-lookup"><span data-stu-id="b5066-133">Name</span></span> | <span data-ttu-id="b5066-134">Typ</span><span class="sxs-lookup"><span data-stu-id="b5066-134">Type</span></span> | <span data-ttu-id="b5066-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5066-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="b5066-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="b5066-136">Authorization</span></span> | <span data-ttu-id="b5066-137">String</span><span class="sxs-lookup"><span data-stu-id="b5066-137">String</span></span> | <span data-ttu-id="b5066-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b5066-138">Bearer {token}.</span></span> <span data-ttu-id="b5066-139">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b5066-139">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b5066-140">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="b5066-140">Request body</span></span>
<span data-ttu-id="b5066-141">Empty</span><span class="sxs-lookup"><span data-stu-id="b5066-141">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b5066-142">Antwort</span><span class="sxs-lookup"><span data-stu-id="b5066-142">Response</span></span>
<span data-ttu-id="b5066-143">Wenn erfolgreich und Gerät vorhanden ist – [](alerts.md) 200 OK mit Liste der Benachrichtigungsentitäten im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="b5066-143">If successful and device exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="b5066-144">Wenn das Gerät nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="b5066-144">If device was not found - 404 Not Found.</span></span>
