---
title: API zum Abrufen computerbezogener Warnungen
description: Erfahren Sie, wie Sie die API zum Abrufen computerbezogener Warnungen verwenden, um alle Warnungen im Zusammenhang mit einem bestimmten Gerät in Microsoft Defender für Endpunkt abzurufen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Geräte, verwandte, Warnungen
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: bf445332fed7b8661c510bf60f36088b79e2d8df
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770025"
---
# <a name="get-machine-related-alerts--api"></a><span data-ttu-id="418d5-104">API zum Abrufen computerbezogener Warnungen</span><span class="sxs-lookup"><span data-stu-id="418d5-104">Get machine related alerts  API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="418d5-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="418d5-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="418d5-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="418d5-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="418d5-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="418d5-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="418d5-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="418d5-108">API description</span></span>
<span data-ttu-id="418d5-109">Ruft alle [Warnungen](alerts.md) im Zusammenhang mit einem bestimmten Gerät ab.</span><span class="sxs-lookup"><span data-stu-id="418d5-109">Retrieves all [Alerts](alerts.md) related to a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="418d5-110">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="418d5-110">Limitations</span></span>
1. <span data-ttu-id="418d5-111">Sie können Abfragen auf Geräten durchführen, die zuletzt gemäß ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="418d5-111">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="418d5-112">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="418d5-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


<span data-ttu-id="418d5-113">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="418d5-113">Permission type</span></span> |   <span data-ttu-id="418d5-114">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="418d5-114">Permission</span></span>  |   <span data-ttu-id="418d5-115">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="418d5-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="418d5-116">Anwendung</span><span class="sxs-lookup"><span data-stu-id="418d5-116">Application</span></span> |   <span data-ttu-id="418d5-117">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="418d5-117">Alert.Read.All</span></span> |    <span data-ttu-id="418d5-118">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="418d5-118">'Read all alerts'</span></span>
<span data-ttu-id="418d5-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="418d5-119">Application</span></span> |   <span data-ttu-id="418d5-120">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="418d5-120">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="418d5-121">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="418d5-121">'Read and write all alerts'</span></span>
<span data-ttu-id="418d5-122">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="418d5-122">Delegated (work or school account)</span></span> | <span data-ttu-id="418d5-123">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="418d5-123">Alert.Read</span></span> | <span data-ttu-id="418d5-124">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="418d5-124">'Read alerts'</span></span>
<span data-ttu-id="418d5-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="418d5-125">Delegated (work or school account)</span></span> | <span data-ttu-id="418d5-126">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="418d5-126">Alert.ReadWrite</span></span> | <span data-ttu-id="418d5-127">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="418d5-127">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="418d5-128">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="418d5-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="418d5-129">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="418d5-129">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="418d5-130">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="418d5-130">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="418d5-131">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="418d5-131">HTTP request</span></span>
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="418d5-132">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="418d5-132">Request headers</span></span>

<span data-ttu-id="418d5-133">Name</span><span class="sxs-lookup"><span data-stu-id="418d5-133">Name</span></span> | <span data-ttu-id="418d5-134">Typ</span><span class="sxs-lookup"><span data-stu-id="418d5-134">Type</span></span> | <span data-ttu-id="418d5-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="418d5-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="418d5-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="418d5-136">Authorization</span></span> | <span data-ttu-id="418d5-137">String</span><span class="sxs-lookup"><span data-stu-id="418d5-137">String</span></span> | <span data-ttu-id="418d5-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="418d5-138">Bearer {token}.</span></span> <span data-ttu-id="418d5-139">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="418d5-139">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="418d5-140">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="418d5-140">Request body</span></span>
<span data-ttu-id="418d5-141">Empty</span><span class="sxs-lookup"><span data-stu-id="418d5-141">Empty</span></span>

## <a name="response"></a><span data-ttu-id="418d5-142">Antwort</span><span class="sxs-lookup"><span data-stu-id="418d5-142">Response</span></span>
<span data-ttu-id="418d5-143">Wenn erfolgreich und Gerät vorhanden – 200 OK mit Liste der Warnungsentitäten im Textkörper. [](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="418d5-143">If successful and device exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="418d5-144">Wenn das Gerät nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="418d5-144">If device was not found - 404 Not Found.</span></span>
