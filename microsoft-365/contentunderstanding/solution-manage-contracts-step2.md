---
title: 'Schritt 2: Erstellen Microsoft Teams Vertragsverwaltungskanals mithilfe von Microsoft Teams'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Erfahren Sie, wie Sie Microsoft Teams zum Erstellen Ihres Vertragsverwaltungskanals mithilfe einer Microsoft 365 verwenden.
ms.openlocfilehash: 81d5fe34383453b187363b13c21ef47844948193
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636182"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a><span data-ttu-id="50304-104">Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="50304-104">Step 2.</span></span> <span data-ttu-id="50304-105">Erstellen Microsoft Teams Vertragsverwaltungskanals mithilfe von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="50304-105">Use Microsoft Teams to create your contract management channel</span></span>

<span data-ttu-id="50304-106">Wenn Ihre Organisation eine Lösung für die Vertragsverwaltung eingerichtet hat, benötigen Sie einen zentralen Ort, an dem Beteiligte Verträge überprüfen und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="50304-106">When your organization sets up a contracts management solution, you need a central location in which stakeholders can review and manage contracts.</span></span> <span data-ttu-id="50304-107">Zu diesem Zweck können Sie [Microsoft Teams](https://docs.microsoft.com/microsoftteams/) verwenden, um einen Teams einrichten und die Features in Teams verwenden:</span><span class="sxs-lookup"><span data-stu-id="50304-107">For this purpose, you can use [Microsoft Teams](https://docs.microsoft.com/microsoftteams/) to set up a Teams channel and use the features in Teams to:</span></span>

- <span data-ttu-id="50304-108">**Erstellen Sie einen Ort für Beteiligte, um alle Verträge, die Aktionen erfordern, einfach zu sehen.**</span><span class="sxs-lookup"><span data-stu-id="50304-108">**Create a location for stakeholders to easily see all contracts that require action.**</span></span> <span data-ttu-id="50304-109">In der Teams Sie beispielsweise eine  Registerkarte Verträge im Kanal Vertragsverwaltung erstellen, in der Mitgliedern eine nützliche Kachelansicht aller Verträge angezeigt wird, die genehmigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="50304-109">For example, in Teams you can create a **Contracts** tab in the Contract Management channel in which members can see a useful tile view of all contracts that need approval.</span></span> <span data-ttu-id="50304-110">Sie können die Ansicht auch so konfigurieren, dass jede "Karte" die wichtigen Daten auflistet, die Ihnen wichtig sind (z. B. *Client,* *Auftragnehmer* und *Gebührenbetrag).*</span><span class="sxs-lookup"><span data-stu-id="50304-110">You can also configure the view so that each "card" lists the important data you care about (such as *Client*, *Contractor*, and *Fee amount*).</span></span>

     ![Registerkarte Verträge.](../media/content-understanding/tile-view.png)

- <span data-ttu-id="50304-112">**Verfügen Sie über einen Ort, an dem Mitglieder miteinander interagieren und wichtige Ereignisse sehen können.**</span><span class="sxs-lookup"><span data-stu-id="50304-112">**Have a location for members to interact with each other and see important events.**</span></span> <span data-ttu-id="50304-113">Beispielsweise kann in Teams die  Registerkarte Beiträge verwendet werden, um Unterhaltungen zu führen, Updates zu erhalten und Aktionen zu sehen (z. B. ein Mitglied, das einen Vertrag ablehnt).</span><span class="sxs-lookup"><span data-stu-id="50304-113">For example, in Teams, the **Posts** tab can be used to have conversations, get updates, and see actions (such as a member rejecting a contract).</span></span> <span data-ttu-id="50304-114">Wenn etwas passiert ist (z. B. ein neuer Vertrag, der zur Genehmigung eingereicht wurde), kann die Registerkarte **Beiträge** nicht nur zum Ankündigen, sondern auch zum Aufzeichnen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50304-114">When something has happened (such as a new contract submitted for approval), the **Posts** tab can be used not only to announce it, but also to keep a record of it.</span></span> <span data-ttu-id="50304-115">Und wenn Mitglieder Benachrichtigungen abonnieren, werden sie benachrichtigt, wenn ein Update vorkommt.</span><span class="sxs-lookup"><span data-stu-id="50304-115">And if members subscribe to notifications, they'll get notified whenever there's an update.</span></span> 

     ![Registerkarte Beiträge.](../media/content-understanding/posts.png)</br> 

- <span data-ttu-id="50304-117">**Haben Sie einen Ort, an dem Mitglieder genehmigte Verträge sehen können, um zu wissen, wann sie zur Zahlung eingereicht werden können.**</span><span class="sxs-lookup"><span data-stu-id="50304-117">**Have a location for members to see approved contracts to know when they can be submitted for payment.**</span></span> <span data-ttu-id="50304-118">In Teams können Sie einen <b>For Payment-Kanal</b> erstellen, der alle Verträge auflistet, die zur Zahlung übermittelt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="50304-118">In Teams, you can create a <b>For Payment</b> channel that will list all contracts that will need to be submitted to payment.</span></span> <span data-ttu-id="50304-119">Sie können diese Lösung problemlos erweitern, um diese Informationen stattdessen direkt in eine Finanzanwendung eines Drittanbieters (z. B. Dynamics CRM) zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="50304-119">You can easily extend this solution to instead write this information directly to a third-party financial application (for example, Dynamics CRM).</span></span>

## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a><span data-ttu-id="50304-120">Anfügen SharePoint Dokumentbibliothek an die Registerkarte Verträge</span><span class="sxs-lookup"><span data-stu-id="50304-120">Attach your SharePoint document library to the Contracts tab</span></span> 

<span data-ttu-id="50304-121">Nachdem Sie im **Kanal** Vertragsverwaltung eine Registerkarte Verträge erstellt haben, müssen Sie die SharePoint [Dokumentbibliothek anfügen.](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)</span><span class="sxs-lookup"><span data-stu-id="50304-121">After you create a **Contracts** tab in your Contracts Management channel, you need to [attach your SharePoint document library to it](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b).</span></span> <span data-ttu-id="50304-122">Die SharePoint Dokumentbibliothek, die Sie anfügen möchten, ist die Dokumentbibliothek, auf die Sie ihr SharePoint Syntex-Dokumentverständnismodell im vorherigen Abschnitt angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="50304-122">The SharePoint document library you want to attach is the one in which you applied your SharePoint Syntex document understanding model to in the previous section.</span></span>

<span data-ttu-id="50304-123">Nachdem Sie die SharePoint hinzugefügt haben, können Sie alle klassifizierten Verträge über eine Standardlistenansicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="50304-123">After you attach the SharePoint document library, you'll be able to view any classified contracts through a default list view.</span></span>

   ![Listenansicht.](../media/content-understanding/list-view.png) 

## <a name="customize-your-contracts-tab-tile-view"></a><span data-ttu-id="50304-125">Anpassen der Kachelansicht der Registerkarte Verträge</span><span class="sxs-lookup"><span data-stu-id="50304-125">Customize your Contracts tab tile view</span></span>

> [!NOTE]
> <span data-ttu-id="50304-126">In diesem Abschnitt werden Codebeispiele referenziert, die in der [ContractTileFormatting.json-Datei](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) enthalten sind, die im [Repository "Contracts Management Solution Assets" enthalten ist.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)</span><span class="sxs-lookup"><span data-stu-id="50304-126">This section references code examples that are contained in the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file that is included in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span>

<span data-ttu-id="50304-127">Während Teams Sie Ihre Verträge in einer Kachelansicht anzeigen können, möchten Sie sie möglicherweise so anpassen, dass die Vertragsdaten angezeigt werden, die Sie auf der Vertragskarte sichtbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="50304-127">While Teams lets you view your contracts in a tile view, you might want to customize it to view the contract data you want to make visible in the contract card.</span></span> <span data-ttu-id="50304-128">Für die Registerkarte  Verträge ist es z. B. wichtig, dass Mitglieder den Client, den Auftragnehmer und den Gebührenbetrag auf der Vertragskarte sehen.</span><span class="sxs-lookup"><span data-stu-id="50304-128">For example, for the **Contracts** tab, it is important for members to see the client, contractor, and fee amount on the contract card.</span></span> <span data-ttu-id="50304-129">Alle diese Felder wurden aus jedem Vertrag über Ihr SharePoint Syntex-Modell extrahiert, das auf Ihre Dokumentbibliothek angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="50304-129">All of these fields were extracted from each contract through your SharePoint Syntex model that was applied to your document library.</span></span> <span data-ttu-id="50304-130">Sie möchten auch in der Lage sein, die Kachelkopfleiste für jeden Status in unterschiedliche Farben zu ändern, damit Mitglieder leicht sehen können, wo sich der Vertrag im Genehmigungsprozess befindet.</span><span class="sxs-lookup"><span data-stu-id="50304-130">You also want to be able to change the tile header bar to different colors for each status so that members can easily see where the contract is in the approval process.</span></span> <span data-ttu-id="50304-131">Beispielsweise verfügen alle genehmigten Verträge über eine blaue Kopfzeile.</span><span class="sxs-lookup"><span data-stu-id="50304-131">For example, all approved contracts will have a blue header bar.</span></span>

   ![Listenansicht.](../media/content-understanding/tile.png)

<span data-ttu-id="50304-133">Für die von Ihnen verwendete benutzerdefinierte Kachelansicht müssen Sie Änderungen an der JSON-Datei vornehmen, die zum Formatieren der aktuellen Kachelansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="50304-133">The custom tile view you use requires you to make changes to the JSON file used to format the current tile view.</span></span> <span data-ttu-id="50304-134">Sie können auf die JSON-Datei verweisen, die zum Erstellen der Kartenansicht verwendet wird, indem Sie sich die Datei [ContractTileFormatting.js](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) ansehen.</span><span class="sxs-lookup"><span data-stu-id="50304-134">You can reference the JSON file used to create the card view by looking at the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file.</span></span> <span data-ttu-id="50304-135">In den folgenden Abschnitten werden bestimmte Abschnitte des Codes für Features in den Vertragskarten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="50304-135">In the following sections, you'll see specific sections of the code for features that are in the contract cards.</span></span>

<span data-ttu-id="50304-136">Wenn Sie den JSON-Code für Ihre Ansicht in Ihrem Teams-Kanal anzeigen oder ändern möchten, wählen Sie im Teams-Kanal das Dropdownmenü Ansicht aus, und wählen Sie dann Aktuelle Ansicht **formatieren aus.**</span><span class="sxs-lookup"><span data-stu-id="50304-136">If you want to see or make changes to the JSON code for your view in your Teams channel, in the Teams channel, select the view drop-down menu, and then select **Format current view**.</span></span>

   ![json-Format.](../media/content-understanding/jason-format.png) 

## <a name="card-size-and-shape"></a><span data-ttu-id="50304-138">Kartengröße und -form</span><span class="sxs-lookup"><span data-stu-id="50304-138">Card size and shape</span></span>

<span data-ttu-id="50304-139">In der [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) sehen Sie sich den folgenden Abschnitt an, um den Code für die Formatierung der Größe und Form der Karte zu sehen.</span><span class="sxs-lookup"><span data-stu-id="50304-139">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, look at the following section to see the code for how the size and shape of the card is formatted.</span></span>

```JSON
                  {
                    "elmType": "div",
                    "style": {
                      "background-color": "#f5f5f5",
                      "padding": "5px",
                      "width": "180px"
                    },
                    "children": [
                      {
                        "elmType": "img",
                        "attributes": {
                          "src": "@thumbnail.large"
                        },
                        "style": {
                          "width": "185px",
                          "height": "248px"
                        }
                      }
```


## <a name="contract-status"></a><span data-ttu-id="50304-140">Vertragsstatus</span><span class="sxs-lookup"><span data-stu-id="50304-140">Contract status</span></span>

<span data-ttu-id="50304-141">Mit dem folgenden Code können Sie den Status jeder Titelkarte definieren.</span><span class="sxs-lookup"><span data-stu-id="50304-141">The following code lets you define the status of each title card.</span></span> <span data-ttu-id="50304-142">Beachten Sie, dass für jeden Statuswert (*Neu*, *In Review*, *Approved* und *Rejected*) jeweils ein anderer Farbcode angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="50304-142">Note that each status value (*New*, *In review*, *Approved*, and *Rejected*) will display a different color code for each.</span></span> <span data-ttu-id="50304-143">Sehen SieContractTileFormatting.jsin der Datei [ "on"](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) den Abschnitt an, in dem der Status definiert ist.</span><span class="sxs-lookup"><span data-stu-id="50304-143">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, look at the section that defines the status.</span></span>

```JSON
          {
            "elmType": "div",
            "children": [
              {
                "elmType": "div",
                "style": {
                  "color": "white",
                  "background-color": "=if([$Status] == 'New', '#00b7c3', if([$Status] == 'In review', '#ffaa44', if([$Status] == 'Approved', '#0078d4', if([$Status] == 'Rejected', '#d13438', '#8378de'))))",
                  "padding": "5px 15px",
                  "height": "auto",
                  "text-transform": "uppercase",
                  "font-size": "12.5px"
                },
                "txtContent": "[$Status]"
              }
```


## <a name="extracted-fields"></a><span data-ttu-id="50304-144">Extrahierte Felder</span><span class="sxs-lookup"><span data-stu-id="50304-144">Extracted fields</span></span>

<span data-ttu-id="50304-145">Jede Vertragskarte zeigt drei Felder an, die für jeden Vertrag extrahiert wurden (*Client,* *Auftragnehmer* und *Gebührenbetrag*).</span><span class="sxs-lookup"><span data-stu-id="50304-145">Each contract card will display three fields that were extracted for each contract (*Client*, *Contractor*, and *Fee Amount*).</span></span> <span data-ttu-id="50304-146">Darüber hinaus möchten Sie auch die Uhrzeit/das Datum anzeigen, an dem die Datei vom SharePoint syntex-Modell klassifiziert wurde, mit dem sie identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="50304-146">Additionally, you also want to display the time/date that the file was classified by the SharePoint Syntex model used to identify it.</span></span> 

<span data-ttu-id="50304-147">In der [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) werden diese in den folgenden Abschnitten definiert.</span><span class="sxs-lookup"><span data-stu-id="50304-147">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, the following sections define each of these.</span></span>

### <a name="client"></a><span data-ttu-id="50304-148">Client</span><span class="sxs-lookup"><span data-stu-id="50304-148">Client</span></span>

<span data-ttu-id="50304-149">In diesem Abschnitt wird definiert, wie "Client" auf der Karte angezeigt wird, und der Wert für den jeweiligen Vertrag verwendet.</span><span class="sxs-lookup"><span data-stu-id="50304-149">This section defines how "Client" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
                      },
