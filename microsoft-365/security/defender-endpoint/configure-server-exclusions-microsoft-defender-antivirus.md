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
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a>Konfigurieren Microsoft Defender Antivirus Ausschlüsse auf Windows Server


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus auf Windows Server 2016 und Windows Server 2019 registriert Sie automatisch bei bestimmten Ausschlüssen, wie von der angegebenen Serverrolle definiert. Diese Ausschlüsse werden nicht in den standardmäßigen Ausschlusslisten angezeigt, die in der [Windows-Sicherheit App](microsoft-defender-security-center-antivirus.md)angezeigt werden.

> [!NOTE]
> Automatische Ausschlüsse gelten nur für RTP-Scans (Real-Time Protection). Automatische Ausschlüsse werden während einer Vollständig-/Schnell- oder Bedarfsüberprüfung nicht berücksichtigt.

Zusätzlich zu automatischen Ausschlüssen, die durch die Serverrolle definiert sind, können Sie benutzerdefinierte Ausschlüsse hinzufügen oder entfernen. Lesen Sie dazu die folgenden Artikel:
- [Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateiname, Erweiterung und Ordnerspeicherort](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a>Ein paar Punkte, die Sie beachten sollten

Beachten Sie die folgenden wichtigen Punkte:

- Benutzerdefinierte Ausschlüsse haben Vorrang vor automatischen Ausschlüssen.
- Automatische Ausschlüsse gelten nur für RTP-Scans (Real-Time Protection). Automatische Ausschlüsse werden während einer Vollständig-/Schnell- oder Bedarfsüberprüfung nicht berücksichtigt.
- Benutzerdefinierte und doppelte Ausschlüsse führen nicht zu Konflikten mit automatischen Ausschlüssen.
- Microsoft Defender Antivirus ermittelt mithilfe der DISM-Tools (Deployment Image Servicing and Management), welche Rollen auf Ihrem Computer installiert sind.

## <a name="opt-out-of-automatic-exclusions"></a>Abmelden von automatischen Ausschlüssen

In Windows Server 2016 und Windows Server 2019 schließen die vordefinierten Ausschlüsse, die von Sicherheitsupdates bereitgestellt werden, nur die Standardpfade für eine Rolle oder ein Feature aus. Wenn Sie eine Rolle oder ein Feature in einem benutzerdefinierten Pfad installiert haben oder den Satz von Ausschlüssen manuell steuern möchten, stellen Sie sicher, dass Sie die automatischen Ausschlüsse, die in Security Intelligence-Updates bereitgestellt werden, deaktivieren. Beachten Sie jedoch, dass die automatisch übermittelten Ausschlüsse für Windows Server 2016 und 2019-Rollen optimiert sind. Informationen zum [Definieren von Ausschlüssen](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) finden Sie unter Empfehlungen, bevor Sie Ihre Ausschlusslisten definieren.

> [!WARNING]
> Das Deaktivieren automatischer Ausschlüsse kann sich negativ auf die Leistung auswirken oder zu einer Datenbeschädigung führen. Die automatisch übermittelten Ausschlüsse sind für Windows Server 2016- und Windows Server 2019-Rollen optimiert.

Da vordefinierte Ausschlüsse **standardpfade** nur ausschließen, müssen Sie, wenn Sie NTDS und SYSVOL auf ein anderes Laufwerk oder einen anderen Pfad verschieben, *der vom ursprünglichen Pfad abweicht,* ausschlüsse manuell mithilfe der hier [aufgeführten](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) Informationen hinzufügen.

Sie können die automatischen Ausschlusslisten mit Gruppenrichtlinien, PowerShell-Cmdlets und WMI deaktivieren.

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Verwenden von Gruppenrichtlinien zum Deaktivieren der Liste der automatischen Ausschlüsse auf Windows Server 2016 und Windows Server 2019

1. Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)). Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **"Bearbeiten".**
2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und klicken Sie dann auf **"Administrative Vorlagen".**
3. Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Ausschlüssen.**
4. Doppelklicken Sie auf **"Automatische Ausschlüsse deaktivieren",** und legen Sie die Option auf **"Aktiviert"** fest. Klicken Sie anschließend auf **OK**. 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a>Verwenden von PowerShell-Cmdlets zum Deaktivieren der Liste der automatischen Ausschlüsse in Windows Server 2016 und 2019

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:

