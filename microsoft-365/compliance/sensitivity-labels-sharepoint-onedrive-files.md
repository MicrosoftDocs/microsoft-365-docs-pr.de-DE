---
title: Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/01/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Administratoren können die Unterstützung für die Sensitivitäts Bezeichnung für Word-, Excel-und PowerPoint-Dateien in SharePoint und OneDrive aktivieren.
ms.openlocfilehash: c62db0d77ed805c607e79bf25cb9816a554cb6d2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802828"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="6d644-103">Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive (öffentliche Vorschau)</span><span class="sxs-lookup"><span data-stu-id="6d644-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="6d644-104">Wenn Sie zuvor Sensitivitäts Bezeichnungen angewendet haben, die die Verschlüsselung in Office-Dateien in SharePoint und OneDrive gespeichert haben, konnte der Dienst den Inhalt dieser Dateien nicht verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6d644-104">Previously, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="6d644-105">Die gemeinsame Dokumenterstellung, eDiscovery, Verhinderung von Datenverlust, Suche, vertiefen und anderen kollaborativen Features funktionierte unter diesen Umständen nicht.</span><span class="sxs-lookup"><span data-stu-id="6d644-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="6d644-106">In dieser Vorschau werden diese Funktionen aktiviert:</span><span class="sxs-lookup"><span data-stu-id="6d644-106">This preview enables these features:</span></span>

- <span data-ttu-id="6d644-107">SharePoint erkennt Vertraulichkeits Bezeichnungen, die auf Word-, Excel-und PowerPoint-Dateien in SharePoint und OneDrive angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6d644-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="6d644-108">SharePoint erzwingt auch die Einstellungen, die mit den einzelnen Bezeichnungen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6d644-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="6d644-109">Wenn Sie eine Datei aus SharePoint oder OneDrive herunterladen, wird die Vertraulichkeits Bezeichnung mit der Datei durchgesetzt, und die Einstellungen bleiben erhalten.</span><span class="sxs-lookup"><span data-stu-id="6d644-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="6d644-110">Wenden Sie Sensitivitäts Bezeichnungen auf Office-Dateien an, und öffnen und bearbeiten Sie Dateien, auf die die Vertraulichkeits Bezeichnungen angewendet werden (sofern die Berechtigungen der Bezeichnung dies zulassen), indem Sie die Webversionen von Word, Excel und PowerPoint verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d644-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="6d644-111">Bei Word im Internet können Sie beim Bearbeiten von Dokumenten auch die automatische Beschriftung verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d644-111">With Word on the web, you can also use Auto labeling when you edit documents.</span></span>

- <span data-ttu-id="6d644-112">Office 365 eDiscovery unterstützt die Volltextsuche in Dateien, auf die Sensitivitäts Bezeichnungen angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="6d644-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="6d644-113">DLP-Richtlinien (Data Loss Prevention) decken Inhalte in diesen Dateien ab.</span><span class="sxs-lookup"><span data-stu-id="6d644-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="6d644-114">Für die Überwachung von Sensitivitäts Bezeichnungen stehen drei neue Überwachungsereignisse zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="6d644-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="6d644-115">FileSensitivityApplied</span><span class="sxs-lookup"><span data-stu-id="6d644-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="6d644-116">FileSensitivityLabelChanged</span><span class="sxs-lookup"><span data-stu-id="6d644-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="6d644-117">FileSensitivityLabelRemoved</span><span class="sxs-lookup"><span data-stu-id="6d644-117">FileSensitivityLabelRemoved</span></span>

