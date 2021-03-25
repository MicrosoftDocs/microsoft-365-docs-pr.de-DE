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
# <a name="get-investigation-api"></a><span data-ttu-id="c7727-104">Abrufen der Untersuchungs-API</span><span class="sxs-lookup"><span data-stu-id="c7727-104">Get Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c7727-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c7727-105">**Applies to:**</span></span>
- [<span data-ttu-id="c7727-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c7727-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c7727-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7727-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c7727-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="c7727-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c7727-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c7727-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c7727-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7727-110">API description</span></span>
<span data-ttu-id="c7727-111">Ruft eine bestimmte [Untersuchung nach](investigation.md) seiner ID ab.</span><span class="sxs-lookup"><span data-stu-id="c7727-111">Retrieves specific [Investigation](investigation.md) by its ID.</span></span>
<br> <span data-ttu-id="c7727-112">ID kann die Untersuchungs-ID oder die Benachrichtigungs-ID sein, die die Untersuchung auslöst.</span><span class="sxs-lookup"><span data-stu-id="c7727-112">ID can be the investigation ID or the investigation triggering alert ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="c7727-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c7727-113">Limitations</span></span>
1. <span data-ttu-id="c7727-114">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="c7727-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="c7727-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c7727-115">Permissions</span></span>
<span data-ttu-id="c7727-116">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c7727-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c7727-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c7727-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c7727-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="c7727-118">Permission type</span></span> |   <span data-ttu-id="c7727-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c7727-119">Permission</span></span>  |   <span data-ttu-id="c7727-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c7727-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c7727-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="c7727-121">Application</span></span> |   <span data-ttu-id="c7727-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="c7727-122">Alert.Read.All</span></span> |    <span data-ttu-id="c7727-123">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="c7727-123">'Read all alerts'</span></span>
<span data-ttu-id="c7727-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="c7727-124">Application</span></span> |   <span data-ttu-id="c7727-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c7727-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="c7727-126">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="c7727-126">'Read and write all alerts'</span></span>
<span data-ttu-id="c7727-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="c7727-127">Delegated (work or school account)</span></span> | <span data-ttu-id="c7727-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="c7727-128">Alert.Read</span></span> | <span data-ttu-id="c7727-129">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="c7727-129">'Read alerts'</span></span>
<span data-ttu-id="c7727-130">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="c7727-130">Delegated (work or school account)</span></span> | <span data-ttu-id="c7727-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c7727-131">Alert.ReadWrite</span></span> | <span data-ttu-id="c7727-132">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="c7727-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="c7727-133">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="c7727-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c7727-134">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="c7727-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c7727-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="c7727-135">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="c7727-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="c7727-136">Request headers</span></span>

<span data-ttu-id="c7727-137">Name</span><span class="sxs-lookup"><span data-stu-id="c7727-137">Name</span></span> | <span data-ttu-id="c7727-138">Typ</span><span class="sxs-lookup"><span data-stu-id="c7727-138">Type</span></span> | <span data-ttu-id="c7727-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7727-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="c7727-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="c7727-140">Authorization</span></span> | <span data-ttu-id="c7727-141">String</span><span class="sxs-lookup"><span data-stu-id="c7727-141">String</span></span> | <span data-ttu-id="c7727-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c7727-142">Bearer {token}.</span></span> <span data-ttu-id="c7727-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="c7727-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="c7727-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="c7727-144">Request body</span></span>
<span data-ttu-id="c7727-145">Empty</span><span class="sxs-lookup"><span data-stu-id="c7727-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c7727-146">Antwort</span><span class="sxs-lookup"><span data-stu-id="c7727-146">Response</span></span>
<span data-ttu-id="c7727-147">Wenn die Methode erfolgreich ist, gibt sie den Antwortcode "200, Ok" mit einer [Investigations-Entität](investigation.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="c7727-147">If successful, this method returns 200, Ok response code with a [Investigations](investigation.md) entity.</span></span>

