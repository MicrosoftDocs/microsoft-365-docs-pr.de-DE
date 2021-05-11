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
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311573"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="514da-104">Bericht zur Inhaltssuche exportieren</span><span class="sxs-lookup"><span data-stu-id="514da-104">Export a Content search report</span></span>

<span data-ttu-id="514da-105">Anstatt den vollständigen Satz von Suchergebnissen aus einer Inhaltssuche im Microsoft 365 Compliance Center (oder aus einer Suche, die einem Core eDiscovery-Fall zugeordnet ist) zu exportieren, können Sie dieselben Berichte exportieren, die beim Exportieren der tatsächlichen Suchergebnisse generiert werden.</span><span class="sxs-lookup"><span data-stu-id="514da-105">Instead of exporting the full set of search results from a Content search in the Microsoft 365 compliance Center (or from a search that's associated with a Core eDiscovery case), you can export the same reports that are generated when you export the actual search results.</span></span>
  
<span data-ttu-id="514da-106">Wenn Sie einen Bericht exportieren, werden die Berichtsdateien in einen Ordner auf Ihrem lokalen Computer heruntergeladen, der denselben Namen wie die Inhaltssuche hat, aber dieser wird mit _ReportsOnly *.*</span><span class="sxs-lookup"><span data-stu-id="514da-106">When you export a report, the report files are downloaded to a folder on your local computer that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="514da-107">Wenn die Inhaltssuche beispielsweise den Namen  *ContosoCase0815* hat, wird der Bericht in einen Ordner mit dem Namen *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="514da-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="514da-108">Eine Liste der Dokumente, die im Bericht enthalten sind, finden Sie unter [What's included in the report](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="514da-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-export-a-search-report"></a><span data-ttu-id="514da-109">Vor dem Exportieren eines Suchberichts</span><span class="sxs-lookup"><span data-stu-id="514da-109">Before you export a search report</span></span>

- <span data-ttu-id="514da-110">Zum Exportieren eines Suchberichts muss Ihnen die Verwaltungsrolle Compliancesuche im Security & Compliance Center zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="514da-110">To export a search report, you have to be assigned the Compliance Search management role in Security & Compliance Center.</span></span> <span data-ttu-id="514da-111">Diese Rolle wird standardmäßig den integrierten Rollengruppen eDiscovery Manager und Organization Management zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="514da-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="514da-112">Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="514da-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="514da-113">Wenn Sie einen Bericht exportieren, werden die Daten vorübergehend an einem Azure Storage in der Microsoft Cloud gespeichert, bevor sie auf Ihren lokalen Computer heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="514da-113">When you export a report, the data is temporarily stored in an Azure Storage location in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="514da-114">Stellen Sie sicher, dass Ihre Organisation eine Verbindung mit dem Endpunkt in Azure herstellen kann, der **\* .blob.core.windows.net** ist (der Platzhalter stellt einen eindeutigen Bezeichner für Ihren Export dar).</span><span class="sxs-lookup"><span data-stu-id="514da-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="514da-115">Die Suchergebnisse werden zwei Wochen nach der Azure Storage aus dem Speicherort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="514da-115">The search results data is deleted from the Azure Storage location two weeks after it's created.</span></span>

- <span data-ttu-id="514da-116">Der Computer, den Sie zum Exportieren der Suchergebnisse verwenden, muss die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="514da-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="514da-117">Neueste Version von Windows (32-Bit- oder 64-Bit-Version)</span><span class="sxs-lookup"><span data-stu-id="514da-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="514da-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="514da-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="514da-119">Sie müssen einen der folgenden unterstützten Browser verwenden, um das eDiscovery Export Tool<sup>1 ausführen zu können:</sup></span><span class="sxs-lookup"><span data-stu-id="514da-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="514da-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="514da-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="514da-121">ODER</span><span class="sxs-lookup"><span data-stu-id="514da-121">OR</span></span>

  - <span data-ttu-id="514da-122">Microsoft Internet Explorer 10 und höher</span><span class="sxs-lookup"><span data-stu-id="514da-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="514da-123"><sup>1</sup> Microsoft stellt keine Erweiterungen oder Add-Ons von Drittanbietern für ClickOnce her.</span><span class="sxs-lookup"><span data-stu-id="514da-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="514da-124">Das Exportieren von Suchergebnissen mithilfe eines nicht unterstützten Browsers mit Drittanbietererweiterungen oder -add-ons wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="514da-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="514da-125"><sup>2</sup> Als Ergebnis der letzten Änderungen an Microsoft Edge ist ClickOnce unterstützung standardmäßig nicht mehr aktiviert.</span><span class="sxs-lookup"><span data-stu-id="514da-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="514da-126">Anweisungen zum Aktivieren ClickOnce in Edge finden Sie unter [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="514da-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="514da-127">Wenn die geschätzte Gesamtgröße der von der Suche zurückgegebenen Ergebnisse 2 TB überschreitet, schlägt das Exportieren der Berichte fehl.</span><span class="sxs-lookup"><span data-stu-id="514da-127">If the estimated total size of the results returned by search exceeds 2 TB, exporting the reports fails.</span></span> <span data-ttu-id="514da-128">Um die Berichte erfolgreich zu exportieren, versuchen Sie, den Bereich zu einengt und die Suche erneut ausführen, sodass die geschätzte Größe der Ergebnisse kleiner als 2 TB ist.</span><span class="sxs-lookup"><span data-stu-id="514da-128">To successfully export the reports, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="514da-129">Wenn die Ergebnisse einer Suche älter als 7 Tage sind und Sie einen Exportberichtsauftrag übermitteln, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, die Suche erneut zu führen, um die Suchergebnisse zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="514da-129">If the results of a search are older than 7 days and you submit an export report job, an error message is displayed prompting you to rerun the search to update the search results.</span></span> <span data-ttu-id="514da-130">Brechen Sie in diesem Fall den Export ab, führen Sie die Suche erneut aus, und starten Sie den Export erneut.</span><span class="sxs-lookup"><span data-stu-id="514da-130">If this happens, cancel the export, rerun the search, and then start the export again.</span></span>

- <span data-ttu-id="514da-131">Das Exportieren von Suchberichten gilt für die maximale Anzahl von Exporten, die gleichzeitig ausgeführt werden, und die maximale Anzahl von Exporten, die ein einzelner Benutzer ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="514da-131">Exporting search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="514da-132">Weitere Informationen zu Exportbeschränkungen finden Sie [unter Exportieren von Inhaltssuchergebnissen](export-search-results.md#export-limits).</span><span class="sxs-lookup"><span data-stu-id="514da-132">For more information about export limits, see [Export Content search results](export-search-results.md#export-limits).</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="514da-133">Schritt 1: Generieren des Berichts für den Export</span><span class="sxs-lookup"><span data-stu-id="514da-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="514da-134">Der erste Schritt besteht in der Vorbereitung des Berichts für das Herunterladen auf Ihren Computer, der exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="514da-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="514da-135">Wenn Sie den Bericht exportieren, werden die Berichtsdokumente in einen Azure Storage in der Microsoft Cloud hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="514da-135">When you export the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="514da-136">Wählen Sie Microsoft 365 Compliance Center die Inhaltssuche aus, aus der Sie den Bericht exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="514da-136">In the Microsoft 365 compliance center, select the Content search that you want to export the report from.</span></span>
  
2. <span data-ttu-id="514da-137">Klicken Sie **im** Menü Aktionen unten auf der Suchf flyout-Seite auf **Bericht exportieren.**</span><span class="sxs-lookup"><span data-stu-id="514da-137">On the **Actions** menu at the bottom of the search flyout page, click **Export report**.</span></span>

   ![Export report option in Actions menu](../media/ActionMenuExportReport.png)

   <span data-ttu-id="514da-139">Die **Flyoutseite** Export report wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="514da-139">The **Export report** flyout page is displayed.</span></span> <span data-ttu-id="514da-140">Die Exportberichtsoptionen, die zum Exportieren von Informationen zur Suche verfügbar sind, hängen davon ab, ob sich suchergebnisse in Postfächern oder Websites oder in einer Kombination aus beiden befinden.</span><span class="sxs-lookup"><span data-stu-id="514da-140">The export report options available to export information about the search depend on whether search results are located in mailboxes or sites or a combination of both.</span></span>
  
3. <span data-ttu-id="514da-141">Wählen **Sie unter** Ausgabeoptionen eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="514da-141">Under **Output options**, choose one of the following options:</span></span>
  
   ![Exportausgabeoptionen](../media/ExportOutputOptions.png)

    - <span data-ttu-id="514da-143">**Alle Elemente, mit Ausnahme von** Elementen, die nicht ein unbekanntes Format haben, sind verschlüsselt oder wurden aus anderen Gründen nicht indiziert.</span><span class="sxs-lookup"><span data-stu-id="514da-143">**All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="514da-144">Mit dieser Option werden nur Informationen zu indizierten Elementen exportiert.</span><span class="sxs-lookup"><span data-stu-id="514da-144">This option only exports information about indexed items.</span></span>
  
    - <span data-ttu-id="514da-145">**Alle Elemente, einschließlich** der Elemente, die ein nicht unbekanntes Format haben, sind verschlüsselt oder wurden aus anderen Gründen nicht indiziert.</span><span class="sxs-lookup"><span data-stu-id="514da-145">**All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="514da-146">Mit dieser Option werden Informationen zu indizierten und nicht indizierten Elementen exportiert.</span><span class="sxs-lookup"><span data-stu-id="514da-146">This option exports information about indexed and unindexed items.</span></span>
  
    - <span data-ttu-id="514da-147">**Nur Elemente, die ein nicht unbekanntes** Format haben, verschlüsselt sind oder aus anderen Gründen nicht indiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="514da-147">**Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="514da-148">Mit dieser Option werden nur Informationen zu nicht indizierten Elementen exportiert.</span><span class="sxs-lookup"><span data-stu-id="514da-148">This option only exports information about unindexed items.</span></span>

4. <span data-ttu-id="514da-149">Konfigurieren Sie **die Option Deduplizierung für Exchange aktivieren.**</span><span class="sxs-lookup"><span data-stu-id="514da-149">Configure the **Enable de-duplication for Exchange content** option.</span></span>
  
   - <span data-ttu-id="514da-150">Wenn Sie diese Option auswählen, wird die Anzahl doppelter Nachrichten (vor Deduplizierung und nach Deduplizierung) in den Exportzusammenfassungsbericht aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="514da-150">If you select this option, the count of duplicate messages (before de-duplication and after de-duplication) is included in the export summary report.</span></span> <span data-ttu-id="514da-151">Außerdem wird nur eine Kopie einer Nachricht in die Datei manifest.xml eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="514da-151">Also, only one copy of a message will be included in the manifest.xml file.</span></span> <span data-ttu-id="514da-152">Der Exportergebnisbericht enthält jedoch eine Zeile für jede Kopie einer doppelten Nachricht, damit Sie die Postfächer identifizieren können, die eine Kopie der doppelten Nachricht enthalten.</span><span class="sxs-lookup"><span data-stu-id="514da-152">But the export results report will contain a row for every copy of a duplicate message so that you can identify the mailboxes that contain a copy of the duplicate message.</span></span> <span data-ttu-id="514da-153">Weitere Informationen zu den exportierten Berichten finden Sie unter [What's included in the report](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="514da-153">For more information about the exported reports, see [What's included in the report](#whats-included-in-the-report).</span></span>

   - <span data-ttu-id="514da-154">Wenn Sie diese Option nicht auswählen, enthalten die Exportberichte Informationen zu allen nachrichten, die von der Suche zurückgegeben werden, einschließlich Duplikaten.</span><span class="sxs-lookup"><span data-stu-id="514da-154">If you don't select this option, the export reports will contain information about all messages returned by the search, including duplicates.</span></span>

     <span data-ttu-id="514da-155">Weitere Informationen zur Deduplizierung und zur Ermittlung doppelter Elemente finden Sie unter [Deduplizierung in eDiscovery-Suchergebnissen.](de-duplication-in-ediscovery-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="514da-155">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

5. <span data-ttu-id="514da-156">Klicken Sie **auf Bericht generieren**.</span><span class="sxs-lookup"><span data-stu-id="514da-156">Click **Generate report**.</span></span>

   <span data-ttu-id="514da-157">Die Suchberichte werden zum Herunterladen vorbereitet, d. h. die Berichtsdokumente werden an einen Azure Storage in der Microsoft Cloud hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="514da-157">The search reports are prepared for downloading, which means the report documents are uploaded to an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="514da-158">Dieser Vorgang kann einige Minuten in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="514da-158">This may take several minutes.</span></span>

<span data-ttu-id="514da-159">Anweisungen zum Herunterladen der exportierten Suchberichte finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="514da-159">See the next section for instructions to download the exported search reports.</span></span>
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="514da-160">Schritt 2: Herunterladen des Berichts</span><span class="sxs-lookup"><span data-stu-id="514da-160">Step 2: Download the report</span></span>

<span data-ttu-id="514da-161">Im nächsten Schritt laden Sie den Bericht aus dem Azure Storage auf Ihren lokalen Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="514da-161">The next step is to download the report from the Azure Storage area to your local computer.</span></span>

1. <span data-ttu-id="514da-162">Wählen Sie **auf der** Seite Inhaltssuche im Microsoft 365 Compliance Center die Registerkarte **Exporte** aus.</span><span class="sxs-lookup"><span data-stu-id="514da-162">On the **Content search** page in the Microsoft 365 compliance center, select the **Exports** tab</span></span>
  
   <span data-ttu-id="514da-163">Möglicherweise müssen Sie auf **Aktualisieren klicken,** um die Liste der Exportaufträge so zu aktualisieren, dass der erstellte Exportauftrag angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="514da-163">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="514da-164">Exportberichtsaufträge haben denselben Namen wie die entsprechende Suche, _ReportsOnly **an** den Suchnamen angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="514da-164">Export report jobs have the same name as the corresponding search with **_ReportsOnly** appended to the search name.</span></span>
  
2. <span data-ttu-id="514da-165">Wählen Sie den Exportauftrag aus, den Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="514da-165">Select the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="514da-166">Klicken Sie **auf der** Flyoutseite Export report unter **Export key** auf Kopieren in **die Zwischenablage.**</span><span class="sxs-lookup"><span data-stu-id="514da-166">On the **Export report** flyout page under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="514da-167">Sie verwenden diesen Schlüssel in Schritt 6, um die Suchergebnisse herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="514da-167">You use this key in step 6 to download the search results.</span></span>
  
   > [!IMPORTANT]
   > <span data-ttu-id="514da-168">Da jeder benutzer das eDiscovery-Export-Tool installieren und starten kann und diesen Schlüssel dann zum Herunterladen des Suchberichts verwenden kann, sollten Sie Vorkehrungen treffen, um diesen Schlüssel so zu schützen, wie Sie Kennwörter oder andere sicherheitsrelevante Informationen schützen würden.</span><span class="sxs-lookup"><span data-stu-id="514da-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span>

4. <span data-ttu-id="514da-169">Klicken Sie oben auf der Flyoutseite auf **Ergebnisse herunterladen.**</span><span class="sxs-lookup"><span data-stu-id="514da-169">At the top of the flyout page, click **Download results**.</span></span>

5. <span data-ttu-id="514da-170">Wenn Sie aufgefordert werden, das **eDiscovery-Exporttool zu** installieren, klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="514da-170">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>

6. <span data-ttu-id="514da-171">Gehen Sie **im eDiscovery-Exporttool** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="514da-171">In the **eDiscovery Export Tool**, do the following:</span></span>

   ![eDiscovery-Exporttool](../media/eDiscoveryExportTool.png)

   1. <span data-ttu-id="514da-173">Fügen Sie den Exportschlüssel, den Sie in Schritt 3 kopiert haben, in das entsprechende Feld ein.</span><span class="sxs-lookup"><span data-stu-id="514da-173">Paste the export key that you copied in step 3 in the appropriate box.</span></span>
  
   2. <span data-ttu-id="514da-174">Klicken **Sie auf Durchsuchen,** um den Speicherort anzugeben, an dem Sie die Suchberichtsdateien herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="514da-174">Click **Browse** to specify the location where you want to download the search report files.</span></span>

7. <span data-ttu-id="514da-175">Klicken Sie zum Herunterladen der Suchergebnisse auf Ihren Computer auf **Starten**.</span><span class="sxs-lookup"><span data-stu-id="514da-175">Click **Start** to download the search results to your computer.</span></span>
  
    <span data-ttu-id="514da-176">Das **eDiscovery-Exporttool** zeigt Statusinformationen zum Exportvorgang an, einschließlich einer Schätzung der Anzahl (und Größe) der verbleibenden Elemente, die heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="514da-176">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="514da-177">Wenn der Exportvorgang abgeschlossen ist, können Sie auf die Dateien am Speicherort zugreifen, an dem sie heruntergeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="514da-177">When the export process is complete, you can access the files in the location where they were downloaded.</span></span>
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="514da-178">Was im Bericht enthalten ist</span><span class="sxs-lookup"><span data-stu-id="514da-178">What's included in the report</span></span>

<span data-ttu-id="514da-179">Wenn Sie einen Bericht über die Ergebnisse einer Inhaltssuche generieren und exportieren, werden die folgenden Dokumente heruntergeladen:</span><span class="sxs-lookup"><span data-stu-id="514da-179">When you generate and export a report about the results of a Content search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="514da-180">**Exportzusammenfassung:** Ein Excel, das eine Zusammenfassung des Exports enthält.</span><span class="sxs-lookup"><span data-stu-id="514da-180">**Export summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="514da-181">Dazu gehören Informationen wie die Anzahl der durchsuchten Inhaltsquellen, die Anzahl der Suchergebnisse aus den einzelnen Inhaltsspeicherorten, die geschätzte Anzahl der Elemente, die tatsächliche Anzahl der exportierten Elemente und die geschätzte und tatsächliche Größe der exportierten Elemente.</span><span class="sxs-lookup"><span data-stu-id="514da-181">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span>

   <span data-ttu-id="514da-182">Wenn Sie beim Exportieren des Berichts nicht indizierte Elemente enthalten, wird die Anzahl der nicht indizierten Elemente in der Gesamtanzahl der geschätzten Suchergebnisse und in der Gesamtzahl der heruntergeladenen Suchergebnisse (wenn Sie die Suchergebnisse exportieren) enthalten, die im Zusammenfassenden Exportbericht aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="514da-182">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the export summary report.</span></span> <span data-ttu-id="514da-183">Anders ausgedrückt: Die Gesamtanzahl der heruntergeladenen Elemente entspricht der Gesamtzahl der geschätzten Ergebnisse und der Gesamtzahl der nicht indizierten Elemente.</span><span class="sxs-lookup"><span data-stu-id="514da-183">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span>
  
- <span data-ttu-id="514da-184">**Manifest:** Eine Manifestdatei (im XML-Format), die Informationen zu jedem Element enthält, das in den Suchergebnissen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="514da-184">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="514da-185">Wenn Sie die Deduplizierungsoption aktiviert haben, sind doppelte Nachrichten nicht in der Manifestdatei enthalten.</span><span class="sxs-lookup"><span data-stu-id="514da-185">If you enabled the de-duplication option, duplicate message are not included in the manifest file.</span></span>

- <span data-ttu-id="514da-186">**Ergebnisse:** Ein Excel, das eine Zeile mit Informationen zu jedem indizierten Element enthält, das mit den Suchergebnissen exportiert würde.</span><span class="sxs-lookup"><span data-stu-id="514da-186">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="514da-187">Für E-Mails enthält das Ergebnisprotokoll Informationen zu jeder Nachricht, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="514da-187">For email, the result log contains information about each message, including:</span></span> 

  - <span data-ttu-id="514da-188">Der Speicherort der Nachricht im Quellpostfach (einschließlich der Angabe, ob die Nachricht sich im primären oder im Archivpostfach befindet).</span><span class="sxs-lookup"><span data-stu-id="514da-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>

  - <span data-ttu-id="514da-189">Das Datum, an dem die Nachricht gesendet oder empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="514da-189">The date the message was sent or received.</span></span>

  - <span data-ttu-id="514da-190">Die Betreffzeile der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="514da-190">The Subject line from the message.</span></span>

  - <span data-ttu-id="514da-191">Absender und Empfänger der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="514da-191">The sender and recipients of the message.</span></span>

  <span data-ttu-id="514da-192">Für Dokumente von SharePoint und OneDrive for Business enthält das Ergebnisprotokoll Informationen zu jedem Dokument, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="514da-192">For documents from SharePoint and OneDrive for Business sites, the results log contains information about each document, including:</span></span>

  - <span data-ttu-id="514da-193">Die URL für das Dokument.</span><span class="sxs-lookup"><span data-stu-id="514da-193">The URL for the document.</span></span>

  - <span data-ttu-id="514da-194">Die URL für die Websitesammlung, in der sich das Dokument befindet.</span><span class="sxs-lookup"><span data-stu-id="514da-194">The URL for the site collection where the document is located.</span></span>

  - <span data-ttu-id="514da-195">Das Datum, an dem das Dokument zuletzt geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="514da-195">The date that the document was last modified.</span></span>

  - <span data-ttu-id="514da-196">Der Name des Dokuments (das sich in der Spalte Betreff im Ergebnisprotokoll befindet).</span><span class="sxs-lookup"><span data-stu-id="514da-196">The name of the document (which is located in the Subject column in the result log).</span></span>

  > [!NOTE]
  > <span data-ttu-id="514da-197">Die Anzahl der Zeilen im **Ergebnisbericht** sollte gleich der Gesamtzahl der Suchergebnisse minus der Gesamtzahl der im Bericht **Nicht indizierte Elemente aufgeführten Elemente** sein.</span><span class="sxs-lookup"><span data-stu-id="514da-197">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span>
  
- <span data-ttu-id="514da-198">**Trace.log**: Ein Ablaufverfolgungsprotokoll, das detaillierte Protokollierungsinformationen zum Exportprozess enthält und beim Aufdecken von Problemen beim Export helfen kann.</span><span class="sxs-lookup"><span data-stu-id="514da-198">**Trace.log**: A trace log that contains detailed logging information about the export process and can help uncover issues during export.</span></span> <span data-ttu-id="514da-199">Wenn Sie ein Ticket mit dem Microsoft Support zu einem Problem im Zusammenhang mit dem Exportieren von Suchberichten öffnen, werden Sie möglicherweise aufgefordert, dieses Ablaufverfolgungsprotokoll zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="514da-199">If you open a ticket with Microsoft Support about an issue related to exporting search reports, you may be asked to provide this trace log.</span></span>

- <span data-ttu-id="514da-200">**Nicht indizierte Elemente:** Ein Excel, das Informationen zu nicht indizierten Elementen enthält, die in den Suchergebnissen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="514da-200">**Unindexed items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="514da-201">Wenn Sie beim Generieren des Suchergebnissesberichts keine nicht indizierten Elemente verwenden, wird dieser Bericht weiterhin heruntergeladen, ist jedoch leer.</span><span class="sxs-lookup"><span data-stu-id="514da-201">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
