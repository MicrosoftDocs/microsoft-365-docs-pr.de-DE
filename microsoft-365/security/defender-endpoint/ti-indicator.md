---
title: Indikatorressourcentyp
description: Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators mithilfe von Microsoft Defender for Endpoint.
keywords: apis, supported apis, get, TiIndicator, Indicator, recent
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
ms.openlocfilehash: bbd908c15f4d65d4923c088261c92de6d2d3cc35
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187206"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="a871c-104">Indikatorressourcentyp</span><span class="sxs-lookup"><span data-stu-id="a871c-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a871c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a871c-105">**Applies to:**</span></span>
- [<span data-ttu-id="a871c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a871c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a871c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a871c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a871c-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a871c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a871c-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a871c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="a871c-110">Weitere Informationen finden Sie [auf der entsprechenden Seite Indikatoren](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) im Portal.</span><span class="sxs-lookup"><span data-stu-id="a871c-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="a871c-111">Methode</span><span class="sxs-lookup"><span data-stu-id="a871c-111">Method</span></span>|<span data-ttu-id="a871c-112">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="a871c-112">Return Type</span></span> |<span data-ttu-id="a871c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a871c-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="a871c-114">Auflisten von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="a871c-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="a871c-115">[Indikator](ti-indicator.md) Sammlung</span><span class="sxs-lookup"><span data-stu-id="a871c-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="a871c-116">Auflisten von Indikatorentitäten. [](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="a871c-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="a871c-117">Submit Indicator</span><span class="sxs-lookup"><span data-stu-id="a871c-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="a871c-118">Indikator</span><span class="sxs-lookup"><span data-stu-id="a871c-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="a871c-119">Senden oder Aktualisieren [der Indicator-Entität.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="a871c-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="a871c-120">Importindikatoren</span><span class="sxs-lookup"><span data-stu-id="a871c-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="a871c-121">[Indikator](ti-indicator.md) Sammlung</span><span class="sxs-lookup"><span data-stu-id="a871c-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="a871c-122">Senden oder Aktualisieren von Indicators-Entitäten. [](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="a871c-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="a871c-123">Löschindikator</span><span class="sxs-lookup"><span data-stu-id="a871c-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="a871c-124">Kein Inhalt</span><span class="sxs-lookup"><span data-stu-id="a871c-124">No Content</span></span> | <span data-ttu-id="a871c-125">Löscht die [Indicator-Entität.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="a871c-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="a871c-126">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a871c-126">Properties</span></span>
<span data-ttu-id="a871c-127">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a871c-127">Property</span></span> |  <span data-ttu-id="a871c-128">Typ</span><span class="sxs-lookup"><span data-stu-id="a871c-128">Type</span></span>    |   <span data-ttu-id="a871c-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a871c-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="a871c-130">id</span><span class="sxs-lookup"><span data-stu-id="a871c-130">id</span></span> | <span data-ttu-id="a871c-131">String</span><span class="sxs-lookup"><span data-stu-id="a871c-131">String</span></span> | <span data-ttu-id="a871c-132">Identität der [Indicator-Entität.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="a871c-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="a871c-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="a871c-133">indicatorValue</span></span> | <span data-ttu-id="a871c-134">String</span><span class="sxs-lookup"><span data-stu-id="a871c-134">String</span></span> | <span data-ttu-id="a871c-135">Der Wert des [Indikators](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="a871c-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="a871c-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="a871c-136">indicatorType</span></span> | <span data-ttu-id="a871c-137">Enum</span><span class="sxs-lookup"><span data-stu-id="a871c-137">Enum</span></span> | <span data-ttu-id="a871c-138">Typ des Indikators.</span><span class="sxs-lookup"><span data-stu-id="a871c-138">Type of the indicator.</span></span> <span data-ttu-id="a871c-139">Mögliche Werte sind: "FileSha1", "FileSha256", "IpAddress", "DomainName" und "Url".</span><span class="sxs-lookup"><span data-stu-id="a871c-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="a871c-140">Anwendung</span><span class="sxs-lookup"><span data-stu-id="a871c-140">application</span></span> | <span data-ttu-id="a871c-141">String</span><span class="sxs-lookup"><span data-stu-id="a871c-141">String</span></span> | <span data-ttu-id="a871c-142">Die Anwendung, die dem Indikator zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a871c-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="a871c-143">Aktion</span><span class="sxs-lookup"><span data-stu-id="a871c-143">action</span></span> | <span data-ttu-id="a871c-144">Enum</span><span class="sxs-lookup"><span data-stu-id="a871c-144">Enum</span></span> | <span data-ttu-id="a871c-145">Die Aktion, die ergriffen wird, wenn der Indikator in der Organisation ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="a871c-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="a871c-146">Mögliche Werte sind: "Alert", "AlertAndBlock" und "Allowed".</span><span class="sxs-lookup"><span data-stu-id="a871c-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="a871c-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="a871c-147">sourceType</span></span> | <span data-ttu-id="a871c-148">Enum</span><span class="sxs-lookup"><span data-stu-id="a871c-148">Enum</span></span> | <span data-ttu-id="a871c-149">"User" für den Fall, dass der indikator, der von einem Benutzer (z. B. aus dem Portal) erstellt wurde, "AadApp" für den Fall, dass er mithilfe einer automatisierten Anwendung über die API übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="a871c-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="a871c-150">source</span><span class="sxs-lookup"><span data-stu-id="a871c-150">source</span></span> | <span data-ttu-id="a871c-151">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a871c-151">string</span></span> | <span data-ttu-id="a871c-152">Der Name des Benutzers/der Anwendung, der den Indikator übermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="a871c-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="a871c-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="a871c-153">createdBy</span></span> | <span data-ttu-id="a871c-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a871c-154">String</span></span> | <span data-ttu-id="a871c-155">Eindeutige Identität des Benutzers/der Anwendung, der den Indikator übermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="a871c-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="a871c-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="a871c-156">lastUpdatedBy</span></span> | <span data-ttu-id="a871c-157">String</span><span class="sxs-lookup"><span data-stu-id="a871c-157">String</span></span> | <span data-ttu-id="a871c-158">Die Identität des Benutzers/der Anwendung, der den Indikator zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="a871c-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="a871c-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="a871c-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="a871c-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a871c-160">DateTimeOffset</span></span> | <span data-ttu-id="a871c-161">Datum und Uhrzeit, zu der der Indikator erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a871c-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="a871c-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="a871c-162">expirationTime</span></span> | <span data-ttu-id="a871c-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a871c-163">DateTimeOffset</span></span> | <span data-ttu-id="a871c-164">Die Ablaufzeit des Indikators.</span><span class="sxs-lookup"><span data-stu-id="a871c-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="a871c-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="a871c-165">lastUpdateTime</span></span> | <span data-ttu-id="a871c-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a871c-166">DateTimeOffset</span></span> | <span data-ttu-id="a871c-167">Das letzte Mal, wenn der Indikator aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a871c-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="a871c-168">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="a871c-168">severity</span></span> | <span data-ttu-id="a871c-169">Enum</span><span class="sxs-lookup"><span data-stu-id="a871c-169">Enum</span></span> | <span data-ttu-id="a871c-170">Der Schweregrad des Indikators.</span><span class="sxs-lookup"><span data-stu-id="a871c-170">The severity of the indicator.</span></span> <span data-ttu-id="a871c-171">mögliche Werte sind: "Informational", "Low", "Medium" und "High".</span><span class="sxs-lookup"><span data-stu-id="a871c-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="a871c-172">title</span><span class="sxs-lookup"><span data-stu-id="a871c-172">title</span></span> | <span data-ttu-id="a871c-173">String</span><span class="sxs-lookup"><span data-stu-id="a871c-173">String</span></span> | <span data-ttu-id="a871c-174">Indikatortitel.</span><span class="sxs-lookup"><span data-stu-id="a871c-174">Indicator title.</span></span>
<span data-ttu-id="a871c-175">description</span><span class="sxs-lookup"><span data-stu-id="a871c-175">description</span></span> | <span data-ttu-id="a871c-176">String</span><span class="sxs-lookup"><span data-stu-id="a871c-176">String</span></span> | <span data-ttu-id="a871c-177">Beschreibung des Indikators.</span><span class="sxs-lookup"><span data-stu-id="a871c-177">Description of the indicator.</span></span>
<span data-ttu-id="a871c-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="a871c-178">recommendedActions</span></span> | <span data-ttu-id="a871c-179">String</span><span class="sxs-lookup"><span data-stu-id="a871c-179">String</span></span> | <span data-ttu-id="a871c-180">Empfohlene Aktionen für den Indikator.</span><span class="sxs-lookup"><span data-stu-id="a871c-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="a871c-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="a871c-181">rbacGroupNames</span></span> | <span data-ttu-id="a871c-182">Liste der Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="a871c-182">List of strings</span></span> | <span data-ttu-id="a871c-183">RBAC-Gerätegruppennamen, bei denen der Indikator verfügbar und aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="a871c-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="a871c-184">Leere Liste für den Fall, dass sie für alle Geräte verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="a871c-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="a871c-185">Json-Darstellung</span><span class="sxs-lookup"><span data-stu-id="a871c-185">Json representation</span></span>

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
