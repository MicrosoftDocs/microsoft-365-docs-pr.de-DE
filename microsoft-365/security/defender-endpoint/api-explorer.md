---
title: API Explorer in Microsoft Defender for Endpoint
ms.reviewer: ''
description: Erstellen und Ausführen von API-Abfragen, Testen und Senden von Anforderungen für alle verfügbaren API mithilfe des API-Explorers
keywords: api, explorer, send, request, get, post,
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b8d0d991e46464bae3b4d21d6218b9b3b2d2b4cb
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930113"
---
# <a name="api-explorer"></a><span data-ttu-id="d074c-104">API-Explorer</span><span class="sxs-lookup"><span data-stu-id="d074c-104">API Explorer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d074c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d074c-105">**Applies to:**</span></span>
- [<span data-ttu-id="d074c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d074c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


<span data-ttu-id="d074c-107">Der Microsoft Defender for Endpoint API Explorer ist ein Tool, mit dem Sie verschiedene Defender for Endpoint-APIs interaktiv erkunden können.</span><span class="sxs-lookup"><span data-stu-id="d074c-107">The Microsoft Defender for Endpoint API Explorer is a tool that helps you explore various Defender for Endpoint APIs interactively.</span></span> 

<span data-ttu-id="d074c-108">Der API-Explorer erleichtert das Erstellen und Ausführen von API-Abfragen, Tests und Senden von Anforderungen für alle verfügbaren Defender for Endpoint-API-Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="d074c-108">The API Explorer makes it easy to construct and do API queries, test, and send requests for any available Defender for Endpoint API endpoint.</span></span> <span data-ttu-id="d074c-109">Verwenden Sie den API-Explorer, um Aktionen zu ergreifen oder Daten zu finden, die möglicherweise noch nicht über die Benutzeroberfläche verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d074c-109">Use the API Explorer to take actions or find data that might not yet be available through the user interface.</span></span>

<span data-ttu-id="d074c-110">Das Tool ist während der App-Entwicklung hilfreich.</span><span class="sxs-lookup"><span data-stu-id="d074c-110">The tool is useful during app development.</span></span> <span data-ttu-id="d074c-111">Es ermöglicht Ihnen, API-Abfragen durchzuführen, die Ihre Benutzerzugriffseinstellungen respektieren, wodurch die Notwendigkeit reduziert wird, Zugriffstoken zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d074c-111">It allows you to perform API queries that respect your user access settings, reducing the need to generate access tokens.</span></span>

<span data-ttu-id="d074c-112">Sie können das Tool auch verwenden, um den Katalog von Beispielabfragen zu erkunden, Ergebniscodebeispiele zu kopieren und Debuginformationen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d074c-112">You can also use the tool to explore the gallery of sample queries, copy result code samples, and generate debug information.</span></span>

<span data-ttu-id="d074c-113">Mit dem API-Explorer können Sie:</span><span class="sxs-lookup"><span data-stu-id="d074c-113">With the API Explorer, you can:</span></span>

- <span data-ttu-id="d074c-114">Ausführen von Anforderungen für jede Methode und Sehen von Antworten in Echtzeit</span><span class="sxs-lookup"><span data-stu-id="d074c-114">Run requests for any method and see responses in real-time</span></span>
- <span data-ttu-id="d074c-115">Durchsuchen Sie schnell die API-Beispiele, und erfahren Sie, welche Parameter sie unterstützen</span><span class="sxs-lookup"><span data-stu-id="d074c-115">Quickly browse through the API samples and learn what parameters they support</span></span>
- <span data-ttu-id="d074c-116">Einfaches Erstellen von #A0 Keine Authentifizierung über die Anmeldung des Verwaltungsportals hinaus</span><span class="sxs-lookup"><span data-stu-id="d074c-116">Make API calls with ease; no need to authenticate beyond the management portal sign in</span></span>

## <a name="access-api-explorer"></a><span data-ttu-id="d074c-117">Access-API-Explorer</span><span class="sxs-lookup"><span data-stu-id="d074c-117">Access API Explorer</span></span>

<span data-ttu-id="d074c-118">Wählen Sie im linken Navigationsmenü **Partner & APIs**  >  **API Explorer aus.**</span><span class="sxs-lookup"><span data-stu-id="d074c-118">From the left navigation menu, select **Partners & APIs** > **API Explorer**.</span></span>

## <a name="supported-apis"></a><span data-ttu-id="d074c-119">Unterstützte APIs</span><span class="sxs-lookup"><span data-stu-id="d074c-119">Supported APIs</span></span>

<span data-ttu-id="d074c-120">DER API-Explorer unterstützt alle APIs, die von Defender for Endpoint angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="d074c-120">API Explorer supports all the APIs offered by Defender for Endpoint.</span></span>
  
<span data-ttu-id="d074c-121">Die Liste der unterstützten APIs ist in der [APIs-Dokumentation verfügbar.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d074c-121">The list of supported APIs is available in the [APIs documentation](apis-intro.md).</span></span> 

## <a name="get-started-with-the-api-explorer"></a><span data-ttu-id="d074c-122">Erste Schritte mit dem API-Explorer</span><span class="sxs-lookup"><span data-stu-id="d074c-122">Get started with the API Explorer</span></span>

1. <span data-ttu-id="d074c-123">Im linken Bereich finden Sie eine Liste der Beispielanforderungen, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d074c-123">In the left pane, there is a list of sample requests that you can use.</span></span> 
2. <span data-ttu-id="d074c-124">Folgen Sie den Links, und klicken Sie **auf Abfrage ausführen.**</span><span class="sxs-lookup"><span data-stu-id="d074c-124">Follow the links and click **Run query**.</span></span> 

<span data-ttu-id="d074c-125">Für einige Beispiele ist möglicherweise die Angabe eines Parameters in der URL erforderlich, z. B. {machine- ID}.</span><span class="sxs-lookup"><span data-stu-id="d074c-125">Some of the samples may require specifying a parameter in the URL, for example, {machine- ID}.</span></span>

## <a name="faq"></a><span data-ttu-id="d074c-126">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="d074c-126">FAQ</span></span>

<span data-ttu-id="d074c-127">**Muss ich über ein API-Token verfügen, um den API-Explorer verwenden zu können?**</span><span class="sxs-lookup"><span data-stu-id="d074c-127">**Do I need to have an API token to use the API Explorer?**</span></span> <br>
<span data-ttu-id="d074c-128">Anmeldeinformationen für den Zugriff auf eine API sind nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d074c-128">Credentials to access an API aren't needed.</span></span> <span data-ttu-id="d074c-129">Der API-Explorer verwendet das Defender for Endpoint-Verwaltungsportaltoken, wenn eine Anforderung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d074c-129">The API Explorer uses the Defender for Endpoint management portal token whenever it makes a request.</span></span>

<span data-ttu-id="d074c-130">Die Anmeldeinformationen für die Benutzerauthentifizierung werden verwendet, um zu überprüfen, ob der API-Explorer autorisiert ist, in Ihrem Auftrag auf Daten zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d074c-130">The logged-in user authentication credential is used to verify that the API Explorer is authorized to access data on your behalf.</span></span>

<span data-ttu-id="d074c-131">Bestimmte API-Anforderungen sind basierend auf Ihren RBAC-Berechtigungen eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="d074c-131">Specific API requests are limited based on your RBAC privileges.</span></span> <span data-ttu-id="d074c-132">Beispielsweise ist eine Anforderung zum "Indikator übermitteln" auf die Rolle des Sicherheitsadministrators beschränkt.</span><span class="sxs-lookup"><span data-stu-id="d074c-132">For example, a request to "Submit indicator" is limited to the security admin role.</span></span> 
