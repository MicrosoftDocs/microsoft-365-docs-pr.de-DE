---
title: Abrufen der API für dateibezogene Computer
description: Erfahren Sie, wie Sie die API zum Abrufen dateibezogener Computer verwenden, um eine Sammlung von Computern im Zusammenhang mit einem Dateihash in Microsoft Defender für Endpunkt abzurufen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Geräte, Hash
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
ms.openlocfilehash: 211a29bcd9265ae20c4f3e1817fcaaf562260d39
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770277"
---
# <a name="get-file-related-machines-api"></a><span data-ttu-id="d7f1c-104">Abrufen der API für dateibezogene Computer</span><span class="sxs-lookup"><span data-stu-id="d7f1c-104">Get file-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d7f1c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d7f1c-105">**Applies to:**</span></span>
- [<span data-ttu-id="d7f1c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d7f1c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d7f1c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7f1c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d7f1c-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="d7f1c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d7f1c-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d7f1c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d7f1c-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7f1c-110">API description</span></span>
<span data-ttu-id="d7f1c-111">Ruft eine Sammlung von [Computern](machine.md) im Zusammenhang mit einem bestimmten Dateihash ab.</span><span class="sxs-lookup"><span data-stu-id="d7f1c-111">Retrieves a collection of [Machines](machine.md) related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="d7f1c-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="d7f1c-112">Limitations</span></span>
1. <span data-ttu-id="d7f1c-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="d7f1c-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="d7f1c-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d7f1c-114">Permissions</span></span>
<span data-ttu-id="d7f1c-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d7f1c-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d7f1c-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d7f1c-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d7f1c-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="d7f1c-117">Permission type</span></span> |   <span data-ttu-id="d7f1c-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="d7f1c-118">Permission</span></span>  |   <span data-ttu-id="d7f1c-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="d7f1c-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d7f1c-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="d7f1c-120">Application</span></span> |   <span data-ttu-id="d7f1c-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="d7f1c-121">Machine.Read.All</span></span> |  <span data-ttu-id="d7f1c-122">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="d7f1c-122">'Read all machine profiles'</span></span>
<span data-ttu-id="d7f1c-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="d7f1c-123">Application</span></span> |   <span data-ttu-id="d7f1c-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d7f1c-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="d7f1c-125">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="d7f1c-125">'Read and write all machine information'</span></span>
<span data-ttu-id="d7f1c-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="d7f1c-126">Delegated (work or school account)</span></span> | <span data-ttu-id="d7f1c-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="d7f1c-127">Machine.Read</span></span> | <span data-ttu-id="d7f1c-128">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="d7f1c-128">'Read machine information'</span></span>
<span data-ttu-id="d7f1c-129">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="d7f1c-129">Delegated (work or school account)</span></span> | <span data-ttu-id="d7f1c-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d7f1c-130">Machine.ReadWrite</span></span> | <span data-ttu-id="d7f1c-131">"Lesen und Schreiben von Computerinformationen"</span><span class="sxs-lookup"><span data-stu-id="d7f1c-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="d7f1c-132">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="d7f1c-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d7f1c-133">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="d7f1c-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="d7f1c-134">Die Antwort enthält nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="d7f1c-134">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d7f1c-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="d7f1c-135">HTTP request</span></span>
```
GET /api/files/{id}/machines
```

## <a name="request-headers"></a><span data-ttu-id="d7f1c-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="d7f1c-136">Request headers</span></span>

<span data-ttu-id="d7f1c-137">Name</span><span class="sxs-lookup"><span data-stu-id="d7f1c-137">Name</span></span> | <span data-ttu-id="d7f1c-138">Typ</span><span class="sxs-lookup"><span data-stu-id="d7f1c-138">Type</span></span> | <span data-ttu-id="d7f1c-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7f1c-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="d7f1c-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="d7f1c-140">Authorization</span></span> | <span data-ttu-id="d7f1c-141">String</span><span class="sxs-lookup"><span data-stu-id="d7f1c-141">String</span></span> | <span data-ttu-id="d7f1c-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d7f1c-142">Bearer {token}.</span></span> <span data-ttu-id="d7f1c-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="d7f1c-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d7f1c-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="d7f1c-144">Request body</span></span>
<span data-ttu-id="d7f1c-145">Empty</span><span class="sxs-lookup"><span data-stu-id="d7f1c-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d7f1c-146">Antwort</span><span class="sxs-lookup"><span data-stu-id="d7f1c-146">Response</span></span>
<span data-ttu-id="d7f1c-147">Wenn erfolgreich und Datei vorhanden – 200 OK mit Liste der Computerentitäten im Textkörper. [](machine.md)</span><span class="sxs-lookup"><span data-stu-id="d7f1c-147">If successful and file exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="d7f1c-148">Wenn datei nicht vorhanden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="d7f1c-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="d7f1c-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7f1c-149">Example</span></span>

<span data-ttu-id="d7f1c-150">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="d7f1c-150">**Request**</span></span>

<span data-ttu-id="d7f1c-151">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="d7f1c-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
