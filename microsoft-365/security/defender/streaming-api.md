---
title: Streamen Microsoft 365 Defender-Ereignisse
description: Erfahren Sie, wie Sie Microsoft 365 Defender so konfigurieren, dass Advanced Hunting-Ereignisse an Event Hubs oder Azure-Speicherkonten gestreamt werden.
keywords: Rohdatenexport, Streaming-API, API, Event Hubs, Azure Storage, Speicherkonto, Erweiterte Suche, Freigabe von Rohdaten
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
ms.openlocfilehash: fad3dd64c9acf079bd8da778d417240c44031569
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772470"
---
# <a name="streaming-api"></a><span data-ttu-id="477dc-104">Streaming-API</span><span class="sxs-lookup"><span data-stu-id="477dc-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="477dc-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="477dc-105">**Applies to:**</span></span>
- [<span data-ttu-id="477dc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="477dc-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="477dc-107">Streamen Von Advanced Hunting-Ereignissen an Event Hubs und/oder Azure-Speicherkonten.</span><span class="sxs-lookup"><span data-stu-id="477dc-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="477dc-108">Microsoft 365 Defender unterstützt das Streamen aller über die [erweiterte Suche](../defender/advanced-hunting-overview.md) verfügbaren Ereignisse an [Event Hubs](/azure/event-hubs/) und/oder [Azure-Speicherkonten.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="477dc-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="477dc-109">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="477dc-109">In this section</span></span>

<span data-ttu-id="477dc-110">Thema</span><span class="sxs-lookup"><span data-stu-id="477dc-110">Topic</span></span> | <span data-ttu-id="477dc-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="477dc-111">Description</span></span>
:---|:---
[<span data-ttu-id="477dc-112">Streamen von Ereignissen an Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="477dc-112">Stream events to Azure Event Hubs</span></span>](streaming-api-event-hub.md)| <span data-ttu-id="477dc-113">Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Microsoft 365 Defender so konfigurieren, dass die [erweiterte Suche](../defender/advanced-hunting-overview.md) auf Event Hubs gestreamt wird.</span><span class="sxs-lookup"><span data-stu-id="477dc-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="477dc-114">Streamen von Ereignissen auf Ihr Azure-Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="477dc-114">Stream events to your Azure storage account</span></span>](streaming-api-storage.md)| <span data-ttu-id="477dc-115">Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Microsoft 365 Defender so konfigurieren, dass [advanced Hunting](advanced-hunting-overview.md) auf Ihr Azure-Speicherkonto gestreamt wird.</span><span class="sxs-lookup"><span data-stu-id="477dc-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="477dc-116">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="477dc-116">Related topics</span></span>
- [<span data-ttu-id="477dc-117">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="477dc-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="477dc-118">Dokumentation zu Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="477dc-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="477dc-119">Azure Storage Kontodokumentation</span><span class="sxs-lookup"><span data-stu-id="477dc-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
