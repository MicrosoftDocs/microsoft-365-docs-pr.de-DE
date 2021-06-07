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
ms.openlocfilehash: c8403dee11070dcf0825fad2502d8d21d54933fd
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782753"
---
# <a name="raw-data-streaming-api"></a>RAW-Datenstreaming-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Streamen Von Advanced Hunting-Ereignissen an Event Hubs und/oder Azure-Speicherkonten.


Microsoft Defender für Endpunkt unterstützt Streamingereignisse, die über [die erweiterte Suche](../defender/advanced-hunting-overview.md) für Event [Hubs](/azure/event-hubs/) und/oder [Azure-Speicherkonten](/azure/storage/common/storage-account-overview)verfügbar sind.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Thema | Beschreibung
:---|:---
[Streamen von Microsoft Defender für Endpunkt-Ereignissen an Azure Event Hubs](raw-data-export-event-hub.md)| Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Defender für Endpunkt so konfigurieren, dass [die erweiterte Suche](advanced-hunting-overview.md) auf Event Hubs gestreamt wird.
[Stream defender für Endpunkt-Ereignisse auf Ihr Azure-Speicherkonto](raw-data-export-storage.md)| Erfahren Sie, wie Sie die Streaming-API in Ihrem Mandanten aktivieren und Defender für Endpunkt so konfigurieren, dass [advanced Hunting](advanced-hunting-overview.md) auf Ihr Azure-Speicherkonto gestreamt wird.


## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Dokumentation zu Azure Event Hubs](/azure/event-hubs/)
- [Azure Storage Kontodokumentation](/azure/storage/common/storage-account-overview)