---
title: Streamen des Microsoft Defender für Endpunkt-Ereignisses
description: Erfahren Sie, wie Sie Microsoft Defender für Endpunkt so konfigurieren, dass Advanced Hunting-Ereignisse auf Event Hubs oder Azure-Speicherkonten gestreamt werden.
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
ms.custom: api
ms.openlocfilehash: 3e6d4df1c2c0f4934de1e8a54e8c1676aae230e3
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771621"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="b1c66-104">RAW-Datenstreaming-API</span><span class="sxs-lookup"><span data-stu-id="b1c66-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b1c66-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b1c66-105">**Applies to:**</span></span>
- [<span data-ttu-id="b1c66-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b1c66-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="b1c66-107">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="b1c66-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b1c66-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b1c66-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="b1c66-109">Streamen Von Advanced Hunting-Ereignissen an Event Hubs und/oder Azure-Speicherkonten.</span><span class="sxs-lookup"><span data-stu-id="b1c66-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="b1c66-110">Defender für Endpunkt unterstützt das Streamen aller über die [erweiterte Suche](advanced-hunting-overview.md) verfügbaren Ereignisse an [Event Hubs](/azure/event-hubs/) und/oder [Azure-Speicherkonten.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="b1c66-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="b1c66-111">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="b1c66-111">In this section</span></span>

<span data-ttu-id="b1c66-112">Thema</span><span class="sxs-lookup"><span data-stu-id="b1c66-112">Topic</span></span> | <span data-ttu-id="b1c66-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1c66-113">Description</span></span>
:---|:---
[<span data-ttu-id="b1c66-114">Streamen von Microsoft Defender für Endpunkt-Ereignissen an Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="b1c66-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="b1c66-115">Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Defender für Endpunkt so konfigurieren, dass [die erweiterte Suche](advanced-hunting-overview.md) auf Event Hubs gestreamt wird.</span><span class="sxs-lookup"><span data-stu-id="b1c66-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="b1c66-116">Stream defender für Endpunkt-Ereignisse auf Ihr Azure-Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="b1c66-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="b1c66-117">Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Defender für Endpunkt so konfigurieren, dass [advanced Hunting](advanced-hunting-overview.md) auf Ihr Azure-Speicherkonto gestreamt wird.</span><span class="sxs-lookup"><span data-stu-id="b1c66-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b1c66-118">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b1c66-118">Related topics</span></span>
- [<span data-ttu-id="b1c66-119">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="b1c66-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b1c66-120">Dokumentation zu Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="b1c66-120">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="b1c66-121">Azure Storage Kontodokumentation</span><span class="sxs-lookup"><span data-stu-id="b1c66-121">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)