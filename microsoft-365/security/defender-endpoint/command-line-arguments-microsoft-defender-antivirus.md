---
title: Verwalten von Microsoft Defender Antivirus mithilfe der Befehlszeile
description: Führen Sie Microsoft Defender Antivirus-Scans aus, und konfigurieren Sie den Schutz der nächsten Generation mit einem dedizierten Befehlszeilenprogramm.
keywords: Ausführen der Windows Defender-Überprüfung, Ausführen der Antivirenscan über die Befehlszeile, Ausführen der Windows Defender-Überprüfung über die Befehlszeile, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 1b357f7c1e02211f3949383a380666cb7444f814
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764627"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="7c568-104">Konfigurieren und Verwalten von Microsoft Defender Antivirus mit mpcmdrun.exe Befehlszeilentool</span><span class="sxs-lookup"><span data-stu-id="7c568-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7c568-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7c568-105">**Applies to:**</span></span>

- [<span data-ttu-id="7c568-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7c568-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="7c568-107">Sie können verschiedene Microsoft Defender Antivirus-Funktionen mit dem dedizierten Befehlszeilentool **mpcmdrun.exe.**</span><span class="sxs-lookup"><span data-stu-id="7c568-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="7c568-108">Dieses Hilfsprogramm ist hilfreich, wenn Sie die Verwendung von Microsoft Defender Antivirus automatisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7c568-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="7c568-109">Das Hilfsprogramm finden Sie unter `%ProgramFiles%\Windows Defender\MpCmdRun.exe` .</span><span class="sxs-lookup"><span data-stu-id="7c568-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="7c568-110">Sie müssen ihn über eine Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="7c568-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="7c568-111">Möglicherweise müssen Sie eine Administratorversion der Eingabeaufforderung öffnen.</span><span class="sxs-lookup"><span data-stu-id="7c568-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="7c568-112">Wenn Sie im Menü **Start** nach Eingabeaufforderung suchen, wählen Sie **Als Administrator ausführen aus.**</span><span class="sxs-lookup"><span data-stu-id="7c568-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="7c568-113">Wenn Sie eine aktualisierte Microsoft Defender Platform-Version ausführen, führen Sie sie `**MpCmdRun**` an folgendem Speicherort aus: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .</span><span class="sxs-lookup"><span data-stu-id="7c568-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

<span data-ttu-id="7c568-114">Das Hilfsprogramm verfügt über die folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="7c568-114">The utility has the following commands:</span></span>

```console
MpCmdRun.exe [command] [-options]
```
<span data-ttu-id="7c568-115">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7c568-115">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="7c568-116">Befehl</span><span class="sxs-lookup"><span data-stu-id="7c568-116">Command</span></span>  | <span data-ttu-id="7c568-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c568-117">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="7c568-118">`-?` **oder** `-h`</span><span class="sxs-lookup"><span data-stu-id="7c568-118">`-?` **or** `-h`</span></span>   | <span data-ttu-id="7c568-119">Zeigt alle verfügbaren Optionen für dieses Tool an.</span><span class="sxs-lookup"><span data-stu-id="7c568-119">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="7c568-120">Sucht nach schadhafter Software.</span><span class="sxs-lookup"><span data-stu-id="7c568-120">Scans for malicious software.</span></span> <span data-ttu-id="7c568-121">Die Werte für **ScanType** lauten: **0** Standard, je nach Konfiguration, **-1** Schnellscan, **-2** Vollständiger Scan, **-3** Benutzerdefinierter Datei- und Verzeichnisscan.</span><span class="sxs-lookup"><span data-stu-id="7c568-121">Values for **ScanType** are: **0** Default, according to your configuration, **-1** Quick scan, **-2** Full scan, **-3** File and directory custom scan.</span></span>  <span data-ttu-id="7c568-122">CpuThrottling berücksichtigt die konfigurierte CPU-Einschränkung aus der Richtlinie</span><span class="sxs-lookup"><span data-stu-id="7c568-122">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="7c568-123">Startet die Diagnoseablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="7c568-123">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="7c568-124">Sammelt Supportinformationen.</span><span class="sxs-lookup"><span data-stu-id="7c568-124">Collects support information.</span></span> <span data-ttu-id="7c568-125">Siehe '[Sammeln von Diagnosedaten](collect-diagnostic-data.md)'</span><span class="sxs-lookup"><span data-stu-id="7c568-125">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="7c568-126">Identisch mit `-GetFiles` , aber Ausgaben in temporären DiagTrack-Ordner</span><span class="sxs-lookup"><span data-stu-id="7c568-126">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="7c568-127">Stellt die installierte Sicherheitsintelligenz in einer früheren Sicherungskopie oder im ursprünglichen Standardsatz wieder her.</span><span class="sxs-lookup"><span data-stu-id="7c568-127">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="7c568-128">Entfernt nur die dynamisch heruntergeladene Sicherheitsintelligenz</span><span class="sxs-lookup"><span data-stu-id="7c568-128">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="7c568-129">Wiederherstellung des vorherigen installierten Moduls</span><span class="sxs-lookup"><span data-stu-id="7c568-129">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="7c568-130">Sucht nach neuen Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="7c568-130">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="7c568-131">Wiederherstellen oder Auflisten isolierter Elemente</span><span class="sxs-lookup"><span data-stu-id="7c568-131">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="7c568-132">Lädt dynamische Sicherheitsintelligenz</span><span class="sxs-lookup"><span data-stu-id="7c568-132">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="7c568-133">Listet die geladene dynamische Sicherheitsintelligenz auf.</span><span class="sxs-lookup"><span data-stu-id="7c568-133">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="7c568-134">Entfernt dynamische Sicherheitsintelligenz</span><span class="sxs-lookup"><span data-stu-id="7c568-134">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="7c568-135">Überprüft, ob ein Pfad ausgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="7c568-135">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="7c568-136">Überprüft, ob Ihr Netzwerk mit dem Microsoft Defender Antivirus-Clouddienst kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="7c568-136">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="7c568-137">Dieser Befehl funktioniert nur unter Windows 10, Version 1703 oder höher.</span><span class="sxs-lookup"><span data-stu-id="7c568-137">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="7c568-138">Häufige Fehler beim Ausführen von Befehlen mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="7c568-138">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="7c568-139">Fehlermeldung</span><span class="sxs-lookup"><span data-stu-id="7c568-139">Error message</span></span> | <span data-ttu-id="7c568-140">Möglicher Grund</span><span class="sxs-lookup"><span data-stu-id="7c568-140">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="7c568-141">Der Microsoft Defender Antivirus-Dienst ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7c568-141">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="7c568-142">Aktivieren Sie den Dienst, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="7c568-142">Enable the service and try again.</span></span> <br>   <span data-ttu-id="7c568-143">**Hinweis:**  In Windows 10 1909 oder älter und Windows Server 2019 oder älter wurde der Dienst früher als "Windows Defender Antivirus" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7c568-143">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called "Windows Defender Antivirus" service.</span></span>|
| `0x80070667` | <span data-ttu-id="7c568-144">Sie ausführen den Befehl von einem Computer, der `-ValidateMapsConnection` Windows 10, Version 1607 oder älter, oder Windows Server 2016 oder älter ist.</span><span class="sxs-lookup"><span data-stu-id="7c568-144">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="7c568-145">Führen Sie den Befehl von einem Computer aus, der Windows 10, Version 1703 oder neuer, oder Windows Server 2019 oder neuer ist.</span><span class="sxs-lookup"><span data-stu-id="7c568-145">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="7c568-146">Das Tool muss entweder ausgeführt werden: oder (wobei sich möglicherweise unterscheiden, da Plattformupdates monatlich `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` sind, außer im März)</span><span class="sxs-lookup"><span data-stu-id="7c568-146">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="7c568-147">Zu wenig Rechte.</span><span class="sxs-lookup"><span data-stu-id="7c568-147">Not enough privileges.</span></span> <span data-ttu-id="7c568-148">Verwenden Sie die Eingabeaufforderung (cmd.exe) als Administrator.</span><span class="sxs-lookup"><span data-stu-id="7c568-148">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="7c568-149">Die Firewall blockiert die Verbindung oder führt eine SSL-Überprüfung durch.</span><span class="sxs-lookup"><span data-stu-id="7c568-149">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="7c568-150">Mögliche netzwerkbezogene Probleme, wie Probleme bei der Namensauflösung</span><span class="sxs-lookup"><span data-stu-id="7c568-150">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="7c568-151">Die Firewall blockiert die Verbindung oder führt eine SSL-Überprüfung durch.</span><span class="sxs-lookup"><span data-stu-id="7c568-151">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="7c568-152">Die Firewall blockiert die Verbindung oder führt eine SSL-Überprüfung durch.</span><span class="sxs-lookup"><span data-stu-id="7c568-152">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="7c568-153">Die Firewall blockiert die Verbindung oder führt eine SSL-Überprüfung durch.</span><span class="sxs-lookup"><span data-stu-id="7c568-153">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7c568-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c568-154">See also</span></span>

- [<span data-ttu-id="7c568-155">Konfigurieren von Microsoft Defender Antivirus-Features</span><span class="sxs-lookup"><span data-stu-id="7c568-155">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="7c568-156">Verwalten von Microsoft Defender Antivirus in Ihrem Unternehmen</span><span class="sxs-lookup"><span data-stu-id="7c568-156">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7c568-157">Referenzthemen für Verwaltungs- und Konfigurationstools</span><span class="sxs-lookup"><span data-stu-id="7c568-157">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7c568-158">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="7c568-158">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)