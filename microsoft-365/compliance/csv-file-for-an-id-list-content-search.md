---
title: Erstellen einer CSV-Datei für eine Inhaltssuche anhand der ID-Liste
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: Verwenden Sie CSV-Dateien aus einer vorhandenen Inhaltssuche, um eine ID-Listensuche zu erstellen, die bestimmte e-Mail-Nachrichten zurückgibt.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817974"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="131f0-103">Erstellen einer CSV-Datei für eine Inhaltssuche anhand der ID-Liste</span><span class="sxs-lookup"><span data-stu-id="131f0-103">Prepare a CSV file for an ID list Content Search</span></span>

<span data-ttu-id="131f0-104">Sie können mithilfe einer Liste von Exchange-IDs nach bestimmten Post Fachnachrichten und anderen Postfachelementen suchen.</span><span class="sxs-lookup"><span data-stu-id="131f0-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="131f0-105">Um eine ID-Listensuche (formell als gezielte Suche bezeichnet) zu erstellen, senden Sie eine CSV-Datei (Comma Separated Value), die die zu suchenden Postfachelemente identifiziert.</span><span class="sxs-lookup"><span data-stu-id="131f0-105">To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="131f0-106">Für diese CSV-Datei verwenden Sie die **Results.csv** Datei oder die nicht **Indexierte Items.csv** Datei, die beim Exportieren der Inhalts Suchergebnisse oder beim Exportieren eines Inhalts Suchberichts aus einer vorhandenen Inhaltssuche enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="131f0-106">For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search.</span></span> <span data-ttu-id="131f0-107">Bearbeiten Sie dann eine dieser Dateien, um anzugeben, nach welchen Elementen gesucht werden soll, und erstellen Sie dann eine neue ID-Listensuche, und senden Sie die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="131f0-107">Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span>

