---
title: Exportieren eines Berichts für die Inhaltssuche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
description: 'Anstatt die tatsächlichen Ergebnisse einer Inhaltssuche im Security #a0 Compliance Center in Office 365 zu exportieren, können Sie einen Suchergebnisbericht exportieren. Der Bericht enthält eine Zusammenfassung der Suchergebnisse und ein Dokument mit detaillierten Informationen zu jedem Element, das exportiert werden würde.'
ms.openlocfilehash: a46051210ae4d8b4254d0415668e3b9902bf5589
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595602"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="57943-104">Exportieren eines Berichts für die Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="57943-104">Export a Content Search report</span></span>

<span data-ttu-id="57943-105">Anstatt den vollständigen Satz von Suchergebnissen aus einer Inhaltssuche im Security #a0 Compliance Center (und aus einer Inhaltssuche, die einem eDiscovery-Fall zugeordnet ist) zu exportieren, können Sie dieselben Berichte exportieren, die beim Exportieren der Suchergebnisse generiert werden.</span><span class="sxs-lookup"><span data-stu-id="57943-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="57943-106">Wenn Sie einen Bericht exportieren, wird er in einen Ordner mit dem gleichen Namen wie die Inhaltssuche heruntergeladen, dieser wird jedoch *_ReportsOnly*angefügt.</span><span class="sxs-lookup"><span data-stu-id="57943-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="57943-107">Wenn die Inhaltssuche beispielsweise " *ContosoCase0815*" lautet, wird der Bericht in einen Ordner mit dem Namen " *ContosoCase0815_ReportsOnly*" heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="57943-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="57943-108">Eine Liste der Dokumente, die im Bericht enthalten sind, finden Sie unter [What es included in the Report](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="57943-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="57943-109">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="57943-109">Before you begin</span></span>

- <span data-ttu-id="57943-110">Zum Exportieren eines Inhalts Suchberichts müssen Sie im Security #a0 Compliance Center die Compliance Search-Verwaltungsrolle zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="57943-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="57943-111">Diese Rolle wird den integrierten eDiscovery-Manager-und Organisations Verwaltungsrollengruppen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="57943-111">This role is assigned to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="57943-112">Sie wird nicht standardmäßig der Rollengruppe "Organisationsverwaltung" zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="57943-112">It isn't assigned by default to the Organization Management role group.</span></span> <span data-ttu-id="57943-113">Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="57943-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="57943-114">Wenn Sie einen Bericht exportieren, werden die Daten temporär in einem eindeutigen Azure-Speicherbereich in der Microsoft-Cloud gespeichert, bevor Sie auf Ihren lokalen Computer heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="57943-114">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="57943-115">Stellen Sie sicher, dass Ihre Organisation eine Verbindung mit dem Endpunkt in Azure herstellen kann, also \*\* \*. BLOB.Core.Windows.net\*\* (der Platzhalter stellt einen eindeutigen Bezeichner für den Export dar).</span><span class="sxs-lookup"><span data-stu-id="57943-115">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="57943-116">Die Suchergebnis Daten werden zwei Wochen nach ihrer Erstellung aus dem Azure-Speicherbereich gelöscht.</span><span class="sxs-lookup"><span data-stu-id="57943-116">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="57943-117">Der Computer, den Sie zum Exportieren der Suchergebnisse verwenden, muss die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="57943-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="57943-118">32-Bit-oder 64-Bit-Versionen von Windows 7 und höheren Versionen</span><span class="sxs-lookup"><span data-stu-id="57943-118">32-bit or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="57943-119">Microsoft .NET Framework 4,7</span><span class="sxs-lookup"><span data-stu-id="57943-119">Microsoft .NET Framework 4.7</span></span>
    
