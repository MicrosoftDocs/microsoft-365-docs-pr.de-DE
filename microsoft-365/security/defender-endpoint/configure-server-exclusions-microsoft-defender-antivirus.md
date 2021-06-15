---
title: Konfigurieren Microsoft Defender Antivirus Ausschlüsse auf Windows Server
ms.reviewer: ''
manager: dansimp
description: Windows Der Server enthält automatische Ausschlüsse, basierend auf der Serverrolle. Sie können auch benutzerdefinierte Ausschlüsse hinzufügen.
keywords: Ausschlüsse, Server, automatische Ausschlüsse, automatisch, benutzerdefiniert, Scans, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 02/10/2021
ms.openlocfilehash: 31d5c22d11a28c9604b2be3145ebd46715a6e5b3
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925515"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a><span data-ttu-id="f9fdc-105">Konfigurieren Microsoft Defender Antivirus Ausschlüsse auf Windows Server</span><span class="sxs-lookup"><span data-stu-id="f9fdc-105">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>


<span data-ttu-id="f9fdc-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f9fdc-106">**Applies to:**</span></span>

- [<span data-ttu-id="f9fdc-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f9fdc-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f9fdc-108">Microsoft Defender Antivirus auf Windows Server 2016 und Windows Server 2019 registriert Sie automatisch bei bestimmten Ausschlüssen, wie von der angegebenen Serverrolle definiert.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-108">Microsoft Defender Antivirus on Windows Server 2016 and Windows Server 2019 automatically enrolls you in certain exclusions, as defined by your specified server role.</span></span> <span data-ttu-id="f9fdc-109">Diese Ausschlüsse werden nicht in den standardmäßigen Ausschlusslisten angezeigt, die in der [Windows-Sicherheit App](microsoft-defender-security-center-antivirus.md)angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-109">These exclusions do not appear in the standard exclusion lists that are shown in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f9fdc-110">Automatische Ausschlüsse gelten nur für RTP-Scans (Real-Time Protection).</span><span class="sxs-lookup"><span data-stu-id="f9fdc-110">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="f9fdc-111">Automatische Ausschlüsse werden während einer Vollständig-/Schnell- oder Bedarfsüberprüfung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-111">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>

<span data-ttu-id="f9fdc-112">Zusätzlich zu automatischen Ausschlüssen, die durch die Serverrolle definiert sind, können Sie benutzerdefinierte Ausschlüsse hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-112">In addition to server role-defined automatic exclusions, you can add or remove custom exclusions.</span></span> <span data-ttu-id="f9fdc-113">Lesen Sie dazu die folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="f9fdc-113">To do that, refer to these articles:</span></span>
- [<span data-ttu-id="f9fdc-114">Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateiname, Erweiterung und Ordnerspeicherort</span><span class="sxs-lookup"><span data-stu-id="f9fdc-114">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f9fdc-115">Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden</span><span class="sxs-lookup"><span data-stu-id="f9fdc-115">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a><span data-ttu-id="f9fdc-116">Ein paar Punkte, die Sie beachten sollten</span><span class="sxs-lookup"><span data-stu-id="f9fdc-116">A few points to keep in mind</span></span>

<span data-ttu-id="f9fdc-117">Beachten Sie die folgenden wichtigen Punkte:</span><span class="sxs-lookup"><span data-stu-id="f9fdc-117">Keep the following important points in mind:</span></span>

- <span data-ttu-id="f9fdc-118">Benutzerdefinierte Ausschlüsse haben Vorrang vor automatischen Ausschlüssen.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-118">Custom exclusions take precedence over automatic exclusions.</span></span>
- <span data-ttu-id="f9fdc-119">Automatische Ausschlüsse gelten nur für RTP-Scans (Real-Time Protection).</span><span class="sxs-lookup"><span data-stu-id="f9fdc-119">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="f9fdc-120">Automatische Ausschlüsse werden während einer Vollständig-/Schnell- oder Bedarfsüberprüfung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-120">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>
- <span data-ttu-id="f9fdc-121">Benutzerdefinierte und doppelte Ausschlüsse führen nicht zu Konflikten mit automatischen Ausschlüssen.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-121">Custom and duplicate exclusions do not conflict with automatic exclusions.</span></span>
- <span data-ttu-id="f9fdc-122">Microsoft Defender Antivirus ermittelt mithilfe der DISM-Tools (Deployment Image Servicing and Management), welche Rollen auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-122">Microsoft Defender Antivirus uses the Deployment Image Servicing and Management (DISM) tools to determine which roles are installed on your computer.</span></span>

## <a name="opt-out-of-automatic-exclusions"></a><span data-ttu-id="f9fdc-123">Abmelden von automatischen Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="f9fdc-123">Opt out of automatic exclusions</span></span>

<span data-ttu-id="f9fdc-124">In Windows Server 2016 und Windows Server 2019 schließen die vordefinierten Ausschlüsse, die von Sicherheitsupdates bereitgestellt werden, nur die Standardpfade für eine Rolle oder ein Feature aus.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-124">In Windows Server 2016 and Windows Server 2019, the predefined exclusions delivered by Security intelligence updates only exclude the default paths for a role or feature.</span></span> <span data-ttu-id="f9fdc-125">Wenn Sie eine Rolle oder ein Feature in einem benutzerdefinierten Pfad installiert haben oder den Satz von Ausschlüssen manuell steuern möchten, stellen Sie sicher, dass Sie die automatischen Ausschlüsse, die in Security Intelligence-Updates bereitgestellt werden, deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-125">If you installed a role or feature in a custom path, or you want to manually control the set of exclusions, make sure to opt out of the automatic exclusions delivered in Security intelligence updates.</span></span> <span data-ttu-id="f9fdc-126">Beachten Sie jedoch, dass die automatisch übermittelten Ausschlüsse für Windows Server 2016 und 2019-Rollen optimiert sind.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-126">But keep in mind that the exclusions that are delivered automatically are optimized for Windows Server 2016 and 2019 roles.</span></span> <span data-ttu-id="f9fdc-127">Informationen zum [Definieren von Ausschlüssen](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) finden Sie unter Empfehlungen, bevor Sie Ihre Ausschlusslisten definieren.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-127">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

> [!WARNING]
> <span data-ttu-id="f9fdc-128">Das Deaktivieren automatischer Ausschlüsse kann sich negativ auf die Leistung auswirken oder zu einer Datenbeschädigung führen.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-128">Opting out of automatic exclusions may adversely impact performance, or result in data corruption.</span></span> <span data-ttu-id="f9fdc-129">Die automatisch übermittelten Ausschlüsse sind für Windows Server 2016- und Windows Server 2019-Rollen optimiert.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-129">The exclusions that are delivered automatically are optimized for Windows Server 2016 and Windows Server 2019 roles.</span></span>

<span data-ttu-id="f9fdc-130">Da vordefinierte Ausschlüsse **standardpfade** nur ausschließen, müssen Sie, wenn Sie NTDS und SYSVOL auf ein anderes Laufwerk oder einen anderen Pfad verschieben, *der vom ursprünglichen Pfad abweicht,* ausschlüsse manuell mithilfe der hier [aufgeführten](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) Informationen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-130">Because predefined exclusions only exclude **default paths**, if you move NTDS and SYSVOL to another drive or path that is *different from the original path*, you must add exclusions manually using the information [here](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span></span>

<span data-ttu-id="f9fdc-131">Sie können die automatischen Ausschlusslisten mit Gruppenrichtlinien, PowerShell-Cmdlets und WMI deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-131">You can disable the automatic exclusion lists with Group Policy, PowerShell cmdlets, and WMI.</span></span>

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="f9fdc-132">Verwenden von Gruppenrichtlinien zum Deaktivieren der Liste der automatischen Ausschlüsse auf Windows Server 2016 und Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="f9fdc-132">Use Group Policy to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

1. <span data-ttu-id="f9fdc-133">Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="f9fdc-133">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span></span> <span data-ttu-id="f9fdc-134">Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="f9fdc-134">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>
2. <span data-ttu-id="f9fdc-135">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und klicken Sie dann auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="f9fdc-135">In the **Group Policy Management Editor** go to **Computer configuration**, and then click **Administrative templates**.</span></span>
3. <span data-ttu-id="f9fdc-136">Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Ausschlüssen.**</span><span class="sxs-lookup"><span data-stu-id="f9fdc-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>
4. <span data-ttu-id="f9fdc-137">Doppelklicken Sie auf **"Automatische Ausschlüsse deaktivieren",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-137">Double-click **Turn off Auto Exclusions**, and set the option to **Enabled**.</span></span> <span data-ttu-id="f9fdc-138">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-138">Then click **OK**.</span></span> 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a><span data-ttu-id="f9fdc-139">Verwenden von PowerShell-Cmdlets zum Deaktivieren der Liste der automatischen Ausschlüsse in Windows Server 2016 und 2019</span><span class="sxs-lookup"><span data-stu-id="f9fdc-139">Use PowerShell cmdlets to disable the auto-exclusions list on Windows Server 2016 and 2019</span></span>

<span data-ttu-id="f9fdc-140">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="f9fdc-140">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

<span data-ttu-id="f9fdc-141">Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="f9fdc-141">To learn more, see the following resources:</span></span>

- <span data-ttu-id="f9fdc-142">[Verwenden Sie PowerShell-Cmdlets, um Microsoft Defender Antivirus zu konfigurieren und auszuführen.](use-powershell-cmdlets-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f9fdc-142">[Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>
- <span data-ttu-id="f9fdc-143">[Verwenden Sie PowerShell mit Microsoft Defender Antivirus](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="f9fdc-143">[Use PowerShell with Microsoft Defender Antivirus](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="f9fdc-144">Verwenden Windows Management Instruction (WMI) zum Deaktivieren der Liste der automatischen Ausschlüsse auf Windows Server 2016 und Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="f9fdc-144">Use Windows Management Instruction (WMI) to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

<span data-ttu-id="f9fdc-145">Verwenden Sie die **Set-Methode** der [MSFT_MpPreference-Klasse](/previous-versions/windows/desktop/defender/msft-mppreference) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f9fdc-145">Use the **Set** method of the [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) class for the following properties:</span></span>

```WMI
DisableAutoExclusions
```

<span data-ttu-id="f9fdc-146">Weitere Informationen und zulässige Parameter finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="f9fdc-146">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="f9fdc-147">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="f9fdc-147">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a><span data-ttu-id="f9fdc-148">Liste der automatischen Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f9fdc-148">List of automatic exclusions</span></span>

<span data-ttu-id="f9fdc-149">Die folgenden Abschnitte enthalten die Ausschlüsse, die mit automatischen Ausschlüssen von Dateipfaden und Dateitypen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-149">The following sections contain the exclusions that are delivered with automatic exclusions file paths and file types.</span></span>

### <a name="default-exclusions-for-all-roles"></a><span data-ttu-id="f9fdc-150">Standardausschlüsse für alle Rollen</span><span class="sxs-lookup"><span data-stu-id="f9fdc-150">Default exclusions for all roles</span></span>

<span data-ttu-id="f9fdc-151">In diesem Abschnitt werden die Standardausschlüsse für alle Rollen Windows Server 2016 und 2019 aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-151">This section lists the default exclusions for all Windows Server 2016 and 2019 roles.</span></span>

> [!NOTE]
> <span data-ttu-id="f9fdc-152">Die Standardspeicherorte können sich von den in diesem Artikel aufgeführten Speicherorten unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-152">The default locations could be different than what's listed in this article.</span></span>

#### <a name="windows-tempedb-files"></a><span data-ttu-id="f9fdc-153">Windows "temp.edb"-Dateien</span><span class="sxs-lookup"><span data-stu-id="f9fdc-153">Windows "temp.edb" files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a><span data-ttu-id="f9fdc-154">Windows Aktualisieren von Dateien oder Dateien mit automatischer Aktualisierung</span><span class="sxs-lookup"><span data-stu-id="f9fdc-154">Windows Update files or Automatic Update files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a><span data-ttu-id="f9fdc-155">Windows-Sicherheit-Dateien</span><span class="sxs-lookup"><span data-stu-id="f9fdc-155">Windows Security files</span></span>

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a><span data-ttu-id="f9fdc-156">Gruppenrichtliniendateien</span><span class="sxs-lookup"><span data-stu-id="f9fdc-156">Group Policy files</span></span>

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a><span data-ttu-id="f9fdc-157">WINS-Dateien</span><span class="sxs-lookup"><span data-stu-id="f9fdc-157">WINS files</span></span>

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a><span data-ttu-id="f9fdc-158">Dateireplikationsdienstausschlüsse (File Replication Service, FRS)</span><span class="sxs-lookup"><span data-stu-id="f9fdc-158">File Replication Service (FRS) exclusions</span></span>

- <span data-ttu-id="f9fdc-159">Dateien im Arbeitsordner des Dateireplikationsdiensts (File Replication Service, FRS).</span><span class="sxs-lookup"><span data-stu-id="f9fdc-159">Files in the File Replication Service (FRS) working folder.</span></span> <span data-ttu-id="f9fdc-160">Der FRS-Arbeitsordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span><span class="sxs-lookup"><span data-stu-id="f9fdc-160">The FRS working folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span></span>

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- <span data-ttu-id="f9fdc-161">FRS-Datenbankprotokolldateien.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-161">FRS Database log files.</span></span> <span data-ttu-id="f9fdc-162">Der Frs-Datenbankprotokollordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span><span class="sxs-lookup"><span data-stu-id="f9fdc-162">The FRS Database log file folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span></span>

  - `%windir%\Ntfrs\*\Edb\*.log`

- <span data-ttu-id="f9fdc-163">Der FRS-Stagingordner.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-163">The FRS staging folder.</span></span> <span data-ttu-id="f9fdc-164">Der Stagingordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span><span class="sxs-lookup"><span data-stu-id="f9fdc-164">The staging folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span></span>

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- <span data-ttu-id="f9fdc-165">Der FRS-Vorinstallationsordner.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-165">The FRS preinstall folder.</span></span> <span data-ttu-id="f9fdc-166">Dieser Ordner wird vom Ordner angegeben. `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span><span class="sxs-lookup"><span data-stu-id="f9fdc-166">This folder is specified by the folder `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span></span>

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- <span data-ttu-id="f9fdc-167">Die DFSR-Datenbank (Distributed File System Replication) und Arbeitsordner.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-167">The Distributed File System Replication (DFSR) database and working folders.</span></span> <span data-ttu-id="f9fdc-168">Diese Ordner werden durch den Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span><span class="sxs-lookup"><span data-stu-id="f9fdc-168">These folders are specified by the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span></span>

  > [!NOTE]
  > <span data-ttu-id="f9fdc-169">Informationen zu benutzerdefinierten Speicherorten finden Sie unter ["Automatische Ausschlüsse deaktivieren".](#opt-out-of-automatic-exclusions)</span><span class="sxs-lookup"><span data-stu-id="f9fdc-169">For custom locations, see [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span></span>

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

#### <a name="process-exclusions"></a><span data-ttu-id="f9fdc-170">Prozessausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f9fdc-170">Process exclusions</span></span>

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a><span data-ttu-id="f9fdc-171">Hyper-V-Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f9fdc-171">Hyper-V exclusions</span></span>

<span data-ttu-id="f9fdc-172">In der folgenden Tabelle sind die Dateitypausschlüsse, Ordnerausschlüsse und Prozessausschlüsse aufgeführt, die bei der Installation der Hyper-V-Rolle automatisch übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-172">The following table lists the file type exclusions, folder exclusions, and process exclusions that are delivered automatically when you install the Hyper-V role.</span></span>

|<span data-ttu-id="f9fdc-173">Dateitypausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f9fdc-173">File type exclusions</span></span> |<span data-ttu-id="f9fdc-174">Ausschlüsse von Ordnern</span><span class="sxs-lookup"><span data-stu-id="f9fdc-174">Folder exclusions</span></span>  | <span data-ttu-id="f9fdc-175">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="f9fdc-175">Process exclusions</span></span> |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a><span data-ttu-id="f9fdc-176">SYSVOL-Dateien</span><span class="sxs-lookup"><span data-stu-id="f9fdc-176">SYSVOL files</span></span>

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a><span data-ttu-id="f9fdc-177">Active Directory-Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f9fdc-177">Active Directory exclusions</span></span>

<span data-ttu-id="f9fdc-178">In diesem Abschnitt werden die Ausschlüsse aufgeführt, die bei der Installation von Active Directory Domain Services automatisch übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-178">This section lists the exclusions that are delivered automatically when you install Active Directory Domain Services.</span></span>

#### <a name="ntds-database-files"></a><span data-ttu-id="f9fdc-179">NTDS-Datenbankdateien</span><span class="sxs-lookup"><span data-stu-id="f9fdc-179">NTDS database files</span></span>

<span data-ttu-id="f9fdc-180">Die Datenbankdateien werden im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span><span class="sxs-lookup"><span data-stu-id="f9fdc-180">The database files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span></span>

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a><span data-ttu-id="f9fdc-181">Die AD DS-Transaktionsprotokolldateien</span><span class="sxs-lookup"><span data-stu-id="f9fdc-181">The AD DS transaction log files</span></span>

<span data-ttu-id="f9fdc-182">Die Transaktionsprotokolldateien werden im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span><span class="sxs-lookup"><span data-stu-id="f9fdc-182">The transaction log files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span></span>

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a><span data-ttu-id="f9fdc-183">Der NTDS-Arbeitsordner</span><span class="sxs-lookup"><span data-stu-id="f9fdc-183">The NTDS working folder</span></span>

<span data-ttu-id="f9fdc-184">Dieser Ordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span><span class="sxs-lookup"><span data-stu-id="f9fdc-184">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span></span>

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a><span data-ttu-id="f9fdc-185">Prozessausschlüsse für AD DS- und AD DS-bezogene Supportdateien</span><span class="sxs-lookup"><span data-stu-id="f9fdc-185">Process exclusions for AD DS and AD DS-related support files</span></span>

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a><span data-ttu-id="f9fdc-186">DHCP-Serverausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f9fdc-186">DHCP Server exclusions</span></span>

<span data-ttu-id="f9fdc-187">In diesem Abschnitt werden die Ausschlüsse aufgeführt, die bei der Installation der DHCP-Serverrolle automatisch übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-187">This section lists the exclusions that are delivered automatically when you install the DHCP Server role.</span></span> <span data-ttu-id="f9fdc-188">Die Speicherorte der DHCP-Serverdateien werden durch die Parameter *DatabasePath,* *DhcpLogFilePath* und *BackupDatabasePath* im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span><span class="sxs-lookup"><span data-stu-id="f9fdc-188">The DHCP Server file locations are specified by the *DatabasePath*, *DhcpLogFilePath*, and *BackupDatabasePath* parameters in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span></span>

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a><span data-ttu-id="f9fdc-189">DNS-Serverausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f9fdc-189">DNS Server exclusions</span></span>

<span data-ttu-id="f9fdc-190">In diesem Abschnitt werden die Datei- und Ordnerausschlüsse sowie die Prozessausschlüsse aufgeführt, die automatisch übermittelt werden, wenn Sie die DNS-Serverrolle installieren.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-190">This section lists the file and folder exclusions and the process exclusions that are delivered automatically when you install the DNS Server role.</span></span>

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a><span data-ttu-id="f9fdc-191">Datei- und Ordnerausschlüsse für die DNS-Serverrolle</span><span class="sxs-lookup"><span data-stu-id="f9fdc-191">File and folder exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a><span data-ttu-id="f9fdc-192">Prozessausschlüsse für die DNS-Serverrolle</span><span class="sxs-lookup"><span data-stu-id="f9fdc-192">Process exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a><span data-ttu-id="f9fdc-193">Datei- und Storage dienstausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f9fdc-193">File and Storage Services exclusions</span></span>

<span data-ttu-id="f9fdc-194">In diesem Abschnitt werden die Datei- und Ordnerausschlüsse aufgeführt, die automatisch übermittelt werden, wenn Sie die Rolle "Datei" und "Storage Dienste" installieren.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-194">This section lists the file and folder exclusions that are delivered automatically when you install the File and Storage Services role.</span></span> <span data-ttu-id="f9fdc-195">Die unten aufgeführten Ausschlüsse enthalten keine Ausschlüsse für die Clusterrolle.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-195">The exclusions listed below do not include exclusions for the Clustering role.</span></span>

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a><span data-ttu-id="f9fdc-196">Druckserverausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f9fdc-196">Print Server exclusions</span></span>

<span data-ttu-id="f9fdc-197">In diesem Abschnitt werden die Dateitypausschlüsse, Ordnerausschlüsse und Prozessausschlüsse aufgeführt, die automatisch übermittelt werden, wenn Sie die Rolle "Druckserver" installieren.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-197">This section lists the file type exclusions, folder exclusions, and the process exclusions that are delivered automatically when you install the Print Server role.</span></span>

#### <a name="file-type-exclusions"></a><span data-ttu-id="f9fdc-198">Dateitypausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f9fdc-198">File type exclusions</span></span>

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a><span data-ttu-id="f9fdc-199">Ausschlüsse von Ordnern</span><span class="sxs-lookup"><span data-stu-id="f9fdc-199">Folder exclusions</span></span>

<span data-ttu-id="f9fdc-200">Dieser Ordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span><span class="sxs-lookup"><span data-stu-id="f9fdc-200">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span></span>

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a><span data-ttu-id="f9fdc-201">Prozessausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f9fdc-201">Process exclusions</span></span>

- `spoolsv.exe`

### <a name="web-server-exclusions"></a><span data-ttu-id="f9fdc-202">Webserverausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f9fdc-202">Web Server exclusions</span></span>

<span data-ttu-id="f9fdc-203">In diesem Abschnitt werden die Ordnerausschlüsse und Prozessausschlüsse aufgeführt, die automatisch übermittelt werden, wenn Sie die Webserverrolle installieren.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-203">This section lists the folder exclusions and the process exclusions that are delivered automatically when you install the Web Server role.</span></span>

#### <a name="folder-exclusions"></a><span data-ttu-id="f9fdc-204">Ausschlüsse von Ordnern</span><span class="sxs-lookup"><span data-stu-id="f9fdc-204">Folder exclusions</span></span>

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a><span data-ttu-id="f9fdc-205">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="f9fdc-205">Process exclusions</span></span>

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a><span data-ttu-id="f9fdc-206">Deaktivieren der Überprüfung von Dateien im Ordner "Sysvol\Sysvol" oder im Ordner "SYSVOL_DFSR\Sysvol"</span><span class="sxs-lookup"><span data-stu-id="f9fdc-206">Turning off scanning of files in the Sysvol\Sysvol folder or the SYSVOL_DFSR\Sysvol folder</span></span>

<span data-ttu-id="f9fdc-207">Der aktuelle Speicherort des `Sysvol\Sysvol` Ordners oder `SYSVOL_DFSR\Sysvol` ordners und alle Unterordner ist das Dateisystem-Analyseziel des Stamms der Replikatgruppe.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-207">The current location of the `Sysvol\Sysvol` or `SYSVOL_DFSR\Sysvol` folder and all the subfolders is the file system reparse target of the replica set root.</span></span> <span data-ttu-id="f9fdc-208">Die `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` Ordner und Ordner verwenden standardmäßig die folgenden Speicherorte:</span><span class="sxs-lookup"><span data-stu-id="f9fdc-208">The `Sysvol\Sysvol` and `SYSVOL_DFSR\Sysvol` folders use the following locations by default:</span></span>

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

<span data-ttu-id="f9fdc-209">Der Pfad zu der aktuell aktiven `SYSVOL` Wird von der NETLOGON-Freigabe referenziert und kann durch den SysVol-Wertnamen im folgenden Unterschlüssel bestimmt werden: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span><span class="sxs-lookup"><span data-stu-id="f9fdc-209">The path to the currently active `SYSVOL` is referenced by the NETLOGON share and can be determined by the SysVol value name in the following subkey: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span></span>

<span data-ttu-id="f9fdc-210">Schließen Sie die folgenden Dateien aus diesem Ordner und allen unteren Ordnern aus:</span><span class="sxs-lookup"><span data-stu-id="f9fdc-210">Exclude the following files from this folder and all its subfolders:</span></span>

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

### <a name="windows-server-update-services-exclusions"></a><span data-ttu-id="f9fdc-211">Windows Server Update Services Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f9fdc-211">Windows Server Update Services exclusions</span></span>

<span data-ttu-id="f9fdc-212">In diesem Abschnitt werden die Ordnerausschlüsse aufgeführt, die automatisch übermittelt werden, wenn Sie die Rolle Windows Server Update Services (WSUS) installieren.</span><span class="sxs-lookup"><span data-stu-id="f9fdc-212">This section lists the folder exclusions that are delivered automatically when you install the Windows Server Update Services (WSUS) role.</span></span> <span data-ttu-id="f9fdc-213">Der WSUS-Ordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span><span class="sxs-lookup"><span data-stu-id="f9fdc-213">The WSUS folder is specified in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span></span>

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a><span data-ttu-id="f9fdc-214">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9fdc-214">See also</span></span>

- [<span data-ttu-id="f9fdc-215">Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender Antivirus Scans</span><span class="sxs-lookup"><span data-stu-id="f9fdc-215">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f9fdc-216">Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateiname, Erweiterung und Ordnerspeicherort</span><span class="sxs-lookup"><span data-stu-id="f9fdc-216">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f9fdc-217">Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden</span><span class="sxs-lookup"><span data-stu-id="f9fdc-217">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f9fdc-218">Häufige Fehler, die beim Festlegen von Ausschlüssen vermieden werden sollten</span><span class="sxs-lookup"><span data-stu-id="f9fdc-218">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f9fdc-219">Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus Überprüfungen und Korrekturen</span><span class="sxs-lookup"><span data-stu-id="f9fdc-219">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f9fdc-220">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="f9fdc-220">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
