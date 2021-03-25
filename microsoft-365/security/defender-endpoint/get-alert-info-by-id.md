---
title: Abrufen von Warnungsinformationen über die ID-API
description: Erfahren Sie, wie Sie mithilfe der API Abrufen von Warnungsinformationen nach ID eine bestimmte Warnung mithilfe ihrer ID in Microsoft Defender for Endpoint abrufen.
keywords: apis, graph api, supported apis, get, alert, information, id
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
ms.openlocfilehash: f9130b054ccea762e6c5cc4f2952bbfa82d24b83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200425"
---
# <a name="get-alert-information-by-id-api"></a><span data-ttu-id="9f527-104">Abrufen von Warnungsinformationen über die ID-API</span><span class="sxs-lookup"><span data-stu-id="9f527-104">Get alert information by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9f527-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9f527-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="9f527-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9f527-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9f527-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9f527-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9f527-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f527-108">API description</span></span>
<span data-ttu-id="9f527-109">Ruft eine bestimmte [Warnung nach](alerts.md) ihrer ID ab.</span><span class="sxs-lookup"><span data-stu-id="9f527-109">Retrieves specific [Alert](alerts.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="9f527-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="9f527-110">Limitations</span></span>
1. <span data-ttu-id="9f527-111">Sie können Warnungen nach Dem konfigurierten Aufbewahrungszeitraum zuletzt aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9f527-111">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="9f527-112">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="9f527-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="9f527-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9f527-113">Permissions</span></span>
<span data-ttu-id="9f527-114">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9f527-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9f527-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9f527-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9f527-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="9f527-116">Permission type</span></span> |   <span data-ttu-id="9f527-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9f527-117">Permission</span></span>  |   <span data-ttu-id="9f527-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9f527-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9f527-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="9f527-119">Application</span></span> |   <span data-ttu-id="9f527-120">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="9f527-120">Alert.Read.All</span></span> |    <span data-ttu-id="9f527-121">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="9f527-121">'Read all alerts'</span></span>
<span data-ttu-id="9f527-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="9f527-122">Application</span></span> |   <span data-ttu-id="9f527-123">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9f527-123">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="9f527-124">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="9f527-124">'Read and write all alerts'</span></span>
<span data-ttu-id="9f527-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="9f527-125">Delegated (work or school account)</span></span> | <span data-ttu-id="9f527-126">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="9f527-126">Alert.Read</span></span> | <span data-ttu-id="9f527-127">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="9f527-127">'Read alerts'</span></span>
<span data-ttu-id="9f527-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="9f527-128">Delegated (work or school account)</span></span> | <span data-ttu-id="9f527-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9f527-129">Alert.ReadWrite</span></span> | <span data-ttu-id="9f527-130">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="9f527-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="9f527-131">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="9f527-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9f527-132">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="9f527-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="9f527-133">Der Benutzer muss auf das Gerät zugreifen können, das der Warnung zugeordnet ist, basierend auf den Gerätegruppeneinstellungen (Weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen)</span><span class="sxs-lookup"><span data-stu-id="9f527-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9f527-134">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="9f527-134">HTTP request</span></span>
```
GET /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="9f527-135">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="9f527-135">Request headers</span></span>

<span data-ttu-id="9f527-136">Name</span><span class="sxs-lookup"><span data-stu-id="9f527-136">Name</span></span> | <span data-ttu-id="9f527-137">Typ</span><span class="sxs-lookup"><span data-stu-id="9f527-137">Type</span></span> | <span data-ttu-id="9f527-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f527-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="9f527-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="9f527-139">Authorization</span></span> | <span data-ttu-id="9f527-140">String</span><span class="sxs-lookup"><span data-stu-id="9f527-140">String</span></span> | <span data-ttu-id="9f527-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="9f527-141">Bearer {token}.</span></span> <span data-ttu-id="9f527-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="9f527-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9f527-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="9f527-143">Request body</span></span>
<span data-ttu-id="9f527-144">Empty</span><span class="sxs-lookup"><span data-stu-id="9f527-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9f527-145">Antwort</span><span class="sxs-lookup"><span data-stu-id="9f527-145">Response</span></span>
<span data-ttu-id="9f527-146">Wenn die Methode erfolgreich ist, werden 200 OK und die Warnungsentität im Antworttext zurückgegeben. [](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="9f527-146">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body.</span></span> <span data-ttu-id="9f527-147">Wenn eine Warnung mit der angegebenen ID nicht gefunden wurde - 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="9f527-147">If alert with the specified id was not found - 404 Not Found.</span></span>