- [Verwenden Sie PowerShell-Cmdlets, um Microsoft Defender Antivirus zu konfigurieren und auszuführen.](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Verwenden Sie PowerShell mit Microsoft Defender Antivirus](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Verwenden Windows Management Instruction (WMI) zum Deaktivieren der Liste der automatischen Ausschlüsse auf Windows Server 2016 und Windows Server 2019

Verwenden Sie die **Set-Methode** der [MSFT_MpPreference-Klasse](/previous-versions/windows/desktop/defender/msft-mppreference) für die folgenden Eigenschaften:

```WMI
DisableAutoExclusions
```

Weitere Informationen und zulässige Parameter finden Sie in den folgenden Themen:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a>Liste der automatischen Ausschlüsse

Die folgenden Abschnitte enthalten die Ausschlüsse, die mit automatischen Ausschlüssen von Dateipfaden und Dateitypen bereitgestellt werden.

### <a name="default-exclusions-for-all-roles"></a>Standardausschlüsse für alle Rollen

In diesem Abschnitt werden die Standardausschlüsse für alle Rollen Windows Server 2016 und 2019 aufgeführt.

> [!NOTE]
> Die Standardspeicherorte können sich von den in diesem Artikel aufgeführten Speicherorten unterscheiden.

#### <a name="windows-tempedb-files"></a>Windows "temp.edb"-Dateien

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a>Windows Aktualisieren von Dateien oder Dateien mit automatischer Aktualisierung

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a>Windows-Sicherheit-Dateien

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

#### <a name="file-replication-service-frs-exclusions"></a>Dateireplikationsdienstausschlüsse (File Replication Service, FRS)

- Dateien im Arbeitsordner des Dateireplikationsdiensts (File Replication Service, FRS). Der FRS-Arbeitsordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- FRS-Datenbankprotokolldateien. Der Frs-Datenbankprotokollordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`

  - `%windir%\Ntfrs\*\Edb\*.log`

- Der FRS-Stagingordner. Der Stagingordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- Der FRS-Vorinstallationsordner. Dieser Ordner wird vom Ordner angegeben. `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- Die DFSR-Datenbank (Distributed File System Replication) und Arbeitsordner. Diese Ordner werden durch den Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`

  > [!NOTE]
  > Informationen zu benutzerdefinierten Speicherorten finden Sie unter ["Automatische Ausschlüsse deaktivieren".](#opt-out-of-automatic-exclusions)

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

In der folgenden Tabelle sind die Dateitypausschlüsse, Ordnerausschlüsse und Prozessausschlüsse aufgeführt, die bei der Installation der Hyper-V-Rolle automatisch übermittelt werden.

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

In diesem Abschnitt werden die Ausschlüsse aufgeführt, die bei der Installation von Active Directory Domain Services automatisch übermittelt werden.

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

In diesem Abschnitt werden die Ausschlüsse aufgeführt, die bei der Installation der DHCP-Serverrolle automatisch übermittelt werden. Die Speicherorte der DHCP-Serverdateien werden durch die Parameter *DatabasePath,* *DhcpLogFilePath* und *BackupDatabasePath* im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a>DNS-Serverausschlüsse

In diesem Abschnitt werden die Datei- und Ordnerausschlüsse sowie die Prozessausschlüsse aufgeführt, die automatisch übermittelt werden, wenn Sie die DNS-Serverrolle installieren.

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a>Datei- und Ordnerausschlüsse für die DNS-Serverrolle

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a>Prozessausschlüsse für die DNS-Serverrolle

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a>Datei- und Storage dienstausschlüsse

In diesem Abschnitt werden die Datei- und Ordnerausschlüsse aufgeführt, die automatisch übermittelt werden, wenn Sie die Rolle "Datei" und "Storage Dienste" installieren. Die unten aufgeführten Ausschlüsse enthalten keine Ausschlüsse für die Clusterrolle.

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a>Druckserverausschlüsse

In diesem Abschnitt werden die Dateitypausschlüsse, Ordnerausschlüsse und Prozessausschlüsse aufgeführt, die automatisch übermittelt werden, wenn Sie die Rolle "Druckserver" installieren.

#### <a name="file-type-exclusions"></a>Dateitypausschlüsse

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a>Ausschlüsse von Ordnern

Dieser Ordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a>Prozessausschlüsse

- `spoolsv.exe`

### <a name="web-server-exclusions"></a>Webserverausschlüsse

In diesem Abschnitt werden die Ordnerausschlüsse und Prozessausschlüsse aufgeführt, die automatisch übermittelt werden, wenn Sie die Webserverrolle installieren.

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

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a>Deaktivieren der Überprüfung von Dateien im Ordner "Sysvol\Sysvol" oder im Ordner "SYSVOL_DFSR\Sysvol"

Der aktuelle Speicherort des `Sysvol\Sysvol` Ordners oder `SYSVOL_DFSR\Sysvol` ordners und alle Unterordner ist das Dateisystem-Analyseziel des Stamms der Replikatgruppe. Die `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` Ordner und Ordner verwenden standardmäßig die folgenden Speicherorte:

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

Der Pfad zu der aktuell aktiven `SYSVOL` Wird von der NETLOGON-Freigabe referenziert und kann durch den SysVol-Wertnamen im folgenden Unterschlüssel bestimmt werden: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`

Schließen Sie die folgenden Dateien aus diesem Ordner und allen unteren Ordnern aus:

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

### <a name="windows-server-update-services-exclusions"></a>Windows Server Update Services Ausschlüsse

In diesem Abschnitt werden die Ordnerausschlüsse aufgeführt, die automatisch übermittelt werden, wenn Sie die Rolle Windows Server Update Services (WSUS) installieren. Der WSUS-Ordner wird im Registrierungsschlüssel angegeben. `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a>Siehe auch

- [Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender Antivirus Scans](configure-exclusions-microsoft-defender-antivirus.md)
- [Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateiname, Erweiterung und Ordnerspeicherort](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Häufige Fehler, die beim Festlegen von Ausschlüssen vermieden werden sollten](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus Überprüfungen und Korrekturen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
