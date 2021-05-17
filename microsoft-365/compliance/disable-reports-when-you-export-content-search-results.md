---
title: Deaktivieren von Berichten beim Exportieren von Inhaltssuchergebnissen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Bearbeiten Sie Windows Registrierung auf Ihrem lokalen Computer, um Berichte zu deaktivieren, wenn Sie die Ergebnisse einer Inhaltssuche aus dem Security & Compliance Center exportieren.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817854"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="3840d-103">Deaktivieren von Berichten beim Exportieren von Inhaltssuchergebnissen</span><span class="sxs-lookup"><span data-stu-id="3840d-103">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="3840d-104">Wenn Sie das eDiscovery-Export-Tool zum Exportieren der Ergebnisse einer Inhaltssuche im Security & Compliance Center verwenden, erstellt und exportiert das Tool automatisch zwei Berichte, die zusätzliche Informationen zu den exportierten Inhalten enthalten.</span><span class="sxs-lookup"><span data-stu-id="3840d-104">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="3840d-105">Diese Berichte sind die Results.csv und die Manifest.xml -Datei (ausführliche Beschreibungen dieser Berichte finden Sie im Abschnitt Häufig gestellte Fragen zum Deaktivieren von Exportberichten in diesem Thema). [](#frequently-asked-questions-about-disabling-export-reports)</span><span class="sxs-lookup"><span data-stu-id="3840d-105">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="3840d-106">Da diese Dateien sehr groß sein können, können Sie die Downloadzeit beschleunigen und Speicherplatz sparen, indem Sie verhindern, dass diese Dateien exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="3840d-106">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="3840d-107">Sie können dies tun, indem Sie Windows Registrierung auf dem Computer ändern, den Sie zum Exportieren der Suchergebnisse verwenden.</span><span class="sxs-lookup"><span data-stu-id="3840d-107">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="3840d-108">Wenn Sie die Berichte zu einem späteren Zeitpunkt hinzufügen möchten, können Sie die Registrierungseinstellung bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="3840d-108">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="3840d-109">Erstellen von Registrierungseinstellungen zum Deaktivieren der Exportberichte</span><span class="sxs-lookup"><span data-stu-id="3840d-109">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="3840d-110">Führen Sie das folgende Verfahren auf dem Computer aus, mit dem Sie die Ergebnisse einer Inhaltssuche exportieren.</span><span class="sxs-lookup"><span data-stu-id="3840d-110">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="3840d-111">Schließen Sie das eDiscovery-Export-Tool, wenn es geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="3840d-111">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="3840d-112">Führen Sie einen oder beide der folgenden Schritte aus, je nachdem, welchen Exportbericht Sie deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3840d-112">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="3840d-113">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="3840d-113">**Results.csv**</span></span>
    
      <span data-ttu-id="3840d-114">Speichern Sie den folgenden Text in Windows Registrierungsdatei, indem Sie das Dateinamensuffix .reg verwenden. Beispielsweise DisableResultsCsv.reg.</span><span class="sxs-lookup"><span data-stu-id="3840d-114">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="3840d-115">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="3840d-115">**Manifest.xml**</span></span>
    
      <span data-ttu-id="3840d-116">Speichern Sie den folgenden Text in Windows Registrierungsdatei, indem Sie das Dateinamensuffix .reg verwenden. Beispielsweise DisableManifestXml.reg.</span><span class="sxs-lookup"><span data-stu-id="3840d-116">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="3840d-117">Klicken Windows Explorer auf oder doppelklicken Sie auf die .reg-Datei, die Sie in den vorherigen Schritten erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3840d-117">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="3840d-118">Klicken Sie im Fenster Benutzerzugriffssteuerung auf **Ja,** damit der Registrierungs-Editor die Änderung vornehmen kann.</span><span class="sxs-lookup"><span data-stu-id="3840d-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="3840d-119">Wenn Sie zum Fortfahren aufgefordert werden, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="3840d-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="3840d-120">Der Registrierungs-Editor zeigt eine Meldung an, dass die Einstellung erfolgreich zur Registrierung hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="3840d-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="3840d-121">Bearbeiten von Registrierungseinstellungen zum erneuten Aktivieren der Exportberichte</span><span class="sxs-lookup"><span data-stu-id="3840d-121">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="3840d-122">Wenn Sie die Results.csv- und Manifest.xml-Berichte durch Erstellen der .reg-Dateien im vorherigen Verfahren deaktiviert haben, können Sie diese Dateien bearbeiten, um einen Bericht erneut zu aktivieren, sodass er mit den Suchergebnissen exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="3840d-122">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="3840d-123">Führen Sie erneut das folgende Verfahren auf dem Computer aus, mit dem Sie die Ergebnisse einer Inhaltssuche exportieren.</span><span class="sxs-lookup"><span data-stu-id="3840d-123">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="3840d-124">Schließen Sie das eDiscovery-Export-Tool, wenn es geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="3840d-124">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="3840d-125">Bearbeiten Sie eine oder beide der .reg-Bearbeitungsdateien, die Sie im vorherigen Verfahren erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3840d-125">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="3840d-126">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="3840d-126">**Results.csv**</span></span>
    
        <span data-ttu-id="3840d-127">Öffnen Sie die Datei DisableResultsCsv.reg in Editor, ändern Sie den Wert in , und speichern Sie `False` `True` die Datei.</span><span class="sxs-lookup"><span data-stu-id="3840d-127">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="3840d-128">Wenn Sie die Datei beispielsweise bearbeitet haben, sieht sie wie die folgende aus:</span><span class="sxs-lookup"><span data-stu-id="3840d-128">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="3840d-129">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="3840d-129">**Manifest.xml**</span></span>
    
        <span data-ttu-id="3840d-130">Öffnen Sie die Datei DisableManifestXml.reg in Editor, ändern Sie den Wert in , und speichern Sie `False` `True` die Datei.</span><span class="sxs-lookup"><span data-stu-id="3840d-130">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="3840d-131">Wenn Sie die Datei beispielsweise bearbeitet haben, sieht sie wie die folgende aus:</span><span class="sxs-lookup"><span data-stu-id="3840d-131">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="3840d-132">Klicken Windows Explorer auf eine REG-Datei, die Sie im vorherigen Schritt bearbeitet haben, oder doppelklicken Sie auf diese.</span><span class="sxs-lookup"><span data-stu-id="3840d-132">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="3840d-133">Klicken Sie im Fenster Benutzerzugriffssteuerung auf **Ja,** damit der Registrierungs-Editor die Änderung vornehmen kann.</span><span class="sxs-lookup"><span data-stu-id="3840d-133">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="3840d-134">Wenn Sie zum Fortfahren aufgefordert werden, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="3840d-134">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="3840d-135">Der Registrierungs-Editor zeigt eine Meldung an, dass die Einstellung erfolgreich zur Registrierung hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="3840d-135">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="3840d-136">Häufig gestellte Fragen zum Deaktivieren von Exportberichten</span><span class="sxs-lookup"><span data-stu-id="3840d-136">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="3840d-137">**Was sind die Results.csv und Manifest.xml Berichte?**</span><span class="sxs-lookup"><span data-stu-id="3840d-137">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="3840d-138">Die Results.csv und Manifest.xml enthalten zusätzliche Informationen zu den exportierten Inhalten.</span><span class="sxs-lookup"><span data-stu-id="3840d-138">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="3840d-139">**Results.csv** Ein Excel, das Informationen zu jedem Element enthält, das als Suchergebnis heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="3840d-139">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="3840d-140">Für E-Mails enthält das Ergebnisprotokoll Informationen zu jeder Nachricht, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="3840d-140">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="3840d-141">Der Speicherort der Nachricht im Quellpostfach (einschließlich der Angabe, ob die Nachricht sich im primären oder im Archivpostfach befindet).</span><span class="sxs-lookup"><span data-stu-id="3840d-141">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="3840d-142">Das Datum, an dem die Nachricht gesendet oder empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="3840d-142">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="3840d-143">Die Betreffzeile der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="3840d-143">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="3840d-144">Absender und Empfänger der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="3840d-144">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="3840d-145">Gibt an, ob es sich bei der Nachricht um eine doppelte Nachricht handelt, wenn Sie die Deduplizierung beim Exportieren der Suchergebnisse aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="3840d-145">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="3840d-146">Doppelte Nachrichten haben einen Wert in der Spalte **Parent ItemId,** der die Nachricht als Duplikat identifiziert.</span><span class="sxs-lookup"><span data-stu-id="3840d-146">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="3840d-147">Der Wert in der **Spalte Parent ItemId** ist identisch mit dem Wert in der **Spalte Item DocumentId** der Nachricht, die exportiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3840d-147">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="3840d-148">Für Dokumente von SharePoint und OneDrive for Business enthält das Ergebnisprotokoll Informationen zu jedem Dokument, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="3840d-148">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="3840d-149">Die URL für das Dokument.</span><span class="sxs-lookup"><span data-stu-id="3840d-149">The URL for the document.</span></span>
    
  - <span data-ttu-id="3840d-150">Die URL für die Websitesammlung, in der sich das Dokument befindet.</span><span class="sxs-lookup"><span data-stu-id="3840d-150">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="3840d-151">Das Datum, an dem das Dokument zuletzt geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="3840d-151">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="3840d-152">Der Name des Dokuments (das sich in der Spalte Betreff im Ergebnisprotokoll befindet).</span><span class="sxs-lookup"><span data-stu-id="3840d-152">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="3840d-153">**Manifest.xml** Eine Manifestdatei (im XML-Format), die Informationen zu jedem Element enthält, das in den Suchergebnissen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3840d-153">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="3840d-154">Die Informationen in diesem Bericht sind mit dem bericht Results.csv identisch, haben jedoch das format, das durch das elektronische Ermittlungsreferenzmodell (Electronic Discovery Reference Model, EDRM) angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3840d-154">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="3840d-155">Weitere Informationen zu EDRM finden Sie unter [https://www.edrm.net](https://www.edrm.net) .</span><span class="sxs-lookup"><span data-stu-id="3840d-155">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="3840d-156">**Wann sollte ich das Exportieren dieser Berichte deaktivieren?**</span><span class="sxs-lookup"><span data-stu-id="3840d-156">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="3840d-157">Dies hängt von Ihren spezifischen Anforderungen ab.</span><span class="sxs-lookup"><span data-stu-id="3840d-157">It depends on your specific needs.</span></span> <span data-ttu-id="3840d-158">Viele Organisationen benötigen keine zusätzlichen Informationen zu Suchergebnissen und benötigen diese Berichte nicht.</span><span class="sxs-lookup"><span data-stu-id="3840d-158">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="3840d-159">**Auf welchem Computer muss ich dies tun?**</span><span class="sxs-lookup"><span data-stu-id="3840d-159">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="3840d-160">Sie müssen die Registrierungseinstellung auf jedem lokalen Computer ändern, auf dem Sie das eDiscovery-Export-Tool ausführen.</span><span class="sxs-lookup"><span data-stu-id="3840d-160">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="3840d-161">**Muss ich den Computer neu starten, nachdem ich diese Einstellung geändert habe?**</span><span class="sxs-lookup"><span data-stu-id="3840d-161">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="3840d-162">Nein, Sie müssen den Computer nicht neu starten.</span><span class="sxs-lookup"><span data-stu-id="3840d-162">No, you don't have to restart the computer.</span></span> <span data-ttu-id="3840d-163">Wenn das eDiscovery-Exporttool jedoch ausgeführt wird, müssen Sie es schließen und es neu starten, nachdem Sie die Registrierungseinstellung geändert haben.</span><span class="sxs-lookup"><span data-stu-id="3840d-163">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="3840d-164">**Wird ein vorhandener Registrierungsschlüssel bearbeitet oder wird ein neuer Schlüssel erstellt?**</span><span class="sxs-lookup"><span data-stu-id="3840d-164">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="3840d-165">Beim ersten Ausführen der .reg-Datei, die Sie im Verfahren in diesem Thema erstellt haben, wird ein neuer Registrierungsschlüssel erstellt.</span><span class="sxs-lookup"><span data-stu-id="3840d-165">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="3840d-166">Anschließend wird die Einstellung jedes Mal bearbeitet, wenn Sie die .reg-Bearbeitungsdatei ändern und erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="3840d-166">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
