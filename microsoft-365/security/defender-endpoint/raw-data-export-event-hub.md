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
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="47d41-104">Konfigurieren von Microsoft Defender for Endpoint zum Streamen von Advanced Hunting-Ereignissen an Ihre Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="47d41-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="47d41-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="47d41-105">**Applies to:**</span></span>

- [<span data-ttu-id="47d41-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="47d41-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="47d41-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="47d41-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="47d41-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="47d41-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="47d41-109">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="47d41-109">Before you begin:</span></span>

1. <span data-ttu-id="47d41-110">Erstellen Sie [einen Ereignishub](https://docs.microsoft.com/azure/event-hubs/) in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="47d41-110">Create an [event hub](https://docs.microsoft.com/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="47d41-111">Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu \*\*Abonnements > Ihr Abonnement > Ressourcenanbieter > Registrieren bei **Microsoft.insights**.</span><span class="sxs-lookup"><span data-stu-id="47d41-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to \*\*Subscriptions > Your subscription > Resource Providers > Register to **Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="47d41-112">Aktivieren des Streamings von Rohdaten:</span><span class="sxs-lookup"><span data-stu-id="47d41-112">Enable raw data streaming:</span></span>

1. <span data-ttu-id="47d41-113">Melden Sie sich beim [Microsoft Defender Security Center](https://securitycenter.windows.com) als \* globaler **Administrator** _ oder _*_Sicherheitsadministrator_*\* an.</span><span class="sxs-lookup"><span data-stu-id="47d41-113">Log in to the [Microsoft Defender Security Center](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="47d41-114">Wechseln Sie zur [Seite Datenexporteinstellungen im](https://securitycenter.windows.com/interoperability/dataexport) Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="47d41-114">Go to the [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="47d41-115">Klicken Sie auf **Datenexporteinstellungen hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="47d41-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="47d41-116">Wählen Sie einen Namen für Ihre neuen Einstellungen aus.</span><span class="sxs-lookup"><span data-stu-id="47d41-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="47d41-117">Wählen **Sie Weiterleiten von Ereignissen an Azure Event Hubs aus.**</span><span class="sxs-lookup"><span data-stu-id="47d41-117">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="47d41-118">Geben Sie **ihren Event Hubs-Namen** und Ihre **Event Hubs-Ressourcen-ID ein.**</span><span class="sxs-lookup"><span data-stu-id="47d41-118">Type your **Event Hubs name** and your **Event Hubs resource ID**.</span></span>

   <span data-ttu-id="47d41-119">Um Ihre **Event Hubs-Ressourcen-ID** zu erhalten, wechseln Sie zu Ihrer Azure Event Hubs-Namespaceseite auf der Registerkarte Eigenschaften von [Azure](https://ms.portal.azure.com/) > > kopieren Sie den Text unter **Ressourcen-ID**:</span><span class="sxs-lookup"><span data-stu-id="47d41-119">In order to get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > properties tab > copy the text under **Resource ID**:</span></span>

   ![Abbildung der Event Hub-Ressource Id1](images/event-hub-resource-id.png)

7. <span data-ttu-id="47d41-121">Wählen Sie die Ereignisse aus, die Sie streamen möchten, und klicken Sie auf **Speichern.**</span><span class="sxs-lookup"><span data-stu-id="47d41-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="47d41-122">Das Schema der Ereignisse in Azure Event Hubs:</span><span class="sxs-lookup"><span data-stu-id="47d41-122">The schema of the events in Azure Event Hubs:</span></span>

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

- <span data-ttu-id="47d41-123">Jede Ereignishubnachricht in Azure Event Hubs enthält eine Liste von Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="47d41-123">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="47d41-124">Jeder Datensatz enthält den Ereignisnamen, den Zeitpunkt, zu dem Microsoft Defender for Endpoint das Ereignis empfangen hat, den Mandanten, zu dem er gehört (Sie erhalten nur Ereignisse von Ihrem Mandanten), und das Ereignis im JSON-Format in einer Eigenschaft namens "**properties**".</span><span class="sxs-lookup"><span data-stu-id="47d41-124">Each record contains the event name, the time Microsoft Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="47d41-125">Weitere Informationen zum Schema von Microsoft Defender for Endpoint-Ereignissen finden Sie unter [Advanced Hunting overview](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="47d41-125">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="47d41-126">In Advanced Hunting verfügt **die DeviceInfo-Tabelle** über eine Spalte mit dem Namen **MachineGroup,** die die Gruppe des Geräts enthält.</span><span class="sxs-lookup"><span data-stu-id="47d41-126">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="47d41-127">Hier wird jedes Ereignis auch mit dieser Spalte eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="47d41-127">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="47d41-128">Weitere [Informationen finden Sie](machine-groups.md) unter Gerätegruppen.</span><span class="sxs-lookup"><span data-stu-id="47d41-128">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="47d41-129">Datentypzuordnung:</span><span class="sxs-lookup"><span data-stu-id="47d41-129">Data types mapping:</span></span>

<span data-ttu-id="47d41-130">Gehen Sie wie folgt vor, um die Datentypen für Ereigniseigenschaften zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="47d41-130">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="47d41-131">Melden Sie sich beim [Microsoft Defender Security Center an,](https://securitycenter.windows.com) und wechseln Sie zur Seite Erweiterte [Suche](https://securitycenter.windows.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="47d41-131">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="47d41-132">Führen Sie die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="47d41-132">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="47d41-133">Im Folgenden finden Sie ein Beispiel für ein Device Info-Ereignis:</span><span class="sxs-lookup"><span data-stu-id="47d41-133">Here is an example for Device Info event:</span></span> 

  ![Abbildung der Event Hub-Ressource Id2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="47d41-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="47d41-135">Related topics</span></span>
- [<span data-ttu-id="47d41-136">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="47d41-136">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="47d41-137">Microsoft Defender for Endpoint-Streaming-API</span><span class="sxs-lookup"><span data-stu-id="47d41-137">Microsoft Defender for Endpoint streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="47d41-138">Streamen von Microsoft Defender for Endpoint-Ereignissen an Ihr Azure-Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="47d41-138">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="47d41-139">Dokumentation zu Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="47d41-139">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="47d41-140">Problembehandlung bei Konnektivitätsproblemen – Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="47d41-140">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
