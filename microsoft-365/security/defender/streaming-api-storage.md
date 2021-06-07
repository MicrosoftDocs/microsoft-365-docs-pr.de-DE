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
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="00106-104">Konfigurieren von Microsoft 365 Defender zum Streamen von Advanced Hunting-Ereignissen auf Ihr Storage Konto</span><span class="sxs-lookup"><span data-stu-id="00106-104">Configure  Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="00106-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="00106-105">**Applies to:**</span></span>
- [<span data-ttu-id="00106-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00106-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a><span data-ttu-id="00106-107">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="00106-107">Before you begin:</span></span>

1. <span data-ttu-id="00106-108">Erstellen Sie ein [Storage Konto](/azure/storage/common/storage-account-overview) in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="00106-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="00106-109">Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu **Abonnements > Ihr Abonnement > Ressourcenanbieter > Registrieren bei Microsoft.Insights.**</span><span class="sxs-lookup"><span data-stu-id="00106-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="00106-110">Aktivieren Des Streamings von Rohdaten:</span><span class="sxs-lookup"><span data-stu-id="00106-110">Enable raw data streaming:</span></span>

1. <span data-ttu-id="00106-111">Melden Sie sich bei [Microsoft 365 Defender Security Center](https://security.microsoft.com) als \* globaler **Administrator** _ oder _\*_Sicherheitsadministrator_\*\*an.</span><span class="sxs-lookup"><span data-stu-id="00106-111">Log in to [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="00106-112">Wechseln Sie zur [Seite "Datenexporteinstellungen"](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="00106-112">Go to [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="00106-113">Klicken Sie auf **"Datenexporteinstellungen hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="00106-113">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="00106-114">Wählen Sie einen Namen für ihre neuen Einstellungen aus.</span><span class="sxs-lookup"><span data-stu-id="00106-114">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="00106-115">Wählen Sie **"Forward"-Ereignisse aus, um Azure Storage .**</span><span class="sxs-lookup"><span data-stu-id="00106-115">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="00106-116">Geben Sie Ihre **Storage Kontoressourcen-ID** ein.</span><span class="sxs-lookup"><span data-stu-id="00106-116">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="00106-117">Um Ihre **Storage Kontoressourcen-ID** abzurufen, wechseln Sie zur Storage Kontoseite im [Azure-Portal](https://ms.portal.azure.com/) > Registerkarte "Eigenschaften", > kopieren Sie den Text unter **Storage Kontoressourcen-ID:**</span><span class="sxs-lookup"><span data-stu-id="00106-117">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage Account Resource ID**:</span></span>

   ![Abbildung der Event Hub-Ressourcen-ID1](../defender-endpoint/images/storage-account-resource-id.png)

7. <span data-ttu-id="00106-119">Wählen Sie die Ereignisse aus, die Sie streamen möchten, und klicken Sie auf **"Speichern".**</span><span class="sxs-lookup"><span data-stu-id="00106-119">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="00106-120">Das Schema der Ereignisse im Storage-Konto:</span><span class="sxs-lookup"><span data-stu-id="00106-120">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="00106-121">Für jeden Ereignistyp wird ein Blobcontainer erstellt:</span><span class="sxs-lookup"><span data-stu-id="00106-121">A blob container will be created for each event type:</span></span> 

  ![Abbildung der Event Hub-Ressourcen-ID2](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="00106-123">Das Schema jeder Zeile in einem Blob ist der folgende JSON-Code:</span><span class="sxs-lookup"><span data-stu-id="00106-123">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="00106-124">Jedes Blob enthält mehrere Zeilen.</span><span class="sxs-lookup"><span data-stu-id="00106-124">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="00106-125">Jede Zeile enthält den Ereignisnamen, den Zeitpunkt, zu dem Defender für Endpunkt das Ereignis empfangen hat, den Mandanten, zu dem es gehört (Sie erhalten nur Ereignisse von Ihrem Mandanten) und das Ereignis im JSON-Format in einer Eigenschaft namens "properties".</span><span class="sxs-lookup"><span data-stu-id="00106-125">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="00106-126">Weitere Informationen zum Schema von Microsoft 365 Defender-Ereignissen finden Sie in der [Übersicht über die erweiterte Suche.](../defender/advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="00106-126">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="00106-127">Zuordnung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="00106-127">Data types mapping</span></span>

<span data-ttu-id="00106-128">Gehen Sie folgendermaßen vor, um die Datentypen für unsere Ereigniseigenschaften abzurufen:</span><span class="sxs-lookup"><span data-stu-id="00106-128">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="00106-129">Melden Sie sich bei [Microsoft 365 Security Center](https://security.microsoft.com) an, und wechseln Sie zur Seite ["Erweiterte Suche".](https://security.microsoft.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="00106-129">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="00106-130">Führen Sie die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis abzurufen:</span><span class="sxs-lookup"><span data-stu-id="00106-130">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="00106-131">Hier ist ein Beispiel für das Device Info-Ereignis:</span><span class="sxs-lookup"><span data-stu-id="00106-131">Here is an example for Device Info event:</span></span> 

  ![Abbildung der Event Hub-Ressourcen-ID3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="00106-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="00106-133">Related topics</span></span>
- [<span data-ttu-id="00106-134">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="00106-134">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="00106-135">Microsoft 365 Defender Streaming-API</span><span class="sxs-lookup"><span data-stu-id="00106-135">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="00106-136">Streamen Microsoft 365 Defender-Ereignisse auf Ihr Azure-Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="00106-136">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="00106-137">Azure Storage Kontodokumentation</span><span class="sxs-lookup"><span data-stu-id="00106-137">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