- <span data-ttu-id="57943-120">Sie müssen einen der folgenden unterstützten Browser verwenden, um das eDiscovery-Export Tool<sup>1</sup>auszuführen:</span><span class="sxs-lookup"><span data-stu-id="57943-120">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="57943-121">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="57943-121">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="57943-122">ODER</span><span class="sxs-lookup"><span data-stu-id="57943-122">OR</span></span>

  - <span data-ttu-id="57943-123">Microsoft Internet Explorer 10 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="57943-123">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="57943-124"><sup>1</sup> Microsoft stellt keine Drittanbietererweiterungen oder Add-ons für ClickOnce-Anwendungen her.</span><span class="sxs-lookup"><span data-stu-id="57943-124"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="57943-125">Das Exportieren von Suchergebnissen mit einem nicht unterstützten Browser mit Erweiterungen oder Add-ons von Drittanbietern wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="57943-125">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="57943-126"><sup>2</sup> aufgrund der letzten Änderungen an Microsoft Edge ist die ClickOnce-Unterstützung standardmäßig nicht mehr aktiviert.</span><span class="sxs-lookup"><span data-stu-id="57943-126"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="57943-127">Anweisungen zum Aktivieren der ClickOnce-Unterstützung in Edge finden Sie unter [Verwenden des Office 365 eDiscovery-Export Tools in Microsoft Edge](configure-edge-to-export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="57943-127">For instructions on enabling ClickOnce support in Edge, see [Use the Office 365 eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="57943-128">Wenn die geschätzte Gesamtgröße der Ergebnisse, die von einer Inhaltssuche zurückgegeben werden, 2 TB überschreitet, schlägt das Exportieren des Berichts fehl.</span><span class="sxs-lookup"><span data-stu-id="57943-128">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="57943-129">Um den Bericht erfolgreich zu exportieren, versuchen Sie, den Bereich einzugrenzen, und führen Sie die Suche erneut aus, damit die geschätzte Größe der Ergebnisse weniger als 2 TB beträgt.</span><span class="sxs-lookup"><span data-stu-id="57943-129">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="57943-130">Das Exportieren von Inhalts Suchberichten gilt für die maximale Anzahl von Exporten, die gleichzeitig ausgeführt werden, und für die maximale Anzahl von Exporten, die ein einzelner Benutzer ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="57943-130">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="57943-131">Weitere Informationen zu Exportbeschränkungen finden Sie unter [Exportieren von Inhalts Suchergebnissen](export-search-results.md#export-limits).</span><span class="sxs-lookup"><span data-stu-id="57943-131">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="57943-132">Generieren und Herunterladen eines Inhalts Suchberichts</span><span class="sxs-lookup"><span data-stu-id="57943-132">Generate and download a Content Search report</span></span>

<span data-ttu-id="57943-133">Die Schritte zum Generieren und Herunterladen eines Inhalts Suchberichts ähneln dem tatsächlichen Exportieren von Suchergebnissen.</span><span class="sxs-lookup"><span data-stu-id="57943-133">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="57943-134">Schritt 1: Generieren des Berichts für den Export</span><span class="sxs-lookup"><span data-stu-id="57943-134">Step 1: Generate the report for export</span></span>

<span data-ttu-id="57943-135">Der erste Schritt besteht darin, den Bericht für den Download auf Ihrem Computer vorzubereiten, der exportiert.</span><span class="sxs-lookup"><span data-stu-id="57943-135">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="57943-136">Wenn Sie den Bericht anzeigen, werden die Berichtsdokumente in einen Azure-Speicherbereich in der Microsoft-Cloud hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="57943-136">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="57943-137">Wechseln Sie zu [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="57943-137">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="57943-138">Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto bei Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="57943-138">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="57943-139">Klicken Sie im linken Bereich des Security #a0 Compliance Centers auf **Such** \> **Inhaltssuche**.</span><span class="sxs-lookup"><span data-stu-id="57943-139">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="57943-140">Wählen Sie auf der Seite **Inhaltssuche** eine Suche aus.</span><span class="sxs-lookup"><span data-stu-id="57943-140">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="57943-141">Klicken Sie im Detailbereich unter **Bericht auf einen Computer exportieren**auf **Bericht generieren**.</span><span class="sxs-lookup"><span data-stu-id="57943-141">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="57943-142">Wenn die Suchergebnisse älter als 7 Tage sind, werden Sie aufgefordert, die Suchergebnisse zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="57943-142">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="57943-143">Wenn dies geschieht, brechen Sie den Export ab, klicken Sie im Detailbereich für die ausgewählte Suche auf **Suchergebnisse aktualisieren** , und starten Sie dann den Berichtsexport erneut, nachdem die Ergebnisse aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="57943-143">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="57943-144">Wählen Sie auf der Seite **Bericht exportieren** unter **diese Elemente aus der Suche einschließen**eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="57943-144">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="57943-145">Nur indizierte Elemente exportieren</span><span class="sxs-lookup"><span data-stu-id="57943-145">Export only indexed items</span></span>
    
    - <span data-ttu-id="57943-146">Indizierte und nicht indizierte Elemente exportieren</span><span class="sxs-lookup"><span data-stu-id="57943-146">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="57943-147">Nur nicht indizierte Elemente exportieren</span><span class="sxs-lookup"><span data-stu-id="57943-147">Export only unindexed items</span></span>
    
    <span data-ttu-id="57943-148">Weitere Informationen zu nicht indizierten Elementen finden Sie unter [teilweise indizierte Elemente in der Inhaltssuche](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="57943-148">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="57943-149">Wählen Sie aus, um Suchstatistiken für alle Versionen von SharePoint-Dokumenten einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="57943-149">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="57943-150">Diese Option wird nur angezeigt, wenn die Inhaltsquellen der Suche SharePoint-oder OneDrive für Unternehmen-Websites enthalten.</span><span class="sxs-lookup"><span data-stu-id="57943-150">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="57943-151">Klicken Sie auf **Bericht generieren**.</span><span class="sxs-lookup"><span data-stu-id="57943-151">Click **Generate report**.</span></span>
    
    <span data-ttu-id="57943-152">Der Bericht "Suchergebnisse" wird zum Herunterladen vorbereitet, was bedeutet, dass die Berichtsdokumente in den Azure-Speicherbereich in der Microsoft-Cloud hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="57943-152">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="57943-153">Wenn der Bericht zum Download bereit ist, wird der Link **Bericht herunterladen** unter **Bericht auf einem Computer exportieren** im Detailbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="57943-153">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="57943-154">Sie können auch einen Bericht für eine Inhaltssuche exportieren, die einem eDiscovery-Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="57943-154">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="57943-155">Wechseln Sie dazu zu **eDiscovery** \> **eDiscovery**, wählen Sie einen Fall aus, und klicken Sie auf Bearbeitungs](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)Symbol **Bearbeiten** ![.</span><span class="sxs-lookup"><span data-stu-id="57943-155">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="57943-156">Wählen Sie **auf der Seite suchen eine** Suche aus, **und klicken Sie** ![dann auf Export exportieren](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> Suchergebnisse Symbol **Exportieren eines Berichts**.</span><span class="sxs-lookup"><span data-stu-id="57943-156">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="57943-157">Schritt 2: Herunterladen des Berichts</span><span class="sxs-lookup"><span data-stu-id="57943-157">Step 2: Download the report</span></span>

<span data-ttu-id="57943-158">Der nächste Schritt besteht darin, den Bericht aus dem Azure-Speicherbereich auf Ihren lokalen Computer herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="57943-158">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="57943-159">Klicken Sie im Detailbereich für die Suche, für die Sie den Bericht erstellt haben, unter **Bericht auf Computer exportieren**auf **Bericht herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="57943-159">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="57943-160">Die Seite **Bericht herunterladen** wird angezeigt und enthält die folgenden Informationen zu dem Bericht, der auf Ihren Computer heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="57943-160">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="57943-161">Die Anzahl der Elemente, die heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="57943-161">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="57943-162">Die geschätzte Gesamtgröße der Elemente, die heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="57943-162">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="57943-163">Ob indiziert oder nicht indiziert exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="57943-163">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="57943-164">Nicht indizierte Elemente sind Elemente, die ein erkanntes Format aufweisen, verschlüsselt sind oder aus anderen Gründen nicht indiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="57943-164">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="57943-165">Gibt an, ob Versionen von SharePoint-Dokumenten heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="57943-165">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="57943-166">Der Status des Berichtsexport Prozesses.</span><span class="sxs-lookup"><span data-stu-id="57943-166">The status of the report export process.</span></span> <span data-ttu-id="57943-167">Sie können auch dann mit dem Herunterladen des Berichts beginnen, wenn die Vorbereitung des Berichts nicht abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="57943-167">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="57943-168">Klicken Sie unter **Schlüssel exportieren** auf **In Zwischenablage kopieren**.</span><span class="sxs-lookup"><span data-stu-id="57943-168">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="57943-169">Sie verwenden diesen Schlüssel in Schritt 5, um den Bericht herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="57943-169">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="57943-170">Da jeder Benutzer das eDiscovery-Export Tool installieren und starten und dann den Suchbericht mit diesem Schlüssel herunterladen kann, müssen Sie Vorkehrungen treffen, um diesen Schlüssel so zu schützen, wie Sie Kennwörter oder andere sicherheitsrelevante Informationen schützen.</span><span class="sxs-lookup"><span data-stu-id="57943-170">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="57943-171">Klicken Sie auf **Bericht herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="57943-171">Click **Download report**.</span></span>
    
4. <span data-ttu-id="57943-172">Wenn Sie aufgefordert werden, das **eDiscovery-Export Tool von Microsoft Office 365**zu installieren, klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="57943-172">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="57943-173">Fügen Sie im **eDiscovery-Exporttool** den Export-Schlüssel, den Sie in Schritt 2 kopiert haben, in das entsprechende Feld ein.</span><span class="sxs-lookup"><span data-stu-id="57943-173">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="57943-174">Klicken Sie auf **Durchsuchen** , um den Speicherort anzugeben, an dem Sie den Bericht herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="57943-174">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="57943-175">Klicken Sie zum Herunterladen der Suchergebnisse auf Ihren Computer auf **Starten**.</span><span class="sxs-lookup"><span data-stu-id="57943-175">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="57943-176">Im **eDiscovery-Export Tool** werden Statusinformationen zum Exportprozess angezeigt, einschließlich einer Schätzung der Zahl (und der Größe) der restlichen Elemente, die heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="57943-176">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="57943-177">Wenn der Exportvorgang abgeschlossen ist, können Sie auf die Dateien an dem Speicherort zugreifen, an dem Sie heruntergeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="57943-177">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="57943-178">Sie können den Bericht für eine Inhaltssuche herunterladen, die einem eDiscovery-Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="57943-178">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="57943-179">Wechseln Sie dazu zu **eDiscovery** \> **eDiscovery**, wählen Sie einen Fall aus, und klicken Sie auf Bearbeitungs](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)Symbol **Bearbeiten** ![.</span><span class="sxs-lookup"><span data-stu-id="57943-179">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="57943-180">Wählen Sie auf der Seite **Exports** einen Berichtsexport aus, und klicken Sie dann im Detailbereich auf **Bericht herunterladen** .</span><span class="sxs-lookup"><span data-stu-id="57943-180">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="57943-181">Was ist im Bericht enthalten?</span><span class="sxs-lookup"><span data-stu-id="57943-181">What's included in the report</span></span>

<span data-ttu-id="57943-182">Wenn Sie einen Bericht zu den Ergebnissen einer Inhaltssuche generieren und exportieren, werden die folgenden Dokumente heruntergeladen:</span><span class="sxs-lookup"><span data-stu-id="57943-182">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="57943-183">**Export Zusammenfassung:** Ein Excel-Dokument, das eine Zusammenfassung des Exports enthält.</span><span class="sxs-lookup"><span data-stu-id="57943-183">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="57943-184">Dazu gehören Informationen wie die Anzahl der durchsuchten Inhaltsquellen, die Anzahl der Suchergebnisse von jedem Inhaltsspeicherort, die geschätzte Anzahl von Elementen, die tatsächliche Anzahl der exportierten Elemente sowie die geschätzte und tatsächliche Größe von Elementen. , die exportiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="57943-184">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="57943-185">Wenn Sie nicht indizierte Elemente beim Exportieren des Berichts einschließen, wird die Anzahl der nicht indizierten Elemente in der Gesamtzahl der geschätzten Suchergebnisse und in der Gesamtzahl der heruntergeladenen Suchergebnisse (wenn Sie die Suchergebnisse exportieren), die in der Liste Export Zusammenfassungsbericht.</span><span class="sxs-lookup"><span data-stu-id="57943-185">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="57943-186">Mit anderen Worten: die Gesamtzahl der heruntergeladenen Elemente entspricht der Gesamtzahl der geschätzten Ergebnisse und der Gesamtzahl der nicht indizierten Elemente.</span><span class="sxs-lookup"><span data-stu-id="57943-186">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="57943-187">**Manifest:** Eine Manifestdatei (im XML-Format), die Informationen zu jedem Element enthält, das in den Suchergebnissen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="57943-187">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="57943-188">**Ergebnisse:** Ein Excel-Dokument, das eine Zeile mit Informationen zu jedem indizierten Element enthält, das mit den Suchergebnissen exportiert werden würde.</span><span class="sxs-lookup"><span data-stu-id="57943-188">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="57943-189">Bei e-Mails enthält das Ergebnisprotokoll Informationen zu den einzelnen Nachrichten, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="57943-189">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="57943-190">Der Speicherort der Nachricht im Quellpostfach (einschließlich der Angabe, ob die Nachricht sich im primären oder im Archivpostfach befindet).</span><span class="sxs-lookup"><span data-stu-id="57943-190">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="57943-191">Das Datum, an dem die Nachricht gesendet oder empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="57943-191">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="57943-192">Die Betreffzeile der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="57943-192">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="57943-193">Absender und Empfänger der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="57943-193">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="57943-194">Bei Dokumenten aus SharePoint-und OneDrive für Unternehmen-Websites enthält das Ergebnisprotokoll Informationen zu den einzelnen Dokumenten, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="57943-194">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="57943-195">Die URL für das Dokument.</span><span class="sxs-lookup"><span data-stu-id="57943-195">The URL for the document.</span></span>
    
  - <span data-ttu-id="57943-196">Die URL für die Websitesammlung, in der sich das Dokument befindet.</span><span class="sxs-lookup"><span data-stu-id="57943-196">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="57943-197">Das Datum, an dem das Dokument zuletzt geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="57943-197">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="57943-198">Der Name des Dokuments (der sich in der Spalte Betreff im Ergebnisprotokoll befindet).</span><span class="sxs-lookup"><span data-stu-id="57943-198">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="57943-199">Die Anzahl der Zeilen im **Ergebnis** Bericht sollte der Gesamtzahl der Suchergebnisse minus der Gesamtzahl der im Bericht nicht **Indexierte Elemente** aufgeführten Elemente entsprechen.</span><span class="sxs-lookup"><span data-stu-id="57943-199">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="57943-200">Nicht **indizierte Elemente:** Ein Excel-Dokument, das Informationen zu nicht indizierten Elementen enthält, die in den Suchergebnissen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="57943-200">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="57943-201">Wenn Sie nicht indizierte Elemente beim Generieren des Berichts "Suchergebnisse" einschließen, wird dieser Bericht weiterhin heruntergeladen, wird jedoch leer sein.</span><span class="sxs-lookup"><span data-stu-id="57943-201">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
