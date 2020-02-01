---
title: Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Administratoren können die Unterstützung für die Sensitivitäts Bezeichnung für Word-, Excel-und PowerPoint-Dateien in SharePoint und OneDrive aktivieren.
ms.openlocfilehash: a1b42525984080d56a0f95018003cd251bff0122
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597502"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="64c29-103">Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive (öffentliche Vorschau)</span><span class="sxs-lookup"><span data-stu-id="64c29-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="64c29-104">Vor dieser Vorschau haben Sie bei der Anwendung von Sensitivitäts Bezeichnungen, die die Verschlüsselung in Office-Dateien in SharePoint und OneDrive gespeichert haben, den Inhalt dieser Dateien nicht verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="64c29-104">Before this preview, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="64c29-105">Die gemeinsame Dokumenterstellung, eDiscovery, Verhinderung von Datenverlust, Suche, vertiefen und anderen kollaborativen Features funktionierte unter diesen Umständen nicht.</span><span class="sxs-lookup"><span data-stu-id="64c29-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="64c29-106">In dieser Vorschau werden diese Funktionen aktiviert, wenn die Verschlüsselung mit einem cloudbasierten Schlüssel angewendet wurde:</span><span class="sxs-lookup"><span data-stu-id="64c29-106">This preview enables these features when the encryption has been applied with a cloud-based key:</span></span>

- <span data-ttu-id="64c29-107">SharePoint erkennt Vertraulichkeits Bezeichnungen, die auf Word-, Excel-und PowerPoint-Dateien in SharePoint und OneDrive angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="64c29-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="64c29-108">SharePoint erzwingt auch die Einstellungen, die mit den einzelnen Bezeichnungen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="64c29-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="64c29-109">Wenn Sie eine Datei aus SharePoint oder OneDrive herunterladen, wird die Vertraulichkeits Bezeichnung mit der Datei durchgesetzt, und die Einstellungen bleiben erhalten.</span><span class="sxs-lookup"><span data-stu-id="64c29-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="64c29-110">Wenden Sie Sensitivitäts Bezeichnungen auf Office-Dateien an, und öffnen und bearbeiten Sie Dateien, auf die die Vertraulichkeits Bezeichnungen angewendet werden (sofern die Berechtigungen der Bezeichnung dies zulassen), indem Sie die Webversionen von Word, Excel und PowerPoint verwenden.</span><span class="sxs-lookup"><span data-stu-id="64c29-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="64c29-111">Bei Word im Internet können Sie beim Bearbeiten von Dokumenten auch die automatische Beschriftung verwenden.</span><span class="sxs-lookup"><span data-stu-id="64c29-111">With Word on the web, you can also use auto labeling when you edit documents.</span></span>

- <span data-ttu-id="64c29-112">Office 365 eDiscovery unterstützt die Volltextsuche in Dateien, auf die Sensitivitäts Bezeichnungen angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="64c29-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="64c29-113">DLP-Richtlinien (Data Loss Prevention) decken Inhalte in diesen Dateien ab.</span><span class="sxs-lookup"><span data-stu-id="64c29-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="64c29-114">Für die Überwachung von Sensitivitäts Bezeichnungen stehen drei neue Überwachungsereignisse zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="64c29-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="64c29-115">FileSensitivityApplied</span><span class="sxs-lookup"><span data-stu-id="64c29-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="64c29-116">FileSensitivityLabelChanged</span><span class="sxs-lookup"><span data-stu-id="64c29-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="64c29-117">FileSensitivityLabelRemoved</span><span class="sxs-lookup"><span data-stu-id="64c29-117">FileSensitivityLabelRemoved</span></span>

> [!NOTE]
> <span data-ttu-id="64c29-118">Wenn die Verschlüsselung nicht mit einem cloudbasierten Schlüssel, sondern mit einem lokalen Schlüssel, einer wichtigen Verwaltungstopologie, die häufig als "eigenen Schlüssel halten" (Hyok), verwendet wurde, ändert sich das SharePoint-Verhalten bei dieser Vorschau nicht.</span><span class="sxs-lookup"><span data-stu-id="64c29-118">If encryption hasn't been applied with a cloud-based key but an on-premises key, a key management topology often referred to as "hold your own key" (HYOK), the SharePoint behavior doesn't change with this preview.</span></span> 

