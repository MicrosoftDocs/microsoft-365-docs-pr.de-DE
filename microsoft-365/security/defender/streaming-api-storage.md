---
title: Streamen Microsoft 365 Defender Ereignisse an Ihr Storage Konto
description: Erfahren Sie, wie Sie Microsoft 365 Defender konfigurieren, um Ereignisse der erweiterten Suche in Ihr Storage Konto zu streamen.
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
ms.openlocfilehash: 656387e60bac90c7e9de4852779948dabce0efe3
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029657"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="225f6-104">Konfigurieren Microsoft 365 Defender zum Streamen von Advanced Hunting-Ereignissen auf Ihr Storage Konto</span><span class="sxs-lookup"><span data-stu-id="225f6-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="225f6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="225f6-105">**Applies to:**</span></span>
- [<span data-ttu-id="225f6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="225f6-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="225f6-107">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="225f6-107">Before you begin</span></span>

1. <span data-ttu-id="225f6-108">Erstellen Sie ein [Storage Konto](/azure/storage/common/storage-account-overview) in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="225f6-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="225f6-109">Melden Sie sich bei Ihrem [Azure-Mandanten](https://ms.portal.azure.com/)an, wechseln Sie zu **Abonnements > Ihr Abonnement > Ressourcenanbieter > Registrieren bei Microsoft.Insights.**</span><span class="sxs-lookup"><span data-stu-id="225f6-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="225f6-110">Aktivieren des Streamings von Rohdaten</span><span class="sxs-lookup"><span data-stu-id="225f6-110">Enable raw data streaming</span></span>

1. <span data-ttu-id="225f6-111">Melden Sie sich beim Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ) als \* globaler **Administrator** _ oder _\*_Sicherheitsadministrator_\*\*an.</span><span class="sxs-lookup"><span data-stu-id="225f6-111">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="225f6-112">Wechseln Sie zu **Einstellungen** \> **Microsoft 365 Defender** \> **Streaming-API.**</span><span class="sxs-lookup"><span data-stu-id="225f6-112">Go to **Settings** \> **Microsoft 365 Defender** \> **Streaming API**.</span></span> <span data-ttu-id="225f6-113">Um direkt zur Seite der **Streaming-API** zu wechseln, verwenden Sie <https://security.microsoft.com/settings/mtp_settings/raw_data_export> .</span><span class="sxs-lookup"><span data-stu-id="225f6-113">To go directly to the **Streaming API** page, use <https://security.microsoft.com/settings/mtp_settings/raw_data_export>.</span></span>

3. <span data-ttu-id="225f6-114">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="225f6-114">Click **Add**.</span></span>

4. <span data-ttu-id="225f6-115">Konfigurieren Sie im angezeigten Flyout **"Neue Streaming-API-Einstellungen hinzufügen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="225f6-115">In the **Add new Streaming API settings** flyout that appears, configure the following settings:</span></span>
   1. <span data-ttu-id="225f6-116">**Name:** Wählen Sie einen Namen für ihre neuen Einstellungen aus.</span><span class="sxs-lookup"><span data-stu-id="225f6-116">**Name**: Choose a name for your new settings.</span></span>
   2. <span data-ttu-id="225f6-117">Select **Forward events to Azure Storage**.</span><span class="sxs-lookup"><span data-stu-id="225f6-117">Select **Forward events to Azure Storage**.</span></span>
   3. <span data-ttu-id="225f6-118">Geben Sie im angezeigten **Feld Storage Kontoressourcen-ID** Ihre **Storage Kontoressourcen-ID** ein.</span><span class="sxs-lookup"><span data-stu-id="225f6-118">In the **Storage Account Resource ID** box that appears, type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="225f6-119">Um Ihre **Storage Kontoressourcen-ID** abzurufen, öffnen Sie das Azure-Portal unter <https://portal.azure.com> , klicken Sie auf Storage **Konten** zur Registerkarte \> Eigenschaften \> wechseln, kopieren Sie den Text unter Storage **Kontoressourcen-ID.**</span><span class="sxs-lookup"><span data-stu-id="225f6-119">To get your **Storage Account Resource ID**, open the Azure portal at <https://portal.azure.com>, click **Storage accounts** \> go to the properties tab \> copy the text under **Storage Account Resource ID**.</span></span>

      ![Abbildung der Event Hub-Ressourcen-ID1](../defender-endpoint/images/storage-account-resource-id.png)

   4. <span data-ttu-id="225f6-121">Wählen Sie im Flyout **"Neue Streaming-API-Einstellungen hinzufügen"** die **Ereignistypen aus,** die Sie streamen möchten.</span><span class="sxs-lookup"><span data-stu-id="225f6-121">Back on the **Add new Streaming API settings** flyout, choose the **Event types** that you want to stream.</span></span>

   <span data-ttu-id="225f6-122">Wenn Sie fertig sind, klicken Sie auf **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="225f6-122">When you're finished, click **Submit**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="225f6-123">Das Schema der Ereignisse im Storage Konto</span><span class="sxs-lookup"><span data-stu-id="225f6-123">The schema of the events in the Storage account</span></span>

