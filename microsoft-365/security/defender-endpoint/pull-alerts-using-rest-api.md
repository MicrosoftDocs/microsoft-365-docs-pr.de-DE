---
title: Abrufen von Microsoft Defender für Endpunkterkennungen mithilfe der REST-API
description: Erfahren Sie, wie Sie einen Microsoft Defender für Endpunkt-API-Endpunkt aufrufen, um Erkennungen mithilfe der SIEM-REST-API im JSON-Format abzurufen.
keywords: Erkennungen, Pullerkennungen, Rest-API, Anforderung, Antwort
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: 6716b0eb029b49ec08cb52ebefc23e50b19036ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771669"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a><span data-ttu-id="bd2af-104">Abrufen von Microsoft Defender für Endpunkterkennungen mithilfe der SIEM-REST-API</span><span class="sxs-lookup"><span data-stu-id="bd2af-104">Pull Microsoft Defender for Endpoint detections using SIEM REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bd2af-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bd2af-105">**Applies to:**</span></span>
- [<span data-ttu-id="bd2af-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bd2af-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bd2af-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd2af-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bd2af-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="bd2af-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bd2af-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bd2af-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- <span data-ttu-id="bd2af-110">[Microsoft Defender für Endpunkt-Warnung](alerts.md) besteht aus einer oder mehreren Erkennungen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-110">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="bd2af-111">[Die Microsoft Defender für Endpunkterkennung](api-portal-mapping.md) besteht aus dem verdächtigen Ereignis, das auf dem Gerät aufgetreten ist, und den zugehörigen Warnungsdetails.</span><span class="sxs-lookup"><span data-stu-id="bd2af-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="bd2af-112">-Die Microsoft Defender für Endpunkt-Warnungs-API ist die neueste API für die Benachrichtigungsnutzung und enthält eine detaillierte Liste der zugehörigen Nachweise für jede Warnung.</span><span class="sxs-lookup"><span data-stu-id="bd2af-112">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="bd2af-113">Weitere Informationen finden Sie unter ["Warnungsmethoden und -eigenschaften"](alerts.md) und ["Warnungen auflisten".](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="bd2af-113">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="bd2af-114">Microsoft Defender für Endpunkt unterstützt das OAuth 2.0-Protokoll, um Erkennungen aus der API abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-114">Microsoft Defender for Endpoint supports the OAuth 2.0 protocol to pull detections from the API.</span></span>

<span data-ttu-id="bd2af-115">Im Allgemeinen unterstützt das OAuth 2.0-Protokoll vier Arten von Flüssen:</span><span class="sxs-lookup"><span data-stu-id="bd2af-115">In general, the OAuth 2.0 protocol supports four types of flows:</span></span>
- <span data-ttu-id="bd2af-116">Autorisierungserteilungsfluss</span><span class="sxs-lookup"><span data-stu-id="bd2af-116">Authorization grant flow</span></span>
- <span data-ttu-id="bd2af-117">Impliziter Fluss</span><span class="sxs-lookup"><span data-stu-id="bd2af-117">Implicit flow</span></span>
- <span data-ttu-id="bd2af-118">Clientanmeldeinformationsfluss</span><span class="sxs-lookup"><span data-stu-id="bd2af-118">Client credentials flow</span></span>
- <span data-ttu-id="bd2af-119">Ressourcenbesitzerablauf</span><span class="sxs-lookup"><span data-stu-id="bd2af-119">Resource owner flow</span></span>

<span data-ttu-id="bd2af-120">Weitere Informationen zu den OAuth-Spezifikationen finden Sie auf der [OAuth-Website.](http://www.oauth.net)</span><span class="sxs-lookup"><span data-stu-id="bd2af-120">For more information about the OAuth specifications, see the [OAuth Website](http://www.oauth.net).</span></span>

<span data-ttu-id="bd2af-121">Microsoft Defender für Endpunkt unterstützt den _Autorisierungserteilungs-_ und _Clientanmeldeinformationsfluss,_ um Zugriff auf Pullerkennungen mit Azure Active Directory (AAD) als Autorisierungsserver zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bd2af-121">Microsoft Defender for Endpoint supports the _Authorization grant flow_ and _Client credential flow_ to obtain access to pull detections, with Azure Active Directory (AAD) as the authorization server.</span></span>

<span data-ttu-id="bd2af-122">Der _Autorisierungserteilungsfluss_ verwendet Benutzeranmeldeinformationen, um einen Autorisierungscode abzurufen, der dann zum Abrufen eines Zugriffstokens verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bd2af-122">The _Authorization grant flow_ uses user credentials to get an authorization code, which is then used to obtain an access token.</span></span>

<span data-ttu-id="bd2af-123">Der _Clientanmeldeinformationsfluss_ verwendet Clientanmeldeinformationen, um sich bei der Microsoft Defender für Endpunkt-Endpunkt-URL zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="bd2af-123">The _Client credential flow_ uses client credentials to authenticate against the Microsoft Defender for Endpoint endpoint URL.</span></span> <span data-ttu-id="bd2af-124">Dieser Fluss eignet sich für Szenarien, in denen ein OAuth-Client Anforderungen an eine API erstellt, für die keine Benutzeranmeldeinformationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bd2af-124">This flow is suitable for scenarios when an OAuth client creates requests to an API that doesn't require user credentials.</span></span>

<span data-ttu-id="bd2af-125">Verwenden Sie die folgende Methode in der Microsoft Defender für Endpunkt-API, um Erkennungen im JSON-Format abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-125">Use the following method in the Microsoft Defender for Endpoint API to pull detections in JSON format.</span></span>

>[!NOTE]
><span data-ttu-id="bd2af-126">Microsoft Defender Security Center führt ähnliche Warnungserkennungen in einer einzigen Warnung zusammen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-126">Microsoft Defender Security Center merges similar alert detections into a single alert.</span></span> <span data-ttu-id="bd2af-127">Diese API ruft Warnungserkennungen in der rohen Form basierend auf den von Ihnen festgelegten Abfrageparametern ab, sodass Sie Ihre eigene Gruppierung und Filterung anwenden können.</span><span class="sxs-lookup"><span data-stu-id="bd2af-127">This API pulls alert detections in its raw form based on the query parameters you set, enabling you to apply your own grouping and filtering.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="bd2af-128">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="bd2af-128">Before you begin</span></span>
- <span data-ttu-id="bd2af-129">Bevor Sie den Microsoft Defender für Endpunkt-Endpunkt aufrufen, um Erkennungen abzurufen, müssen Sie die SIEM-Integrationsanwendung in Azure Active Directory (AAD) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="bd2af-129">Before calling the Microsoft Defender for Endpoint endpoint to pull detections, you'll need to enable the SIEM integration application in Azure Active Directory (AAD).</span></span> <span data-ttu-id="bd2af-130">Weitere Informationen finden Sie unter [Aktivieren der SIEM-Integration in Microsoft Defender für Endpunkt.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="bd2af-130">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="bd2af-p106">Notieren Sie sich die folgenden Werte bei der Registrierung Ihrer Azure-App. Sie benötigen diese Werte, um den OAuth-Fluss in Ihrem Dienst oder Ihrer Dämon-App zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="bd2af-p106">Take note of the following values in your Azure application registration. You need these values to configure the OAuth flow in your service or daemon app:</span></span>
  - <span data-ttu-id="bd2af-133">App-ID (eindeutig für Ihre Anwendung)</span><span class="sxs-lookup"><span data-stu-id="bd2af-133">Application ID (unique to your application)</span></span>
  - <span data-ttu-id="bd2af-134">App-Schlüssel oder Secret (eindeutig für Ihre App)</span><span class="sxs-lookup"><span data-stu-id="bd2af-134">App key, or secret (unique to your application)</span></span>
  - <span data-ttu-id="bd2af-135">OAuth 2.0-Tokenendpunkt Ihrer App</span><span class="sxs-lookup"><span data-stu-id="bd2af-135">Your app's OAuth 2.0 token endpoint</span></span>
    - <span data-ttu-id="bd2af-p107">Klicken Sie für diesen Wert auf **Endpunkte anzeigen** am unteren Rand des Azure-Verwaltungsportals auf der App-Seite. Der Endpunkt sieht wie `https://login.microsoftonline.com/{tenantId}/oauth2/token` aus.</span><span class="sxs-lookup"><span data-stu-id="bd2af-p107">Find this value by clicking **View Endpoints** at the bottom of the Azure Management Portal in your app's page. The endpoint will look like `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="bd2af-138">Abrufen eines Zugriffstokens</span><span class="sxs-lookup"><span data-stu-id="bd2af-138">Get an access token</span></span>
<span data-ttu-id="bd2af-139">Bevor Sie Aufrufe an den Endpunkt erstellen, müssen Sie ein Zugriffstoken abrufen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-139">Before creating calls to the endpoint, you'll need to get an access token.</span></span>

<span data-ttu-id="bd2af-140">Sie verwenden das Zugriffstoken, um auf die geschützte Ressource zuzugreifen, bei der es sich um Erkennungen in Microsoft Defender für Endpunkt handelt.</span><span class="sxs-lookup"><span data-stu-id="bd2af-140">You'll use the access token to access the protected resource, which is detections in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="bd2af-141">Um ein Zugriffstoken abzurufen, müssen Sie eine POST-Anforderung an den Token ausgebenden Endpunkt ausführen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-141">To get an access token, you'll need to do a POST request to the token issuing endpoint.</span></span> <span data-ttu-id="bd2af-142">Hier ist eine Beispielanforderung:</span><span class="sxs-lookup"><span data-stu-id="bd2af-142">Here is a sample request:</span></span>

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
<span data-ttu-id="bd2af-143">Als Antwort werden ein Zugriffstoken und Ablauf Access-Token und Gültigkeitsinformationen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bd2af-143">The response will include an access token and expiry information.</span></span>

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
<span data-ttu-id="bd2af-144">Sie können nun den Wert im *feld access_token* in einer Anforderung an die Defender für Endpunkt-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd2af-144">You can now use the value in the *access_token* field in a request to the Defender for Endpoint API.</span></span>

## <a name="request"></a><span data-ttu-id="bd2af-145">Anforderung</span><span class="sxs-lookup"><span data-stu-id="bd2af-145">Request</span></span>
<span data-ttu-id="bd2af-146">Mit einem Zugriffstoken kann Ihre App authentifizierte Anforderungen an die Microsoft Defender für Endpunkt-API senden.</span><span class="sxs-lookup"><span data-stu-id="bd2af-146">With an access token, your app can make authenticated requests to the Microsoft Defender for Endpoint API.</span></span> <span data-ttu-id="bd2af-147">Ihre App muss das Zugriffstoken an den Autorisierungs-Header jeder Anforderung anfügen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-147">Your app must append the access token to the Authorization header of each request.</span></span>

### <a name="request-syntax"></a><span data-ttu-id="bd2af-148">Anforderungssyntax</span><span class="sxs-lookup"><span data-stu-id="bd2af-148">Request syntax</span></span>
<span data-ttu-id="bd2af-149">Methode</span><span class="sxs-lookup"><span data-stu-id="bd2af-149">Method</span></span> | <span data-ttu-id="bd2af-150">Anforderungs-URI</span><span class="sxs-lookup"><span data-stu-id="bd2af-150">Request URI</span></span>
:---|:---|
<span data-ttu-id="bd2af-151">GET</span><span class="sxs-lookup"><span data-stu-id="bd2af-151">GET</span></span>| <span data-ttu-id="bd2af-152">Verwenden Sie den für Ihre Region geltenden URI.</span><span class="sxs-lookup"><span data-stu-id="bd2af-152">Use the URI applicable for your region.</span></span> <br><br> <span data-ttu-id="bd2af-153">**Für die EU:**`https://wdatp-alertexporter-eu.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="bd2af-153">**For EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span></span> </br> <span data-ttu-id="bd2af-154">**Für die USA:**`https://wdatp-alertexporter-us.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="bd2af-154">**For US**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span></span> <br> <span data-ttu-id="bd2af-155">**Für Großbritannien:**`https://wdatp-alertexporter-uk.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="bd2af-155">**For UK**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span></span> 

### <a name="request-header"></a><span data-ttu-id="bd2af-156">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="bd2af-156">Request header</span></span>
<span data-ttu-id="bd2af-157">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="bd2af-157">Header</span></span> | <span data-ttu-id="bd2af-158">Typ</span><span class="sxs-lookup"><span data-stu-id="bd2af-158">Type</span></span> | <span data-ttu-id="bd2af-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd2af-159">Description</span></span>|
:--|:--|:--
<span data-ttu-id="bd2af-160">Authorization</span><span class="sxs-lookup"><span data-stu-id="bd2af-160">Authorization</span></span> | <span data-ttu-id="bd2af-161">string</span><span class="sxs-lookup"><span data-stu-id="bd2af-161">string</span></span> | <span data-ttu-id="bd2af-162">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bd2af-162">Required.</span></span> <span data-ttu-id="bd2af-163">Das Azure AD-Zugriffstoken im Formular **Bearertoken.** &lt;  &gt;</span><span class="sxs-lookup"><span data-stu-id="bd2af-163">The Azure AD access token in the form **Bearer** &lt;*token*&gt;.</span></span> |

### <a name="request-parameters"></a><span data-ttu-id="bd2af-164">Anforderungsparameter</span><span class="sxs-lookup"><span data-stu-id="bd2af-164">Request parameters</span></span>

<span data-ttu-id="bd2af-165">Verwenden Sie optionale Abfrageparameter, um die in einer Antwort zurückgegebene Datenmenge anzugeben und zu steuern.</span><span class="sxs-lookup"><span data-stu-id="bd2af-165">Use optional query parameters to specify and control the amount of data returned in a response.</span></span> <span data-ttu-id="bd2af-166">Wenn Sie diese Methode ohne Parameter aufrufen, enthält die Antwort alle Warnungen in Ihrer Organisation in den letzten 2 Stunden.</span><span class="sxs-lookup"><span data-stu-id="bd2af-166">If you call this method without parameters, the response contains all the alerts in your organization in the last 2 hours.</span></span>

<span data-ttu-id="bd2af-167">Name</span><span class="sxs-lookup"><span data-stu-id="bd2af-167">Name</span></span> | <span data-ttu-id="bd2af-168">Wert</span><span class="sxs-lookup"><span data-stu-id="bd2af-168">Value</span></span>| <span data-ttu-id="bd2af-169">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd2af-169">Description</span></span>
:---|:---|:---
<span data-ttu-id="bd2af-170">sinceTimeUtc</span><span class="sxs-lookup"><span data-stu-id="bd2af-170">sinceTimeUtc</span></span> | <span data-ttu-id="bd2af-171">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd2af-171">DateTime</span></span> | <span data-ttu-id="bd2af-172">Definiert die unteren zeitgebundenen Warnungen, aus denen basierend auf dem Feld abgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="bd2af-172">Defines the lower time bound alerts are retrieved from, based on field:</span></span> <br> `LastProcessedTimeUtc` <br> <span data-ttu-id="bd2af-173">Der Zeitraum ist: von sinceTimeUtc-Zeit bis zur aktuellen Zeit.</span><span class="sxs-lookup"><span data-stu-id="bd2af-173">The time range will be: from sinceTimeUtc time to current time.</span></span> <br><br> <span data-ttu-id="bd2af-174">**HINWEIS:** Wenn nicht angegeben, werden alle Warnungen abgerufen, die in den letzten zwei Stunden generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="bd2af-174">**NOTE**: When not specified, all alerts generated in the last two hours are retrieved.</span></span>
<span data-ttu-id="bd2af-175">untilTimeUtc</span><span class="sxs-lookup"><span data-stu-id="bd2af-175">untilTimeUtc</span></span> | <span data-ttu-id="bd2af-176">DateTime</span><span class="sxs-lookup"><span data-stu-id="bd2af-176">DateTime</span></span> | <span data-ttu-id="bd2af-177">Definiert, dass warnungen mit oberen Zeitgrenzen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bd2af-177">Defines the upper time bound alerts are retrieved.</span></span> <br> <span data-ttu-id="bd2af-178">Der Zeitraum ist: von `sinceTimeUtc` Zeit zu `untilTimeUtc` Zeit.</span><span class="sxs-lookup"><span data-stu-id="bd2af-178">The time range will be: from `sinceTimeUtc` time to `untilTimeUtc` time.</span></span> <br><br> <span data-ttu-id="bd2af-179">**HINWEIS:** Wenn nicht angegeben, ist der Standardwert die aktuelle Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="bd2af-179">**NOTE**: When not specified, the default value will be the current time.</span></span>
<span data-ttu-id="bd2af-180">Vor</span><span class="sxs-lookup"><span data-stu-id="bd2af-180">ago</span></span> | <span data-ttu-id="bd2af-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="bd2af-181">string</span></span> | <span data-ttu-id="bd2af-182">Ruft Warnungen im folgenden Zeitraum ab: von `(current_time - ago)` Zeit zu `current_time` Zeit.</span><span class="sxs-lookup"><span data-stu-id="bd2af-182">Pulls alerts in the following time range: from `(current_time - ago)` time to `current_time` time.</span></span> <br><br> <span data-ttu-id="bd2af-183">Der Wert sollte gemäß **dem ISO 8601-Dauerformat** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="bd2af-183">Value should be set according to **ISO 8601** duration format</span></span> <br> <span data-ttu-id="bd2af-184">Beispiel: `ago=PT10M` Ruft Warnungen ab, die in den letzten 10 Minuten empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="bd2af-184">Example: `ago=PT10M` will pull alerts received in the last 10 minutes.</span></span>
<span data-ttu-id="bd2af-185">Begrenzung</span><span class="sxs-lookup"><span data-stu-id="bd2af-185">limit</span></span> | <span data-ttu-id="bd2af-186">int</span><span class="sxs-lookup"><span data-stu-id="bd2af-186">int</span></span> | <span data-ttu-id="bd2af-187">Definiert die Anzahl der abzurufenden Warnungen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-187">Defines the number of alerts to be retrieved.</span></span> <span data-ttu-id="bd2af-188">Die neuesten Warnungen werden basierend auf der definierten Anzahl abgerufen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-188">Most recent alerts will be retrieved based on the number defined.</span></span><br><br> <span data-ttu-id="bd2af-189">**HINWEIS:** Wenn nicht angegeben, werden alle im Zeitraum verfügbaren Warnungen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-189">**NOTE**: When not specified, all alerts available in the time range will be retrieved.</span></span>
<span data-ttu-id="bd2af-190">Computergruppen</span><span class="sxs-lookup"><span data-stu-id="bd2af-190">machinegroups</span></span> | <span data-ttu-id="bd2af-191">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="bd2af-191">string</span></span> | <span data-ttu-id="bd2af-192">Gibt Gerätegruppen an, aus denen Warnungen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-192">Specifies device groups to pull alerts from.</span></span> <br><br> <span data-ttu-id="bd2af-193">**HINWEIS:** Wenn nicht angegeben, werden Warnungen von allen Gerätegruppen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-193">**NOTE**: When not specified, alerts from all device groups will be retrieved.</span></span> <br><br> <span data-ttu-id="bd2af-194">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bd2af-194">Example:</span></span> <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
<span data-ttu-id="bd2af-195">DeviceCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="bd2af-195">DeviceCreatedMachineTags</span></span> | <span data-ttu-id="bd2af-196">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="bd2af-196">string</span></span> | <span data-ttu-id="bd2af-197">Einzelnes Gerätetag aus der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="bd2af-197">Single device tag from the registry.</span></span>
<span data-ttu-id="bd2af-198">CloudCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="bd2af-198">CloudCreatedMachineTags</span></span> | <span data-ttu-id="bd2af-199">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="bd2af-199">string</span></span> | <span data-ttu-id="bd2af-200">Gerätetags, die in Microsoft Defender Security Center erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="bd2af-200">Device tags that were created in Microsoft Defender Security Center.</span></span>

### <a name="request-example"></a><span data-ttu-id="bd2af-201">Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="bd2af-201">Request example</span></span>
<span data-ttu-id="bd2af-202">Im folgenden Beispiel wird veranschaulicht, wie Sie alle Erkennungen in Ihrer Organisation abrufen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-202">The following example demonstrates how to retrieve all the detections in your organization.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

<span data-ttu-id="bd2af-203">Das folgende Beispiel zeigt eine Anforderung zum Abrufen der letzten 20 Erkennungen seit 2016-09-12 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="bd2af-203">The following example demonstrates a request to get the last 20 detections since 2016-09-12 00:00:00.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a><span data-ttu-id="bd2af-204">Antwort</span><span class="sxs-lookup"><span data-stu-id="bd2af-204">Response</span></span>
<span data-ttu-id="bd2af-205">Der Rückgabewert ist ein Array von Warnungsobjekten im JSON-Format.</span><span class="sxs-lookup"><span data-stu-id="bd2af-205">The return value is an array of alert objects in JSON format.</span></span>

<span data-ttu-id="bd2af-206">Hier ist ein Beispiel für einen Rückgabewert:</span><span class="sxs-lookup"><span data-stu-id="bd2af-206">Here is an example return value:</span></span>

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a><span data-ttu-id="bd2af-207">Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="bd2af-207">Code examples</span></span>
### <a name="get-access-token"></a><span data-ttu-id="bd2af-208">Zugriffstoken abrufen</span><span class="sxs-lookup"><span data-stu-id="bd2af-208">Get access token</span></span>
<span data-ttu-id="bd2af-209">Die folgenden Codebeispiele veranschaulichen, wie Sie ein Zugriffstoken zum Aufrufen der Microsoft Defender für Endpunkt-SIEM-API abrufen.</span><span class="sxs-lookup"><span data-stu-id="bd2af-209">The following code examples demonstrate how to obtain an access token for calling the Microsoft Defender for Endpoint SIEM API.</span></span>

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a><span data-ttu-id="bd2af-210">Verwenden des Tokens zum Herstellen einer Verbindung mit dem Erkennungsendpunkt</span><span class="sxs-lookup"><span data-stu-id="bd2af-210">Use token to connect to the detections endpoint</span></span>
<span data-ttu-id="bd2af-211">Die folgenden Codebeispiele veranschaulichen, wie Sie ein Zugriffstoken zum Aufrufen der Defender für Endpunkt-SIEM-API zum Abrufen von Warnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd2af-211">The following code examples demonstrate how to use an access token for calling the Defender for Endpoint SIEM API to get alerts.</span></span>

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a><span data-ttu-id="bd2af-212">Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="bd2af-212">Error codes</span></span>
<span data-ttu-id="bd2af-213">Die Rest-API von Microsoft Defender für Endpunkt gibt die folgenden Fehlercodes zurück, die durch eine ungültige Anforderung verursacht wurden.</span><span class="sxs-lookup"><span data-stu-id="bd2af-213">The Microsoft Defender for Endpoint REST API returns the following error codes caused by an invalid request.</span></span>

<span data-ttu-id="bd2af-214">HTTP-Fehlercode</span><span class="sxs-lookup"><span data-stu-id="bd2af-214">HTTP error code</span></span> | <span data-ttu-id="bd2af-215">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd2af-215">Description</span></span>
:---|:---
<span data-ttu-id="bd2af-216">401</span><span class="sxs-lookup"><span data-stu-id="bd2af-216">401</span></span> | <span data-ttu-id="bd2af-217">Fehlerhafte Anforderung oder ungültiges Token.</span><span class="sxs-lookup"><span data-stu-id="bd2af-217">Malformed request or invalid token.</span></span>
<span data-ttu-id="bd2af-218">403</span><span class="sxs-lookup"><span data-stu-id="bd2af-218">403</span></span> | <span data-ttu-id="bd2af-219">Nicht autorisierte Ausnahme : Eine der Domänen wird nicht vom Mandantenadministrator verwaltet, oder der Mandantenstatus wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="bd2af-219">Unauthorized exception - any of the domains is not managed by the tenant administrator or tenant state is deleted.</span></span>
<span data-ttu-id="bd2af-220">500</span><span class="sxs-lookup"><span data-stu-id="bd2af-220">500</span></span> | <span data-ttu-id="bd2af-221">Fehler im Dienst.</span><span class="sxs-lookup"><span data-stu-id="bd2af-221">Error in the service.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bd2af-222">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="bd2af-222">Related topics</span></span>
- [<span data-ttu-id="bd2af-223">Aktivieren der SIEM-Integration in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bd2af-223">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="bd2af-224">Konfigurieren von ArcSight zum Abrufen von Microsoft Defender für Endpunkterkennungen</span><span class="sxs-lookup"><span data-stu-id="bd2af-224">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="bd2af-225">Abrufen von Erkennungen an Ihre SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="bd2af-225">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="bd2af-226">Microsoft Defender für Endpunkterkennungsfelder</span><span class="sxs-lookup"><span data-stu-id="bd2af-226">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="bd2af-227">Behandeln von Problemen mit der Integration von SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="bd2af-227">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
