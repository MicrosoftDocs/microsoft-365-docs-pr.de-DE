---
title: Streamen von Microsoft Defender für Endpunkt-Ereignissen auf Ihr Storage Konto
description: Erfahren Sie, wie Sie Microsoft Defender für Endpunkt konfigurieren, um Advanced Hunting-Ereignisse auf Ihr Storage Konto zu streamen.
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
ms.openlocfilehash: 6be79e4991c9e20c46458eacd97ac0b7b7466bc8
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771657"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>Konfigurieren von Microsoft Defender für Endpunkt zum Streamen von Advanced Hunting-Ereignissen auf Ihr Storage Konto

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>Bevor Sie beginnen

1. Erstellen Sie ein [Storage Konto](/azure/storage/common/storage-account-overview) in Ihrem Mandanten.

2. Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu **Abonnements > Ihr Abonnement > Ressourcenanbieter > Registrieren bei Microsoft.insights.**

## <a name="enable-raw-data-streaming"></a>Aktivieren des Streamings von Rohdaten

1. Melden Sie sich beim [Microsoft Defender für Endpunkt-Portal](https://securitycenter.windows.com) als ***globaler Administrator** _ oder _*_Sicherheitsadministrator_**an.

2. Wechseln Sie auf Microsoft Defender Security Center zur [Seite "Datenexporteinstellungen".](https://securitycenter.windows.com/interoperability/dataexport)

3. Klicken Sie auf **"Datenexporteinstellungen hinzufügen".**

4. Wählen Sie einen Namen für ihre neuen Einstellungen aus.

5. Choose **Forward events to Azure Storage**.

6. Geben Sie Ihre **Storage Kontoressourcen-ID** ein. Um Ihre **Storage Kontoressourcen-ID** abzurufen, wechseln Sie zur Storage Kontoseite im [Azure-Portal](https://ms.portal.azure.com/) > Registerkarte "Eigenschaften", > kopieren Sie den Text unter **Storage Kontoressourcen-ID:**

   ![Abbildung der Event Hub-Ressourcen-ID1](images/storage-account-resource-id.png)

7. Wählen Sie die Ereignisse aus, die Sie streamen möchten, und klicken Sie auf **"Speichern".**

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Das Schema der Ereignisse im Storage Konto

- Für jeden Ereignistyp wird ein Blobcontainer erstellt: 

  ![Abbildung der Event Hub-Ressourcen-ID2](images/storage-account-event-schema.png)

- Das Schema jeder Zeile in einem Blob ist der folgende JSON-Code: 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- Jedes Blob enthält mehrere Zeilen.

- Jede Zeile enthält den Ereignisnamen, den Zeitpunkt, zu dem Defender für Endpunkt das Ereignis empfangen hat, den Mandanten, zu dem es gehört (Sie erhalten nur Ereignisse von Ihrem Mandanten) und das Ereignis im JSON-Format in einer Eigenschaft namens "properties".

- Weitere Informationen zum Schema von Microsoft Defender für Endpunkt-Ereignissen finden Sie in der [Übersicht über die erweiterte Suche.](advanced-hunting-overview.md)

- Bei der erweiterten Suche verfügt die **DeviceInfo-Tabelle** über eine Spalte mit dem Namen **MachineGroup,** die die Gruppe des Geräts enthält. Hier wird jedes Ereignis auch mit dieser Spalte versehen. Weitere Informationen finden Sie unter ["Gerätegruppen".](machine-groups.md)

## <a name="data-types-mapping"></a>Zuordnung von Datentypen

Gehen Sie folgendermaßen vor, um die Datentypen für unsere Ereigniseigenschaften abzurufen:

1. Melden Sie sich bei [Microsoft Defender Security Center an,](https://securitycenter.windows.com) und wechseln Sie zur [Seite "Erweiterte Suche".](https://securitycenter.windows.com/hunting-package)

2. Führen Sie die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis abzurufen: 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Hier ist ein Beispiel für das Device Info-Ereignis: 

  ![Abbildung der Event Hub-Ressourcen-ID3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Microsoft Defender für Endpunkt-Streaming-API](raw-data-export.md)
- [Streamen von Microsoft Defender für Endpunkt-Ereignissen auf Ihr Azure-Speicherkonto](raw-data-export-storage.md)
- [Azure Storage Kontodokumentation](/azure/storage/common/storage-account-overview)