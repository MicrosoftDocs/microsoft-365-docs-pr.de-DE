---
title: Behandeln von Problemen mit Regeln zur Reduzierung der Angriffsfläche
description: Ressourcen und Beispielcode zur Problembehandlung bei Attack Surface Reduction-Regeln in Microsoft Defender for Endpoint.
keywords: Problembehandlung, Fehler, Behebung, Windows Defender z. B. Asr, Regeln, Hips, Problembehandlung, Überwachung, Ausschluss, falsch positiv, gebrochen, Blockieren, Microsoft Defender für Endpunkt, microsoft defender advanced threat protection
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
ms.openlocfilehash: cc8c66665740449e499c11e1db4403caef20cf9c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183765"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>Problembehandlung bei Regeln zur Reduzierung der Angriffsfläche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Wenn Sie Regeln zur Reduzierung der [Angriffsfläche](attack-surface-reduction.md) verwenden, können Probleme auftreten, z. B.:

- Eine Regel blockiert eine Datei, einen Prozess oder führt eine andere Aktion aus, die sie nicht verwenden sollte (falsch positiv)

- Eine Regel funktioniert nicht wie beschrieben oder blockiert keine Datei oder einen Prozess, die sie verwenden soll (falsch negativ)

Es gibt vier Schritte zur Problembehandlung:

