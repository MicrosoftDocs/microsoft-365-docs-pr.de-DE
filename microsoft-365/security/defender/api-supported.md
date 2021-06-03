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
ms.openlocfilehash: c10b2863503a5bda829cbf67379a606b687ac2e3
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730942"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="84b7c-104">Unterstützte Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="84b7c-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="84b7c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="84b7c-105">**Applies to:**</span></span>
- <span data-ttu-id="84b7c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84b7c-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84b7c-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="84b7c-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="84b7c-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="84b7c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="84b7c-109">Liste der verfügbaren APIs</span><span class="sxs-lookup"><span data-stu-id="84b7c-109">List of available APIs</span></span>

<span data-ttu-id="84b7c-110">Artikel</span><span class="sxs-lookup"><span data-stu-id="84b7c-110">Article</span></span> | <span data-ttu-id="84b7c-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84b7c-111">Description</span></span>
-|-
[<span data-ttu-id="84b7c-112">Erweiterte Suche-API</span><span class="sxs-lookup"><span data-stu-id="84b7c-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="84b7c-113">Führen Sie Erweiterte Suchabfragen aus.</span><span class="sxs-lookup"><span data-stu-id="84b7c-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="84b7c-114">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="84b7c-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="84b7c-115">Auflisten und Aktualisieren von Vorfällen sowie andere praktische Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="84b7c-115">List and update incidents, along with other practical tasks.</span></span>
<span data-ttu-id="84b7c-116">[Streaming-API](../defender-endpoint/raw-data-export.md) (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="84b7c-116">[Streaming API](../defender-endpoint/raw-data-export.md) (Preview)</span></span> | <span data-ttu-id="84b7c-117">Senden von Echtzeitereignissen und -warnungen, die in einem einzelnen Datenstrom auftreten.</span><span class="sxs-lookup"><span data-stu-id="84b7c-117">Ship real-time events and alerts as they occur in a single data stream.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="84b7c-118">Endpunkt-URIs</span><span class="sxs-lookup"><span data-stu-id="84b7c-118">Endpoint URIs</span></span>

<span data-ttu-id="84b7c-119">Der Basis-URI für beide Haupt-APIs ist: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="84b7c-119">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="84b7c-120">Verwenden Sie für eine bessere Leistung einen Server, der näher an Ihrer Geolocation ist:</span><span class="sxs-lookup"><span data-stu-id="84b7c-120">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="84b7c-121">Usa: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="84b7c-121">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="84b7c-122">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="84b7c-122">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="84b7c-123">Vereinigtes Königreich: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="84b7c-123">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="84b7c-124">Token können durch Zugriff auf erworben https://api.security.microsoft.com werden.</span><span class="sxs-lookup"><span data-stu-id="84b7c-124">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="84b7c-125">Alle APIs entlang des `/api` Pfads verwenden das [OData-Protokoll,](/odata/overview) z. B. https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="84b7c-125">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="84b7c-126">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="84b7c-126">Related articles</span></span>

- [<span data-ttu-id="84b7c-127">Microsoft 365 Übersicht über Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="84b7c-127">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="84b7c-128">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="84b7c-128">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="84b7c-129">Streaming-API</span><span class="sxs-lookup"><span data-stu-id="84b7c-129">Streaming API</span></span>](../defender-endpoint/raw-data-export.md)
- [<span data-ttu-id="84b7c-130">Informationen zu API-Beschränkungen und -Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="84b7c-130">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="84b7c-131">Verstehen von Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="84b7c-131">Understand error codes</span></span>](api-error-codes.md)
