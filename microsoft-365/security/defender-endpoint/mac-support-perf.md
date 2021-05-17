---
title: Behandeln von Leistungsproblemen für Microsoft Defender for Endpoint unter macOS
description: Behandeln von Leistungsproblemen in Microsoft Defender for Endpoint unter macOS.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, performance
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
ms.openlocfilehash: 623717e7b1a3149dbccf07d32200820a7f9083cb
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934249"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Behandeln von Leistungsproblemen für Microsoft Defender for Endpoint unter macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt unter Mac OS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Dieses Thema enthält einige allgemeine Schritte, mit deren Unterstützung Leistungsprobleme im Zusammenhang mit Microsoft Defender for Endpoint auf macOS eindr werden können.

Der Echtzeitschutz (Real-Time Protection, RTP) ist ein Feature von Microsoft Defender for Endpoint unter macOS, das Ihr Gerät kontinuierlich überwacht und vor Bedrohungen schützt. Es besteht aus Datei- und Prozessüberwachung und anderen Heuristiken.

Je nach den ausgeführten Anwendungen und den Gerätemerkmalen kann es bei der Ausführung von Microsoft Defender for Endpoint unter macOS zu einer suboptimalen Leistung führen. Insbesondere Anwendungen oder Systemprozesse, die über einen kurzen Zeitraum auf viele Ressourcen zugreifen, können zu Leistungsproblemen in Microsoft Defender for Endpoint auf macOS führen.

Die folgenden Schritte können verwendet werden, um diese Probleme zu beheben und zu beheben:

1. Deaktivieren Sie den Echtzeitschutz mithilfe einer der folgenden Methoden, und beobachten Sie, ob sich die Leistung verbessert. Dieser Ansatz hilft, die Leistungsprobleme von Microsoft Defender for Endpoint auf macOS zu verengt.

      Wenn Ihr Gerät nicht von Ihrer Organisation verwaltet wird, kann der Echtzeitschutz mithilfe einer der folgenden Optionen deaktiviert werden:

    - Über die Benutzeroberfläche. Öffnen Sie Microsoft Defender for Endpoint unter macOS, und navigieren Sie zu **Einstellungen verwalten.**

      ![Verwalten des Screenshots für den Echtzeitschutz](images/mdatp-36-rtp.png)

    - Vom Terminal aus. Aus Sicherheitsgründen erfordert dieser Vorgang eine Erhöhung.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      Wenn Ihr Gerät von Ihrer Organisation verwaltet wird, kann der Echtzeitschutz von Ihrem Administrator mithilfe der Anweisungen unter Festlegen von Einstellungen für Microsoft Defender for Endpoint unter [macOS deaktiviert werden.](mac-preferences.md)
      
      Wenn das Leistungsproblem weiterhin besteht, während der Echtzeitschutz deaktiviert ist, könnte der Ursprung des Problems die EDR sein. Wenden Sie sich in diesem Fall an den Kundensupport, um weitere Anweisungen und Gegenmaßnahmen zu erhalten.

2. Öffnen Sie finder, und navigieren Sie zu   >  **Anwendungsprogramme**. Öffnen **Sie Aktivitätsüberwachung,** und analysieren Sie, welche Anwendungen die Ressourcen auf Ihrem System verwenden. Typische Beispiele sind Softwareupdater und Compiler.

1. Um die Anwendungen zu finden, die die meisten Scans auslösen, können Sie Echtzeitstatistiken verwenden, die von Defender for Endpoint auf Mac gesammelt wurden.

      > [!NOTE]
      > Dieses Feature ist in Version 100.90.70 oder neuer verfügbar.
      Dieses Feature ist standardmäßig auf den **Kanälen Dogfood** und **InsiderFast** aktiviert. Wenn Sie einen anderen Updatekanal verwenden, kann dieses Feature über die Befehlszeile aktiviert werden:
      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      Dieses Feature erfordert die Aktivierung des Echtzeitschutzes. Führen Sie den folgenden Befehl aus, um den Status des Echtzeitschutzes zu überprüfen:

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    Stellen Sie **sicher, real_time_protection_enabled** eintrag true ist. Führen Sie andernfalls den folgenden Befehl aus, um ihn zu aktivieren:

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      Führen Sie zum Erfassen aktueller Statistiken aus:

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      > [!NOTE]
      > Die **Verwendung von --output json** (beachten Sie den doppelten Strich) stellt sicher, dass das Ausgabeformat für die Analyse bereit ist.
      In der Ausgabe dieses Befehls werden alle Prozesse und die zugehörigen Scanaktivitäten angezeigt.

1. Laden Sie auf Ihrem Mac-System den Beispiel-Python-Parser high_cpu_parser.py mit dem Befehl herunter:

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    Die Ausgabe dieses Befehls sollte der folgenden ähneln:

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 
    0s
    ```

1. Geben Sie als Nächstes die folgenden Befehle ein:

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      Die Ausgabe der oben genannten Ist eine Liste der größten Mitwirkenden bei Leistungsproblemen. Die erste Spalte ist die Prozess-ID (PID), die zweite Spalte ist te Prozessname, und die letzte Spalte ist die Anzahl der gescannten Dateien, sortiert nach Auswirkung.

      Die Ausgabe des Befehls ist z. B. wie folgt:

      ```output
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

      Um die Leistung von Defender for Endpoint auf Dem Mac zu verbessern, suchen Sie die Datei mit der höchsten Zahl unter der Zeile Gescannte Dateien insgesamt, und fügen Sie einen Ausschluss hinzu. Weitere Informationen finden Sie unter [Configure and validate exclusions for Defender for Endpoint on Linux](linux-exclusions.md).

      > [!NOTE]
      > Die Anwendung speichert Statistiken im Arbeitsspeicher und verfolgt nur die Dateiaktivität, seit sie gestartet wurde und der Echtzeitschutz aktiviert wurde. Prozesse, die vor oder während Zeiträumen gestartet wurden, in denen der Echtzeitschutz deaktiviert war, werden nicht gezählt. Darüber hinaus werden nur Ereignisse gezählt, die Scans ausgelöst haben.
      > 
1. Konfigurieren Sie Microsoft Defender for Endpoint unter macOS mit Ausschlüssen für die Prozesse oder Datenträgerspeicherorte, die zu Leistungsproblemen beitragen, und aktivieren Sie den Echtzeitschutz erneut.

     Weitere Informationen finden Sie unter Configure [and validate exclusions for Microsoft Defender for Endpoint auf macOS.](mac-exclusions.md)
