---
title: Indikatorressourcentyp
description: Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators mit Microsoft Defender für Endpunkt.
keywords: APIs, unterstützte APIs, abrufen, TiIndicator, Indikator, zuletzt verwendet
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
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771381"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="dd223-104">Indikatorressourcentyp</span><span class="sxs-lookup"><span data-stu-id="dd223-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dd223-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="dd223-105">**Applies to:**</span></span>
- [<span data-ttu-id="dd223-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="dd223-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dd223-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd223-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dd223-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="dd223-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dd223-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="dd223-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="dd223-110">Weitere Informationen finden Sie auf der entsprechenden [Seite "Indikatoren"](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) im Portal.</span><span class="sxs-lookup"><span data-stu-id="dd223-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="dd223-111">Methode</span><span class="sxs-lookup"><span data-stu-id="dd223-111">Method</span></span>|<span data-ttu-id="dd223-112">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="dd223-112">Return Type</span></span> |<span data-ttu-id="dd223-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd223-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="dd223-114">Indikatoren auflisten</span><span class="sxs-lookup"><span data-stu-id="dd223-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="dd223-115">[Indikator](ti-indicator.md) Auflistung</span><span class="sxs-lookup"><span data-stu-id="dd223-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="dd223-116">Listenindikatorentitäten. [](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="dd223-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="dd223-117">Indikator für "Absenden"</span><span class="sxs-lookup"><span data-stu-id="dd223-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="dd223-118">Indikator</span><span class="sxs-lookup"><span data-stu-id="dd223-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="dd223-119">Senden oder Aktualisieren der Indikatorentität. [](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="dd223-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="dd223-120">Importindikatoren</span><span class="sxs-lookup"><span data-stu-id="dd223-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="dd223-121">[Indikator](ti-indicator.md) Auflistung</span><span class="sxs-lookup"><span data-stu-id="dd223-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="dd223-122">Übermitteln oder Aktualisieren von Indikatorenentitäten. [](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="dd223-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="dd223-123">Indikator löschen</span><span class="sxs-lookup"><span data-stu-id="dd223-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="dd223-124">Kein Inhalt</span><span class="sxs-lookup"><span data-stu-id="dd223-124">No Content</span></span> | <span data-ttu-id="dd223-125">Löscht [](ti-indicator.md) die Indikatorentität.</span><span class="sxs-lookup"><span data-stu-id="dd223-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="dd223-126">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dd223-126">Properties</span></span>
<span data-ttu-id="dd223-127">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dd223-127">Property</span></span> |  <span data-ttu-id="dd223-128">Typ</span><span class="sxs-lookup"><span data-stu-id="dd223-128">Type</span></span>    |   <span data-ttu-id="dd223-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd223-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="dd223-130">id</span><span class="sxs-lookup"><span data-stu-id="dd223-130">id</span></span> | <span data-ttu-id="dd223-131">String</span><span class="sxs-lookup"><span data-stu-id="dd223-131">String</span></span> | <span data-ttu-id="dd223-132">Die Identität [](ti-indicator.md) der Indikatorentität.</span><span class="sxs-lookup"><span data-stu-id="dd223-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="dd223-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="dd223-133">indicatorValue</span></span> | <span data-ttu-id="dd223-134">String</span><span class="sxs-lookup"><span data-stu-id="dd223-134">String</span></span> | <span data-ttu-id="dd223-135">Der Wert des [Indikators](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="dd223-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="dd223-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="dd223-136">indicatorType</span></span> | <span data-ttu-id="dd223-137">Enum</span><span class="sxs-lookup"><span data-stu-id="dd223-137">Enum</span></span> | <span data-ttu-id="dd223-138">Typ des Indikators.</span><span class="sxs-lookup"><span data-stu-id="dd223-138">Type of the indicator.</span></span> <span data-ttu-id="dd223-139">Mögliche Werte sind: "FileSha1", "FileSha256", "IpAddress", "DomainName" und "Url".</span><span class="sxs-lookup"><span data-stu-id="dd223-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="dd223-140">Anwendung</span><span class="sxs-lookup"><span data-stu-id="dd223-140">application</span></span> | <span data-ttu-id="dd223-141">String</span><span class="sxs-lookup"><span data-stu-id="dd223-141">String</span></span> | <span data-ttu-id="dd223-142">Die Anwendung, die dem Indikator zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="dd223-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="dd223-143">Aktion</span><span class="sxs-lookup"><span data-stu-id="dd223-143">action</span></span> | <span data-ttu-id="dd223-144">Enum</span><span class="sxs-lookup"><span data-stu-id="dd223-144">Enum</span></span> | <span data-ttu-id="dd223-145">Die Aktion, die ausgeführt wird, wenn der Indikator in der Organisation erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="dd223-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="dd223-146">Mögliche Werte sind: "Alert", "AlertAndBlock" und "Allowed".</span><span class="sxs-lookup"><span data-stu-id="dd223-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="dd223-147">Sourcetype</span><span class="sxs-lookup"><span data-stu-id="dd223-147">sourceType</span></span> | <span data-ttu-id="dd223-148">Enum</span><span class="sxs-lookup"><span data-stu-id="dd223-148">Enum</span></span> | <span data-ttu-id="dd223-149">"Benutzer" für den Fall, dass der Indikator von einem Benutzer erstellt wurde (z. B. aus dem Portal), "AadApp" für den Fall, dass er mithilfe einer automatisierten Anwendung über die API übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="dd223-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="dd223-150">source</span><span class="sxs-lookup"><span data-stu-id="dd223-150">source</span></span> | <span data-ttu-id="dd223-151">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="dd223-151">string</span></span> | <span data-ttu-id="dd223-152">Der Name des Benutzers/der Anwendung, die den Indikator übermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="dd223-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="dd223-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="dd223-153">createdBy</span></span> | <span data-ttu-id="dd223-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="dd223-154">String</span></span> | <span data-ttu-id="dd223-155">Eindeutige Identität des Benutzers/der Anwendung, die den Indikator übermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="dd223-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="dd223-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="dd223-156">lastUpdatedBy</span></span> | <span data-ttu-id="dd223-157">String</span><span class="sxs-lookup"><span data-stu-id="dd223-157">String</span></span> | <span data-ttu-id="dd223-158">Die Identität des Benutzers/der Anwendung, die den Indikator zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="dd223-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="dd223-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="dd223-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="dd223-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="dd223-160">DateTimeOffset</span></span> | <span data-ttu-id="dd223-161">Datum und Uhrzeit der Erstellung des Indikators.</span><span class="sxs-lookup"><span data-stu-id="dd223-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="dd223-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="dd223-162">expirationTime</span></span> | <span data-ttu-id="dd223-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="dd223-163">DateTimeOffset</span></span> | <span data-ttu-id="dd223-164">Die Ablaufzeit des Indikators.</span><span class="sxs-lookup"><span data-stu-id="dd223-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="dd223-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="dd223-165">lastUpdateTime</span></span> | <span data-ttu-id="dd223-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="dd223-166">DateTimeOffset</span></span> | <span data-ttu-id="dd223-167">Der Zeitpunkt der letzten Aktualisierung des Indikators.</span><span class="sxs-lookup"><span data-stu-id="dd223-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="dd223-168">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="dd223-168">severity</span></span> | <span data-ttu-id="dd223-169">Enum</span><span class="sxs-lookup"><span data-stu-id="dd223-169">Enum</span></span> | <span data-ttu-id="dd223-170">Der Schweregrad des Indikators.</span><span class="sxs-lookup"><span data-stu-id="dd223-170">The severity of the indicator.</span></span> <span data-ttu-id="dd223-171">Mögliche Werte sind: "Informational", "Low", "Medium" und "High".</span><span class="sxs-lookup"><span data-stu-id="dd223-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="dd223-172">title</span><span class="sxs-lookup"><span data-stu-id="dd223-172">title</span></span> | <span data-ttu-id="dd223-173">String</span><span class="sxs-lookup"><span data-stu-id="dd223-173">String</span></span> | <span data-ttu-id="dd223-174">Titel des Indikators.</span><span class="sxs-lookup"><span data-stu-id="dd223-174">Indicator title.</span></span>
<span data-ttu-id="dd223-175">description</span><span class="sxs-lookup"><span data-stu-id="dd223-175">description</span></span> | <span data-ttu-id="dd223-176">String</span><span class="sxs-lookup"><span data-stu-id="dd223-176">String</span></span> | <span data-ttu-id="dd223-177">Beschreibung des Indikators.</span><span class="sxs-lookup"><span data-stu-id="dd223-177">Description of the indicator.</span></span>
<span data-ttu-id="dd223-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="dd223-178">recommendedActions</span></span> | <span data-ttu-id="dd223-179">String</span><span class="sxs-lookup"><span data-stu-id="dd223-179">String</span></span> | <span data-ttu-id="dd223-180">Empfohlene Aktionen für den Indikator.</span><span class="sxs-lookup"><span data-stu-id="dd223-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="dd223-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="dd223-181">rbacGroupNames</span></span> | <span data-ttu-id="dd223-182">Liste der Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="dd223-182">List of strings</span></span> | <span data-ttu-id="dd223-183">RBAC-Gerätegruppennamen, in denen der Indikator verfügbar und aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="dd223-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="dd223-184">Leere Liste für den Fall, dass sie für alle Geräte verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="dd223-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="dd223-185">JSON-Darstellung</span><span class="sxs-lookup"><span data-stu-id="dd223-185">Json representation</span></span>

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
