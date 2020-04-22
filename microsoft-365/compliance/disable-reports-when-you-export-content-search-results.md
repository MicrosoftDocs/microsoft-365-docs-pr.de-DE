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
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: Bearbeiten Sie die Windows-Registrierung auf dem lokalen Computer, um Berichte zu deaktivieren, wenn Sie die Ergebnisse einer Inhaltssuche aus dem Security & Compliance Center in Office 365 exportieren. Durch das Deaktivieren dieser Berichte kann die Downloadzeit beschleunigt und Speicherplatz gespart werden.
ms.openlocfilehash: 3bd5fadda750c709c463fbc4d84668b43e0d3a10
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633450"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="158c3-104">Deaktivieren von Berichten beim Exportieren von Inhaltssuchergebnissen</span><span class="sxs-lookup"><span data-stu-id="158c3-104">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="158c3-105">Wenn Sie das eDiscovery-Export Tool verwenden, um die Ergebnisse einer Inhaltssuche im Security & Compliance Center zu exportieren, erstellt und exportiert das Tool automatisch zwei Berichte, die zusätzliche Informationen zu den exportierten Inhalten enthalten.</span><span class="sxs-lookup"><span data-stu-id="158c3-105">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="158c3-106">Bei diesen Berichten handelt es sich um die Datei "results. csv" und die Datei "Manifest. xml" (ausführliche Beschreibungen dieser Berichte finden Sie im Abschnitt [häufig gestellte Fragen zum Deaktivieren von Export Berichten](#frequently-asked-questions-about-disabling-export-reports) in diesem Thema).</span><span class="sxs-lookup"><span data-stu-id="158c3-106">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="158c3-107">Da diese Dateien sehr umfangreich sein können, können Sie die Downloadzeit beschleunigen und Speicherplatz sparen, indem Sie verhindern, dass diese Dateien exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="158c3-107">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="158c3-108">Sie können dies tun, indem Sie die Windows-Registrierung auf dem Computer ändern, den Sie zum Exportieren der Suchergebnisse verwenden.</span><span class="sxs-lookup"><span data-stu-id="158c3-108">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="158c3-109">Wenn Sie die Berichte zu einem späteren Zeitpunkt einbeziehen möchten, können Sie die Registrierungseinstellung bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="158c3-109">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="158c3-110">Erstellen von Registrierungseinstellungen zum Deaktivieren der Export Berichte</span><span class="sxs-lookup"><span data-stu-id="158c3-110">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="158c3-111">Führen Sie das folgende Verfahren auf dem Computer aus, mit dem Sie die Ergebnisse mit einer Inhaltssuche exportieren.</span><span class="sxs-lookup"><span data-stu-id="158c3-111">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="158c3-112">Schließen Sie das eDiscovery-Export Tool, wenn es geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="158c3-112">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="158c3-113">Führen Sie einen oder beide der folgenden Schritte aus, je nachdem, welchen Exportbericht Sie deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="158c3-113">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="158c3-114">**Results. CSV**</span><span class="sxs-lookup"><span data-stu-id="158c3-114">**Results.csv**</span></span>
    
      <span data-ttu-id="158c3-115">Speichern Sie den folgenden Text in einer Windows-Registrierungsdatei unter Verwendung eines filename-Suffixes von. reg; Beispiel: DisableResultsCsv. reg.</span><span class="sxs-lookup"><span data-stu-id="158c3-115">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="158c3-116">**Manifest. XML**</span><span class="sxs-lookup"><span data-stu-id="158c3-116">**Manifest.xml**</span></span>
    
      <span data-ttu-id="158c3-117">Speichern Sie den folgenden Text in einer Windows-Registrierungsdatei unter Verwendung eines filename-Suffixes von. reg; Beispiel: DisableManifestXml. reg.</span><span class="sxs-lookup"><span data-stu-id="158c3-117">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="158c3-118">Klicken oder Doppelklicken Sie in Windows-Explorer auf die reg-Datei, die Sie in den vorherigen Schritten erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="158c3-118">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="158c3-119">Klicken Sie im Fenster Benutzerzugriffssteuerung auf **Ja** , damit der Registrierungs-Editor die Änderung vornehmen kann.</span><span class="sxs-lookup"><span data-stu-id="158c3-119">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="158c3-120">Wenn Sie aufgefordert werden, den Vorgang fortzusetzen, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="158c3-120">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="158c3-121">Der Registrierungs-Editor zeigt eine Meldung an, die besagt, dass die Einstellung der Registrierung erfolgreich hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="158c3-121">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="158c3-122">Bearbeiten von Registrierungseinstellungen zum erneuten Aktivieren der Export Berichte</span><span class="sxs-lookup"><span data-stu-id="158c3-122">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="158c3-123">Wenn Sie die Berichte "results. csv" und "Manifest. xml" durch Erstellen der reg-Dateien im vorherigen Verfahren deaktiviert haben, können Sie diese Dateien bearbeiten, um einen Bericht erneut zu aktivieren, sodass er mit den Suchergebnissen exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="158c3-123">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="158c3-124">Führen Sie erneut das folgende Verfahren auf dem Computer aus, mit dem Sie die Ergebnisse mit einer Inhaltssuche exportieren.</span><span class="sxs-lookup"><span data-stu-id="158c3-124">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="158c3-125">Schließen Sie das eDiscovery-Export Tool, wenn es geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="158c3-125">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="158c3-126">Bearbeiten Sie eine oder beide der reg-Bearbeitungs Dateien, die Sie im vorherigen Verfahren erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="158c3-126">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="158c3-127">**Results. CSV**</span><span class="sxs-lookup"><span data-stu-id="158c3-127">**Results.csv**</span></span>
    
        <span data-ttu-id="158c3-128">Öffnen Sie die Datei DisableResultsCsv. reg im Editor, ändern Sie `False` den `True`Wert in, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="158c3-128">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="158c3-129">Nachdem Sie die Datei beispielsweise bearbeitet haben, sieht Sie wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="158c3-129">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="158c3-130">**Manifest. XML**</span><span class="sxs-lookup"><span data-stu-id="158c3-130">**Manifest.xml**</span></span>
    
        <span data-ttu-id="158c3-131">Öffnen Sie die Datei DisableManifestXml. reg im Editor, ändern Sie `False` den `True`Wert in, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="158c3-131">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="158c3-132">Nachdem Sie die Datei beispielsweise bearbeitet haben, sieht Sie wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="158c3-132">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="158c3-133">Klicken oder Doppelklicken Sie in Windows-Explorer auf eine REG-Datei, die Sie im vorherigen Schritt bearbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="158c3-133">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="158c3-134">Klicken Sie im Fenster Benutzerzugriffssteuerung auf **Ja** , damit der Registrierungs-Editor die Änderung vornehmen kann.</span><span class="sxs-lookup"><span data-stu-id="158c3-134">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="158c3-135">Wenn Sie aufgefordert werden, den Vorgang fortzusetzen, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="158c3-135">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="158c3-136">Der Registrierungs-Editor zeigt eine Meldung an, die besagt, dass die Einstellung der Registrierung erfolgreich hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="158c3-136">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="158c3-137">Häufig gestellte Fragen zum Deaktivieren von Export Berichten</span><span class="sxs-lookup"><span data-stu-id="158c3-137">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="158c3-138">**Was sind die Berichte "results. csv" und "Manifest. xml"?**</span><span class="sxs-lookup"><span data-stu-id="158c3-138">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="158c3-139">Die Dateien results. CSV und Manifest. XML enthalten zusätzliche Informationen über den exportierten Inhalt.</span><span class="sxs-lookup"><span data-stu-id="158c3-139">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="158c3-140">**Results. CSV** ein Excel-Dokument, das Informationen zu jedem Element enthält, das als Suchergebnis heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="158c3-140">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="158c3-141">Bei e-Mails enthält das Ergebnisprotokoll Informationen zu den einzelnen Nachrichten, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="158c3-141">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="158c3-142">Der Speicherort der Nachricht im Quellpostfach (einschließlich der Angabe, ob die Nachricht sich im primären oder im Archivpostfach befindet).</span><span class="sxs-lookup"><span data-stu-id="158c3-142">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="158c3-143">Das Datum, an dem die Nachricht gesendet oder empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="158c3-143">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="158c3-144">Die Betreffzeile der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="158c3-144">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="158c3-145">Absender und Empfänger der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="158c3-145">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="158c3-146">Gibt an, ob es sich bei der Nachricht um eine doppelte Nachricht handelt, wenn Sie beim Exportieren der Suchergebnisse die Deduplizierung aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="158c3-146">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="158c3-147">Doppelte Nachrichten weisen einen Wert in der **übergeordneten Itemid** -Spalte auf, die die Nachricht als Duplikat identifiziert.</span><span class="sxs-lookup"><span data-stu-id="158c3-147">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="158c3-148">Der Wert in der **übergeordneten Itemid** -Spalte ist identisch mit dem Wert in der Spalte **Element Dokument-Nr** der exportierten Nachricht.</span><span class="sxs-lookup"><span data-stu-id="158c3-148">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="158c3-149">Bei Dokumenten aus SharePoint-und OneDrive für Unternehmen-Websites enthält das Ergebnisprotokoll Informationen zu den einzelnen Dokumenten, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="158c3-149">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="158c3-150">Die URL für das Dokument.</span><span class="sxs-lookup"><span data-stu-id="158c3-150">The URL for the document.</span></span>
    
  - <span data-ttu-id="158c3-151">Die URL für die Websitesammlung, in der sich das Dokument befindet.</span><span class="sxs-lookup"><span data-stu-id="158c3-151">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="158c3-152">Das Datum, an dem das Dokument zuletzt geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="158c3-152">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="158c3-153">Der Name des Dokuments (der sich in der Spalte Betreff im Ergebnisprotokoll befindet).</span><span class="sxs-lookup"><span data-stu-id="158c3-153">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="158c3-154">**Manifest. XML** eine Manifestdatei (im XML-Format), die Informationen zu jedem Element enthält, das in den Suchergebnissen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="158c3-154">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="158c3-155">Die Informationen in diesem Bericht sind identisch mit dem Bericht "results. csv", jedoch in dem Format, das im Electronic Discovery Reference Model (EDRM) angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="158c3-155">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="158c3-156">Weitere Informationen zu EDRM finden Sie unter [https://www.edrm.net](https://www.edrm.net).</span><span class="sxs-lookup"><span data-stu-id="158c3-156">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="158c3-157">**Wann sollte ich den Export dieser Berichte deaktivieren?**</span><span class="sxs-lookup"><span data-stu-id="158c3-157">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="158c3-158">Dies hängt von ihren spezifischen Anforderungen ab.</span><span class="sxs-lookup"><span data-stu-id="158c3-158">It depends on your specific needs.</span></span> <span data-ttu-id="158c3-159">Viele Organisationen benötigen keine zusätzlichen Informationen zu Suchergebnissen und benötigen diese Berichte nicht.</span><span class="sxs-lookup"><span data-stu-id="158c3-159">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="158c3-160">**Auf welchem Computer muss ich diese Funktion ausführen?**</span><span class="sxs-lookup"><span data-stu-id="158c3-160">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="158c3-161">Sie müssen die Registrierungseinstellung auf einem lokalen Computer ändern, auf dem Sie das eDiscovery-Export Tool ausführen.</span><span class="sxs-lookup"><span data-stu-id="158c3-161">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="158c3-162">**Muss ich den Computer neu starten, nachdem ich diese Einstellung geändert habe?**</span><span class="sxs-lookup"><span data-stu-id="158c3-162">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="158c3-163">Nein, Sie müssen den Computer nicht neu starten.</span><span class="sxs-lookup"><span data-stu-id="158c3-163">No, you don't have to restart the computer.</span></span> <span data-ttu-id="158c3-164">Wenn das eDiscovery-Export Tool jedoch aktiv ist, müssen Sie es schließen und neu starten, nachdem Sie die Registrierungseinstellung geändert haben.</span><span class="sxs-lookup"><span data-stu-id="158c3-164">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="158c3-165">**Wird ein vorhandener Registrierungsschlüssel bearbeitet oder wird ein neuer Schlüssel erstellt?**</span><span class="sxs-lookup"><span data-stu-id="158c3-165">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="158c3-166">Ein neuer Registrierungsschlüssel wird erstellt, wenn Sie die reg-Datei zum ersten Mal ausführen, die Sie im Verfahren in diesem Thema erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="158c3-166">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="158c3-167">Anschließend wird die Einstellung jedes Mal bearbeitet, wenn Sie die reg-Bearbeitungs Datei ändern und erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="158c3-167">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
