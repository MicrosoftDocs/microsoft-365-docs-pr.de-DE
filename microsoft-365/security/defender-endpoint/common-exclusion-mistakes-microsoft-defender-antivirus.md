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
ms.date: 06/15/2021
ms.openlocfilehash: f9ca83fcfba4b79898a0fed527e38947a4c230d6
ms.sourcegitcommit: 959c3c3633e40b7b0f5e2c8372409778005a24db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52950131"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Häufige Fehler, die beim Festlegen von Ausschlüssen vermieden werden sollten

Sie können eine Ausschlussliste für Elemente definieren, die Microsoft Defender Antivirus nicht überprüfen möchten. Solche ausgeschlossenen Elemente können Bedrohungen enthalten, die Ihr Gerät anfällig machen. In diesem Artikel werden einige häufige Fehler beschrieben, die Sie beim Definieren von Ausschlüssen vermeiden sollten. 

Bevor Sie Ihre Ausschlusslisten definieren, finden Sie unter Empfehlungen Informationen [zum Definieren von Ausschlüssen.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)

## <a name="excluding-certain-trusted-items"></a>Ausschließen bestimmter vertrauenswürdiger Elemente

Bestimmte Dateien, Dateitypen, Ordner oder Prozesse sollten nicht von der Überprüfung ausgeschlossen werden, obwohl Sie ihnen vertrauen, dass sie nicht bösartig sind. 

Definieren Sie keine Ausschlüsse für die Ordnerspeicherorte, Dateierweiterungen und Prozesse, die in den folgenden Abschnitten aufgeführt sind:
- Ordnerspeicherorte
- Dateierweiterungen
- Prozesse

### <a name="folder-locations"></a>Ordnerspeicherorte

Definieren Sie im Allgemeinen keine Ausschlüsse für die folgenden Ordnerspeicherorte:

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

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Beachten Sie die folgende Ausnahme für SharePoint:** Schließen Sie dies `C:\Users\ServiceAccount\AppData\Local\Temp` aus, wenn Sie [den Virenschutz auf Dateiebene in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)verwenden.

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Beachten Sie die folgende Ausnahme für SharePoint:** Schließen Sie dies `C:\Users\Default\AppData\Local\Temp` aus, wenn Sie [den Virenschutz auf Dateiebene in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)verwenden.

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

`dotnet.exe`

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
> Sie können Dateitypen ausschließen, z. B. `.gif` , oder wenn Ihre Umgebung über eine `.jpg` `.jpeg` `.png` moderne, aktuelle Software mit einer strengen Updaterichtlinie zur Behandlung von Sicherheitsrisiken verfügt.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Verwenden des Dateinamens in der Ausschlussliste

Eine Schadsoftware hat möglicherweise denselben Namen wie die Datei, der Sie vertrauen und die von der Überprüfung ausgeschlossen werden soll. Um potenzielle Schadsoftware nicht von der Überprüfung auszuschließen, verwenden Sie daher einen vollqualifizierten Pfad zu der Datei, die Sie ausschließen möchten, anstatt nur den Dateinamen zu verwenden. Wenn Sie beispielsweise die Überprüfung ausschließen `Filename.exe` möchten, verwenden Sie den vollständigen Pfad zur Datei, `C:\program files\contoso\Filename.exe` z. B. .

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Verwenden einer einzelnen Ausschlussliste für mehrere Serverworkloads

Verwenden Sie keine einzige Ausschlussliste, um Ausschlüsse für mehrere Serverworkloads zu definieren. Teilen Sie die Ausschlüsse für unterschiedliche Anwendungs- oder Dienstarbeitslasten in mehrere Ausschlusslisten auf. Beispielsweise muss sich die Ausschlussliste für Ihre IIS Server-Workload von der Ausschlussliste für Ihre SQL Server Workload unterscheiden.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Verwenden falscher Umgebungsvariablen als Platzhalter in den Dateinamen- und Ordnerpfad- oder Erweiterungsausschlusslisten

Microsoft Defender Antivirus Der Dienst wird im Systemkontext mithilfe des LocalSystem-Kontos ausgeführt, was bedeutet, dass informationen von der Systemumgebungsvariablen und nicht von der Benutzerumgebungsvariablen abgerufen werden. Die Verwendung von Umgebungsvariablen als Platzhalter in Ausschlusslisten ist auf Systemvariablen und auf Prozesse beschränkt, die als NT AUTHORITY\SYSTEM-Konto ausgeführt werden. Verwenden Sie daher beim Hinzufügen von Microsoft Defender Antivirus Ordner- und Prozessausschlüssen keine Benutzerumgebungsvariablen als Platzhalter. Eine vollständige Liste der Systemumgebungsvariablen finden Sie in der Tabelle unter ["Systemumgebungsvariablen".](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables)

Informationen zur Verwendung von Platzhaltern in Ausschlusslisten finden Sie unter [Verwenden von Platzhaltern in Dateinamen- und Ordnerpfad- oder Erweiterungsausschlusslisten.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

