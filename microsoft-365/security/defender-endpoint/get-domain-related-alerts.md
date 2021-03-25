---
title: Abrufen der domänenbezogenen Benachrichtigungs-API
description: Erfahren Sie, wie Sie die API Zum Abrufen domänenbezogener Warnungen verwenden, um Warnungen im Zusammenhang mit einer bestimmten Domänenadresse in Microsoft Defender for Endpoint abzurufen.
keywords: apis, graph api, supported apis, get, domain, related, alerts
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
ms.openlocfilehash: f8de54072c0b0ebef69b8e5586fee058b971c51f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166572"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="00e07-104">Abrufen der domänenbezogenen Benachrichtigungs-API</span><span class="sxs-lookup"><span data-stu-id="00e07-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="00e07-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="00e07-105">**Applies to:**</span></span>
- [<span data-ttu-id="00e07-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="00e07-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="00e07-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00e07-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="00e07-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="00e07-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="00e07-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="00e07-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="00e07-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00e07-110">API description</span></span>
<span data-ttu-id="00e07-111">Ruft eine Auflistung von [Warnungen im](alerts.md) Zusammenhang mit einer bestimmten Domänenadresse ab.</span><span class="sxs-lookup"><span data-stu-id="00e07-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="00e07-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="00e07-112">Limitations</span></span>
1. <span data-ttu-id="00e07-113">Sie können Warnungen abfragen, die zuletzt entsprechend ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="00e07-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="00e07-114">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="00e07-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="00e07-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="00e07-115">Permissions</span></span>
<span data-ttu-id="00e07-116">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00e07-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="00e07-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="00e07-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="00e07-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="00e07-118">Permission type</span></span> |   <span data-ttu-id="00e07-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="00e07-119">Permission</span></span>  |   <span data-ttu-id="00e07-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="00e07-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="00e07-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="00e07-121">Application</span></span> |   <span data-ttu-id="00e07-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="00e07-122">Alert.Read.All</span></span> |    <span data-ttu-id="00e07-123">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="00e07-123">'Read all alerts'</span></span>
<span data-ttu-id="00e07-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="00e07-124">Application</span></span> |   <span data-ttu-id="00e07-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="00e07-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="00e07-126">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="00e07-126">'Read and write all alerts'</span></span>
<span data-ttu-id="00e07-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="00e07-127">Delegated (work or school account)</span></span> | <span data-ttu-id="00e07-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="00e07-128">Alert.Read</span></span> | <span data-ttu-id="00e07-129">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="00e07-129">'Read alerts'</span></span>
<span data-ttu-id="00e07-130">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="00e07-130">Delegated (work or school account)</span></span> | <span data-ttu-id="00e07-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="00e07-131">Alert.ReadWrite</span></span> | <span data-ttu-id="00e07-132">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="00e07-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="00e07-133">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="00e07-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="00e07-134">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="00e07-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="00e07-135">Die Antwort umfasst nur Warnungen, die Geräten zugeordnet sind und auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="00e07-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="00e07-136">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="00e07-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="00e07-137">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="00e07-137">Request headers</span></span>

| <span data-ttu-id="00e07-138">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="00e07-138">Header</span></span>        | <span data-ttu-id="00e07-139">Wert</span><span class="sxs-lookup"><span data-stu-id="00e07-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="00e07-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="00e07-140">Authorization</span></span> | <span data-ttu-id="00e07-141">String</span><span class="sxs-lookup"><span data-stu-id="00e07-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="00e07-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="00e07-142">Request body</span></span>
<span data-ttu-id="00e07-143">Empty</span><span class="sxs-lookup"><span data-stu-id="00e07-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="00e07-144">Antwort</span><span class="sxs-lookup"><span data-stu-id="00e07-144">Response</span></span>
<span data-ttu-id="00e07-145">Wenn erfolgreich und Domäne vorhanden ist – 200 OK mit Liste der [Benachrichtigungsentitäten.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="00e07-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="00e07-146">Wenn domäne nicht vorhanden ist - 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="00e07-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="00e07-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00e07-147">Example</span></span>

<span data-ttu-id="00e07-148">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="00e07-148">**Request**</span></span>

<span data-ttu-id="00e07-149">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="00e07-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
