---
title: Hinzufügen oder Entfernen der Computertag-API
description: Erfahren Sie, wie Sie die Api zum Hinzufügen oder Entfernen von Computertags verwenden, um ein Tag für einen Computer in Microsoft Defender für Endpunkt hinzuzufügen oder zu entfernen.
keywords: APIs, Graph-API, unterstützte APIs, Tags, Computertags
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
ms.openlocfilehash: 3818fc0050790b2c3b307f95ee0760c516cbf893
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769821"
---
# <a name="add-or-remove-machine-tags-api"></a><span data-ttu-id="0c834-104">Hinzufügen oder Entfernen der Computertag-API</span><span class="sxs-lookup"><span data-stu-id="0c834-104">Add or Remove Machine Tags API</span></span>

<span data-ttu-id="0c834-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0c834-105">**Applies to:**</span></span>

- [<span data-ttu-id="0c834-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0c834-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> <span data-ttu-id="0c834-107">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="0c834-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0c834-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0c834-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="0c834-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c834-109">API description</span></span>

<span data-ttu-id="0c834-110">Fügt einem bestimmten [Computer](machine.md)ein Tag hinzu oder entfernt es.</span><span class="sxs-lookup"><span data-stu-id="0c834-110">Adds or remove tag to a specific [Machine](machine.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="0c834-111">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="0c834-111">Limitations</span></span>

1. <span data-ttu-id="0c834-112">Sie können Beiträge auf Computern bereitstellen, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c834-112">You can post on machines last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="0c834-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="0c834-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="0c834-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0c834-114">Permissions</span></span>

<span data-ttu-id="0c834-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0c834-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0c834-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0c834-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="0c834-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="0c834-117">Permission type</span></span> |    <span data-ttu-id="0c834-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0c834-118">Permission</span></span>    |    <span data-ttu-id="0c834-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0c834-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0c834-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="0c834-120">Application</span></span> |    <span data-ttu-id="0c834-121">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="0c834-121">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="0c834-122">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="0c834-122">'Read and write all machine information'</span></span>
<span data-ttu-id="0c834-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="0c834-123">Delegated (work or school account)</span></span> | <span data-ttu-id="0c834-124">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0c834-124">Machine.ReadWrite</span></span> | <span data-ttu-id="0c834-125">"Lesen und Schreiben von Computerinformationen"</span><span class="sxs-lookup"><span data-stu-id="0c834-125">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="0c834-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="0c834-126">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="0c834-127">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Sicherheitseinstellung verwalten".</span><span class="sxs-lookup"><span data-stu-id="0c834-127">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="0c834-128">Weitere Informationen (weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen)](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0c834-128">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="0c834-129">Der Benutzer muss basierend auf den Computergruppeneinstellungen Zugriff auf den Computer haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Computergruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="0c834-129">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="0c834-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="0c834-130">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a><span data-ttu-id="0c834-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="0c834-131">Request headers</span></span>

<span data-ttu-id="0c834-132">Name</span><span class="sxs-lookup"><span data-stu-id="0c834-132">Name</span></span> | <span data-ttu-id="0c834-133">Typ</span><span class="sxs-lookup"><span data-stu-id="0c834-133">Type</span></span> | <span data-ttu-id="0c834-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c834-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="0c834-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="0c834-135">Authorization</span></span> | <span data-ttu-id="0c834-136">String</span><span class="sxs-lookup"><span data-stu-id="0c834-136">String</span></span> | <span data-ttu-id="0c834-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="0c834-137">Bearer {token}.</span></span> <span data-ttu-id="0c834-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0c834-138">**Required**.</span></span>
<span data-ttu-id="0c834-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="0c834-139">Content-Type</span></span> | <span data-ttu-id="0c834-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0c834-140">string</span></span> | <span data-ttu-id="0c834-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="0c834-141">application/json.</span></span> <span data-ttu-id="0c834-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0c834-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="0c834-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="0c834-143">Request body</span></span>

<span data-ttu-id="0c834-144">Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:</span><span class="sxs-lookup"><span data-stu-id="0c834-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="0c834-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="0c834-145">Parameter</span></span> |    <span data-ttu-id="0c834-146">Typ</span><span class="sxs-lookup"><span data-stu-id="0c834-146">Type</span></span>    | <span data-ttu-id="0c834-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c834-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="0c834-148">Wert</span><span class="sxs-lookup"><span data-stu-id="0c834-148">Value</span></span> |    <span data-ttu-id="0c834-149">String</span><span class="sxs-lookup"><span data-stu-id="0c834-149">String</span></span> |    <span data-ttu-id="0c834-150">Der Tagname.</span><span class="sxs-lookup"><span data-stu-id="0c834-150">The tag name.</span></span> <span data-ttu-id="0c834-151">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0c834-151">**Required**.</span></span>
<span data-ttu-id="0c834-152">Aktion</span><span class="sxs-lookup"><span data-stu-id="0c834-152">Action</span></span>    | <span data-ttu-id="0c834-153">Enum</span><span class="sxs-lookup"><span data-stu-id="0c834-153">Enum</span></span> |    <span data-ttu-id="0c834-154">Hinzufügen oder Entfernen.</span><span class="sxs-lookup"><span data-stu-id="0c834-154">Add or Remove.</span></span> <span data-ttu-id="0c834-155">Zulässige Werte sind: 'Add' oder 'Remove'.</span><span class="sxs-lookup"><span data-stu-id="0c834-155">Allowed values are: 'Add' or 'Remove'.</span></span> <span data-ttu-id="0c834-156">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0c834-156">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="0c834-157">Antwort</span><span class="sxs-lookup"><span data-stu-id="0c834-157">Response</span></span>

<span data-ttu-id="0c834-158">Wenn die Methode erfolgreich ist, werden der Antwortcode "200 – Ok" und der aktualisierte Computer im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0c834-158">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="0c834-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c834-159">Example</span></span>

<span data-ttu-id="0c834-160">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="0c834-160">**Request**</span></span>

<span data-ttu-id="0c834-161">Nachfolgend sehen Sie ein Beispiel für eine Anforderung, die ein Computertag hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="0c834-161">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- <span data-ttu-id="0c834-162">Um das Computertag zu entfernen, legen Sie die Aktion im Anforderungstext auf "Entfernen" anstelle von "Hinzufügen" fest.</span><span class="sxs-lookup"><span data-stu-id="0c834-162">To remove machine tag, set the Action to 'Remove' instead of 'Add' in the request body.</span></span>
