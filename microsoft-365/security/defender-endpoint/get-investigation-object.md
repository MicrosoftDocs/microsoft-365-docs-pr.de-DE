---
title: Abrufen der Investigation-Objekt-API
description: Verwenden dieser API zum Erstellen von Aufrufen im Zusammenhang mit dem Abrufen des Investigation-Objekts
keywords: apis, graph api, supported apis, Investigation object
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
ms.openlocfilehash: 9f011f10a9fe3c3aec535e157abee2367998b1a4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166528"
---
# <a name="get-investigation-api"></a><span data-ttu-id="f7f42-104">Abrufen der Untersuchungs-API</span><span class="sxs-lookup"><span data-stu-id="f7f42-104">Get Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f7f42-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f7f42-105">**Applies to:**</span></span>
- [<span data-ttu-id="f7f42-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f7f42-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f7f42-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7f42-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f7f42-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f7f42-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f7f42-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f7f42-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f7f42-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7f42-110">API description</span></span>
<span data-ttu-id="f7f42-111">Ruft eine bestimmte [Untersuchung nach](investigation.md) seiner ID ab.</span><span class="sxs-lookup"><span data-stu-id="f7f42-111">Retrieves specific [Investigation](investigation.md) by its ID.</span></span>
<br> <span data-ttu-id="f7f42-112">ID kann die Untersuchungs-ID oder die Benachrichtigungs-ID sein, die die Untersuchung auslöst.</span><span class="sxs-lookup"><span data-stu-id="f7f42-112">ID can be the investigation ID or the investigation triggering alert ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="f7f42-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f7f42-113">Limitations</span></span>
1. <span data-ttu-id="f7f42-114">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="f7f42-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="f7f42-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f7f42-115">Permissions</span></span>
<span data-ttu-id="f7f42-116">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f7f42-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f7f42-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f7f42-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f7f42-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="f7f42-118">Permission type</span></span> |   <span data-ttu-id="f7f42-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f7f42-119">Permission</span></span>  |   <span data-ttu-id="f7f42-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f7f42-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f7f42-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f7f42-121">Application</span></span> |   <span data-ttu-id="f7f42-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="f7f42-122">Alert.Read.All</span></span> |    <span data-ttu-id="f7f42-123">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="f7f42-123">'Read all alerts'</span></span>
<span data-ttu-id="f7f42-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f7f42-124">Application</span></span> |   <span data-ttu-id="f7f42-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f7f42-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="f7f42-126">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="f7f42-126">'Read and write all alerts'</span></span>
<span data-ttu-id="f7f42-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="f7f42-127">Delegated (work or school account)</span></span> | <span data-ttu-id="f7f42-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="f7f42-128">Alert.Read</span></span> | <span data-ttu-id="f7f42-129">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="f7f42-129">'Read alerts'</span></span>
<span data-ttu-id="f7f42-130">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="f7f42-130">Delegated (work or school account)</span></span> | <span data-ttu-id="f7f42-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f7f42-131">Alert.ReadWrite</span></span> | <span data-ttu-id="f7f42-132">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="f7f42-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="f7f42-133">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="f7f42-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f7f42-134">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="f7f42-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f7f42-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="f7f42-135">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="f7f42-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="f7f42-136">Request headers</span></span>

<span data-ttu-id="f7f42-137">Name</span><span class="sxs-lookup"><span data-stu-id="f7f42-137">Name</span></span> | <span data-ttu-id="f7f42-138">Typ</span><span class="sxs-lookup"><span data-stu-id="f7f42-138">Type</span></span> | <span data-ttu-id="f7f42-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7f42-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="f7f42-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="f7f42-140">Authorization</span></span> | <span data-ttu-id="f7f42-141">String</span><span class="sxs-lookup"><span data-stu-id="f7f42-141">String</span></span> | <span data-ttu-id="f7f42-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f7f42-142">Bearer {token}.</span></span> <span data-ttu-id="f7f42-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="f7f42-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f7f42-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="f7f42-144">Request body</span></span>
<span data-ttu-id="f7f42-145">Empty</span><span class="sxs-lookup"><span data-stu-id="f7f42-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f7f42-146">Antwort</span><span class="sxs-lookup"><span data-stu-id="f7f42-146">Response</span></span>
<span data-ttu-id="f7f42-147">Wenn die Methode erfolgreich ist, gibt sie den Antwortcode "200, Ok" mit einer [Investigations-Entität](investigation.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="f7f42-147">If successful, this method returns 200, Ok response code with a [Investigations](investigation.md) entity.</span></span>

