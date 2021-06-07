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
ms.openlocfilehash: 21a83c4876a90a231eb2a78d10a290be2dca2fa0
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782477"
---
# <a name="streaming-api"></a><span data-ttu-id="caa8a-104">Streaming-API</span><span class="sxs-lookup"><span data-stu-id="caa8a-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="caa8a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="caa8a-105">**Applies to:**</span></span>
- [<span data-ttu-id="caa8a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="caa8a-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="caa8a-107">Streamen Von Advanced Hunting-Ereignissen an Event Hubs und/oder Azure-Speicherkonten.</span><span class="sxs-lookup"><span data-stu-id="caa8a-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="caa8a-108">Microsoft 365 Defender unterstützt Streamingereignisse über [die erweiterte Suche](../defender/advanced-hunting-overview.md) an Event [Hubs](/azure/event-hubs/) und/oder [Azure-Speicherkonten.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="caa8a-108">Microsoft 365 Defender supports streaming events through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="caa8a-109">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="caa8a-109">In this section</span></span>

<span data-ttu-id="caa8a-110">Thema</span><span class="sxs-lookup"><span data-stu-id="caa8a-110">Topic</span></span> | <span data-ttu-id="caa8a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="caa8a-111">Description</span></span>
:---|:---
[<span data-ttu-id="caa8a-112">Streamen von Ereignissen an Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="caa8a-112">Stream events to Azure Event Hubs</span></span>](streaming-api-event-hub.md)| <span data-ttu-id="caa8a-113">Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Microsoft 365 Defender so konfigurieren, dass die [erweiterte Suche](../defender/advanced-hunting-overview.md) auf Event Hubs gestreamt wird.</span><span class="sxs-lookup"><span data-stu-id="caa8a-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="caa8a-114">Streamen von Ereignissen auf Ihr Azure-Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="caa8a-114">Stream events to your Azure storage account</span></span>](streaming-api-storage.md)| <span data-ttu-id="caa8a-115">Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Microsoft 365 Defender so konfigurieren, dass [advanced Hunting](advanced-hunting-overview.md) auf Ihr Azure-Speicherkonto gestreamt wird.</span><span class="sxs-lookup"><span data-stu-id="caa8a-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="caa8a-116">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="caa8a-116">Related topics</span></span>
- [<span data-ttu-id="caa8a-117">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="caa8a-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="caa8a-118">Dokumentation zu Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="caa8a-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="caa8a-119">Azure Storage Kontodokumentation</span><span class="sxs-lookup"><span data-stu-id="caa8a-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
