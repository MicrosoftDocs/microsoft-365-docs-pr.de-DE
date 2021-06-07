---
title: Übermitteln oder Aktualisieren der Indikator-API
description: Erfahren Sie, wie Sie die Api zum Senden oder Aktualisieren von Indikatoren verwenden, um eine neue Indikatorentität in Microsoft Defender für Endpunkt zu übermitteln oder zu aktualisieren.
keywords: APIs, Graph-API, unterstützte APIs, übermitteln, TI, Indikator, aktualisieren
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
ms.openlocfilehash: ce0dc0ce255e9717082687bd1f8bf5941739261d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771705"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="8dc72-104">Übermitteln oder Aktualisieren der Indikator-API</span><span class="sxs-lookup"><span data-stu-id="8dc72-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8dc72-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8dc72-105">**Applies to:**</span></span>
- [<span data-ttu-id="8dc72-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8dc72-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8dc72-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8dc72-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8dc72-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="8dc72-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8dc72-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="8dc72-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="8dc72-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8dc72-110">API description</span></span>
<span data-ttu-id="8dc72-111">Sendet oder aktualisiert [](ti-indicator.md) die neue Indikatorentität.</span><span class="sxs-lookup"><span data-stu-id="8dc72-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="8dc72-112">Die CIDR-Notation für IPs wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8dc72-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="8dc72-113">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="8dc72-113">Limitations</span></span>
1. <span data-ttu-id="8dc72-114">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="8dc72-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="8dc72-115">Es gibt einen Grenzwert von 15.000 aktiven Indikatoren pro Mandant.</span><span class="sxs-lookup"><span data-stu-id="8dc72-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="8dc72-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8dc72-116">Permissions</span></span>
<span data-ttu-id="8dc72-117">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8dc72-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8dc72-118">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter ["Erste Schritte".](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8dc72-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="8dc72-119">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="8dc72-119">Permission type</span></span> |   <span data-ttu-id="8dc72-120">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8dc72-120">Permission</span></span>  |   <span data-ttu-id="8dc72-121">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8dc72-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8dc72-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="8dc72-122">Application</span></span> |   <span data-ttu-id="8dc72-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8dc72-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="8dc72-124">"Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="8dc72-124">'Read and write Indicators'</span></span>
<span data-ttu-id="8dc72-125">Anwendung</span><span class="sxs-lookup"><span data-stu-id="8dc72-125">Application</span></span> |   <span data-ttu-id="8dc72-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8dc72-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="8dc72-127">"Alle Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="8dc72-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="8dc72-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="8dc72-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="8dc72-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8dc72-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="8dc72-130">"Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="8dc72-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="8dc72-131">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="8dc72-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="8dc72-132">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="8dc72-132">Request headers</span></span>

<span data-ttu-id="8dc72-133">Name</span><span class="sxs-lookup"><span data-stu-id="8dc72-133">Name</span></span> | <span data-ttu-id="8dc72-134">Typ</span><span class="sxs-lookup"><span data-stu-id="8dc72-134">Type</span></span> | <span data-ttu-id="8dc72-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8dc72-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="8dc72-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="8dc72-136">Authorization</span></span> | <span data-ttu-id="8dc72-137">String</span><span class="sxs-lookup"><span data-stu-id="8dc72-137">String</span></span> | <span data-ttu-id="8dc72-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8dc72-138">Bearer {token}.</span></span> <span data-ttu-id="8dc72-139">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8dc72-139">**Required**.</span></span>
<span data-ttu-id="8dc72-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8dc72-140">Content-Type</span></span> | <span data-ttu-id="8dc72-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8dc72-141">string</span></span> | <span data-ttu-id="8dc72-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="8dc72-142">application/json.</span></span> <span data-ttu-id="8dc72-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8dc72-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8dc72-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="8dc72-144">Request body</span></span>
<span data-ttu-id="8dc72-145">Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:</span><span class="sxs-lookup"><span data-stu-id="8dc72-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="8dc72-146">Parameter</span><span class="sxs-lookup"><span data-stu-id="8dc72-146">Parameter</span></span> | <span data-ttu-id="8dc72-147">Typ</span><span class="sxs-lookup"><span data-stu-id="8dc72-147">Type</span></span>    | <span data-ttu-id="8dc72-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8dc72-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="8dc72-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="8dc72-149">indicatorValue</span></span> | <span data-ttu-id="8dc72-150">String</span><span class="sxs-lookup"><span data-stu-id="8dc72-150">String</span></span> | <span data-ttu-id="8dc72-151">Die Identität [](ti-indicator.md) der Indikatorentität.</span><span class="sxs-lookup"><span data-stu-id="8dc72-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="8dc72-152">**Required**</span><span class="sxs-lookup"><span data-stu-id="8dc72-152">**Required**</span></span>
<span data-ttu-id="8dc72-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="8dc72-153">indicatorType</span></span> | <span data-ttu-id="8dc72-154">Enum</span><span class="sxs-lookup"><span data-stu-id="8dc72-154">Enum</span></span> | <span data-ttu-id="8dc72-155">Typ des Indikators.</span><span class="sxs-lookup"><span data-stu-id="8dc72-155">Type of the indicator.</span></span> <span data-ttu-id="8dc72-156">Mögliche Werte sind: "FileSha1", "FileSha256", "IpAddress", "DomainName" und "Url".</span><span class="sxs-lookup"><span data-stu-id="8dc72-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="8dc72-157">**Required**</span><span class="sxs-lookup"><span data-stu-id="8dc72-157">**Required**</span></span>
<span data-ttu-id="8dc72-158">Aktion</span><span class="sxs-lookup"><span data-stu-id="8dc72-158">action</span></span> | <span data-ttu-id="8dc72-159">Enum</span><span class="sxs-lookup"><span data-stu-id="8dc72-159">Enum</span></span> | <span data-ttu-id="8dc72-160">Die Aktion, die ausgeführt wird, wenn der Indikator in der Organisation erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="8dc72-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="8dc72-161">Mögliche Werte sind: "Alert", "AlertAndBlock" und "Allowed".</span><span class="sxs-lookup"><span data-stu-id="8dc72-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="8dc72-162">**Required**</span><span class="sxs-lookup"><span data-stu-id="8dc72-162">**Required**</span></span>
<span data-ttu-id="8dc72-163">Anwendung</span><span class="sxs-lookup"><span data-stu-id="8dc72-163">application</span></span> | <span data-ttu-id="8dc72-164">String</span><span class="sxs-lookup"><span data-stu-id="8dc72-164">String</span></span> | <span data-ttu-id="8dc72-165">Die Anwendung, die dem Indikator zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8dc72-165">The application associated with the indicator.</span></span> <span data-ttu-id="8dc72-166">**Optional**</span><span class="sxs-lookup"><span data-stu-id="8dc72-166">**Optional**</span></span>
<span data-ttu-id="8dc72-167">title</span><span class="sxs-lookup"><span data-stu-id="8dc72-167">title</span></span> | <span data-ttu-id="8dc72-168">String</span><span class="sxs-lookup"><span data-stu-id="8dc72-168">String</span></span> | <span data-ttu-id="8dc72-169">Titel der Indikatorwarnung.</span><span class="sxs-lookup"><span data-stu-id="8dc72-169">Indicator alert title.</span></span> <span data-ttu-id="8dc72-170">**Required**</span><span class="sxs-lookup"><span data-stu-id="8dc72-170">**Required**</span></span>
<span data-ttu-id="8dc72-171">description</span><span class="sxs-lookup"><span data-stu-id="8dc72-171">description</span></span> | <span data-ttu-id="8dc72-172">String</span><span class="sxs-lookup"><span data-stu-id="8dc72-172">String</span></span> | <span data-ttu-id="8dc72-173">Beschreibung des Indikators.</span><span class="sxs-lookup"><span data-stu-id="8dc72-173">Description of the indicator.</span></span> <span data-ttu-id="8dc72-174">**Required**</span><span class="sxs-lookup"><span data-stu-id="8dc72-174">**Required**</span></span>
<span data-ttu-id="8dc72-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="8dc72-175">expirationTime</span></span> | <span data-ttu-id="8dc72-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8dc72-176">DateTimeOffset</span></span> | <span data-ttu-id="8dc72-177">Die Ablaufzeit des Indikators.</span><span class="sxs-lookup"><span data-stu-id="8dc72-177">The expiration time of the indicator.</span></span> <span data-ttu-id="8dc72-178">**Optional**</span><span class="sxs-lookup"><span data-stu-id="8dc72-178">**Optional**</span></span>
<span data-ttu-id="8dc72-179">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="8dc72-179">severity</span></span> | <span data-ttu-id="8dc72-180">Enum</span><span class="sxs-lookup"><span data-stu-id="8dc72-180">Enum</span></span> | <span data-ttu-id="8dc72-181">Der Schweregrad des Indikators.</span><span class="sxs-lookup"><span data-stu-id="8dc72-181">The severity of the indicator.</span></span> <span data-ttu-id="8dc72-182">Mögliche Werte sind: "Informational", "Low", "Medium" und "High".</span><span class="sxs-lookup"><span data-stu-id="8dc72-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="8dc72-183">**Optional**</span><span class="sxs-lookup"><span data-stu-id="8dc72-183">**Optional**</span></span>
<span data-ttu-id="8dc72-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="8dc72-184">recommendedActions</span></span> | <span data-ttu-id="8dc72-185">String</span><span class="sxs-lookup"><span data-stu-id="8dc72-185">String</span></span> | <span data-ttu-id="8dc72-186">Empfohlene Aktionen für TI-Indikatorwarnung.</span><span class="sxs-lookup"><span data-stu-id="8dc72-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="8dc72-187">**Optional**</span><span class="sxs-lookup"><span data-stu-id="8dc72-187">**Optional**</span></span>
<span data-ttu-id="8dc72-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="8dc72-188">rbacGroupNames</span></span> | <span data-ttu-id="8dc72-189">String</span><span class="sxs-lookup"><span data-stu-id="8dc72-189">String</span></span> | <span data-ttu-id="8dc72-190">Durch Trennzeichen getrennte Liste der RBAC-Gruppennamen, auf die der Indikator angewendet werden würde.</span><span class="sxs-lookup"><span data-stu-id="8dc72-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="8dc72-191">**Optional**</span><span class="sxs-lookup"><span data-stu-id="8dc72-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="8dc72-192">Antwort</span><span class="sxs-lookup"><span data-stu-id="8dc72-192">Response</span></span>
- <span data-ttu-id="8dc72-193">Wenn die Methode erfolgreich ist, werden der Antwortcode 200 – OK und die erstellte/aktualisierte [Indikatorentität](ti-indicator.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8dc72-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="8dc72-194">Wenn nicht erfolgreich: Diese Methode gibt "400 – Ungültige Anforderung" zurück.</span><span class="sxs-lookup"><span data-stu-id="8dc72-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="8dc72-195">Eine ungültige Anforderung weist in der Regel auf einen falschen Textkörper hin.</span><span class="sxs-lookup"><span data-stu-id="8dc72-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="8dc72-196">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8dc72-196">Example</span></span>

<span data-ttu-id="8dc72-197">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="8dc72-197">**Request**</span></span>

<span data-ttu-id="8dc72-198">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="8dc72-198">Here is an example of the request.</span></span>

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

## <a name="related-topic"></a><span data-ttu-id="8dc72-199">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="8dc72-199">Related topic</span></span>
- [<span data-ttu-id="8dc72-200">Indikatoren verwalten</span><span class="sxs-lookup"><span data-stu-id="8dc72-200">Manage indicators</span></span>](manage-indicators.md)
