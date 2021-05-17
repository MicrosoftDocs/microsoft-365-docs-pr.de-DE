---
title: Unterstützte Microsoft 365 Defender-APIs
description: Unterstützte Microsoft 365 Defender-APIs
keywords: Microsoft 365 Defender, APIs, API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f2c66dca326589807f5712c5548c177a0d08ade0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935725"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="e77eb-104">Unterstützte Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="e77eb-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e77eb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e77eb-105">**Applies to:**</span></span>
- <span data-ttu-id="e77eb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e77eb-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e77eb-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="e77eb-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e77eb-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="e77eb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="e77eb-109">Liste der verfügbaren APIs</span><span class="sxs-lookup"><span data-stu-id="e77eb-109">List of available APIs</span></span>

<span data-ttu-id="e77eb-110">Artikel</span><span class="sxs-lookup"><span data-stu-id="e77eb-110">Article</span></span> | <span data-ttu-id="e77eb-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e77eb-111">Description</span></span>
-|-
[<span data-ttu-id="e77eb-112">Erweiterte Suche-API</span><span class="sxs-lookup"><span data-stu-id="e77eb-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="e77eb-113">Führen Sie Erweiterte Suchabfragen aus.</span><span class="sxs-lookup"><span data-stu-id="e77eb-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="e77eb-114">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="e77eb-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="e77eb-115">Auflisten und Aktualisieren von Vorfällen sowie andere praktische Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="e77eb-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="e77eb-116">Endpunkt-URIs</span><span class="sxs-lookup"><span data-stu-id="e77eb-116">Endpoint URIs</span></span>

<span data-ttu-id="e77eb-117">Der Basis-URI für beide Haupt-APIs ist: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="e77eb-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="e77eb-118">Verwenden Sie für eine bessere Leistung einen Server, der näher an Ihrer Geolocation ist:</span><span class="sxs-lookup"><span data-stu-id="e77eb-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="e77eb-119">Usa: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e77eb-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="e77eb-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e77eb-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="e77eb-121">Vereinigtes Königreich: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e77eb-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="e77eb-122">Token können durch Zugriff auf erworben https://api.security.microsoft.com werden.</span><span class="sxs-lookup"><span data-stu-id="e77eb-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="e77eb-123">Alle APIs entlang des `/api` Pfads verwenden das [OData-Protokoll,](/odata/overview) z. B. https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="e77eb-123">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e77eb-124">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="e77eb-124">Related articles</span></span>

- [<span data-ttu-id="e77eb-125">Microsoft 365 Übersicht über Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="e77eb-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="e77eb-126">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="e77eb-126">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="e77eb-127">Informationen zu API-Beschränkungen und -Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="e77eb-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="e77eb-128">Verstehen von Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="e77eb-128">Understand error codes</span></span>](api-error-codes.md)