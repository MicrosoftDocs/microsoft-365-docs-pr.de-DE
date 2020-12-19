---
title: Unterstützte Microsoft 365 Defender-APIs
description: Unterstützte Microsoft 365 Defender-APIs
keywords: MTP, APIs, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719322"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="d5c97-104">Unterstützte Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="d5c97-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d5c97-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d5c97-105">**Applies to:**</span></span>
- <span data-ttu-id="d5c97-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5c97-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5c97-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="d5c97-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d5c97-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="d5c97-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="d5c97-109">Liste der verfügbaren APIs</span><span class="sxs-lookup"><span data-stu-id="d5c97-109">List of available APIs</span></span>

<span data-ttu-id="d5c97-110">Artikel</span><span class="sxs-lookup"><span data-stu-id="d5c97-110">Article</span></span> | <span data-ttu-id="d5c97-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5c97-111">Description</span></span>
-|-
[<span data-ttu-id="d5c97-112">Erweiterte Suche-API</span><span class="sxs-lookup"><span data-stu-id="d5c97-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="d5c97-113">Führen Sie erweiterte Jagd Abfragen aus.</span><span class="sxs-lookup"><span data-stu-id="d5c97-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="d5c97-114">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="d5c97-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="d5c97-115">Auflisten und Aktualisieren von Vorfällen sowie anderer praktischer Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="d5c97-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="d5c97-116">Endpunkt-URIs</span><span class="sxs-lookup"><span data-stu-id="d5c97-116">Endpoint URIs</span></span>

<span data-ttu-id="d5c97-117">Der Basis-URI für die beiden Haupt-APIs lautet: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="d5c97-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="d5c97-118">Um eine bessere Leistung zu erzielen, verwenden Sie einen Server näher an Ihrem Standort:</span><span class="sxs-lookup"><span data-stu-id="d5c97-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="d5c97-119">Vereinigte Staaten: API-US.Security.Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d5c97-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="d5c97-120">Europa: API-EU.Security.Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d5c97-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="d5c97-121">Vereinigtes Königreich: API-UK.Security.Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d5c97-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="d5c97-122">Token können durch den Zugriff erworben werden https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="d5c97-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="d5c97-123">Alle APIs entlang des `/api` Pfads verwenden das [OData](https://docs.microsoft.com/odata/overview) -Protokoll, beispielsweise https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="d5c97-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d5c97-124">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="d5c97-124">Related articles</span></span>

- [<span data-ttu-id="d5c97-125">Microsoft 365 Defender-APIs (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="d5c97-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="d5c97-126">Zugreifen auf die Microsoft Threat Protection-APIs</span><span class="sxs-lookup"><span data-stu-id="d5c97-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="d5c97-127">Informationen zu API-Grenzwerten und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="d5c97-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="d5c97-128">Grundlegendes zu Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="d5c97-128">Understand error codes</span></span>](api-error-codes.md)
