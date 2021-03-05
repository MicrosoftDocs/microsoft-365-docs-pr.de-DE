---
title: Migrationen von Mandanten zu Mandanten in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie Microsoft 365-Mandanten migrieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 09b2bc77333afaf1991064369846241328db85ff
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461643"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="bfa19-103">Migrationen von Mandanten zu Mandanten in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bfa19-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="bfa19-104">Es gibt verschiedene Architekturansätze für Fusionen, Übernahmen, Abgänge und andere Szenarien, die Sie dazu führen können, einen vorhandenen Microsoft 365-Mandanten zu einem neuen Mandanten zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="bfa19-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="bfa19-105">Die meisten Kunden arbeiten mit Microsoft Consulting Services oder einem Microsoft-Partner zusammen, um Mandanten zu migrieren, einschließlich der Verwendung von Drittanbietertools zum Migrieren von Inhalten.</span><span class="sxs-lookup"><span data-stu-id="bfa19-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="bfa19-106">Verwenden Sie das Architekturmodell für die [Mandanten-zu-Mandant-Migration,](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) um zu verstehen, wie Sie Migrationen zwischen Mandanten und Mandanten von Microsoft 365 und die Schritte einer Migration planen.</span><span class="sxs-lookup"><span data-stu-id="bfa19-106">Use the [Tenant-to-tenant migration architecture model](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="bfa19-107">[![Mandanten-zu-Mandant-Migrationsmodell](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="bfa19-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="bfa19-108">Sie laden dieses Modell im [PDF-Format](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) herunter und drucken es auf Brief-, Rechts- oder Tabloidpapier (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="bfa19-108">You download this model in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="bfa19-109">Dieses Modell bietet Anleitungen und einen Ausgangspunkt für die Planung mit Abschnitten zu folgenden Bereichen:</span><span class="sxs-lookup"><span data-stu-id="bfa19-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="bfa19-110">Zuordnung von Geschäftsszenarien zu Architekturansätzen</span><span class="sxs-lookup"><span data-stu-id="bfa19-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="bfa19-111">Überlegungen zum Entwurf</span><span class="sxs-lookup"><span data-stu-id="bfa19-111">Design considerations</span></span>

<span data-ttu-id="bfa19-112">Dieses Modell enthält außerdem detaillierte Beispiele für:</span><span class="sxs-lookup"><span data-stu-id="bfa19-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="bfa19-113">Ein einzelner Ereignismigrationsfluss</span><span class="sxs-lookup"><span data-stu-id="bfa19-113">A single event migration flow</span></span>
- <span data-ttu-id="bfa19-114">Ein phasenweiser Migrationsfluss</span><span class="sxs-lookup"><span data-stu-id="bfa19-114">A phased migration flow</span></span>
- <span data-ttu-id="bfa19-115">Eine Mandanten verschieben oder geteilten Fluss</span><span class="sxs-lookup"><span data-stu-id="bfa19-115">A tenant move or split flow</span></span>
