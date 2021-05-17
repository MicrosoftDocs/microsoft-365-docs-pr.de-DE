---
title: Streamen von Microsoft Defender for Endpoint-Ereignissen an Azure Event Hubs
description: Erfahren Sie, wie Sie Microsoft Defender for Endpoint zum Streamen von Advanced Hunting-Ereignissen an Ihren Event Hub konfigurieren.
keywords: Rohdatenexport, Streaming-API, API, Azure Event Hubs, Azure-Speicher, Speicherkonto, Erweiterte Suche, Unformatierte Datenfreigabe
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
ms.openlocfilehash: df305c9fcc7fb9249f2387567600adb899f8c49a
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861047"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Konfigurieren von Microsoft Defender for Endpoint zum Streamen von Advanced Hunting-Ereignissen an Ihre Azure Event Hubs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>Bevor Sie beginnen:

1. Erstellen Sie [einen Ereignishub](https://docs.microsoft.com/azure/event-hubs/) in Ihrem Mandanten.

2. Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu **Abonnements > Ihr Abonnement > Ressourcenanbieter > Registrieren bei **Microsoft.insights**.

## <a name="enable-raw-data-streaming"></a>Aktivieren des Streamings von Rohdaten:

1. Melden Sie sich beim [Microsoft Defender Security Center](https://securitycenter.windows.com) als ***Globaler Administrator** _ oder _*_Sicherheitsadministrator_** an.

2. Wechseln Sie zur [Seite Datenexporteinstellungen](https://securitycenter.windows.com/interoperability/dataexport) auf Microsoft Defender Security Center.

3. Klicken Sie auf **Datenexporteinstellungen hinzufügen.**

4. Wählen Sie einen Namen für Ihre neuen Einstellungen aus.

5. Wählen **Sie Weiterleiten von Ereignissen an Azure Event Hubs aus.**

6. Geben Sie **ihren Event Hubs-Namen** und Ihre **Event Hubs-Ressourcen-ID ein.**

   Um Ihre **Event Hubs-Ressourcen-ID** zu erhalten, wechseln Sie zu Ihrer Azure Event Hubs-Namespaceseite auf der Registerkarte Eigenschaften von [Azure](https://ms.portal.azure.com/) > > kopieren Sie den Text unter **Ressourcen-ID**:

   ![Abbildung der Event Hub-Ressource Id1](images/event-hub-resource-id.png)

7. Wählen Sie die Ereignisse aus, die Sie streamen möchten, und klicken Sie auf **Speichern.**

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Das Schema der Ereignisse in Azure Event Hubs:

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

- Jede Ereignishubnachricht in Azure Event Hubs enthält eine Liste von Datensätzen.

- Jeder Datensatz enthält den Ereignisnamen, den Zeitpunkt, zu dem Microsoft Defender for Endpoint das Ereignis empfangen hat, den Mandanten, zu dem er gehört (Sie erhalten nur Ereignisse von Ihrem Mandanten), und das Ereignis im JSON-Format in einer Eigenschaft namens "**properties**".

- Weitere Informationen zum Schema von Microsoft Defender for Endpoint-Ereignissen finden Sie unter [Advanced Hunting overview](advanced-hunting-overview.md).

- In Advanced Hunting verfügt **die DeviceInfo-Tabelle** über eine Spalte mit dem Namen **MachineGroup,** die die Gruppe des Geräts enthält. Hier wird jedes Ereignis auch mit dieser Spalte eingerichtet. Weitere [Informationen finden Sie](machine-groups.md) unter Gerätegruppen.

## <a name="data-types-mapping"></a>Datentypzuordnung:

Gehen Sie wie folgt vor, um die Datentypen für Ereigniseigenschaften zu erhalten:

1. Melden Sie sich bei [Microsoft Defender Security Center](https://securitycenter.windows.com) an, und wechseln Sie zur [Seite Erweiterte Suche](https://securitycenter.windows.com/hunting-package).

2. Führen Sie die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis zu erhalten:
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Im Folgenden finden Sie ein Beispiel für ein Device Info-Ereignis: 

  ![Abbildung der Event Hub-Ressource Id2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Microsoft Defender for Endpoint-Streaming-API](raw-data-export.md)
- [Streamen von Microsoft Defender for Endpoint-Ereignissen an Ihr Azure-Speicherkonto](raw-data-export-storage.md)
- [Dokumentation zu Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs/)
- [Problembehandlung bei Konnektivitätsproblemen – Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
