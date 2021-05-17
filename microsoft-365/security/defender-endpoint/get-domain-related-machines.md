---
title: Abrufen der DOMÄNENbezogenen Computer-API
description: Erfahren Sie, wie Sie die API "Domänenbezogene Computer abrufen" verwenden, um Computer zu erhalten, die mit oder von einer Domäne in Microsoft Defender for Endpoint kommuniziert haben.
keywords: apis, graph api, supported apis, get, domain, related, devices
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
ms.openlocfilehash: 3fffb87c486e8b6b89b5e868b96d02dfae496e0b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166578"
---
# <a name="get-domain-related-machines-api"></a><span data-ttu-id="e674e-104">Abrufen der DOMÄNENbezogenen Computer-API</span><span class="sxs-lookup"><span data-stu-id="e674e-104">Get domain related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e674e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e674e-105">**Applies to:**</span></span>
- [<span data-ttu-id="e674e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e674e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e674e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e674e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e674e-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="e674e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e674e-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e674e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e674e-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e674e-110">API description</span></span>
<span data-ttu-id="e674e-111">Ruft eine Sammlung von Computern [ab,](machine.md) die mit oder von einer bestimmten Domänenadresse kommuniziert haben.</span><span class="sxs-lookup"><span data-stu-id="e674e-111">Retrieves a collection of [Machines](machine.md) that have communicated to or from a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="e674e-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e674e-112">Limitations</span></span>
1. <span data-ttu-id="e674e-113">Sie können auf Geräten abfragen, die zuletzt entsprechend Ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e674e-113">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="e674e-114">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="e674e-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="e674e-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e674e-115">Permissions</span></span>
<span data-ttu-id="e674e-116">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e674e-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e674e-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e674e-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e674e-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="e674e-118">Permission type</span></span> |   <span data-ttu-id="e674e-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e674e-119">Permission</span></span>  |   <span data-ttu-id="e674e-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e674e-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e674e-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="e674e-121">Application</span></span> |   <span data-ttu-id="e674e-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="e674e-122">Machine.Read.All</span></span> |  <span data-ttu-id="e674e-123">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="e674e-123">'Read all machine profiles'</span></span>
<span data-ttu-id="e674e-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="e674e-124">Application</span></span> |   <span data-ttu-id="e674e-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e674e-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="e674e-126">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="e674e-126">'Read and write all machine information'</span></span>
<span data-ttu-id="e674e-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="e674e-127">Delegated (work or school account)</span></span> | <span data-ttu-id="e674e-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="e674e-128">Machine.Read</span></span> | <span data-ttu-id="e674e-129">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="e674e-129">'Read machine information'</span></span>
<span data-ttu-id="e674e-130">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="e674e-130">Delegated (work or school account)</span></span> | <span data-ttu-id="e674e-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e674e-131">Machine.ReadWrite</span></span> | <span data-ttu-id="e674e-132">"Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="e674e-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="e674e-133">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="e674e-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e674e-134">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="e674e-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="e674e-135">Die Antwort umfasst nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen zugreifen kann (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="e674e-135">Response will include only devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e674e-136">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="e674e-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a><span data-ttu-id="e674e-137">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="e674e-137">Request headers</span></span>

<span data-ttu-id="e674e-138">Name</span><span class="sxs-lookup"><span data-stu-id="e674e-138">Name</span></span> | <span data-ttu-id="e674e-139">Typ</span><span class="sxs-lookup"><span data-stu-id="e674e-139">Type</span></span> | <span data-ttu-id="e674e-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e674e-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="e674e-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="e674e-141">Authorization</span></span> | <span data-ttu-id="e674e-142">String</span><span class="sxs-lookup"><span data-stu-id="e674e-142">String</span></span> | <span data-ttu-id="e674e-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e674e-143">Bearer {token}.</span></span> <span data-ttu-id="e674e-144">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="e674e-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e674e-145">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="e674e-145">Request body</span></span>
<span data-ttu-id="e674e-146">Empty</span><span class="sxs-lookup"><span data-stu-id="e674e-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e674e-147">Antwort</span><span class="sxs-lookup"><span data-stu-id="e674e-147">Response</span></span>
<span data-ttu-id="e674e-148">Wenn erfolgreich und Domäne vorhanden ist – 200 OK mit Liste der [Computerentitäten.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="e674e-148">If successful and domain exists - 200 OK with list of [machine](machine.md) entities.</span></span> <span data-ttu-id="e674e-149">Wenn domäne nicht vorhanden ist - 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="e674e-149">If domain do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="e674e-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e674e-150">Example</span></span>

<span data-ttu-id="e674e-151">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="e674e-151">**Request**</span></span>

<span data-ttu-id="e674e-152">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="e674e-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
