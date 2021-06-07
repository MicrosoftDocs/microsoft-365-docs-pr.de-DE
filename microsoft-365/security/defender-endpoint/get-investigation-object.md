---
title: Abrufen der Untersuchungsobjekt-API
description: Verwenden Sie diese API, um Aufrufe im Zusammenhang mit dem Abrufen des Investigation-Objekts zu erstellen.
keywords: APIs, Graph-API, unterstützte APIs, Untersuchungsobjekt
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
ms.openlocfilehash: 001b8dcf4b0bfd2550f41454fc840602a6e4361f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770131"
---
# <a name="get-investigation-api"></a><span data-ttu-id="0a157-104">Abrufen der Untersuchungs-API</span><span class="sxs-lookup"><span data-stu-id="0a157-104">Get Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0a157-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0a157-105">**Applies to:**</span></span>
- [<span data-ttu-id="0a157-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0a157-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0a157-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a157-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0a157-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="0a157-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0a157-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0a157-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="0a157-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a157-110">API description</span></span>
<span data-ttu-id="0a157-111">Ruft eine bestimmte [Untersuchung](investigation.md) anhand ihrer ID ab.</span><span class="sxs-lookup"><span data-stu-id="0a157-111">Retrieves specific [Investigation](investigation.md) by its ID.</span></span>
<br> <span data-ttu-id="0a157-112">Die ID kann die Untersuchungs-ID oder die Warnungs-ID sein, die die Untersuchung auslöst.</span><span class="sxs-lookup"><span data-stu-id="0a157-112">ID can be the investigation ID or the investigation triggering alert ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="0a157-113">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="0a157-113">Limitations</span></span>
1. <span data-ttu-id="0a157-114">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="0a157-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="0a157-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0a157-115">Permissions</span></span>
<span data-ttu-id="0a157-116">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0a157-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0a157-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0a157-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="0a157-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="0a157-118">Permission type</span></span> |   <span data-ttu-id="0a157-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0a157-119">Permission</span></span>  |   <span data-ttu-id="0a157-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0a157-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0a157-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="0a157-121">Application</span></span> |   <span data-ttu-id="0a157-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="0a157-122">Alert.Read.All</span></span> |    <span data-ttu-id="0a157-123">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="0a157-123">'Read all alerts'</span></span>
<span data-ttu-id="0a157-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="0a157-124">Application</span></span> |   <span data-ttu-id="0a157-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="0a157-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="0a157-126">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="0a157-126">'Read and write all alerts'</span></span>
<span data-ttu-id="0a157-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="0a157-127">Delegated (work or school account)</span></span> | <span data-ttu-id="0a157-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="0a157-128">Alert.Read</span></span> | <span data-ttu-id="0a157-129">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="0a157-129">'Read alerts'</span></span>
<span data-ttu-id="0a157-130">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="0a157-130">Delegated (work or school account)</span></span> | <span data-ttu-id="0a157-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0a157-131">Alert.ReadWrite</span></span> | <span data-ttu-id="0a157-132">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="0a157-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="0a157-133">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="0a157-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="0a157-134">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0a157-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="0a157-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="0a157-135">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="0a157-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="0a157-136">Request headers</span></span>

<span data-ttu-id="0a157-137">Name</span><span class="sxs-lookup"><span data-stu-id="0a157-137">Name</span></span> | <span data-ttu-id="0a157-138">Typ</span><span class="sxs-lookup"><span data-stu-id="0a157-138">Type</span></span> | <span data-ttu-id="0a157-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a157-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="0a157-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="0a157-140">Authorization</span></span> | <span data-ttu-id="0a157-141">String</span><span class="sxs-lookup"><span data-stu-id="0a157-141">String</span></span> | <span data-ttu-id="0a157-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="0a157-142">Bearer {token}.</span></span> <span data-ttu-id="0a157-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0a157-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0a157-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="0a157-144">Request body</span></span>
<span data-ttu-id="0a157-145">Empty</span><span class="sxs-lookup"><span data-stu-id="0a157-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0a157-146">Antwort</span><span class="sxs-lookup"><span data-stu-id="0a157-146">Response</span></span>
<span data-ttu-id="0a157-147">Bei erfolgreicher Ausführung gibt die Methode den Antwortcode 200,OK mit einer [ Investigations -Entität zurück.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="0a157-147">If successful, this method returns 200, Ok response code with a [Investigations](investigation.md) entity.</span></span>

