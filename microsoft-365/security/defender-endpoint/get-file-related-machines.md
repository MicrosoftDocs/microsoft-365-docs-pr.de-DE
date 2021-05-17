---
title: Abrufen der API für dateibezogene Computer
description: Erfahren Sie, wie Sie die API Dateibezogene Computer abrufen verwenden, um eine Sammlung von Computern im Zusammenhang mit einem Dateihash in Microsoft Defender for Endpoint zu erhalten.
keywords: apis, graph api, supported apis, get, devices, hash
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
ms.openlocfilehash: 051bdad362e142446d248e90fad608fe5c0f016f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166539"
---
# <a name="get-file-related-machines-api"></a><span data-ttu-id="cd577-104">Abrufen der API für dateibezogene Computer</span><span class="sxs-lookup"><span data-stu-id="cd577-104">Get file-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cd577-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cd577-105">**Applies to:**</span></span>
- [<span data-ttu-id="cd577-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cd577-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cd577-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd577-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cd577-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="cd577-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cd577-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cd577-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="cd577-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd577-110">API description</span></span>
<span data-ttu-id="cd577-111">Ruft eine Sammlung von [Computern ab, die](machine.md) mit einem bestimmten Dateihash verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="cd577-111">Retrieves a collection of [Machines](machine.md) related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="cd577-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="cd577-112">Limitations</span></span>
1. <span data-ttu-id="cd577-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="cd577-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="cd577-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cd577-114">Permissions</span></span>
<span data-ttu-id="cd577-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cd577-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cd577-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cd577-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="cd577-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="cd577-117">Permission type</span></span> |   <span data-ttu-id="cd577-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="cd577-118">Permission</span></span>  |   <span data-ttu-id="cd577-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="cd577-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cd577-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="cd577-120">Application</span></span> |   <span data-ttu-id="cd577-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="cd577-121">Machine.Read.All</span></span> |  <span data-ttu-id="cd577-122">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="cd577-122">'Read all machine profiles'</span></span>
<span data-ttu-id="cd577-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="cd577-123">Application</span></span> |   <span data-ttu-id="cd577-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cd577-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="cd577-125">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="cd577-125">'Read and write all machine information'</span></span>
<span data-ttu-id="cd577-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="cd577-126">Delegated (work or school account)</span></span> | <span data-ttu-id="cd577-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="cd577-127">Machine.Read</span></span> | <span data-ttu-id="cd577-128">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="cd577-128">'Read machine information'</span></span>
<span data-ttu-id="cd577-129">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="cd577-129">Delegated (work or school account)</span></span> | <span data-ttu-id="cd577-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="cd577-130">Machine.ReadWrite</span></span> | <span data-ttu-id="cd577-131">"Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="cd577-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="cd577-132">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="cd577-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="cd577-133">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="cd577-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="cd577-134">Die Antwort umfasst nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="cd577-134">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="cd577-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="cd577-135">HTTP request</span></span>
```
GET /api/files/{id}/machines
```

## <a name="request-headers"></a><span data-ttu-id="cd577-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="cd577-136">Request headers</span></span>

<span data-ttu-id="cd577-137">Name</span><span class="sxs-lookup"><span data-stu-id="cd577-137">Name</span></span> | <span data-ttu-id="cd577-138">Typ</span><span class="sxs-lookup"><span data-stu-id="cd577-138">Type</span></span> | <span data-ttu-id="cd577-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd577-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="cd577-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="cd577-140">Authorization</span></span> | <span data-ttu-id="cd577-141">String</span><span class="sxs-lookup"><span data-stu-id="cd577-141">String</span></span> | <span data-ttu-id="cd577-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="cd577-142">Bearer {token}.</span></span> <span data-ttu-id="cd577-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="cd577-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="cd577-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="cd577-144">Request body</span></span>
<span data-ttu-id="cd577-145">Empty</span><span class="sxs-lookup"><span data-stu-id="cd577-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cd577-146">Antwort</span><span class="sxs-lookup"><span data-stu-id="cd577-146">Response</span></span>
<span data-ttu-id="cd577-147">Wenn erfolgreich und Datei vorhanden ist – [](machine.md) 200 OK mit liste der Computerentitäten im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="cd577-147">If successful and file exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="cd577-148">Wenn die Datei nicht vorhanden ist – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="cd577-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="cd577-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd577-149">Example</span></span>

<span data-ttu-id="cd577-150">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="cd577-150">**Request**</span></span>

<span data-ttu-id="cd577-151">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cd577-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
