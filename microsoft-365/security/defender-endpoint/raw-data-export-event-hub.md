---
title: Streamen von Microsoft Defender für Endpunkt-Ereignissen an Azure Event Hubs
description: Erfahren Sie, wie Sie Microsoft Defender für Endpunkt so konfigurieren, dass Advanced Hunting-Ereignisse auf Ihren Event Hub gestreamt werden.
keywords: Rohdatenexport, Streaming-API, API, Azure Event Hubs, Azure-Speicher, Speicherkonto, Erweiterte Suche, Freigabe von Rohdaten
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
ms.openlocfilehash: 8985a40c99ad4db9710dfbf9805d537a921f6c96
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780165"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Konfigurieren von Microsoft Defender für Endpunkt zum Streamen von Advanced Hunting-Ereignissen auf Ihre Azure Event Hubs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>Bevor Sie beginnen

1. Erstellen Sie einen [Event Hub](/azure/event-hubs/) in Ihrem Mandanten.

2. Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu **Abonnements > Ihr Abonnement > Ressourcenanbieter > Registrieren bei **Microsoft.insights".

## <a name="enable-raw-data-streaming"></a>Aktivieren des Streamings von Rohdaten

1. Melden Sie sich beim [Microsoft Defender Security Center](https://securitycenter.windows.com) als ***globaler Administrator** _ oder _*_Sicherheitsadministrator_** an.

2. Wechseln Sie auf Microsoft Defender Security Center zur [Seite "Datenexporteinstellungen".](https://securitycenter.windows.com/interoperability/dataexport)

3. Klicken Sie auf **"Datenexporteinstellungen hinzufügen".**

4. Wählen Sie einen Namen für ihre neuen Einstellungen aus.

5. Wählen Sie **"Forward"-Ereignisse an Azure Event Hubs aus.**

6. Geben Sie den Namen der **Event Hubs** und ihre **Event Hubs-Ressourcen-ID** ein.

   Um Ihre **Event Hubs-Ressourcen-ID** abzurufen, wechseln Sie zur Azure Event Hubs-Namespaceseite auf der Registerkarte ["Azure](https://ms.portal.azure.com/) > Eigenschaften", > kopieren Sie den Text unter **"Ressourcen-ID":**

   ![Abbildung der Event Hub-Ressourcen-ID1](images/event-hub-resource-id.png)

7. Wählen Sie die Ereignisse aus, die Sie streamen möchten, und klicken Sie auf **"Speichern".**

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Das Schema der Ereignisse in Azure Event Hubs

```
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- Jede Event Hub-Nachricht in Azure Event Hubs enthält eine Liste von Datensätzen.

- Jeder Datensatz enthält den Ereignisnamen, den Zeitpunkt, zu dem Microsoft Defender für Endpunkt das Ereignis empfangen hat, den Mandanten, zu dem es gehört (Sie erhalten nur Ereignisse von Ihrem Mandanten) und das Ereignis im JSON-Format in einer Eigenschaft namens **"Eigenschaften".**

- Weitere Informationen zum Schema von Microsoft Defender für Endpunkt-Ereignissen finden Sie in der [Übersicht über die erweiterte Suche.](advanced-hunting-overview.md)

- Bei der erweiterten Suche verfügt die **DeviceInfo-Tabelle** über eine Spalte mit dem Namen **MachineGroup,** die die Gruppe des Geräts enthält. Hier wird jedes Ereignis auch mit dieser Spalte versehen. Weitere Informationen finden Sie unter ["Gerätegruppen".](machine-groups.md)

## <a name="data-types-mapping"></a>Zuordnung von Datentypen

Gehen Sie folgendermaßen vor, um die Datentypen für Ereigniseigenschaften abzurufen:

1. Melden Sie sich bei [Microsoft Defender Security Center an,](https://securitycenter.windows.com) und wechseln Sie zur [Seite "Erweiterte Suche".](https://securitycenter.windows.com/hunting-package)

2. Führen Sie die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis abzurufen:
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Hier ist ein Beispiel für das Device Info-Ereignis: 

  ![Abbildung der Event Hub-Ressourcen-ID2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Microsoft Defender für Endpunkt-Streaming-API](raw-data-export.md)
- [Streamen von Microsoft Defender für Endpunkt-Ereignissen auf Ihr Azure-Speicherkonto](raw-data-export-storage.md)
- [Dokumentation zu Azure Event Hubs](/azure/event-hubs/)
- [Behandeln von Konnektivitätsproblemen – Azure Event Hubs](/azure/event-hubs/troubleshooting-guide)