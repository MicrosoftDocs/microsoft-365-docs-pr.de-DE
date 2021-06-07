---
title: Bewertungsmethoden und -eigenschaften
description: Ruft die Belichtungsbewertung Ihrer Organisation, die Sicherheitsbewertung des Geräts und die Belichtungsbewertung nach Gerätegruppe ab.
keywords: APIs, Graph-API, unterstützte APIs, Bewertung, Belichtungsbewertung, Sicherheitsbewertung des Geräts, Belichtungsbewertung nach Gerätegruppe
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771429"
---
# <a name="score-resource-type"></a><span data-ttu-id="bfac6-104">Score-Ressourcentyp</span><span class="sxs-lookup"><span data-stu-id="bfac6-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bfac6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bfac6-105">**Applies to:**</span></span>
- [<span data-ttu-id="bfac6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bfac6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="bfac6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfac6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bfac6-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="bfac6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bfac6-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bfac6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="bfac6-110">Methoden</span><span class="sxs-lookup"><span data-stu-id="bfac6-110">Methods</span></span>

<span data-ttu-id="bfac6-111">Methode</span><span class="sxs-lookup"><span data-stu-id="bfac6-111">Method</span></span> |<span data-ttu-id="bfac6-112">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="bfac6-112">Return Type</span></span> |<span data-ttu-id="bfac6-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bfac6-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="bfac6-114">Erhalten des Gefährdungsscores</span><span class="sxs-lookup"><span data-stu-id="bfac6-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="bfac6-115">Bewertung</span><span class="sxs-lookup"><span data-stu-id="bfac6-115">Score</span></span>](score.md) | <span data-ttu-id="bfac6-116">Rufen Sie die Belichtungsbewertung der Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="bfac6-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="bfac6-117">Sicherheitsbewertung des Geräts erhalten</span><span class="sxs-lookup"><span data-stu-id="bfac6-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="bfac6-118">Bewertung</span><span class="sxs-lookup"><span data-stu-id="bfac6-118">Score</span></span>](score.md) | <span data-ttu-id="bfac6-119">Rufen Sie die Sicherheitsbewertung des Unternehmensgeräts ab.</span><span class="sxs-lookup"><span data-stu-id="bfac6-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="bfac6-120">Belichtungsbewertung nach Gerätegruppe auflisten</span><span class="sxs-lookup"><span data-stu-id="bfac6-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="bfac6-121">Bewertung</span><span class="sxs-lookup"><span data-stu-id="bfac6-121">Score</span></span>](score.md) | <span data-ttu-id="bfac6-122">Auflisten von Bewertungen nach Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="bfac6-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="bfac6-123">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bfac6-123">Properties</span></span>

<span data-ttu-id="bfac6-124">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bfac6-124">Property</span></span> |  <span data-ttu-id="bfac6-125">Typ</span><span class="sxs-lookup"><span data-stu-id="bfac6-125">Type</span></span>    |   <span data-ttu-id="bfac6-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bfac6-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="bfac6-127">Bewertung</span><span class="sxs-lookup"><span data-stu-id="bfac6-127">Score</span></span> | <span data-ttu-id="bfac6-128">Gleitkommawert mit doppelter Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="bfac6-128">Double</span></span> | <span data-ttu-id="bfac6-129">Die aktuelle Bewertung.</span><span class="sxs-lookup"><span data-stu-id="bfac6-129">The current score.</span></span>
<span data-ttu-id="bfac6-130">Zeit</span><span class="sxs-lookup"><span data-stu-id="bfac6-130">Time</span></span> | <span data-ttu-id="bfac6-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="bfac6-131">DateTime</span></span> | <span data-ttu-id="bfac6-132">Datum und Uhrzeit des Aufrufs dieser API.</span><span class="sxs-lookup"><span data-stu-id="bfac6-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="bfac6-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="bfac6-133">RbacGroupName</span></span> | <span data-ttu-id="bfac6-134">String</span><span class="sxs-lookup"><span data-stu-id="bfac6-134">String</span></span> | <span data-ttu-id="bfac6-135">Der Name der Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="bfac6-135">The device group name.</span></span>
