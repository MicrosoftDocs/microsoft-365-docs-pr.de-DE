---
title: Streamen Microsoft 365 von Defender-Ereignissen an Ihr Storage Konto
description: Erfahren Sie, wie Sie Microsoft 365 Defender zum Streamen von Advanced Hunting-Ereignissen an Ihr Storage konfigurieren.
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
ms.openlocfilehash: 1a1d6b63bcdf21535f36b23d4a30e5ea01833c36
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729992"
---
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="66fe6-104">Konfigurieren Microsoft 365 Defender zum Streamen von Advanced Hunting-Ereignissen an Ihr Storage Konto</span><span class="sxs-lookup"><span data-stu-id="66fe6-104">Configure  Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="66fe6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="66fe6-105">**Applies to:**</span></span>
- [<span data-ttu-id="66fe6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66fe6-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a><span data-ttu-id="66fe6-107">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="66fe6-107">Before you begin:</span></span>

1. <span data-ttu-id="66fe6-108">Erstellen Sie [Storage Konto](/azure/storage/common/storage-account-overview) in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="66fe6-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="66fe6-109">Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu Abonnements > Ihr Abonnement > Ressourcenanbieter > **Registrieren bei Microsoft.Insights**.</span><span class="sxs-lookup"><span data-stu-id="66fe6-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="66fe6-110">Aktivieren des Streamings von Rohdaten:</span><span class="sxs-lookup"><span data-stu-id="66fe6-110">Enable raw data streaming:</span></span>

1. <span data-ttu-id="66fe6-111">Melden Sie sich [Microsoft 365 #A0](https://security.microsoft.com) als ***globaler Administrator** _ oder _*_Sicherheitsadministrator \*\*_ an.</span><span class="sxs-lookup"><span data-stu-id="66fe6-111">Log in to [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="66fe6-112">Wechseln Sie [zur Seite Datenexporteinstellungen](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="66fe6-112">Go to [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="66fe6-113">Klicken Sie auf **Datenexporteinstellungen hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="66fe6-113">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="66fe6-114">Wählen Sie einen Namen für Ihre neuen Einstellungen aus.</span><span class="sxs-lookup"><span data-stu-id="66fe6-114">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="66fe6-115">Wählen **Sie Weiterleiten von Ereignissen aus, die Azure Storage.**</span><span class="sxs-lookup"><span data-stu-id="66fe6-115">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="66fe6-116">Geben Sie Storage **Kontoressourcen-ID ein.**</span><span class="sxs-lookup"><span data-stu-id="66fe6-116">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="66fe6-117">Um Ihre **Storage-Kontoressourcen-ID** zu erhalten, wechseln Sie zu Ihrer Storage-Kontoseite im [Azure-Portal](https://ms.portal.azure.com/) > Eigenschaftenregisterkarte > kopieren Sie den Text unter **Storage Kontoressourcen-ID**:</span><span class="sxs-lookup"><span data-stu-id="66fe6-117">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage Account Resource ID**:</span></span>

   ![Abbildung der Ereignishubressourcen-ID1](images/storage-account-resource-id.png)

7. <span data-ttu-id="66fe6-119">Wählen Sie die Ereignisse aus, die Sie streamen möchten, und klicken Sie auf **Speichern.**</span><span class="sxs-lookup"><span data-stu-id="66fe6-119">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="66fe6-120">Das Schema der Ereignisse im Storage Konto:</span><span class="sxs-lookup"><span data-stu-id="66fe6-120">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="66fe6-121">Für jeden Ereignistyp wird ein Blobcontainer erstellt:</span><span class="sxs-lookup"><span data-stu-id="66fe6-121">A blob container will be created for each event type:</span></span> 

  ![Abbildung der Ereignishubressourcen-ID2](images/storage-account-event-schema.png)

- <span data-ttu-id="66fe6-123">Das Schema jeder Zeile in einem Blob ist das folgende JSON:</span><span class="sxs-lookup"><span data-stu-id="66fe6-123">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="66fe6-124">Jedes Blob enthält mehrere Zeilen.</span><span class="sxs-lookup"><span data-stu-id="66fe6-124">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="66fe6-125">Jede Zeile enthält den Ereignisnamen, den Zeitpunkt, zu dem Defender for Endpoint das Ereignis empfangen hat, den Mandanten, zu dem sie gehört (Sie erhalten nur Ereignisse von Ihrem Mandanten), und das Ereignis im JSON-Format in einer Eigenschaft namens "properties".</span><span class="sxs-lookup"><span data-stu-id="66fe6-125">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="66fe6-126">Weitere Informationen zum Schema Microsoft 365 Defender-Ereignisse finden Sie unter [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="66fe6-126">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="66fe6-127">Datentypzuordnung:</span><span class="sxs-lookup"><span data-stu-id="66fe6-127">Data types mapping:</span></span>

<span data-ttu-id="66fe6-128">Gehen Sie wie folgt vor, um die Datentypen für unsere Ereigniseigenschaften zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="66fe6-128">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="66fe6-129">Melden Sie sich [bei Microsoft 365 Sicherheitscenter an,](https://security.microsoft.com) und wechseln Sie zur [Seite Erweiterte Suche](https://security.microsoft.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="66fe6-129">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="66fe6-130">Führen Sie die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="66fe6-130">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="66fe6-131">Im Folgenden finden Sie ein Beispiel für ein Device Info-Ereignis:</span><span class="sxs-lookup"><span data-stu-id="66fe6-131">Here is an example for Device Info event:</span></span> 

  ![Abbildung der Ereignishubressourcen-ID3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="66fe6-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="66fe6-133">Related topics</span></span>
- [<span data-ttu-id="66fe6-134">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="66fe6-134">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="66fe6-135">Microsoft 365 Defender Streaming-API</span><span class="sxs-lookup"><span data-stu-id="66fe6-135">Microsoft 365 Defender Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="66fe6-136">Streamen Microsoft 365 Von Defender-Ereignissen an Ihr Azure-Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="66fe6-136">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="66fe6-137">Azure Storage Kontodokumentation</span><span class="sxs-lookup"><span data-stu-id="66fe6-137">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
