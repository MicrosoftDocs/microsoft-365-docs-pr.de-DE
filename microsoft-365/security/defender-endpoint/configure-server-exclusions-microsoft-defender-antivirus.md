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
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a>Konfigurieren von Microsoft Defender Antivirus-Ausschlüssen unter Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus unter Windows Server 2016 und Windows Server 2019 registriert Sie automatisch bei bestimmten Ausschlüssen, wie durch Ihre angegebene Serverrolle definiert. Diese Ausschlüsse werden nicht in den Standardausschlusslisten angezeigt, die in der [Windows Security App angezeigt werden.](microsoft-defender-security-center-antivirus.md)

> [!NOTE]
> Automatische Ausschlüsse gelten nur für die Überprüfung des Echtzeitschutzes (Real-Time Protection, RTP). Automatische Ausschlüsse werden bei einer Vollständig-/Schnell- oder Bei-Bedarf-Überprüfung nicht berücksichtigt.

Zusätzlich zu serverrolledefinierten automatischen Ausschlüssen können Sie benutzerdefinierte Ausschlüsse hinzufügen oder entfernen. Lesen Sie dazu die folgenden Artikel:
- [Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateinamen, Erweiterung und Ordnerspeicherort](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a>Einige Punkte, die Sie beachten sollten

Beachten Sie die folgenden wichtigen Punkte:

- Benutzerdefinierte Ausschlüsse haben Vorrang vor automatischen Ausschlüssen.
- Automatische Ausschlüsse gelten nur für die Überprüfung des Echtzeitschutzes (Real-Time Protection, RTP). Automatische Ausschlüsse werden bei einer Vollständig-/Schnell- oder Bei-Bedarf-Überprüfung nicht berücksichtigt.
- Benutzerdefinierte und doppelte Ausschlüsse stehen nicht in Konflikt mit automatischen Ausschlüssen.
- Microsoft Defender Antivirus verwendet die Tools für die Bereitstellungsimagewartung und -verwaltung (Deployment Image Servicing and Management, DISM), um zu bestimmen, welche Rollen auf Ihrem Computer installiert sind.

## <a name="opt-out-of-automatic-exclusions"></a>Abmelden automatischer Ausschlüsse

In Windows Server 2016 und Windows Server 2019 schließen die vordefinierten Ausschlüsse von Security Intelligence-Updates nur die Standardpfade für eine Rolle oder ein Feature aus. Wenn Sie eine Rolle oder ein Feature in einem benutzerdefinierten Pfad installiert haben oder den Satz von Ausschlüssen manuell steuern möchten, müssen Sie die automatischen Ausschlüsse, die in Sicherheitsintelligenzupdates übermittelt werden, abmelden. Beachten Sie jedoch, dass die automatisch zugestellten Ausschlüsse für Windows Server 2016- und 2019-Rollen optimiert sind. Weitere [Informationen finden Sie unter Empfehlungen zum Definieren von Ausschlüssen,](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) bevor Sie Ihre Ausschlusslisten definieren.

> [!WARNING]
> Das Abmelden automatischer Ausschlüsse kann sich negativ auf die Leistung auswirken oder zu Datenbeschädigungen führen. Die automatisch zugestellten Ausschlüsse sind für Windows Server 2016- und Windows Server 2019-Rollen optimiert.

Da vordefinierte Ausschlüsse nur Standardpfade **ausschließen,** müssen Sie, wenn Sie NTDS und SYSVOL auf ein anderes Laufwerk oder einen anderen Pfad *verschieben,* der sich vom ursprünglichen Pfad unterscheiden, mithilfe der hier gezeigten Informationen manuell Ausschlüsse [hinzufügen.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)

Sie können die automatischen Ausschlusslisten mit Gruppenrichtlinien, PowerShell-Cmdlets und WMI deaktivieren.

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Deaktivieren der Liste automatischer Ausschlüsse unter Windows Server 2016 und Windows Server 2019 mithilfe von Gruppenrichtlinien

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)). Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **Bearbeiten**.
2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie dann auf **Administrative Vorlagen**.
3. Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus**  >  **Exclusions**.
4. Doppelklicken Sie **auf Automatische Ausschlüsse deaktivieren,** und legen Sie die Option auf **Aktiviert .** Klicken Sie anschließend auf **OK**. 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a>Verwenden von PowerShell-Cmdlets zum Deaktivieren der Liste automatischer Ausschlüsse unter Windows Server 2016 und 2019

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:

