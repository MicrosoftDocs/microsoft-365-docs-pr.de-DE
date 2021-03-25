---
title: Abrufen von Microsoft Defender for Endpoint-Erkennungen mithilfe der REST-API
description: Erfahren Sie, wie Sie einen Microsoft Defender for Endpoint-API-Endpunkt aufrufen, um Erkennungen im JSON-Format mithilfe der SIEM REST-API zu ziehen.
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
ms.openlocfilehash: a7d13da6abfb2cd6c829b6fd04fdf94de8cd20b8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186869"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a><span data-ttu-id="32e45-104">Abrufen von Microsoft Defender for Endpoint-Erkennungen mithilfe der SIEM REST-API</span><span class="sxs-lookup"><span data-stu-id="32e45-104">Pull Microsoft Defender for Endpoint detections using SIEM REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="32e45-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="32e45-105">**Applies to:**</span></span>
- [<span data-ttu-id="32e45-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="32e45-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="32e45-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="32e45-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="32e45-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="32e45-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="32e45-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="32e45-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- <span data-ttu-id="32e45-110">[Microsoft Defender for Endpoint Alert](alerts.md) besteht aus einer oder mehreren Erkennungen.</span><span class="sxs-lookup"><span data-stu-id="32e45-110">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="32e45-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) besteht aus dem verdächtigen Ereignis, das auf dem Gerät aufgetreten ist, und den zugehörigen Warnungsdetails.</span><span class="sxs-lookup"><span data-stu-id="32e45-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="32e45-112">-Die Microsoft Defender for Endpoint Alert-API ist die neueste API für den Warnungsverbrauch und enthält eine detaillierte Liste verwandter Nachweise für jede Warnung.</span><span class="sxs-lookup"><span data-stu-id="32e45-112">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="32e45-113">Weitere Informationen finden Sie unter [Warnungsmethoden und -eigenschaften und](alerts.md) [Warnungen auflisten.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="32e45-113">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="32e45-114">Microsoft Defender for Endpoint unterstützt das OAuth 2.0-Protokoll zum Abrufen von Erkennungen aus der API.</span><span class="sxs-lookup"><span data-stu-id="32e45-114">Microsoft Defender for Endpoint supports the OAuth 2.0 protocol to pull detections from the API.</span></span>

<span data-ttu-id="32e45-115">Im Allgemeinen unterstützt das OAuth 2.0-Protokoll vier Arten von Flüssen:</span><span class="sxs-lookup"><span data-stu-id="32e45-115">In general, the OAuth 2.0 protocol supports four types of flows:</span></span>
- <span data-ttu-id="32e45-116">Autorisierungszuteilungsfluss</span><span class="sxs-lookup"><span data-stu-id="32e45-116">Authorization grant flow</span></span>
- <span data-ttu-id="32e45-117">Impliziter Fluss</span><span class="sxs-lookup"><span data-stu-id="32e45-117">Implicit flow</span></span>
- <span data-ttu-id="32e45-118">Ablauf von Clientanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="32e45-118">Client credentials flow</span></span>
- <span data-ttu-id="32e45-119">Fluss des Ressourcenbesitzers</span><span class="sxs-lookup"><span data-stu-id="32e45-119">Resource owner flow</span></span>

<span data-ttu-id="32e45-120">Weitere Informationen zu den OAuth-Spezifikationen finden Sie auf der [OAuth-Website](http://www.oauth.net).</span><span class="sxs-lookup"><span data-stu-id="32e45-120">For more information about the OAuth specifications, see the [OAuth Website](http://www.oauth.net).</span></span>

<span data-ttu-id="32e45-121">Microsoft Defender for  Endpoint unterstützt den Autorisierungserteilungsfluss und den Clientanmeldeinformationenfluss, um Zugriff auf Pullerkennungen zu erhalten, mit Azure Active Directory (AAD) als Autorisierungsserver. </span><span class="sxs-lookup"><span data-stu-id="32e45-121">Microsoft Defender for Endpoint supports the _Authorization grant flow_ and _Client credential flow_ to obtain access to pull detections, with Azure Active Directory (AAD) as the authorization server.</span></span>

<span data-ttu-id="32e45-122">Der _Autorisierungszuteilungsfluss_ verwendet Benutzeranmeldeinformationen, um einen Autorisierungscode abzurufen, der dann zum Abrufen eines Zugriffstokens verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="32e45-122">The _Authorization grant flow_ uses user credentials to get an authorization code, which is then used to obtain an access token.</span></span>

<span data-ttu-id="32e45-123">Der _Clientanmeldeinformationenfluss_ verwendet Clientanmeldeinformationen, um sich bei der Microsoft Defender for Endpoint-Endpunkt-URL zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="32e45-123">The _Client credential flow_ uses client credentials to authenticate against the Microsoft Defender for Endpoint endpoint URL.</span></span> <span data-ttu-id="32e45-124">Dieser Fluss eignet sich für Szenarien, in denen ein OAuth-Client Anforderungen an eine API erstellt, für die keine Benutzeranmeldeinformationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="32e45-124">This flow is suitable for scenarios when an OAuth client creates requests to an API that doesn't require user credentials.</span></span>

<span data-ttu-id="32e45-125">Verwenden Sie die folgende Methode in der Microsoft Defender for Endpoint-API, um Erkennungen im JSON-Format zu ziehen.</span><span class="sxs-lookup"><span data-stu-id="32e45-125">Use the following method in the Microsoft Defender for Endpoint API to pull detections in JSON format.</span></span>

>[!NOTE]
><span data-ttu-id="32e45-126">Microsoft Defender Security Center führt ähnliche Warnungserkennungen in einer einzigen Warnung zusammen.</span><span class="sxs-lookup"><span data-stu-id="32e45-126">Microsoft Defender Security Center merges similar alert detections into a single alert.</span></span> <span data-ttu-id="32e45-127">Diese API erstellt Warnungserkennungen in ihrer rohen Form basierend auf den von Ihnen festgelegten Abfrageparametern, sodass Sie Ihre eigene Gruppierung und Filterung anwenden können.</span><span class="sxs-lookup"><span data-stu-id="32e45-127">This API pulls alert detections in its raw form based on the query parameters you set, enabling you to apply your own grouping and filtering.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="32e45-128">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="32e45-128">Before you begin</span></span>
- <span data-ttu-id="32e45-129">Bevor Sie den Microsoft Defender for Endpoint-Endpunkt zum Ziehen von Erkennungen aufrufen, müssen Sie die SIEM-Integrationsanwendung in Azure Active Directory (AAD) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="32e45-129">Before calling the Microsoft Defender for Endpoint endpoint to pull detections, you'll need to enable the SIEM integration application in Azure Active Directory (AAD).</span></span> <span data-ttu-id="32e45-130">Weitere Informationen finden Sie unter [Aktivieren der SIEM-Integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span><span class="sxs-lookup"><span data-stu-id="32e45-130">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="32e45-p106">Notieren Sie sich die folgenden Werte bei der Registrierung Ihrer Azure-App. Sie benötigen diese Werte, um den OAuth-Fluss in Ihrem Dienst oder Ihrer Dämon-App zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="32e45-p106">Take note of the following values in your Azure application registration. You need these values to configure the OAuth flow in your service or daemon app:</span></span>
  - <span data-ttu-id="32e45-133">App-ID (eindeutig für Ihre Anwendung)</span><span class="sxs-lookup"><span data-stu-id="32e45-133">Application ID (unique to your application)</span></span>
  - <span data-ttu-id="32e45-134">App-Schlüssel oder Secret (eindeutig für Ihre App)</span><span class="sxs-lookup"><span data-stu-id="32e45-134">App key, or secret (unique to your application)</span></span>
  - <span data-ttu-id="32e45-135">OAuth 2.0-Tokenendpunkt Ihrer App</span><span class="sxs-lookup"><span data-stu-id="32e45-135">Your app's OAuth 2.0 token endpoint</span></span>
    - <span data-ttu-id="32e45-p107">Klicken Sie für diesen Wert auf **Endpunkte anzeigen** am unteren Rand des Azure-Verwaltungsportals auf der App-Seite. Der Endpunkt sieht wie `https://login.microsoftonline.com/{tenantId}/oauth2/token` aus.</span><span class="sxs-lookup"><span data-stu-id="32e45-p107">Find this value by clicking **View Endpoints** at the bottom of the Azure Management Portal in your app's page. The endpoint will look like `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="32e45-138">Abrufen eines Zugriffstokens</span><span class="sxs-lookup"><span data-stu-id="32e45-138">Get an access token</span></span>
<span data-ttu-id="32e45-139">Vor dem Erstellen von Aufrufen an den Endpunkt müssen Sie ein Zugriffstoken erhalten.</span><span class="sxs-lookup"><span data-stu-id="32e45-139">Before creating calls to the endpoint, you'll need to get an access token.</span></span>

<span data-ttu-id="32e45-140">Sie verwenden das Zugriffstoken für den Zugriff auf die geschützte Ressource, d. h. Erkennungen in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="32e45-140">You'll use the access token to access the protected resource, which is detections in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="32e45-141">Um ein Zugriffstoken abzurufen, müssen Sie eine POST-Anforderung an den Tokenausstellenden Endpunkt senden.</span><span class="sxs-lookup"><span data-stu-id="32e45-141">To get an access token, you'll need to do a POST request to the token issuing endpoint.</span></span> <span data-ttu-id="32e45-142">Hier ist eine Beispielanforderung:</span><span class="sxs-lookup"><span data-stu-id="32e45-142">Here is a sample request:</span></span>

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
<span data-ttu-id="32e45-143">Als Antwort werden ein Zugriffstoken und Ablauf Access-Token und Gültigkeitsinformationen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="32e45-143">The response will include an access token and expiry information.</span></span>

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
<span data-ttu-id="32e45-144">Sie können jetzt den Wert im Feld *access_token* in einer Anforderung an die Defender for Endpoint-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="32e45-144">You can now use the value in the *access_token* field in a request to the Defender for Endpoint API.</span></span>

## <a name="request"></a><span data-ttu-id="32e45-145">Anforderung</span><span class="sxs-lookup"><span data-stu-id="32e45-145">Request</span></span>
<span data-ttu-id="32e45-146">Mit einem Zugriffstoken kann Ihre App authentifizierte Anforderungen an die Microsoft Defender for Endpoint-API senden.</span><span class="sxs-lookup"><span data-stu-id="32e45-146">With an access token, your app can make authenticated requests to the Microsoft Defender for Endpoint API.</span></span> <span data-ttu-id="32e45-147">Ihre App muss das Zugriffstoken an den Autorisierungs-Header jeder Anforderung anfügen.</span><span class="sxs-lookup"><span data-stu-id="32e45-147">Your app must append the access token to the Authorization header of each request.</span></span>

### <a name="request-syntax"></a><span data-ttu-id="32e45-148">Anforderungssyntax</span><span class="sxs-lookup"><span data-stu-id="32e45-148">Request syntax</span></span>
<span data-ttu-id="32e45-149">Methode</span><span class="sxs-lookup"><span data-stu-id="32e45-149">Method</span></span> | <span data-ttu-id="32e45-150">Anforderungs-URI</span><span class="sxs-lookup"><span data-stu-id="32e45-150">Request URI</span></span>
:---|:---|
<span data-ttu-id="32e45-151">GET</span><span class="sxs-lookup"><span data-stu-id="32e45-151">GET</span></span>| <span data-ttu-id="32e45-152">Verwenden Sie den URI, der für Ihre Region gilt.</span><span class="sxs-lookup"><span data-stu-id="32e45-152">Use the URI applicable for your region.</span></span> <br><br> <span data-ttu-id="32e45-153">**Für EU:**`https://wdatp-alertexporter-eu.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="32e45-153">**For EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span></span> </br> <span data-ttu-id="32e45-154">**Für USA**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="32e45-154">**For US**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span></span> <br> <span data-ttu-id="32e45-155">**Für Großbritannien**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="32e45-155">**For UK**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span></span> 

### <a name="request-header"></a><span data-ttu-id="32e45-156">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="32e45-156">Request header</span></span>
<span data-ttu-id="32e45-157">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="32e45-157">Header</span></span> | <span data-ttu-id="32e45-158">Typ</span><span class="sxs-lookup"><span data-stu-id="32e45-158">Type</span></span> | <span data-ttu-id="32e45-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32e45-159">Description</span></span>|
:--|:--|:--
<span data-ttu-id="32e45-160">Authorization</span><span class="sxs-lookup"><span data-stu-id="32e45-160">Authorization</span></span> | <span data-ttu-id="32e45-161">string</span><span class="sxs-lookup"><span data-stu-id="32e45-161">string</span></span> | <span data-ttu-id="32e45-162">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="32e45-162">Required.</span></span> <span data-ttu-id="32e45-163">Das Azure AD-Zugriffstoken im Format **Bearer-Token** &lt;  &gt; .</span><span class="sxs-lookup"><span data-stu-id="32e45-163">The Azure AD access token in the form **Bearer** &lt;*token*&gt;.</span></span> |

### <a name="request-parameters"></a><span data-ttu-id="32e45-164">Anforderungsparameter</span><span class="sxs-lookup"><span data-stu-id="32e45-164">Request parameters</span></span>

<span data-ttu-id="32e45-165">Verwenden Sie optionale Abfrageparameter, um die In einer Antwort zurückgegebene Datenmenge anzugeben und zu steuern.</span><span class="sxs-lookup"><span data-stu-id="32e45-165">Use optional query parameters to specify and control the amount of data returned in a response.</span></span> <span data-ttu-id="32e45-166">Wenn Sie diese Methode ohne Parameter aufrufen, enthält die Antwort alle Warnungen in Ihrer Organisation in den letzten 2 Stunden.</span><span class="sxs-lookup"><span data-stu-id="32e45-166">If you call this method without parameters, the response contains all the alerts in your organization in the last 2 hours.</span></span>

<span data-ttu-id="32e45-167">Name</span><span class="sxs-lookup"><span data-stu-id="32e45-167">Name</span></span> | <span data-ttu-id="32e45-168">Wert</span><span class="sxs-lookup"><span data-stu-id="32e45-168">Value</span></span>| <span data-ttu-id="32e45-169">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32e45-169">Description</span></span>
:---|:---|:---
<span data-ttu-id="32e45-170">sinceTimeUtc</span><span class="sxs-lookup"><span data-stu-id="32e45-170">sinceTimeUtc</span></span> | <span data-ttu-id="32e45-171">DateTime</span><span class="sxs-lookup"><span data-stu-id="32e45-171">DateTime</span></span> | <span data-ttu-id="32e45-172">Definiert die Warnungen mit niedrigerer Zeit, die basierend auf dem Feld abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="32e45-172">Defines the lower time bound alerts are retrieved from, based on field:</span></span> <br> `LastProcessedTimeUtc` <br> <span data-ttu-id="32e45-173">Der Zeitbereich ist: von sinceTimeUtc-Zeit bis zur aktuellen Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="32e45-173">The time range will be: from sinceTimeUtc time to current time.</span></span> <br><br> <span data-ttu-id="32e45-174">**HINWEIS**: Wenn nicht angegeben, werden alle Warnungen abgerufen, die in den letzten zwei Stunden generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="32e45-174">**NOTE**: When not specified, all alerts generated in the last two hours are retrieved.</span></span>
<span data-ttu-id="32e45-175">untilTimeUtc</span><span class="sxs-lookup"><span data-stu-id="32e45-175">untilTimeUtc</span></span> | <span data-ttu-id="32e45-176">DateTime</span><span class="sxs-lookup"><span data-stu-id="32e45-176">DateTime</span></span> | <span data-ttu-id="32e45-177">Definiert die Warnungen für die obere Zeit, die abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="32e45-177">Defines the upper time bound alerts are retrieved.</span></span> <br> <span data-ttu-id="32e45-178">Der Zeitraum ist: von `sinceTimeUtc` Zeit zu `untilTimeUtc` Zeit.</span><span class="sxs-lookup"><span data-stu-id="32e45-178">The time range will be: from `sinceTimeUtc` time to `untilTimeUtc` time.</span></span> <br><br> <span data-ttu-id="32e45-179">**HINWEIS**: Wenn dieser Wert nicht angegeben wird, ist der Standardwert die aktuelle Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="32e45-179">**NOTE**: When not specified, the default value will be the current time.</span></span>
<span data-ttu-id="32e45-180">ago</span><span class="sxs-lookup"><span data-stu-id="32e45-180">ago</span></span> | <span data-ttu-id="32e45-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="32e45-181">string</span></span> | <span data-ttu-id="32e45-182">Zieht Warnungen im folgenden Zeitraum: von `(current_time - ago)` Zeit zu `current_time` Zeit.</span><span class="sxs-lookup"><span data-stu-id="32e45-182">Pulls alerts in the following time range: from `(current_time - ago)` time to `current_time` time.</span></span> <br><br> <span data-ttu-id="32e45-183">Wert sollte gemäß **ISO 8601-Dauerformat** festgelegt werden</span><span class="sxs-lookup"><span data-stu-id="32e45-183">Value should be set according to **ISO 8601** duration format</span></span> <br> <span data-ttu-id="32e45-184">Beispiel: `ago=PT10M` Benachrichtigungen, die in den letzten 10 Minuten empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="32e45-184">Example: `ago=PT10M` will pull alerts received in the last 10 minutes.</span></span>
<span data-ttu-id="32e45-185">Begrenzung</span><span class="sxs-lookup"><span data-stu-id="32e45-185">limit</span></span> | <span data-ttu-id="32e45-186">int</span><span class="sxs-lookup"><span data-stu-id="32e45-186">int</span></span> | <span data-ttu-id="32e45-187">Definiert die Anzahl der abzurufenden Warnungen.</span><span class="sxs-lookup"><span data-stu-id="32e45-187">Defines the number of alerts to be retrieved.</span></span> <span data-ttu-id="32e45-188">Die neuesten Warnungen werden basierend auf der definierten Anzahl abgerufen.</span><span class="sxs-lookup"><span data-stu-id="32e45-188">Most recent alerts will be retrieved based on the number defined.</span></span><br><br> <span data-ttu-id="32e45-189">**HINWEIS**: Wenn nicht angegeben, werden alle im Zeitraum verfügbaren Warnungen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="32e45-189">**NOTE**: When not specified, all alerts available in the time range will be retrieved.</span></span>
<span data-ttu-id="32e45-190">machinegroups</span><span class="sxs-lookup"><span data-stu-id="32e45-190">machinegroups</span></span> | <span data-ttu-id="32e45-191">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="32e45-191">string</span></span> | <span data-ttu-id="32e45-192">Gibt Gerätegruppen an, aus der Warnungen abziehen sollen.</span><span class="sxs-lookup"><span data-stu-id="32e45-192">Specifies device groups to pull alerts from.</span></span> <br><br> <span data-ttu-id="32e45-193">**HINWEIS:** Wenn nicht angegeben, werden Warnungen von allen Gerätegruppen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="32e45-193">**NOTE**: When not specified, alerts from all device groups will be retrieved.</span></span> <br><br> <span data-ttu-id="32e45-194">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="32e45-194">Example:</span></span> <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/Alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
<span data-ttu-id="32e45-195">DeviceCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="32e45-195">DeviceCreatedMachineTags</span></span> | <span data-ttu-id="32e45-196">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="32e45-196">string</span></span> | <span data-ttu-id="32e45-197">Einzelnes Gerätetag aus der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="32e45-197">Single device tag from the registry.</span></span>
<span data-ttu-id="32e45-198">CloudCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="32e45-198">CloudCreatedMachineTags</span></span> | <span data-ttu-id="32e45-199">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="32e45-199">string</span></span> | <span data-ttu-id="32e45-200">Gerätetags, die im Microsoft Defender Security Center erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="32e45-200">Device tags that were created in Microsoft Defender Security Center.</span></span>

### <a name="request-example"></a><span data-ttu-id="32e45-201">Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="32e45-201">Request example</span></span>
<span data-ttu-id="32e45-202">Im folgenden Beispiel wird veranschaulicht, wie alle Erkennungen in Ihrer Organisation abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="32e45-202">The following example demonstrates how to retrieve all the detections in your organization.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

<span data-ttu-id="32e45-203">Das folgende Beispiel veranschaulicht eine Anforderung zum Anfordern der letzten 20 Erkennungen seit 2016-09-12 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="32e45-203">The following example demonstrates a request to get the last 20 detections since 2016-09-12 00:00:00.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a><span data-ttu-id="32e45-204">Antwort</span><span class="sxs-lookup"><span data-stu-id="32e45-204">Response</span></span>
<span data-ttu-id="32e45-205">Der Rückgabewert ist ein Array von Warnungsobjekten im JSON-Format.</span><span class="sxs-lookup"><span data-stu-id="32e45-205">The return value is an array of alert objects in JSON format.</span></span>

<span data-ttu-id="32e45-206">Im Folgenden finden Sie ein Beispiel für den Rückgabewert:</span><span class="sxs-lookup"><span data-stu-id="32e45-206">Here is an example return value:</span></span>

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

## <a name="code-examples"></a><span data-ttu-id="32e45-207">Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="32e45-207">Code examples</span></span>
### <a name="get-access-token"></a><span data-ttu-id="32e45-208">Zugriffstoken erhalten</span><span class="sxs-lookup"><span data-stu-id="32e45-208">Get access token</span></span>
<span data-ttu-id="32e45-209">In den folgenden Codebeispielen wird gezeigt, wie Sie ein Zugriffstoken zum Aufrufen der Microsoft Defender for Endpoint SIEM-API abrufen.</span><span class="sxs-lookup"><span data-stu-id="32e45-209">The following code examples demonstrate how to obtain an access token for calling the Microsoft Defender for Endpoint SIEM API.</span></span>

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

### <a name="use-token-to-connect-to-the-detections-endpoint"></a><span data-ttu-id="32e45-210">Verwenden von Token zum Herstellen einer Verbindung mit dem Erkennungsendpunkt</span><span class="sxs-lookup"><span data-stu-id="32e45-210">Use token to connect to the detections endpoint</span></span>
<span data-ttu-id="32e45-211">In den folgenden Codebeispielen wird die Verwendung eines Zugriffstokens zum Aufrufen der Defender for Endpoint SIEM-API zum Abrufen von Warnungen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="32e45-211">The following code examples demonstrate how to use an access token for calling the Defender for Endpoint SIEM API to get alerts.</span></span>

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

## <a name="error-codes"></a><span data-ttu-id="32e45-212">Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="32e45-212">Error codes</span></span>
<span data-ttu-id="32e45-213">Die Microsoft Defender for Endpoint REST-API gibt die folgenden Fehlercodes zurück, die durch eine ungültige Anforderung verursacht wurden.</span><span class="sxs-lookup"><span data-stu-id="32e45-213">The Microsoft Defender for Endpoint REST API returns the following error codes caused by an invalid request.</span></span>

<span data-ttu-id="32e45-214">HTTP-Fehlercode</span><span class="sxs-lookup"><span data-stu-id="32e45-214">HTTP error code</span></span> | <span data-ttu-id="32e45-215">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32e45-215">Description</span></span>
:---|:---
<span data-ttu-id="32e45-216">401</span><span class="sxs-lookup"><span data-stu-id="32e45-216">401</span></span> | <span data-ttu-id="32e45-217">Falsch formatierte Anforderung oder ungültiges Token.</span><span class="sxs-lookup"><span data-stu-id="32e45-217">Malformed request or invalid token.</span></span>
<span data-ttu-id="32e45-218">403</span><span class="sxs-lookup"><span data-stu-id="32e45-218">403</span></span> | <span data-ttu-id="32e45-219">Nicht autorisierte Ausnahme: Eine der Domänen wird nicht vom Mandantenadministrator verwaltet, oder der Mandantenstatus wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="32e45-219">Unauthorized exception - any of the domains is not managed by the tenant administrator or tenant state is deleted.</span></span>
<span data-ttu-id="32e45-220">500</span><span class="sxs-lookup"><span data-stu-id="32e45-220">500</span></span> | <span data-ttu-id="32e45-221">Fehler im Dienst.</span><span class="sxs-lookup"><span data-stu-id="32e45-221">Error in the service.</span></span>

## <a name="related-topics"></a><span data-ttu-id="32e45-222">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="32e45-222">Related topics</span></span>
- [<span data-ttu-id="32e45-223">Aktivieren der SIEM-Integration in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="32e45-223">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="32e45-224">Konfigurieren von ArcSight zum Ziehen von Microsoft Defender for Endpoint-Erkennungen</span><span class="sxs-lookup"><span data-stu-id="32e45-224">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="32e45-225">Ziehen von Erkennungen an Ihre SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="32e45-225">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="32e45-226">Microsoft Defender for Endpoint Detection-Felder</span><span class="sxs-lookup"><span data-stu-id="32e45-226">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="32e45-227">Problembehandlung bei der Integration von SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="32e45-227">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
