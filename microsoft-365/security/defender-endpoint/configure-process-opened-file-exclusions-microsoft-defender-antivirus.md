---
title: Konfigurieren von Ausschlüssen für Dateien, die von bestimmten Prozessen geöffnet werden
description: Sie können Dateien von Scans ausschließen, wenn sie von einem bestimmten Prozess geöffnet wurden.
keywords: Microsoft Defender Antivirus, Prozess, Ausschluss, Dateien, Scans
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2fdc646cf616ff6a6fa36a83be3d2b1dd0432fbe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274613"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a><span data-ttu-id="079b2-104">Konfigurieren von Ausschlüssen für Dateien, die von Prozessen geöffnet werden</span><span class="sxs-lookup"><span data-stu-id="079b2-104">Configure exclusions for files opened by processes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="079b2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="079b2-105">**Applies to:**</span></span>

- [<span data-ttu-id="079b2-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="079b2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="079b2-107">Sie können Dateien, die von bestimmten Prozessen geöffnet wurden, aus Microsoft Defender Antivirus-Scans ausschließen.</span><span class="sxs-lookup"><span data-stu-id="079b2-107">You can exclude files that have been opened by specific processes from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="079b2-108">Weitere [Informationen finden Sie unter Empfehlungen zum Definieren von Ausschlüssen,](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) bevor Sie Ihre Ausschlusslisten definieren.</span><span class="sxs-lookup"><span data-stu-id="079b2-108">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

<span data-ttu-id="079b2-109">In diesem Artikel wird beschrieben, wie Ausschlusslisten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="079b2-109">This article describes how to configure exclusion lists.</span></span> 

## <a name="examples-of-exclusions"></a><span data-ttu-id="079b2-110">Beispiele für Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="079b2-110">Examples of exclusions</span></span>

|<span data-ttu-id="079b2-111">Ausschluss</span><span class="sxs-lookup"><span data-stu-id="079b2-111">Exclusion</span></span> | <span data-ttu-id="079b2-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="079b2-112">Example</span></span> |
|---|---|
|<span data-ttu-id="079b2-113">Jede Datei auf dem Computer, die von einem beliebigen Prozess mit einem bestimmten Dateinamen geöffnet wird</span><span class="sxs-lookup"><span data-stu-id="079b2-113">Any file on the machine that is opened by any process with a specific file name</span></span> | <span data-ttu-id="079b2-114">Die Angabe `test.exe` würde Dateien ausschließen, die von:</span><span class="sxs-lookup"><span data-stu-id="079b2-114">Specifying `test.exe` would exclude files opened by:</span></span> <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|<span data-ttu-id="079b2-115">Jede Datei auf dem Computer, die von einem beliebigen Prozess unter einem bestimmten Ordner geöffnet wird</span><span class="sxs-lookup"><span data-stu-id="079b2-115">Any file on the machine that is opened by any process under a specific folder</span></span> | <span data-ttu-id="079b2-116">Die Angabe `c:\test\sample\*` würde Dateien ausschließen, die von:</span><span class="sxs-lookup"><span data-stu-id="079b2-116">Specifying `c:\test\sample\*` would exclude files opened by:</span></span><br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|<span data-ttu-id="079b2-117">Jede Datei auf dem Computer, die von einem bestimmten Prozess in einem bestimmten Ordner geöffnet wird</span><span class="sxs-lookup"><span data-stu-id="079b2-117">Any file on the machine that is opened by a specific process in a specific folder</span></span> | <span data-ttu-id="079b2-118">Durch angeben `c:\test\process.exe` würden nur geöffnete Dateien ausgeschlossen. `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="079b2-118">Specifying `c:\test\process.exe` would exclude files only opened by `c:\test\process.exe`</span></span> |


<span data-ttu-id="079b2-119">Wenn Sie der Prozessausschlussliste einen Prozess hinzufügen, werden von Microsoft Defender Antivirus geöffnete Dateien nicht gescannt, unabhängig davon, wo sich die Dateien befinden.</span><span class="sxs-lookup"><span data-stu-id="079b2-119">When you add a process to the process exclusion list, Microsoft Defender Antivirus won't scan files opened by that process, no matter where the files are located.</span></span> <span data-ttu-id="079b2-120">Der Prozess selbst wird jedoch überprüft, es sei denn, er wurde auch der Dateiausschlussliste [hinzugefügt.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="079b2-120">The process itself, however, will be scanned unless it has also been added to the [file exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="079b2-121">Die Ausschlüsse gelten nur für [den Immer-on-Echtzeitschutz und die Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="079b2-121">The exclusions only apply to [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="079b2-122">Sie gelten nicht für geplante oder on-Demand-Scans.</span><span class="sxs-lookup"><span data-stu-id="079b2-122">They don't apply to scheduled or on-demand scans.</span></span>

<span data-ttu-id="079b2-123">Änderungen, die mit Gruppenrichtlinien an den Ausschlusslisten vorgenommen **wurden,** werden in den Listen in der [Windows Security App angezeigt.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="079b2-123">Changes made with Group Policy to the exclusion lists **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="079b2-124">In der Windows-Sicherheits-App vorgenommene Änderungen **werden jedoch nicht** in den Gruppenrichtlinienlisten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="079b2-124">However, changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="079b2-125">Sie können die Listen in Gruppenrichtlinien, Microsoft Endpoint Configuration Manager, Microsoft Intune und mit der Windows-Sicherheits-App hinzufügen, entfernen und auf Ausschlüsse überprüfen, und Sie können Platzhalter verwenden, um die Listen weiter anzupassen.</span><span class="sxs-lookup"><span data-stu-id="079b2-125">You can add, remove, and review the lists for exclusions in Group Policy, Microsoft Endpoint Configuration Manager, Microsoft Intune, and with the Windows Security app, and you can use wildcards to further customize the lists.</span></span>

<span data-ttu-id="079b2-126">Sie können auch PowerShell-Cmdlets und WMI verwenden, um die Ausschlusslisten zu konfigurieren, einschließlich der Überprüfung Ihrer Listen.</span><span class="sxs-lookup"><span data-stu-id="079b2-126">You can also use PowerShell cmdlets and WMI to configure the exclusion lists, including reviewing your lists.</span></span>

<span data-ttu-id="079b2-127">Standardmäßig werden lokale Änderungen an den Listen (von Benutzern mit Administratorrechten, mit PowerShell und WMI vorgenommene Änderungen) mit den Listen zusammengeführt, wie von Gruppenrichtlinien, Configuration Manager oder Intune definiert (und bereitgestellt).</span><span class="sxs-lookup"><span data-stu-id="079b2-127">By default, local changes made to the lists (by users with administrator privileges; changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="079b2-128">Die Gruppenrichtlinienlisten haben bei Konflikten Vorrang.</span><span class="sxs-lookup"><span data-stu-id="079b2-128">The Group Policy lists will take precedence in the case of conflicts.</span></span>

<span data-ttu-id="079b2-129">Sie können [konfigurieren, wie lokal und global definierte Ausschlusslisten](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) zusammengeführt werden, damit lokale Änderungen verwaltete Bereitstellungseinstellungen außer Kraft setzen können.</span><span class="sxs-lookup"><span data-stu-id="079b2-129">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a><span data-ttu-id="079b2-130">Konfigurieren der Liste der Ausschlüsse für Dateien, die von angegebenen Prozessen geöffnet wurden</span><span class="sxs-lookup"><span data-stu-id="079b2-130">Configure the list of exclusions for files opened by specified processes</span></span>

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="079b2-131">Verwenden von Microsoft Intune zum Ausschließen von Dateien, die von angegebenen Prozessen geöffnet wurden, von Scans</span><span class="sxs-lookup"><span data-stu-id="079b2-131">Use Microsoft Intune to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="079b2-132">Weitere Informationen finden Sie [unter Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and Microsoft Defender Antivirus device restriction settings for Windows [10 in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="079b2-132">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="079b2-133">Verwenden von Microsoft Endpoint Manager zum Ausschließen von Dateien, die von angegebenen Prozessen geöffnet wurden, von Scans</span><span class="sxs-lookup"><span data-stu-id="079b2-133">Use Microsoft Endpoint Manager to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="079b2-134">Weitere [Informationen zum Konfigurieren von](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) Microsoft Endpoint Manager (current branch) finden Sie unter Erstellen und Bereitstellen von Antischalwarerichtlinien: Ausschlusseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="079b2-134">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="079b2-135">Verwenden von Gruppenrichtlinien zum Ausschließen von Dateien, die von angegebenen Prozessen geöffnet wurden, von Scans</span><span class="sxs-lookup"><span data-stu-id="079b2-135">Use Group Policy to exclude files that have been opened by specified processes from scans</span></span>

1. <span data-ttu-id="079b2-136">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="079b2-136">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="079b2-137">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="079b2-137">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="079b2-138">Erweitern Sie die Struktur auf **Windows-Komponenten > Microsoft Defender Antivirus > Ausschlüsse .**</span><span class="sxs-lookup"><span data-stu-id="079b2-138">Expand the tree to **Windows components > Microsoft Defender Antivirus > Exclusions**.</span></span>

4. <span data-ttu-id="079b2-139">Doppelklicken Sie **auf Prozessausschlüsse,** und fügen Sie die Ausschlüsse hinzu:</span><span class="sxs-lookup"><span data-stu-id="079b2-139">Double-click **Process Exclusions** and add the exclusions:</span></span>

    1. <span data-ttu-id="079b2-140">Legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="079b2-140">Set the option to **Enabled**.</span></span>
    2. <span data-ttu-id="079b2-141">Klicken Sie **im Abschnitt** Optionen auf **Anzeigen...**.</span><span class="sxs-lookup"><span data-stu-id="079b2-141">Under the **Options** section, click **Show...**.</span></span>
    3. <span data-ttu-id="079b2-142">Geben Sie jeden Prozess in einer eigenen Zeile unter der **Spalte Wertname** ein.</span><span class="sxs-lookup"><span data-stu-id="079b2-142">Enter each process on its own line under the **Value name** column.</span></span> <span data-ttu-id="079b2-143">In der Beispieltabelle finden Sie die verschiedenen Arten von Prozessausschlüssen.</span><span class="sxs-lookup"><span data-stu-id="079b2-143">See the example table for the different types of process exclusions.</span></span>  <span data-ttu-id="079b2-144">Geben **Sie 0** in die **Spalte Wert** für alle Prozesse ein.</span><span class="sxs-lookup"><span data-stu-id="079b2-144">Enter **0** in the **Value** column for all processes.</span></span>

5. <span data-ttu-id="079b2-145">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="079b2-145">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="079b2-146">Verwenden von PowerShell-Cmdlets zum Ausschließen von Dateien, die von angegebenen Prozessen geöffnet wurden, von Scans</span><span class="sxs-lookup"><span data-stu-id="079b2-146">Use PowerShell cmdlets to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="079b2-147">Die Verwendung von PowerShell zum Hinzufügen oder Entfernen von Ausschlüssen für Dateien, die von Prozessen geöffnet wurden, erfordert die Verwendung einer Kombination von drei Cmdlets mit dem `-ExclusionProcess` Parameter.</span><span class="sxs-lookup"><span data-stu-id="079b2-147">Using PowerShell to add or remove exclusions for files that have been opened by processes requires using a combination of three cmdlets with the `-ExclusionProcess` parameter.</span></span> <span data-ttu-id="079b2-148">Die Cmdlets befinden sich alle im [Defender-Modul.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="079b2-148">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="079b2-149">Das Format für die Cmdlets ist:</span><span class="sxs-lookup"><span data-stu-id="079b2-149">The format for the cmdlets is:</span></span>

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

<span data-ttu-id="079b2-150">Die folgenden Sind als \<cmdlet> zulässig:</span><span class="sxs-lookup"><span data-stu-id="079b2-150">The following are allowed as the \<cmdlet>:</span></span>

|<span data-ttu-id="079b2-151">Konfigurationsaktion</span><span class="sxs-lookup"><span data-stu-id="079b2-151">Configuration action</span></span> | <span data-ttu-id="079b2-152">PowerShell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="079b2-152">PowerShell cmdlet</span></span> |
|---|---|
|<span data-ttu-id="079b2-153">Erstellen oder Überschreiben der Liste</span><span class="sxs-lookup"><span data-stu-id="079b2-153">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="079b2-154">Zur Liste hinzufügen</span><span class="sxs-lookup"><span data-stu-id="079b2-154">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="079b2-155">Entfernen von Elementen aus der Liste</span><span class="sxs-lookup"><span data-stu-id="079b2-155">Remove items from the list</span></span> | `Remove-MpPreference` |

>[!IMPORTANT]
><span data-ttu-id="079b2-156">Wenn Sie eine Liste mit oder erstellt haben, überschreibt das `Set-MpPreference` `Add-MpPreference` Cmdlet erneut die vorhandene `Set-MpPreference` Liste.</span><span class="sxs-lookup"><span data-stu-id="079b2-156">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="079b2-157">Der folgende Codeausschnitt würde z. B. dazu führen, dass Microsoft Defender AV-Scans alle Dateien ausschließen, die durch den angegebenen Prozess geöffnet werden:</span><span class="sxs-lookup"><span data-stu-id="079b2-157">For example, the following code snippet would cause Microsoft Defender AV scans to exclude any file that is opened by the specified process:</span></span>

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

<span data-ttu-id="079b2-158">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Manage antivirus with PowerShell [cmdlets and Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span><span class="sxs-lookup"><span data-stu-id="079b2-158">For more information on how to use PowerShell with Microsoft Defender Antivirus, see Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span></span>

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="079b2-159">Verwenden von Windows Management Instruction (WMI) zum Ausschließen von Dateien, die von angegebenen Prozessen geöffnet wurden, von Scans</span><span class="sxs-lookup"><span data-stu-id="079b2-159">Use Windows Management Instruction (WMI) to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="079b2-160">Verwenden Sie [ **die Methoden Set,** **Add** und **Remove** der **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="079b2-160">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionProcess
```

<span data-ttu-id="079b2-161">Die Verwendung von **Set,** **Add** und **Remove** entspricht ihren Entsprechungen in PowerShell: `Set-MpPreference` , und `Add-MpPreference` `Remove-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="079b2-161">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="079b2-162">Weitere Informationen und zulässige Parameter finden Sie  [unter Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="079b2-162">For more information and allowed parameters, see  [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="079b2-163">Verwenden der Windows Security-App zum Ausschließen von Dateien, die von angegebenen Prozessen geöffnet wurden, von Scans</span><span class="sxs-lookup"><span data-stu-id="079b2-163">Use the Windows Security app to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="079b2-164">Anweisungen [finden Sie unter Hinzufügen von Ausschlüssen in der Windows Security-App.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="079b2-164">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

## <a name="use-wildcards-in-the-process-exclusion-list"></a><span data-ttu-id="079b2-165">Verwenden von Platzhaltern in der Prozessausschlussliste</span><span class="sxs-lookup"><span data-stu-id="079b2-165">Use wildcards in the process exclusion list</span></span>

<span data-ttu-id="079b2-166">Die Verwendung von Platzhaltern in der Prozessausschlussliste ist von der Verwendung in anderen Ausschlusslisten verschieden.</span><span class="sxs-lookup"><span data-stu-id="079b2-166">The use of wildcards in the process exclusion list is different from their use in other exclusion lists.</span></span>

<span data-ttu-id="079b2-167">Insbesondere können Sie das Fragezeichen ( ) nicht verwenden, und das Sternchen ( ) kann nur am Ende eines vollständigen `?` `*` Pfads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="079b2-167">In particular, you cannot use the question mark (`?`) wildcard, and the asterisk (`*`) wildcard can only be used at the end of a complete path.</span></span> <span data-ttu-id="079b2-168">Sie können umgebungsvariablen (z. B. ) weiterhin als Platzhalter verwenden, wenn Sie Elemente in der Prozessausschlussliste `%ALLUSERSPROFILE%` definieren.</span><span class="sxs-lookup"><span data-stu-id="079b2-168">You can still use environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the process exclusion list.</span></span>

<span data-ttu-id="079b2-169">In der folgenden Tabelle wird beschrieben, wie die Platzhalter in der Prozessausschlussliste verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="079b2-169">The following table describes how the wildcards can be used in the process exclusion list:</span></span>

|<span data-ttu-id="079b2-170">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="079b2-170">Wildcard</span></span> | <span data-ttu-id="079b2-171">Beispiel für die Verwendung</span><span class="sxs-lookup"><span data-stu-id="079b2-171">Example use</span></span> | <span data-ttu-id="079b2-172">Beispiel für Übereinstimmungen</span><span class="sxs-lookup"><span data-stu-id="079b2-172">Example matches</span></span> |
|:---|:---|:---|
|<span data-ttu-id="079b2-173">`*` (Sternchen)</span><span class="sxs-lookup"><span data-stu-id="079b2-173">`*` (asterisk)</span></span> <br/><br/> <span data-ttu-id="079b2-174">Ersetzt eine beliebige Anzahl von Zeichen</span><span class="sxs-lookup"><span data-stu-id="079b2-174">Replaces any number of characters</span></span> | `C:\MyData\*` | <span data-ttu-id="079b2-175">Jede Datei, die von geöffnet wird `C:\MyData\file.exe`</span><span class="sxs-lookup"><span data-stu-id="079b2-175">Any file opened by `C:\MyData\file.exe`</span></span> |
|<span data-ttu-id="079b2-176">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="079b2-176">Environment variables</span></span> <br/><br/> <span data-ttu-id="079b2-177">Die definierte Variable wird als Pfad aufgefüllt, wenn der Ausschluss ausgewertet wird</span><span class="sxs-lookup"><span data-stu-id="079b2-177">The defined variable is populated as a path when the exclusion is evaluated</span></span> | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | <span data-ttu-id="079b2-178">Jede Datei, die von geöffnet wird `C:\ProgramData\CustomLogFiles\file.exe`</span><span class="sxs-lookup"><span data-stu-id="079b2-178">Any file opened by `C:\ProgramData\CustomLogFiles\file.exe`</span></span> |

## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="079b2-179">Überprüfen der Liste der Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="079b2-179">Review the list of exclusions</span></span>

<span data-ttu-id="079b2-180">Sie können die Elemente in der Ausschlussliste mit MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure)oder der Windows Security [App abrufen.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="079b2-180">You can retrieve the items in the exclusion list with MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure), or the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

<span data-ttu-id="079b2-181">Wenn Sie PowerShell verwenden, können Sie die Liste auf zwei Arten abrufen:</span><span class="sxs-lookup"><span data-stu-id="079b2-181">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="079b2-182">Rufen Sie den Status aller Microsoft Defender Antivirus-Einstellungen ab.</span><span class="sxs-lookup"><span data-stu-id="079b2-182">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="079b2-183">Jede liste wird in separaten Zeilen angezeigt, aber die Elemente in jeder Liste werden in derselben Zeile kombiniert.</span><span class="sxs-lookup"><span data-stu-id="079b2-183">Each of the lists will be displayed on separate lines, but the items within each list will be combined into the same line.</span></span>
- <span data-ttu-id="079b2-184">Schreiben Sie den Status aller Einstellungen in eine Variable, und verwenden Sie diese Variable, um nur die bestimmte Liste auf aufruft, an der Sie interessiert sind.</span><span class="sxs-lookup"><span data-stu-id="079b2-184">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="079b2-185">Jede Verwendung `Add-MpPreference` von wird in eine neue Zeile geschrieben.</span><span class="sxs-lookup"><span data-stu-id="079b2-185">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="079b2-186">Überprüfen der Ausschlussliste mithilfe von MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="079b2-186">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="079b2-187">Verwenden Sie den folgenden Befehl, um Ausschlüsse mit dem [dedizierten Befehlszeilentool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="079b2-187">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> <span data-ttu-id="079b2-188">Das Überprüfen von Ausschlüssen mit MpCmdRun erfordert Microsoft Defender Antivirus CAMP, Version 4.18.1812.3 (veröffentlicht im Dezember 2018) oder höher.</span><span class="sxs-lookup"><span data-stu-id="079b2-188">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="079b2-189">Überprüfen der Liste der Ausschlüsse zusammen mit allen anderen Microsoft Defender Antivirus-Einstellungen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="079b2-189">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="079b2-190">Verwenden Sie das folgende Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="079b2-190">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="079b2-191">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender)</span><span class="sxs-lookup"><span data-stu-id="079b2-191">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="079b2-192">Abrufen einer bestimmten Ausschlussliste mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="079b2-192">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="079b2-193">Verwenden Sie den folgenden Codeausschnitt (geben Sie jede Zeile als separaten Befehl ein); Ersetzen **Sie WDAVprefs** durch die Bezeichnung, die Sie der Variablen nennen möchten:</span><span class="sxs-lookup"><span data-stu-id="079b2-193">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

<span data-ttu-id="079b2-194">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender)</span><span class="sxs-lookup"><span data-stu-id="079b2-194">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="related-articles"></a><span data-ttu-id="079b2-195">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="079b2-195">Related articles</span></span>

- [<span data-ttu-id="079b2-196">Konfigurieren und Überprüfen von Ausschlüssen in Microsoft Defender Antivirus-Scans</span><span class="sxs-lookup"><span data-stu-id="079b2-196">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="079b2-197">Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateinamen, Erweiterung und Ordnerspeicherort</span><span class="sxs-lookup"><span data-stu-id="079b2-197">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="079b2-198">Konfigurieren von Microsoft Defender Antivirus-Ausschlüssen unter Windows Server</span><span class="sxs-lookup"><span data-stu-id="079b2-198">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="079b2-199">Häufige Fehler, die beim Festlegen von Ausschlüssen vermieden werden sollten</span><span class="sxs-lookup"><span data-stu-id="079b2-199">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="079b2-200">Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus-Scans und -Korrekturen</span><span class="sxs-lookup"><span data-stu-id="079b2-200">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="079b2-201">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="079b2-201">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)