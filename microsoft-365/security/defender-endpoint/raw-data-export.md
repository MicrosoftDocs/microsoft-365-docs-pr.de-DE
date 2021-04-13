---
title: Streamen des Microsoft Defender for Endpoint-Ereignisses
description: Informationen zum Konfigurieren von Microsoft Defender for Endpoint zum Streamen von Advanced Hunting-Ereignissen an Event Hubs oder Azure-Speicherkonto
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
ms.openlocfilehash: f6a45629d610ea3cc3ca7d517021a215b72b1439
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688753"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="cf01d-104">Raw Data Streaming API</span><span class="sxs-lookup"><span data-stu-id="cf01d-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cf01d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cf01d-105">**Applies to:**</span></span>
- [<span data-ttu-id="cf01d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cf01d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="cf01d-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="cf01d-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cf01d-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cf01d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="cf01d-109">Streamen von Advanced Hunting-Ereignissen an Event Hubs und/oder Azure-Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="cf01d-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="cf01d-110">Defender for Endpoint unterstützt das Streamen aller ereignisse, die über [die erweiterte](advanced-hunting-overview.md) Suche verfügbar sind, an [event hubs](https://docs.microsoft.com/azure/event-hubs/) und/oder [azure storage account](https://docs.microsoft.com/azure/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="cf01d-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](https://docs.microsoft.com/azure/event-hubs/) and/or [Azure storage account](https://docs.microsoft.com/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="cf01d-111">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="cf01d-111">In this section</span></span>

<span data-ttu-id="cf01d-112">Thema</span><span class="sxs-lookup"><span data-stu-id="cf01d-112">Topic</span></span> | <span data-ttu-id="cf01d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf01d-113">Description</span></span>
:---|:---
[<span data-ttu-id="cf01d-114">Streamen von Microsoft Defender for Endpoint-Ereignissen an Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="cf01d-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="cf01d-115">Erfahren Sie mehr über das Aktivieren der Streaming-API in Ihrem Mandanten und konfigurieren Sie Defender for Endpoint zum [Streamen von Advanced Hunting](advanced-hunting-overview.md) zu Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="cf01d-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="cf01d-116">Stream Defender for Endpoint-Ereignisse an Ihr Azure-Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="cf01d-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="cf01d-117">Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Defender for Endpoint so konfigurieren, dass [Advanced Hunting](advanced-hunting-overview.md) an Ihr Azure-Speicherkonto streamt.</span><span class="sxs-lookup"><span data-stu-id="cf01d-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="cf01d-118">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cf01d-118">Related topics</span></span>
- [<span data-ttu-id="cf01d-119">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="cf01d-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cf01d-120">Dokumentation zu Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="cf01d-120">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="cf01d-121">Dokumentation zu Azure Storage Account</span><span class="sxs-lookup"><span data-stu-id="cf01d-121">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
