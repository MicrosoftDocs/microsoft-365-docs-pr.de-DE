---
title: Streamen Microsoft 365 Defender-Ereignisse auf Azure Event Hubs
description: Erfahren Sie, wie Sie Microsoft 365 Defender so konfigurieren, dass Advanced Hunting-Ereignisse an Ihren Event Hub gestreamt werden.
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
ms.openlocfilehash: 82a2e5cc3555dd3f444e7a1fc1b7126603bea489
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778221"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Konfigurieren Microsoft 365 Defender zum Streamen von Advanced Hunting-Ereignissen auf Ihre Azure Event Hubs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



## <a name="before-you-begin"></a>Bevor Sie beginnen:

1. Erstellen Sie einen [Event Hub](/azure/event-hubs/) in Ihrem Mandanten.

2. Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu **Abonnements > Ihr Abonnement > Ressourcenanbieter > Registrieren bei Microsoft.Insights.**

3. Erstellen Sie einen Event Hub-Namespace, wechseln Sie zu **Event Hubs > Hinzufügen,** und wählen Sie die Preisstufe, die Durchsatzeinheiten und die automatische Aufblasung aus, die für die erwartete Last geeignet sind. Weitere Informationen finden Sie unter [Preise – Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).  

4. Nachdem der Event Hub-Namespace erstellt wurde, müssen Sie den App-Registrierungsdienstprinzipal als Leser, Azure Event Hubs-Datenempfänger und den Benutzer hinzufügen, der sich bei Microsoft 365 Defender als Mitwirkender anmeldet (dies kann auch auf Ressourcengruppen- oder Abonnementebene erfolgen). Wechseln Sie zu **Event Hubs Namespace > Access Control (IAM) > Hinzufügen** und Überprüfen unter **Rollenzuweisungen.**

## <a name="enable-raw-data-streaming"></a>Aktivieren Des Streamings von Rohdaten:

1. Melden Sie sich beim [Microsoft 365 Defender Security Center](https://security.microsoft.com) als * globaler **Administrator** _ oder _*_Sicherheitsadministrator_**an.

2. Wechseln Sie zur [Seite "Datenexporteinstellungen".](https://security.microsoft.com/settings/mtp_settings/raw_data_export)

3. Klicken Sie auf **"Hinzufügen".**

4. Wählen Sie einen Namen für ihre neuen Einstellungen aus.

5. Wählen Sie **"Forward"-Ereignisse an Azure Event Hubs aus.**

6. Sie können auswählen, ob Sie die Ereignisdaten in einen einzelnen Event Hub exportieren oder jede Ereignistabelle in einen anderen geraden Hub im Event Hub-Namespace exportieren möchten. 

7. Um die Ereignisdaten in einen einzelnen Event Hub zu exportieren, geben Sie ihren **Event Hub-Namen** und Ihre **Event Hub-Ressourcen-ID** ein.

   Um Ihre **Event Hubs-Ressourcen-ID** abzurufen, wechseln Sie zur Azure Event Hubs-Namespaceseite auf der Registerkarte ["Azure-Eigenschaften",](https://ms.portal.azure.com/)> kopieren Sie den Text unter  >   **"Ressourcen-ID":**

   ![Abbildung der Event Hub-Ressourcen-ID1](images/event-hub-resource-id.png)

8. Wählen Sie die Ereignisse aus, die Sie streamen möchten, und klicken Sie auf **"Speichern".**

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Das Schema der Ereignisse in Azure Event Hubs:

```
{
    "records": [
                    {
                        "time": "<The time Microsoft 365 Defender received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- Jede Event Hub-Nachricht in Azure Event Hubs enthält eine Liste von Datensätzen.

- Jeder Datensatz enthält den Ereignisnamen, den Zeitpunkt, zu dem Microsoft 365 Defender das Ereignis empfangen hat, den Mandanten, zu dem er gehört (Sie erhalten nur Ereignisse von Ihrem Mandanten) und das Ereignis im JSON-Format in einer Eigenschaft namens **"Properties".**

- Weitere Informationen zum Schema von Microsoft 365 Defender-Ereignissen finden Sie in der [Übersicht über die erweiterte Suche.](../defender/advanced-hunting-overview.md)

- Bei der erweiterten Suche verfügt die **DeviceInfo-Tabelle** über eine Spalte mit dem Namen **MachineGroup,** die die Gruppe des Geräts enthält. Hier wird jedes Ereignis auch mit dieser Spalte versehen. 

9. Um jede Ereignistabelle in einen anderen Event Hub zu exportieren, lassen Sie einfach den Namen des **Event Hub** leer, und Microsoft 365 Defender übernimmt den Rest.


## <a name="data-types-mapping"></a>Zuordnung von Datentypen:

Gehen Sie folgendermaßen vor, um die Datentypen für Ereigniseigenschaften abzurufen:

1. Melden Sie sich bei [Microsoft 365 Security Center](https://security.microsoft.com) an, und wechseln Sie zur Seite ["Erweiterte Suche".](https://security.microsoft.com/hunting-package)

2. Führen Sie die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis abzurufen:
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Hier ist ein Beispiel für das Device Info-Ereignis: 

  ![Abbildung der Event Hub-Ressourcen-ID2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender-Streaming-API](raw-data-export.md)
- [Streamen Microsoft 365 Defender-Ereignisse auf Ihr Azure-Speicherkonto](raw-data-export-storage.md)
- [Dokumentation zu Azure Event Hubs](/azure/event-hubs/)
- [Behandeln von Konnektivitätsproblemen – Azure Event Hubs](/azure/event-hubs/troubleshooting-guide)
