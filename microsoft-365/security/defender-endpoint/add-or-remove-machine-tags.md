---
title: Hinzufügen oder Entfernen der Computertags-API
description: Erfahren Sie, wie Sie mithilfe der API computertags hinzufügen oder entfernen ein Tag für einen Computer in Microsoft Defender for Endpoint hinzufügen oder entfernen.
keywords: apis, graph api, supported apis, tags, machine tags
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
ms.openlocfilehash: 98dd513cc66683ff1b95f66d6d7b89916ce54bab
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199775"
---
# <a name="add-or-remove-machine-tags-api"></a><span data-ttu-id="eada9-104">Hinzufügen oder Entfernen der Computertags-API</span><span class="sxs-lookup"><span data-stu-id="eada9-104">Add or Remove Machine Tags API</span></span>

<span data-ttu-id="eada9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="eada9-105">**Applies to:**</span></span>

- [<span data-ttu-id="eada9-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="eada9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> <span data-ttu-id="eada9-107">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="eada9-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eada9-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="eada9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="eada9-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eada9-109">API description</span></span>

<span data-ttu-id="eada9-110">Fügt einem bestimmten Computer ein Tag hinzu oder [entfernt es.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="eada9-110">Adds or remove tag to a specific [Machine](machine.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="eada9-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="eada9-111">Limitations</span></span>

1. <span data-ttu-id="eada9-112">Sie können auf Computern posten, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum gesehen wurden.</span><span class="sxs-lookup"><span data-stu-id="eada9-112">You can post on machines last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="eada9-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="eada9-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="eada9-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="eada9-114">Permissions</span></span>

<span data-ttu-id="eada9-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eada9-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="eada9-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="eada9-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="eada9-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="eada9-117">Permission type</span></span> |    <span data-ttu-id="eada9-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="eada9-118">Permission</span></span>    |    <span data-ttu-id="eada9-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="eada9-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="eada9-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="eada9-120">Application</span></span> |    <span data-ttu-id="eada9-121">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="eada9-121">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="eada9-122">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="eada9-122">'Read and write all machine information'</span></span>
<span data-ttu-id="eada9-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="eada9-123">Delegated (work or school account)</span></span> | <span data-ttu-id="eada9-124">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="eada9-124">Machine.ReadWrite</span></span> | <span data-ttu-id="eada9-125">"Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="eada9-125">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="eada9-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="eada9-126">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="eada9-127">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Sicherheitseinstellung verwalten".</span><span class="sxs-lookup"><span data-stu-id="eada9-127">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="eada9-128">Weitere Informationen finden Sie unter [Erstellen und Verwalten von](user-roles.md) Rollen.</span><span class="sxs-lookup"><span data-stu-id="eada9-128">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="eada9-129">Der Benutzer muss auf der Grundlage der Computergruppeneinstellungen auf den Computer zugreifen können (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Computergruppen).</span><span class="sxs-lookup"><span data-stu-id="eada9-129">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="eada9-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="eada9-130">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a><span data-ttu-id="eada9-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="eada9-131">Request headers</span></span>

<span data-ttu-id="eada9-132">Name</span><span class="sxs-lookup"><span data-stu-id="eada9-132">Name</span></span> | <span data-ttu-id="eada9-133">Typ</span><span class="sxs-lookup"><span data-stu-id="eada9-133">Type</span></span> | <span data-ttu-id="eada9-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eada9-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="eada9-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="eada9-135">Authorization</span></span> | <span data-ttu-id="eada9-136">String</span><span class="sxs-lookup"><span data-stu-id="eada9-136">String</span></span> | <span data-ttu-id="eada9-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="eada9-137">Bearer {token}.</span></span> <span data-ttu-id="eada9-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="eada9-138">**Required**.</span></span>
<span data-ttu-id="eada9-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="eada9-139">Content-Type</span></span> | <span data-ttu-id="eada9-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="eada9-140">string</span></span> | <span data-ttu-id="eada9-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="eada9-141">application/json.</span></span> <span data-ttu-id="eada9-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="eada9-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="eada9-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="eada9-143">Request body</span></span>

<span data-ttu-id="eada9-144">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="eada9-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="eada9-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="eada9-145">Parameter</span></span> |    <span data-ttu-id="eada9-146">Typ</span><span class="sxs-lookup"><span data-stu-id="eada9-146">Type</span></span>    | <span data-ttu-id="eada9-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eada9-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="eada9-148">Wert</span><span class="sxs-lookup"><span data-stu-id="eada9-148">Value</span></span> |    <span data-ttu-id="eada9-149">String</span><span class="sxs-lookup"><span data-stu-id="eada9-149">String</span></span> |    <span data-ttu-id="eada9-150">Der Tagname.</span><span class="sxs-lookup"><span data-stu-id="eada9-150">The tag name.</span></span> <span data-ttu-id="eada9-151">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="eada9-151">**Required**.</span></span>
<span data-ttu-id="eada9-152">Aktion</span><span class="sxs-lookup"><span data-stu-id="eada9-152">Action</span></span>    | <span data-ttu-id="eada9-153">Enum</span><span class="sxs-lookup"><span data-stu-id="eada9-153">Enum</span></span> |    <span data-ttu-id="eada9-154">Hinzufügen oder Entfernen.</span><span class="sxs-lookup"><span data-stu-id="eada9-154">Add or Remove.</span></span> <span data-ttu-id="eada9-155">Zulässige Werte sind: "Hinzufügen" oder "Entfernen".</span><span class="sxs-lookup"><span data-stu-id="eada9-155">Allowed values are: 'Add' or 'Remove'.</span></span> <span data-ttu-id="eada9-156">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="eada9-156">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="eada9-157">Antwort</span><span class="sxs-lookup"><span data-stu-id="eada9-157">Response</span></span>

<span data-ttu-id="eada9-158">Wenn die Methode erfolgreich ist, werden der Antwortcode 200 – Ok und der aktualisierte Computer im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="eada9-158">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="eada9-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eada9-159">Example</span></span>

<span data-ttu-id="eada9-160">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="eada9-160">**Request**</span></span>

<span data-ttu-id="eada9-161">Im Folgenden finden Sie ein Beispiel für eine Anforderung, die ein Computertag hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="eada9-161">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- <span data-ttu-id="eada9-162">Wenn Sie das Computertag entfernen möchten, legen Sie die Aktion im Anforderungstext auf "Entfernen" statt auf "Hinzufügen" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eada9-162">To remove machine tag, set the Action to 'Remove' instead of 'Add' in the request body.</span></span>
