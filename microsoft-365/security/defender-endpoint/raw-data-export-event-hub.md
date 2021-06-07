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
ms.custom: api
ms.openlocfilehash: 03b19f3af3c140729db2b5d51bb7ae11d906497b
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771645"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="c4843-104">Konfigurieren von Microsoft Defender für Endpunkt zum Streamen von Advanced Hunting-Ereignissen auf Ihre Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="c4843-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c4843-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c4843-105">**Applies to:**</span></span>

- [<span data-ttu-id="c4843-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c4843-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="c4843-107">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="c4843-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c4843-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c4843-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="c4843-109">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="c4843-109">Before you begin</span></span>

1. <span data-ttu-id="c4843-110">Erstellen Sie einen [Event Hub](/azure/event-hubs/) in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="c4843-110">Create an [event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="c4843-111">Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu \*\*Abonnements > Ihr Abonnement > Ressourcenanbieter > Registrieren bei \*\*Microsoft.insights".</span><span class="sxs-lookup"><span data-stu-id="c4843-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to \*\*Subscriptions > Your subscription > Resource Providers > Register to \*\*Microsoft.insights\*\*\*\*.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="c4843-112">Aktivieren des Streamings von Rohdaten</span><span class="sxs-lookup"><span data-stu-id="c4843-112">Enable raw data streaming</span></span>

1. <span data-ttu-id="c4843-113">Melden Sie sich beim [Microsoft Defender Security Center](https://securitycenter.windows.com) als ***globaler Administrator** _ oder _*_Sicherheitsadministrator_\*\* an.</span><span class="sxs-lookup"><span data-stu-id="c4843-113">Log in to the [Microsoft Defender Security Center](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="c4843-114">Wechseln Sie zur [Seite "Datenexporteinstellungen"](https://securitycenter.windows.com/interoperability/dataexport) auf Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="c4843-114">Go to the [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="c4843-115">Klicken Sie auf **"Datenexporteinstellungen hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="c4843-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="c4843-116">Wählen Sie einen Namen für ihre neuen Einstellungen aus.</span><span class="sxs-lookup"><span data-stu-id="c4843-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="c4843-117">Wählen Sie **"Forward"-Ereignisse an Azure Event Hubs aus.**</span><span class="sxs-lookup"><span data-stu-id="c4843-117">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="c4843-118">Geben Sie den Namen der **Event Hubs** und ihre **Event Hubs-Ressourcen-ID** ein.</span><span class="sxs-lookup"><span data-stu-id="c4843-118">Type your **Event Hubs name** and your **Event Hubs resource ID**.</span></span>

   <span data-ttu-id="c4843-119">Um Ihre **Event Hubs-Ressourcen-ID** abzurufen, wechseln Sie zur Azure Event Hubs-Namespaceseite auf der Registerkarte ["Azure](https://ms.portal.azure.com/) > Eigenschaften", > kopieren Sie den Text unter **"Ressourcen-ID":**</span><span class="sxs-lookup"><span data-stu-id="c4843-119">In order to get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > properties tab > copy the text under **Resource ID**:</span></span>

   ![Abbildung der Event Hub-Ressourcen-ID1](images/event-hub-resource-id.png)

7. <span data-ttu-id="c4843-121">Wählen Sie die Ereignisse aus, die Sie streamen möchten, und klicken Sie auf **"Speichern".**</span><span class="sxs-lookup"><span data-stu-id="c4843-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="c4843-122">Das Schema der Ereignisse in Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="c4843-122">The schema of the events in Azure Event Hubs</span></span>

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

- <span data-ttu-id="c4843-123">Jede Event Hub-Nachricht in Azure Event Hubs enthält eine Liste von Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="c4843-123">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="c4843-124">Jeder Datensatz enthält den Ereignisnamen, den Zeitpunkt, zu dem Microsoft Defender für Endpunkt das Ereignis empfangen hat, den Mandanten, zu dem es gehört (Sie erhalten nur Ereignisse von Ihrem Mandanten) und das Ereignis im JSON-Format in einer Eigenschaft namens **"Eigenschaften".**</span><span class="sxs-lookup"><span data-stu-id="c4843-124">Each record contains the event name, the time Microsoft Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="c4843-125">Weitere Informationen zum Schema von Microsoft Defender für Endpunkt-Ereignissen finden Sie in der [Übersicht über die erweiterte Suche.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c4843-125">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="c4843-126">Bei der erweiterten Suche verfügt die **DeviceInfo-Tabelle** über eine Spalte mit dem Namen **MachineGroup,** die die Gruppe des Geräts enthält.</span><span class="sxs-lookup"><span data-stu-id="c4843-126">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="c4843-127">Hier wird jedes Ereignis auch mit dieser Spalte versehen.</span><span class="sxs-lookup"><span data-stu-id="c4843-127">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="c4843-128">Weitere Informationen finden Sie unter ["Gerätegruppen".](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="c4843-128">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="c4843-129">Zuordnung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="c4843-129">Data types mapping</span></span>

<span data-ttu-id="c4843-130">Gehen Sie folgendermaßen vor, um die Datentypen für Ereigniseigenschaften abzurufen:</span><span class="sxs-lookup"><span data-stu-id="c4843-130">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="c4843-131">Melden Sie sich bei [Microsoft Defender Security Center an,](https://securitycenter.windows.com) und wechseln Sie zur [Seite "Erweiterte Suche".](https://securitycenter.windows.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="c4843-131">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="c4843-132">Führen Sie die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis abzurufen:</span><span class="sxs-lookup"><span data-stu-id="c4843-132">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="c4843-133">Hier ist ein Beispiel für das Device Info-Ereignis:</span><span class="sxs-lookup"><span data-stu-id="c4843-133">Here is an example for Device Info event:</span></span> 

  ![Abbildung der Event Hub-Ressourcen-ID2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="c4843-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c4843-135">Related topics</span></span>
- [<span data-ttu-id="c4843-136">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="c4843-136">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c4843-137">Microsoft Defender für Endpunkt-Streaming-API</span><span class="sxs-lookup"><span data-stu-id="c4843-137">Microsoft Defender for Endpoint streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="c4843-138">Streamen von Microsoft Defender für Endpunkt-Ereignissen auf Ihr Azure-Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="c4843-138">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="c4843-139">Dokumentation zu Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="c4843-139">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="c4843-140">Behandeln von Konnektivitätsproblemen – Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="c4843-140">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](/azure/event-hubs/troubleshooting-guide)