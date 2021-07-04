---
title: Kommandobeispiele für Liveantworten
description: Erfahren Sie, wie Sie grundlegende oder erweiterte Liveantwortbefehle für Microsoft Defender für Endpunkt ausführen und Beispiele zur Verwendung anzeigen.
keywords: 'Beispiel: Befehl, Cli, Remote, Shell, Verbindung, Live, Antwort, Echtzeit, Befehl, Skript, korrigieren, suchen, exportieren, protokollieren, ablegen, herunterladen, Datei'
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 82052634b79bf433731d0afdab45e3d75e6497e0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289331"
---
# <a name="live-response-command-examples"></a><span data-ttu-id="72ae6-104">Kommandobeispiele für Liveantworten</span><span class="sxs-lookup"><span data-stu-id="72ae6-104">Live response command examples</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="72ae6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="72ae6-105">**Applies to:**</span></span>
- [<span data-ttu-id="72ae6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="72ae6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="72ae6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72ae6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="72ae6-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="72ae6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="72ae6-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="72ae6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="72ae6-110">Erfahren Sie mehr über allgemeine Befehle, die in der Liveantwort verwendet werden, und sehen Sie sich Beispiele dazu an, wie sie in der Regel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72ae6-110">Learn about common commands used in live response and see examples on how they are typically used.</span></span>

<span data-ttu-id="72ae6-111">Je nachdem, welche Rolle Ihnen zugewiesen wurde, können Sie einfache oder erweiterte Liveantwortbefehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="72ae6-111">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="72ae6-112">Weitere Informationen zu grundlegenden und erweiterten Befehlen finden Sie unter Untersuchen von [Entitäten auf Geräten mit Liveantwort.](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="72ae6-112">For more information on basic and advanced commands, see [Investigate entities on devices using live response](live-response.md).</span></span>

## <a name="analyze"></a><span data-ttu-id="72ae6-113">Analysieren</span><span class="sxs-lookup"><span data-stu-id="72ae6-113">analyze</span></span>

```console
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```console
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a><span data-ttu-id="72ae6-114">Verbindungen</span><span class="sxs-lookup"><span data-stu-id="72ae6-114">connections</span></span>

```console
# List active connections in json format using parameter name
connections -output json
```

```console
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a><span data-ttu-id="72ae6-115">dir</span><span class="sxs-lookup"><span data-stu-id="72ae6-115">dir</span></span>

```console
# List files and sub-folders in the current folder
dir
```

```console
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```console
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a><span data-ttu-id="72ae6-116">Fileinfo</span><span class="sxs-lookup"><span data-stu-id="72ae6-116">fileinfo</span></span>

```console
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a><span data-ttu-id="72ae6-117">Findfile</span><span class="sxs-lookup"><span data-stu-id="72ae6-117">findfile</span></span>

```console
# Find file by name
findfile test.txt
```

## <a name="getfile"></a><span data-ttu-id="72ae6-118">Getfile</span><span class="sxs-lookup"><span data-stu-id="72ae6-118">getfile</span></span>

```console
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```console
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> <span data-ttu-id="72ae6-119">Die folgenden Dateitypen **können nicht** mithilfe dieses Befehls aus der Live-Antwort heruntergeladen werden:</span><span class="sxs-lookup"><span data-stu-id="72ae6-119">The following file types **cannot** be downloaded using this command from within Live Response:</span></span>
>
> - [<span data-ttu-id="72ae6-120">Analysepunktdateien</span><span class="sxs-lookup"><span data-stu-id="72ae6-120">Reparse point files</span></span>](/windows/desktop/fileio/reparse-points/)
> - [<span data-ttu-id="72ae6-121">Spärliche Dateien</span><span class="sxs-lookup"><span data-stu-id="72ae6-121">Sparse files</span></span>](/windows/desktop/fileio/sparse-files/)
> - <span data-ttu-id="72ae6-122">Leere Dateien</span><span class="sxs-lookup"><span data-stu-id="72ae6-122">Empty files</span></span>
> - <span data-ttu-id="72ae6-123">Virtuelle Dateien oder Dateien, die nicht vollständig lokal vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="72ae6-123">Virtual files, or files that are not fully present locally</span></span>
>
> <span data-ttu-id="72ae6-124">Diese Dateitypen **werden** von [PowerShell](/powershell/scripting/overview)unterstützt.</span><span class="sxs-lookup"><span data-stu-id="72ae6-124">These file types **are** supported by [PowerShell](/powershell/scripting/overview).</span></span>
>
> <span data-ttu-id="72ae6-125">Verwenden Sie PowerShell als Alternative, wenn Sie Probleme bei der Verwendung dieses Befehls in Live Response haben.</span><span class="sxs-lookup"><span data-stu-id="72ae6-125">Use PowerShell as an alternative, if you have problems using this command from within Live Response.</span></span>

## <a name="library"></a><span data-ttu-id="72ae6-126">Bibliothek</span><span class="sxs-lookup"><span data-stu-id="72ae6-126">library</span></span>

```console
# List files in the library
library
```

```console
# Delete a file from the library
library delete script.ps1
```

## <a name="processes"></a><span data-ttu-id="72ae6-127">Prozesse</span><span class="sxs-lookup"><span data-stu-id="72ae6-127">processes</span></span>

```console
# Show all processes
processes
```

```console
# Get process by pid
processes 123
```

```console
# Get process by pid with argument name
processes -pid 123
```

```console
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a><span data-ttu-id="72ae6-128">Putfile</span><span class="sxs-lookup"><span data-stu-id="72ae6-128">putfile</span></span>

```console
# Upload file from library
putfile get-process-by-name.ps1
```

```console
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```console
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a><span data-ttu-id="72ae6-129">Registrierung</span><span class="sxs-lookup"><span data-stu-id="72ae6-129">registry</span></span>

```console
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```console
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a><span data-ttu-id="72ae6-130">Beheben</span><span class="sxs-lookup"><span data-stu-id="72ae6-130">remediate</span></span>

```console
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```console
# Remediate process with specific PID
remediate process 7960
```

```console
# See list of all remediated entities
remediate list
```

## <a name="run"></a><span data-ttu-id="72ae6-131">Ausführen</span><span class="sxs-lookup"><span data-stu-id="72ae6-131">run</span></span>

```console
# Run PowerShell script from the library without arguments
run script.ps1
```

```console
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```

>[!NOTE]
>
> <span data-ttu-id="72ae6-132">Für lange ausgeführte Befehle wie **"Ausführen"** oder **"Getfile"** empfiehlt es sich, das **&** Symbol " " am Ende des Befehls zu verwenden, um diese Aktion im Hintergrund auszuführen.</span><span class="sxs-lookup"><span data-stu-id="72ae6-132">For long running commands such as '**run**' or '**getfile**', you may want to use the '**&**' symbol at the end of the command to perform that action in the background.</span></span>
> <span data-ttu-id="72ae6-133">Auf diese Weise können Sie den Computer weiter untersuchen und zum Hintergrundbefehl zurückkehren, wenn Sie mit dem [Einfachbefehl](live-response.md#basic-commands)'**fg**' fertig sind.</span><span class="sxs-lookup"><span data-stu-id="72ae6-133">This will allow you to continue investigating the machine and return to the background command when done using '**fg**' [basic command](live-response.md#basic-commands).</span></span>

## <a name="scheduledtask"></a><span data-ttu-id="72ae6-134">scheduledtask</span><span class="sxs-lookup"><span data-stu-id="72ae6-134">scheduledtask</span></span>

```console
# Get all scheduled tasks
scheduledtasks
```

```console
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```

## <a name="undo"></a><span data-ttu-id="72ae6-135">Rückgängig</span><span class="sxs-lookup"><span data-stu-id="72ae6-135">undo</span></span>

```console
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```console
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```
