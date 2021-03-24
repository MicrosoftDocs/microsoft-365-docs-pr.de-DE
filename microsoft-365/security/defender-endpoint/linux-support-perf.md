---
title: Beheben von Leistungsproblemen für Microsoft Defender ATP für Linux
description: Behandeln von Leistungsproblemen in Microsoft Defender ATP für Linux.
keywords: microsoft, defender, atp, linux, performance
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
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5c64d16e0753fa87713f2a34583825234fb9c98c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062487"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-linux"></a>Behandeln von Leistungsproblemen für Microsoft Defender for Endpoint für Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Dieser Artikel enthält einige allgemeine Schritte, die verwendet werden können, um Leistungsprobleme im Zusammenhang mit Defender for Endpoint für Linux zu einenten.

Der Echtzeitschutz (Real-Time Protection, RTP) ist ein Feature von Defender for Endpoint für Linux, das Ihr Gerät kontinuierlich überwacht und vor Bedrohungen schützt. Es besteht aus Datei- und Prozessüberwachung und anderen Heuristiken.

Abhängig von den ausgeführten Anwendungen und den Gerätemerkmalen kann es bei der Ausführung von Defender for Endpoint für Linux zu einer suboptimalen Leistung kommen. Insbesondere Anwendungen oder Systemprozesse, die über einen kurzen Zeitraum auf viele Ressourcen zugreifen, können zu Leistungsproblemen in Defender for Endpoint für Linux führen.

Stellen Sie vor dem Start sicher, dass andere Sicherheitsprodukte derzeit **nicht auf dem Gerät ausgeführt werden.** Mehrere Sicherheitsprodukte können Konflikte und Auswirkungen auf die Hostleistung haben.

Die folgenden Schritte können verwendet werden, um diese Probleme zu beheben und zu beheben:

1. Deaktivieren Sie den Echtzeitschutz mithilfe einer der folgenden Methoden, und beobachten Sie, ob sich die Leistung verbessert. Dieser Ansatz trägt dazu bei, die Leistungsprobleme von Defender for Endpoint für Linux zu eind nen.

    Wenn Ihr Gerät nicht von Ihrer Organisation verwaltet wird, kann der Echtzeitschutz über die Befehlszeile deaktiviert werden:

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    Wenn Ihr Gerät von Ihrer Organisation verwaltet wird, kann der Echtzeitschutz von Ihrem Administrator mithilfe der Anweisungen unter Festlegen von Einstellungen für [Defender for Endpoint für Linux deaktiviert werden.](linux-preferences.md)

    Wenn das Leistungsproblem weiterhin besteht, während der Echtzeitschutz deaktiviert ist, könnte der Ursprung des Problems die Endpunkterkennungs- und Reaktionskomponente sein. In diesem Fall wenden Sie sich an den Kundensupport, um weitere Anweisungen und Gegenmaßnahmen zu erhalten.

2. Um die Anwendungen zu finden, die die meisten Scans auslösen, können Sie von Defender for Endpoint für Linux gesammelte Echtzeitstatistiken verwenden.

    > [!NOTE]
    > Dieses Feature ist in Version 100.90.70 oder neuer verfügbar.

    Dieses Feature ist standardmäßig auf den `Dogfood` Kanälen und `InsiderFast` aktiviert. Wenn Sie einen anderen Updatekanal verwenden, kann dieses Feature über die Befehlszeile aktiviert werden:
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    Dieses Feature erfordert die Aktivierung des Echtzeitschutzes. Führen Sie den folgenden Befehl aus, um den Status des Echtzeitschutzes zu überprüfen:

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    Stellen Sie sicher, `real_time_protection_enabled` dass der Eintrag ist `true` . Führen Sie andernfalls den folgenden Befehl aus, um ihn zu aktivieren:

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    Führen Sie zum Erfassen aktueller Statistiken aus:

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > Die ```--output json``` Verwendung (beachten Sie den doppelten Strich) stellt sicher, dass das Ausgabeformat für die Analyse bereit ist.

    In der Ausgabe dieses Befehls werden alle Prozesse und die zugehörigen Scanaktivitäten angezeigt.

3. Laden Sie auf Ihrem Linux-System den Beispiel-Python-Parser **high_cpu_parser.py** mit dem Befehl herunter:

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    Die Ausgabe dieses Befehls sollte der folgenden ähneln:

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. Geben Sie als Nächstes die folgenden Befehle ein:

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      Die Ausgabe der oben genannten Ist eine Liste der größten Mitwirkenden bei Leistungsproblemen. Die erste Spalte ist die Prozess-ID (PID), die zweite Spalte ist te Prozessname, und die letzte Spalte ist die Anzahl der gescannten Dateien, sortiert nach Auswirkung.
    Die Ausgabe des Befehls ist z. B. wie folgt: 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool     1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd    407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    Um die Leistung von Defender for Endpoint für Linux zu verbessern, suchen Sie den Server mit der höchsten Anzahl unter der Zeile, und fügen Sie einen Ausschluss `Total files scanned` hinzu. Weitere Informationen finden Sie unter [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).

    >[!NOTE]
    > Die Anwendung speichert Statistiken im Arbeitsspeicher und verfolgt nur die Dateiaktivität, seit sie gestartet wurde und der Echtzeitschutz aktiviert wurde. Prozesse, die vor oder während Zeiträumen gestartet wurden, in denen der Echtzeitschutz deaktiviert war, werden nicht gezählt. Darüber hinaus werden nur Ereignisse gezählt, die Scans ausgelöst haben.

5. Konfigurieren Sie Microsoft Defender ATP für Linux mit Ausschlüssen für die Prozesse oder Datenträgerspeicherorte, die zu Leistungsproblemen beitragen, und aktivieren Sie den Echtzeitschutz erneut.

    Weitere Informationen finden Sie unter [Configure and validate exclusions for Microsoft Defender ATP for Linux](linux-exclusions.md).
