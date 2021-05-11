---
title: Vorbereiten einer CSV-Datei für eine ID-Liste Inhaltssuche
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
description: Verwenden Sie eine CSV-Datei aus einer vorhandenen Inhaltssuche, um eine ID-Listensuche zu erstellen, die bestimmte E-Mail-Elemente zurückgibt.
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311538"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="4fdab-103">Vorbereiten einer CSV-Datei für eine ID-Liste Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="4fdab-103">Prepare a CSV file for an ID list Content search</span></span>

<span data-ttu-id="4fdab-104">Sie können nach bestimmten Postfach-E-Mail-Nachrichten und anderen Postfachelementen mithilfe einer Liste von Exchange suchen.</span><span class="sxs-lookup"><span data-stu-id="4fdab-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="4fdab-105">Um eine ID-Listensuche zu erstellen, übermitteln Sie eine durch Kommata getrennte Wertedatei (CSV), in der Sie die spezifischen Postfachelemente angeben, nach denen Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="4fdab-105">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="4fdab-106">Für diese CSV-Datei verwenden Sie die **Results.csv-Datei** oder die **Nicht indizierte** Items.csv-Datei, die enthalten sind, wenn Sie die Inhaltssuchergebnisse exportieren oder einen Inhaltssuchbericht aus einer vorhandenen Inhaltssuche exportieren.</span><span class="sxs-lookup"><span data-stu-id="4fdab-106">For this CSV file, you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content search results or export a Content search report from an existing Content search.</span></span> <span data-ttu-id="4fdab-107">Anschließend bearbeiten Sie eine dieser Dateien, um die zu suchende bestimmten Elemente anzugeben, eine neue ID-Listensuche zu erstellen und die CSV-Datei zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="4fdab-107">Then you edit one of these files to indicate the specific items to search for, create a new ID list search, and submit the CSV file.</span></span>

<span data-ttu-id="4fdab-108">**Warum eine ID-Listensuche erstellen?**</span><span class="sxs-lookup"><span data-stu-id="4fdab-108">**Why create an ID list search?**</span></span> <span data-ttu-id="4fdab-109">Wenn Sie nicht ermitteln können, ob ein Element auf eine eDiscovery-Anforderung basierend auf den Metadaten in den **Results.csv-** oder **Nicht indizierten Items.csv-Dateien** reagiert, können Sie eine ID-Listensuche verwenden, um dieses Element zu suchen, in der Vorschau anzuzeigen und dann zu exportieren, um festzustellen, ob es auf den untersuchten Fall reagiert.</span><span class="sxs-lookup"><span data-stu-id="4fdab-109">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="4fdab-110">Id-Listensuchen werden in der Regel verwendet, um nach einer bestimmten Gruppe nicht indizierter Elemente zu suchen und diese zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="4fdab-110">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

<span data-ttu-id="4fdab-111">Hier finden Sie eine kurze Übersicht über den Prozess zum Erstellen einer ID-Listensuche.</span><span class="sxs-lookup"><span data-stu-id="4fdab-111">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="4fdab-112">Erstellen und ausführen Sie eine neue Suche im Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="4fdab-112">Create and run a new search in the Microsoft 365 compliance center.</span></span>