1. [Bestätigen von Voraussetzungen](#confirm-prerequisites)

2. [Verwenden des Überwachungsmodus zum Testen der Regel](#use-audit-mode-to-test-the-rule)

3. [Hinzufügen von Ausschlüssen für die angegebene Regel](#add-exclusions-for-a-false-positive) (für falsch positive Ergebnisse)

4. [Übermitteln von Supportprotokollen](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>Bestätigen von Voraussetzungen

Regeln zur Reduzierung der Angriffsfläche funktionieren nur auf Geräten mit den folgenden Bedingungen:

- Auf Endpunkten wird Windows 10 Enterprise, Version 1709 (auch als Fall Creators Update bekannt) ausgeführt.

- Endpunkte verwenden Microsoft Defender Antivirus als einzige Antivirenschutz-App. [Wenn Sie eine andere Antiviren-App verwenden, wird Microsoft Defender AV selbst deaktiviert.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

- [Echtzeitschutz](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) ist aktiviert.

- Der Überwachungsmodus ist nicht aktiviert. Verwenden Sie Gruppenrichtlinien, um die Regel auf **Deaktiviert** (Wert: **0**) zu setzen, wie unter Aktivieren von Regeln zur Reduzierung der [Angriffsfläche beschrieben.](enable-attack-surface-reduction.md)

Wenn alle voraussetzungen erfüllt sind, fahren Sie mit dem nächsten Schritt fort, um die Regel im Überwachungsmodus zu testen.

## <a name="use-audit-mode-to-test-the-rule"></a>Verwenden des Überwachungsmodus zum Testen der Regel

Sie können die Windows Defender Test ground-Website unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass Regeln zur Reduzierung der Angriffsfläche in der Regel für vorkonfigurierte Szenarien und Prozesse auf einem Gerät geeignet sind, oder Sie können den Überwachungsmodus verwenden, der nur Regeln für die Berichterstellung ermöglicht.

Befolgen Sie diese Anweisungen unter [Verwenden des Demotools,](evaluate-attack-surface-reduction.md) um zu sehen, wie Regeln zur Reduzierung der Angriffsfläche funktionieren, um die spezifische Regel zu testen, mit der Probleme auftreten.

1. Aktivieren Sie den Überwachungsmodus für die bestimmte Regel, die Sie testen möchten. Verwenden Sie Gruppenrichtlinien, um die Regel auf den **Überwachungsmodus** (Wert: **2)** zu setzen, wie unter [Enable attack surface reduction rules beschrieben.](enable-attack-surface-reduction.md) Der Überwachungsmodus ermöglicht es der Regel, die Datei oder den Prozess zu melden, ermöglicht jedoch weiterhin die Ausführung.

2. Führen Sie die Aktivität aus, die ein Problem verursacht (z. B. öffnen oder ausführen Sie die Datei oder den Prozess, die blockiert werden soll, aber zulässig ist).

3. [Überprüfen Sie die Ereignisprotokolle](attack-surface-reduction.md) der Regel zur Reduzierung der Angriffsfläche, um zu sehen, ob die Regel die Datei oder den Prozess blockiert hätte, wenn die Regel auf **Aktiviert festgelegt wurde.**

Wenn eine Regel eine Datei oder einen Prozess nicht blockiert, von der Sie erwarten, dass sie blockiert wird, überprüfen Sie zunächst, ob der Überwachungsmodus aktiviert ist.

Der Überwachungsmodus wurde möglicherweise für das Testen eines anderen Features oder durch ein automatisiertes PowerShell-Skript aktiviert und nach Abschluss der Tests möglicherweise nicht deaktiviert.

Wenn Sie die Regel mit dem Demotool und mit dem Überwachungsmodus getestet haben und Regeln zur Reduzierung der Angriffsfläche in vorkonfigurierten Szenarien funktionieren, die Regel jedoch nicht wie erwartet funktioniert, fahren Sie mit einem der folgenden Abschnitte basierend auf Ihrer Situation fort:

1. Wenn die Regel zur Reduzierung der Angriffsfläche etwas blockiert, das sie nicht blockieren sollte (auch als falsch positiv bezeichnet), können Sie zunächst einen Regelausschluss für die Angriffsflächereduzierung [hinzufügen.](#add-exclusions-for-a-false-positive)

2. Wenn die Regel zur Reduzierung der Angriffsfläche etwas blockiert, das blockiert werden soll (auch als falsch negativ bezeichnet), können Sie sofort mit dem letzten Schritt fortfahren, Diagnosedaten sammeln und das Problem an uns [übermitteln.](#collect-diagnostic-data-for-file-submissions)

## <a name="add-exclusions-for-a-false-positive"></a>Hinzufügen von Ausschlüssen für ein falsch positives Ergebnis

Wenn die Regel zur Reduzierung der Angriffsfläche etwas blockiert, das sie nicht blockieren sollte (auch als falsch positiv bezeichnet), können Sie Ausschlüsse hinzufügen, um zu verhindern, dass Regeln zur Reduzierung der Angriffsfläche die ausgeschlossenen Dateien oder Ordner auswerten.

Informationen zum Hinzufügen eines Ausschlusses finden Sie unter [Customize Attack surface reduction](customize-attack-surface-reduction.md).

>[!IMPORTANT]
>Sie können einzelne Dateien und Ordner angeben, die ausgeschlossen werden sollen, aber sie können keine einzelnen Regeln angeben.
>Dies bedeutet, dass alle ausgeschlossenen Dateien oder Ordner von allen ASR-Regeln ausgeschlossen werden.

## <a name="report-a-false-positive-or-false-negative"></a>Melden eines falsch positiven oder falsch negativen Werts

Verwenden Sie [Windows Defender Webbasiertes Übermittlungsformular](https://www.microsoft.com/wdsi/filesubmission) für Sicherheitsintelligenz, um ein falsch negatives oder falsch positives Ergebnis für den Netzwerkschutz zu melden. Mit einem Windows E5-Abonnement können Sie auch einen Link zu allen [zugeordneten Warnungen bereitstellen.](alerts-queue.md)

## <a name="collect-diagnostic-data-for-file-submissions"></a>Sammeln von Diagnosedaten für Dateiübermittlungen

Wenn Sie ein Problem mit Regeln zur Reduzierung der Angriffsfläche melden, werden Sie aufgefordert, Diagnosedaten zu sammeln und zu übermitteln, die von Microsoft-Support- und Engineeringteams zur Problembehandlung verwendet werden können.

1. Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und ändern Sie Windows Defender Verzeichnis:

   ```console
   cd "c:\program files\windows defender"
   ```

2. Führen Sie diesen Befehl aus, um die Diagnoseprotokolle zu generieren:

   ```console
   mpcmdrun -getfiles
   ```

3. Standardmäßig werden sie in `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` gespeichert. Fügen Sie die Datei an das Übermittlungsformular an.

## <a name="related-articles"></a>Verwandte Artikel

- [Regeln zur Verringerung der Angriffsfläche](attack-surface-reduction.md)

- [Aktivieren von Regeln zur Reduzierung der Angriffsfläche](enable-attack-surface-reduction.md)

- [Bewerten von Regeln zur Reduzierung der Angriffsfläche](evaluate-attack-surface-reduction.md)
