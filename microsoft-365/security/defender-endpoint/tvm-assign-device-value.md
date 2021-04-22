---
title: Zuweisen des Gerätewerts – Bedrohungs- und Sicherheitsrisikoverwaltung
description: Erfahren Sie, wie Sie einem Gerät einen niedrigen, normalen oder hohen Wert zuweisen, um zwischen den Ressourcenprioritäten zu unterscheiden.
keywords: Microsoft Defender for Endpoint Device Value, Threat and Vulnerability Management Device Value, High Value Devices, Device Value Exposure Score
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ca6c88b08b331eb65035387a9c070d0914b1651d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935197"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="412c3-104">Zuweisen des Gerätewerts – Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="412c3-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="412c3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="412c3-105">**Applies to:**</span></span>

- [<span data-ttu-id="412c3-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="412c3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="412c3-107">Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="412c3-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="412c3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="412c3-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="412c3-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="412c3-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="412c3-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="412c3-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="412c3-111">Wenn Sie den Wert eines Geräts definieren, können Sie zwischen den Ressourcenprioritäten unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="412c3-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="412c3-112">Der Gerätewert wird verwendet, um die Risikobereitschaft eines einzelnen Vermögenswerts in die Berechnung der Risikobewertung für das Risiko- und Sicherheitsrisikomanagement zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="412c3-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="412c3-113">Geräte, die als "hoher Wert" zugewiesen sind, erhalten mehr Gewichtung.</span><span class="sxs-lookup"><span data-stu-id="412c3-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="412c3-114">Sie können auch die [Set Device Value API verwenden.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="412c3-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="412c3-115">Gerätewertoptionen:</span><span class="sxs-lookup"><span data-stu-id="412c3-115">Device value options:</span></span>

- <span data-ttu-id="412c3-116">Niedrig</span><span class="sxs-lookup"><span data-stu-id="412c3-116">Low</span></span>
- <span data-ttu-id="412c3-117">Normal (Standard)</span><span class="sxs-lookup"><span data-stu-id="412c3-117">Normal (Default)</span></span>
- <span data-ttu-id="412c3-118">Hoch</span><span class="sxs-lookup"><span data-stu-id="412c3-118">High</span></span>

<span data-ttu-id="412c3-119">Beispiele für Geräte, denen ein hoher Wert zugewiesen werden sollte:</span><span class="sxs-lookup"><span data-stu-id="412c3-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="412c3-120">Domänencontroller, Active Directory</span><span class="sxs-lookup"><span data-stu-id="412c3-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="412c3-121">Mit dem Internet zu verbindende Geräte</span><span class="sxs-lookup"><span data-stu-id="412c3-121">Internet facing devices</span></span>
- <span data-ttu-id="412c3-122">VIP-Geräte</span><span class="sxs-lookup"><span data-stu-id="412c3-122">VIP devices</span></span>
- <span data-ttu-id="412c3-123">Geräte, die interne/externe Produktionsdienste hosten</span><span class="sxs-lookup"><span data-stu-id="412c3-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="412c3-124">Gerätewert auswählen</span><span class="sxs-lookup"><span data-stu-id="412c3-124">Choose device value</span></span>

1. <span data-ttu-id="412c3-125">Navigieren Sie zu einer beliebigen Geräteseite, der einfachste Ort ist aus dem Gerätebestand.</span><span class="sxs-lookup"><span data-stu-id="412c3-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="412c3-126">Wählen **Sie Gerätewert** aus drei Punkten neben der Aktionsleiste am oberen Rand der Seite aus.</span><span class="sxs-lookup"><span data-stu-id="412c3-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![Beispiel für das Dropdownmenü des Gerätewerts.](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="412c3-128">Ein Flyout wird mit dem aktuellen Gerätewert und dem, was es bedeutet, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="412c3-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="412c3-129">Überprüfen Sie den Wert des Geräts, und wählen Sie das Gerät aus, das am besten zu Ihrem Gerät passt.</span><span class="sxs-lookup"><span data-stu-id="412c3-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="412c3-130">![Beispiel für das Flyout des Gerätewerts.](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="412c3-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="412c3-131">Auswirkungen des Gerätewerts auf ihre Belichtungsergebnis</span><span class="sxs-lookup"><span data-stu-id="412c3-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="412c3-132">Die Belichtungsnote ist ein gewichteter Durchschnitt auf allen Geräten.</span><span class="sxs-lookup"><span data-stu-id="412c3-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="412c3-133">Wenn Sie Gerätegruppen haben, können Sie die Bewertung auch nach Gerätegruppe filtern.</span><span class="sxs-lookup"><span data-stu-id="412c3-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="412c3-134">Normale Geräte haben eine Gewichtung von 1</span><span class="sxs-lookup"><span data-stu-id="412c3-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="412c3-135">Geräte mit geringem Wert haben eine Gewichtung von 0,75</span><span class="sxs-lookup"><span data-stu-id="412c3-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="412c3-136">Hochwertige Geräte haben eine Gewichtung von NumberOfAssets /10.</span><span class="sxs-lookup"><span data-stu-id="412c3-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="412c3-137">Wenn Sie über 100 Geräte verfügen, hat jedes hochwertige Gerät eine Gewichtung von 10 (100/10)</span><span class="sxs-lookup"><span data-stu-id="412c3-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="412c3-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="412c3-138">Related topics</span></span>

- [<span data-ttu-id="412c3-139">Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="412c3-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="412c3-140">Belichtungsergebnis</span><span class="sxs-lookup"><span data-stu-id="412c3-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="412c3-141">APIs</span><span class="sxs-lookup"><span data-stu-id="412c3-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)