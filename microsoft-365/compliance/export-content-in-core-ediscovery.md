---
title: Exportieren und Herunterladen von Inhalten aus einem Core eDiscovery-Fall
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Beschreibt das Exportieren und Herunterladen von Inhalten aus einem Core eDiscovery-Fall in Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310842"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="1aa8f-103">Exportieren von Inhalten aus einem Core eDiscovery-Fall</span><span class="sxs-lookup"><span data-stu-id="1aa8f-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="1aa8f-104">Nachdem eine Einem Core eDiscovery-Fall zugeordnete Suche erfolgreich ausgeführt wurde, können Sie die Suchergebnisse exportieren.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-104">After a search associated with a Core eDiscovery case is successfully run, you can export the search results.</span></span> <span data-ttu-id="1aa8f-105">Beim Exportieren von Suchergebnissen werden Postfachelemente in PST-Dateien oder als einzelne Nachrichten heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="1aa8f-106">Wenn Sie Inhalte aus SharePoint und OneDrive for Business exportieren, werden Kopien von systemeigenen Office und anderen Dokumenten exportiert.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="1aa8f-107">Eine Results.csv, die Informationen zu jedem exportierten Element enthält, und eine Manifestdatei (im XML-Format), die Informationen zu jedem Suchergebnis enthält, wird ebenfalls exportiert.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
## <a name="export-search-results"></a><span data-ttu-id="1aa8f-108">Exportieren von Suchergebnissen</span><span class="sxs-lookup"><span data-stu-id="1aa8f-108">Export search results</span></span>

1. <span data-ttu-id="1aa8f-109">Wechseln Sie zu, und melden Sie sich mit den Anmeldeinformationen für ein Benutzerkonto an, dem die entsprechenden [https://compliance.microsoft.com](https://compliance.microsoft.com) eDiscovery-Berechtigungen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-109">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="1aa8f-110">Klicken Sie im linken Navigationsbereich Microsoft 365 Compliance Center auf Alle **anzeigen,** und klicken Sie dann auf **eDiscovery > Core**.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-110">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="1aa8f-111">Klicken Sie auf der Seite **Core eDiscovery** auf den Namen des Falls, in dem Sie den Haltebereich erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-111">On the **Core eDiscovery** page, click the name of the case that you want to create the hold in.</span></span>

4. <span data-ttu-id="1aa8f-112">Klicken Sie **auf der** Startseite für den Fall auf **die** Registerkarte Suchen.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-112">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="1aa8f-113">Klicken Sie **im** Menü Aktionen unten auf der Flyoutseite auf **Ergebnisse exportieren.**</span><span class="sxs-lookup"><span data-stu-id="1aa8f-113">On the **Actions** menu at the bottom of the flyout page, click **Export results**.</span></span>

   ![Export results option in Actions menu](../media/ActionMenuExportResults.png)

   <span data-ttu-id="1aa8f-115">Der Workflow zum Exportieren der Ergebnisse einer Suche, die einem Core eDiscovery-Fall zugeordnet ist, entspricht dem Exportieren der Suchergebnisse für eine Suche auf der Seite **Inhaltssuche.**</span><span class="sxs-lookup"><span data-stu-id="1aa8f-115">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="1aa8f-116">Schrittweise Anweisungen finden Sie unter [Exportieren von Inhaltssuchergebnissen](export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="1aa8f-116">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="1aa8f-117">Beim Exportieren von Suchergebnissen haben Sie die Möglichkeit, die Deduplizierung zu aktivieren, sodass nur eine Kopie einer E-Mail-Nachricht exportiert wird, obwohl in den durchsuchten Postfächern möglicherweise mehrere Instanzen derselben Nachricht gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-117">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="1aa8f-118">Weitere Informationen zur Deduplizierung und zur Ermittlung doppelter Elemente finden Sie unter [Deduplizierung in eDiscovery-Suchergebnissen.](de-duplication-in-ediscovery-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="1aa8f-118">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

   <span data-ttu-id="1aa8f-119">Nachdem Sie den Export gestartet haben, werden die Suchergebnisse zum Herunterladen vorbereitet, d. h. sie werden an einen von Microsoft bereitgestellten Azure Storage in der Microsoft Cloud übertragen.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-119">After you start the export, the search results are prepared for downloading, which means they are transferred to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="1aa8f-120">Klicken Sie **in der Fall** auf die Registerkarte Exporte, um die Liste der Exportaufträge anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-120">Click the **Exports** tab in the case to display the list of export jobs.</span></span>
  
   ![Exportieren von Aufträgen auf der Registerkarte Export im Fall Core eDiscovery](../media/CoreeDiscoveryExport.png)

   <span data-ttu-id="1aa8f-122">Möglicherweise müssen Sie auf **Aktualisieren klicken,** um die Liste der Exportaufträge so zu aktualisieren, dass der erstellte Exportauftrag angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-122">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="1aa8f-123">Exportaufträge haben denselben Namen wie die entsprechende Suche mit **_Export** an den Suchnamen angefügt.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-123">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="1aa8f-124">Klicken Sie auf den exportauftrag, den Sie erstellt haben, um Statusinformationen auf der Flyoutseite anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-124">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="1aa8f-125">Diese Informationen enthalten den Prozentsatz der Elemente, die an den Speicherort Azure Storage wurden.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-125">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="1aa8f-126">Nachdem alle Elemente übertragen wurden, klicken Sie auf **Ergebnisse herunterladen,** um die Suchergebnisse auf Ihren lokalen Computer herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-126">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="1aa8f-127">Weitere Informationen zum Herunterladen von Suchergebnissen finden Sie unter Schritt 2 unter [Exportieren von Inhaltssuchergebnissen.](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="1aa8f-127">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

### <a name="more-information-about-exporting-searches-from-a-case"></a><span data-ttu-id="1aa8f-128">Weitere Informationen zum Exportieren von Suchen aus einem Fall</span><span class="sxs-lookup"><span data-stu-id="1aa8f-128">More information about exporting searches from a case</span></span>

- <span data-ttu-id="1aa8f-129">Weitere Informationen zu den Exportdateien, die beim Exportieren von Suchergebnissen enthalten sind, finden Sie unter [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="1aa8f-129">For more information about the export files that are included when you export search results, see [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).</span></span>

- <span data-ttu-id="1aa8f-130">Wenn Sie den Export neu starten, wirken sich alle Änderungen an den Abfragen der Suchanfragen, aus der der Exportauftrag ist, nicht auf die abgerufenen Suchergebnisse aus.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-130">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="1aa8f-131">Wenn Sie einen Export neu starten, wird derselbe kombinierte Suchabfrageauftrag, der beim Erstellen des Exportauftrags ausgeführt wurde, erneut ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-131">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="1aa8f-132">Wenn Sie einen Export neu starten, werden die Suchergebnisse, die an den Speicherort Azure Storage, die vorherigen Ergebnisse überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-132">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="1aa8f-133">Die vorherigen kopierten Ergebnisse stehen nicht zum Herunterladen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-133">The previous results that were copied won't be available to be downloaded.</span></span>
