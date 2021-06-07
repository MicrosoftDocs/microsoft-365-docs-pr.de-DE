---
title: API zum Abrufen domänenbezogener Warnungen
description: Erfahren Sie, wie Sie die API zum Abrufen domänenbezogener Warnungen verwenden, um Warnungen im Zusammenhang mit einer bestimmten Domänenadresse in Microsoft Defender für Endpunkt abzurufen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Domäne, verwandte, Warnungen
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
ms.openlocfilehash: c5de779566f1aa8e53da10b9aa5bceb92f5a0a3c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772257"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="af1b1-104">API zum Abrufen domänenbezogener Warnungen</span><span class="sxs-lookup"><span data-stu-id="af1b1-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="af1b1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="af1b1-105">**Applies to:**</span></span>
- [<span data-ttu-id="af1b1-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="af1b1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="af1b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af1b1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="af1b1-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="af1b1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="af1b1-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="af1b1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="af1b1-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af1b1-110">API description</span></span>
<span data-ttu-id="af1b1-111">Ruft eine Sammlung von [Warnungen](alerts.md) im Zusammenhang mit einer bestimmten Domänenadresse ab.</span><span class="sxs-lookup"><span data-stu-id="af1b1-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="af1b1-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="af1b1-112">Limitations</span></span>
1. <span data-ttu-id="af1b1-113">Sie können nach Warnungen abfragen, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="af1b1-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="af1b1-114">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="af1b1-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="af1b1-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="af1b1-115">Permissions</span></span>
<span data-ttu-id="af1b1-116">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="af1b1-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="af1b1-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="af1b1-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="af1b1-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="af1b1-118">Permission type</span></span> |   <span data-ttu-id="af1b1-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="af1b1-119">Permission</span></span>  |   <span data-ttu-id="af1b1-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="af1b1-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="af1b1-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="af1b1-121">Application</span></span> |   <span data-ttu-id="af1b1-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="af1b1-122">Alert.Read.All</span></span> |    <span data-ttu-id="af1b1-123">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="af1b1-123">'Read all alerts'</span></span>
<span data-ttu-id="af1b1-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="af1b1-124">Application</span></span> |   <span data-ttu-id="af1b1-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="af1b1-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="af1b1-126">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="af1b1-126">'Read and write all alerts'</span></span>
<span data-ttu-id="af1b1-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="af1b1-127">Delegated (work or school account)</span></span> | <span data-ttu-id="af1b1-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="af1b1-128">Alert.Read</span></span> | <span data-ttu-id="af1b1-129">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="af1b1-129">'Read alerts'</span></span>
<span data-ttu-id="af1b1-130">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="af1b1-130">Delegated (work or school account)</span></span> | <span data-ttu-id="af1b1-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="af1b1-131">Alert.ReadWrite</span></span> | <span data-ttu-id="af1b1-132">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="af1b1-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="af1b1-133">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="af1b1-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="af1b1-134">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="af1b1-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="af1b1-135">Die Antwort enthält nur Warnungen, die Geräten zugeordnet sind, auf die der Benutzer zugriff hat, basierend auf Gerätegruppeneinstellungen (weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="af1b1-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="af1b1-136">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="af1b1-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="af1b1-137">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="af1b1-137">Request headers</span></span>

| <span data-ttu-id="af1b1-138">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="af1b1-138">Header</span></span>        | <span data-ttu-id="af1b1-139">Wert</span><span class="sxs-lookup"><span data-stu-id="af1b1-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="af1b1-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="af1b1-140">Authorization</span></span> | <span data-ttu-id="af1b1-141">String</span><span class="sxs-lookup"><span data-stu-id="af1b1-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="af1b1-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="af1b1-142">Request body</span></span>
<span data-ttu-id="af1b1-143">Empty</span><span class="sxs-lookup"><span data-stu-id="af1b1-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="af1b1-144">Antwort</span><span class="sxs-lookup"><span data-stu-id="af1b1-144">Response</span></span>
<span data-ttu-id="af1b1-145">Wenn erfolgreich und Domäne vorhanden – 200 OK mit Liste der Warnungsentitäten. [](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="af1b1-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="af1b1-146">Wenn Domäne nicht vorhanden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="af1b1-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="af1b1-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af1b1-147">Example</span></span>

<span data-ttu-id="af1b1-148">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="af1b1-148">**Request**</span></span>

<span data-ttu-id="af1b1-149">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="af1b1-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
