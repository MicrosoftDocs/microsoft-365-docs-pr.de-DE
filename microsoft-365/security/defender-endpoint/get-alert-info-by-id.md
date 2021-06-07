---
title: Abrufen von Warnungsinformationen nach ID-API
description: Erfahren Sie, wie Sie die API zum Abrufen von Warnungsinformationen nach ID verwenden, um eine bestimmte Warnung anhand ihrer ID in Microsoft Defender für Endpunkt abzurufen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnung, Informationen, ID
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
ms.openlocfilehash: b9de7645abc59849b3ca28f64904b0ba49d4eef5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771897"
---
# <a name="get-alert-information-by-id-api"></a><span data-ttu-id="817bb-104">Abrufen von Warnungsinformationen nach ID-API</span><span class="sxs-lookup"><span data-stu-id="817bb-104">Get alert information by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="817bb-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="817bb-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="817bb-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="817bb-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="817bb-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="817bb-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="817bb-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="817bb-108">API description</span></span>
<span data-ttu-id="817bb-109">Ruft eine bestimmte [Warnung](alerts.md) anhand ihrer ID ab.</span><span class="sxs-lookup"><span data-stu-id="817bb-109">Retrieves specific [Alert](alerts.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="817bb-110">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="817bb-110">Limitations</span></span>
1. <span data-ttu-id="817bb-111">Sie können Benachrichtigungen erhalten, die nach Dem konfigurierten Aufbewahrungszeitraum zuletzt aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="817bb-111">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="817bb-112">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="817bb-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="817bb-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="817bb-113">Permissions</span></span>
<span data-ttu-id="817bb-114">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="817bb-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="817bb-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="817bb-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="817bb-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="817bb-116">Permission type</span></span> |   <span data-ttu-id="817bb-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="817bb-117">Permission</span></span>  |   <span data-ttu-id="817bb-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="817bb-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="817bb-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="817bb-119">Application</span></span> |   <span data-ttu-id="817bb-120">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="817bb-120">Alert.Read.All</span></span> |    <span data-ttu-id="817bb-121">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="817bb-121">'Read all alerts'</span></span>
<span data-ttu-id="817bb-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="817bb-122">Application</span></span> |   <span data-ttu-id="817bb-123">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="817bb-123">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="817bb-124">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="817bb-124">'Read and write all alerts'</span></span>
<span data-ttu-id="817bb-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="817bb-125">Delegated (work or school account)</span></span> | <span data-ttu-id="817bb-126">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="817bb-126">Alert.Read</span></span> | <span data-ttu-id="817bb-127">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="817bb-127">'Read alerts'</span></span>
<span data-ttu-id="817bb-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="817bb-128">Delegated (work or school account)</span></span> | <span data-ttu-id="817bb-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="817bb-129">Alert.ReadWrite</span></span> | <span data-ttu-id="817bb-130">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="817bb-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="817bb-131">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="817bb-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="817bb-132">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="817bb-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="817bb-133">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben, das der Warnung zugeordnet ist (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="817bb-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="817bb-134">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="817bb-134">HTTP request</span></span>
```
GET /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="817bb-135">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="817bb-135">Request headers</span></span>

<span data-ttu-id="817bb-136">Name</span><span class="sxs-lookup"><span data-stu-id="817bb-136">Name</span></span> | <span data-ttu-id="817bb-137">Typ</span><span class="sxs-lookup"><span data-stu-id="817bb-137">Type</span></span> | <span data-ttu-id="817bb-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="817bb-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="817bb-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="817bb-139">Authorization</span></span> | <span data-ttu-id="817bb-140">String</span><span class="sxs-lookup"><span data-stu-id="817bb-140">String</span></span> | <span data-ttu-id="817bb-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="817bb-141">Bearer {token}.</span></span> <span data-ttu-id="817bb-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="817bb-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="817bb-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="817bb-143">Request body</span></span>
<span data-ttu-id="817bb-144">Empty</span><span class="sxs-lookup"><span data-stu-id="817bb-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="817bb-145">Antwort</span><span class="sxs-lookup"><span data-stu-id="817bb-145">Response</span></span>
<span data-ttu-id="817bb-146">Wenn die Methode erfolgreich ist, werden 200 OK und die [Warnungsentität](alerts.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="817bb-146">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body.</span></span> <span data-ttu-id="817bb-147">Wenn warnung mit der angegebenen ID nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="817bb-147">If alert with the specified id was not found - 404 Not Found.</span></span>