- <span data-ttu-id="225f6-124">Für jeden Ereignistyp wird ein Blobcontainer erstellt:</span><span class="sxs-lookup"><span data-stu-id="225f6-124">A blob container will be created for each event type:</span></span>

  ![Abbildung der Event Hub-Ressourcen-ID2](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="225f6-126">Das Schema jeder Zeile in einem Blob ist der folgende JSON-Code:</span><span class="sxs-lookup"><span data-stu-id="225f6-126">The schema of each row in a blob is the following JSON:</span></span>

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- <span data-ttu-id="225f6-127">Jedes Blob enthält mehrere Zeilen.</span><span class="sxs-lookup"><span data-stu-id="225f6-127">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="225f6-128">Jede Zeile enthält den Ereignisnamen, den Zeitpunkt, zu dem Defender für Endpunkt das Ereignis empfangen hat, den Mandanten, zu dem es gehört (Sie erhalten nur Ereignisse von Ihrem Mandanten) und das Ereignis im JSON-Format in einer Eigenschaft namens "properties".</span><span class="sxs-lookup"><span data-stu-id="225f6-128">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="225f6-129">Weitere Informationen zum Schema von Microsoft 365 Defender-Ereignissen finden Sie in der [Übersicht über die erweiterte Suche.](../defender/advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="225f6-129">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="225f6-130">Zuordnung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="225f6-130">Data types mapping</span></span>

<span data-ttu-id="225f6-131">Gehen Sie folgendermaßen vor, um die Datentypen für unsere Ereigniseigenschaften abzurufen:</span><span class="sxs-lookup"><span data-stu-id="225f6-131">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="225f6-132">Melden Sie sich beim Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ) an, und wechseln Sie zur  \> **erweiterten Suche**.</span><span class="sxs-lookup"><span data-stu-id="225f6-132">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Hunting** \> **Advanced hunting**.</span></span> <span data-ttu-id="225f6-133">Verwenden Sie <security.microsoft.com/advanced-hunting>, um direkt zur Seite **"Erweiterte Suche"** zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="225f6-133">To go directly to the **Advanced hunting** page, use <security.microsoft.com/advanced-hunting>.</span></span>

2. <span data-ttu-id="225f6-134">Führen Sie auf der Registerkarte **"Abfrage"** die folgende Abfrage aus, um die Datentypzuordnung für jedes Ereignis abzurufen:</span><span class="sxs-lookup"><span data-stu-id="225f6-134">On the **Query** tab, run the following query to get the data types mapping for each event:</span></span>

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- <span data-ttu-id="225f6-135">Hier ist ein Beispiel für das Device Info-Ereignis:</span><span class="sxs-lookup"><span data-stu-id="225f6-135">Here is an example for Device Info event:</span></span>

  ![Abbildung der Event Hub-Ressourcen-ID3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="225f6-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="225f6-137">Related topics</span></span>

- [<span data-ttu-id="225f6-138">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="225f6-138">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="225f6-139">Microsoft 365 Defender Streaming-API</span><span class="sxs-lookup"><span data-stu-id="225f6-139">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="225f6-140">Streamen Microsoft 365 Defender Ereignisse auf Ihr Azure-Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="225f6-140">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="225f6-141">Azure Storage Kontodokumentation</span><span class="sxs-lookup"><span data-stu-id="225f6-141">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
