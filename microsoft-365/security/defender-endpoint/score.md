---
title: Bewertungsmethoden und -eigenschaften
description: Ruft die Belichtungs-, Geräte- und Belichtungsergebnis ihrer Organisation nach Gerätegruppe ab.
keywords: apis, graph api, supported apis, score, exposure score, device secure score, exposure score by device group
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1c287a72318cfb2e6e4e3860ac90a90e561040fe
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500952"
---
# <a name="score-resource-type"></a><span data-ttu-id="b279d-104">Bewertungsressourcentyp</span><span class="sxs-lookup"><span data-stu-id="b279d-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b279d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b279d-105">**Applies to:**</span></span>
- [<span data-ttu-id="b279d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b279d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b279d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b279d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b279d-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b279d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b279d-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b279d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="b279d-110">Methoden</span><span class="sxs-lookup"><span data-stu-id="b279d-110">Methods</span></span>

<span data-ttu-id="b279d-111">Methode</span><span class="sxs-lookup"><span data-stu-id="b279d-111">Method</span></span> |<span data-ttu-id="b279d-112">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="b279d-112">Return Type</span></span> |<span data-ttu-id="b279d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b279d-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="b279d-114">Erhalten des Gefährdungsscores</span><span class="sxs-lookup"><span data-stu-id="b279d-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="b279d-115">Bewertung</span><span class="sxs-lookup"><span data-stu-id="b279d-115">Score</span></span>](score.md) | <span data-ttu-id="b279d-116">Hier erhalten Sie die belichtungsergebnis der Organisation.</span><span class="sxs-lookup"><span data-stu-id="b279d-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="b279d-117">Sicherheitsbewertung des Geräts erhalten</span><span class="sxs-lookup"><span data-stu-id="b279d-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="b279d-118">Bewertung</span><span class="sxs-lookup"><span data-stu-id="b279d-118">Score</span></span>](score.md) | <span data-ttu-id="b279d-119">Holen Sie sich die sicherheitse Bewertung des Organisationsgeräts.</span><span class="sxs-lookup"><span data-stu-id="b279d-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="b279d-120">Belichtungsergebnis nach Gerätegruppe auflisten</span><span class="sxs-lookup"><span data-stu-id="b279d-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="b279d-121">Bewertung</span><span class="sxs-lookup"><span data-stu-id="b279d-121">Score</span></span>](score.md) | <span data-ttu-id="b279d-122">Noten nach Gerätegruppe auflisten.</span><span class="sxs-lookup"><span data-stu-id="b279d-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="b279d-123">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b279d-123">Properties</span></span>

<span data-ttu-id="b279d-124">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b279d-124">Property</span></span> |  <span data-ttu-id="b279d-125">Typ</span><span class="sxs-lookup"><span data-stu-id="b279d-125">Type</span></span>    |   <span data-ttu-id="b279d-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b279d-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="b279d-127">Bewertung</span><span class="sxs-lookup"><span data-stu-id="b279d-127">Score</span></span> | <span data-ttu-id="b279d-128">Gleitkommawert mit doppelter Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="b279d-128">Double</span></span> | <span data-ttu-id="b279d-129">Die aktuelle Bewertung.</span><span class="sxs-lookup"><span data-stu-id="b279d-129">The current score.</span></span>
<span data-ttu-id="b279d-130">Zeit</span><span class="sxs-lookup"><span data-stu-id="b279d-130">Time</span></span> | <span data-ttu-id="b279d-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="b279d-131">DateTime</span></span> | <span data-ttu-id="b279d-132">Datum und Uhrzeit des Aufrufs dieser API.</span><span class="sxs-lookup"><span data-stu-id="b279d-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="b279d-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="b279d-133">RbacGroupName</span></span> | <span data-ttu-id="b279d-134">String</span><span class="sxs-lookup"><span data-stu-id="b279d-134">String</span></span> | <span data-ttu-id="b279d-135">Der Name der Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="b279d-135">The device group name.</span></span>