2. <span data-ttu-id="4fdab-113">Exportieren Sie die Inhaltssuchergebnisse oder den Inhaltssuchbericht.</span><span class="sxs-lookup"><span data-stu-id="4fdab-113">Export the content search results or the content search report.</span></span> <span data-ttu-id="4fdab-114">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="4fdab-114">For more information, see:</span></span>

    - [<span data-ttu-id="4fdab-115">Ergebnisse der Inhaltssuche exportieren </span><span class="sxs-lookup"><span data-stu-id="4fdab-115">Export Content search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="4fdab-116">Bericht zur Inhaltssuche exportieren</span><span class="sxs-lookup"><span data-stu-id="4fdab-116">Export a Content search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="4fdab-117">Bearbeiten Sie **Results.csv** oder **Nicht indizierte Items.csv,** und identifizieren Sie die bestimmten Postfachelemente, die in die ID-Listensuche aufgenommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4fdab-117">Edit the **Results.csv** file or **Unindexed Items.csv** file and identify the specific mailbox items to include in the ID list search.</span></span> <span data-ttu-id="4fdab-118">Weitere Informationen [finden Sie in](#prepare-the-csv-file-for-an-id-list-search) den Anweisungen zum Vorbereiten einer CSV-Datei für eine ID-Listensuche.</span><span class="sxs-lookup"><span data-stu-id="4fdab-118">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="4fdab-119">Erstellen Sie eine neue ID-Listensuche (siehe [Anweisungen),](#create-an-id-list-search)und übermitteln Sie die vorbereitete CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="4fdab-119">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="4fdab-120">Die erstellte Suchabfrage sucht nur nach den in der CSV-Datei ausgewählten Elementen.</span><span class="sxs-lookup"><span data-stu-id="4fdab-120">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="4fdab-121">Id-Listensuchen werden nur für Postfachelemente unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4fdab-121">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="4fdab-122">Sie können nicht nach Dokumenten SharePoint und OneDrive in einer ID-Listensuche suchen.</span><span class="sxs-lookup"><span data-stu-id="4fdab-122">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="4fdab-123">Vorbereiten der CSV-Datei für eine ID-Listensuche</span><span class="sxs-lookup"><span data-stu-id="4fdab-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="4fdab-124">Nachdem Sie die Suchergebnisse oder den Bericht für eine Suche exportiert haben, führen Sie die folgenden Schritte aus, um die CSV-Datei für eine ID-Listensuche vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="4fdab-124">After you export the search results or report for a search, perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="4fdab-125">Diese CSV-Datei identifiziert jedes Element in der ID-Listensuche.</span><span class="sxs-lookup"><span data-stu-id="4fdab-125">This CSV file identifies every item in the ID list search.</span></span>

<span data-ttu-id="4fdab-126">Sie können eine CSV-Datei aus einer Suche verwenden, die SharePoint websites und OneDrive-Konten enthielt, Aber Sie können nur Postfachelemente für eine ID-Listensuche auswählen.</span><span class="sxs-lookup"><span data-stu-id="4fdab-126">You can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can only select mailbox items for an ID list search.</span></span> <span data-ttu-id="4fdab-127">Wenn Sie ein Dokument in SharePoint oder OneDrive auswählen, kann die CSV-Datei beim Erstellen einer ID-Listensuche nicht validiert werden.</span><span class="sxs-lookup"><span data-stu-id="4fdab-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="4fdab-128">Öffnen Sie **Results.csv** **oder Nicht indizierte Items.csv** in Excel.</span><span class="sxs-lookup"><span data-stu-id="4fdab-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="4fdab-129">Geben Sie in der **Spalte** Ausgewählt in der Zelle **Ja** ein, die dem Element entspricht, nach dem Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="4fdab-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="4fdab-130">Wiederholen Sie diesen Schritt für jedes Element, nach dem Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="4fdab-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4fdab-131">Wenn Sie die CSV-Datei in Excel öffnen, wurde das Datenformat für die Spalte **Dokument-ID** möglicherweise in **Allgemein geändert.**</span><span class="sxs-lookup"><span data-stu-id="4fdab-131">When you open the CSV file in Excel, the data format for the **Document ID** column may have been changed to **General**.</span></span> <span data-ttu-id="4fdab-132">Dies führt dazu, dass die Dokument-ID für ein Element in der wissenschaftlichen Notation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4fdab-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="4fdab-133">Beispielsweise wird die Dokument-ID "481037338205" als "4.81037E+11" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4fdab-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11".</span></span> <span data-ttu-id="4fdab-134">In diesem Fall müssen Sie die nächsten Schritte ausführen, um das Datenformat der Spalte **Dokument-ID** in **Zahl** zu ändern, um das richtige Format für die Dokument-ID wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="4fdab-134">If this happens, you have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="4fdab-135">Wenn Sie dies nicht tun, wird bei der ID-Listensuche, die die CSV-Datei verwendet, ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4fdab-135">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="4fdab-136">Klicken Sie mit der rechten Maustaste auf die gesamte **Spalte Dokument-ID,** und wählen Sie **Zellen formatieren aus.**</span><span class="sxs-lookup"><span data-stu-id="4fdab-136">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="4fdab-137">Klicken Sie **im Feld Kategorie** auf **Nummer**.</span><span class="sxs-lookup"><span data-stu-id="4fdab-137">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="4fdab-138">Ändern Sie die Anzahl der Dezimalstellen in **0**, und klicken Sie dann auf **OK,** um Die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4fdab-138">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="4fdab-139">Beachten Sie, dass die Werte in der Spalte Dokument-ID in Zahlen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4fdab-139">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="4fdab-140">Im Folgenden finden Sie ein Beispiel für eine CSV-Datei, die für eine ID-Listeninhaltssuche übermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4fdab-140">Here's an example of a CSV file that's ready to be submitted for an ID list content search.</span></span>

    ![Beispiel für eine CSV-Datei für eine gezielte Inhaltssuche](../media/SearchIDListCSVFile.png)

6. <span data-ttu-id="4fdab-142">Speichern Sie die CSV-Datei, oder verwenden **Sie Speichern unter,** um die Datei mit einem anderen Dateinamen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4fdab-142">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="4fdab-143">Achten Sie in beiden Fällen darauf, die Datei im CSV-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4fdab-143">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="4fdab-144">Erstellen einer ID-Listensuche</span><span class="sxs-lookup"><span data-stu-id="4fdab-144">Create an ID list search</span></span>

<span data-ttu-id="4fdab-145">Im nächsten Schritt erstellen Sie eine neue ID-Listensuche und übermitteln die CSV-Datei, die Sie im vorherigen Schritt vorbereitet haben.</span><span class="sxs-lookup"><span data-stu-id="4fdab-145">The next step is to create a new ID list search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4fdab-146">Sie sollten eine ID-Listensuche nicht mehr als 2 Tage nach dem Exportieren der Suchergebnisse oder Berichte erstellen.</span><span class="sxs-lookup"><span data-stu-id="4fdab-146">You should create an ID list search no more than 2 days after exporting the search results or report.</span></span> <span data-ttu-id="4fdab-147">Wenn die Suchergebnisse oder berichte, in denen vor mehr als 2 Tagen exportiert wurden, sollten Sie die Suchergebnisse oder den Bericht erneut exportieren, um aktualisierte CSV-Dateien zu generieren.</span><span class="sxs-lookup"><span data-stu-id="4fdab-147">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="4fdab-148">Anschließend können Sie eine der aktualisierten CSV-Dateien vorbereiten und verwenden, um eine ID-Listensuche zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4fdab-148">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="4fdab-149">Gehen Sie auf <https://compliance.microsoft.com>, und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="4fdab-149">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="4fdab-150">Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Centers auf **Alle anzeigen** und dann auf **Inhaltssuche**.</span><span class="sxs-lookup"><span data-stu-id="4fdab-150">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="4fdab-151">Klicken Sie **auf der Seite** Inhaltssuche auf Suche nach **ID-Liste**.</span><span class="sxs-lookup"><span data-stu-id="4fdab-151">On the **Content search** page, click **Search by ID List**.</span></span>

4. <span data-ttu-id="4fdab-152">Nennen Sie **im Flyout** Suche nach ID-Liste die Suche (und beschreiben Sie sie optional), und klicken Sie dann auf **Durchsuchen,** und wählen Sie die CSV-Datei aus, die Sie im vorherigen Schritt vorbereitet haben.</span><span class="sxs-lookup"><span data-stu-id="4fdab-152">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="4fdab-153">Microsoft 365 versucht, die CSV-Datei zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4fdab-153">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="4fdab-154">Wenn die Überprüfung nicht erfolgreich war, wird eine Fehlermeldung angezeigt, die Ihnen bei der Problembehandlung der Überprüfungsfehler helfen kann.</span><span class="sxs-lookup"><span data-stu-id="4fdab-154">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="4fdab-155">Die CSV-Datei muss erfolgreich überprüft werden, um eine ID-Listensuche zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4fdab-155">The CSV file has to be successfully validated to create an ID list search.</span></span>

5. <span data-ttu-id="4fdab-156">Nachdem die CSV-Datei erfolgreich überprüft wurde, klicken Sie auf **Suchen,** um die ID-Listensuche zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4fdab-156">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="4fdab-157">Hier ist ein Beispiel für die Flyoutseite aus einer ID-Listensuche, die die generierte Abfrage und die geschätzte Anzahl von Suchergebnissen zeigt.</span><span class="sxs-lookup"><span data-stu-id="4fdab-157">Here's an example of the flyout page from an ID list search that shows the query that's generated and the estimated number of search results.</span></span>

    ![Suchabfrage für id list search](../media/SearchIDListFlyout.png)

    <span data-ttu-id="4fdab-159">Die Anzahl der geschätzten Elemente, die in Statistiken für die ID-Suche angezeigt werden, sollte mit der Anzahl der Elemente übereinstimmen, die Sie in der CSV-Datei ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4fdab-159">The number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

6. <span data-ttu-id="4fdab-160">Anzeigen oder Exportieren der von der ID-Listensuche zurückgegebenen Elemente.</span><span class="sxs-lookup"><span data-stu-id="4fdab-160">Preview or export the items returned by the ID list search.</span></span>

## <a name="more-information"></a><span data-ttu-id="4fdab-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4fdab-161">More information</span></span>

<span data-ttu-id="4fdab-162">Wenn Sie ein Postfach nach dem Erstellen einer ID-Listensuche verschieben, gibt die Abfrage für die Suche die angegebenen Elemente nicht zurück.</span><span class="sxs-lookup"><span data-stu-id="4fdab-162">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="4fdab-163">Das liegt daran, dass die **DocumentId-Eigenschaft** für Postfachelemente geändert wird, wenn ein Postfach verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="4fdab-163">That's because the **DocumentId** property for mailbox items is changed when a mailbox is moved.</span></span> <span data-ttu-id="4fdab-164">In der seltenen Instanz, in der ein Postfach nach dem Erstellen einer ID-Listensuche verschoben wird, sollten Sie eine neue Inhaltssuche erstellen (oder die Suchergebnisse für eine vorhandene Suche aktualisieren) und dann die Suchergebnisse oder den Bericht exportieren, um aktualisierte CSV-Dateien zu generieren, die zum Erstellen einer neuen ID-Listensuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4fdab-164">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new Content search (or update the search results for an existing search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
