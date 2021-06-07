---
title: Versionshinweise zur Microsoft Defender für Endpunkt-API
description: Versionshinweise für Updates, die an den APIs des Microsoft Defender für Endpunkt-Satzes vorgenommen wurden.
keywords: Versionshinweise zur Microsoft Defender für Endpunkt-API, mde, APIs, Microsoft Defender für Endpunkt-API, Updates, Notizen, Release
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
ms.openlocfilehash: ec7adcc153d4c6bedfb1984951acad7a401cbd55
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788811"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="78144-104">Versionshinweise zur Microsoft Defender für Endpunkt-API</span><span class="sxs-lookup"><span data-stu-id="78144-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="78144-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="78144-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="78144-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="78144-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="78144-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="78144-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="78144-108">Die folgenden Informationen enthalten die Aktualisierungen, die an den Microsoft Defender für Endpunkt-APIs vorgenommen wurden, und das Datum, an dem sie vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="78144-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="78144-109">RSS-Feed: Erhalten Sie Benachrichtigungen, wenn diese Seite aktualisiert wird, indem Sie die folgende URL kopieren und in Ihren Feed-Reader einfügen:</span><span class="sxs-lookup"><span data-stu-id="78144-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a><span data-ttu-id="78144-110">Versionshinweise – neueste bis älteste (dd.mm.yyyyy)</span><span class="sxs-lookup"><span data-stu-id="78144-110">Release notes - newest to oldest (dd.mm.yyyy)</span></span>

### <a name="05252021"></a><span data-ttu-id="78144-111">05.25.2021</span><span class="sxs-lookup"><span data-stu-id="78144-111">05.25.2021</span></span>

- <span data-ttu-id="78144-112">Neue API [Export-Bewertungsmethoden und -Eigenschaften pro Gerät](get-assessment-methods-properties.md)hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="78144-112">Added new API [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span></span>

### <a name="03052021"></a><span data-ttu-id="78144-113">03.05.2021</span><span class="sxs-lookup"><span data-stu-id="78144-113">03.05.2021</span></span>

- <span data-ttu-id="78144-114">Neue API hinzugefügt: [Korrekturaktivitätsmethoden und -eigenschaften.](get-remediation-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="78144-114">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="78144-115">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="78144-115">10.02.2021</span></span>

- <span data-ttu-id="78144-116">Neue API hinzugefügt: [Warnungen bei Batchaktualisierungen.](batch-update-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="78144-116">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="78144-117">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="78144-117">25.01.2021</span></span>

- <span data-ttu-id="78144-118">Aktualisierte Rateneinschränkungen für die API für [die erweiterte Suche](run-advanced-query-api.md) von 15 bis 45 Anforderungen pro Minute.</span><span class="sxs-lookup"><span data-stu-id="78144-118">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="78144-119">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="78144-119">21.01.2021</span></span>

- <span data-ttu-id="78144-120">Neue API hinzugefügt: [Geräte nach Tag suchen.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="78144-120">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="78144-121">Neue API hinzugefügt: [Import indicators](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="78144-121">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="78144-122">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="78144-122">03.01.2021</span></span>

- <span data-ttu-id="78144-123">Aktualisierter Warnungsnachweis: eigenschaften ***detectionStatus** _, _*_parentProcessFilePath_*_ und _ *_parentProcessFileName_** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="78144-123">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="78144-124">Aktualisierte [Warnungsentität:](alerts.md) ***die eigenschaft "detectorId"*** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="78144-124">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="78144-125">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="78144-125">15.12.2020</span></span>

- <span data-ttu-id="78144-126">Aktualisierte [](machine.md) Geräteentität: ***IpInterfaces-Liste*** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="78144-126">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="78144-127">Siehe ["Geräte auflisten".](get-machines.md)</span><span class="sxs-lookup"><span data-stu-id="78144-127">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="78144-128">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="78144-128">04.11.2020</span></span>

- <span data-ttu-id="78144-129">Neue API hinzugefügt: [Gerätewert festlegen.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="78144-129">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="78144-130">Aktualisierte [](machine.md) Geräteentität: ***deviceValue-Eigenschaft*** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="78144-130">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="78144-131">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="78144-131">01.09.2020</span></span>

- <span data-ttu-id="78144-132">Option zum Erweitern der Warnungsentität um die zugehörigen Nachweise hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="78144-132">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="78144-133">Siehe ["Warnungen auflisten".](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="78144-133">See [List Alerts](get-alerts.md).</span></span>
