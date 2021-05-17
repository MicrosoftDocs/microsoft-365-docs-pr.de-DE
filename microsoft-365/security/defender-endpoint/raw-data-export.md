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
# <a name="raw-data-streaming-api"></a>Raw Data Streaming API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Streamen von Advanced Hunting-Ereignissen an Event Hubs und/oder Azure-Speicherkonto.

Defender for Endpoint unterstützt das Streamen aller ereignisse, die über [die erweiterte](advanced-hunting-overview.md) Suche verfügbar sind, an [event hubs](https://docs.microsoft.com/azure/event-hubs/) und/oder [azure storage account](https://docs.microsoft.com/azure/event-hubs/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Thema | Beschreibung
:---|:---
[Streamen von Microsoft Defender for Endpoint-Ereignissen an Azure Event Hubs](raw-data-export-event-hub.md)| Erfahren Sie mehr über das Aktivieren der Streaming-API in Ihrem Mandanten und konfigurieren Sie Defender for Endpoint zum [Streamen von Advanced Hunting](advanced-hunting-overview.md) zu Event Hubs.
[Stream Defender for Endpoint-Ereignisse an Ihr Azure-Speicherkonto](raw-data-export-storage.md)| Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Defender for Endpoint so konfigurieren, dass [Advanced Hunting](advanced-hunting-overview.md) an Ihr Azure-Speicherkonto streamt.


## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Dokumentation zu Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs/)
- [Azure Storage Kontodokumentation](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
