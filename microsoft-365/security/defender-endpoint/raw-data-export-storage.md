---
title: Streamen von Microsoft Defender for Endpoint-Ereignissen an Ihr Storage Konto
description: Erfahren Sie, wie Sie Microsoft Defender for Endpoint zum Streamen von Advanced Hunting-Ereignissen an Ihr Storage konfigurieren.
keywords: Rohdatenexport, Streaming-API, API, Event Hubs, Azure-Speicher, Speicherkonto, Erweiterte Suche, Unformatierte Datenfreigabe
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
ms.openlocfilehash: 19fe0c9c3dc6f2e4226a4aa9a6cd983bc95bae3a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688789"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="31dab-104">Konfigurieren von Microsoft Defender for Endpoint zum Streamen von Advanced Hunting-Ereignissen Storage Konto</span><span class="sxs-lookup"><span data-stu-id="31dab-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="31dab-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="31dab-105">**Applies to:**</span></span>
- [<span data-ttu-id="31dab-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="31dab-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="31dab-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="31dab-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="31dab-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="31dab-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="31dab-109">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="31dab-109">Before you begin:</span></span>

1. <span data-ttu-id="31dab-110">Erstellen Sie [Storage Konto](https://docs.microsoft.com/azure/storage/common/storage-account-overview) in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="31dab-110">Create a [Storage account](https://docs.microsoft.com/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="31dab-111">Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu Abonnements > Ihr Abonnement > Ressourcenanbieter > **Registrieren bei Microsoft.insights**.</span><span class="sxs-lookup"><span data-stu-id="31dab-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="31dab-112">Aktivieren des Streamings von Rohdaten:</span><span class="sxs-lookup"><span data-stu-id="31dab-112">Enable raw data streaming:</span></span>

1. <span data-ttu-id="31dab-113">Melden Sie sich [beim Microsoft Defender for Endpoint-Portal](https://securitycenter.windows.com) als \* globaler **Administrator** _ oder _*_Sicherheitsadministrator_*\* an.</span><span class="sxs-lookup"><span data-stu-id="31dab-113">Log in to [Microsoft Defender for Endpoint portal](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="31dab-114">Wechseln Sie [zu Seite Datenexporteinstellungen](https://securitycenter.windows.com/interoperability/dataexport) auf Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="31dab-114">Go to [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="31dab-115">Klicken Sie auf **Datenexporteinstellungen hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="31dab-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="31dab-116">Wählen Sie einen Namen für Ihre neuen Einstellungen aus.</span><span class="sxs-lookup"><span data-stu-id="31dab-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="31dab-117">Wählen **Sie Weiterleiten von Ereignissen aus, die Azure Storage.**</span><span class="sxs-lookup"><span data-stu-id="31dab-117">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="31dab-118">Geben Sie Storage **Kontoressourcen-ID ein.**</span><span class="sxs-lookup"><span data-stu-id="31dab-118">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="31dab-119">Um Ihre **Storage-Kontoressourcen-ID** zu erhalten, wechseln Sie zu Ihrer Storage-Kontoseite im [Azure-Portal](https://ms.portal.azure.com/) > Eigenschaftenregisterkarte > kopieren Sie den Text unter **Storage Kontoressourcen-ID**:</span><span class="sxs-lookup"><span data-stu-id="31dab-119">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage account resource ID**:</span></span>

   ![Abbildung der Ereignishubressourcen-ID1](images/storage-account-resource-id.png)

7. <span data-ttu-id="31dab-121">Wählen Sie die Ereignisse aus, die Sie streamen möchten, und klicken Sie auf **Speichern.**</span><span class="sxs-lookup"><span data-stu-id="31dab-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="31dab-122">Das Schema der Ereignisse im Storage Konto:</span><span class="sxs-lookup"><span data-stu-id="31dab-122">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="31dab-123">Für jeden Ereignistyp wird ein Blobcontainer erstellt:</span><span class="sxs-lookup"><span data-stu-id="31dab-123">A blob container will be created for each event type:</span></span> 

  ![Abbildung der Ereignishubressourcen-ID2](images/storage-account-event-schema.png)

- <span data-ttu-id="31dab-125">Das Schema jeder Zeile in einem Blob ist das folgende JSON:</span><span class="sxs-lookup"><span data-stu-id="31dab-125">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="31dab-126">Jedes Blob enthält mehrere Zeilen.</span><span class="sxs-lookup"><span data-stu-id="31dab-126">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="31dab-127">Jede Zeile enthält den Ereignisnamen, den Zeitpunkt, zu dem Defender for Endpoint das Ereignis empfangen hat, den Mandanten, zu dem sie gehört (Sie erhalten nur Ereignisse von Ihrem Mandanten), und das Ereignis im JSON-Format in einer Eigenschaft namens "properties".</span><span class="sxs-lookup"><span data-stu-id="31dab-127">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="31dab-128">Weitere Informationen zum Schema von Microsoft Defender for Endpoint-Ereignissen finden Sie unter [Advanced Hunting overview](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="31dab-128">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="31dab-129">In Advanced Hunting verfügt **die DeviceInfo-Tabelle** über eine Spalte mit dem Namen **MachineGroup,** die die Gruppe des Geräts enthält.</span><span class="sxs-lookup"><span data-stu-id="31dab-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="31dab-130">Hier wird jedes Ereignis auch mit dieser Spalte eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="31dab-130">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="31dab-131">Weitere [Informationen finden Sie](machine-groups.md) unter Gerätegruppen.</span><span class="sxs-lookup"><span data-stu-id="31dab-131">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="31dab-132">Datentypzuordnung:</span><span class="sxs-lookup"><span data-stu-id="31dab-132">Data types mapping:</span></span>

<span data-ttu-id="31dab-133">Gehen Sie wie folgt vor, um die Datentypen für unsere Ereigniseigenschaften zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="31dab-133">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="31dab-134">Melden Sie sich bei [Microsoft Defender Security Center](https://securitycenter.windows.com) an, und wechseln Sie zur [Seite Erweiterte Suche](https://securitycenter.windows.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="31dab-134">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="31dab-135">Führen Sie die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="31dab-135">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="31dab-136">Im Folgenden finden Sie ein Beispiel für ein Device Info-Ereignis:</span><span class="sxs-lookup"><span data-stu-id="31dab-136">Here is an example for Device Info event:</span></span> 

  ![Abbildung der Ereignishubressourcen-ID3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="31dab-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="31dab-138">Related topics</span></span>
- [<span data-ttu-id="31dab-139">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="31dab-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="31dab-140">Microsoft Defender for Endpoint Streaming API</span><span class="sxs-lookup"><span data-stu-id="31dab-140">Microsoft Defender for Endpoint Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="31dab-141">Streamen von Microsoft Defender for Endpoint-Ereignissen an Ihr Azure-Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="31dab-141">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="31dab-142">Azure Storage Kontodokumentation</span><span class="sxs-lookup"><span data-stu-id="31dab-142">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
