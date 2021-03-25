---
title: Beispiele für Liveantwortbefehle
description: Erfahren Sie, wie Sie einfache oder erweiterte Liveantwortbefehle für Microsoft Defender for Endpoint ausführen, und sehen Sie sich Beispiele zur Verwendung an.
keywords: beispiel, befehl, cli, remote, shell, connection, live, response, real-time, command, script, remediate, hunt, export, log, drop, download, file
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
ms.openlocfilehash: b25712e331597dc38d3f1cf98fdf70886406432e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066904"
---
# <a name="live-response-command-examples"></a><span data-ttu-id="cde01-104">Beispiele für Liveantwortbefehle</span><span class="sxs-lookup"><span data-stu-id="cde01-104">Live response command examples</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cde01-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cde01-105">**Applies to:**</span></span>
- [<span data-ttu-id="cde01-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cde01-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="cde01-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cde01-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cde01-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="cde01-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cde01-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cde01-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="cde01-110">Erfahren Sie mehr über allgemeine Befehle, die in der Liveantwort verwendet werden, und sehen Sie sich Beispiele dafür an, wie sie in der Regel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cde01-110">Learn about common commands used in live response and see examples on how they are typically used.</span></span>

<span data-ttu-id="cde01-111">Je nachdem, welche Rolle Ihnen gewährt wurde, können Sie einfache oder erweiterte Liveantwortbefehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="cde01-111">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="cde01-112">Weitere Informationen zu einfachen und erweiterten Befehlen finden Sie unter [Investigate entities on devices using live response](live-response.md).</span><span class="sxs-lookup"><span data-stu-id="cde01-112">For more information on basic and advanced commands, see [Investigate entities on devices using live response](live-response.md).</span></span>


## <a name="analyze"></a><span data-ttu-id="cde01-113">analyze</span><span class="sxs-lookup"><span data-stu-id="cde01-113">analyze</span></span> 

```
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a><span data-ttu-id="cde01-114">connections</span><span class="sxs-lookup"><span data-stu-id="cde01-114">connections</span></span>

```
# List active connections in json format using parameter name
connections -output json
```

```
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a><span data-ttu-id="cde01-115">dir</span><span class="sxs-lookup"><span data-stu-id="cde01-115">dir</span></span>

```
# List files and sub-folders in the current folder
dir
```

```
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a><span data-ttu-id="cde01-116">fileinfo</span><span class="sxs-lookup"><span data-stu-id="cde01-116">fileinfo</span></span>

```
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a><span data-ttu-id="cde01-117">findfile</span><span class="sxs-lookup"><span data-stu-id="cde01-117">findfile</span></span>

```
# Find file by name
findfile test.txt
```

## <a name="getfile"></a><span data-ttu-id="cde01-118">getfile</span><span class="sxs-lookup"><span data-stu-id="cde01-118">getfile</span></span>

```
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> <span data-ttu-id="cde01-119">Die folgenden Dateitypen **können nicht** mithilfe dieses Befehls aus Live Response heruntergeladen werden:</span><span class="sxs-lookup"><span data-stu-id="cde01-119">The following file types **cannot** be downloaded using this command from within Live Response:</span></span>
>
> * [<span data-ttu-id="cde01-120">Reparse point files</span><span class="sxs-lookup"><span data-stu-id="cde01-120">Reparse point files</span></span>](/windows/desktop/fileio/reparse-points/)
> * [<span data-ttu-id="cde01-121">Spärige Dateien</span><span class="sxs-lookup"><span data-stu-id="cde01-121">Sparse files</span></span>](/windows/desktop/fileio/sparse-files/)
> * <span data-ttu-id="cde01-122">Leere Dateien</span><span class="sxs-lookup"><span data-stu-id="cde01-122">Empty files</span></span>
> * <span data-ttu-id="cde01-123">Virtuelle Dateien oder Dateien, die lokal nicht vollständig vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="cde01-123">Virtual files, or files that are not fully present locally</span></span>
>
> <span data-ttu-id="cde01-124">Diese Dateitypen **werden** von [PowerShell unterstützt.](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="cde01-124">These file types **are** supported by [PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true).</span></span>
>
> <span data-ttu-id="cde01-125">Verwenden Sie PowerShell als Alternative, wenn Sie Probleme bei der Verwendung dieses Befehls in Live Response haben.</span><span class="sxs-lookup"><span data-stu-id="cde01-125">Use PowerShell as an alternative, if you have problems using this command from within Live Response.</span></span>

## <a name="processes"></a><span data-ttu-id="cde01-126">Prozesse</span><span class="sxs-lookup"><span data-stu-id="cde01-126">processes</span></span>
```
# Show all processes
processes
```

```
# Get process by pid
processes 123
```

```
# Get process by pid with argument name
processes -pid 123
```

```
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a><span data-ttu-id="cde01-127">putfile</span><span class="sxs-lookup"><span data-stu-id="cde01-127">putfile</span></span>

```
# Upload file from library
putfile get-process-by-name.ps1
```

```
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a><span data-ttu-id="cde01-128">Registrierung</span><span class="sxs-lookup"><span data-stu-id="cde01-128">registry</span></span>

```
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a><span data-ttu-id="cde01-129">remediate</span><span class="sxs-lookup"><span data-stu-id="cde01-129">remediate</span></span>

```
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```
# Remediate process with specific PID
remediate process 7960
```

```
# See list of all remediated entities
remediate list
```

## <a name="run"></a><span data-ttu-id="cde01-130">run</span><span class="sxs-lookup"><span data-stu-id="cde01-130">run</span></span>

```
# Run PowerShell script from the library without arguments
run script.ps1
```

```
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```

## <a name="scheduledtask"></a><span data-ttu-id="cde01-131">scheduledtask</span><span class="sxs-lookup"><span data-stu-id="cde01-131">scheduledtask</span></span>

```
# Get all scheduled tasks
scheduledtasks
```

```
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```


## <a name="undo"></a><span data-ttu-id="cde01-132">Rückgängig machen</span><span class="sxs-lookup"><span data-stu-id="cde01-132">undo</span></span>

```
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```

