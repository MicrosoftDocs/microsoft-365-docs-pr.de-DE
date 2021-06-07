---
title: Streamen Microsoft 365 Defender-Ereignisse auf Ihr Storage Konto
description: Erfahren Sie, wie Sie Microsoft 365 Defender so konfigurieren, dass Advanced Hunting-Ereignisse in Ihr Storage-Konto gestreamt werden.
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
ms.openlocfilehash: a4e706bbb2246bd0629db721373ffcd4164d123d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772505"
---
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Konfigurieren von Microsoft 365 Defender zum Streamen von Advanced Hunting-Ereignissen auf Ihr Storage Konto

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a>Bevor Sie beginnen:

1. Erstellen Sie ein [Storage Konto](/azure/storage/common/storage-account-overview) in Ihrem Mandanten.

2. Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu **Abonnements > Ihr Abonnement > Ressourcenanbieter > Registrieren bei Microsoft.Insights.**

## <a name="enable-raw-data-streaming"></a>Aktivieren Des Streamings von Rohdaten:

1. Melden Sie sich bei [Microsoft 365 Defender Security Center](https://security.microsoft.com) als * globaler **Administrator** _ oder _*_Sicherheitsadministrator_**an.

2. Wechseln Sie zur [Seite "Datenexporteinstellungen"](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.

3. Klicken Sie auf **"Datenexporteinstellungen hinzufügen".**

4. Wählen Sie einen Namen für ihre neuen Einstellungen aus.

5. Wählen Sie **"Forward"-Ereignisse aus, um Azure Storage .**

6. Geben Sie Ihre **Storage Kontoressourcen-ID** ein. Um Ihre **Storage Kontoressourcen-ID** abzurufen, wechseln Sie zur Storage Kontoseite im [Azure-Portal](https://ms.portal.azure.com/) > Registerkarte "Eigenschaften", > kopieren Sie den Text unter **Storage Kontoressourcen-ID:**

   ![Abbildung der Event Hub-Ressourcen-ID1](../defender-endpoint/images/storage-account-resource-id.png)

7. Wählen Sie die Ereignisse aus, die Sie streamen möchten, und klicken Sie auf **"Speichern".**

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Das Schema der Ereignisse im Storage-Konto:

- Für jeden Ereignistyp wird ein Blobcontainer erstellt: 

  ![Abbildung der Event Hub-Ressourcen-ID2](../defender-endpoint/images/storage-account-event-schema.png)

- Das Schema jeder Zeile in einem Blob ist der folgende JSON-Code: 

  ```
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

1. Melden Sie sich bei [Microsoft 365 Security Center](https://security.microsoft.com) an, und wechseln Sie zur Seite ["Erweiterte Suche".](https://security.microsoft.com/hunting-package)

2. Führen Sie die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis abzurufen: 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Hier ist ein Beispiel für das Device Info-Ereignis: 

  ![Abbildung der Event Hub-Ressourcen-ID3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender Streaming-API](streaming-api.md)
- [Streamen Microsoft 365 Defender-Ereignisse auf Ihr Azure-Speicherkonto](streaming-api-storage.md)
- [Azure Storage Kontodokumentation](/azure/storage/common/storage-account-overview)
