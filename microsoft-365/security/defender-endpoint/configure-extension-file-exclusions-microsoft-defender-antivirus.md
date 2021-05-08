---
title: Konfigurieren und Überprüfen von Ausschlüssen basierend auf Erweiterung, Name oder Speicherort
description: Schließen Sie Dateien basierend auf der Dateierweiterung, dem Dateinamen oder dem Speicherort von Microsoft Defender Antivirus-Scans aus.
keywords: Ausschlüsse, Dateien, Erweiterung, Dateityp, Ordnername, Dateiname, Scans
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 3d65275d504ece4ac298558e660fa70c32a76d06
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274532"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a><span data-ttu-id="031be-104">Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateierweiterung und Ordnerspeicherort</span><span class="sxs-lookup"><span data-stu-id="031be-104">Configure and validate exclusions based on file extension and folder location</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="031be-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="031be-105">**Applies to:**</span></span>

- [<span data-ttu-id="031be-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="031be-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="031be-107">Microsoft Defender Antivirus-Ausschlüsse gelten nicht für andere Microsoft Defender for Endpoint-Funktionen, einschließlich Endpunkterkennung und -reaktion [(EDR),](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)Regeln zur Reduzierung der Angriffsfläche [(Attack Surface Reduction, ASR)](/microsoft-365/security/defender-endpoint/attack-surface-reduction)und kontrollierter [Ordnerzugriff.](/microsoft-365/security/defender-endpoint/controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="031be-107">Microsoft Defender Antivirus exclusions don't apply to other Microsoft Defender for Endpoint capabilities, including [endpoint detection and response (EDR)](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response), [attack surface reduction (ASR) rules](/microsoft-365/security/defender-endpoint/attack-surface-reduction), and [controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span> <span data-ttu-id="031be-108">Dateien, die Sie mithilfe der in diesem Artikel beschriebenen Methoden ausschließen, können weiterhin EDR-Warnungen und andere Erkennungen auslösen.</span><span class="sxs-lookup"><span data-stu-id="031be-108">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span> <span data-ttu-id="031be-109">Um Dateien allgemein auszuschließen, fügen Sie sie den benutzerdefinierten Microsoft Defender for [Endpoint-Indikatoren hinzu.](/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="031be-109">To exclude files broadly, add them to the Microsoft Defender for Endpoint [custom indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

## <a name="exclusion-lists"></a><span data-ttu-id="031be-110">Ausschlusslisten</span><span class="sxs-lookup"><span data-stu-id="031be-110">Exclusion lists</span></span>

<span data-ttu-id="031be-111">Sie können bestimmte Dateien von Microsoft Defender Antivirus-Scans ausschließen, indem Sie Ausschlusslisten ändern.</span><span class="sxs-lookup"><span data-stu-id="031be-111">You can exclude certain files from Microsoft Defender Antivirus scans by modifying exclusion lists.</span></span> <span data-ttu-id="031be-112">**Im Allgemeinen sollten Sie keine Ausschlüsse anwenden müssen.**</span><span class="sxs-lookup"><span data-stu-id="031be-112">**Generally, you shouldn't need to apply exclusions**.</span></span> <span data-ttu-id="031be-113">Microsoft Defender Antivirus enthält viele automatische Ausschlüsse, die auf bekannten Betriebssystemverhalten und typischen Verwaltungsdateien basieren, z. B. solche, die in der Unternehmensverwaltung, datenbankverwaltung und anderen Unternehmensszenarien und -situationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="031be-113">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>

> [!NOTE]
> <span data-ttu-id="031be-114">Ausschlüsse gelten auch für Erkennungen von potenziell unerwünschten Apps (PuA).</span><span class="sxs-lookup"><span data-stu-id="031be-114">Exclusions apply to Potentially Unwanted Apps (PUA) detections as well.</span></span>

> [!NOTE]
> <span data-ttu-id="031be-115">Automatische Ausschlüsse gelten nur für Windows Server 2016 und höher.</span><span class="sxs-lookup"><span data-stu-id="031be-115">Automatic exclusions apply only to Windows Server 2016 and above.</span></span> <span data-ttu-id="031be-116">Diese Ausschlüsse sind in der Windows Security-App und in PowerShell nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="031be-116">These exclusions are not visible in the Windows Security app and in PowerShell.</span></span>

<span data-ttu-id="031be-117">In diesem Artikel wird beschrieben, wie Ausschlusslisten für die Dateien und Ordner konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="031be-117">This article  describes how to configure exclusion lists for the files and folders.</span></span> <span data-ttu-id="031be-118">Weitere [Informationen finden Sie unter Empfehlungen zum Definieren von Ausschlüssen,](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) bevor Sie Ihre Ausschlusslisten definieren.</span><span class="sxs-lookup"><span data-stu-id="031be-118">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

| <span data-ttu-id="031be-119">Ausschluss</span><span class="sxs-lookup"><span data-stu-id="031be-119">Exclusion</span></span> | <span data-ttu-id="031be-120">Beispiele</span><span class="sxs-lookup"><span data-stu-id="031be-120">Examples</span></span> | <span data-ttu-id="031be-121">Ausschlussliste</span><span class="sxs-lookup"><span data-stu-id="031be-121">Exclusion list</span></span> |
|:---|:---|:---|
|<span data-ttu-id="031be-122">Jede Datei mit einer bestimmten Erweiterung</span><span class="sxs-lookup"><span data-stu-id="031be-122">Any file with a specific extension</span></span> | <span data-ttu-id="031be-123">Alle Dateien mit der angegebenen Erweiterung an einer beliebigen Stelle auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="031be-123">All files with the specified extension, anywhere on the machine.</span></span> <p> <span data-ttu-id="031be-124">Gültige Syntax: `.test` und `test`</span><span class="sxs-lookup"><span data-stu-id="031be-124">Valid syntax: `.test` and `test`</span></span>  | <span data-ttu-id="031be-125">Erweiterungsausschlüsse</span><span class="sxs-lookup"><span data-stu-id="031be-125">Extension exclusions</span></span> |
|<span data-ttu-id="031be-126">Jede Datei unter einem bestimmten Ordner</span><span class="sxs-lookup"><span data-stu-id="031be-126">Any file under a specific folder</span></span> | <span data-ttu-id="031be-127">Alle Dateien unter dem `c:\test\sample` Ordner</span><span class="sxs-lookup"><span data-stu-id="031be-127">All files under the `c:\test\sample` folder</span></span> | <span data-ttu-id="031be-128">Datei- und Ordnerausschlüsse</span><span class="sxs-lookup"><span data-stu-id="031be-128">File and folder exclusions</span></span> |
| <span data-ttu-id="031be-129">Eine bestimmte Datei in einem bestimmten Ordner</span><span class="sxs-lookup"><span data-stu-id="031be-129">A specific file in a specific folder</span></span> | <span data-ttu-id="031be-130">Nur die `c:\sample\sample.test` Datei</span><span class="sxs-lookup"><span data-stu-id="031be-130">The file `c:\sample\sample.test` only</span></span> | <span data-ttu-id="031be-131">Datei- und Ordnerausschlüsse</span><span class="sxs-lookup"><span data-stu-id="031be-131">File and folder exclusions</span></span> |
| <span data-ttu-id="031be-132">Ein bestimmter Prozess</span><span class="sxs-lookup"><span data-stu-id="031be-132">A specific process</span></span> | <span data-ttu-id="031be-133">Die ausführbare Datei `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="031be-133">The executable file `c:\test\process.exe`</span></span> | <span data-ttu-id="031be-134">Datei- und Ordnerausschlüsse</span><span class="sxs-lookup"><span data-stu-id="031be-134">File and folder exclusions</span></span> |

<span data-ttu-id="031be-135">Ausschlusslisten haben die folgenden Merkmale:</span><span class="sxs-lookup"><span data-stu-id="031be-135">Exclusion lists have the following characteristics:</span></span>

- <span data-ttu-id="031be-136">Ordnerausschlüsse gelten für alle Dateien und Ordner unter diesem Ordner, es sei denn, der Unterordner ist ein Reparaturpunkt.</span><span class="sxs-lookup"><span data-stu-id="031be-136">Folder exclusions apply to all files and folders under that folder, unless the subfolder is a reparse point.</span></span> <span data-ttu-id="031be-137">Unterordner für Reparse-Punkte müssen separat ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="031be-137">Reparse point subfolders must be excluded separately.</span></span>
- <span data-ttu-id="031be-138">Dateierweiterungen gelten für jeden Dateinamen mit der definierten Erweiterung, wenn kein Pfad oder Ordner definiert ist.</span><span class="sxs-lookup"><span data-stu-id="031be-138">File extensions apply to any file name with the defined extension if a path or folder is not defined.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="031be-139">Die Verwendung von Platzhaltern wie dem Sternchen ( ) ändert die Interpretation \* der Ausschlussregeln.</span><span class="sxs-lookup"><span data-stu-id="031be-139">Using wildcards such as the asterisk (\*) will alter how the exclusion rules are interpreted.</span></span> <span data-ttu-id="031be-140">Wichtige Informationen zur Funktionsweise [von](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) Platzhaltern finden Sie im Abschnitt Verwenden von Platzhaltern im Abschnitt Dateinamen- und Ordnerpfad- oder Erweiterungsausschlusslisten.</span><span class="sxs-lookup"><span data-stu-id="031be-140">See the [Use wildcards in the file name and folder path or extension exclusion lists](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) section for important information about how wildcards work.</span></span>
> - <span data-ttu-id="031be-141">Zugeordnete Netzwerklaufwerke können nicht ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="031be-141">You cannot exclude mapped network drives.</span></span> <span data-ttu-id="031be-142">Sie müssen den tatsächlichen Netzwerkpfad angeben.</span><span class="sxs-lookup"><span data-stu-id="031be-142">You must specify the actual network path.</span></span>
> - <span data-ttu-id="031be-143">Ordner, die nach dem Starten des Microsoft Defender Antivirus-Diensts erstellt werden und der Ausschlussliste hinzugefügt wurden, werden nicht einbezogen.</span><span class="sxs-lookup"><span data-stu-id="031be-143">Folders that are reparse points that are created after the Microsoft Defender Antivirus service starts and that have been added to the exclusion list will not be included.</span></span> <span data-ttu-id="031be-144">Sie müssen den Dienst neu starten (indem Sie Windows neu starten), damit neue Reparsepunkte als gültiges Ausschlussziel erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="031be-144">You must restart the service (by restarting Windows) for new reparse points to be recognized as a valid exclusion target.</span></span>

<span data-ttu-id="031be-145">Informationen zum Ausschließen von Dateien, die von einem bestimmten Prozess geöffnet wurden, finden Sie unter [Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="031be-145">To exclude files opened by a specific process, see [Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="031be-146">Die Ausschlüsse gelten für [geplante Scans,](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [Bedarfsscans](run-scan-microsoft-defender-antivirus.md)und [Echtzeitschutz.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="031be-146">The exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="031be-147">Änderungen an der Ausschlussliste, die mit Gruppenrichtlinien vorgenommen **wurden,** werden in den Listen in der [Windows Security App angezeigt.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="031be-147">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
> <span data-ttu-id="031be-148">In der Windows -Sicherheits-App vorgenommene **Änderungen werden** nicht in den Gruppenrichtlinienlisten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="031be-148">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="031be-149">Standardmäßig werden lokale Änderungen an den Listen (von Benutzern mit Administratorrechten, einschließlich änderungen, die mit PowerShell und WMI vorgenommen wurden) mit den Listen zusammengeführt, wie von Gruppenrichtlinien, Configuration Manager oder Intune definiert (und bereitgestellt).</span><span class="sxs-lookup"><span data-stu-id="031be-149">By default, local changes made to the lists (by users with administrator privileges, including changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="031be-150">Die Gruppenrichtlinienlisten haben Vorrang, wenn Konflikte auftreten.</span><span class="sxs-lookup"><span data-stu-id="031be-150">The Group Policy lists take precedence when there are conflicts.</span></span>

<span data-ttu-id="031be-151">Sie können [konfigurieren, wie lokal und global definierte Ausschlusslisten](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) zusammengeführt werden, damit lokale Änderungen verwaltete Bereitstellungseinstellungen außer Kraft setzen können.</span><span class="sxs-lookup"><span data-stu-id="031be-151">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a><span data-ttu-id="031be-152">Konfigurieren der Liste der Ausschlüsse basierend auf dem Ordnernamen oder der Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="031be-152">Configure the list of exclusions based on folder name or file extension</span></span>

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="031be-153">Konfigurieren von Dateinamen-, Ordner- oder Dateierweiterungsausschlüssen mithilfe von Intune</span><span class="sxs-lookup"><span data-stu-id="031be-153">Use Intune to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="031be-154">Lesen Sie die folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="031be-154">See the following articles:</span></span>
- [<span data-ttu-id="031be-155">Konfigurieren von Geräteeinschränkungseinstellungen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="031be-155">Configure device restriction settings in Microsoft Intune</span></span>](/intune/device-restrictions-configure)
- [<span data-ttu-id="031be-156">Microsoft Defender Antivirus Geräteeinschränkungseinstellungen für Windows 10 in Intune</span><span class="sxs-lookup"><span data-stu-id="031be-156">Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune</span></span>](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="031be-157">Konfigurieren von Dateinamen-, Ordner- oder Dateierweiterungsausschlüssen mithilfe von Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="031be-157">Use Configuration Manager to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="031be-158">Weitere [Informationen zum Konfigurieren von](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) Microsoft Endpoint Manager (current branch) finden Sie unter Erstellen und Bereitstellen von Antischalwarerichtlinien: Ausschlusseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="031be-158">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a><span data-ttu-id="031be-159">Konfigurieren von Ordner- oder Dateierweiterungsausschlüssen mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="031be-159">Use Group Policy to configure folder or file extension exclusions</span></span>

>[!NOTE]
><span data-ttu-id="031be-160">Wenn Sie einen vollqualifizierten Pfad zu einer Datei angeben, wird nur diese Datei ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="031be-160">If you specify a fully qualified path to a file, then only that file is excluded.</span></span> <span data-ttu-id="031be-161">Wenn ein Ordner im Ausschluss definiert ist, werden alle Dateien und Unterverzeichnisse unter diesem Ordner ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="031be-161">If a folder is defined in the exclusion, then all files and subdirectories under that folder are excluded.</span></span>

1. <span data-ttu-id="031be-162">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="031be-162">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="031be-163">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**</span><span class="sxs-lookup"><span data-stu-id="031be-163">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="031be-164">Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus**  >  **Exclusions**.</span><span class="sxs-lookup"><span data-stu-id="031be-164">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>

4. <span data-ttu-id="031be-165">Öffnen Sie **die Einstellung Pfadausschlüsse** für die Bearbeitung, und fügen Sie Ihre Ausschlüsse hinzu.</span><span class="sxs-lookup"><span data-stu-id="031be-165">Open the **Path Exclusions** setting for editing, and add your exclusions.</span></span>

    1. <span data-ttu-id="031be-166">Legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="031be-166">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="031be-167">Klicken Sie **im Abschnitt Optionen** auf **Anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="031be-167">Under the **Options** section, click **Show**.</span></span>
    1. <span data-ttu-id="031be-168">Geben Sie jeden Ordner in einer eigenen Zeile unter der **Spalte Wertname** an.</span><span class="sxs-lookup"><span data-stu-id="031be-168">Specify each folder on its own line under the **Value name** column.</span></span>
    1. <span data-ttu-id="031be-169">Wenn Sie eine Datei angeben, stellen Sie sicher, dass Sie einen vollqualifizierten Pfad zur Datei eingeben, einschließlich Laufwerkbuchstabe, Ordnerpfad, Dateinamen und Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="031be-169">If you are specifying a file, ensure that you enter a fully qualified path to the file, including the drive letter, folder path, file name, and extension.</span></span> <span data-ttu-id="031be-170">Geben **Sie 0** in die **Spalte Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="031be-170">Enter **0** in the **Value** column.</span></span>

5. <span data-ttu-id="031be-171">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="031be-171">Choose **OK**.</span></span>

6. <span data-ttu-id="031be-172">Öffnen Sie **die Einstellung Erweiterungsausschlüsse** für die Bearbeitung, und fügen Sie Ihre Ausschlüsse hinzu.</span><span class="sxs-lookup"><span data-stu-id="031be-172">Open the **Extension Exclusions** setting for editing and add your exclusions.</span></span>

    1. <span data-ttu-id="031be-173">Legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="031be-173">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="031be-174">Wählen Sie **im Abschnitt Optionen** die Option Anzeigen **aus.**</span><span class="sxs-lookup"><span data-stu-id="031be-174">Under the **Options** section, select **Show**.</span></span>
    1. <span data-ttu-id="031be-175">Geben Sie jede Dateierweiterung in einer eigenen Zeile unter der **Spalte Wertname** ein.</span><span class="sxs-lookup"><span data-stu-id="031be-175">Enter each file extension on its own line under the **Value name** column.</span></span>  <span data-ttu-id="031be-176">Geben **Sie 0** in die **Spalte Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="031be-176">Enter **0** in the **Value** column.</span></span>

7. <span data-ttu-id="031be-177">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="031be-177">Choose **OK**.</span></span>

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="031be-178">Konfigurieren von Dateinamen-, Ordner- oder Dateierweiterungsausschlüssen mithilfe von PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="031be-178">Use PowerShell cmdlets to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="031be-179">Die Verwendung von PowerShell zum Hinzufügen oder Entfernen von Ausschlüssen für Dateien basierend auf der Erweiterung, dem Speicherort oder dem Dateinamen erfordert die Verwendung einer Kombination aus drei Cmdlets und dem entsprechenden Ausschlusslistenparameter.</span><span class="sxs-lookup"><span data-stu-id="031be-179">Using PowerShell to add or remove exclusions for files based on the extension, location, or file name requires using a combination of three cmdlets and the appropriate exclusion list parameter.</span></span> <span data-ttu-id="031be-180">Die Cmdlets befinden sich alle im [Defender-Modul.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="031be-180">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="031be-181">Das Format für die Cmdlets lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="031be-181">The format for the cmdlets is as follows:</span></span>

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

<span data-ttu-id="031be-182">Die folgenden Sind als `<cmdlet>` zulässig:</span><span class="sxs-lookup"><span data-stu-id="031be-182">The following are allowed as the `<cmdlet>`:</span></span>

| <span data-ttu-id="031be-183">Konfigurationsaktion</span><span class="sxs-lookup"><span data-stu-id="031be-183">Configuration action</span></span> | <span data-ttu-id="031be-184">PowerShell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="031be-184">PowerShell cmdlet</span></span> |
|:---|:---|
|<span data-ttu-id="031be-185">Erstellen oder Überschreiben der Liste</span><span class="sxs-lookup"><span data-stu-id="031be-185">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="031be-186">Zur Liste hinzufügen</span><span class="sxs-lookup"><span data-stu-id="031be-186">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="031be-187">Element aus der Liste entfernen</span><span class="sxs-lookup"><span data-stu-id="031be-187">Remove item from the list</span></span> | `Remove-MpPreference` |

<span data-ttu-id="031be-188">Die folgenden Sind als `<exclusion list>` zulässig:</span><span class="sxs-lookup"><span data-stu-id="031be-188">The following are allowed as the `<exclusion list>`:</span></span>

| <span data-ttu-id="031be-189">Ausschlusstyp</span><span class="sxs-lookup"><span data-stu-id="031be-189">Exclusion type</span></span> | <span data-ttu-id="031be-190">PowerShell-Parameter</span><span class="sxs-lookup"><span data-stu-id="031be-190">PowerShell parameter</span></span> |
|:---|:---|
| <span data-ttu-id="031be-191">Alle Dateien mit einer angegebenen Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="031be-191">All files with a specified file extension</span></span> | `-ExclusionExtension` |
| <span data-ttu-id="031be-192">Alle Dateien unter einem Ordner (einschließlich Dateien in Unterverzeichnissen) oder einer bestimmten Datei</span><span class="sxs-lookup"><span data-stu-id="031be-192">All files under a folder (including files in subdirectories), or a specific file</span></span> | `-ExclusionPath` |

> [!IMPORTANT]
> <span data-ttu-id="031be-193">Wenn Sie eine Liste mit oder erstellt haben, überschreibt das `Set-MpPreference` `Add-MpPreference` Cmdlet erneut die vorhandene `Set-MpPreference` Liste.</span><span class="sxs-lookup"><span data-stu-id="031be-193">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="031be-194">Der folgende Codeausschnitt würde beispielsweise dazu führen, dass Microsoft Defender Antivirus-Scans jede Datei mit der `.test` Dateierweiterung ausschließen:</span><span class="sxs-lookup"><span data-stu-id="031be-194">For example, the following code snippet would cause Microsoft Defender Antivirus scans to exclude any file with the `.test` file extension:</span></span>

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

<span data-ttu-id="031be-195">Weitere Informationen finden Sie unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="031be-195">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="031be-196">Konfigurieren von Dateinamen-, Ordner- oder Dateierweiterungsausschlüssen mithilfe der Windows-Verwaltungsanweisung (WMI)</span><span class="sxs-lookup"><span data-stu-id="031be-196">Use Windows Management Instruction (WMI) to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="031be-197">Verwenden Sie [ **die Methoden Set,** **Add** und **Remove** der **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="031be-197">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionExtension
ExclusionPath
```

<span data-ttu-id="031be-198">Die Verwendung von **Set,** **Add** und **Remove** entspricht ihren Entsprechungen in PowerShell: `Set-MpPreference` , und `Add-MpPreference` `Remove-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="031be-198">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="031be-199">Weitere Informationen finden Sie unter [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="031be-199">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="031be-200">Konfigurieren von Dateinamen-, Ordner- oder Dateierweiterungsausschlüssen mithilfe der Windows Security-App</span><span class="sxs-lookup"><span data-stu-id="031be-200">Use the Windows Security app to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="031be-201">Anweisungen [finden Sie unter Hinzufügen von Ausschlüssen in der Windows Security-App.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="031be-201">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="031be-202">Verwenden von Platzhaltern in den Listen für Dateinamen und Ordnerpfad oder Erweiterungsausschluss</span><span class="sxs-lookup"><span data-stu-id="031be-202">Use wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="031be-203">Sie können das Sternchen, fragezeichen oder Umgebungsvariablen (z. B. ) als Platzhalter verwenden, wenn Sie Elemente in der Ausschlussliste für Dateinamen oder `*` `?` `%ALLUSERSPROFILE%` Ordnerpfade definieren.</span><span class="sxs-lookup"><span data-stu-id="031be-203">You can use the asterisk `*`, question mark `?`, or environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the file name or folder path exclusion list.</span></span> <span data-ttu-id="031be-204">Die Interpretation dieser Platzhalter unterscheidet sich von der üblichen Verwendung in anderen Apps und Sprachen.</span><span class="sxs-lookup"><span data-stu-id="031be-204">The way in which these wildcards are interpreted differs from their usual usage in other apps and languages.</span></span> <span data-ttu-id="031be-205">Lesen Sie diesen Abschnitt, um ihre spezifischen Einschränkungen zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="031be-205">Make sure to read this section to understand their specific limitations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="031be-206">Es gibt wichtige Einschränkungen und Verwendungsszenarien für diese Platzhalter:</span><span class="sxs-lookup"><span data-stu-id="031be-206">There are key limitations and usage scenarios for these wildcards:</span></span>
> - <span data-ttu-id="031be-207">Die Verwendung von Umgebungsvariablen ist auf Computervariablen und auf Prozesse beschränkt, die als NT AUTHORITY\SYSTEM-Konto ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="031be-207">Environment variable usage is limited to machine variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span>
> - <span data-ttu-id="031be-208">Sie können keinen Platzhalter an stelle eines Laufwerkbuchstabens verwenden.</span><span class="sxs-lookup"><span data-stu-id="031be-208">You cannot use a wildcard in place of a drive letter.</span></span>
> - <span data-ttu-id="031be-209">Für einen einzelnen Ordner wird ein Sternchen in einem `*` Ordnerausschluss angezeigt.</span><span class="sxs-lookup"><span data-stu-id="031be-209">An asterisk `*` in a folder exclusion stands in place for a single folder.</span></span> <span data-ttu-id="031be-210">Verwenden Sie mehrere Instanzen `\*\` von, um mehrere geschachtelte Ordner mit nicht angegebenen Namen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="031be-210">Use multiple instances of `\*\` to indicate multiple nested folders with unspecified names.</span></span>

<span data-ttu-id="031be-211">In der folgenden Tabelle wird beschrieben, wie die Platzhalter verwendet werden können, und es werden einige Beispiele aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="031be-211">The following table describes how the wildcards can be used and provides some examples.</span></span>


|<span data-ttu-id="031be-212">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="031be-212">Wildcard</span></span>  |<span data-ttu-id="031be-213">Beispiele</span><span class="sxs-lookup"><span data-stu-id="031be-213">Examples</span></span>  |
|:---------|:---------|
|<span data-ttu-id="031be-214">`*` (Sternchen)</span><span class="sxs-lookup"><span data-stu-id="031be-214">`*` (asterisk)</span></span> <p> <span data-ttu-id="031be-215">In **Dateinamen- und Dateierweiterungseinschlüssen** ersetzt das Sternchen eine beliebige Anzahl von Zeichen und gilt nur für Dateien im letzten Ordner, der im Argument definiert ist.</span><span class="sxs-lookup"><span data-stu-id="031be-215">In **file name and file extension inclusions**, the asterisk replaces any number of characters, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="031be-216">In **Ordnerausschlüssen** ersetzt das Sternchen einen einzelnen Ordner.</span><span class="sxs-lookup"><span data-stu-id="031be-216">In **folder exclusions**, the asterisk replaces a single folder.</span></span> <span data-ttu-id="031be-217">Verwenden Sie `*` mehrere mit Ordnerschrägstrichen, `\` um mehrere geschachtelte Ordner anzugeben.</span><span class="sxs-lookup"><span data-stu-id="031be-217">Use multiple `*` with folder slashes `\` to indicate multiple nested folders.</span></span> <span data-ttu-id="031be-218">Nachdem die Anzahl der Ordner mit Platzhaltern und benannten Ordnern übereinstimmen, werden auch alle Unterordner einbezogen.</span><span class="sxs-lookup"><span data-stu-id="031be-218">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   | <span data-ttu-id="031be-219">`C:\MyData\*.txt` includes `C:\MyData\notes.txt`</span><span class="sxs-lookup"><span data-stu-id="031be-219">`C:\MyData\*.txt` includes `C:\MyData\notes.txt`</span></span> <p> <span data-ttu-id="031be-220">`C:\somepath\*\Data` enthält alle Dateien in und deren Unterordner sowie `C:\somepath\Archives\Data` `C:\somepath\Authorized\Data` deren Unterordner</span><span class="sxs-lookup"><span data-stu-id="031be-220">`C:\somepath\*\Data` includes any file in `C:\somepath\Archives\Data` and its subfolders, and `C:\somepath\Authorized\Data` and its subfolders</span></span> <p> <span data-ttu-id="031be-221">`C:\Serv\*\*\Backup` enthält alle Dateien in `C:\Serv\Primary\Denied\Backup` und deren Unterordnern und `C:\Serv\Secondary\Allowed\Backup` unterordnern</span><span class="sxs-lookup"><span data-stu-id="031be-221">`C:\Serv\*\*\Backup` includes any file in `C:\Serv\Primary\Denied\Backup` and its subfolders and `C:\Serv\Secondary\Allowed\Backup` and its subfolders</span></span>     |
|<span data-ttu-id="031be-222">`?` (Fragezeichen)</span><span class="sxs-lookup"><span data-stu-id="031be-222">`?` (question mark)</span></span>  <p> <span data-ttu-id="031be-223">In **Dateinamen- und Dateierweiterungseinschlüssen** ersetzt das Fragezeichen ein einzelnes Zeichen und gilt nur für Dateien im letzten Ordner, der im Argument definiert ist.</span><span class="sxs-lookup"><span data-stu-id="031be-223">In **file name and file extension inclusions**, the question mark replaces a single character, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="031be-224">In **Ordnerausschlüssen** ersetzt das Fragezeichen ein einzelnes Zeichen in einem Ordnernamen.</span><span class="sxs-lookup"><span data-stu-id="031be-224">In **folder exclusions**, the question mark replaces a single character in a folder name.</span></span> <span data-ttu-id="031be-225">Nachdem die Anzahl der Ordner mit Platzhaltern und benannten Ordnern übereinstimmen, werden auch alle Unterordner einbezogen.</span><span class="sxs-lookup"><span data-stu-id="031be-225">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   |<span data-ttu-id="031be-226">`C:\MyData\my?.zip` includes `C:\MyData\my1.zip`</span><span class="sxs-lookup"><span data-stu-id="031be-226">`C:\MyData\my?.zip` includes `C:\MyData\my1.zip`</span></span> <p> <span data-ttu-id="031be-227">`C:\somepath\?\Data` enthält eine beliebige Datei in `C:\somepath\P\Data` und ihren Unterordnern</span><span class="sxs-lookup"><span data-stu-id="031be-227">`C:\somepath\?\Data` includes any file in `C:\somepath\P\Data` and its subfolders</span></span>  <p> <span data-ttu-id="031be-228">`C:\somepath\test0?\Data` würde eine beliebige Datei in `C:\somepath\test01\Data` und ihre Unterordner enthalten</span><span class="sxs-lookup"><span data-stu-id="031be-228">`C:\somepath\test0?\Data` would include any file in `C:\somepath\test01\Data` and its subfolders</span></span>          |
|<span data-ttu-id="031be-229">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="031be-229">Environment variables</span></span> <p> <span data-ttu-id="031be-230">Die definierte Variable wird als Pfad aufgefüllt, wenn der Ausschluss ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="031be-230">The defined variable is populated as a path when the exclusion is evaluated.</span></span>          |<span data-ttu-id="031be-231">`%ALLUSERSPROFILE%\CustomLogFiles` würde umfassen `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span><span class="sxs-lookup"><span data-stu-id="031be-231">`%ALLUSERSPROFILE%\CustomLogFiles` would include `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span></span>         |
        

> [!IMPORTANT]
> <span data-ttu-id="031be-232">Wenn Sie ein Argument für den Dateiausschluss mit einem Argument für den Ordnerausschluss kombinieren, werden die Regeln bei der Übereinstimmung des Dateiarguments im übereinstimmenden Ordner beendet und in keinem Unterordner nach Datei übereinstimmungen suchen.</span><span class="sxs-lookup"><span data-stu-id="031be-232">If you mix a file exclusion argument with a folder exclusion argument, the rules will stop at the file argument match in the matched folder, and will not look for file matches in any subfolders.</span></span>
> <span data-ttu-id="031be-233">Sie können z. B. alle Dateien ausschließen, die mit "date" in den Ordnern und mit dem `c:\data\final\marked` `c:\data\review\marked` Rule-Argument `c:\data\*\marked\date*` beginnen.</span><span class="sxs-lookup"><span data-stu-id="031be-233">For example, you can exclude all files that start with "date" in the folders `c:\data\final\marked` and `c:\data\review\marked` by using the rule argument `c:\data\*\marked\date*`.</span></span>
> <span data-ttu-id="031be-234">Dieses Argument passt jedoch nicht zu Dateien in Unterordnern unter oder `c:\data\final\marked` `c:\data\review\marked` .</span><span class="sxs-lookup"><span data-stu-id="031be-234">This argument, however, will not match any files in subfolders under `c:\data\final\marked` or `c:\data\review\marked`.</span></span>

<a id="review"></a>

### <a name="system-environment-variables"></a><span data-ttu-id="031be-235">Systemumgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="031be-235">System environment variables</span></span>

<span data-ttu-id="031be-236">In der folgenden Tabelle werden die Systemkontoumgebungsvariablen aufgeführt und beschrieben.</span><span class="sxs-lookup"><span data-stu-id="031be-236">The following table lists and describes the system account environment variables.</span></span> 

| <span data-ttu-id="031be-237">Diese Systemumgebungsvariable...</span><span class="sxs-lookup"><span data-stu-id="031be-237">This system environment variable...</span></span> | <span data-ttu-id="031be-238">Umleitungen zu diesem</span><span class="sxs-lookup"><span data-stu-id="031be-238">Redirects to this</span></span> |
|:--|:--|
| `%APPDATA%`| `C:\Users\UserName.DomainName\AppData\Roaming` |
| `%APPDATA%\Microsoft\Internet Explorer\Quick Launch` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch` |
| `%APPDATA%\Microsoft\Windows\Start Menu` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu` |
| `%APPDATA%\Microsoft\Windows\Start Menu\Programs` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs` |
| `%LOCALAPPDATA%` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%ProgramData%` | `C:\ProgramData` |
| `%ProgramFiles%` | `C:\Program Files` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles%\Windows Sidebar\Gadgets` | `C:\Program Files\Windows Sidebar\Gadgets` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles(x86)%` | `C:\Program Files (x86)` |
| `%ProgramFiles(x86)%\Common Files` | `C:\Program Files (x86)\Common Files` |
| `%SystemDrive%` | `C:` |
| `%SystemDrive%\Program Files` | `C:\Program Files` |
| `%SystemDrive%\Program Files (x86)` | `C:\Program Files (x86)` |
| `%SystemDrive%\Users` | `C:\Users` |
| `%SystemDrive%\Users\Public` | `C:\Users\Public` |
| `%SystemRoot%` | `C:\Windows` |
| `%windir%` | `C:\Windows` |
| `%windir%\Fonts` | `C:\Windows\Fonts` |
| `%windir%\Resources` | `C:\Windows\Resources` |
| `%windir%\resources\0409` | `C:\Windows\resources\0409` |
| `%windir%\system32` | `C:\Windows\System32` |
| `%ALLUSERSPROFILE%` | `C:\ProgramData` |
| `%ALLUSERSPROFILE%\Application Data` | `C:\ProgramData\Application Data` |
| `%ALLUSERSPROFILE%\Documents` | `C:\ProgramData\Documents` |
| `%ALLUSERSPROFILE%\Documents\My Music\Sample Music` | `C:\ProgramData\Documents\My Music\Sample Music` |
| `%ALLUSERSPROFILE%\Documents\My Music` | `C:\ProgramData\Documents\My Music` |
| `%ALLUSERSPROFILE%\Documents\My Pictures` | `C:\ProgramData\Documents\My Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures` | `C:\ProgramData\Documents\My Pictures\Sample Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Videos` | `C:\ProgramData\Documents\My Videos` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore` | `C:\ProgramData\Microsoft\Windows\DeviceMetadataStore` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer` | `C:\ProgramData\Microsoft\Windows\GameExplorer` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones` | `C:\ProgramData\Microsoft\Windows\Ringtones` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu` | `C:\ProgramData\Microsoft\Windows\Start Menu` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Templates` | `C:\ProgramData\Microsoft\Windows\Templates` |
| `%ALLUSERSPROFILE%\Start Menu` | `C:\ProgramData\Start Menu` |
| `%ALLUSERSPROFILE%\Start Menu\Programs` | <span data-ttu-id="031be-239">C:\ProgramData\Startmenü\Programme</span><span class="sxs-lookup"><span data-stu-id="031be-239">C:\ProgramData\Start Menu\Programs</span></span> |
| `%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Start Menu\Programs\Administrative Tools` | 
| `%ALLUSERSPROFILE%\Templates` | `C:\ProgramData\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\History` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History` |
| `%PUBLIC%` | `C:\Users\Public` |
| `%PUBLIC%\AccountPictures` | `C:\Users\Public\AccountPictures` |
| `%PUBLIC%\Desktop` | `C:\Users\Public\Desktop` |
| `%PUBLIC%\Documents` | `C:\Users\Public\Documents` |
| `%PUBLIC%\Downloads` | `C:\Users\Public\Downloads` |
| `%PUBLIC%\Music\Sample Music` | `C:\Users\Public\Music\Sample Music` |
| `%PUBLIC%\Music\Sample Playlists` | `C:\Users\Public\Music\Sample Playlists` |
| `%PUBLIC%\Pictures\Sample Pictures` | `C:\Users\Public\Pictures\Sample Pictures` |
| `%PUBLIC%\RecordedTV.library-ms` | `C:\Users\Public\RecordedTV.library-ms` |
| `%PUBLIC%\Videos` | `C:\Users\Public\Videos` |
| `%PUBLIC%\Videos\Sample Videos` | `C:\Users\Public\Videos\Sample Videos` | 
| `%USERPROFILE%` | `C:\Windows\System32\config\systemprofile` |
| `%USERPROFILE%\AppData\Local` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%USERPROFILE%\AppData\LocalLow` | `C:\Windows\System32\config\systemprofile\AppData\LocalLow` |
| `%USERPROFILE%\AppData\Roaming` | `C:\Windows\System32\config\systemprofile\AppData\Roaming` |


## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="031be-240">Überprüfen der Liste der Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="031be-240">Review the list of exclusions</span></span>

<span data-ttu-id="031be-241">Sie können die Elemente in der Ausschlussliste mithilfe einer der folgenden Methoden abrufen:</span><span class="sxs-lookup"><span data-stu-id="031be-241">You can retrieve the items in the exclusion list using one of the following methods:</span></span>
- [<span data-ttu-id="031be-242">Intune</span><span class="sxs-lookup"><span data-stu-id="031be-242">Intune</span></span>](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [<span data-ttu-id="031be-243">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="031be-243">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- <span data-ttu-id="031be-244">MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="031be-244">MpCmdRun</span></span>
- <span data-ttu-id="031be-245">PowerShell</span><span class="sxs-lookup"><span data-stu-id="031be-245">PowerShell</span></span>
- [<span data-ttu-id="031be-246">Windows Security App</span><span class="sxs-lookup"><span data-stu-id="031be-246">Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)

>[!IMPORTANT]
><span data-ttu-id="031be-247">Änderungen an der Ausschlussliste, die mit Gruppenrichtlinien vorgenommen **wurden,** werden in den Listen in der [Windows Security App angezeigt.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="031be-247">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
>
><span data-ttu-id="031be-248">In der Windows -Sicherheits-App vorgenommene **Änderungen werden** nicht in den Gruppenrichtlinienlisten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="031be-248">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="031be-249">Wenn Sie PowerShell verwenden, können Sie die Liste auf zwei Arten abrufen:</span><span class="sxs-lookup"><span data-stu-id="031be-249">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="031be-250">Rufen Sie den Status aller Microsoft Defender Antivirus-Einstellungen ab.</span><span class="sxs-lookup"><span data-stu-id="031be-250">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="031be-251">Jede Liste wird in separaten Zeilen angezeigt, aber die Elemente in jeder Liste werden in derselben Zeile kombiniert.</span><span class="sxs-lookup"><span data-stu-id="031be-251">Each list is displayed on separate lines, but the items within each list are combined into the same line.</span></span>
- <span data-ttu-id="031be-252">Schreiben Sie den Status aller Einstellungen in eine Variable, und verwenden Sie diese Variable, um nur die bestimmte Liste auf aufruft, an der Sie interessiert sind.</span><span class="sxs-lookup"><span data-stu-id="031be-252">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="031be-253">Jede Verwendung `Add-MpPreference` von wird in eine neue Zeile geschrieben.</span><span class="sxs-lookup"><span data-stu-id="031be-253">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="031be-254">Überprüfen der Ausschlussliste mithilfe von MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="031be-254">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="031be-255">Verwenden Sie den folgenden Befehl, um Ausschlüsse mit dem [dedizierten Befehlszeilentool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="031be-255">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.1812.3 (Where 4.18.1812.3 is this month's MDAV "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

>[!NOTE]
><span data-ttu-id="031be-256">Das Überprüfen von Ausschlüssen mit MpCmdRun erfordert Microsoft Defender Antivirus CAMP, Version 4.18.1812.3 (veröffentlicht im Dezember 2018) oder höher.</span><span class="sxs-lookup"><span data-stu-id="031be-256">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="031be-257">Überprüfen der Liste der Ausschlüsse zusammen mit allen anderen Microsoft Defender Antivirus-Einstellungen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="031be-257">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="031be-258">Verwenden Sie das folgende Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="031be-258">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="031be-259">Im folgenden Beispiel werden die in der Liste `ExclusionExtension` enthaltenen Elemente hervorgehoben:</span><span class="sxs-lookup"><span data-stu-id="031be-259">In the following example, the items contained in the `ExclusionExtension` list are highlighted:</span></span>

![PowerShell-Ausgabe für Get-MpPreference, in der die Ausschlussliste neben anderen Einstellungen angezeigt wird](images/defender/wdav-powershell-get-exclusions-all.png)

<span data-ttu-id="031be-261">Weitere Informationen finden Sie unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="031be-261">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="031be-262">Abrufen einer bestimmten Ausschlussliste mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="031be-262">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="031be-263">Verwenden Sie den folgenden Codeausschnitt (geben Sie jede Zeile als separaten Befehl ein); Ersetzen **Sie WDAVprefs** durch die Bezeichnung, die Sie der Variablen nennen möchten:</span><span class="sxs-lookup"><span data-stu-id="031be-263">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

<span data-ttu-id="031be-264">Im folgenden Beispiel wird die Liste für jede Verwendung des Cmdlets in neue Zeilen `Add-MpPreference` aufgeteilt:</span><span class="sxs-lookup"><span data-stu-id="031be-264">In the following example, the list is split into new lines for each use of the `Add-MpPreference` cmdlet:</span></span>

![PowerShell-Ausgabe mit nur den Einträgen in der Ausschlussliste](images/defender/wdav-powershell-get-exclusions-variable.png)

<span data-ttu-id="031be-266">Weitere Informationen finden Sie unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="031be-266">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="031be-267">Überprüfen von Ausschlusslisten mit der EICAR-Testdatei</span><span class="sxs-lookup"><span data-stu-id="031be-267">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="031be-268">Sie können überprüfen, ob Ihre Ausschlusslisten funktionieren, indem Sie PowerShell mit dem Cmdlet oder der .NET WebClient-Klasse verwenden, um `Invoke-WebRequest` eine Testdatei herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="031be-268">You can validate that your exclusion lists are working by using PowerShell with either the `Invoke-WebRequest` cmdlet or the .NET WebClient class to download a test file.</span></span>

<span data-ttu-id="031be-269">Ersetzen Sie im folgenden PowerShell-Codeausschnitt *test.txt* durch eine Datei, die Ihren Ausschlussregeln entspricht.</span><span class="sxs-lookup"><span data-stu-id="031be-269">In the following PowerShell snippet, replace *test.txt* with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="031be-270">Wenn Sie beispielsweise die Erweiterung ausgeschlossen `.testing` haben, ersetzen Sie `test.txt` durch `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="031be-270">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="031be-271">Wenn Sie einen Pfad testen, stellen Sie sicher, dass Sie das Cmdlet innerhalb dieses Pfads ausführen.</span><span class="sxs-lookup"><span data-stu-id="031be-271">If you are testing a path, ensure you run the cmdlet within that path.</span></span>

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

<span data-ttu-id="031be-272">Wenn Microsoft Defender Antivirus Schadsoftware meldet, funktioniert die Regel nicht.</span><span class="sxs-lookup"><span data-stu-id="031be-272">If Microsoft Defender Antivirus reports malware, then the rule is not working.</span></span> <span data-ttu-id="031be-273">Wenn kein Bericht über Schadsoftware vorhanden ist und die heruntergeladene Datei vorhanden ist, funktioniert der Ausschluss.</span><span class="sxs-lookup"><span data-stu-id="031be-273">If there is no report of malware and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="031be-274">Sie können die Datei öffnen, um zu bestätigen, dass die Inhalte mit den auf der [EICAR-Testdateiwebsite beschriebenen Inhalten identisch sind.](http://www.eicar.org/86-0-Intended-use.html)</span><span class="sxs-lookup"><span data-stu-id="031be-274">You can open the file to confirm the contents are the same as what is described on the [EICAR test file website](http://www.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="031be-275">Sie können auch den folgenden #A0 verwenden, der die .NET WebClient-Klasse aufruft, um die Testdatei herunterzuladen – wie beim Cmdlet. Ersetzen Siec:\test.txtdurch eine Datei, die der zu überprüfenden Regel `Invoke-WebRequest` entspricht: </span><span class="sxs-lookup"><span data-stu-id="031be-275">You can also use the following PowerShell code, which calls the .NET WebClient class to download the test file - as with the `Invoke-WebRequest` cmdlet; replace *c:\test.txt* with a file that conforms to the rule you are validating:</span></span>

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

<span data-ttu-id="031be-276">Wenn Sie keinen Internetzugriff haben, können Sie eine eigene EICAR-Testdatei erstellen, indem Sie die EICAR-Zeichenfolge mit dem folgenden PowerShell-Befehl in eine neue Textdatei schreiben:</span><span class="sxs-lookup"><span data-stu-id="031be-276">If you do not have Internet access, you can create your own EICAR test file by writing the EICAR string to a new text file with the following PowerShell command:</span></span>

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

<span data-ttu-id="031be-277">Sie können die Zeichenfolge auch in eine leere Textdatei kopieren und versuchen, sie mit dem Dateinamen oder in dem Ordner zu speichern, den Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="031be-277">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="related-topics"></a><span data-ttu-id="031be-278">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="031be-278">Related topics</span></span>

- [<span data-ttu-id="031be-279">Konfigurieren und Überprüfen von Ausschlüssen in Microsoft Defender Antivirus-Scans</span><span class="sxs-lookup"><span data-stu-id="031be-279">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="031be-280">Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden</span><span class="sxs-lookup"><span data-stu-id="031be-280">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="031be-281">Konfigurieren von Microsoft Defender Antivirus-Ausschlüssen unter Windows Server</span><span class="sxs-lookup"><span data-stu-id="031be-281">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="031be-282">Häufige Fehler, die beim Festlegen von Ausschlüssen vermieden werden sollten</span><span class="sxs-lookup"><span data-stu-id="031be-282">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
