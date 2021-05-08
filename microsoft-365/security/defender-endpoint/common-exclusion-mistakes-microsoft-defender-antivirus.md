---
title: Häufige Fehler, die beim Festlegen von Ausschlüssen vermieden werden sollten
description: Vermeiden Sie häufige Fehler beim Definieren von Ausschlüssen für Microsoft Defender Antivirus Scans.
keywords: Ausschlüsse, Dateien, Erweiterung, Dateityp, Ordnername, Dateiname, Scans
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
ms.openlocfilehash: de739ca3c6a4ab305b575fa7e2f419d044d997a8
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274971"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Häufige Fehler, die beim Festlegen von Ausschlüssen vermieden werden sollten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

Sie können eine Ausschlussliste für Elemente definieren, die nicht von Microsoft Defender Antivirus werden sollen. Solche ausgeschlossenen Elemente können Bedrohungen enthalten, die Ihr Gerät anfällig machen. 

In diesem Artikel werden einige häufige Fehler beschrieben, die Sie beim Definieren von Ausschlüssen vermeiden sollten. 

Informationen zum Definieren von Ausschlusslisten finden Sie [Empfehlungen zum Definieren von Ausschlüssen](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).

## <a name="excluding-certain-trusted-items"></a>Ausschließen bestimmter vertrauenswürdiger Elemente

Bestimmte Dateien, Dateitypen, Ordner oder Prozesse sollten nicht von der Überprüfung ausgeschlossen werden, auch wenn Sie davon aus sind, dass sie nicht schädlich sind. 

Definieren Sie keine Ausschlüsse für die Ordnerstandorte, Dateierweiterungen und Prozesse, die in der folgenden Tabelle aufgeführt sind:

| Ordnerstandorte | Dateierweiterungen | Prozesse |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> `bginfo.exe`[1] <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> `msbuild.exe`[2] <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> Sie können Dateitypen ausschließen, z. B. , , oder wenn Ihre Umgebung über eine moderne, aktuelle Software mit einer strikten Updaterichtlinie verfügt, um Sicherheitsrisiken `.gif` `.jpg` zu `.jpeg` `.png` behandeln.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Verwenden des Dateinamens in der Ausschlussliste

Eine Schadsoftware hat möglicherweise denselben Namen wie die Datei, der Sie vertrauen und von der Überprüfung ausschließen möchten. Um zu verhindern, dass eine potenzielle Schadsoftware von der Überprüfung ausgeschlossen wird, verwenden Sie daher einen vollqualifizierten Pfad zu der Datei, die Sie ausschließen möchten, anstatt nur den Dateinamen zu verwenden. Wenn Sie beispielsweise die Überprüfung ausschließen möchten, verwenden Sie den vollständigen Pfad `Filename.exe` zur Datei, z. B. `C:\program files\contoso\Filename.exe` .

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Verwenden einer einzelnen Ausschlussliste für mehrere Serverarbeitslasten

Verwenden Sie keine einzelne Ausschlussliste, um Ausschlüsse für mehrere Serverworkloads zu definieren. Teilen Sie die Ausschlüsse für verschiedene Anwendungs- oder Dienstarbeitslasten in mehrere Ausschlusslisten auf. Beispielsweise muss sich die Ausschlussliste für Ihre IIS Server-Arbeitsauslastung von der Ausschlussliste für Ihre SQL Server unterscheiden.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Verwenden falscher Umgebungsvariablen als Platzhalter in den Listen für Dateinamen- und Ordnerpfad oder Erweiterungsausschluss

Microsoft Defender Antivirus Der Dienst wird im Systemkontext mit dem LocalSystem-Konto ausgeführt, d. h., er ruft Informationen von der Variablen systemumgebung ab, nicht von der Benutzerumgebungsvariablen. Die Verwendung von Umgebungsvariablen als Platzhalter in Ausschlusslisten ist auf Systemvariablen und auf Prozesse beschränkt, die als NT AUTHORITY\SYSTEM-Konto ausgeführt werden. Verwenden Sie daher keine Benutzerumgebungsvariablen als Platzhalter, wenn Microsoft Defender Antivirus und Prozessausschlüsse hinzufügen. Eine vollständige Liste der Systemumgebungsvariablen [finden](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) Sie in der Tabelle unter Systemumgebungsvariablen.

Informationen zur Verwendung [von Platzhaltern in](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) Ausschlusslisten finden Sie unter Verwenden von Platzhaltern in den Listen für Dateinamen und Ordnerpfad oder Erweiterungsausschluss.

## <a name="related-articles"></a>Verwandte Artikel

- [Konfigurieren und Überprüfen von Ausschlüssen in Microsoft Defender Antivirus Scans](configure-exclusions-microsoft-defender-antivirus.md)
- [Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateierweiterung und Ordnerspeicherort](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurieren Microsoft Defender Antivirus Ausschlüssen auf Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
