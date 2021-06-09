---
title: Planen von Scans mit Microsoft Defender für Endpunkt unter macOS
description: Erfahren Sie, wie Sie eine automatische Überprüfungszeit für Microsoft Defender für Endpunkt in macOS planen, um die Ressourcen Ihrer Organisation besser zu schützen.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Mac, Scans, Antivirus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a93ea3427c72eb5529715b92cb18d01462493cc6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842854"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="ccfd2-104">Planen von Scans mit Microsoft Defender für Endpunkt unter macOS</span><span class="sxs-lookup"><span data-stu-id="ccfd2-104">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ccfd2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ccfd2-105">**Applies to:**</span></span>
- [<span data-ttu-id="ccfd2-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ccfd2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ccfd2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ccfd2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ccfd2-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="ccfd2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ccfd2-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="ccfd2-110">Sie können zwar jederzeit einen Bedrohungsscan mit Microsoft Defender für Endpunkt starten, Ihr Unternehmen kann jedoch von geplanten oder zeitlich festgelegten Scans profitieren.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-110">While you can start a threat scan at any time with Microsoft Defender for Endpoint, your enterprise might benefit from scheduled or timed scans.</span></span> <span data-ttu-id="ccfd2-111">Sie können z. B. planen, dass eine Überprüfung am Anfang jedes Arbeitstags oder jeder Woche ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-111">For example, you can schedule a scan to run at the beginning of every workday or week.</span></span> 

## <a name="schedule-a-scan-with-launchd"></a><span data-ttu-id="ccfd2-112">Planen einer Überprüfung mit *gestarteter*</span><span class="sxs-lookup"><span data-stu-id="ccfd2-112">Schedule a scan with *launchd*</span></span>

<span data-ttu-id="ccfd2-113">Sie können einen Überprüfungszeitplan mit dem *gestarteten* Daemon auf einem macOS-Gerät erstellen.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-113">You can create a scanning schedule using the *launchd* daemon on a macOS device.</span></span>

1. <span data-ttu-id="ccfd2-114">Der folgende Code zeigt das Schema, das Sie zum Planen einer Überprüfung verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-114">The following code shows the schema you need to use to schedule a scan.</span></span> <span data-ttu-id="ccfd2-115">Öffnen Sie einen Text-Editor, und verwenden Sie dieses Beispiel als Leitfaden für Ihre eigene geplante Scandatei.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-115">Open a text editor and use this example as a guide for your own scheduled scan file.</span></span>

    <span data-ttu-id="ccfd2-116">Weitere Informationen zum hier verwendeten *PLIST-Dateiformat* finden Sie unter ["Informationen zu Eigenschaftenlistendateien"](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) auf der offiziellen Apple-Entwicklerwebsite.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-116">For more information on the *.plist* file format used here, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) at the official Apple developer website.</span></span>

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. <span data-ttu-id="ccfd2-117">Speichern Sie die Datei als *com.microsoft.wdav.schedquickscan.plist*.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-117">Save the file as *com.microsoft.wdav.schedquickscan.plist*.</span></span>

    > [!TIP]
    > <span data-ttu-id="ccfd2-118">Um einen vollständigen Scan anstelle eines Schnellscans auszuführen, ändern Sie Zeile 12, `<string>/usr/local/bin/mdatp scan quick</string>` um die Option anstelle (d. h. ) zu verwenden und die Datei als `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* anstelle von *com.microsoft.wdav.sched **quick** scan.plist zu* speichern.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-118">To run a full scan instead of a quick scan, change line 12, `<string>/usr/local/bin/mdatp scan quick</string>`, to use the `full` option instead of `quick` (i.e. `<string>/usr/local/bin/mdatp scan full</string>`) and save the file as *com.microsoft.wdav.sched **full** scan.plist* instead of *com.microsoft.wdav.sched **quick** scan.plist*.</span></span>

3. <span data-ttu-id="ccfd2-119">Öffnen Sie **Terminal**.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-119">Open **Terminal**.</span></span>
4. <span data-ttu-id="ccfd2-120">Geben Sie die folgenden Befehle ein, um die Datei zu laden:</span><span class="sxs-lookup"><span data-stu-id="ccfd2-120">Enter the following commands to load your file:</span></span>

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. <span data-ttu-id="ccfd2-121">Die geplante Überprüfung wird zu Datum, Uhrzeit und Häufigkeit ausgeführt, die Sie in Ihrer p-Liste definiert haben.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-121">Your scheduled scan will run at the date, time, and frequency you defined in your p-list.</span></span> <span data-ttu-id="ccfd2-122">In diesem Beispiel wird die Überprüfung jeden Freitag um 02:00 Uhr ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-122">In the example, the scan runs at 2:00 AM every Friday.</span></span> 

    <span data-ttu-id="ccfd2-123">Der `Weekday` Wert von verwendet eine ganze `StartCalendarInterval` Zahl, um den fünften Tag der Woche oder Freitag anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-123">The `Weekday` value of `StartCalendarInterval` uses an integer to indicate the fifth day of the week, or Friday.</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="ccfd2-124">Agents, die mit *gestarteten* Agents ausgeführt werden, werden nicht zum geplanten Zeitpunkt ausgeführt, während das Gerät eingelummert ist.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-124">Agents executed with *launchd* will not run at the scheduled time while the device is asleep.</span></span> <span data-ttu-id="ccfd2-125">Sie werden stattdessen ausgeführt, sobald das Gerät aus dem Standbymodus fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-125">They will instead run once the device resumes from sleep mode.</span></span>
 >
 > <span data-ttu-id="ccfd2-126">Wenn das Gerät deaktiviert ist, wird die Überprüfung zum nächsten geplanten Scanzeitpunkt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-126">If the device is turned off, the scan will run at the next scheduled scan time.</span></span>

## <a name="schedule-a-scan-with-intune"></a><span data-ttu-id="ccfd2-127">Planen einer Überprüfung mit Intune</span><span class="sxs-lookup"><span data-stu-id="ccfd2-127">Schedule a scan with Intune</span></span>

<span data-ttu-id="ccfd2-128">Sie können Scans auch mit Microsoft Intune planen.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-128">You can also schedule scans with Microsoft Intune.</span></span> <span data-ttu-id="ccfd2-129">Das unter ["Skripts für Microsoft Defender für Endpunkt"](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) verfügbare [shell-Skript](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) runMDATPQuickScan.sh wird beibehalten, wenn das Gerät aus dem Standbymodus fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="ccfd2-129">The [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell script available at [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) will persist when the device resumes from sleep mode.</span></span> 

<span data-ttu-id="ccfd2-130">Ausführlichere Anweisungen zur Verwendung dieses Skripts in Ihrem Unternehmen finden Sie unter Verwenden von [Shellskripts auf macOS-Geräten in Intune.](/mem/intune/apps/macos-shell-scripts)</span><span class="sxs-lookup"><span data-stu-id="ccfd2-130">See [Use shell scripts on macOS devices in Intune](/mem/intune/apps/macos-shell-scripts) for more detailed instructions on how to use this script in your enterprise.</span></span>