<span data-ttu-id="131f0-108">Im folgenden finden Sie eine kurze Übersicht über den Prozess zum Erstellen einer ID-Listensuche.</span><span class="sxs-lookup"><span data-stu-id="131f0-108">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="131f0-109">Erstellen Sie eine neue oder geführte Inhaltssuche im Security & Compliance Center, und führen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="131f0-109">Create and run a new or guided Content Search in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="131f0-110">Exportieren Sie die Inhalts Suchergebnisse, oder exportieren Sie den Bericht zur Inhaltssuche.</span><span class="sxs-lookup"><span data-stu-id="131f0-110">Export the content search results or export the content search report.</span></span> <span data-ttu-id="131f0-111">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="131f0-111">For more information, see:</span></span>

    - [<span data-ttu-id="131f0-112">Exportieren von Inhaltssuchergebnissen </span><span class="sxs-lookup"><span data-stu-id="131f0-112">Export Content Search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="131f0-113">Exportieren eines Inhaltssuchberichts</span><span class="sxs-lookup"><span data-stu-id="131f0-113">Export a Content Search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="131f0-114">Bearbeiten Sie die **Results.csv** Datei oder den nicht **indizierten Items.csv** , und identifizieren Sie die spezifischen Postfachelemente, die in die ID-Listensuche einbezogen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="131f0-114">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search.</span></span> <span data-ttu-id="131f0-115">Lesen Sie die [Anweisungen](#prepare-the-csv-file-for-an-id-list-search) zum Vorbereiten einer CSV-Datei für eine ID-Listensuche.</span><span class="sxs-lookup"><span data-stu-id="131f0-115">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="131f0-116">Erstellen Sie eine neue ID-Listensuche (Lesen Sie die [Anweisungen](#create-an-id-list-search)), und übermitteln Sie die vorbereitete CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="131f0-116">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="131f0-117">Die erstellte Suchabfrage sucht nur nach den Elementen, die in der CSV-Datei ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="131f0-117">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="131f0-118">Die Suche von ID-Listen wird nur für Postfachelemente unterstützt.</span><span class="sxs-lookup"><span data-stu-id="131f0-118">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="131f0-119">Sie können nicht nach SharePoint-und OneDrive-Dokumenten in einer ID-Listensuche suchen.</span><span class="sxs-lookup"><span data-stu-id="131f0-119">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

 <span data-ttu-id="131f0-120">**Gründe für die Erstellung einer ID-Listensuche**</span><span class="sxs-lookup"><span data-stu-id="131f0-120">**Why create an ID list search?**</span></span> <span data-ttu-id="131f0-121">Wenn Sie nicht ermitteln können, ob ein Element auf einer eDiscovery-Anforderung basierend auf den Metadaten in den **Results.csv** -oder nicht **indizierten Items.csv** -Dateien reagiert, können Sie eine ID-Listensuche verwenden, um das Element zu suchen, in der Vorschau anzuzeigen und dann zu exportieren, um zu ermitteln, ob es auf den Fall reagiert, den Sie untersuchen.</span><span class="sxs-lookup"><span data-stu-id="131f0-121">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="131f0-122">ID-Listensuche wird in der Regel zum Suchen und Zurückgeben einer bestimmten Gruppe von nicht indizierten Elementen verwendet.</span><span class="sxs-lookup"><span data-stu-id="131f0-122">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="131f0-123">Vorbereiten der CSV-Datei für eine ID-Listensuche</span><span class="sxs-lookup"><span data-stu-id="131f0-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="131f0-124">Nachdem Sie die Suchergebnisse oder den Bericht für eine Inhaltssuche exportiert haben, können Sie die folgenden Schritte ausführen, um die CSV-Datei für eine ID-Listensuche vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="131f0-124">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="131f0-125">In dieser CSV-Datei werden alle Elemente in der ID-Listensuche identifiziert.</span><span class="sxs-lookup"><span data-stu-id="131f0-125">This CSV file will identify every item in the ID list search.</span></span>

<span data-ttu-id="131f0-126">Beachten Sie, dass Sie eine CSV-Datei aus einer Suche verwenden können, die SharePoint-Websites und OneDrive-Konten enthielt, aber Sie können *nur* Postfachelemente für eine ID-Listensuche auswählen.</span><span class="sxs-lookup"><span data-stu-id="131f0-126">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search.</span></span> <span data-ttu-id="131f0-127">Wenn Sie ein Dokument in SharePoint oder OneDrive auswählen, wird die Überprüfung der CSV-Datei beim Erstellen einer ID-Listensuche nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="131f0-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="131f0-128">Öffnen Sie die Items.csvDatei **Results.csv** oder nicht **indiziert** in Excel.</span><span class="sxs-lookup"><span data-stu-id="131f0-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="131f0-129">Geben Sie in der **ausgewählten** Spalte **Ja** in die Zelle ein, die dem Element entspricht, nach dem Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="131f0-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="131f0-130">Wiederholen Sie diesen Schritt für jedes Element, nach dem Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="131f0-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="131f0-131">Wenn Sie die CSV-Datei in Excel öffnen, wird das Datenformat für die **Dokument-ID-** Spalte in " **Allgemein**" geändert.</span><span class="sxs-lookup"><span data-stu-id="131f0-131">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**.</span></span> <span data-ttu-id="131f0-132">Dies führt dazu, dass die Dokument-ID für ein Element in der wissenschaftlichen Notation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="131f0-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="131f0-133">Beispielsweise wird die Dokument-ID "481037338205" als "4.81037 e + 11" angezeigt. Sie müssen die nächsten Schritte durchführen, um das Datenformat der Spalte " **Dokument-ID** " in " **Number** " zu ändern, um das richtige Format für die Dokument-ID wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="131f0-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="131f0-134">Wenn Sie dies nicht tun, schlägt die ID-Listensuche, in der die CSV-Datei verwendet wird, fehl.</span><span class="sxs-lookup"><span data-stu-id="131f0-134">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="131f0-135">Klicken Sie mit der rechten Maustaste auf die gesamte Spalte **Dokument-ID** , und wählen Sie **Zellen formatieren**aus.</span><span class="sxs-lookup"><span data-stu-id="131f0-135">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="131f0-136">Klicken Sie im Feld **Kategorie** auf **Zahl**.</span><span class="sxs-lookup"><span data-stu-id="131f0-136">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="131f0-137">Ändern Sie die Anzahl der Dezimalstellen in **0**, und klicken Sie dann auf **OK** , um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="131f0-137">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="131f0-138">Beachten Sie, dass die Werte in der Spalte "Dokument-ID" in Zahlen geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="131f0-138">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="131f0-139">Im folgenden finden Sie ein Beispiel für eine CSV-Datei, die für eine ID-Listeninhalts Suche gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="131f0-139">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>

    ![Beispiel für eine CSV-Datei für eine gezielte Inhaltssuche](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. <span data-ttu-id="131f0-141">Speichern Sie die CSV-Datei, oder **Speichern Sie die** Datei unter anderem Dateinamen speichern.</span><span class="sxs-lookup"><span data-stu-id="131f0-141">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="131f0-142">In beiden Fällen müssen Sie die Datei im CSV-Format speichern.</span><span class="sxs-lookup"><span data-stu-id="131f0-142">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="131f0-143">Erstellen einer ID-Listensuche</span><span class="sxs-lookup"><span data-stu-id="131f0-143">Create an ID list search</span></span>

<span data-ttu-id="131f0-144">Im nächsten Schritt erstellen Sie eine neue ID-Listeninhalts Suche und übermitteln die CSV-Datei, die Sie im vorherigen Schritt vorbereitet haben.</span><span class="sxs-lookup"><span data-stu-id="131f0-144">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="131f0-145">Sie sollten eine ID-Listensuche nicht länger als 2 Tage nach dem Exportieren der Ergebnisse oder des Berichts aus einer Inhaltssuche erstellen.</span><span class="sxs-lookup"><span data-stu-id="131f0-145">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search.</span></span> <span data-ttu-id="131f0-146">Wenn die Suchergebnisse oder der Bericht vor mehr als 2 Tagen exportiert wurden, sollten Sie die Suchergebnisse oder den Bericht erneut exportieren, um aktualisierte CSV-Dateien zu generieren.</span><span class="sxs-lookup"><span data-stu-id="131f0-146">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="131f0-147">Anschließend können Sie eine der aktualisierten CSV-Dateien vorbereiten und Sie zum Erstellen einer ID-Listensuche verwenden.</span><span class="sxs-lookup"><span data-stu-id="131f0-147">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="131f0-148">Wechseln Sie im Security & Compliance Center zu **Such** \> **Inhaltssuche**.</span><span class="sxs-lookup"><span data-stu-id="131f0-148">In the Security & Compliance Center, go to **Search** \> **Content search**.</span></span>

2. <span data-ttu-id="131f0-149">Klicken Sie auf der Seite **Suchen** auf den Pfeil neben ![ Symbol ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **neue Suche**hinzufügen, und klicken Sie dann auf **nach ID-Liste suchen**.</span><span class="sxs-lookup"><span data-stu-id="131f0-149">On the **Search** page, click the arrow next to ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>

    ![Klicken Sie in der Dropdownliste neue Suche auf nach ID-Liste suchen.](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. <span data-ttu-id="131f0-151">Geben Sie im Flyout **Suche nach ID-Liste** den Namen der Suche ein (und beschreiben Sie Sie optional), und klicken Sie dann auf **Durchsuchen** , und wählen Sie dann die CSV-Datei aus, die Sie im vorherigen Schritt vorbereitet haben.</span><span class="sxs-lookup"><span data-stu-id="131f0-151">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="131f0-152">Microsoft 365 versucht, die CSV-Datei zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="131f0-152">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="131f0-153">Wenn die Überprüfung nicht erfolgreich ist, wird eine Fehlermeldung angezeigt, die Ihnen helfen kann, die Validierungsfehler zu beheben.</span><span class="sxs-lookup"><span data-stu-id="131f0-153">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="131f0-154">Die CSV-Datei muss erfolgreich überprüft werden, um eine ID-Listensuche zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="131f0-154">The CSV file has to be successfully validated to create an ID list search.</span></span>

4. <span data-ttu-id="131f0-155">Nachdem die CSV-Datei erfolgreich überprüft wurde, klicken Sie auf **Suchen** , um die ID-Listensuche zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="131f0-155">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="131f0-156">Im folgenden finden Sie ein Beispiel für die geschätzten Suchergebnisse und die Abfrage, die für eine ID-Listensuche generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="131f0-156">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>

    ![Suchabfrage für eine gezielte Inhaltssuche im Detailbereich](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    <span data-ttu-id="131f0-158">Beachten Sie, dass die Anzahl der geschätzten Elemente, die in Statistik für die ID-Suche angezeigt werden, mit der Anzahl der Elemente übereinstimmen sollte, die Sie in der CSV-Datei ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="131f0-158">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

5. <span data-ttu-id="131f0-159">Vorschau oder Exportieren der Elemente, die von der ID-Listensuche zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="131f0-159">Preview or export the items returned by the ID list search.</span></span>

> [!NOTE]
> <span data-ttu-id="131f0-160">Wenn Sie ein Postfach nach dem Erstellen einer ID-Listensuche migrieren, gibt die Abfrage für die Suche nicht die angegebenen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="131f0-160">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="131f0-161">Das liegt daran, dass die **Document** -Eigenschaft für Postfachelemente geändert wird, wenn ein Postfach verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="131f0-161">That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved.</span></span> <span data-ttu-id="131f0-162">In der seltenen Instanz, in der ein Postfach verschoben wird, nachdem Sie eine ID-Listensuche erstellt haben, sollten Sie eine neue Inhaltssuche erstellen (oder die Suchergebnisse für die vorhandene Inhaltssuche aktualisieren) und dann die Suchergebnisse oder den Bericht exportieren, um aktualisierte CSV-Dateien zu generieren, mit denen eine neue ID-Listensuche erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="131f0-162">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
