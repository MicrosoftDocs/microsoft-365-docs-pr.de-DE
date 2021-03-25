---
title: Bewertungsmethoden und -eigenschaften
description: Ruft die Belichtungs-, Geräte- und Belichtungsergebnis ihrer Organisation nach Gerätegruppe ab.
keywords: apis, graph api, supported apis, score, exposure score, device secure score, exposure score by device group
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 72dacca8529b54b082590d911f03aaa86bfe9097
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200161"
---
# <a name="score-resource-type"></a><span data-ttu-id="ec0ef-104">Bewertungsressourcentyp</span><span class="sxs-lookup"><span data-stu-id="ec0ef-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ec0ef-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ec0ef-105">**Applies to:**</span></span>
- [<span data-ttu-id="ec0ef-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ec0ef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ec0ef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec0ef-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ec0ef-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="ec0ef-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ec0ef-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ec0ef-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="ec0ef-110">Methoden</span><span class="sxs-lookup"><span data-stu-id="ec0ef-110">Methods</span></span>

<span data-ttu-id="ec0ef-111">Methode</span><span class="sxs-lookup"><span data-stu-id="ec0ef-111">Method</span></span> |<span data-ttu-id="ec0ef-112">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="ec0ef-112">Return Type</span></span> |<span data-ttu-id="ec0ef-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec0ef-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="ec0ef-114">Belichtungsergebnis erhalten</span><span class="sxs-lookup"><span data-stu-id="ec0ef-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="ec0ef-115">Bewertung</span><span class="sxs-lookup"><span data-stu-id="ec0ef-115">Score</span></span>](score.md) | <span data-ttu-id="ec0ef-116">Hier erhalten Sie die belichtungsergebnis der Organisation.</span><span class="sxs-lookup"><span data-stu-id="ec0ef-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="ec0ef-117">Sichern der Gerätepunktzahl</span><span class="sxs-lookup"><span data-stu-id="ec0ef-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="ec0ef-118">Bewertung</span><span class="sxs-lookup"><span data-stu-id="ec0ef-118">Score</span></span>](score.md) | <span data-ttu-id="ec0ef-119">Holen Sie sich die sicherheitse Bewertung des Organisationsgeräts.</span><span class="sxs-lookup"><span data-stu-id="ec0ef-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="ec0ef-120">Belichtungsergebnis nach Gerätegruppe auflisten</span><span class="sxs-lookup"><span data-stu-id="ec0ef-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="ec0ef-121">Bewertung</span><span class="sxs-lookup"><span data-stu-id="ec0ef-121">Score</span></span>](score.md) | <span data-ttu-id="ec0ef-122">Noten nach Gerätegruppe auflisten.</span><span class="sxs-lookup"><span data-stu-id="ec0ef-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="ec0ef-123">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ec0ef-123">Properties</span></span>

<span data-ttu-id="ec0ef-124">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ec0ef-124">Property</span></span> |  <span data-ttu-id="ec0ef-125">Typ</span><span class="sxs-lookup"><span data-stu-id="ec0ef-125">Type</span></span>    |   <span data-ttu-id="ec0ef-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec0ef-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="ec0ef-127">Bewertung</span><span class="sxs-lookup"><span data-stu-id="ec0ef-127">Score</span></span> | <span data-ttu-id="ec0ef-128">Gleitkommawert mit doppelter Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="ec0ef-128">Double</span></span> | <span data-ttu-id="ec0ef-129">Die aktuelle Bewertung.</span><span class="sxs-lookup"><span data-stu-id="ec0ef-129">The current score.</span></span>
<span data-ttu-id="ec0ef-130">Zeit</span><span class="sxs-lookup"><span data-stu-id="ec0ef-130">Time</span></span> | <span data-ttu-id="ec0ef-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="ec0ef-131">DateTime</span></span> | <span data-ttu-id="ec0ef-132">Datum und Uhrzeit des Aufrufs dieser API.</span><span class="sxs-lookup"><span data-stu-id="ec0ef-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="ec0ef-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="ec0ef-133">RbacGroupName</span></span> | <span data-ttu-id="ec0ef-134">String</span><span class="sxs-lookup"><span data-stu-id="ec0ef-134">String</span></span> | <span data-ttu-id="ec0ef-135">Der Name der Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="ec0ef-135">The device group name.</span></span>
