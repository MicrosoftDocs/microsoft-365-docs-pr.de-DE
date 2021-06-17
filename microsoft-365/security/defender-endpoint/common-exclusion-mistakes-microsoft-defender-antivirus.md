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
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="71b2e-104">Häufige Fehler, die beim Festlegen von Ausschlüssen vermieden werden sollten</span><span class="sxs-lookup"><span data-stu-id="71b2e-104">Common mistakes to avoid when defining exclusions</span></span>

<span data-ttu-id="71b2e-105">Sie können eine Ausschlussliste für Elemente definieren, die Microsoft Defender Antivirus nicht überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="71b2e-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="71b2e-106">Solche ausgeschlossenen Elemente können Bedrohungen enthalten, die Ihr Gerät anfällig machen.</span><span class="sxs-lookup"><span data-stu-id="71b2e-106">Such excluded items could contain threats that make your device vulnerable.</span></span> <span data-ttu-id="71b2e-107">In diesem Artikel werden einige häufige Fehler beschrieben, die Sie beim Definieren von Ausschlüssen vermeiden sollten.</span><span class="sxs-lookup"><span data-stu-id="71b2e-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="71b2e-108">Bevor Sie Ihre Ausschlusslisten definieren, finden Sie unter Empfehlungen Informationen [zum Definieren von Ausschlüssen.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)</span><span class="sxs-lookup"><span data-stu-id="71b2e-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="71b2e-109">Ausschließen bestimmter vertrauenswürdiger Elemente</span><span class="sxs-lookup"><span data-stu-id="71b2e-109">Excluding certain trusted items</span></span>

<span data-ttu-id="71b2e-110">Bestimmte Dateien, Dateitypen, Ordner oder Prozesse sollten nicht von der Überprüfung ausgeschlossen werden, obwohl Sie ihnen vertrauen, dass sie nicht bösartig sind.</span><span class="sxs-lookup"><span data-stu-id="71b2e-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="71b2e-111">Definieren Sie keine Ausschlüsse für die Ordnerspeicherorte, Dateierweiterungen und Prozesse, die in den folgenden Abschnitten aufgeführt sind:</span><span class="sxs-lookup"><span data-stu-id="71b2e-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following sections:</span></span>
- <span data-ttu-id="71b2e-112">Ordnerspeicherorte</span><span class="sxs-lookup"><span data-stu-id="71b2e-112">Folder locations</span></span>
- <span data-ttu-id="71b2e-113">Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="71b2e-113">File extensions</span></span>
- <span data-ttu-id="71b2e-114">Prozesse</span><span class="sxs-lookup"><span data-stu-id="71b2e-114">Processes</span></span>

### <a name="folder-locations"></a><span data-ttu-id="71b2e-115">Ordnerspeicherorte</span><span class="sxs-lookup"><span data-stu-id="71b2e-115">Folder locations</span></span>

<span data-ttu-id="71b2e-116">Definieren Sie im Allgemeinen keine Ausschlüsse für die folgenden Ordnerspeicherorte:</span><span class="sxs-lookup"><span data-stu-id="71b2e-116">In general, do not define exclusions for the following folder locations:</span></span>

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

<span data-ttu-id="71b2e-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Beachten Sie die folgende Ausnahme für SharePoint:** Schließen Sie dies `C:\Users\ServiceAccount\AppData\Local\Temp` aus, wenn Sie [den Virenschutz auf Dateiebene in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)verwenden.</span><span class="sxs-lookup"><span data-stu-id="71b2e-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\ServiceAccount\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

<span data-ttu-id="71b2e-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Beachten Sie die folgende Ausnahme für SharePoint:** Schließen Sie dies `C:\Users\Default\AppData\Local\Temp` aus, wenn Sie [den Virenschutz auf Dateiebene in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)verwenden.</span><span class="sxs-lookup"><span data-stu-id="71b2e-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\Default\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

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

### <a name="file-extensions"></a><span data-ttu-id="71b2e-119">Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="71b2e-119">File extensions</span></span>

<span data-ttu-id="71b2e-120">Definieren Sie im Allgemeinen keine Ausschlüsse für die folgenden Dateierweiterungen:</span><span class="sxs-lookup"><span data-stu-id="71b2e-120">In general, do not define exclusions for the following file extensions:</span></span>

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

