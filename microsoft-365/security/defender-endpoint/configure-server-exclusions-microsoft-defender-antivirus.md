---
title: Konfigurieren von Microsoft Defender Antivirus-Ausschlüssen unter Windows Server
ms.reviewer: ''
manager: dansimp
description: Windows Server enthält automatische Ausschlüsse basierend auf der Serverrolle. Sie können auch benutzerdefinierte Ausschlüsse hinzufügen.
keywords: Ausschlüsse, Server, automatische Ausschlüsse, automatisch, benutzerdefinierte, Scans, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.openlocfilehash: 507edb980f671b2f39403cc41e540150f5e82891
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764341"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a><span data-ttu-id="03389-105">Konfigurieren von Microsoft Defender Antivirus-Ausschlüssen unter Windows Server</span><span class="sxs-lookup"><span data-stu-id="03389-105">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="03389-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="03389-106">**Applies to:**</span></span>

- [<span data-ttu-id="03389-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="03389-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="03389-108">Microsoft Defender Antivirus unter Windows Server 2016 und Windows Server 2019 registriert Sie automatisch bei bestimmten Ausschlüssen, wie durch Ihre angegebene Serverrolle definiert.</span><span class="sxs-lookup"><span data-stu-id="03389-108">Microsoft Defender Antivirus on Windows Server 2016 and Windows Server 2019 automatically enrolls you in certain exclusions, as defined by your specified server role.</span></span> <span data-ttu-id="03389-109">Diese Ausschlüsse werden nicht in den Standardausschlusslisten angezeigt, die in der [Windows Security App angezeigt werden.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="03389-109">These exclusions do not appear in the standard exclusion lists that are shown in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="03389-110">Automatische Ausschlüsse gelten nur für die Überprüfung des Echtzeitschutzes (Real-Time Protection, RTP).</span><span class="sxs-lookup"><span data-stu-id="03389-110">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="03389-111">Automatische Ausschlüsse werden bei einer Vollständig-/Schnell- oder Bei-Bedarf-Überprüfung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="03389-111">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>

<span data-ttu-id="03389-112">Zusätzlich zu serverrolledefinierten automatischen Ausschlüssen können Sie benutzerdefinierte Ausschlüsse hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="03389-112">In addition to server role-defined automatic exclusions, you can add or remove custom exclusions.</span></span> <span data-ttu-id="03389-113">Lesen Sie dazu die folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="03389-113">To do that, refer to these articles:</span></span>
- [<span data-ttu-id="03389-114">Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateinamen, Erweiterung und Ordnerspeicherort</span><span class="sxs-lookup"><span data-stu-id="03389-114">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="03389-115">Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden</span><span class="sxs-lookup"><span data-stu-id="03389-115">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a><span data-ttu-id="03389-116">Einige Punkte, die Sie beachten sollten</span><span class="sxs-lookup"><span data-stu-id="03389-116">A few points to keep in mind</span></span>

<span data-ttu-id="03389-117">Beachten Sie die folgenden wichtigen Punkte:</span><span class="sxs-lookup"><span data-stu-id="03389-117">Keep the following important points in mind:</span></span>

- <span data-ttu-id="03389-118">Benutzerdefinierte Ausschlüsse haben Vorrang vor automatischen Ausschlüssen.</span><span class="sxs-lookup"><span data-stu-id="03389-118">Custom exclusions take precedence over automatic exclusions.</span></span>
- <span data-ttu-id="03389-119">Automatische Ausschlüsse gelten nur für die Überprüfung des Echtzeitschutzes (Real-Time Protection, RTP).</span><span class="sxs-lookup"><span data-stu-id="03389-119">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="03389-120">Automatische Ausschlüsse werden bei einer Vollständig-/Schnell- oder Bei-Bedarf-Überprüfung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="03389-120">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>
- <span data-ttu-id="03389-121">Benutzerdefinierte und doppelte Ausschlüsse stehen nicht in Konflikt mit automatischen Ausschlüssen.</span><span class="sxs-lookup"><span data-stu-id="03389-121">Custom and duplicate exclusions do not conflict with automatic exclusions.</span></span>
- <span data-ttu-id="03389-122">Microsoft Defender Antivirus verwendet die Tools für die Bereitstellungsimagewartung und -verwaltung (Deployment Image Servicing and Management, DISM), um zu bestimmen, welche Rollen auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="03389-122">Microsoft Defender Antivirus uses the Deployment Image Servicing and Management (DISM) tools to determine which roles are installed on your computer.</span></span>

## <a name="opt-out-of-automatic-exclusions"></a><span data-ttu-id="03389-123">Abmelden automatischer Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-123">Opt out of automatic exclusions</span></span>

<span data-ttu-id="03389-124">In Windows Server 2016 und Windows Server 2019 schließen die vordefinierten Ausschlüsse von Security Intelligence-Updates nur die Standardpfade für eine Rolle oder ein Feature aus.</span><span class="sxs-lookup"><span data-stu-id="03389-124">In Windows Server 2016 and Windows Server 2019, the predefined exclusions delivered by Security intelligence updates only exclude the default paths for a role or feature.</span></span> <span data-ttu-id="03389-125">Wenn Sie eine Rolle oder ein Feature in einem benutzerdefinierten Pfad installiert haben oder den Satz von Ausschlüssen manuell steuern möchten, müssen Sie die automatischen Ausschlüsse, die in Sicherheitsintelligenzupdates übermittelt werden, abmelden.</span><span class="sxs-lookup"><span data-stu-id="03389-125">If you installed a role or feature in a custom path, or you want to manually control the set of exclusions, make sure to opt out of the automatic exclusions delivered in Security intelligence updates.</span></span> <span data-ttu-id="03389-126">Beachten Sie jedoch, dass die automatisch zugestellten Ausschlüsse für Windows Server 2016- und 2019-Rollen optimiert sind.</span><span class="sxs-lookup"><span data-stu-id="03389-126">But keep in mind that the exclusions that are delivered automatically are optimized for Windows Server 2016 and 2019 roles.</span></span> <span data-ttu-id="03389-127">Weitere [Informationen finden Sie unter Empfehlungen zum Definieren von Ausschlüssen,](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) bevor Sie Ihre Ausschlusslisten definieren.</span><span class="sxs-lookup"><span data-stu-id="03389-127">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

> [!WARNING]
> <span data-ttu-id="03389-128">Das Abmelden automatischer Ausschlüsse kann sich negativ auf die Leistung auswirken oder zu Datenbeschädigungen führen.</span><span class="sxs-lookup"><span data-stu-id="03389-128">Opting out of automatic exclusions may adversely impact performance, or result in data corruption.</span></span> <span data-ttu-id="03389-129">Die automatisch zugestellten Ausschlüsse sind für Windows Server 2016- und Windows Server 2019-Rollen optimiert.</span><span class="sxs-lookup"><span data-stu-id="03389-129">The exclusions that are delivered automatically are optimized for Windows Server 2016 and Windows Server 2019 roles.</span></span>

<span data-ttu-id="03389-130">Da vordefinierte Ausschlüsse nur Standardpfade **ausschließen,** müssen Sie, wenn Sie NTDS und SYSVOL auf ein anderes Laufwerk oder einen anderen Pfad *verschieben,* der sich vom ursprünglichen Pfad unterscheiden, mithilfe der hier gezeigten Informationen manuell Ausschlüsse [hinzufügen.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)</span><span class="sxs-lookup"><span data-stu-id="03389-130">Because predefined exclusions only exclude **default paths**, if you move NTDS and SYSVOL to another drive or path that is *different from the original path*, you must add exclusions manually using the information [here](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span></span>

<span data-ttu-id="03389-131">Sie können die automatischen Ausschlusslisten mit Gruppenrichtlinien, PowerShell-Cmdlets und WMI deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="03389-131">You can disable the automatic exclusion lists with Group Policy, PowerShell cmdlets, and WMI.</span></span>

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="03389-132">Deaktivieren der Liste automatischer Ausschlüsse unter Windows Server 2016 und Windows Server 2019 mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="03389-132">Use Group Policy to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

1. <span data-ttu-id="03389-133">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="03389-133">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span></span> <span data-ttu-id="03389-134">Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="03389-134">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>
2. <span data-ttu-id="03389-135">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie dann auf **Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="03389-135">In the **Group Policy Management Editor** go to **Computer configuration**, and then click **Administrative templates**.</span></span>
3. <span data-ttu-id="03389-136">Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus**  >  **Exclusions**.</span><span class="sxs-lookup"><span data-stu-id="03389-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>
4. <span data-ttu-id="03389-137">Doppelklicken Sie **auf Automatische Ausschlüsse deaktivieren,** und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="03389-137">Double-click **Turn off Auto Exclusions**, and set the option to **Enabled**.</span></span> <span data-ttu-id="03389-138">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="03389-138">Then click **OK**.</span></span> 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a><span data-ttu-id="03389-139">Verwenden von PowerShell-Cmdlets zum Deaktivieren der Liste automatischer Ausschlüsse unter Windows Server 2016 und 2019</span><span class="sxs-lookup"><span data-stu-id="03389-139">Use PowerShell cmdlets to disable the auto-exclusions list on Windows Server 2016 and 2019</span></span>

<span data-ttu-id="03389-140">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="03389-140">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

<span data-ttu-id="03389-141">Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="03389-141">To learn more, see the following resources:</span></span>

- <span data-ttu-id="03389-142">[Verwenden Sie PowerShell-Cmdlets zum Konfigurieren und Ausführen von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="03389-142">[Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>
- <span data-ttu-id="03389-143">[Verwenden von PowerShell mit Microsoft Defender Antivirus](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="03389-143">[Use PowerShell with Microsoft Defender Antivirus](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="03389-144">Deaktivieren der Liste automatischer Ausschlüsse unter Windows Server 2016 und Windows Server 2019 mithilfe von Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="03389-144">Use Windows Management Instruction (WMI) to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

<span data-ttu-id="03389-145">Verwenden Sie **die Set-Methode** [der MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="03389-145">Use the **Set** method of the [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) class for the following properties:</span></span>

```WMI
DisableAutoExclusions
```

<span data-ttu-id="03389-146">Weitere Informationen und zulässige Parameter finden Sie im Folgenden:</span><span class="sxs-lookup"><span data-stu-id="03389-146">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="03389-147">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="03389-147">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a><span data-ttu-id="03389-148">Liste automatischer Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-148">List of automatic exclusions</span></span>

<span data-ttu-id="03389-149">Die folgenden Abschnitte enthalten die Ausschlüsse, die mit automatischen Ausschlüssen dateipfade und Dateitypen zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="03389-149">The following sections contain the exclusions that are delivered with automatic exclusions file paths and file types.</span></span>

### <a name="default-exclusions-for-all-roles"></a><span data-ttu-id="03389-150">Standardausschlüsse für alle Rollen</span><span class="sxs-lookup"><span data-stu-id="03389-150">Default exclusions for all roles</span></span>

<span data-ttu-id="03389-151">In diesem Abschnitt werden die Standardausschlüsse für alle Windows Server 2016- und 2019-Rollen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="03389-151">This section lists the default exclusions for all Windows Server 2016 and 2019 roles.</span></span>

> [!NOTE]
> <span data-ttu-id="03389-152">Die Standardspeicherorte können sich von den in diesem Artikel aufgeführten Unterscheiden unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="03389-152">The default locations could be different than what's listed in this article.</span></span>

#### <a name="windows-tempedb-files"></a><span data-ttu-id="03389-153">Windows"temp.edb"-Dateien</span><span class="sxs-lookup"><span data-stu-id="03389-153">Windows "temp.edb" files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a><span data-ttu-id="03389-154">Windows Update-Dateien oder Automatische Updatedateien</span><span class="sxs-lookup"><span data-stu-id="03389-154">Windows Update files or Automatic Update files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a><span data-ttu-id="03389-155">Windows-Sicherheitsdateien</span><span class="sxs-lookup"><span data-stu-id="03389-155">Windows Security files</span></span>

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a><span data-ttu-id="03389-156">Gruppenrichtliniendateien</span><span class="sxs-lookup"><span data-stu-id="03389-156">Group Policy files</span></span>

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a><span data-ttu-id="03389-157">WINS-Dateien</span><span class="sxs-lookup"><span data-stu-id="03389-157">WINS files</span></span>

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a><span data-ttu-id="03389-158">Ausschlüsse des Dateireplikationsdiensts (File Replication Service, FRS)</span><span class="sxs-lookup"><span data-stu-id="03389-158">File Replication Service (FRS) exclusions</span></span>

- <span data-ttu-id="03389-159">Dateien im Arbeitsordner des Dateireplikationsdiensts (File Replication Service, FRS).</span><span class="sxs-lookup"><span data-stu-id="03389-159">Files in the File Replication Service (FRS) working folder.</span></span> <span data-ttu-id="03389-160">Der Arbeitsordner "FRS" wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span><span class="sxs-lookup"><span data-stu-id="03389-160">The FRS working folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span></span>

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- <span data-ttu-id="03389-161">FRS-Datenbankprotokolldateien.</span><span class="sxs-lookup"><span data-stu-id="03389-161">FRS Database log files.</span></span> <span data-ttu-id="03389-162">Der Ordner "FRS-Datenbankprotokolldatei" wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span><span class="sxs-lookup"><span data-stu-id="03389-162">The FRS Database log file folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span></span>

  - `%windir%\Ntfrs\*\Edb\*.log`

- <span data-ttu-id="03389-163">Der FrS-Stagingordner.</span><span class="sxs-lookup"><span data-stu-id="03389-163">The FRS staging folder.</span></span> <span data-ttu-id="03389-164">Der Stagingordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span><span class="sxs-lookup"><span data-stu-id="03389-164">The staging folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span></span>

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- <span data-ttu-id="03389-165">Der Ordner "FRS preinstall".</span><span class="sxs-lookup"><span data-stu-id="03389-165">The FRS preinstall folder.</span></span> <span data-ttu-id="03389-166">Dieser Ordner wird durch den Ordner angegeben. `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span><span class="sxs-lookup"><span data-stu-id="03389-166">This folder is specified by the folder `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span></span>

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- <span data-ttu-id="03389-167">Die DfSR-Datenbank (Distributed File System Replication) und arbeitsordner.</span><span class="sxs-lookup"><span data-stu-id="03389-167">The Distributed File System Replication (DFSR) database and working folders.</span></span> <span data-ttu-id="03389-168">Diese Ordner werden durch den Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span><span class="sxs-lookup"><span data-stu-id="03389-168">These folders are specified by the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span></span>

  > [!NOTE]
  > <span data-ttu-id="03389-169">Benutzerdefinierte Speicherorte finden Sie [unter Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span><span class="sxs-lookup"><span data-stu-id="03389-169">For custom locations, see [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span></span>

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

#### <a name="process-exclusions"></a><span data-ttu-id="03389-170">Prozessausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-170">Process exclusions</span></span>

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a><span data-ttu-id="03389-171">Hyper-V-Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-171">Hyper-V exclusions</span></span>

<span data-ttu-id="03389-172">In der folgenden Tabelle sind die Dateitypausschlüsse, Ordnerausschlüsse und Prozessausschlüsse aufgeführt, die bei der Installation der Hyper-V-Rolle automatisch zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="03389-172">The following table lists the file type exclusions, folder exclusions, and process exclusions that are delivered automatically when you install the Hyper-V role.</span></span>

|<span data-ttu-id="03389-173">Dateitypausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-173">File type exclusions</span></span> |<span data-ttu-id="03389-174">Ausschlüsse von Ordnern</span><span class="sxs-lookup"><span data-stu-id="03389-174">Folder exclusions</span></span>  | <span data-ttu-id="03389-175">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="03389-175">Process exclusions</span></span> |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a><span data-ttu-id="03389-176">SYSVOL-Dateien</span><span class="sxs-lookup"><span data-stu-id="03389-176">SYSVOL files</span></span>

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a><span data-ttu-id="03389-177">Active Directory-Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-177">Active Directory exclusions</span></span>

<span data-ttu-id="03389-178">In diesem Abschnitt werden die Ausschlüsse aufgeführt, die bei der Installation von Active Directory-Domänendiensten automatisch zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="03389-178">This section lists the exclusions that are delivered automatically when you install Active Directory Domain Services.</span></span>

#### <a name="ntds-database-files"></a><span data-ttu-id="03389-179">NTDS-Datenbankdateien</span><span class="sxs-lookup"><span data-stu-id="03389-179">NTDS database files</span></span>

<span data-ttu-id="03389-180">Die Datenbankdateien werden im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span><span class="sxs-lookup"><span data-stu-id="03389-180">The database files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span></span>

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a><span data-ttu-id="03389-181">Die AD DS-Transaktionsprotokolldateien</span><span class="sxs-lookup"><span data-stu-id="03389-181">The AD DS transaction log files</span></span>

<span data-ttu-id="03389-182">Die Transaktionsprotokolldateien werden im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span><span class="sxs-lookup"><span data-stu-id="03389-182">The transaction log files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span></span>

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a><span data-ttu-id="03389-183">Der NTDS-Arbeitsordner</span><span class="sxs-lookup"><span data-stu-id="03389-183">The NTDS working folder</span></span>

<span data-ttu-id="03389-184">Dieser Ordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span><span class="sxs-lookup"><span data-stu-id="03389-184">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span></span>

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a><span data-ttu-id="03389-185">Prozessausschlüsse für AD DS- und AD DS-bezogene Supportdateien</span><span class="sxs-lookup"><span data-stu-id="03389-185">Process exclusions for AD DS and AD DS-related support files</span></span>

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a><span data-ttu-id="03389-186">DHCP-Serverausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-186">DHCP Server exclusions</span></span>

<span data-ttu-id="03389-187">In diesem Abschnitt werden die Ausschlüsse aufgeführt, die bei der Installation der DHCP-Serverrolle automatisch zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="03389-187">This section lists the exclusions that are delivered automatically when you install the DHCP Server role.</span></span> <span data-ttu-id="03389-188">Die Speicherorte der DHCP -Server-Datei werden durch die *Parameter DatabasePath,* *DhcpLogFilePath* und *BackupDatabasePath* im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span><span class="sxs-lookup"><span data-stu-id="03389-188">The DHCP Server file locations are specified by the *DatabasePath*, *DhcpLogFilePath*, and *BackupDatabasePath* parameters in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span></span>

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a><span data-ttu-id="03389-189">DNS-Serverausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-189">DNS Server exclusions</span></span>

<span data-ttu-id="03389-190">In diesem Abschnitt werden die Datei- und Ordnerausschlüsse sowie die Prozessausschlüsse aufgeführt, die bei der Installation der DNS-Serverrolle automatisch zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="03389-190">This section lists the file and folder exclusions and the process exclusions that are delivered automatically when you install the DNS Server role.</span></span>

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a><span data-ttu-id="03389-191">Datei- und Ordnerausschlüsse für die DNS-Serverrolle</span><span class="sxs-lookup"><span data-stu-id="03389-191">File and folder exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a><span data-ttu-id="03389-192">Prozessausschlüsse für die DNS-Serverrolle</span><span class="sxs-lookup"><span data-stu-id="03389-192">Process exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a><span data-ttu-id="03389-193">Datei- und Speicherdiensteausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-193">File and Storage Services exclusions</span></span>

<span data-ttu-id="03389-194">In diesem Abschnitt werden die Datei- und Ordnerausschlüsse aufgeführt, die bei der Installation der Rolle Datei- und Speicherdienste automatisch zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="03389-194">This section lists the file and folder exclusions that are delivered automatically when you install the File and Storage Services role.</span></span> <span data-ttu-id="03389-195">Die unten aufgeführten Ausschlüsse enthalten keine Ausschlüsse für die Clusterrolle.</span><span class="sxs-lookup"><span data-stu-id="03389-195">The exclusions listed below do not include exclusions for the Clustering role.</span></span>

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a><span data-ttu-id="03389-196">Print Server-Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-196">Print Server exclusions</span></span>

<span data-ttu-id="03389-197">In diesem Abschnitt werden die Dateitypausschlüsse, Ordnerausschlüsse und Prozessausschlüsse aufgeführt, die bei der Installation der Print Server-Rolle automatisch zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="03389-197">This section lists the file type exclusions, folder exclusions, and the process exclusions that are delivered automatically when you install the Print Server role.</span></span>

#### <a name="file-type-exclusions"></a><span data-ttu-id="03389-198">Dateitypausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-198">File type exclusions</span></span>

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a><span data-ttu-id="03389-199">Ausschlüsse von Ordnern</span><span class="sxs-lookup"><span data-stu-id="03389-199">Folder exclusions</span></span>

<span data-ttu-id="03389-200">Dieser Ordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span><span class="sxs-lookup"><span data-stu-id="03389-200">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span></span>

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a><span data-ttu-id="03389-201">Prozessausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-201">Process exclusions</span></span>

- `spoolsv.exe`

### <a name="web-server-exclusions"></a><span data-ttu-id="03389-202">Webserverausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-202">Web Server exclusions</span></span>

<span data-ttu-id="03389-203">In diesem Abschnitt werden die Ordnerausschlüsse und Prozessausschlüsse aufgeführt, die bei der Installation der Webserverrolle automatisch zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="03389-203">This section lists the folder exclusions and the process exclusions that are delivered automatically when you install the Web Server role.</span></span>

#### <a name="folder-exclusions"></a><span data-ttu-id="03389-204">Ausschlüsse von Ordnern</span><span class="sxs-lookup"><span data-stu-id="03389-204">Folder exclusions</span></span>

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a><span data-ttu-id="03389-205">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="03389-205">Process exclusions</span></span>

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a><span data-ttu-id="03389-206">Deaktivieren der Überprüfung von Dateien im Ordner Sysvol\Sysvol oder im Ordner SYSVOL_DFSR\Sysvol</span><span class="sxs-lookup"><span data-stu-id="03389-206">Turning off scanning of files in the Sysvol\Sysvol folder or the SYSVOL_DFSR\Sysvol folder</span></span>

<span data-ttu-id="03389-207">Der aktuelle Speicherort des Oder-Ordners und aller Unterordner ist das `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` Dateisystemreparationsziel des Replikatsatzstamms.</span><span class="sxs-lookup"><span data-stu-id="03389-207">The current location of the `Sysvol\Sysvol` or `SYSVOL_DFSR\Sysvol` folder and all the subfolders is the file system reparse target of the replica set root.</span></span> <span data-ttu-id="03389-208">Die `Sysvol\Sysvol` Ordner und verwenden standardmäßig die folgenden `SYSVOL_DFSR\Sysvol` Speicherorte:</span><span class="sxs-lookup"><span data-stu-id="03389-208">The `Sysvol\Sysvol` and `SYSVOL_DFSR\Sysvol` folders use the following locations by default:</span></span>

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

<span data-ttu-id="03389-209">Auf den Pfad zum aktuell aktiven Wird von der NETLOGON-Freigabe verwiesen und kann durch den `SYSVOL` SysVol-Wertnamen im folgenden Unterschlüssel bestimmt werden: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span><span class="sxs-lookup"><span data-stu-id="03389-209">The path to the currently active `SYSVOL` is referenced by the NETLOGON share and can be determined by the SysVol value name in the following subkey: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span></span>

<span data-ttu-id="03389-210">Schließen Sie die folgenden Dateien aus diesem Ordner und allen unterordnern aus:</span><span class="sxs-lookup"><span data-stu-id="03389-210">Exclude the following files from this folder and all its subfolders:</span></span>

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

### <a name="windows-server-update-services-exclusions"></a><span data-ttu-id="03389-211">Windows Server Update Services-Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="03389-211">Windows Server Update Services exclusions</span></span>

<span data-ttu-id="03389-212">In diesem Abschnitt werden die Ordnerausschlüsse aufgeführt, die automatisch bei der Installation der Windows Server Update Services (WSUS)-Rolle zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="03389-212">This section lists the folder exclusions that are delivered automatically when you install the Windows Server Update Services (WSUS) role.</span></span> <span data-ttu-id="03389-213">Der Ordner WSUS wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span><span class="sxs-lookup"><span data-stu-id="03389-213">The WSUS folder is specified in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span></span>

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a><span data-ttu-id="03389-214">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03389-214">See also</span></span>

- [<span data-ttu-id="03389-215">Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender Antivirus-Scans</span><span class="sxs-lookup"><span data-stu-id="03389-215">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="03389-216">Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateinamen, Erweiterung und Ordnerspeicherort</span><span class="sxs-lookup"><span data-stu-id="03389-216">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="03389-217">Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden</span><span class="sxs-lookup"><span data-stu-id="03389-217">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="03389-218">Häufige Fehler beim Definieren von Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="03389-218">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="03389-219">Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus-Scans und -Korrekturen</span><span class="sxs-lookup"><span data-stu-id="03389-219">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="03389-220">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="03389-220">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)