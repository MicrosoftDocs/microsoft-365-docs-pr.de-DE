---
title: Streamen Microsoft 365 Defender-Ereignisse auf Azure Event Hubs
description: Erfahren Sie, wie Sie Microsoft 365 Defender so konfigurieren, dass Advanced Hunting-Ereignisse auf Ihren Event Hub gestreamt werden.
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
ms.openlocfilehash: e2ede14d6b93a61bc232d42b5926c6adb7c9585f
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736324"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="3b438-104">Konfigurieren Microsoft 365 Defender zum Streamen von Advanced Hunting-Ereignissen auf Ihre Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="3b438-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3b438-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3b438-105">**Applies to:**</span></span>
- [<span data-ttu-id="3b438-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b438-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="3b438-107">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="3b438-107">Before you begin:</span></span>

1. <span data-ttu-id="3b438-108">Erstellen Sie einen [Event Hub](/azure/event-hubs/) in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="3b438-108">Create an [event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="3b438-109">Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu **Abonnements > Ihr Abonnement > Ressourcenanbieter > Registrieren bei Microsoft.Insights.**</span><span class="sxs-lookup"><span data-stu-id="3b438-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

3. <span data-ttu-id="3b438-110">Erstellen Sie einen Event Hub-Namespace, wechseln Sie zu **Event Hubs > Hinzufügen,** und wählen Sie die Preisstufe, die Durchsatzeinheiten und die automatische Aufblasung aus, die für die erwartete Last geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="3b438-110">Create an Event Hub Namespace, go to **Event Hubs > Add** and select the pricing tier, throughput units and Auto-Inflate appropriate for expected load.</span></span> <span data-ttu-id="3b438-111">Weitere Informationen finden Sie unter [Preise – Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="3b438-111">For more information, see [Pricing - Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span></span>  

4. <span data-ttu-id="3b438-112">Nachdem der Event Hub-Namespace erstellt wurde, müssen Sie den App-Registrierungsdienstprinzipal als Leser, Azure Event Hubs-Datenempfänger und den Benutzer hinzufügen, der sich bei Microsoft 365 Defender als Mitwirkender anmeldet (dies kann auch auf Ressourcengruppen- oder Abonnementebene erfolgen).</span><span class="sxs-lookup"><span data-stu-id="3b438-112">Once the event hub namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span> <span data-ttu-id="3b438-113">Wechseln Sie zu **Event Hubs Namespace > Access Control (IAM) > Hinzufügen** und Überprüfen unter **Rollenzuweisungen.**</span><span class="sxs-lookup"><span data-stu-id="3b438-113">Go to **Event hubs namespace > Access control (IAM) > Add** and verify under **Role assignements**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="3b438-114">Aktivieren Des Streamings von Rohdaten:</span><span class="sxs-lookup"><span data-stu-id="3b438-114">Enable raw data streaming:</span></span>

1. <span data-ttu-id="3b438-115">Melden Sie sich beim [Microsoft 365 Defender Security Center](https://security.microsoft.com) als \* globaler **Administrator** _ oder _\*_Sicherheitsadministrator_\*\*an.</span><span class="sxs-lookup"><span data-stu-id="3b438-115">Log in to the [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="3b438-116">Wechseln Sie zur [Seite "Datenexporteinstellungen".](https://security.microsoft.com/settings/mtp_settings/raw_data_export)</span><span class="sxs-lookup"><span data-stu-id="3b438-116">Go to the [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span></span>

3. <span data-ttu-id="3b438-117">Klicken Sie auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="3b438-117">Click on **Add**.</span></span>

4. <span data-ttu-id="3b438-118">Wählen Sie einen Namen für ihre neuen Einstellungen aus.</span><span class="sxs-lookup"><span data-stu-id="3b438-118">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="3b438-119">Wählen Sie **"Forward"-Ereignisse an Azure Event Hubs aus.**</span><span class="sxs-lookup"><span data-stu-id="3b438-119">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="3b438-120">Sie können auswählen, ob Sie die Ereignisdaten in einen einzelnen Event Hub exportieren oder jede Ereignistabelle in einen anderen geraden Hub im Event Hub-Namespace exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3b438-120">You can select if you want to export the event data to a single event hub, or to export each event table to a different even hub in your event hub namespace.</span></span> 

7. <span data-ttu-id="3b438-121">Um die Ereignisdaten in einen einzelnen Event Hub zu exportieren, geben Sie ihren **Event Hub-Namen** und Ihre **Event Hub-Ressourcen-ID** ein.</span><span class="sxs-lookup"><span data-stu-id="3b438-121">To export the event data to a single event hub, Enter your **Event Hub name** and your **Event Hub resource ID**.</span></span>

   <span data-ttu-id="3b438-122">Um Ihre **Event Hubs-Ressourcen-ID** abzurufen, wechseln Sie zur Azure Event Hubs-Namespaceseite auf der Registerkarte ["Azure-Eigenschaften",](https://ms.portal.azure.com/)> kopieren Sie den Text unter  >   **"Ressourcen-ID":**</span><span class="sxs-lookup"><span data-stu-id="3b438-122">To get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > **Properties** tab > copy the text under **Resource ID**:</span></span>

   ![Abbildung der Event Hub-Ressourcen-ID1](images/event-hub-resource-id.png)

8. <span data-ttu-id="3b438-124">Wählen Sie die Ereignisse aus, die Sie streamen möchten, und klicken Sie auf **"Speichern".**</span><span class="sxs-lookup"><span data-stu-id="3b438-124">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="3b438-125">Das Schema der Ereignisse in Azure Event Hubs:</span><span class="sxs-lookup"><span data-stu-id="3b438-125">The schema of the events in Azure Event Hubs:</span></span>

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

- <span data-ttu-id="3b438-126">Jede Event Hub-Nachricht in Azure Event Hubs enthält eine Liste von Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="3b438-126">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="3b438-127">Jeder Datensatz enthält den Ereignisnamen, den Zeitpunkt, zu dem Microsoft 365 Defender das Ereignis empfangen hat, den Mandanten, zu dem es gehört (Sie erhalten nur Ereignisse von Ihrem Mandanten) und das Ereignis im JSON-Format in einer Eigenschaft namens **"Properties".**</span><span class="sxs-lookup"><span data-stu-id="3b438-127">Each record contains the event name, the time Microsoft 365 Defender received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="3b438-128">Weitere Informationen zum Schema von Microsoft 365 Defender-Ereignissen finden Sie unter ["Erweiterte Suche" (Übersicht).](../defender/advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3b438-128">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="3b438-129">Bei der erweiterten Suche verfügt die **DeviceInfo-Tabelle** über eine Spalte mit dem Namen **MachineGroup,** die die Gruppe des Geräts enthält.</span><span class="sxs-lookup"><span data-stu-id="3b438-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="3b438-130">Hier wird jedes Ereignis auch mit dieser Spalte versehen.</span><span class="sxs-lookup"><span data-stu-id="3b438-130">Here every event will be decorated with this column as well.</span></span> 

9. <span data-ttu-id="3b438-131">Um jede Ereignistabelle in einen anderen Event Hub zu exportieren, lassen Sie einfach den Namen des **Event Hub** leer, und Microsoft 365 Defender übernimmt den Rest.</span><span class="sxs-lookup"><span data-stu-id="3b438-131">To export each event table to a different event hub, simply leave the **Event hub name** empty, and Microsoft 365 Defender will do the rest.</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="3b438-132">Zuordnung von Datentypen:</span><span class="sxs-lookup"><span data-stu-id="3b438-132">Data types mapping:</span></span>

<span data-ttu-id="3b438-133">Gehen Sie folgendermaßen vor, um die Datentypen für Ereigniseigenschaften abzurufen:</span><span class="sxs-lookup"><span data-stu-id="3b438-133">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="3b438-134">Melden Sie sich bei [Microsoft 365 Security Center](https://security.microsoft.com) an, und wechseln Sie zur Seite ["Erweiterte Suche".](https://security.microsoft.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="3b438-134">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="3b438-135">Führen Sie die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis abzurufen:</span><span class="sxs-lookup"><span data-stu-id="3b438-135">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="3b438-136">Hier ist ein Beispiel für das Device Info-Ereignis:</span><span class="sxs-lookup"><span data-stu-id="3b438-136">Here is an example for Device Info event:</span></span> 

  ![Abbildung der Event Hub-Ressourcen-ID2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="3b438-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3b438-138">Related topics</span></span>
- [<span data-ttu-id="3b438-139">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="3b438-139">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="3b438-140">Microsoft 365 Defender-Streaming-API</span><span class="sxs-lookup"><span data-stu-id="3b438-140">Microsoft 365 Defender streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="3b438-141">Streamen Microsoft 365 Defender-Ereignisse auf Ihr Azure-Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="3b438-141">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="3b438-142">Dokumentation zu Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="3b438-142">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="3b438-143">Behandeln von Konnektivitätsproblemen – Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="3b438-143">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](/azure/event-hubs/troubleshooting-guide)