```

### <a name="contractor"></a><span data-ttu-id="50304-150">Auftragnehmer</span><span class="sxs-lookup"><span data-stu-id="50304-150">Contractor</span></span>

<span data-ttu-id="50304-151">In diesem Abschnitt wird definiert, wie der "Auftragnehmer" auf der Karte angezeigt wird, und der Wert für den jeweiligen Vertrag verwendet.</span><span class="sxs-lookup"><span data-stu-id="50304-151">This section defines how the "Contractor" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
},
```


### <a name="fee-amount"></a><span data-ttu-id="50304-152">Gebührenbetrag</span><span class="sxs-lookup"><span data-stu-id="50304-152">Fee Amount</span></span>

<span data-ttu-id="50304-153">In diesem Abschnitt wird definiert, wie der "Gebührenbetrag" auf der Karte angezeigt wird, und der Wert für den jeweiligen Vertrag verwendet.</span><span class="sxs-lookup"><span data-stu-id="50304-153">This section defines how the "Fee Amount" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Fee amount",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$FeeAmount]"
                      },
```



### <a name="classification-date"></a><span data-ttu-id="50304-154">Klassifizierungsdatum</span><span class="sxs-lookup"><span data-stu-id="50304-154">Classification date</span></span>

<span data-ttu-id="50304-155">In diesem Abschnitt wird definiert, wie "Klassifizierung" auf der Karte angezeigt wird, und der Wert für den jeweiligen Vertrag verwendet.</span><span class="sxs-lookup"><span data-stu-id="50304-155">This section defines how "Classification" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Classified",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$PrimeLastClassified]"
                      }
```

## <a name="next-step"></a><span data-ttu-id="50304-156">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="50304-156">Next step</span></span>

[<span data-ttu-id="50304-157">Schritt 3. Verwenden Power Automate, um Ihren Fluss zum Verarbeiten Ihrer Verträge zu erstellen</span><span class="sxs-lookup"><span data-stu-id="50304-157">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
