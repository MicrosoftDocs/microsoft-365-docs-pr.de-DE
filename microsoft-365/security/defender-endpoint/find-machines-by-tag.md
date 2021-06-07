---
title: Suchen von Geräten nach Tag-API
description: Suchen aller Geräte, die ein bestimmtes Tag enthalten
keywords: APIs, unterstützte APIs, abrufen, Gerät, suchen, Gerät suchen, nach Tag, Tag
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
ms.openlocfilehash: 88ad63d8b7cc71f7d3f809c7cb0371fc41bb9f5d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771165"
---
# <a name="find-devices-by-tag-api"></a><span data-ttu-id="1646b-104">Suchen von Geräten nach Tag-API</span><span class="sxs-lookup"><span data-stu-id="1646b-104">Find devices by tag API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1646b-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1646b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1646b-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="1646b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1646b-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="1646b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1646b-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1646b-108">API description</span></span>
<span data-ttu-id="1646b-109">Suchen von [Computern](machine.md) nach [Tag](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="1646b-109">Find [Machines](machine.md) by [Tag](machine-tags.md).</span></span>
<br><span data-ttu-id="1646b-110">```startswith``` abfrage wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1646b-110">```startswith``` query is supported.</span></span> 

## <a name="limitations"></a><span data-ttu-id="1646b-111">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="1646b-111">Limitations</span></span>
1. <span data-ttu-id="1646b-112">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="1646b-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1646b-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1646b-113">Permissions</span></span>
<span data-ttu-id="1646b-114">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1646b-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1646b-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1646b-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1646b-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="1646b-116">Permission type</span></span> |   <span data-ttu-id="1646b-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1646b-117">Permission</span></span>  |   <span data-ttu-id="1646b-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1646b-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1646b-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="1646b-119">Application</span></span> |   <span data-ttu-id="1646b-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="1646b-120">Machine.Read.All</span></span> |  <span data-ttu-id="1646b-121">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="1646b-121">'Read all machine profiles'</span></span>
<span data-ttu-id="1646b-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="1646b-122">Application</span></span> |   <span data-ttu-id="1646b-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1646b-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="1646b-124">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="1646b-124">'Read and write all machine information'</span></span>
<span data-ttu-id="1646b-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="1646b-125">Delegated (work or school account)</span></span> | <span data-ttu-id="1646b-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="1646b-126">Machine.Read</span></span> | <span data-ttu-id="1646b-127">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="1646b-127">'Read machine information'</span></span>
<span data-ttu-id="1646b-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="1646b-128">Delegated (work or school account)</span></span> | <span data-ttu-id="1646b-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1646b-129">Machine.ReadWrite</span></span> | <span data-ttu-id="1646b-130">"Lesen und Schreiben von Computerinformationen"</span><span class="sxs-lookup"><span data-stu-id="1646b-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="1646b-131">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="1646b-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="1646b-132">Die Antwort enthält nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="1646b-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="1646b-133">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="1646b-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="1646b-134">Die Antwort enthält nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="1646b-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1646b-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="1646b-135">HTTP request</span></span>
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a><span data-ttu-id="1646b-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="1646b-136">Request headers</span></span>

<span data-ttu-id="1646b-137">Name</span><span class="sxs-lookup"><span data-stu-id="1646b-137">Name</span></span> | <span data-ttu-id="1646b-138">Typ</span><span class="sxs-lookup"><span data-stu-id="1646b-138">Type</span></span> | <span data-ttu-id="1646b-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1646b-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="1646b-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="1646b-140">Authorization</span></span> | <span data-ttu-id="1646b-141">String</span><span class="sxs-lookup"><span data-stu-id="1646b-141">String</span></span> | <span data-ttu-id="1646b-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1646b-142">Bearer {token}.</span></span> <span data-ttu-id="1646b-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="1646b-143">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="1646b-144">Anforderungs-URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="1646b-144">Request URI parameters</span></span>

<span data-ttu-id="1646b-145">Name</span><span class="sxs-lookup"><span data-stu-id="1646b-145">Name</span></span> | <span data-ttu-id="1646b-146">Typ</span><span class="sxs-lookup"><span data-stu-id="1646b-146">Type</span></span> | <span data-ttu-id="1646b-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1646b-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="1646b-148">tag</span><span class="sxs-lookup"><span data-stu-id="1646b-148">tag</span></span> | <span data-ttu-id="1646b-149">String</span><span class="sxs-lookup"><span data-stu-id="1646b-149">String</span></span> | <span data-ttu-id="1646b-150">Der Tagname.</span><span class="sxs-lookup"><span data-stu-id="1646b-150">The tag name.</span></span> <span data-ttu-id="1646b-151">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="1646b-151">**Required**.</span></span>
<span data-ttu-id="1646b-152">useStartsWithFilter</span><span class="sxs-lookup"><span data-stu-id="1646b-152">useStartsWithFilter</span></span> | <span data-ttu-id="1646b-153">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1646b-153">Boolean</span></span> | <span data-ttu-id="1646b-154">Wenn der Wert auf "true" festgelegt ist, wird die Suche nach allen Geräten mit Tagnamen gesucht, die mit dem angegebenen Tag in der Abfrage beginnen.</span><span class="sxs-lookup"><span data-stu-id="1646b-154">When set to true, the search will find all devices with tag name that starts with the given tag in the query.</span></span> <span data-ttu-id="1646b-155">Standardwert ist false.</span><span class="sxs-lookup"><span data-stu-id="1646b-155">Defaults to false.</span></span> <span data-ttu-id="1646b-156">**Optional**.</span><span class="sxs-lookup"><span data-stu-id="1646b-156">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="1646b-157">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="1646b-157">Request body</span></span>
<span data-ttu-id="1646b-158">Empty</span><span class="sxs-lookup"><span data-stu-id="1646b-158">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1646b-159">Antwort</span><span class="sxs-lookup"><span data-stu-id="1646b-159">Response</span></span>
<span data-ttu-id="1646b-160">Wenn erfolgreich – 200 OK mit der Liste der Computer im Antworttext.</span><span class="sxs-lookup"><span data-stu-id="1646b-160">If successful - 200 OK with list of the machines in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="1646b-161">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1646b-161">Example</span></span>

<span data-ttu-id="1646b-162">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="1646b-162">**Request**</span></span>

<span data-ttu-id="1646b-163">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="1646b-163">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```