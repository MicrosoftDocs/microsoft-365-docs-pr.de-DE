---
title: Streamen Microsoft 365 Defender Ereignisse an Ihr Storage Konto
description: Erfahren Sie, wie Sie Microsoft 365 Defender konfigurieren, um Ereignisse der erweiterten Suche in Ihr Storage Konto zu streamen.
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
ms.openlocfilehash: 656387e60bac90c7e9de4852779948dabce0efe3
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029657"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Konfigurieren Microsoft 365 Defender zum Streamen von Advanced Hunting-Ereignissen auf Ihr Storage Konto

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>Bevor Sie beginnen

1. Erstellen Sie ein [Storage Konto](/azure/storage/common/storage-account-overview) in Ihrem Mandanten.

2. Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu **Abonnements > Ihr Abonnement > Ressourcenanbieter > Registrieren bei Microsoft.Insights.**

## <a name="enable-raw-data-streaming"></a>Aktivieren des Streamings von Rohdaten

1. Melden Sie sich beim Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ) als * globaler **Administrator** _ oder _*_Sicherheitsadministrator_**an.

2. Wechseln Sie zu **Einstellungen** \> **Microsoft 365 Defender** \> **Streaming-API.** Um direkt zur Seite der **Streaming-API** zu wechseln, verwenden Sie <https://security.microsoft.com/settings/mtp_settings/raw_data_export> .

3. Klicken Sie auf **Hinzufügen**.

4. Konfigurieren Sie im angezeigten Flyout **"Neue Streaming-API-Einstellungen hinzufügen"** die folgenden Einstellungen:
   1. **Name:** Wählen Sie einen Namen für ihre neuen Einstellungen aus.
   2. Select **Forward events to Azure Storage**.
   3. Geben Sie im angezeigten **Feld Storage Kontoressourcen-ID** Ihre **Storage Kontoressourcen-ID** ein. Um Ihre **Storage Kontoressourcen-ID** abzurufen, öffnen Sie das Azure-Portal unter <https://portal.azure.com> , klicken Sie auf Storage **Konten** zur Registerkarte \> Eigenschaften \> wechseln, kopieren Sie den Text unter Storage **Kontoressourcen-ID.**

      ![Abbildung der Event Hub-Ressourcen-ID1](../defender-endpoint/images/storage-account-resource-id.png)

   4. Wählen Sie im Flyout **"Neue Streaming-API-Einstellungen hinzufügen"** die **Ereignistypen aus,** die Sie streamen möchten.

   Wenn Sie fertig sind, klicken Sie auf **"Absenden".**

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Das Schema der Ereignisse im Storage Konto

- Für jeden Ereignistyp wird ein Blobcontainer erstellt:

  ![Abbildung der Event Hub-Ressourcen-ID2](../defender-endpoint/images/storage-account-event-schema.png)

- Das Schema jeder Zeile in einem Blob ist der folgende JSON-Code:

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- Jedes Blob enthält mehrere Zeilen.

- Jede Zeile enthält den Ereignisnamen, den Zeitpunkt, zu dem Defender für Endpunkt das Ereignis empfangen hat, den Mandanten, zu dem es gehört (Sie erhalten nur Ereignisse von Ihrem Mandanten) und das Ereignis im JSON-Format in einer Eigenschaft namens "properties".

- Weitere Informationen zum Schema von Microsoft 365 Defender-Ereignissen finden Sie in der [Übersicht über die erweiterte Suche.](../defender/advanced-hunting-overview.md)

## <a name="data-types-mapping"></a>Zuordnung von Datentypen

Gehen Sie folgendermaßen vor, um die Datentypen für unsere Ereigniseigenschaften abzurufen:

1. Melden Sie sich beim Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ) an, und wechseln Sie zur  \> **erweiterten Suche**. Verwenden Sie <security.microsoft.com/advanced-hunting>, um direkt zur Seite **"Erweiterte Suche"** zu gelangen.

2. Führen Sie auf der Registerkarte **"Abfrage"** die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis abzurufen:

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- Hier ist ein Beispiel für das Device Info-Ereignis:

  ![Abbildung der Event Hub-Ressourcen-ID3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über die erweiterte Suche](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender Streaming-API](streaming-api.md)
- [Streamen Microsoft 365 Defender Ereignisse auf Ihr Azure-Speicherkonto](streaming-api-storage.md)
- [Azure Storage Kontodokumentation](/azure/storage/common/storage-account-overview)