- [Verwenden Sie PowerShell-Cmdlets zum Konfigurieren und Ausführen von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).
- [Verwenden von PowerShell mit Microsoft Defender Antivirus](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Deaktivieren der Liste automatischer Ausschlüsse unter Windows Server 2016 und Windows Server 2019 mithilfe von Windows Management Instruction (WMI)

Verwenden Sie **die Set-Methode** [der MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) für die folgenden Eigenschaften:

```WMI
DisableAutoExclusions
```

Weitere Informationen und zulässige Parameter finden Sie im Folgenden:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a>Liste automatischer Ausschlüsse

Die folgenden Abschnitte enthalten die Ausschlüsse, die mit automatischen Ausschlüssen dateipfade und Dateitypen zugestellt werden.

### <a name="default-exclusions-for-all-roles"></a>Standardausschlüsse für alle Rollen

In diesem Abschnitt werden die Standardausschlüsse für alle Windows Server 2016- und 2019-Rollen aufgeführt.

> [!NOTE]
> Die Standardspeicherorte können sich von den in diesem Artikel aufgeführten Unterscheiden unterscheiden.

#### <a name="windows-tempedb-files"></a>Windows"temp.edb"-Dateien

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a>Windows Update-Dateien oder Automatische Updatedateien

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a>Windows-Sicherheitsdateien

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a>Gruppenrichtliniendateien

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a>WINS-Dateien

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a>Ausschlüsse des Dateireplikationsdiensts (File Replication Service, FRS)

- Dateien im Arbeitsordner des Dateireplikationsdiensts (File Replication Service, FRS). Der Arbeitsordner "FRS" wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- FRS-Datenbankprotokolldateien. Der Ordner "FRS-Datenbankprotokolldatei" wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`

  - `%windir%\Ntfrs\*\Edb\*.log`

- Der FrS-Stagingordner. Der Stagingordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- Der Ordner "FRS preinstall". Dieser Ordner wird durch den Ordner angegeben. `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- Die DfSR-Datenbank (Distributed File System Replication) und arbeitsordner. Diese Ordner werden durch den Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`

  > [!NOTE]
  > Benutzerdefinierte Speicherorte finden Sie [unter Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).

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

#### <a name="process-exclusions"></a>Prozessausschlüsse

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a>Hyper-V-Ausschlüsse

In der folgenden Tabelle sind die Dateitypausschlüsse, Ordnerausschlüsse und Prozessausschlüsse aufgeführt, die bei der Installation der Hyper-V-Rolle automatisch zugestellt werden.

|Dateitypausschlüsse |Ausschlüsse von Ordnern  | Process exclusions |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a>SYSVOL-Dateien

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a>Active Directory-Ausschlüsse

In diesem Abschnitt werden die Ausschlüsse aufgeführt, die bei der Installation von Active Directory-Domänendiensten automatisch zugestellt werden.

#### <a name="ntds-database-files"></a>NTDS-Datenbankdateien

Die Datenbankdateien werden im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a>Die AD DS-Transaktionsprotokolldateien

Die Transaktionsprotokolldateien werden im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a>Der NTDS-Arbeitsordner

Dieser Ordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a>Prozessausschlüsse für AD DS- und AD DS-bezogene Supportdateien

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a>DHCP-Serverausschlüsse

In diesem Abschnitt werden die Ausschlüsse aufgeführt, die bei der Installation der DHCP-Serverrolle automatisch zugestellt werden. Die Speicherorte der DHCP -Server-Datei werden durch die *Parameter DatabasePath,* *DhcpLogFilePath* und *BackupDatabasePath* im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a>DNS-Serverausschlüsse

In diesem Abschnitt werden die Datei- und Ordnerausschlüsse sowie die Prozessausschlüsse aufgeführt, die bei der Installation der DNS-Serverrolle automatisch zugestellt werden.

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a>Datei- und Ordnerausschlüsse für die DNS-Serverrolle

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a>Prozessausschlüsse für die DNS-Serverrolle

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a>Datei- und Speicherdiensteausschlüsse

In diesem Abschnitt werden die Datei- und Ordnerausschlüsse aufgeführt, die bei der Installation der Rolle Datei- und Speicherdienste automatisch zugestellt werden. Die unten aufgeführten Ausschlüsse enthalten keine Ausschlüsse für die Clusterrolle.

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a>Print Server-Ausschlüsse

In diesem Abschnitt werden die Dateitypausschlüsse, Ordnerausschlüsse und Prozessausschlüsse aufgeführt, die bei der Installation der Print Server-Rolle automatisch zugestellt werden.

#### <a name="file-type-exclusions"></a>Dateitypausschlüsse

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a>Ausschlüsse von Ordnern

Dieser Ordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a>Prozessausschlüsse

- `spoolsv.exe`

### <a name="web-server-exclusions"></a>Webserverausschlüsse

In diesem Abschnitt werden die Ordnerausschlüsse und Prozessausschlüsse aufgeführt, die bei der Installation der Webserverrolle automatisch zugestellt werden.

#### <a name="folder-exclusions"></a>Ausschlüsse von Ordnern

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a>Process exclusions

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a>Deaktivieren der Überprüfung von Dateien im Ordner Sysvol\Sysvol oder im Ordner SYSVOL_DFSR\Sysvol

Der aktuelle Speicherort des Oder-Ordners und aller Unterordner ist das `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` Dateisystemreparationsziel des Replikatsatzstamms. Die `Sysvol\Sysvol` Ordner und verwenden standardmäßig die folgenden `SYSVOL_DFSR\Sysvol` Speicherorte:

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

Auf den Pfad zum aktuell aktiven Wird von der NETLOGON-Freigabe verwiesen und kann durch den `SYSVOL` SysVol-Wertnamen im folgenden Unterschlüssel bestimmt werden: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`

Schließen Sie die folgenden Dateien aus diesem Ordner und allen unterordnern aus:

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

### <a name="windows-server-update-services-exclusions"></a>Windows Server Update Services-Ausschlüsse

In diesem Abschnitt werden die Ordnerausschlüsse aufgeführt, die automatisch bei der Installation der Windows Server Update Services (WSUS)-Rolle zugestellt werden. Der Ordner WSUS wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a>Siehe auch

- [Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender Antivirus-Scans](configure-exclusions-microsoft-defender-antivirus.md)
- [Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateinamen, Erweiterung und Ordnerspeicherort](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Häufige Fehler beim Definieren von Ausschlüssen](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus-Scans und -Korrekturen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)