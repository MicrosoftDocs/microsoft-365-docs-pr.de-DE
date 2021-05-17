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
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Planen von Scans mit Microsoft Defender for Endpoint unter macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Während Sie eine Bedrohungsscan jederzeit mit Microsoft Defender for Endpoint starten können, kann Ihr Unternehmen von geplanten oder terminierten Scans profitieren. Sie können z. B. eine Überprüfung so planen, dass sie am Anfang jedes Arbeitstags oder jeder Woche ausgeführt wird. 

## <a name="schedule-a-scan-with-launchd"></a>Planen einer Überprüfung mit *dem Start*

Sie können einen Überprüfungszeitplan mit dem *gestarteten Daemon* auf einem macOS-Gerät erstellen.

1. Der folgende Code zeigt das Schema, das Sie zum Planen einer Überprüfung verwenden müssen. Öffnen Sie einen Text-Editor, und verwenden Sie dieses Beispiel als Leitfaden für Ihre eigene geplante Scandatei.

    Weitere Informationen zum hier verwendeten *.plist-Dateiformat* finden Sie unter [Informationen](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) zu Eigenschaftenlistendateien auf der offiziellen Apple-Entwicklerwebsite.

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

2. Speichern Sie die Datei unter *com.microsoft.wdav.schedquickscan.plist*.

    > [!TIP]
    > Wenn Sie einen vollständigen Scan anstelle einer Schnellscan ausführen möchten, ändern Sie Zeile 12, , um die Option anstelle von (d. h. ) zu verwenden und die Datei als `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* anstelle von *com.microsoft.wdav.sched **quick** scan.plist zu speichern.*

3. Öffnen **Sie Terminal**.
4. Geben Sie die folgenden Befehle ein, um die Datei zu laden:

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. Die geplante Überprüfung wird zu dem Datum, der Uhrzeit und der Häufigkeit ausgeführt, die Sie in Ihrer p-Liste definiert haben. Im Beispiel wird die Überprüfung jeden Freitag um 02:00 Uhr ausgeführt. 

    Der Wert von verwendet eine ganze Zahl, um den fünften Tag der Woche oder `Weekday` `StartCalendarInterval` Freitag anzugeben.

 > [!IMPORTANT]
 > Agents, die mit *gestartet ausgeführt* werden, werden nicht zum geplanten Zeitpunkt ausgeführt, während das Gerät im Schlaf ist. Sie werden stattdessen ausgeführt, sobald das Gerät aus dem Ruhezustand fortgesetzt wird.
 >
 > Wenn das Gerät deaktiviert ist, wird die Überprüfung zum nächsten geplanten Scanzeittermin ausgeführt.

## <a name="schedule-a-scan-with-intune"></a>Planen einer Überprüfung mit Intune

Sie können auch Scans mit Microsoft Intune. Das [runMDATPQuickScan.sh,](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) das unter [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) verfügbar ist, bleibt erhalten, wenn das Gerät aus dem Ruhezustand fortgesetzt wird. 

Ausführliche Anweisungen zur Verwendung dieses Skripts in Ihrem Unternehmen finden Sie unter Verwenden von Shellskripts auf [macOS-Geräten](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) in Intune.
