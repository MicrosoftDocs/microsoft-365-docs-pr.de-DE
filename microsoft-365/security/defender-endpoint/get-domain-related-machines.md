---
title: API zum Abrufen domänenbezogener Computer
description: Erfahren Sie, wie Sie die API zum Abrufen domänenbezogener Computer verwenden, um Computer abzurufen, die mit oder von einer Domäne in Microsoft Defender für Endpunkt kommuniziert haben.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Domäne, verwandte, Geräte
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
ms.openlocfilehash: 362e3db0ed89924c58fa9662f7acbbe0c16c37c6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772221"
---
# <a name="get-domain-related-machines-api"></a><span data-ttu-id="404af-104">API zum Abrufen domänenbezogener Computer</span><span class="sxs-lookup"><span data-stu-id="404af-104">Get domain related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="404af-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="404af-105">**Applies to:**</span></span>
- [<span data-ttu-id="404af-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="404af-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="404af-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="404af-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="404af-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="404af-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="404af-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="404af-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="404af-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="404af-110">API description</span></span>
<span data-ttu-id="404af-111">Ruft eine Sammlung von [Computern](machine.md) ab, die mit oder von einer bestimmten Domänenadresse kommuniziert haben.</span><span class="sxs-lookup"><span data-stu-id="404af-111">Retrieves a collection of [Machines](machine.md) that have communicated to or from a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="404af-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="404af-112">Limitations</span></span>
1. <span data-ttu-id="404af-113">Sie können Abfragen auf Geräten durchführen, die zuletzt gemäß ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="404af-113">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="404af-114">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="404af-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="404af-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="404af-115">Permissions</span></span>
<span data-ttu-id="404af-116">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="404af-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="404af-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="404af-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="404af-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="404af-118">Permission type</span></span> |   <span data-ttu-id="404af-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="404af-119">Permission</span></span>  |   <span data-ttu-id="404af-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="404af-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="404af-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="404af-121">Application</span></span> |   <span data-ttu-id="404af-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="404af-122">Machine.Read.All</span></span> |  <span data-ttu-id="404af-123">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="404af-123">'Read all machine profiles'</span></span>
<span data-ttu-id="404af-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="404af-124">Application</span></span> |   <span data-ttu-id="404af-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="404af-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="404af-126">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="404af-126">'Read and write all machine information'</span></span>
<span data-ttu-id="404af-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="404af-127">Delegated (work or school account)</span></span> | <span data-ttu-id="404af-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="404af-128">Machine.Read</span></span> | <span data-ttu-id="404af-129">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="404af-129">'Read machine information'</span></span>
<span data-ttu-id="404af-130">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="404af-130">Delegated (work or school account)</span></span> | <span data-ttu-id="404af-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="404af-131">Machine.ReadWrite</span></span> | <span data-ttu-id="404af-132">"Lesen und Schreiben von Computerinformationen"</span><span class="sxs-lookup"><span data-stu-id="404af-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="404af-133">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="404af-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="404af-134">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="404af-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="404af-135">Die Antwort enthält nur Geräte, auf die der Benutzer zugreifen kann, basierend auf Gerätegruppeneinstellungen (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="404af-135">Response will include only devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="404af-136">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="404af-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a><span data-ttu-id="404af-137">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="404af-137">Request headers</span></span>

<span data-ttu-id="404af-138">Name</span><span class="sxs-lookup"><span data-stu-id="404af-138">Name</span></span> | <span data-ttu-id="404af-139">Typ</span><span class="sxs-lookup"><span data-stu-id="404af-139">Type</span></span> | <span data-ttu-id="404af-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="404af-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="404af-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="404af-141">Authorization</span></span> | <span data-ttu-id="404af-142">String</span><span class="sxs-lookup"><span data-stu-id="404af-142">String</span></span> | <span data-ttu-id="404af-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="404af-143">Bearer {token}.</span></span> <span data-ttu-id="404af-144">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="404af-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="404af-145">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="404af-145">Request body</span></span>
<span data-ttu-id="404af-146">Empty</span><span class="sxs-lookup"><span data-stu-id="404af-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="404af-147">Antwort</span><span class="sxs-lookup"><span data-stu-id="404af-147">Response</span></span>
<span data-ttu-id="404af-148">Wenn erfolgreich und Domäne vorhanden – 200 OK mit Liste der Computerentitäten. [](machine.md)</span><span class="sxs-lookup"><span data-stu-id="404af-148">If successful and domain exists - 200 OK with list of [machine](machine.md) entities.</span></span> <span data-ttu-id="404af-149">Wenn Domäne nicht vorhanden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="404af-149">If domain do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="404af-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="404af-150">Example</span></span>

<span data-ttu-id="404af-151">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="404af-151">**Request**</span></span>

<span data-ttu-id="404af-152">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="404af-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
