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
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Planen von Scans mit Microsoft Defender für Endpunkt unter macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Sie können zwar jederzeit einen Bedrohungsscan mit Microsoft Defender für Endpunkt starten, Ihr Unternehmen kann jedoch von geplanten oder zeitlich festgelegten Scans profitieren. Sie können z. B. planen, dass eine Überprüfung am Anfang jedes Arbeitstags oder jeder Woche ausgeführt wird. 

## <a name="schedule-a-scan-with-launchd"></a>Planen einer Überprüfung mit *gestarteter*

Sie können einen Überprüfungszeitplan mit dem *gestarteten* Daemon auf einem macOS-Gerät erstellen.

1. Der folgende Code zeigt das Schema, das Sie zum Planen einer Überprüfung verwenden müssen. Öffnen Sie einen Text-Editor, und verwenden Sie dieses Beispiel als Leitfaden für Ihre eigene geplante Scandatei.

    Weitere Informationen zum hier verwendeten *PLIST-Dateiformat* finden Sie unter ["Informationen zu Eigenschaftenlistendateien"](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) auf der offiziellen Apple-Entwicklerwebsite.

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

2. Speichern Sie die Datei als *com.microsoft.wdav.schedquickscan.plist*.

    > [!TIP]
    > Um einen vollständigen Scan anstelle eines Schnellscans auszuführen, ändern Sie Zeile 12, `<string>/usr/local/bin/mdatp scan quick</string>` um die Option anstelle (d. h. ) zu verwenden und die Datei als `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* anstelle von *com.microsoft.wdav.sched **quick** scan.plist zu* speichern.

3. Öffnen Sie **Terminal**.
4. Geben Sie die folgenden Befehle ein, um die Datei zu laden:

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. Die geplante Überprüfung wird zu Datum, Uhrzeit und Häufigkeit ausgeführt, die Sie in Ihrer p-Liste definiert haben. In diesem Beispiel wird die Überprüfung jeden Freitag um 02:00 Uhr ausgeführt. 

    Der `Weekday` Wert von verwendet eine ganze `StartCalendarInterval` Zahl, um den fünften Tag der Woche oder Freitag anzugeben.

 > [!IMPORTANT]
 > Agents, die mit *gestarteten* Agents ausgeführt werden, werden nicht zum geplanten Zeitpunkt ausgeführt, während das Gerät eingelummert ist. Sie werden stattdessen ausgeführt, sobald das Gerät aus dem Standbymodus fortgesetzt wird.
 >
 > Wenn das Gerät deaktiviert ist, wird die Überprüfung zum nächsten geplanten Scanzeitpunkt ausgeführt.

## <a name="schedule-a-scan-with-intune"></a>Planen einer Überprüfung mit Intune

Sie können Scans auch mit Microsoft Intune planen. Das unter ["Skripts für Microsoft Defender für Endpunkt"](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) verfügbare [shell-Skript](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) runMDATPQuickScan.sh wird beibehalten, wenn das Gerät aus dem Standbymodus fortgesetzt wird. 

Ausführlichere Anweisungen zur Verwendung dieses Skripts in Ihrem Unternehmen finden Sie unter Verwenden von [Shellskripts auf macOS-Geräten in Intune.](/mem/intune/apps/macos-shell-scripts)