<span data-ttu-id="6d644-118">Sie können jetzt auch Vertraulichkeits Bezeichnungen auf Microsoft Teams, Office 365 Gruppen und SharePoint-Websites anwenden.</span><span class="sxs-lookup"><span data-stu-id="6d644-118">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="6d644-119">[Weitere Informationen](sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="6d644-119">[Learn more](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="6d644-120">Bei Bedarf können Sie die Vorschau jederzeit deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6d644-120">If necessary, you can opt out of the preview at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="6d644-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d644-121">Requirements</span></span>

<span data-ttu-id="6d644-122">Diese Features funktionieren nur mit [Sensitivitäts Bezeichnungen](sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="6d644-122">These features work only with [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="6d644-123">Wenn Sie Azure Information Protection-Bezeichnungen verwendet haben, können Sie diese in Sensitivitäts Bezeichnungen umwandeln, um diese Funktionen für neue Dateien, die Sie hochladen, zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6d644-123">If you used Azure Information Protection labels, you can convert them to sensitivity labels to enable these features for new files that you upload.</span></span> [<span data-ttu-id="6d644-124">Erfahren Sie, wie</span><span class="sxs-lookup"><span data-stu-id="6d644-124">Learn how</span></span>](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

<span data-ttu-id="6d644-125">Verwenden Sie für diese Vorschau die OneDrive-Synchronisierungs-App-Version 19.002.0121.0008 oder höher unter Windows und Version 19.002.0107.0008 oder höher unter Mac.</span><span class="sxs-lookup"><span data-stu-id="6d644-125">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="6d644-126">Beide Versionen wurden am 28. Januar 2019 veröffentlicht und sind derzeit für alle Ringe freigegeben.</span><span class="sxs-lookup"><span data-stu-id="6d644-126">Both of these versions were released on January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="6d644-127">[Weitere Informationen finden Sie in den OneDrive-Versions](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)hinweisen.</span><span class="sxs-lookup"><span data-stu-id="6d644-127">[See the OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="6d644-128">Nachdem Sie diese Vorschau aktiviert haben, werden Benutzer, die eine ältere Version der Synchronisierungs-app ausführen, zur Aktualisierung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6d644-128">After you enable this preview, users who run an older version of the sync app will be prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="6d644-129">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6d644-129">Limitations</span></span>

- <span data-ttu-id="6d644-130">Wenn Sie diese Vorschau aktivieren, können Benutzer, die mithilfe des Office-Desktops oder Mobile Apps eine Bezeichnung auf eine Datei anwenden, möglicherweise keine weiteren Änderungen speichern, die Sie an der Datei vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="6d644-130">When you enable this preview, users who apply a label to a file by using the Office desktop or mobile apps might be unable to save other changes they make to the file.</span></span> <span data-ttu-id="6d644-131">Stattdessen werden Benutzer von der APP aufgefordert, lokale Änderungen zu speichern oder zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="6d644-131">Instead, the app prompts users to Save As or Discard local changes.</span></span> <span data-ttu-id="6d644-132">Führen Sie eine der folgenden Aktionen aus, um einen Verlust der Arbeit zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="6d644-132">To avoid losing work, do one of these actions:</span></span>

  - <span data-ttu-id="6d644-133">Verwenden Sie die Webversionen der Office-Apps, um Bezeichnungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="6d644-133">To apply labels, use the web versions of the Office apps.</span></span>

  - <span data-ttu-id="6d644-134">Schließen Sie eine Datei, nachdem Sie eine Bezeichnung angewendet haben, und öffnen Sie die Datei erneut, um weitere Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="6d644-134">Close a file after you apply a label and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="6d644-135">SharePoint wendet die neuen Bezeichnungen nicht automatisch auf vorhandene Dateien an, die Sie bereits mithilfe von Azure Information Protection-Bezeichnungen verschlüsselt haben.</span><span class="sxs-lookup"><span data-stu-id="6d644-135">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="6d644-136">Um die Funktionen zu erhalten, nachdem Sie diese Vorschau aktiviert haben, müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="6d644-136">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>

  - <span data-ttu-id="6d644-137">Konvertieren Sie die Azure Information Protection-Bezeichnungen in Sensitivitäts Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="6d644-137">Convert the Azure Information Protection labels to sensitivity labels.</span></span>

  - <span data-ttu-id="6d644-138">Laden Sie die Dateien herunter, und laden Sie Sie in SharePoint hoch.</span><span class="sxs-lookup"><span data-stu-id="6d644-138">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="6d644-139">SharePoint kann keine Beschriftungen mit benutzerdefinierten Berechtigungen und Beschriftungen mit Ablaufdaten verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6d644-139">SharePoint can't process labels with custom permissions and labels with expiration dates.</span></span>

- <span data-ttu-id="6d644-140">Wenn Benutzer über Bearbeitungsberechtigungen verfügen, können die Webversionen der Office-Apps unabhängig von der Einstellung der Kopierrichtlinie in der Bezeichnung kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="6d644-140">When users have edit permissions, the web versions of the Office apps allow copying regardless of the copy policy setting in the label.</span></span>

- <span data-ttu-id="6d644-141">RMS-Sperrung,-Nachverfolgung und-Berichterstellung werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6d644-141">RMS revocation, tracking, and reporting are unsupported.</span></span>

- <span data-ttu-id="6d644-142">Office-Desktop-Apps und Mobile Apps unterstützen nicht die gemeinsame Dokumenterstellung.</span><span class="sxs-lookup"><span data-stu-id="6d644-142">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="6d644-143">Stattdessen öffnen diese apps weiterhin Dateien im exklusiven Bearbeitungsmodus.</span><span class="sxs-lookup"><span data-stu-id="6d644-143">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="6d644-144">Wenn eine Beschriftung eine Verschlüsselung enthält, kann Microsoft Cloud App Security die Bezeichnungsinformationen für die Dateien in SharePoint nicht lesen.</span><span class="sxs-lookup"><span data-stu-id="6d644-144">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="6d644-145">Vorbereiten der SharePoint Online Management-Shell für die Vorschau</span><span class="sxs-lookup"><span data-stu-id="6d644-145">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="6d644-146">Vergewissern Sie sich vor dem Aktivieren der Vorschau, dass SharePoint Online Verwaltungsshell Version 16.0.19418.12000 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d644-146">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="6d644-147">Wenn Sie bereits über die neueste Version verfügen, können Sie die Vorschau aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6d644-147">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="6d644-148">Wenn Sie eine frühere Version der SharePoint Online Management Shell aus dem PowerShell-Katalog installiert haben, können Sie das Modul aktualisieren, indem Sie das folgende Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="6d644-148">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="6d644-149">Wenn Sie eine frühere Version der SharePoint Online Management Shell aus dem Microsoft Download Center installiert haben, können Sie auch zum **Hinzufügen oder Entfernen von Software** wechseln und die SharePoint Online Management Shell deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="6d644-149">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="6d644-150">Wechseln Sie in einem Webbrowser zur Seite Download Center, und [Laden Sie die neueste SharePoint Online Verwaltungsshell herunter](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="6d644-150">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="6d644-151">Wählen Sie Ihre Sprache aus, und klicken Sie dann auf **herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="6d644-151">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="6d644-152">Wählen Sie zwischen der Datei x64 und x86. msi aus.</span><span class="sxs-lookup"><span data-stu-id="6d644-152">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="6d644-153">Laden Sie die x64-Datei herunter, wenn Sie die 64-Bit-Version von Windows oder die x86-Datei ausführen, wenn Sie die 32-Bit-Version ausführen.</span><span class="sxs-lookup"><span data-stu-id="6d644-153">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="6d644-154">Wenn Sie nicht wissen, finden Sie unter [welche Version des Windows-Betriebssystems soll ich ausführen?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="6d644-154">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="6d644-155">Nachdem Sie die Datei heruntergeladen haben, führen Sie die Datei aus, und führen Sie die Schritte im Setup-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="6d644-155">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="6d644-156">Aktivieren der Vorschau mithilfe von Microsoft PowerShell (Opt-in)</span><span class="sxs-lookup"><span data-stu-id="6d644-156">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="6d644-157">Verwenden Sie zum Aktivieren der Vorschau das Cmdlet "SPOTenant":</span><span class="sxs-lookup"><span data-stu-id="6d644-157">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="6d644-158">Stellen Sie eine Verbindung mit SharePoint her, indem Sie ein Arbeits-oder Schulkonto mit globalen Administrator-oder SharePoint-Administratorrechten in Office 365 verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d644-158">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="6d644-159">Eine Anleitung dazu finden Sie unter [Erste Schritte mit der SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="6d644-159">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="6d644-160">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6d644-160">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="6d644-161">Planen des Roll-out nach dem Erstellen oder Ändern einer Sensitivitäts Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="6d644-161">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="6d644-162">Nachdem Sie eine Sensitivitäts Bezeichnung im Microsoft 365 Compliance Center erstellt oder geändert haben, veröffentlichen Sie Sie in Phasen.</span><span class="sxs-lookup"><span data-stu-id="6d644-162">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="6d644-163">Wenn Sie Bezeichnungen veröffentlichen, die nicht vollständig synchronisiert sind, können die Dateien nicht in den Webversionen der Office-Apps geöffnet werden, wenn die Benutzer die Bezeichnungen auf Dateien anwenden und in SharePoint hochladen.</span><span class="sxs-lookup"><span data-stu-id="6d644-163">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="6d644-164">Such-und eDiscovery funktionieren auch nicht für die Dateien.</span><span class="sxs-lookup"><span data-stu-id="6d644-164">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="6d644-165">Es wird empfohlen, dass Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="6d644-165">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="6d644-166">Veröffentlichen Sie die neue oder geänderte Vertraulichkeits Bezeichnung nur für eine oder zwei Personen.</span><span class="sxs-lookup"><span data-stu-id="6d644-166">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="6d644-167">Warten Sie mindestens 24 Stunden nach der ersten Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="6d644-167">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="6d644-168">Stellen Sie sicher, dass die Bezeichnung vollständig synchronisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6d644-168">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="6d644-169">Veröffentlichen Sie das Label breiter.</span><span class="sxs-lookup"><span data-stu-id="6d644-169">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="6d644-170">Deaktivieren der Vorschau mithilfe von Microsoft PowerShell (Opt-out)</span><span class="sxs-lookup"><span data-stu-id="6d644-170">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="6d644-171">Wenn Sie diese Vorschau deaktivieren, werden Dateien, die Sie während der Vorschau hochgeladen haben, weiterhin durch die Bezeichnung geschützt.</span><span class="sxs-lookup"><span data-stu-id="6d644-171">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="6d644-172">Die entsprechenden Einstellungen werden weiterhin erzwungen.</span><span class="sxs-lookup"><span data-stu-id="6d644-172">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="6d644-173">Wenn Sie Bezeichnungen auf neue Dateien anwenden, nachdem Sie die Vorschau deaktiviert haben, können die Volltextsuche, eDiscovery und die gemeinsame Dokumenterstellung nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6d644-173">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="6d644-174">Verwenden Sie das Cmdlet "SPOTenant", um die Vorschau zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="6d644-174">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="6d644-175">Stellen Sie eine Verbindung mit SharePoint her, indem Sie ein Arbeits-oder Schulkonto mit globalen Administrator-oder SharePoint-Administratorrechten in Office 365 verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d644-175">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="6d644-176">Eine Anleitung dazu finden Sie unter [Erste Schritte mit der SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="6d644-176">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="6d644-177">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6d644-177">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
