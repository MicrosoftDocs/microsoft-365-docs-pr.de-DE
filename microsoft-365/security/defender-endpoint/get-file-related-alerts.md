---
title: Api zum Abrufen dateibezogener Warnungen
description: Erfahren Sie, wie Sie die API zum Abrufen dateibezogener Warnungen verwenden, um eine Sammlung von Warnungen im Zusammenhang mit einem bestimmten Dateihash in Microsoft Defender für Endpunkt abzurufen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Datei, Hash
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
ms.openlocfilehash: b77946f4bfdb793ffbfdf102a7221df083fb92eb
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770298"
---
# <a name="get-file-related-alerts-api"></a><span data-ttu-id="0dafe-104">Api zum Abrufen dateibezogener Warnungen</span><span class="sxs-lookup"><span data-stu-id="0dafe-104">Get file-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0dafe-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0dafe-105">**Applies to:**</span></span>
- [<span data-ttu-id="0dafe-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0dafe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0dafe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0dafe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0dafe-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="0dafe-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0dafe-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0dafe-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="0dafe-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0dafe-110">API description</span></span>
<span data-ttu-id="0dafe-111">Ruft eine Sammlung von Warnungen im Zusammenhang mit einem bestimmten Dateihash ab.</span><span class="sxs-lookup"><span data-stu-id="0dafe-111">Retrieves a collection of alerts related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="0dafe-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="0dafe-112">Limitations</span></span>
1. <span data-ttu-id="0dafe-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="0dafe-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="0dafe-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0dafe-114">Permissions</span></span>
<span data-ttu-id="0dafe-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0dafe-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0dafe-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0dafe-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="0dafe-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="0dafe-117">Permission type</span></span> |   <span data-ttu-id="0dafe-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0dafe-118">Permission</span></span>  |   <span data-ttu-id="0dafe-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0dafe-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0dafe-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="0dafe-120">Application</span></span> |   <span data-ttu-id="0dafe-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="0dafe-121">Alert.Read.All</span></span> |    <span data-ttu-id="0dafe-122">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="0dafe-122">'Read all alerts'</span></span>
<span data-ttu-id="0dafe-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="0dafe-123">Application</span></span> |   <span data-ttu-id="0dafe-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="0dafe-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="0dafe-125">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="0dafe-125">'Read and write all alerts'</span></span>
<span data-ttu-id="0dafe-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="0dafe-126">Delegated (work or school account)</span></span> | <span data-ttu-id="0dafe-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="0dafe-127">Alert.Read</span></span> | <span data-ttu-id="0dafe-128">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="0dafe-128">'Read alerts'</span></span>
<span data-ttu-id="0dafe-129">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="0dafe-129">Delegated (work or school account)</span></span> | <span data-ttu-id="0dafe-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0dafe-130">Alert.ReadWrite</span></span> | <span data-ttu-id="0dafe-131">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="0dafe-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="0dafe-132">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="0dafe-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="0dafe-133">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0dafe-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="0dafe-134">Die Antwort enthält nur Warnungen, die Geräten zugeordnet sind, auf die der Benutzer zugriff hat, basierend auf Gerätegruppeneinstellungen (weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="0dafe-134">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="0dafe-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="0dafe-135">HTTP request</span></span>
```
GET /api/files/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="0dafe-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="0dafe-136">Request headers</span></span>

<span data-ttu-id="0dafe-137">Name</span><span class="sxs-lookup"><span data-stu-id="0dafe-137">Name</span></span> | <span data-ttu-id="0dafe-138">Typ</span><span class="sxs-lookup"><span data-stu-id="0dafe-138">Type</span></span> | <span data-ttu-id="0dafe-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0dafe-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="0dafe-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="0dafe-140">Authorization</span></span> | <span data-ttu-id="0dafe-141">String</span><span class="sxs-lookup"><span data-stu-id="0dafe-141">String</span></span> | <span data-ttu-id="0dafe-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="0dafe-142">Bearer {token}.</span></span> <span data-ttu-id="0dafe-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0dafe-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0dafe-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="0dafe-144">Request body</span></span>
<span data-ttu-id="0dafe-145">Empty</span><span class="sxs-lookup"><span data-stu-id="0dafe-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0dafe-146">Antwort</span><span class="sxs-lookup"><span data-stu-id="0dafe-146">Response</span></span>
<span data-ttu-id="0dafe-147">Wenn erfolgreich und Datei vorhanden – 200 OK mit Liste der Warnungsentitäten im Textkörper. [](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="0dafe-147">If successful and file exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="0dafe-148">Wenn datei nicht vorhanden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="0dafe-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="0dafe-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0dafe-149">Example</span></span>

<span data-ttu-id="0dafe-150">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="0dafe-150">**Request**</span></span>

<span data-ttu-id="0dafe-151">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="0dafe-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/6532ec91d513acc05f43ee0aa3002599729fd3e1/alerts
```
