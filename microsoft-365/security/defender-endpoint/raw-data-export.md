---
title: Streamen Microsoft 365 Defender-Ereignissen
description: Informationen zum Konfigurieren von Microsoft 365 Defender zum Streamen von Advanced Hunting-Ereignissen an Event Hubs oder Azure-Speicherkonto
keywords: Rohdatenexport, Streaming-API, API, Event Hubs, Azure-Speicher, Speicherkonto, Erweiterte Suche, Freigabe von Rohdaten
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0c25ec8bc88a2714fb2f02ef8641c3eae700efe0
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730690"
---
# <a name="streaming-api"></a><span data-ttu-id="afc4c-104">Streaming-API</span><span class="sxs-lookup"><span data-stu-id="afc4c-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="afc4c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="afc4c-105">**Applies to:**</span></span>
- [<span data-ttu-id="afc4c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="afc4c-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="afc4c-107">Streamen von Advanced Hunting-Ereignissen an Event Hubs und/oder Azure-Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="afc4c-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="afc4c-108">Microsoft 365 Defender unterstützt das Streaming aller ereignisse, die über [die erweiterte Suche](../defender/advanced-hunting-overview.md) verfügbar sind, an Event [Hubs](/azure/event-hubs/) und/oder [azure speicherkonto](/azure/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="afc4c-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="afc4c-109">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="afc4c-109">In this section</span></span>

<span data-ttu-id="afc4c-110">Thema</span><span class="sxs-lookup"><span data-stu-id="afc4c-110">Topic</span></span> | <span data-ttu-id="afc4c-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afc4c-111">Description</span></span>
:---|:---
[<span data-ttu-id="afc4c-112">Streamen von Ereignissen an Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="afc4c-112">Stream events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="afc4c-113">Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Microsoft 365 Defender so konfigurieren, dass [Advanced Hunting](../defender/advanced-hunting-overview.md) zu Event Hubs gestreamt wird.</span><span class="sxs-lookup"><span data-stu-id="afc4c-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="afc4c-114">Streamen von Ereignissen an Ihr Azure-Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="afc4c-114">Stream events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="afc4c-115">Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Microsoft 365 Defender so konfigurieren, dass [Advanced Hunting](../defender/advanced-hunting-overview.md) auf Ihr Azure-Speicherkonto gestreamt wird.</span><span class="sxs-lookup"><span data-stu-id="afc4c-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="afc4c-116">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="afc4c-116">Related topics</span></span>
- [<span data-ttu-id="afc4c-117">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="afc4c-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="afc4c-118">Dokumentation zu Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="afc4c-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="afc4c-119">Azure Storage Kontodokumentation</span><span class="sxs-lookup"><span data-stu-id="afc4c-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