### <a name="processes"></a><span data-ttu-id="71b2e-121">Prozesse</span><span class="sxs-lookup"><span data-stu-id="71b2e-121">Processes</span></span> 

<span data-ttu-id="71b2e-122">Definieren Sie im Allgemeinen keine Ausschlüsse für die folgenden Prozesse:</span><span class="sxs-lookup"><span data-stu-id="71b2e-122">In general, do not define exclusions for the following processes:</span></span>

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
> <span data-ttu-id="71b2e-123">Sie können Dateitypen ausschließen, z. B. `.gif` , oder wenn Ihre Umgebung über eine `.jpg` `.jpeg` `.png` moderne, aktuelle Software mit einer strengen Updaterichtlinie zur Behandlung von Sicherheitsrisiken verfügt.</span><span class="sxs-lookup"><span data-stu-id="71b2e-123">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="71b2e-124">Verwenden des Dateinamens in der Ausschlussliste</span><span class="sxs-lookup"><span data-stu-id="71b2e-124">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="71b2e-125">Eine Schadsoftware hat möglicherweise denselben Namen wie die Datei, der Sie vertrauen und die von der Überprüfung ausgeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="71b2e-125">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="71b2e-126">Um potenzielle Schadsoftware nicht von der Überprüfung auszuschließen, verwenden Sie daher einen vollqualifizierten Pfad zu der Datei, die Sie ausschließen möchten, anstatt nur den Dateinamen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="71b2e-126">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="71b2e-127">Wenn Sie beispielsweise die Überprüfung ausschließen `Filename.exe` möchten, verwenden Sie den vollständigen Pfad zur Datei, `C:\program files\contoso\Filename.exe` z. B. .</span><span class="sxs-lookup"><span data-stu-id="71b2e-127">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="71b2e-128">Verwenden einer einzelnen Ausschlussliste für mehrere Serverworkloads</span><span class="sxs-lookup"><span data-stu-id="71b2e-128">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="71b2e-129">Verwenden Sie keine einzige Ausschlussliste, um Ausschlüsse für mehrere Serverworkloads zu definieren.</span><span class="sxs-lookup"><span data-stu-id="71b2e-129">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="71b2e-130">Teilen Sie die Ausschlüsse für unterschiedliche Anwendungs- oder Dienstarbeitslasten in mehrere Ausschlusslisten auf.</span><span class="sxs-lookup"><span data-stu-id="71b2e-130">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="71b2e-131">Beispielsweise muss sich die Ausschlussliste für Ihre IIS Server-Workload von der Ausschlussliste für Ihre SQL Server Workload unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="71b2e-131">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="71b2e-132">Verwenden falscher Umgebungsvariablen als Platzhalter in den Dateinamen- und Ordnerpfad- oder Erweiterungsausschlusslisten</span><span class="sxs-lookup"><span data-stu-id="71b2e-132">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="71b2e-133">Microsoft Defender Antivirus Der Dienst wird im Systemkontext mithilfe des LocalSystem-Kontos ausgeführt, was bedeutet, dass informationen von der Systemumgebungsvariablen und nicht von der Benutzerumgebungsvariablen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="71b2e-133">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="71b2e-134">Die Verwendung von Umgebungsvariablen als Platzhalter in Ausschlusslisten ist auf Systemvariablen und auf Prozesse beschränkt, die als NT AUTHORITY\SYSTEM-Konto ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="71b2e-134">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="71b2e-135">Verwenden Sie daher beim Hinzufügen von Microsoft Defender Antivirus Ordner- und Prozessausschlüssen keine Benutzerumgebungsvariablen als Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="71b2e-135">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="71b2e-136">Eine vollständige Liste der Systemumgebungsvariablen finden Sie in der Tabelle unter ["Systemumgebungsvariablen".](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables)</span><span class="sxs-lookup"><span data-stu-id="71b2e-136">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="71b2e-137">Informationen zur Verwendung von Platzhaltern in Ausschlusslisten finden Sie unter [Verwenden von Platzhaltern in Dateinamen- und Ordnerpfad- oder Erweiterungsausschlusslisten.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="71b2e-137">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

