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
# <a name="streaming-api"></a>Streaming-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Streamen von Advanced Hunting-Ereignissen an Event Hubs und/oder Azure-Speicherkonto.

Microsoft 365 Defender unterstützt das Streaming aller ereignisse, die über [die erweiterte Suche](../defender/advanced-hunting-overview.md) verfügbar sind, an Event [Hubs](/azure/event-hubs/) und/oder [azure speicherkonto](/azure/event-hubs/).



## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Thema | Beschreibung
:---|:---
[Streamen von Ereignissen an Azure Event Hubs](raw-data-export-event-hub.md)| Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Microsoft 365 Defender so konfigurieren, dass [Advanced Hunting](../defender/advanced-hunting-overview.md) zu Event Hubs gestreamt wird.
[Streamen von Ereignissen an Ihr Azure-Speicherkonto](raw-data-export-storage.md)| Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Microsoft 365 Defender so konfigurieren, dass [Advanced Hunting](../defender/advanced-hunting-overview.md) auf Ihr Azure-Speicherkonto gestreamt wird.


## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](../defender/advanced-hunting-overview.md)
- [Dokumentation zu Azure Event Hubs](/azure/event-hubs/)
- [Azure Storage Kontodokumentation](/azure/storage/common/storage-account-overview)
