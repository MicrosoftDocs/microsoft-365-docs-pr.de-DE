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
# <a name="live-response-command-examples"></a>Kommandobeispiele für Liveantworten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Erfahren Sie mehr über allgemeine Befehle, die in der Liveantwort verwendet werden, und sehen Sie sich Beispiele dazu an, wie sie in der Regel verwendet werden.

Je nachdem, welche Rolle Ihnen zugewiesen wurde, können Sie einfache oder erweiterte Liveantwortbefehle ausführen. Weitere Informationen zu grundlegenden und erweiterten Befehlen finden Sie unter Untersuchen von [Entitäten auf Geräten mit Liveantwort.](live-response.md)

## <a name="analyze"></a>Analysieren

```console
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```console
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a>Verbindungen

```console
# List active connections in json format using parameter name
connections -output json
```

```console
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a>dir

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

## <a name="fileinfo"></a>Fileinfo

```console
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a>Findfile

```console
# Find file by name
findfile test.txt
```

## <a name="getfile"></a>Getfile

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
> Die folgenden Dateitypen **können nicht** mithilfe dieses Befehls aus der Live-Antwort heruntergeladen werden:
>
> - [Analysepunktdateien](/windows/desktop/fileio/reparse-points/)
> - [Spärliche Dateien](/windows/desktop/fileio/sparse-files/)
> - Leere Dateien
> - Virtuelle Dateien oder Dateien, die nicht vollständig lokal vorhanden sind
>
> Diese Dateitypen **werden** von [PowerShell](/powershell/scripting/overview)unterstützt.
>
> Verwenden Sie PowerShell als Alternative, wenn Sie Probleme bei der Verwendung dieses Befehls in Live Response haben.

## <a name="library"></a>Bibliothek

```console
# List files in the library
library
```

```console
# Delete a file from the library
library delete script.ps1
```

## <a name="processes"></a>Prozesse

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

## <a name="putfile"></a>Putfile

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

## <a name="registry"></a>Registrierung

```console
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```console
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a>Beheben

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

## <a name="run"></a>Ausführen

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
> Für lange ausgeführte Befehle wie **"Ausführen"** oder **"Getfile"** empfiehlt es sich, das **&** Symbol " " am Ende des Befehls zu verwenden, um diese Aktion im Hintergrund auszuführen.
> Auf diese Weise können Sie den Computer weiter untersuchen und zum Hintergrundbefehl zurückkehren, wenn Sie mit dem [Einfachbefehl](live-response.md#basic-commands)'**fg**' fertig sind.

## <a name="scheduledtask"></a>scheduledtask

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

## <a name="undo"></a>Rückgängig

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
