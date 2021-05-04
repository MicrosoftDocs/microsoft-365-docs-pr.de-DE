---
title: Exportieren eines Berichts für die Inhaltssuche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Anstatt die tatsächlichen Ergebnisse einer Inhaltssuche im Security & Compliance Center in Office 365 zu exportieren, können Sie einen Suchergebnisseinbericht exportieren. Der Bericht enthält eine Zusammenfassung der Suchergebnisse und ein Dokument mit detaillierten Informationen zu jedem element, das exportiert werden würde.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fec6e441458ad7429067a1314a7aec3824aff11a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760153"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="92d02-104">Exportieren eines Berichts für die Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="92d02-104">Export a Content Search report</span></span>

<span data-ttu-id="92d02-105">Anstatt den vollständigen Satz von Suchergebnissen aus einer Inhaltssuche im Security & Compliance Center (und aus einer Inhaltssuche, die einem eDiscovery-Fall zugeordnet ist) zu exportieren, können Sie dieselben Berichte exportieren, die beim Exportieren von Suchergebnissen generiert werden.</span><span class="sxs-lookup"><span data-stu-id="92d02-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="92d02-106">Wenn Sie einen Bericht exportieren, wird er in einen Ordner heruntergeladen, der denselben Namen wie die Inhaltssuche hat, der jedoch mit *_ReportsOnly.*</span><span class="sxs-lookup"><span data-stu-id="92d02-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="92d02-107">Wenn die Inhaltssuche beispielsweise den Namen  *ContosoCase0815* hat, wird der Bericht in einen Ordner mit dem Namen *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="92d02-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="92d02-108">Eine Liste der Dokumente, die im Bericht enthalten sind, finden Sie unter [What's included in the report](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="92d02-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="assign-roles-and-check-system-requirements"></a><span data-ttu-id="92d02-109">Zuweisen von Rollen und Überprüfen von Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="92d02-109">Assign roles and check system requirements</span></span>

- <span data-ttu-id="92d02-110">Zum Exportieren eines Inhaltssuchberichts muss Ihnen die Verwaltungsrolle Compliancesuche im Security & Compliance Center zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="92d02-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="92d02-111">Diese Rolle wird standardmäßig den integrierten Rollengruppen eDiscovery Manager und Organization Management zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="92d02-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="92d02-112">Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="92d02-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="92d02-113">Wenn Sie einen Bericht exportieren, werden die Daten vorübergehend in einem eindeutigen Azure Storage in der Microsoft Cloud gespeichert, bevor sie auf Ihren lokalen Computer heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="92d02-113">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="92d02-114">Stellen Sie sicher, dass Ihre Organisation eine Verbindung mit dem Endpunkt in Azure herstellen kann, der **\* .blob.core.windows.net** ist (der Platzhalter stellt einen eindeutigen Bezeichner für Ihren Export dar).</span><span class="sxs-lookup"><span data-stu-id="92d02-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="92d02-115">Die Suchergebnisse werden zwei Wochen nach der Azure Storage aus dem Bereich gelöscht.</span><span class="sxs-lookup"><span data-stu-id="92d02-115">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span>

