---
title: Behandeln von Problemen mit Regeln zur Reduzierung der Angriffsfläche
description: Ressourcen und Beispielcode zur Problembehandlung bei Attack Surface Reduction-Regeln in Microsoft Defender for Endpoint.
keywords: Problembehandlung, Fehler, Behebung, Windows Defender z. B. Asr, Regeln, Hips, Problembehandlung, Überwachung, Ausschluss, falsch positiv, gebrochen, Blockieren, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 9ff00c706b0fb336c178e227b1cb33eff9e9ebbc
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935221"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a><span data-ttu-id="85df3-104">Problembehandlung bei Regeln zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="85df3-104">Troubleshoot attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="85df3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="85df3-105">**Applies to:**</span></span>
- [<span data-ttu-id="85df3-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="85df3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="85df3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85df3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="85df3-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="85df3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="85df3-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="85df3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="85df3-110">Wenn Sie Regeln zur Reduzierung der [Angriffsfläche](attack-surface-reduction.md) verwenden, können Probleme auftreten, z. B.:</span><span class="sxs-lookup"><span data-stu-id="85df3-110">When you use [attack surface reduction rules](attack-surface-reduction.md) you may run into issues, such as:</span></span>

- <span data-ttu-id="85df3-111">Eine Regel blockiert eine Datei, einen Prozess oder führt eine andere Aktion aus, die sie nicht verwenden sollte (falsch positiv)</span><span class="sxs-lookup"><span data-stu-id="85df3-111">A rule blocks a file, process, or performs some other action that it shouldn't (false positive)</span></span>

- <span data-ttu-id="85df3-112">Eine Regel funktioniert nicht wie beschrieben oder blockiert keine Datei oder einen Prozess, die sie verwenden soll (falsch negativ)</span><span class="sxs-lookup"><span data-stu-id="85df3-112">A rule doesn't work as described, or doesn't block a file or process that it should (false negative)</span></span>

<span data-ttu-id="85df3-113">Es gibt vier Schritte zur Problembehandlung:</span><span class="sxs-lookup"><span data-stu-id="85df3-113">There are four steps to troubleshooting these problems:</span></span>

1. [<span data-ttu-id="85df3-114">Bestätigen von Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="85df3-114">Confirm prerequisites</span></span>](#confirm-prerequisites)

2. [<span data-ttu-id="85df3-115">Verwenden des Überwachungsmodus zum Testen der Regel</span><span class="sxs-lookup"><span data-stu-id="85df3-115">Use audit mode to test the rule</span></span>](#use-audit-mode-to-test-the-rule)

3. <span data-ttu-id="85df3-116">[Hinzufügen von Ausschlüssen für die angegebene Regel](#add-exclusions-for-a-false-positive) (für falsch positive Ergebnisse)</span><span class="sxs-lookup"><span data-stu-id="85df3-116">[Add exclusions for the specified rule](#add-exclusions-for-a-false-positive) (for false positives)</span></span>

4. [<span data-ttu-id="85df3-117">Übermitteln von Supportprotokollen</span><span class="sxs-lookup"><span data-stu-id="85df3-117">Submit support logs</span></span>](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a><span data-ttu-id="85df3-118">Bestätigen von Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="85df3-118">Confirm prerequisites</span></span>

<span data-ttu-id="85df3-119">Regeln zur Reduzierung der Angriffsfläche funktionieren nur auf Geräten mit den folgenden Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="85df3-119">Attack surface reduction rules will only work on devices with the following conditions:</span></span>

- <span data-ttu-id="85df3-120">Endpunkte werden Windows 10 Enterprise Version 1709 (auch als Fall Creators Update bekannt) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="85df3-120">Endpoints are running Windows 10 Enterprise, version 1709 (also known as the Fall Creators Update).</span></span>

- <span data-ttu-id="85df3-121">Endpunkte verwenden Microsoft Defender Antivirus als einzige Antivirenschutz-App.</span><span class="sxs-lookup"><span data-stu-id="85df3-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="85df3-122">[Wenn Sie eine andere Antiviren-App verwenden, wird Microsoft Defender AV selbst deaktiviert.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="85df3-122">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

- <span data-ttu-id="85df3-123">[Echtzeitschutz](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="85df3-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>

- <span data-ttu-id="85df3-124">Der Überwachungsmodus ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="85df3-124">Audit mode isn't enabled.</span></span> <span data-ttu-id="85df3-125">Verwenden Sie Gruppenrichtlinien, um die Regel auf **Deaktiviert** (Wert: **0**) zu setzen, wie unter Aktivieren von Regeln zur Reduzierung der [Angriffsfläche beschrieben.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="85df3-125">Use Group Policy to set the rule to **Disabled** (value: **0**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

<span data-ttu-id="85df3-126">Wenn alle voraussetzungen erfüllt sind, fahren Sie mit dem nächsten Schritt fort, um die Regel im Überwachungsmodus zu testen.</span><span class="sxs-lookup"><span data-stu-id="85df3-126">If these prerequisites have all been met, proceed to the next step to test the rule in audit mode.</span></span>

## <a name="use-audit-mode-to-test-the-rule"></a><span data-ttu-id="85df3-127">Verwenden des Überwachungsmodus zum Testen der Regel</span><span class="sxs-lookup"><span data-stu-id="85df3-127">Use audit mode to test the rule</span></span>

<span data-ttu-id="85df3-128">Sie können die Windows Defender Test ground-Website unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass Regeln zur Reduzierung der Angriffsfläche in der Regel für vorkonfigurierte Szenarien und Prozesse auf einem Gerät funktionieren, oder Sie können den Überwachungsmodus verwenden, der Regeln nur für die Berichterstellung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="85df3-128">You can visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm attack surface reduction rules are generally working for pre-configured scenarios and processes on a device, or you can use audit mode, which enables rules for reporting only.</span></span>

<span data-ttu-id="85df3-129">Befolgen Sie diese Anweisungen unter [Verwenden des Demotools,](evaluate-attack-surface-reduction.md) um zu sehen, wie Regeln zur Reduzierung der Angriffsfläche funktionieren, um die spezifische Regel zu testen, mit der Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="85df3-129">Follow these instructions in [Use the demo tool to see how attack surface reduction rules work](evaluate-attack-surface-reduction.md) to test the specific rule you're encountering problems with.</span></span>

1. <span data-ttu-id="85df3-130">Aktivieren Sie den Überwachungsmodus für die bestimmte Regel, die Sie testen möchten.</span><span class="sxs-lookup"><span data-stu-id="85df3-130">Enable audit mode for the specific rule you want to test.</span></span> <span data-ttu-id="85df3-131">Verwenden Sie Gruppenrichtlinien, um die Regel auf den **Überwachungsmodus** (Wert: **2)** zu setzen, wie unter [Enable attack surface reduction rules beschrieben.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="85df3-131">Use Group Policy to set the rule to **Audit mode** (value: **2**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span> <span data-ttu-id="85df3-132">Der Überwachungsmodus ermöglicht es der Regel, die Datei oder den Prozess zu melden, ermöglicht jedoch weiterhin die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="85df3-132">Audit mode allows the rule to report the file or process, but will still allow it to run.</span></span>

2. <span data-ttu-id="85df3-133">Führen Sie die Aktivität aus, die ein Problem verursacht (z. B. öffnen oder ausführen Sie die Datei oder den Prozess, die blockiert werden soll, aber zulässig ist).</span><span class="sxs-lookup"><span data-stu-id="85df3-133">Perform the activity that is causing an issue (for example, open or execute the file or process that should be blocked but is being allowed).</span></span>

3. <span data-ttu-id="85df3-134">[Überprüfen Sie die Ereignisprotokolle](attack-surface-reduction.md) der Regel zur Reduzierung der Angriffsfläche, um zu sehen, ob die Regel die Datei oder den Prozess blockiert hätte, wenn die Regel auf **Aktiviert festgelegt wurde.**</span><span class="sxs-lookup"><span data-stu-id="85df3-134">[Review the attack surface reduction rule event logs](attack-surface-reduction.md) to see if the rule would have blocked the file or process if the rule had been set to **Enabled**.</span></span>

<span data-ttu-id="85df3-135">Wenn eine Regel eine Datei oder einen Prozess nicht blockiert, von der Sie erwarten, dass sie blockiert wird, überprüfen Sie zunächst, ob der Überwachungsmodus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="85df3-135">If a rule isn't blocking a file or process that you're expecting it should block, first check if audit mode is enabled.</span></span>

<span data-ttu-id="85df3-136">Der Überwachungsmodus wurde möglicherweise für das Testen eines anderen Features oder durch ein automatisiertes PowerShell-Skript aktiviert und nach Abschluss der Tests möglicherweise nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="85df3-136">Audit mode may have been enabled for testing another feature, or by an automated PowerShell script, and may not have been disabled after the tests were completed.</span></span>

<span data-ttu-id="85df3-137">Wenn Sie die Regel mit dem Demotool und mit dem Überwachungsmodus getestet haben und Regeln zur Reduzierung der Angriffsfläche in vorkonfigurierten Szenarien funktionieren, die Regel jedoch nicht wie erwartet funktioniert, fahren Sie mit einem der folgenden Abschnitte basierend auf Ihrer Situation fort:</span><span class="sxs-lookup"><span data-stu-id="85df3-137">If you've tested the rule with the demo tool and with audit mode, and attack surface reduction rules are working on pre-configured scenarios, but the rule isn't working as expected, proceed to either of the following sections based on your situation:</span></span>

1. <span data-ttu-id="85df3-138">Wenn die Regel zur Reduzierung der Angriffsfläche etwas blockiert, das sie nicht blockieren sollte (auch als falsch positiv bezeichnet), können Sie zunächst einen Regelausschluss für die Angriffsflächereduzierung [hinzufügen.](#add-exclusions-for-a-false-positive)</span><span class="sxs-lookup"><span data-stu-id="85df3-138">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can [first add an attack surface reduction rule exclusion](#add-exclusions-for-a-false-positive).</span></span>

2. <span data-ttu-id="85df3-139">Wenn die Regel zur Reduzierung der Angriffsfläche etwas blockiert, das blockiert werden soll (auch als falsch negativ bezeichnet), können Sie sofort mit dem letzten Schritt fortfahren, Diagnosedaten sammeln und das Problem an uns [übermitteln.](#collect-diagnostic-data-for-file-submissions)</span><span class="sxs-lookup"><span data-stu-id="85df3-139">If the attack surface reduction rule isn't blocking something that it should block (also known as a false negative), you can proceed immediately to the last step, [collecting diagnostic data and submitting the issue to us](#collect-diagnostic-data-for-file-submissions).</span></span>

## <a name="add-exclusions-for-a-false-positive"></a><span data-ttu-id="85df3-140">Hinzufügen von Ausschlüssen für ein falsch positives Ergebnis</span><span class="sxs-lookup"><span data-stu-id="85df3-140">Add exclusions for a false positive</span></span>

<span data-ttu-id="85df3-141">Wenn die Regel zur Reduzierung der Angriffsfläche etwas blockiert, das sie nicht blockieren sollte (auch als falsch positiv bezeichnet), können Sie Ausschlüsse hinzufügen, um zu verhindern, dass Regeln zur Reduzierung der Angriffsfläche die ausgeschlossenen Dateien oder Ordner auswerten.</span><span class="sxs-lookup"><span data-stu-id="85df3-141">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can add exclusions to prevent attack surface reduction rules from evaluating the excluded files or folders.</span></span>

<span data-ttu-id="85df3-142">Informationen zum Hinzufügen eines Ausschlusses finden Sie unter [Customize Attack surface reduction](customize-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="85df3-142">To add an exclusion, see [Customize Attack surface reduction](customize-attack-surface-reduction.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="85df3-143">Sie können einzelne Dateien und Ordner angeben, die ausgeschlossen werden sollen, aber sie können keine einzelnen Regeln angeben.</span><span class="sxs-lookup"><span data-stu-id="85df3-143">You can specify individual files and folders to be excluded, but you cannot specify individual rules.</span></span>
><span data-ttu-id="85df3-144">Dies bedeutet, dass alle ausgeschlossenen Dateien oder Ordner von allen ASR-Regeln ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="85df3-144">This means any files or folders that are excluded will be excluded from all ASR rules.</span></span>

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="85df3-145">Melden eines falsch positiven oder falsch negativen Werts</span><span class="sxs-lookup"><span data-stu-id="85df3-145">Report a false positive or false negative</span></span>

<span data-ttu-id="85df3-146">Verwenden Sie Windows Defender [Webbasiertes](https://www.microsoft.com/wdsi/filesubmission) Übermittlungsformular für Sicherheitsintelligenz, um ein falsch negatives oder falsch positives Ergebnis für den Netzwerkschutz zu melden.</span><span class="sxs-lookup"><span data-stu-id="85df3-146">Use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="85df3-147">Mit einem Windows E5-Abonnement können Sie auch einen Link zu allen zugeordneten [Warnungen bereitstellen.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="85df3-147">With a Windows E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="85df3-148">Sammeln von Diagnosedaten für Dateiübermittlungen</span><span class="sxs-lookup"><span data-stu-id="85df3-148">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="85df3-149">Wenn Sie ein Problem mit Regeln zur Reduzierung der Angriffsfläche melden, werden Sie aufgefordert, Diagnosedaten zu sammeln und zu übermitteln, die von Microsoft-Support- und Engineeringteams zur Problembehandlung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="85df3-149">When you report a problem with attack surface reduction rules, you're asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="85df3-150">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und ändern Sie Windows Defender Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="85df3-150">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd "c:\program files\windows defender"
   ```

2. <span data-ttu-id="85df3-151">Führen Sie diesen Befehl aus, um die Diagnoseprotokolle zu generieren:</span><span class="sxs-lookup"><span data-stu-id="85df3-151">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="85df3-152">Standardmäßig werden sie in `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="85df3-152">By default, they're saved to `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> <span data-ttu-id="85df3-153">Fügen Sie die Datei an das Übermittlungsformular an.</span><span class="sxs-lookup"><span data-stu-id="85df3-153">Attach the file to the submission form.</span></span>

## <a name="related-articles"></a><span data-ttu-id="85df3-154">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="85df3-154">Related articles</span></span>

- [<span data-ttu-id="85df3-155">Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="85df3-155">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="85df3-156">Aktivieren der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="85df3-156">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)

- [<span data-ttu-id="85df3-157">Auswerten der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="85df3-157">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
