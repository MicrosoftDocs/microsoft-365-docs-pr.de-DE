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
ms.date: 05/17/2021
ms.openlocfilehash: d10343538c995534878196cc57092c37fd2dcf7b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538063"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Häufige Fehler, die beim Festlegen von Ausschlüssen vermieden werden sollten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

Sie können eine Ausschlussliste für Elemente definieren, die nicht von Microsoft Defender Antivirus werden sollen. Solche ausgeschlossenen Elemente können Bedrohungen enthalten, die Ihr Gerät anfällig machen. 

In diesem Artikel werden einige häufige Fehler beschrieben, die Sie beim Definieren von Ausschlüssen vermeiden sollten. 

Informationen zum Definieren von Ausschlusslisten finden Sie [Empfehlungen zum Definieren von Ausschlüssen](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).

## <a name="excluding-certain-trusted-items"></a>Ausschließen bestimmter vertrauenswürdiger Elemente

Bestimmte Dateien, Dateitypen, Ordner oder Prozesse sollten nicht von der Überprüfung ausgeschlossen werden, auch wenn Sie davon aus sind, dass sie nicht schädlich sind. 

Definieren Sie keine Ausschlüsse für die Ordnerstandorte, Dateierweiterungen und Prozesse, die in den folgenden Abschnitten aufgeführt sind:
- Ordnerstandorte
- Dateierweiterungen
- Prozesse

### <a name="folder-locations"></a>Ordnerstandorte

Definieren Sie im Allgemeinen keine Ausschlüsse für die folgenden Ordnerstandorte:

`%systemdrive%` 

`C:`

`C:\`

`C:\*`

`%ProgramFiles%\Java`

`C:\Program Files\Java` 

`%ProgramFiles%\Contoso\` 

`C:\Program Files\Contoso\` 

`%ProgramFiles(x86)%\Contoso\` 

`C:\Program Files (x86)\Contoso\`

`C:\Temp`

`C:\Temp\`

`C:\Temp\*`

`C:\Users\`

`C:\Users\*`

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Beachten Sie die folgende Ausnahme für SharePoint**: Schließen Sie aus, wenn Sie antivirenschutz auf Dateiebene in `C:\Users\ServiceAccount\AppData\Local\Temp` [SharePoint.](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Beachten Sie die folgende Ausnahme für SharePoint**: Schließen Sie aus, wenn Sie antivirenschutz auf Dateiebene in `C:\Users\Default\AppData\Local\Temp` [SharePoint.](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)

`%Windir%\Prefetch`

`C:\Windows\Prefetch`

`C:\Windows\Prefetch\`

`C:\Windows\Prefetch\*`

`%Windir%\System32\Spool`

`C:\Windows\System32\Spool`

`C:\Windows\System32\CatRoot2`
`%Windir%\Temp`

`C:\Windows\Temp`

`C:\Windows\Temp\`

`C:\Windows\Temp\*`

### <a name="file-extensions"></a>Dateierweiterungen

Definieren Sie im Allgemeinen keine Ausschlüsse für die folgenden Dateierweiterungen:

`.7z`

`.bat`

`.bin`

`.cab`

`.cmd`

`.com` 

`.cpl`

`.dll`

`.exe`

`.fla`

`.gif`

`.gz`

`.hta`

`.inf`

`.java`

`.jar`

`.job`

`.jpeg`

`.jpg`

`.js`

`.ko`

`.ko.gz`

`.msi`

`.ocx`

`.png`

`.ps1`

`.py`

`.rar`

`.reg`

`.scr`

`.sys`

`.tar`

`.tmp`

`.url`

`.vbe`

`.vbs`

`.wsf`

`.zip`

### <a name="processes"></a>Prozesse 

Definieren Sie im Allgemeinen keine Ausschlüsse für die folgenden Prozesse:

`AcroRd32.exe`  

`bitsadmin.exe`  

`excel.exe`  

`iexplore.exe`  

`java.exe`  

`outlook.exe`  

`psexec.exe`  

`powerpnt.exe`  

`powershell.exe`  

`schtasks.exe`

`svchost.exe` 

`wmic.exe`  

`winword.exe`  

`wuauclt.exe`  

`addinprocess.exe`  

`addinprocess32.exe`  

`addinutil.exe`  

`bash.exe`  

`bginfo.exe` 

`cdb.exe`  

`csi.exe`  

`dbghost.exe`  

`dbgsvc.exe`  

`dnx.exe`  

`fsi.exe`  

`fsiAnyCpu.exe`  

`kd.exe`  

`ntkd.exe`  

`lxssmanager.dll`  

`msbuild.exe` 

`mshta.exe`  

`ntsd.exe`  

`rcsi.exe`  

`system.management.automation.dll`  

`windbg.exe`

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
