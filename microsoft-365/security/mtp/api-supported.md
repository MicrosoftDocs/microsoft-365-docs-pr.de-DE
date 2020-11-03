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
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844960"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="90030-104">Unterstützte Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="90030-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="90030-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="90030-105">**Applies to:**</span></span>
- <span data-ttu-id="90030-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90030-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="90030-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="90030-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="90030-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="90030-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="90030-109">Endpunkt-URIs:</span><span class="sxs-lookup"><span data-stu-id="90030-109">End Point URIs:</span></span>

- <span data-ttu-id="90030-110">Der Dienst Basis-URI lautet: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="90030-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="90030-111">Um eine bessere Leistung zu erzielen, können Sie den Server näher an ihrem geografischen Standort verwenden:</span><span class="sxs-lookup"><span data-stu-id="90030-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="90030-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="90030-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="90030-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="90030-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="90030-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="90030-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="90030-115">Die Ressource für die Token-Akquisition sollte wie folgt aussehen: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="90030-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="90030-116">Alle APIs unter ```/api``` Path sind OData-APIs.</span><span class="sxs-lookup"><span data-stu-id="90030-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="90030-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="90030-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="90030-118">Liste der verfügbaren APIs:</span><span class="sxs-lookup"><span data-stu-id="90030-118">List of available APIs:</span></span>

<span data-ttu-id="90030-119">Thema</span><span class="sxs-lookup"><span data-stu-id="90030-119">Topic</span></span> | <span data-ttu-id="90030-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90030-120">Description</span></span>
:---|:---
[<span data-ttu-id="90030-121">Erweiterte Suche-API</span><span class="sxs-lookup"><span data-stu-id="90030-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="90030-122">Ausführen erweiterter Jagd Abfragen aus der API.</span><span class="sxs-lookup"><span data-stu-id="90030-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="90030-123">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="90030-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="90030-124">Führen Sie Vorfall bezogene API-Aufrufe wie: Listen Vorfälle, Update Vorfall und vieles mehr aus.</span><span class="sxs-lookup"><span data-stu-id="90030-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
