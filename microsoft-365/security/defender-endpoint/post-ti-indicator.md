---
title: Senden oder Aktualisieren der Indikator-API
description: Erfahren Sie, wie Sie die Submit- oder Update Indicator-API verwenden, um eine neue Indicator-Entität in Microsoft Defender for Endpoint zu übermitteln oder zu aktualisieren.
keywords: apis, graph api, supported apis, submit, ti, indicator, update
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
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187254"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="a9972-104">Senden oder Aktualisieren der Indikator-API</span><span class="sxs-lookup"><span data-stu-id="a9972-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a9972-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a9972-105">**Applies to:**</span></span>
- [<span data-ttu-id="a9972-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a9972-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a9972-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a9972-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a9972-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a9972-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a9972-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a9972-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="a9972-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9972-110">API description</span></span>
<span data-ttu-id="a9972-111">Sendet oder aktualisiert die neue [Indicator-Entität.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="a9972-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="a9972-112">Die CIDR-Notation für IPs wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9972-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="a9972-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a9972-113">Limitations</span></span>
1. <span data-ttu-id="a9972-114">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="a9972-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="a9972-115">Es gibt einen Grenzwert von 15.000 aktiven Indikatoren pro Mandant.</span><span class="sxs-lookup"><span data-stu-id="a9972-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="a9972-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a9972-116">Permissions</span></span>
<span data-ttu-id="a9972-117">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a9972-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a9972-118">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Erste Schritte](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a9972-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="a9972-119">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="a9972-119">Permission type</span></span> |   <span data-ttu-id="a9972-120">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a9972-120">Permission</span></span>  |   <span data-ttu-id="a9972-121">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a9972-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a9972-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="a9972-122">Application</span></span> |   <span data-ttu-id="a9972-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a9972-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="a9972-124">"Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="a9972-124">'Read and write Indicators'</span></span>
<span data-ttu-id="a9972-125">Anwendung</span><span class="sxs-lookup"><span data-stu-id="a9972-125">Application</span></span> |   <span data-ttu-id="a9972-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="a9972-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="a9972-127">"Alle Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="a9972-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="a9972-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="a9972-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="a9972-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a9972-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="a9972-130">"Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="a9972-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="a9972-131">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="a9972-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="a9972-132">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="a9972-132">Request headers</span></span>

<span data-ttu-id="a9972-133">Name</span><span class="sxs-lookup"><span data-stu-id="a9972-133">Name</span></span> | <span data-ttu-id="a9972-134">Typ</span><span class="sxs-lookup"><span data-stu-id="a9972-134">Type</span></span> | <span data-ttu-id="a9972-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9972-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="a9972-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="a9972-136">Authorization</span></span> | <span data-ttu-id="a9972-137">String</span><span class="sxs-lookup"><span data-stu-id="a9972-137">String</span></span> | <span data-ttu-id="a9972-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a9972-138">Bearer {token}.</span></span> <span data-ttu-id="a9972-139">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="a9972-139">**Required**.</span></span>
<span data-ttu-id="a9972-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a9972-140">Content-Type</span></span> | <span data-ttu-id="a9972-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a9972-141">string</span></span> | <span data-ttu-id="a9972-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="a9972-142">application/json.</span></span> <span data-ttu-id="a9972-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="a9972-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a9972-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="a9972-144">Request body</span></span>
<span data-ttu-id="a9972-145">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="a9972-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="a9972-146">Parameter</span><span class="sxs-lookup"><span data-stu-id="a9972-146">Parameter</span></span> | <span data-ttu-id="a9972-147">Typ</span><span class="sxs-lookup"><span data-stu-id="a9972-147">Type</span></span>    | <span data-ttu-id="a9972-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9972-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="a9972-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="a9972-149">indicatorValue</span></span> | <span data-ttu-id="a9972-150">String</span><span class="sxs-lookup"><span data-stu-id="a9972-150">String</span></span> | <span data-ttu-id="a9972-151">Identität der [Indicator-Entität.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="a9972-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="a9972-152">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="a9972-152">**Required**</span></span>
<span data-ttu-id="a9972-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="a9972-153">indicatorType</span></span> | <span data-ttu-id="a9972-154">Enum</span><span class="sxs-lookup"><span data-stu-id="a9972-154">Enum</span></span> | <span data-ttu-id="a9972-155">Typ des Indikators.</span><span class="sxs-lookup"><span data-stu-id="a9972-155">Type of the indicator.</span></span> <span data-ttu-id="a9972-156">Mögliche Werte sind: "FileSha1", "FileSha256", "IpAddress", "DomainName" und "Url".</span><span class="sxs-lookup"><span data-stu-id="a9972-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="a9972-157">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="a9972-157">**Required**</span></span>
<span data-ttu-id="a9972-158">Aktion</span><span class="sxs-lookup"><span data-stu-id="a9972-158">action</span></span> | <span data-ttu-id="a9972-159">Enum</span><span class="sxs-lookup"><span data-stu-id="a9972-159">Enum</span></span> | <span data-ttu-id="a9972-160">Die Aktion, die ergriffen wird, wenn der Indikator in der Organisation ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="a9972-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="a9972-161">Mögliche Werte sind: "Alert", "AlertAndBlock" und "Allowed".</span><span class="sxs-lookup"><span data-stu-id="a9972-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="a9972-162">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="a9972-162">**Required**</span></span>
<span data-ttu-id="a9972-163">Anwendung</span><span class="sxs-lookup"><span data-stu-id="a9972-163">application</span></span> | <span data-ttu-id="a9972-164">String</span><span class="sxs-lookup"><span data-stu-id="a9972-164">String</span></span> | <span data-ttu-id="a9972-165">Die Anwendung, die dem Indikator zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a9972-165">The application associated with the indicator.</span></span> <span data-ttu-id="a9972-166">**Optional**</span><span class="sxs-lookup"><span data-stu-id="a9972-166">**Optional**</span></span>
<span data-ttu-id="a9972-167">title</span><span class="sxs-lookup"><span data-stu-id="a9972-167">title</span></span> | <span data-ttu-id="a9972-168">String</span><span class="sxs-lookup"><span data-stu-id="a9972-168">String</span></span> | <span data-ttu-id="a9972-169">Titel der Warnung des Indikators.</span><span class="sxs-lookup"><span data-stu-id="a9972-169">Indicator alert title.</span></span> <span data-ttu-id="a9972-170">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="a9972-170">**Required**</span></span>
<span data-ttu-id="a9972-171">description</span><span class="sxs-lookup"><span data-stu-id="a9972-171">description</span></span> | <span data-ttu-id="a9972-172">String</span><span class="sxs-lookup"><span data-stu-id="a9972-172">String</span></span> | <span data-ttu-id="a9972-173">Beschreibung des Indikators.</span><span class="sxs-lookup"><span data-stu-id="a9972-173">Description of the indicator.</span></span> <span data-ttu-id="a9972-174">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="a9972-174">**Required**</span></span>
<span data-ttu-id="a9972-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="a9972-175">expirationTime</span></span> | <span data-ttu-id="a9972-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a9972-176">DateTimeOffset</span></span> | <span data-ttu-id="a9972-177">Die Ablaufzeit des Indikators.</span><span class="sxs-lookup"><span data-stu-id="a9972-177">The expiration time of the indicator.</span></span> <span data-ttu-id="a9972-178">**Optional**</span><span class="sxs-lookup"><span data-stu-id="a9972-178">**Optional**</span></span>
<span data-ttu-id="a9972-179">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="a9972-179">severity</span></span> | <span data-ttu-id="a9972-180">Enum</span><span class="sxs-lookup"><span data-stu-id="a9972-180">Enum</span></span> | <span data-ttu-id="a9972-181">Der Schweregrad des Indikators.</span><span class="sxs-lookup"><span data-stu-id="a9972-181">The severity of the indicator.</span></span> <span data-ttu-id="a9972-182">mögliche Werte sind: "Informational", "Low", "Medium" und "High".</span><span class="sxs-lookup"><span data-stu-id="a9972-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="a9972-183">**Optional**</span><span class="sxs-lookup"><span data-stu-id="a9972-183">**Optional**</span></span>
<span data-ttu-id="a9972-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="a9972-184">recommendedActions</span></span> | <span data-ttu-id="a9972-185">String</span><span class="sxs-lookup"><span data-stu-id="a9972-185">String</span></span> | <span data-ttu-id="a9972-186">Empfohlene Aktionen zur Warnung des TI-Indikators.</span><span class="sxs-lookup"><span data-stu-id="a9972-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="a9972-187">**Optional**</span><span class="sxs-lookup"><span data-stu-id="a9972-187">**Optional**</span></span>
<span data-ttu-id="a9972-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="a9972-188">rbacGroupNames</span></span> | <span data-ttu-id="a9972-189">String</span><span class="sxs-lookup"><span data-stu-id="a9972-189">String</span></span> | <span data-ttu-id="a9972-190">Durch Kommas getrennte Liste der RBAC-Gruppennamen, auf die der Indikator angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a9972-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="a9972-191">**Optional**</span><span class="sxs-lookup"><span data-stu-id="a9972-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="a9972-192">Antwort</span><span class="sxs-lookup"><span data-stu-id="a9972-192">Response</span></span>
- <span data-ttu-id="a9972-193">Wenn die Methode erfolgreich ist, gibt sie den Antwortcode "200 - OK" und die Entität "Erstellt/aktualisiert [Indikator"](ti-indicator.md) im Antworttext zurück.</span><span class="sxs-lookup"><span data-stu-id="a9972-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="a9972-194">Wenn nicht erfolgreich: Diese Methode gibt 400 – Ungültige Anforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="a9972-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="a9972-195">Ungültige Anforderung gibt in der Regel einen falschen Textkörper an.</span><span class="sxs-lookup"><span data-stu-id="a9972-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="a9972-196">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9972-196">Example</span></span>

<span data-ttu-id="a9972-197">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="a9972-197">**Request**</span></span>

<span data-ttu-id="a9972-198">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="a9972-198">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a><span data-ttu-id="a9972-199">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="a9972-199">Related topic</span></span>
- [<span data-ttu-id="a9972-200">Verwalten von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="a9972-200">Manage indicators</span></span>](manage-indicators.md)