- <span data-ttu-id="92d02-116">Der Computer, den Sie zum Exportieren der Suchergebnisse verwenden, muss die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="92d02-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="92d02-117">Neueste Version von Windows (32-Bit- oder 64-Bit-Version)</span><span class="sxs-lookup"><span data-stu-id="92d02-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="92d02-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="92d02-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="92d02-119">Sie müssen einen der folgenden unterstützten Browser verwenden, um das eDiscovery Export Tool<sup>1 ausführen zu können:</sup></span><span class="sxs-lookup"><span data-stu-id="92d02-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="92d02-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="92d02-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="92d02-121">ODER</span><span class="sxs-lookup"><span data-stu-id="92d02-121">OR</span></span>

  - <span data-ttu-id="92d02-122">Microsoft Internet Explorer 10 und höher</span><span class="sxs-lookup"><span data-stu-id="92d02-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="92d02-123"><sup>1</sup> Microsoft stellt keine Erweiterungen oder Add-Ons von Drittanbietern für ClickOnce her.</span><span class="sxs-lookup"><span data-stu-id="92d02-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="92d02-124">Das Exportieren von Suchergebnissen mithilfe eines nicht unterstützten Browsers mit Drittanbietererweiterungen oder -add-ons wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="92d02-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="92d02-125"><sup>2</sup> Als Ergebnis der letzten Änderungen an Microsoft Edge ist ClickOnce unterstützung standardmäßig nicht mehr aktiviert.</span><span class="sxs-lookup"><span data-stu-id="92d02-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="92d02-126">Anweisungen zum Aktivieren ClickOnce in Edge finden Sie unter [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="92d02-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="92d02-127">Wenn die geschätzte Gesamtgröße der von einer Inhaltssuche zurückgegebenen Ergebnisse 2 TB überschreitet, schlägt das Exportieren des Berichts fehl.</span><span class="sxs-lookup"><span data-stu-id="92d02-127">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="92d02-128">Um den Bericht erfolgreich zu exportieren, versuchen Sie, den Bereich zu einenten, und führen Sie die Suche erneut aus, sodass die geschätzte Größe der Ergebnisse kleiner als 2 TB ist.</span><span class="sxs-lookup"><span data-stu-id="92d02-128">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="92d02-129">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span><span class="sxs-lookup"><span data-stu-id="92d02-129">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="92d02-130">Weitere Informationen zu Exportbeschränkungen finden Sie [unter Exportieren von Inhaltssuchergebnissen](export-search-results.md#export-limits).</span><span class="sxs-lookup"><span data-stu-id="92d02-130">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="92d02-131">Generieren und Herunterladen eines Inhaltssuchberichts</span><span class="sxs-lookup"><span data-stu-id="92d02-131">Generate and download a Content Search report</span></span>

<span data-ttu-id="92d02-132">Die Schritte zum Generieren und Herunterladen eines Inhaltssuchberichts ähneln dem tatsächlichen Exportieren von Suchergebnissen.</span><span class="sxs-lookup"><span data-stu-id="92d02-132">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="92d02-133">Schritt 1: Generieren des Berichts für den Export</span><span class="sxs-lookup"><span data-stu-id="92d02-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="92d02-134">Der erste Schritt besteht in der Vorbereitung des Berichts für das Herunterladen auf Ihren Computer, der exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="92d02-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="92d02-135">Wenn Sie den Bericht erstellen, werden die Berichtsdokumente in einen Azure Storage in der Microsoft Cloud hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="92d02-135">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="92d02-136">Wechseln Sie zu [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="92d02-136">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="92d02-137">Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto an.</span><span class="sxs-lookup"><span data-stu-id="92d02-137">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="92d02-138">Klicken Sie im linken Bereich des Security & Compliance Center auf **Inhaltssuche** \> **durchsuchen.**</span><span class="sxs-lookup"><span data-stu-id="92d02-138">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="92d02-139">Wählen Sie **auf der Seite Inhaltssuche** eine Suche aus.</span><span class="sxs-lookup"><span data-stu-id="92d02-139">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="92d02-140">Klicken Sie im Detailbereich unter **Bericht auf einen Computer** exportieren auf Bericht **generieren**.</span><span class="sxs-lookup"><span data-stu-id="92d02-140">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="92d02-141">Wenn die Suchergebnisse älter als 7 Tage sind, werden Sie aufgefordert, die Suchergebnisse zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="92d02-141">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="92d02-142">Brechen Sie in diesem Fall  den Export ab, klicken Sie im Detailbereich für die ausgewählte Suche auf Suchergebnisse aktualisieren, und starten Sie den Berichtsexport erneut, nachdem die Ergebnisse aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="92d02-142">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="92d02-143">Wählen Sie **auf der Seite** Bericht exportieren unter Diese Elemente **aus** der Suche hinzufügen eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="92d02-143">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="92d02-144">Nur indizierte Elemente exportieren</span><span class="sxs-lookup"><span data-stu-id="92d02-144">Export only indexed items</span></span>
    
    - <span data-ttu-id="92d02-145">Indizierte und nicht indizierte Elemente exportieren</span><span class="sxs-lookup"><span data-stu-id="92d02-145">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="92d02-146">Nur nicht indizierte Elemente exportieren</span><span class="sxs-lookup"><span data-stu-id="92d02-146">Export only unindexed items</span></span>
    
    <span data-ttu-id="92d02-147">Weitere Informationen zu nicht indizierten Elementen finden Sie unter [Teilweise indizierte Elemente in der Inhaltssuche](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="92d02-147">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="92d02-148">Wählen Sie, ob Suchstatistiken für alle Versionen von Dokumenten SharePoint werden.</span><span class="sxs-lookup"><span data-stu-id="92d02-148">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="92d02-149">Diese Option wird nur angezeigt, wenn die Inhaltsquellen der Suche SharePoint oder OneDrive for Business enthalten.</span><span class="sxs-lookup"><span data-stu-id="92d02-149">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="92d02-150">Klicken Sie **auf Bericht generieren**.</span><span class="sxs-lookup"><span data-stu-id="92d02-150">Click **Generate report**.</span></span>
    
    <span data-ttu-id="92d02-151">Der Suchergebnissetbericht wird zum Herunterladen vorbereitet, d. h. die Berichtsdokumente werden in den Azure Storage in der Microsoft Cloud hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="92d02-151">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="92d02-152">Wenn der Bericht zum Herunterladen bereit ist, wird der **Link Bericht** herunterladen unter **Bericht auf** einen Computer exportieren im Detailbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="92d02-152">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="92d02-153">Sie können auch einen Bericht für eine Inhaltssuche exportieren, die einem eDiscovery-Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="92d02-153">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="92d02-154">Wechseln Sie dazu zu **eDiscovery** \> **eDiscovery,** wählen Sie einen Fall aus, und klicken Sie auf **Bearbeiten** ![ (Symbol). ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)</span><span class="sxs-lookup"><span data-stu-id="92d02-154">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="92d02-155">Wählen Sie **auf der Seite** Suchen eine  Suche aus, und klicken Sie dann auf Suchergebnisse exportieren Symbol ![ Bericht ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **exportieren**.</span><span class="sxs-lookup"><span data-stu-id="92d02-155">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="92d02-156">Schritt 2: Herunterladen des Berichts</span><span class="sxs-lookup"><span data-stu-id="92d02-156">Step 2: Download the report</span></span>

<span data-ttu-id="92d02-157">Im nächsten Schritt laden Sie den Bericht aus dem Azure Storage auf Ihren lokalen Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="92d02-157">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="92d02-158">Klicken Sie im Detailbereich für die Suche, für die Sie den Bericht generiert haben, unter **Bericht auf** einen Computer exportieren auf **Bericht herunterladen.**</span><span class="sxs-lookup"><span data-stu-id="92d02-158">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="92d02-159">Die **Seite Bericht herunterladen** wird angezeigt und enthält die folgenden Informationen zu dem Bericht, der auf Ihren Computer heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="92d02-159">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="92d02-160">Die Anzahl der Elemente, die heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="92d02-160">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="92d02-161">Die geschätzte Gesamtgröße der Elemente, die heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="92d02-161">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="92d02-162">Gibt an, ob indiziert oder nicht indiziert exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="92d02-162">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="92d02-163">Nicht indizierte Elemente sind Elemente, die ein erkanntes Format haben, verschlüsselt sind oder aus anderen Gründen nicht indiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="92d02-163">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="92d02-164">Gibt an, SharePoint Versionen von Dokumenten heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="92d02-164">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="92d02-165">Der Status des Berichtsexportprozesses.</span><span class="sxs-lookup"><span data-stu-id="92d02-165">The status of the report export process.</span></span> <span data-ttu-id="92d02-166">Sie können mit dem Herunterladen des Berichts beginnen, auch wenn die Vorbereitung des Berichts noch nicht abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="92d02-166">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="92d02-167">Klicken Sie unter **Schlüssel exportieren** auf **In Zwischenablage kopieren**.</span><span class="sxs-lookup"><span data-stu-id="92d02-167">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="92d02-168">Sie verwenden diesen Schlüssel in Schritt 5, um den Bericht herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="92d02-168">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="92d02-169">Da jeder benutzer das eDiscovery-Export-Tool installieren und starten kann und diesen Schlüssel dann zum Herunterladen des Suchberichts verwenden kann, sollten Sie Vorkehrungen treffen, um diesen Schlüssel so zu schützen, wie Sie Kennwörter oder andere sicherheitsrelevante Informationen schützen würden.</span><span class="sxs-lookup"><span data-stu-id="92d02-169">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="92d02-170">Klicken **Sie auf Bericht herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="92d02-170">Click **Download report**.</span></span>
    
4. <span data-ttu-id="92d02-171">Wenn Sie aufgefordert werden, das **eDiscovery-Exporttool zu** installieren, klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="92d02-171">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="92d02-172">Fügen Sie im **eDiscovery-Exporttool** den Export-Schlüssel, den Sie in Schritt 2 kopiert haben, in das entsprechende Feld ein.</span><span class="sxs-lookup"><span data-stu-id="92d02-172">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="92d02-173">Klicken **Sie auf Durchsuchen,** um den Speicherort anzugeben, an dem Sie den Bericht herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="92d02-173">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="92d02-174">Klicken Sie zum Herunterladen der Suchergebnisse auf Ihren Computer auf **Starten**.</span><span class="sxs-lookup"><span data-stu-id="92d02-174">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="92d02-175">Das **eDiscovery-Exporttool** zeigt Statusinformationen zum Exportvorgang an, einschließlich einer Schätzung der Anzahl (und Größe) der verbleibenden Elemente, die heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="92d02-175">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="92d02-176">Wenn der Exportvorgang abgeschlossen ist, können Sie auf die Dateien am Speicherort zugreifen, an dem sie heruntergeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="92d02-176">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="92d02-177">Sie können den Bericht für eine Inhaltssuche herunterladen, die einem eDiscovery-Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="92d02-177">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="92d02-178">Wechseln Sie dazu zu **eDiscovery** \> **eDiscovery,** wählen Sie einen Fall aus, und klicken Sie auf **Bearbeiten** ![ (Symbol). ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)</span><span class="sxs-lookup"><span data-stu-id="92d02-178">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="92d02-179">Wählen Sie **auf der** Seite Exporte einen  Berichtsexport aus, und klicken Sie dann im Detailbereich auf Bericht herunterladen.</span><span class="sxs-lookup"><span data-stu-id="92d02-179">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="92d02-180">Was im Bericht enthalten ist</span><span class="sxs-lookup"><span data-stu-id="92d02-180">What's included in the report</span></span>

<span data-ttu-id="92d02-181">Wenn Sie einen Bericht über die Ergebnisse einer Inhaltssuche generieren und exportieren, werden die folgenden Dokumente heruntergeladen:</span><span class="sxs-lookup"><span data-stu-id="92d02-181">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="92d02-182">**Exportzusammenfassung:** Ein Excel, das eine Zusammenfassung des Exports enthält.</span><span class="sxs-lookup"><span data-stu-id="92d02-182">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="92d02-183">Dazu gehören Informationen wie die Anzahl der durchsuchten Inhaltsquellen, die Anzahl der Suchergebnisse aus den einzelnen Inhaltsspeicherorten, die geschätzte Anzahl der Elemente, die tatsächliche Anzahl der exportierten Elemente und die geschätzte und tatsächliche Größe der exportierten Elemente.</span><span class="sxs-lookup"><span data-stu-id="92d02-183">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="92d02-184">Wenn Sie beim Exportieren des Berichts nicht indizierte Elemente enthalten, wird die Anzahl der nicht indizierten Elemente in der Gesamtanzahl der geschätzten Suchergebnisse und in der Gesamtzahl der heruntergeladenen Suchergebnisse (wenn Sie die Suchergebnisse exportieren sollten) enthalten, die im Bericht "Zusammenfassung exportieren" aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="92d02-184">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="92d02-185">Anders ausgedrückt: Die Gesamtanzahl der heruntergeladenen Elemente entspricht der Gesamtzahl der geschätzten Ergebnisse und der Gesamtzahl der nicht indizierten Elemente.</span><span class="sxs-lookup"><span data-stu-id="92d02-185">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="92d02-186">**Manifest:** Eine Manifestdatei (im XML-Format), die Informationen zu jedem Element enthält, das in den Suchergebnissen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="92d02-186">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="92d02-187">**Ergebnisse:** Ein Excel, das eine Zeile mit Informationen zu jedem indizierten Element enthält, das mit den Suchergebnissen exportiert würde.</span><span class="sxs-lookup"><span data-stu-id="92d02-187">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="92d02-188">Für E-Mails enthält das Ergebnisprotokoll Informationen zu jeder Nachricht, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="92d02-188">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="92d02-189">Der Speicherort der Nachricht im Quellpostfach (einschließlich der Angabe, ob die Nachricht sich im primären oder im Archivpostfach befindet).</span><span class="sxs-lookup"><span data-stu-id="92d02-189">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="92d02-190">Das Datum, an dem die Nachricht gesendet oder empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="92d02-190">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="92d02-191">Die Betreffzeile der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="92d02-191">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="92d02-192">Absender und Empfänger der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="92d02-192">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="92d02-193">Für Dokumente von SharePoint und OneDrive for Business enthält das Ergebnisprotokoll Informationen zu jedem Dokument, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="92d02-193">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="92d02-194">Die URL für das Dokument.</span><span class="sxs-lookup"><span data-stu-id="92d02-194">The URL for the document.</span></span>
    
  - <span data-ttu-id="92d02-195">Die URL für die Websitesammlung, in der sich das Dokument befindet.</span><span class="sxs-lookup"><span data-stu-id="92d02-195">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="92d02-196">Das Datum, an dem das Dokument zuletzt geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="92d02-196">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="92d02-197">Der Name des Dokuments (das sich in der Spalte Betreff im Ergebnisprotokoll befindet).</span><span class="sxs-lookup"><span data-stu-id="92d02-197">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="92d02-198">Die Anzahl der Zeilen im **Ergebnisbericht** sollte gleich der Gesamtzahl der Suchergebnisse minus der Gesamtzahl der im Bericht **Nicht indizierte Elemente aufgeführten Elemente** sein.</span><span class="sxs-lookup"><span data-stu-id="92d02-198">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="92d02-199">**Nicht indizierte Elemente:** Ein Excel, das Informationen zu nicht indizierten Elementen enthält, die in den Suchergebnissen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="92d02-199">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="92d02-200">Wenn Sie beim Generieren des Suchergebnissesberichts keine nicht indizierten Elemente verwenden, wird dieser Bericht weiterhin heruntergeladen, ist jedoch leer.</span><span class="sxs-lookup"><span data-stu-id="92d02-200">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
