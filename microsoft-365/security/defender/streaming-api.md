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
# <a name="streaming-api"></a>Streaming-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Streamen Von Advanced Hunting-Ereignissen an Event Hubs und/oder Azure-Speicherkonten.

Microsoft 365 Defender unterstützt das Streamen aller über die [erweiterte Suche](../defender/advanced-hunting-overview.md) verfügbaren Ereignisse an [Event Hubs](/azure/event-hubs/) und/oder [Azure-Speicherkonten.](/azure/event-hubs/)



## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Thema | Beschreibung
:---|:---
[Streamen von Ereignissen an Azure Event Hubs](streaming-api-event-hub.md)| Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Microsoft 365 Defender so konfigurieren, dass die [erweiterte Suche](../defender/advanced-hunting-overview.md) auf Event Hubs gestreamt wird.
[Streamen von Ereignissen auf Ihr Azure-Speicherkonto](streaming-api-storage.md)| Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Microsoft 365 Defender so konfigurieren, dass [advanced Hunting](advanced-hunting-overview.md) auf Ihr Azure-Speicherkonto gestreamt wird.


## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](../defender/advanced-hunting-overview.md)
- [Dokumentation zu Azure Event Hubs](/azure/event-hubs/)
- [Azure Storage Kontodokumentation](/azure/storage/common/storage-account-overview)
