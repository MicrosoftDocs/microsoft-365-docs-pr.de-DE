---
title: Versionshinweise zur Microsoft Defender for Endpoint-API
description: Versionshinweise für Updates, die an den Microsoft Defender for Endpoint-APIs vorgenommen werden.
keywords: Microsoft Defender for Endpoint API Release Notes, mde, APIs, Microsoft Defender for Endpoint API, updates, notes, release
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
ms.openlocfilehash: 02fd995b04c1644e88b38fd0feebc2c80a3681ac
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933625"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="0e4dc-104">Versionshinweise zur Microsoft Defender for Endpoint-API</span><span class="sxs-lookup"><span data-stu-id="0e4dc-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="0e4dc-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0e4dc-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="0e4dc-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0e4dc-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0e4dc-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0e4dc-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="0e4dc-108">In den folgenden Informationen werden die an den Microsoft Defender for Endpoint-APIs vorgenommenen Updates und deren Datumsangaben aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e4dc-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>


> [!TIP]
> <span data-ttu-id="0e4dc-109">RSS-Feed: Erhalten Sie eine Benachrichtigung, wenn diese Seite aktualisiert wird, indem Sie die folgende URL in Ihren Feedleser kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="0e4dc-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span> 
>```
>https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
>```


### <a name="10022021"></a><span data-ttu-id="0e4dc-110">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="0e4dc-110">10.02.2021</span></span>
<hr>

- <span data-ttu-id="0e4dc-111">Neue API hinzugefügt: [Batchupdatewarnungen](batch-update-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="0e4dc-111">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span> 

<br>

### <a name="25012021"></a><span data-ttu-id="0e4dc-112">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="0e4dc-112">25.01.2021</span></span>
<hr>

- <span data-ttu-id="0e4dc-113">Die Geschwindigkeitseinschränkungen für [die Erweiterte Suche-API](run-advanced-query-api.md) wurden von 15 auf 45 Anforderungen pro Minute aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0e4dc-113">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span> 

<br>

### <a name="21012021"></a><span data-ttu-id="0e4dc-114">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="0e4dc-114">21.01.2021</span></span>
<hr>

- <span data-ttu-id="0e4dc-115">Neue API hinzugefügt: [Suchen von Geräten nach Tag](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="0e4dc-115">Added new API: [Find devices by tag](machine-tags.md).</span></span> 
- <span data-ttu-id="0e4dc-116">Neue API hinzugefügt: [Import Indicators](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="0e4dc-116">Added new API: [Import Indicators](import-ti-indicators.md).</span></span> 

<br>

### <a name="03012021"></a><span data-ttu-id="0e4dc-117">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="0e4dc-117">03.01.2021</span></span>
<hr>

- <span data-ttu-id="0e4dc-118">Aktualisierter Warnungsnachweis: Eigenschaften ***detectionStatus** _, _*_parentProcessFilePath_*_ und _ *_parentProcessFileName_** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0e4dc-118">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="0e4dc-119">Entität [Warnung aktualisiert:](alerts.md) ***eigenschaft detectorId*** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0e4dc-119">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

<br>

### <a name="15122020"></a><span data-ttu-id="0e4dc-120">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="0e4dc-120">15.12.2020</span></span>
<hr>

- <span data-ttu-id="0e4dc-121">Entität [Device aktualisiert:](machine.md) ***IpInterfaces-Liste*** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0e4dc-121">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="0e4dc-122">Weitere [Informationen finden Sie unter Auflisten von Geräten](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="0e4dc-122">See [List devices](get-machines.md).</span></span>

<br>

### <a name="04112020"></a><span data-ttu-id="0e4dc-123">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="0e4dc-123">04.11.2020</span></span>
<hr>

- <span data-ttu-id="0e4dc-124">Neue API hinzugefügt: [Gerätewert festlegen.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="0e4dc-124">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="0e4dc-125">Entität [Device aktualisiert:](machine.md) ***deviceValue-Eigenschaft*** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0e4dc-125">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

<br>

### <a name="01092020"></a><span data-ttu-id="0e4dc-126">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="0e4dc-126">01.09.2020</span></span>
<hr>

- <span data-ttu-id="0e4dc-127">Option hinzugefügt, um die Alert-Entität mit dem zugehörigen Nachweis zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="0e4dc-127">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="0e4dc-128">Weitere [Informationen finden Sie unter List Alerts](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="0e4dc-128">See [List Alerts](get-alerts.md).</span></span>

<br>
<br>