<span data-ttu-id="64c29-119">Sie können jetzt auch Vertraulichkeits Bezeichnungen auf Microsoft Teams, Office 365 Gruppen und SharePoint-Websites anwenden.</span><span class="sxs-lookup"><span data-stu-id="64c29-119">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="64c29-120">Weitere Informationen zu dieser separaten Vorschau finden Sie unter [use Sensitivity Labels with Microsoft Teams, Office 365 Groups, and SharePoint Sites (Public Preview)](sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="64c29-120">For more information about this separate preview, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="64c29-121">Sie haben jederzeit die Möglichkeit, diese Vorschau jederzeit zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="64c29-121">You always have the choice to opt out of this preview at any time.</span></span>

<span data-ttu-id="64c29-122">Sehen Sie sich das folgende Video (kein Audio) an, um diese neuen Funktionen in Aktion anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="64c29-122">Watch the following video (no audio) to see these new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a><span data-ttu-id="64c29-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="64c29-123">Requirements</span></span>

<span data-ttu-id="64c29-124">Diese Features funktionieren nur mit [Vertraulichkeits Bezeichnungen](sensitivity-labels.md) .</span><span class="sxs-lookup"><span data-stu-id="64c29-124">These features work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="64c29-125">Wenn Sie derzeit über Azure Information Protection-Bezeichnungen verfügen, migrieren Sie Sie zunächst zu Sensitivitäts Bezeichnungen, sodass Sie diese Funktionen für neue Dateien, die Sie hochladen, aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="64c29-125">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="64c29-126">Anweisungen finden Sie unter [How to migrate Azure Information Protection Labels to Unified Sensitivity Labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span><span class="sxs-lookup"><span data-stu-id="64c29-126">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="64c29-127">Verwenden Sie für diese Vorschau die OneDrive-Synchronisierungs-App-Version 19.002.0121.0008 oder höher unter Windows und Version 19.002.0107.0008 oder höher unter Mac.</span><span class="sxs-lookup"><span data-stu-id="64c29-127">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="64c29-128">Beide Versionen wurden am 28. Januar 2019 veröffentlicht und sind derzeit für alle Ringe freigegeben.</span><span class="sxs-lookup"><span data-stu-id="64c29-128">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="64c29-129">Weitere Informationen finden Sie in den [Anmerkungen zur OneDrive-Version](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span><span class="sxs-lookup"><span data-stu-id="64c29-129">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="64c29-130">Nachdem Sie diese Vorschau aktiviert haben, werden Benutzer, die eine ältere Version der Synchronisierungs-app ausführen, aufgefordert, Sie zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="64c29-130">After you enable this preview, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="64c29-131">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="64c29-131">Limitations</span></span>

- <span data-ttu-id="64c29-132">Wenn Sie diese Vorschau aktivieren, können Benutzer, die eine Bezeichnung in eine Datei in einem OneDrive-synchronisierungsordner ändern, möglicherweise keine anderen an der Datei vorgenommenen Änderungen speichern.</span><span class="sxs-lookup"><span data-stu-id="64c29-132">When you enable this preview, users who change a label to a file in a OneDrive Sync folder might be unable to save other changes they make to the file.</span></span>  <span data-ttu-id="64c29-133">Benutzer sehen einen [roten Kreis mit einem weißen Kreuz Symbol Fehler](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), und Sie werden aufgefordert, neue Änderungen als separate Kopie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="64c29-133">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span>  <span data-ttu-id="64c29-134">Neben Bezeichnungsänderungen, die von Benutzern initiiert werden, kann dasselbe Verhalten auftreten, wenn ein Administratoreinstellungen für eine veröffentlichte Bezeichnung ändert, die bereits auf Dateien angewendet wird, die auf den synchronisierungsclient des Benutzers heruntergeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="64c29-134">In addition to label changes that are initiated by users, the same behavior can occur if an admin changes settings for a published label that's already applied to files downloaded to users' sync client.</span></span>
    
    <span data-ttu-id="64c29-135">Führen Sie eine der folgenden Aktionen aus, um den Verlust von Arbeit für diese Szenarien zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="64c29-135">To avoid losing work for these scenarios, do one of these actions:</span></span>
    - <span data-ttu-id="64c29-136">Verwenden Sie die Webversionen der Office-Apps, um Bezeichnungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="64c29-136">To apply labels, use the web versions of the Office apps.</span></span>
    - <span data-ttu-id="64c29-137">Schließen Sie eine Datei, nachdem Sie eine Bezeichnung angewendet haben, und öffnen Sie die Datei erneut, um weitere Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="64c29-137">Close a file after you apply a label, and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="64c29-138">SharePoint wendet die neuen Bezeichnungen nicht automatisch auf vorhandene Dateien an, die Sie bereits mithilfe von Azure Information Protection-Bezeichnungen verschlüsselt haben.</span><span class="sxs-lookup"><span data-stu-id="64c29-138">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="64c29-139">Um die Funktionen zu erhalten, nachdem Sie diese Vorschau aktiviert haben, müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="64c29-139">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>
    
    1. <span data-ttu-id="64c29-140">Stellen Sie sicher, dass Sie die Azure Information Protection-Bezeichnungen zu Sensitivitäts Bezeichnungen migriert und diese im Microsoft 365 Compliance Center oder in einer entsprechenden Bezeichnungs Verwaltungskonsole veröffentlicht haben.</span><span class="sxs-lookup"><span data-stu-id="64c29-140">Make sure you have migrated the Azure Information Protection labels to sensitivity labels and published them from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="64c29-141">Laden Sie die Dateien herunter, und laden Sie Sie in SharePoint hoch.</span><span class="sxs-lookup"><span data-stu-id="64c29-141">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="64c29-142">In SharePoint können keine verschlüsselten Dateien verarbeitet werden, wenn die Bezeichnung, auf die die Verschlüsselung angewendet wird, eine der folgenden Konfigurationen für die Verschlüsselung aufweist:</span><span class="sxs-lookup"><span data-stu-id="64c29-142">SharePoint can't process encrypted files when the label that applied the encryption has either of the following configurations for encryption:</span></span>
    - <span data-ttu-id="64c29-143">**Zulassen, dass Benutzerberechtigungen zuweisen, wenn Sie die Bezeichnung anwenden** , und **in Word, PowerPoint und Excel Benutzer zur Angabe von Berechtigungen auffordern**</span><span class="sxs-lookup"><span data-stu-id="64c29-143">**Let users assign permissions when they apply the label** and **In Word, PowerPoint, and Excel, prompt users to specify permissions**</span></span>
    - <span data-ttu-id="64c29-144">Der **Benutzer Zugriff auf Inhalts Ablauf** wird auf einen anderen Wert als **Never**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="64c29-144">**User access to content expires** is set to a value other than **Never**.</span></span>

- <span data-ttu-id="64c29-145">Für ein verschlüsseltes Dokument, das Bearbeitungsberechtigungen für einen Benutzer gewährt, kann das Kopieren in den Webversionen der Office-Apps nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="64c29-145">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="64c29-146">Die Dokument Verfolgungs Website für Azure Information Protection wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="64c29-146">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="64c29-147">Office-Desktop-Apps und Mobile Apps unterstützen nicht die gemeinsame Dokumenterstellung.</span><span class="sxs-lookup"><span data-stu-id="64c29-147">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="64c29-148">Stattdessen öffnen diese apps weiterhin Dateien im exklusiven Bearbeitungsmodus.</span><span class="sxs-lookup"><span data-stu-id="64c29-148">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="64c29-149">Wenn eine Beschriftung eine Verschlüsselung enthält, kann Microsoft Cloud App Security die Bezeichnungsinformationen für die Dateien in SharePoint nicht lesen.</span><span class="sxs-lookup"><span data-stu-id="64c29-149">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="64c29-150">Vorbereiten der SharePoint Online Management-Shell für die Vorschau</span><span class="sxs-lookup"><span data-stu-id="64c29-150">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="64c29-151">Vergewissern Sie sich vor dem Aktivieren der Vorschau, dass SharePoint Online Verwaltungsshell Version 16.0.19418.12000 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="64c29-151">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="64c29-152">Wenn Sie bereits über die neueste Version verfügen, können Sie die Vorschau aktivieren.</span><span class="sxs-lookup"><span data-stu-id="64c29-152">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="64c29-153">Wenn Sie eine frühere Version der SharePoint Online Management Shell aus dem PowerShell-Katalog installiert haben, können Sie das Modul aktualisieren, indem Sie das folgende Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="64c29-153">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="64c29-154">Wenn Sie eine frühere Version der SharePoint Online Management Shell aus dem Microsoft Download Center installiert haben, können Sie auch zum **Hinzufügen oder Entfernen von Software** wechseln und die SharePoint Online Management Shell deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="64c29-154">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="64c29-155">Wechseln Sie in einem Webbrowser zur Download Center-Seite, und [laden Sie die neueste SharePoint Online-Verwaltungsshell herunter](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="64c29-155">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="64c29-156">Wählen Sie die gewünschte Sprache aus, und klicken Sie auf **Download**.</span><span class="sxs-lookup"><span data-stu-id="64c29-156">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="64c29-157">Wählen Sie zwischen der x64- und der x86-Version der MSI-Datei aus.</span><span class="sxs-lookup"><span data-stu-id="64c29-157">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="64c29-158">Laden Sie die x64-Datei herunter, wenn Sie die 64-Bit-Version von Windows oder die x86-Datei ausführen, wenn Sie die 32-Bit-Version ausführen.</span><span class="sxs-lookup"><span data-stu-id="64c29-158">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="64c29-159">Wenn Sie nicht wissen, finden Sie unter [welche Version des Windows-Betriebssystems soll ich ausführen?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="64c29-159">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="64c29-160">Nachdem Sie die Datei heruntergeladen haben, führen Sie die Datei aus, und führen Sie die Schritte im Setup-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="64c29-160">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="64c29-161">Aktivieren der Vorschau mithilfe von Microsoft PowerShell (Opt-in)</span><span class="sxs-lookup"><span data-stu-id="64c29-161">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="64c29-162">Verwenden Sie zum Aktivieren der Vorschau das Cmdlet "SPOTenant":</span><span class="sxs-lookup"><span data-stu-id="64c29-162">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="64c29-163">Stellen Sie eine Verbindung mit SharePoint her, indem Sie ein Arbeits-oder Schulkonto mit globalen Administrator-oder SharePoint-Administratorrechten in Office 365 verwenden.</span><span class="sxs-lookup"><span data-stu-id="64c29-163">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="64c29-164">Eine Anleitung dazu finden Sie unter [Erste Schritte mit der SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="64c29-164">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="64c29-165">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="64c29-165">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="64c29-166">Planen des Roll-out nach dem Erstellen oder Ändern einer Sensitivitäts Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="64c29-166">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="64c29-167">Nachdem Sie eine Sensitivitäts Bezeichnung im Microsoft 365 Compliance Center erstellt oder geändert haben, veröffentlichen Sie Sie in Phasen.</span><span class="sxs-lookup"><span data-stu-id="64c29-167">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="64c29-168">Wenn Sie Bezeichnungen veröffentlichen, die nicht vollständig synchronisiert sind, können die Dateien nicht in den Webversionen der Office-Apps geöffnet werden, wenn die Benutzer die Bezeichnungen auf Dateien anwenden und in SharePoint hochladen.</span><span class="sxs-lookup"><span data-stu-id="64c29-168">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="64c29-169">Such-und eDiscovery funktionieren auch nicht für die Dateien.</span><span class="sxs-lookup"><span data-stu-id="64c29-169">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="64c29-170">Es wird empfohlen, dass Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="64c29-170">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="64c29-171">Veröffentlichen Sie die neue oder geänderte Vertraulichkeits Bezeichnung nur für eine oder zwei Personen.</span><span class="sxs-lookup"><span data-stu-id="64c29-171">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="64c29-172">Warten Sie mindestens 24 Stunden nach der ersten Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="64c29-172">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="64c29-173">Stellen Sie sicher, dass die Bezeichnung vollständig synchronisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="64c29-173">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="64c29-174">Veröffentlichen Sie das Label breiter.</span><span class="sxs-lookup"><span data-stu-id="64c29-174">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="64c29-175">Deaktivieren der Vorschau mithilfe von Microsoft PowerShell (Opt-out)</span><span class="sxs-lookup"><span data-stu-id="64c29-175">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="64c29-176">Wenn Sie diese Vorschau deaktivieren, werden Dateien, die Sie während der Vorschau hochgeladen haben, weiterhin durch die Bezeichnung geschützt.</span><span class="sxs-lookup"><span data-stu-id="64c29-176">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="64c29-177">Die entsprechenden Einstellungen werden weiterhin erzwungen.</span><span class="sxs-lookup"><span data-stu-id="64c29-177">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="64c29-178">Wenn Sie Bezeichnungen auf neue Dateien anwenden, nachdem Sie die Vorschau deaktiviert haben, können die Volltextsuche, eDiscovery und die gemeinsame Dokumenterstellung nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="64c29-178">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="64c29-179">Verwenden Sie das Cmdlet "SPOTenant", um die Vorschau zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="64c29-179">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="64c29-180">Stellen Sie eine Verbindung mit SharePoint her, indem Sie ein Arbeits-oder Schulkonto mit globalen Administrator-oder SharePoint-Administratorrechten in Office 365 verwenden.</span><span class="sxs-lookup"><span data-stu-id="64c29-180">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="64c29-181">Eine Anleitung dazu finden Sie unter [Erste Schritte mit der SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="64c29-181">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="64c29-182">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="64c29-182">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
