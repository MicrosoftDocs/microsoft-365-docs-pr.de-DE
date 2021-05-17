---
title: Festlegen der Gerätewert-API
description: Erfahren Sie, wie Sie den Wert eines Geräts mithilfe einer Microsoft Defender for Endpoint-API angeben.
keywords: apis, graph api, supported apis, tags, machine tags
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 76df62243db837ec91819497980ff1de2295e3b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498315"
---
# <a name="set-device-value-api"></a><span data-ttu-id="41690-104">Festlegen der Gerätewert-API</span><span class="sxs-lookup"><span data-stu-id="41690-104">Set device value API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41690-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="41690-105">**Applies to:**</span></span>
- [<span data-ttu-id="41690-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="41690-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="41690-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41690-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="41690-108">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="41690-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="41690-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="41690-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="41690-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="41690-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="41690-111">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41690-111">API description</span></span>

<span data-ttu-id="41690-112">Legen Sie den Gerätewert eines bestimmten Computers [.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="41690-112">Set the device value of a specific [Machine](machine.md).</span></span><br>
<span data-ttu-id="41690-113">Weitere [Informationen finden Sie unter Zuweisen von](tvm-assign-device-value.md) Gerätewerten.</span><span class="sxs-lookup"><span data-stu-id="41690-113">See [assign device values](tvm-assign-device-value.md) for more information.</span></span>

## <a name="limitations"></a><span data-ttu-id="41690-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="41690-114">Limitations</span></span>

1. <span data-ttu-id="41690-115">Sie können auf Geräten posten, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="41690-115">You can post on devices last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="41690-116">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="41690-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="41690-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="41690-117">Permissions</span></span>

<span data-ttu-id="41690-118">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="41690-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="41690-119">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="41690-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="41690-120">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="41690-120">Permission type</span></span> |    <span data-ttu-id="41690-121">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="41690-121">Permission</span></span>    |    <span data-ttu-id="41690-122">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="41690-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="41690-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="41690-123">Application</span></span> |    <span data-ttu-id="41690-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="41690-124">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="41690-125">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="41690-125">'Read and write all machine information'</span></span>
<span data-ttu-id="41690-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="41690-126">Delegated (work or school account)</span></span> | <span data-ttu-id="41690-127">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="41690-127">Machine.ReadWrite</span></span> | <span data-ttu-id="41690-128">"Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="41690-128">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="41690-129">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="41690-129">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="41690-130">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Sicherheitseinstellung verwalten".</span><span class="sxs-lookup"><span data-stu-id="41690-130">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="41690-131">Weitere Informationen finden Sie unter [Erstellen und Verwalten von](user-roles.md) Rollen.</span><span class="sxs-lookup"><span data-stu-id="41690-131">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="41690-132">Der Benutzer muss auf der Grundlage der Computergruppeneinstellungen auf den Computer zugreifen können (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Computergruppen).</span><span class="sxs-lookup"><span data-stu-id="41690-132">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="41690-133">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="41690-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a><span data-ttu-id="41690-134">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="41690-134">Request headers</span></span>

<span data-ttu-id="41690-135">Name</span><span class="sxs-lookup"><span data-stu-id="41690-135">Name</span></span> | <span data-ttu-id="41690-136">Typ</span><span class="sxs-lookup"><span data-stu-id="41690-136">Type</span></span> | <span data-ttu-id="41690-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41690-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="41690-138">Authorization</span><span class="sxs-lookup"><span data-stu-id="41690-138">Authorization</span></span> | <span data-ttu-id="41690-139">String</span><span class="sxs-lookup"><span data-stu-id="41690-139">String</span></span> | <span data-ttu-id="41690-140">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="41690-140">Bearer {token}.</span></span> <span data-ttu-id="41690-141">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="41690-141">**Required**.</span></span>
<span data-ttu-id="41690-142">Content-Type</span><span class="sxs-lookup"><span data-stu-id="41690-142">Content-Type</span></span> | <span data-ttu-id="41690-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="41690-143">string</span></span> | <span data-ttu-id="41690-144">application/json.</span><span class="sxs-lookup"><span data-stu-id="41690-144">application/json.</span></span> <span data-ttu-id="41690-145">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="41690-145">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="41690-146">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="41690-146">Request body</span></span>

<span data-ttu-id="41690-147">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="41690-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="41690-148">Parameter</span><span class="sxs-lookup"><span data-stu-id="41690-148">Parameter</span></span> |    <span data-ttu-id="41690-149">Typ</span><span class="sxs-lookup"><span data-stu-id="41690-149">Type</span></span>    | <span data-ttu-id="41690-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41690-150">Description</span></span>
:---|:---|:---
<span data-ttu-id="41690-151">DeviceValue</span><span class="sxs-lookup"><span data-stu-id="41690-151">DeviceValue</span></span> |    <span data-ttu-id="41690-152">Enum</span><span class="sxs-lookup"><span data-stu-id="41690-152">Enum</span></span> |    <span data-ttu-id="41690-153">Gerätewert.</span><span class="sxs-lookup"><span data-stu-id="41690-153">Device value.</span></span> <span data-ttu-id="41690-154">Zulässige Werte sind: "Normal", "Niedrig" und "Hoch".</span><span class="sxs-lookup"><span data-stu-id="41690-154">Allowed values are: 'Normal', 'Low' and 'High'.</span></span> <span data-ttu-id="41690-155">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="41690-155">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="41690-156">Antwort</span><span class="sxs-lookup"><span data-stu-id="41690-156">Response</span></span>

<span data-ttu-id="41690-157">Wenn die Methode erfolgreich ist, werden der Antwortcode 200 – Ok und der aktualisierte Computer im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="41690-157">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="41690-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41690-158">Example</span></span>

<span data-ttu-id="41690-159">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="41690-159">**Request**</span></span>

<span data-ttu-id="41690-160">Im Folgenden finden Sie ein Beispiel für eine Anforderung, die ein Computertag hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="41690-160">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
