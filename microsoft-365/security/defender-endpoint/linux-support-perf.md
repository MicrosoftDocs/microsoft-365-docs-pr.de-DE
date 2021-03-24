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
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="2c3b5-104">Behandeln von Leistungsproblemen für Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="2c3b5-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2c3b5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2c3b5-105">**Applies to:**</span></span>
- [<span data-ttu-id="2c3b5-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2c3b5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2c3b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c3b5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
> <span data-ttu-id="2c3b5-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="2c3b5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2c3b5-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="2c3b5-110">Dieser Artikel enthält einige allgemeine Schritte, die verwendet werden können, um Leistungsprobleme im Zusammenhang mit Defender for Endpoint für Linux zu einenten.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-110">This article provides some general steps that can be used to narrow down performance issues related to Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="2c3b5-111">Der Echtzeitschutz (Real-Time Protection, RTP) ist ein Feature von Defender for Endpoint für Linux, das Ihr Gerät kontinuierlich überwacht und vor Bedrohungen schützt.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-111">Real-time protection (RTP) is a feature of Defender for Endpoint for Linux that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="2c3b5-112">Es besteht aus Datei- und Prozessüberwachung und anderen Heuristiken.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-112">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="2c3b5-113">Abhängig von den ausgeführten Anwendungen und den Gerätemerkmalen kann es bei der Ausführung von Defender for Endpoint für Linux zu einer suboptimalen Leistung kommen.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-113">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Defender for Endpoint for Linux.</span></span> <span data-ttu-id="2c3b5-114">Insbesondere Anwendungen oder Systemprozesse, die über einen kurzen Zeitraum auf viele Ressourcen zugreifen, können zu Leistungsproblemen in Defender for Endpoint für Linux führen.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-114">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="2c3b5-115">Stellen Sie vor dem Start sicher, dass andere Sicherheitsprodukte derzeit **nicht auf dem Gerät ausgeführt werden.**</span><span class="sxs-lookup"><span data-stu-id="2c3b5-115">Before starting, **please make sure that other security products are not currently running on the device**.</span></span> <span data-ttu-id="2c3b5-116">Mehrere Sicherheitsprodukte können Konflikte und Auswirkungen auf die Hostleistung haben.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-116">Multiple security products may conflict and impact the host performance.</span></span>

<span data-ttu-id="2c3b5-117">Die folgenden Schritte können verwendet werden, um diese Probleme zu beheben und zu beheben:</span><span class="sxs-lookup"><span data-stu-id="2c3b5-117">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="2c3b5-118">Deaktivieren Sie den Echtzeitschutz mithilfe einer der folgenden Methoden, und beobachten Sie, ob sich die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-118">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="2c3b5-119">Dieser Ansatz trägt dazu bei, die Leistungsprobleme von Defender for Endpoint für Linux zu eind nen.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-119">This approach helps narrow down whether Defender for Endpoint for Linux is contributing to the performance issues.</span></span>

    <span data-ttu-id="2c3b5-120">Wenn Ihr Gerät nicht von Ihrer Organisation verwaltet wird, kann der Echtzeitschutz über die Befehlszeile deaktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="2c3b5-120">If your device is not managed by your organization, real-time protection can be disabled from the command line:</span></span>

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="2c3b5-121">Wenn Ihr Gerät von Ihrer Organisation verwaltet wird, kann der Echtzeitschutz von Ihrem Administrator mithilfe der Anweisungen unter Festlegen von Einstellungen für [Defender for Endpoint für Linux deaktiviert werden.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="2c3b5-121">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

    <span data-ttu-id="2c3b5-122">Wenn das Leistungsproblem weiterhin besteht, während der Echtzeitschutz deaktiviert ist, könnte der Ursprung des Problems die Endpunkterkennungs- und Reaktionskomponente sein.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-122">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="2c3b5-123">In diesem Fall wenden Sie sich an den Kundensupport, um weitere Anweisungen und Gegenmaßnahmen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-123">In this case please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="2c3b5-124">Um die Anwendungen zu finden, die die meisten Scans auslösen, können Sie von Defender for Endpoint für Linux gesammelte Echtzeitstatistiken verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-124">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint for Linux.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2c3b5-125">Dieses Feature ist in Version 100.90.70 oder neuer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-125">This feature is available in version 100.90.70 or newer.</span></span>

    <span data-ttu-id="2c3b5-126">Dieses Feature ist standardmäßig auf den `Dogfood` Kanälen und `InsiderFast` aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-126">This feature is enabled by default on the `Dogfood` and `InsiderFast` channels.</span></span> <span data-ttu-id="2c3b5-127">Wenn Sie einen anderen Updatekanal verwenden, kann dieses Feature über die Befehlszeile aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="2c3b5-127">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    <span data-ttu-id="2c3b5-128">Dieses Feature erfordert die Aktivierung des Echtzeitschutzes.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-128">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="2c3b5-129">Führen Sie den folgenden Befehl aus, um den Status des Echtzeitschutzes zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="2c3b5-129">To check the status of real-time protection, run the following command:</span></span>

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    <span data-ttu-id="2c3b5-130">Stellen Sie sicher, `real_time_protection_enabled` dass der Eintrag ist `true` .</span><span class="sxs-lookup"><span data-stu-id="2c3b5-130">Verify that the `real_time_protection_enabled` entry is `true`.</span></span> <span data-ttu-id="2c3b5-131">Führen Sie andernfalls den folgenden Befehl aus, um ihn zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="2c3b5-131">Otherwise, run the following command to enable it:</span></span>

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="2c3b5-132">Führen Sie zum Erfassen aktueller Statistiken aus:</span><span class="sxs-lookup"><span data-stu-id="2c3b5-132">To collect current statistics, run:</span></span>

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > <span data-ttu-id="2c3b5-133">Die ```--output json``` Verwendung (beachten Sie den doppelten Strich) stellt sicher, dass das Ausgabeformat für die Analyse bereit ist.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-133">Using ```--output json``` (note the double dash) ensures that the output format is ready for parsing.</span></span>

    <span data-ttu-id="2c3b5-134">In der Ausgabe dieses Befehls werden alle Prozesse und die zugehörigen Scanaktivitäten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-134">The output of this command will show all processes and their associated scan activity.</span></span>

3. <span data-ttu-id="2c3b5-135">Laden Sie auf Ihrem Linux-System den Beispiel-Python-Parser **high_cpu_parser.py** mit dem Befehl herunter:</span><span class="sxs-lookup"><span data-stu-id="2c3b5-135">On your Linux system, download the sample Python parser **high_cpu_parser.py** using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    <span data-ttu-id="2c3b5-136">Die Ausgabe dieses Befehls sollte der folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="2c3b5-136">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. <span data-ttu-id="2c3b5-137">Geben Sie als Nächstes die folgenden Befehle ein:</span><span class="sxs-lookup"><span data-stu-id="2c3b5-137">Next, type the following commands:</span></span>

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      <span data-ttu-id="2c3b5-138">Die Ausgabe der oben genannten Ist eine Liste der größten Mitwirkenden bei Leistungsproblemen.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-138">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="2c3b5-139">Die erste Spalte ist die Prozess-ID (PID), die zweite Spalte ist te Prozessname, und die letzte Spalte ist die Anzahl der gescannten Dateien, sortiert nach Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-139">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>
    <span data-ttu-id="2c3b5-140">Die Ausgabe des Befehls ist z. B. wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2c3b5-140">For example, the output of the command will be something like the below:</span></span> 

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

    <span data-ttu-id="2c3b5-141">Um die Leistung von Defender for Endpoint für Linux zu verbessern, suchen Sie den Server mit der höchsten Anzahl unter der Zeile, und fügen Sie einen Ausschluss `Total files scanned` hinzu.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-141">To improve the performance of Defender for Endpoint for Linux, locate the one with the highest number under the `Total files scanned` row and add an exclusion for it.</span></span> <span data-ttu-id="2c3b5-142">Weitere Informationen finden Sie unter [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span><span class="sxs-lookup"><span data-stu-id="2c3b5-142">For more information, see [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span></span>

    >[!NOTE]
    > <span data-ttu-id="2c3b5-143">Die Anwendung speichert Statistiken im Arbeitsspeicher und verfolgt nur die Dateiaktivität, seit sie gestartet wurde und der Echtzeitschutz aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-143">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="2c3b5-144">Prozesse, die vor oder während Zeiträumen gestartet wurden, in denen der Echtzeitschutz deaktiviert war, werden nicht gezählt.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-144">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="2c3b5-145">Darüber hinaus werden nur Ereignisse gezählt, die Scans ausgelöst haben.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-145">Additionally, only events which triggered scans are counted.</span></span>

5. <span data-ttu-id="2c3b5-146">Konfigurieren Sie Microsoft Defender ATP für Linux mit Ausschlüssen für die Prozesse oder Datenträgerspeicherorte, die zu Leistungsproblemen beitragen, und aktivieren Sie den Echtzeitschutz erneut.</span><span class="sxs-lookup"><span data-stu-id="2c3b5-146">Configure Microsoft Defender ATP for Linux with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="2c3b5-147">Weitere Informationen finden Sie unter [Configure and validate exclusions for Microsoft Defender ATP for Linux](linux-exclusions.md).</span><span class="sxs-lookup"><span data-stu-id="2c3b5-147">For more information, see [Configure and validate exclusions for Microsoft Defender ATP for Linux](linux-exclusions.md).</span></span>
