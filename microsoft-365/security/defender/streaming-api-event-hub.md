---
title: Streamen von Microsoft 365 Defender-Ereignissen an den Azure Event Hub
description: Erfahren Sie, wie Sie Microsoft 365 Defender so konfigurieren, dass Advanced Hunting-Ereignisse an Ihren Event Hub gestreamt werden.
keywords: Rohdatenexport, Streaming-API, API, Azure Event Hub, Azure-Speicher, Speicherkonto, Erweiterte Suche, Freigabe von Rohdaten
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
ms.openlocfilehash: 6f5d04d35c8c4fec18e1a689c51ecbc32d416adf
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903816"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a><span data-ttu-id="3768b-104">Konfigurieren Microsoft 365 Defender zum Streamen von Advanced Hunting-Ereignissen auf Ihren Azure Event Hub</span><span class="sxs-lookup"><span data-stu-id="3768b-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Azure Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3768b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3768b-105">**Applies to:**</span></span>
- [<span data-ttu-id="3768b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3768b-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="3768b-107">Bevor Sie loslegen</span><span class="sxs-lookup"><span data-stu-id="3768b-107">Before you begin</span></span>

1. <span data-ttu-id="3768b-108">Erstellen Sie einen [Event Hub](/azure/event-hubs/) in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="3768b-108">Create an [Event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="3768b-109">Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu **Abonnements > Ihr Abonnement > Ressourcenanbieter > Registrieren bei Microsoft.Insights.**</span><span class="sxs-lookup"><span data-stu-id="3768b-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

3. <span data-ttu-id="3768b-110">Erstellen Sie einen Event Hub-Namespace, wechseln Sie zu **Event Hub > Hinzufügen,** und wählen Sie die Preisstufe, die Durchsatzeinheiten und die automatische Aufblasung aus, die für die erwartete Last geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="3768b-110">Create an Event Hub Namespace, go to **Event Hub > Add** and select the pricing tier, throughput units and Auto-Inflate appropriate for expected load.</span></span> <span data-ttu-id="3768b-111">Weitere Informationen finden Sie unter [Preise – Event Hub-| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="3768b-111">For more information, see [Pricing - Event Hub | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span></span>  

### <a name="add-contributor-permissions"></a><span data-ttu-id="3768b-112">Hinzufügen von Mitwirkendenberechtigungen</span><span class="sxs-lookup"><span data-stu-id="3768b-112">Add contributor permissions</span></span> 
<span data-ttu-id="3768b-113">Nachdem der Event Hub-Namespace erstellt wurde, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="3768b-113">Once the Event Hub namespace is created you will need to:</span></span>
1. <span data-ttu-id="3768b-114">Definieren Sie den Benutzer, der sich bei Microsoft 365 Defender als Mitwirkender anmeldet.</span><span class="sxs-lookup"><span data-stu-id="3768b-114">Define the user who will be logging into Microsoft 365 Defender as Contributor.</span></span>

2. <span data-ttu-id="3768b-115">Wenn Sie eine Verbindung mit einer Anwendung herstellen, fügen Sie den App-Registrierungsdienstprinzipal als Reader, Azure Event Hub-Datenempfänger, hinzu (dies kann auch auf Ressourcengruppen- oder Abonnementebene erfolgen).</span><span class="sxs-lookup"><span data-stu-id="3768b-115">If you are connecting to an application, add the App Registration Service Principal as Reader, Azure Event Hub Data Receiver (this can also be done at Resource Group or Subscription level).</span></span> 

    <span data-ttu-id="3768b-116">Wechseln Sie zu **Event hubs namespace > Access Control (IAM) > Hinzufügen** und Überprüfen unter **Rollenzuweisungen.**</span><span class="sxs-lookup"><span data-stu-id="3768b-116">Go to **Event hubs namespace > Access control (IAM) > Add** and verify under **Role assignments**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="3768b-117">Aktivieren des Streamings von Rohdaten</span><span class="sxs-lookup"><span data-stu-id="3768b-117">Enable raw data streaming</span></span>

1. <span data-ttu-id="3768b-118">Melden Sie sich beim [Microsoft 365 Defender Security Center](https://security.microsoft.com) als \* globaler **Administrator** _ oder _\*_Sicherheitsadministrator_\*\*an.</span><span class="sxs-lookup"><span data-stu-id="3768b-118">Log in to the [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="3768b-119">Wechseln Sie zur [Seite "Streaming-API-Einstellungen".](https://security.microsoft.com/settings/mtp_settings/raw_data_export)</span><span class="sxs-lookup"><span data-stu-id="3768b-119">Go to the [Streaming API settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span></span>

3. <span data-ttu-id="3768b-120">Klicken Sie auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="3768b-120">Click on **Add**.</span></span>

4. <span data-ttu-id="3768b-121">Wählen Sie einen Namen für ihre neuen Einstellungen aus.</span><span class="sxs-lookup"><span data-stu-id="3768b-121">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="3768b-122">Wählen Sie **"Forward"-Ereignisse an den Azure Event Hub aus.**</span><span class="sxs-lookup"><span data-stu-id="3768b-122">Choose **Forward events to Azure Event Hub**.</span></span>

6. <span data-ttu-id="3768b-123">Sie können auswählen, ob Sie die Ereignisdaten in einen einzelnen Event Hub exportieren oder jede Ereignistabelle in einen anderen Event Hub in Ihrem Event Hub-Namespace exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3768b-123">You can select if you want to export the event data to a single Event Hub, or to export each event table to a different event hub in your Event Hub namespace.</span></span> 

7. <span data-ttu-id="3768b-124">Um die Ereignisdaten in einen einzelnen Event Hub zu exportieren, geben Sie ihren **Event Hub-Namen** und Ihre **Event Hub-Ressourcen-ID** ein.</span><span class="sxs-lookup"><span data-stu-id="3768b-124">To export the event data to a single Event Hub, enter your **Event Hub name** and your **Event Hub resource ID**.</span></span>

   <span data-ttu-id="3768b-125">Um Ihre **Event Hub-Ressourcen-ID** abzurufen, wechseln Sie zur Azure Event Hub-Namespaceseite auf der Registerkarte ["Azure-Eigenschaften",](https://ms.portal.azure.com/)> kopieren Sie den Text unter  >   **"Ressourcen-ID":**</span><span class="sxs-lookup"><span data-stu-id="3768b-125">To get your **Event Hub resource ID**, go to your Azure Event Hub namespace page on [Azure](https://ms.portal.azure.com/) > **Properties** tab > copy the text under **Resource ID**:</span></span>

   ![Abbildung der Event Hub-Ressourcen-ID1](../defender-endpoint/images/event-hub-resource-id.png)

8. <span data-ttu-id="3768b-127">Wählen Sie die Ereignisse aus, die Sie streamen möchten, und klicken Sie auf **"Speichern".**</span><span class="sxs-lookup"><span data-stu-id="3768b-127">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hub"></a><span data-ttu-id="3768b-128">Das Schema der Ereignisse im Azure Event Hub</span><span class="sxs-lookup"><span data-stu-id="3768b-128">The schema of the events in Azure Event Hub</span></span>

```JSON
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

- <span data-ttu-id="3768b-129">Jede Event Hub-Nachricht in Azure Event Hub enthält eine Liste von Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="3768b-129">Each Event Hub message in Azure Event Hub contains list of records.</span></span>

- <span data-ttu-id="3768b-130">Jeder Datensatz enthält den Ereignisnamen, den Zeitpunkt, zu dem Microsoft 365 Defender das Ereignis empfangen hat, den Mandanten, zu dem es gehört (Sie erhalten nur Ereignisse von Ihrem Mandanten) und das Ereignis im JSON-Format in einer Eigenschaft namens **"Properties".**</span><span class="sxs-lookup"><span data-stu-id="3768b-130">Each record contains the event name, the time Microsoft 365 Defender received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="3768b-131">Weitere Informationen zum Schema von Microsoft 365 Defender-Ereignissen finden Sie unter ["Erweiterte Suche" (Übersicht).](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3768b-131">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="3768b-132">Bei der erweiterten Suche verfügt die **DeviceInfo-Tabelle** über eine Spalte mit dem Namen **MachineGroup,** die die Gruppe des Geräts enthält.</span><span class="sxs-lookup"><span data-stu-id="3768b-132">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="3768b-133">Hier wird jedes Ereignis auch mit dieser Spalte versehen.</span><span class="sxs-lookup"><span data-stu-id="3768b-133">Here every event will be decorated with this column as well.</span></span> 




## <a name="data-types-mapping"></a><span data-ttu-id="3768b-134">Zuordnung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="3768b-134">Data types mapping</span></span>

<span data-ttu-id="3768b-135">Gehen Sie folgendermaßen vor, um die Datentypen für Ereigniseigenschaften abzurufen:</span><span class="sxs-lookup"><span data-stu-id="3768b-135">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="3768b-136">Melden Sie sich bei [Microsoft 365 Security Center](https://security.microsoft.com) an, und wechseln Sie zur Seite ["Erweiterte Suche".](https://security.microsoft.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="3768b-136">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="3768b-137">Führen Sie die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis abzurufen:</span><span class="sxs-lookup"><span data-stu-id="3768b-137">Run the following query to get the data types mapping for each event:</span></span>
 
   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="3768b-138">Hier ist ein Beispiel für das Device Info-Ereignis:</span><span class="sxs-lookup"><span data-stu-id="3768b-138">Here is an example for Device Info event:</span></span> 

  ![Abbildung der Event Hub-Ressourcen-ID2](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="3768b-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3768b-140">Related topics</span></span>
- [<span data-ttu-id="3768b-141">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="3768b-141">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3768b-142">Microsoft 365 Defender-Streaming-API</span><span class="sxs-lookup"><span data-stu-id="3768b-142">Microsoft 365 Defender streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="3768b-143">Streamen Microsoft 365 Defender-Ereignisse auf Ihr Azure-Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="3768b-143">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="3768b-144">Dokumentation zum Azure Event Hub</span><span class="sxs-lookup"><span data-stu-id="3768b-144">Azure Event Hub documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="3768b-145">Behandeln von Konnektivitätsproblemen – Azure Event Hub</span><span class="sxs-lookup"><span data-stu-id="3768b-145">Troubleshoot connectivity issues - Azure Event Hub</span></span>](/azure/event-hubs/troubleshooting-guide)
