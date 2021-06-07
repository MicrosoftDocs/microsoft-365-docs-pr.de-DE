---
title: Untersuchungs-API starten
description: Verwenden Sie diese API, um die Untersuchung auf einem Gerät zu starten.
keywords: APIs, Graph-API, unterstützte APIs, Untersuchung
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
ms.openlocfilehash: b7a6a3e7f6f705f322ee3eb1c1b561bc01c55d29
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770889"
---
# <a name="start-investigation-api"></a><span data-ttu-id="e7e24-104">Untersuchungs-API starten</span><span class="sxs-lookup"><span data-stu-id="e7e24-104">Start Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e7e24-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e7e24-105">**Applies to:**</span></span>
- [<span data-ttu-id="e7e24-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e7e24-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e7e24-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7e24-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e7e24-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="e7e24-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e7e24-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e7e24-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e7e24-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7e24-110">API description</span></span>
<span data-ttu-id="e7e24-111">Starten Sie die automatische Untersuchung auf einem Gerät.</span><span class="sxs-lookup"><span data-stu-id="e7e24-111">Start automated investigation on a device.</span></span>
<br><span data-ttu-id="e7e24-112">Weitere Informationen finden Sie [unter "Übersicht über automatisierte Untersuchungen".](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="e7e24-112">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>


## <a name="limitations"></a><span data-ttu-id="e7e24-113">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="e7e24-113">Limitations</span></span>
1. <span data-ttu-id="e7e24-114">Die Rateneinschränkungen für diese API liegen bei 50 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="e7e24-114">Rate limitations for this API are 50 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="e7e24-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e7e24-115">Permissions</span></span>
<span data-ttu-id="e7e24-116">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e7e24-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e7e24-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e7e24-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e7e24-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="e7e24-118">Permission type</span></span> |   <span data-ttu-id="e7e24-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e7e24-119">Permission</span></span>  |   <span data-ttu-id="e7e24-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e7e24-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e7e24-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="e7e24-121">Application</span></span> |   <span data-ttu-id="e7e24-122">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e7e24-122">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="e7e24-123">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="e7e24-123">'Read and write all alerts'</span></span>
<span data-ttu-id="e7e24-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="e7e24-124">Delegated (work or school account)</span></span> | <span data-ttu-id="e7e24-125">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e7e24-125">Alert.ReadWrite</span></span> | <span data-ttu-id="e7e24-126">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="e7e24-126">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="e7e24-127">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="e7e24-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e7e24-128">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="e7e24-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="e7e24-129">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="e7e24-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="e7e24-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="e7e24-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a><span data-ttu-id="e7e24-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="e7e24-131">Request headers</span></span>

<span data-ttu-id="e7e24-132">Name</span><span class="sxs-lookup"><span data-stu-id="e7e24-132">Name</span></span> | <span data-ttu-id="e7e24-133">Typ</span><span class="sxs-lookup"><span data-stu-id="e7e24-133">Type</span></span> | <span data-ttu-id="e7e24-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7e24-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="e7e24-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="e7e24-135">Authorization</span></span> | <span data-ttu-id="e7e24-136">String</span><span class="sxs-lookup"><span data-stu-id="e7e24-136">String</span></span> | <span data-ttu-id="e7e24-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e7e24-137">Bearer {token}.</span></span> <span data-ttu-id="e7e24-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="e7e24-138">**Required**.</span></span>
<span data-ttu-id="e7e24-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e7e24-139">Content-Type</span></span> | <span data-ttu-id="e7e24-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e7e24-140">string</span></span> | <span data-ttu-id="e7e24-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="e7e24-141">application/json.</span></span> <span data-ttu-id="e7e24-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="e7e24-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e7e24-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="e7e24-143">Request body</span></span>
<span data-ttu-id="e7e24-144">Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:</span><span class="sxs-lookup"><span data-stu-id="e7e24-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="e7e24-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7e24-145">Parameter</span></span> | <span data-ttu-id="e7e24-146">Typ</span><span class="sxs-lookup"><span data-stu-id="e7e24-146">Type</span></span>    | <span data-ttu-id="e7e24-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7e24-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="e7e24-148">Kommentar</span><span class="sxs-lookup"><span data-stu-id="e7e24-148">Comment</span></span> |   <span data-ttu-id="e7e24-149">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e7e24-149">String</span></span> |    <span data-ttu-id="e7e24-150">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7e24-150">Comment to associate with the action.</span></span> <span data-ttu-id="e7e24-151">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="e7e24-151">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="e7e24-152">Antwort</span><span class="sxs-lookup"><span data-stu-id="e7e24-152">Response</span></span>
<span data-ttu-id="e7e24-153">Wenn die Methode erfolgreich ist, wird "201 – Erstellter Antwortcode und [Untersuchung"](investigation.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e7e24-153">If successful, this method returns 201 - Created response code and [Investigation](investigation.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="e7e24-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7e24-154">Example</span></span>

<span data-ttu-id="e7e24-155">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="e7e24-155">**Request**</span></span>

<span data-ttu-id="e7e24-156">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="e7e24-156">Here is an example of the request.</span></span>

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
