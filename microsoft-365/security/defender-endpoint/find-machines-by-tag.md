---
title: Suchen von Geräten nach Tag-API
description: Suchen aller Geräte, die ein specifc-Tag enthalten
keywords: apis, supported apis, get, device, find, find device, by tag, tag
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
ms.openlocfilehash: 6460860828acd5ea0c3509e9eb06061d2a9a0cc2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200149"
---
# <a name="find-devices-by-tag-api"></a><span data-ttu-id="5202e-104">Suchen von Geräten nach Tag-API</span><span class="sxs-lookup"><span data-stu-id="5202e-104">Find devices by tag API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5202e-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5202e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5202e-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="5202e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5202e-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="5202e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5202e-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5202e-108">API description</span></span>
<span data-ttu-id="5202e-109">Suchen [von Computern](machine.md) nach [Tag](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="5202e-109">Find [Machines](machine.md) by [Tag](machine-tags.md).</span></span>
<br><span data-ttu-id="5202e-110">```startswith``` Abfrage wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5202e-110">```startswith``` query is supported.</span></span> 

## <a name="limitations"></a><span data-ttu-id="5202e-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5202e-111">Limitations</span></span>
1. <span data-ttu-id="5202e-112">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="5202e-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="5202e-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5202e-113">Permissions</span></span>
<span data-ttu-id="5202e-114">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5202e-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5202e-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5202e-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5202e-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="5202e-116">Permission type</span></span> |   <span data-ttu-id="5202e-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="5202e-117">Permission</span></span>  |   <span data-ttu-id="5202e-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="5202e-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5202e-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="5202e-119">Application</span></span> |   <span data-ttu-id="5202e-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="5202e-120">Machine.Read.All</span></span> |  <span data-ttu-id="5202e-121">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="5202e-121">'Read all machine profiles'</span></span>
<span data-ttu-id="5202e-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="5202e-122">Application</span></span> |   <span data-ttu-id="5202e-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5202e-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="5202e-124">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="5202e-124">'Read and write all machine information'</span></span>
<span data-ttu-id="5202e-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="5202e-125">Delegated (work or school account)</span></span> | <span data-ttu-id="5202e-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="5202e-126">Machine.Read</span></span> | <span data-ttu-id="5202e-127">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="5202e-127">'Read machine information'</span></span>
<span data-ttu-id="5202e-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="5202e-128">Delegated (work or school account)</span></span> | <span data-ttu-id="5202e-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5202e-129">Machine.ReadWrite</span></span> | <span data-ttu-id="5202e-130">"Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="5202e-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="5202e-131">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="5202e-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="5202e-132">Die Antwort umfasst nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="5202e-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="5202e-133">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="5202e-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="5202e-134">Die Antwort umfasst nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="5202e-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5202e-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="5202e-135">HTTP request</span></span>
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a><span data-ttu-id="5202e-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="5202e-136">Request headers</span></span>

<span data-ttu-id="5202e-137">Name</span><span class="sxs-lookup"><span data-stu-id="5202e-137">Name</span></span> | <span data-ttu-id="5202e-138">Typ</span><span class="sxs-lookup"><span data-stu-id="5202e-138">Type</span></span> | <span data-ttu-id="5202e-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5202e-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="5202e-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="5202e-140">Authorization</span></span> | <span data-ttu-id="5202e-141">String</span><span class="sxs-lookup"><span data-stu-id="5202e-141">String</span></span> | <span data-ttu-id="5202e-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5202e-142">Bearer {token}.</span></span> <span data-ttu-id="5202e-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="5202e-143">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="5202e-144">Anforderungs-URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="5202e-144">Request URI parameters</span></span>

<span data-ttu-id="5202e-145">Name</span><span class="sxs-lookup"><span data-stu-id="5202e-145">Name</span></span> | <span data-ttu-id="5202e-146">Typ</span><span class="sxs-lookup"><span data-stu-id="5202e-146">Type</span></span> | <span data-ttu-id="5202e-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5202e-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="5202e-148">tag</span><span class="sxs-lookup"><span data-stu-id="5202e-148">tag</span></span> | <span data-ttu-id="5202e-149">String</span><span class="sxs-lookup"><span data-stu-id="5202e-149">String</span></span> | <span data-ttu-id="5202e-150">Der Tagname.</span><span class="sxs-lookup"><span data-stu-id="5202e-150">The tag name.</span></span> <span data-ttu-id="5202e-151">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="5202e-151">**Required**.</span></span>
<span data-ttu-id="5202e-152">useStartsWithFilter</span><span class="sxs-lookup"><span data-stu-id="5202e-152">useStartsWithFilter</span></span> | <span data-ttu-id="5202e-153">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="5202e-153">Boolean</span></span> | <span data-ttu-id="5202e-154">Wenn dieser Wert auf true festgelegt ist, findet die Suche alle Geräte mit Dem Tagnamen, die mit dem angegebenen Tag in der Abfrage beginnen.</span><span class="sxs-lookup"><span data-stu-id="5202e-154">When set to true, the search will find all devices with tag name that starts with the given tag in the query.</span></span> <span data-ttu-id="5202e-155">Standardwert ist false.</span><span class="sxs-lookup"><span data-stu-id="5202e-155">Defaults to false.</span></span> <span data-ttu-id="5202e-156">**Optional**.</span><span class="sxs-lookup"><span data-stu-id="5202e-156">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5202e-157">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="5202e-157">Request body</span></span>
<span data-ttu-id="5202e-158">Empty</span><span class="sxs-lookup"><span data-stu-id="5202e-158">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5202e-159">Antwort</span><span class="sxs-lookup"><span data-stu-id="5202e-159">Response</span></span>
<span data-ttu-id="5202e-160">Wenn erfolgreich – 200 OK mit liste der Computer im Antworttext.</span><span class="sxs-lookup"><span data-stu-id="5202e-160">If successful - 200 OK with list of the machines in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="5202e-161">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5202e-161">Example</span></span>

<span data-ttu-id="5202e-162">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="5202e-162">**Request**</span></span>

<span data-ttu-id="5202e-163">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="5202e-163">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```