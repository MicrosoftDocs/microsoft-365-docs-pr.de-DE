---
title: Planen von Scans mit Microsoft Defender for Endpoint unter macOS
description: Erfahren Sie, wie Sie eine automatische Überprüfungszeit für Microsoft Defender for Endpoint in macOS planen, um die Ressourcen Ihrer Organisation besser zu schützen.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, scans, antivirus
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
ms.openlocfilehash: 2c1dc16dc3fbb61a77e1d7348d47fdfd778c56e2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934513"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="392fd-104">Planen von Scans mit Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="392fd-104">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="392fd-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="392fd-105">**Applies to:**</span></span>
- [<span data-ttu-id="392fd-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="392fd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="392fd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="392fd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="392fd-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="392fd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="392fd-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="392fd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="392fd-110">Während Sie eine Bedrohungsscan jederzeit mit Microsoft Defender for Endpoint starten können, kann Ihr Unternehmen von geplanten oder terminierten Scans profitieren.</span><span class="sxs-lookup"><span data-stu-id="392fd-110">While you can start a threat scan at any time with Microsoft Defender for Endpoint, your enterprise might benefit from scheduled or timed scans.</span></span> <span data-ttu-id="392fd-111">Sie können z. B. eine Überprüfung so planen, dass sie am Anfang jedes Arbeitstags oder jeder Woche ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="392fd-111">For example, you can schedule a scan to run at the beginning of every workday or week.</span></span> 

## <a name="schedule-a-scan-with-launchd"></a><span data-ttu-id="392fd-112">Planen einer Überprüfung mit *dem Start*</span><span class="sxs-lookup"><span data-stu-id="392fd-112">Schedule a scan with *launchd*</span></span>

<span data-ttu-id="392fd-113">Sie können einen Überprüfungszeitplan mit dem *gestarteten Daemon* auf einem macOS-Gerät erstellen.</span><span class="sxs-lookup"><span data-stu-id="392fd-113">You can create a scanning schedule using the *launchd* daemon on a macOS device.</span></span>

1. <span data-ttu-id="392fd-114">Der folgende Code zeigt das Schema, das Sie zum Planen einer Überprüfung verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="392fd-114">The following code shows the schema you need to use to schedule a scan.</span></span> <span data-ttu-id="392fd-115">Öffnen Sie einen Text-Editor, und verwenden Sie dieses Beispiel als Leitfaden für Ihre eigene geplante Scandatei.</span><span class="sxs-lookup"><span data-stu-id="392fd-115">Open a text editor and use this example as a guide for your own scheduled scan file.</span></span>

    <span data-ttu-id="392fd-116">Weitere Informationen zum hier verwendeten *.plist-Dateiformat* finden Sie unter [Informationen](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) zu Eigenschaftenlistendateien auf der offiziellen Apple-Entwicklerwebsite.</span><span class="sxs-lookup"><span data-stu-id="392fd-116">For more information on the *.plist* file format used here, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) at the official Apple developer website.</span></span>

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

2. <span data-ttu-id="392fd-117">Speichern Sie die Datei unter *com.microsoft.wdav.schedquickscan.plist*.</span><span class="sxs-lookup"><span data-stu-id="392fd-117">Save the file as *com.microsoft.wdav.schedquickscan.plist*.</span></span>

    > [!TIP]
    > <span data-ttu-id="392fd-118">Wenn Sie einen vollständigen Scan anstelle einer Schnellscan ausführen möchten, ändern Sie Zeile 12, , um die Option anstelle von (d. h. ) zu verwenden und die Datei als `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* anstelle von *com.microsoft.wdav.sched **quick** scan.plist zu speichern.*</span><span class="sxs-lookup"><span data-stu-id="392fd-118">To run a full scan instead of a quick scan, change line 12, `<string>/usr/local/bin/mdatp scan quick</string>`, to use the `full` option instead of `quick` (i.e. `<string>/usr/local/bin/mdatp scan full</string>`) and save the file as *com.microsoft.wdav.sched **full** scan.plist* instead of *com.microsoft.wdav.sched **quick** scan.plist*.</span></span>

3. <span data-ttu-id="392fd-119">Öffnen **Sie Terminal**.</span><span class="sxs-lookup"><span data-stu-id="392fd-119">Open **Terminal**.</span></span>
4. <span data-ttu-id="392fd-120">Geben Sie die folgenden Befehle ein, um die Datei zu laden:</span><span class="sxs-lookup"><span data-stu-id="392fd-120">Enter the following commands to load your file:</span></span>

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. <span data-ttu-id="392fd-121">Die geplante Überprüfung wird zu dem Datum, der Uhrzeit und der Häufigkeit ausgeführt, die Sie in Ihrer p-Liste definiert haben.</span><span class="sxs-lookup"><span data-stu-id="392fd-121">Your scheduled scan will run at the date, time, and frequency you defined in your p-list.</span></span> <span data-ttu-id="392fd-122">Im Beispiel wird die Überprüfung jeden Freitag um 02:00 Uhr ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="392fd-122">In the example, the scan runs at 2:00 AM every Friday.</span></span> 

    <span data-ttu-id="392fd-123">Der Wert von verwendet eine ganze Zahl, um den fünften Tag der Woche oder `Weekday` `StartCalendarInterval` Freitag anzugeben.</span><span class="sxs-lookup"><span data-stu-id="392fd-123">The `Weekday` value of `StartCalendarInterval` uses an integer to indicate the fifth day of the week, or Friday.</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="392fd-124">Agents, die mit *gestartet ausgeführt* werden, werden nicht zum geplanten Zeitpunkt ausgeführt, während das Gerät im Schlaf ist.</span><span class="sxs-lookup"><span data-stu-id="392fd-124">Agents executed with *launchd* will not run at the scheduled time while the device is asleep.</span></span> <span data-ttu-id="392fd-125">Sie werden stattdessen ausgeführt, sobald das Gerät aus dem Ruhezustand fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="392fd-125">They will instead run once the device resumes from sleep mode.</span></span>
 >
 > <span data-ttu-id="392fd-126">Wenn das Gerät deaktiviert ist, wird die Überprüfung zum nächsten geplanten Scanzeittermin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="392fd-126">If the device is turned off, the scan will run at the next scheduled scan time.</span></span>

## <a name="schedule-a-scan-with-intune"></a><span data-ttu-id="392fd-127">Planen einer Überprüfung mit Intune</span><span class="sxs-lookup"><span data-stu-id="392fd-127">Schedule a scan with Intune</span></span>

<span data-ttu-id="392fd-128">Sie können Scans auch mit Microsoft Intune planen.</span><span class="sxs-lookup"><span data-stu-id="392fd-128">You can also schedule scans with Microsoft Intune.</span></span> <span data-ttu-id="392fd-129">Das [runMDATPQuickScan.sh,](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) das unter [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) verfügbar ist, bleibt erhalten, wenn das Gerät aus dem Ruhezustand fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="392fd-129">The [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell script available at [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) will persist when the device resumes from sleep mode.</span></span> 

<span data-ttu-id="392fd-130">Ausführliche Anweisungen zur Verwendung dieses Skripts in Ihrem Unternehmen finden Sie unter Verwenden von Shellskripts auf [macOS-Geräten](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) in Intune.</span><span class="sxs-lookup"><span data-stu-id="392fd-130">See [Use shell scripts on macOS devices in Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) for more detailed instructions on how to use this script in your enterprise.</span></span>
