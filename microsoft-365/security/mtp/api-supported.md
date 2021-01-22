---
title: Unterstützte Microsoft 365 Defender-APIs
description: Unterstützte Microsoft 365 Defender-APIs
keywords: MTP, APIs, API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ee03e5a255a88c084403842e7bf0319c06c0517b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926198"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="cac99-104">Unterstützte Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="cac99-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cac99-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cac99-105">**Applies to:**</span></span>
- <span data-ttu-id="cac99-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cac99-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cac99-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="cac99-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cac99-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="cac99-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="cac99-109">Liste der verfügbaren APIs</span><span class="sxs-lookup"><span data-stu-id="cac99-109">List of available APIs</span></span>

<span data-ttu-id="cac99-110">Artikel</span><span class="sxs-lookup"><span data-stu-id="cac99-110">Article</span></span> | <span data-ttu-id="cac99-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cac99-111">Description</span></span>
-|-
[<span data-ttu-id="cac99-112">Erweiterte Suche-API</span><span class="sxs-lookup"><span data-stu-id="cac99-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="cac99-113">Führen Sie Erweiterte Suchabfragen aus.</span><span class="sxs-lookup"><span data-stu-id="cac99-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="cac99-114">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="cac99-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="cac99-115">Auflisten und Aktualisieren von Vorfällen sowie anderer praktischer Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="cac99-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="cac99-116">Endpunkt-URIs</span><span class="sxs-lookup"><span data-stu-id="cac99-116">Endpoint URIs</span></span>

<span data-ttu-id="cac99-117">Der Basis-URI für beide haupt-APIs ist: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="cac99-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="cac99-118">Um eine bessere Leistung zu erzielen, verwenden Sie einen Server, der näher an Ihrem Geografischen Standort ist:</span><span class="sxs-lookup"><span data-stu-id="cac99-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="cac99-119">Usa: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cac99-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="cac99-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cac99-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="cac99-121">Vereinigtes Königreich: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cac99-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="cac99-122">Token können durch Zugriff auf erworben https://api.security.microsoft.com werden.</span><span class="sxs-lookup"><span data-stu-id="cac99-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="cac99-123">Alle APIs entlang des `/api` Pfads verwenden das [OData-Protokoll,](https://docs.microsoft.com/odata/overview) z. B. https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="cac99-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cac99-124">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="cac99-124">Related articles</span></span>

- [<span data-ttu-id="cac99-125">Übersicht über Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="cac99-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="cac99-126">Zugreifen auf die Microsoft Threat Protection-APIs</span><span class="sxs-lookup"><span data-stu-id="cac99-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="cac99-127">Informationen zu API-Beschränkungen und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="cac99-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="cac99-128">Fehlercodes verstehen</span><span class="sxs-lookup"><span data-stu-id="cac99-128">Understand error codes</span></span>](api-error-codes.md)
