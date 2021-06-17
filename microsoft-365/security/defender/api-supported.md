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
ms.openlocfilehash: acd8ec28fb1d78e3724cb0ca0ebee48133e7310f
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985084"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="1468e-104">Unterstützte Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="1468e-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1468e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1468e-105">**Applies to:**</span></span>
- <span data-ttu-id="1468e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1468e-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1468e-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="1468e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1468e-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="1468e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="1468e-109">Liste der verfügbaren APIs</span><span class="sxs-lookup"><span data-stu-id="1468e-109">List of available APIs</span></span>

<span data-ttu-id="1468e-110">Artikel</span><span class="sxs-lookup"><span data-stu-id="1468e-110">Article</span></span> | <span data-ttu-id="1468e-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1468e-111">Description</span></span>
-|-
[<span data-ttu-id="1468e-112">Erweiterte Bedrohungssuche-API</span><span class="sxs-lookup"><span data-stu-id="1468e-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="1468e-113">Führen Sie Abfragen für die erweiterte Suche aus.</span><span class="sxs-lookup"><span data-stu-id="1468e-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="1468e-114">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="1468e-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="1468e-115">Auflisten und Aktualisieren von Vorfällen zusammen mit anderen praktischen Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="1468e-115">List and update incidents, along with other practical tasks.</span></span>
<span data-ttu-id="1468e-116">[Streaming-API](streaming-api.md) (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1468e-116">[Streaming API](streaming-api.md) (Preview)</span></span> | <span data-ttu-id="1468e-117">Versenden Sie Echtzeitereignisse und -warnungen, sobald sie in einem einzelnen Datenstrom auftreten.</span><span class="sxs-lookup"><span data-stu-id="1468e-117">Ship real-time events and alerts as they occur in a single data stream.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="1468e-118">Endpunkt-URIs</span><span class="sxs-lookup"><span data-stu-id="1468e-118">Endpoint URIs</span></span>

<span data-ttu-id="1468e-119">Der Basis-URI für beide Haupt-APIs lautet: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="1468e-119">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="1468e-120">Um eine bessere Leistung zu erzielen, verwenden Sie einen Server, der sich näher an Ihrem Geolocation befindet:</span><span class="sxs-lookup"><span data-stu-id="1468e-120">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="1468e-121">Vereinigte Staaten: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1468e-121">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="1468e-122">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1468e-122">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="1468e-123">Vereinigtes Königreich: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1468e-123">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="1468e-124">Token können durch Zugriff auf abgerufen https://api.security.microsoft.com werden.</span><span class="sxs-lookup"><span data-stu-id="1468e-124">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="1468e-125">Alle APIs entlang des `/api` Pfads verwenden das [OData-Protokoll,](/odata/overview) z. https://api.security.microsoft.com/api/incidents B. .</span><span class="sxs-lookup"><span data-stu-id="1468e-125">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1468e-126">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="1468e-126">Related articles</span></span>

- [<span data-ttu-id="1468e-127">Microsoft 365 Defender ÜBERSICHT ÜBER APIs</span><span class="sxs-lookup"><span data-stu-id="1468e-127">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="1468e-128">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="1468e-128">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="1468e-129">Streaming- API</span><span class="sxs-lookup"><span data-stu-id="1468e-129">Streaming API</span></span>](../defender-endpoint/raw-data-export.md)
- [<span data-ttu-id="1468e-130">Informationen zu API-Grenzwerten und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="1468e-130">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="1468e-131">Grundlegendes zu Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="1468e-131">Understand error codes</span></span>](api-error-codes.md)
