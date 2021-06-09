---
title: Behandeln von Problemen mit Attack Surface Reduction-Regeln
description: Ressourcen und Beispielcode zur Behandlung von Problemen mit Attack Surface Reduction-Regeln in Microsoft Defender für Endpunkt.
keywords: Troubleshoot, error, fix, windows defender eg, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
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
ms.openlocfilehash: c5c76553ff3f0b32def5fbafbf2c8f010e49eeb2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845420"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>Behandeln von Regeln zur Verringerung der Angriffsfläche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Wenn Sie Regeln zur Verringerung der [Angriffsfläche](attack-surface-reduction.md) verwenden, treten möglicherweise Probleme auf, z. B.:

- Eine Regel blockiert eine Datei, einen Prozess oder führt eine andere Aktion aus, die nicht ausgeführt werden sollte (falsch positiv)

- Eine Regel funktioniert nicht wie beschrieben oder blockiert keine Datei oder einen Prozess, die sie verwenden soll (falsch negativ).

Es gibt vier Schritte zur Problembehandlung:

1. [Bestätigen der Voraussetzungen](#confirm-prerequisites)

2. [Verwenden des Überwachungsmodus zum Testen der Regel](#use-audit-mode-to-test-the-rule)

3. [Hinzufügen von Ausschlüssen für die angegebene Regel](#add-exclusions-for-a-false-positive) (bei falsch positiven Ergebnissen)

4. [Übermitteln von Supportprotokollen](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>Bestätigen der Voraussetzungen

Regeln zur Verringerung der Angriffsfläche funktionieren nur auf Geräten mit den folgenden Bedingungen:

- Endpunkte werden Windows 10 Enterprise Version 1709 (auch bekannt als Fall Creators Update) ausgeführt.

- Endpunkte verwenden Microsoft Defender Antivirus als einzige Antivirenschutz-App. [Die Verwendung einer anderen Antiviren-App bewirkt, dass Microsoft Defender AV sich selbst deaktiviert.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

- [Der Echtzeitschutz](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) ist aktiviert.

- Der Überwachungsmodus ist nicht aktiviert. Verwenden Sie Gruppenrichtlinien, um die Regel auf **Deaktiviert** (Wert: **0)** festzulegen, wie unter ["Attack Surface Reduction"-Regeln](enable-attack-surface-reduction.md)beschrieben.

Wenn alle diese Voraussetzungen erfüllt sind, fahren Sie mit dem nächsten Schritt fort, um die Regel im Überwachungsmodus zu testen.

## <a name="use-audit-mode-to-test-the-rule"></a>Verwenden des Überwachungsmodus zum Testen der Regel

Sie können die Website Windows Defender Testumgebung auf [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass Regeln zur Verringerung der Angriffsfläche in der Regel für vorkonfigurierte Szenarien und Prozesse auf einem Gerät funktionieren, oder Sie können den Überwachungsmodus verwenden, der Regeln nur für die Berichterstellung aktiviert.

Befolgen Sie diese Anweisungen unter [Verwenden des Demotools, um zu sehen, wie Regeln zur Verringerung der Angriffsfläche funktionieren,](evaluate-attack-surface-reduction.md) um die spezifische Regel zu testen, mit der Probleme auftreten.

1. Aktivieren Sie den Überwachungsmodus für die regel, die Sie testen möchten. Verwenden Sie Gruppenrichtlinien, um die Regel auf den **Überwachungsmodus** (Wert: **2)** festzulegen, wie unter ["Attack Surface Reduction"-Regeln](enable-attack-surface-reduction.md)beschrieben. Im Überwachungsmodus kann die Regel die Datei oder den Prozess melden, die Ausführung wird jedoch weiterhin zugelassen.

2. Führen Sie die Aktivität aus, die ein Problem verursacht (z. B. Öffnen oder Ausführen der Datei oder des Prozesses, die blockiert werden soll, aber zulässig ist).

3. Überprüfen Sie die Ereignisprotokolle der Regel zur Verringerung der [Angriffsfläche,](attack-surface-reduction.md) um festzustellen, ob die Regel die Datei oder den Prozess blockiert hätte, wenn die Regel auf **"Aktiviert"** festgelegt worden wäre.

Wenn eine Regel eine Datei oder einen Prozess, von dem Sie erwarten, dass sie blockiert werden soll, nicht blockiert, überprüfen Sie zuerst, ob der Überwachungsmodus aktiviert ist.

Der Überwachungsmodus wurde möglicherweise zum Testen eines anderen Features oder durch ein automatisiertes PowerShell-Skript aktiviert und wurde nach Abschluss der Tests möglicherweise nicht deaktiviert.

Wenn Sie die Regel mit dem Demotool und mit dem Überwachungsmodus getestet haben und Attack Surface Reduction-Regeln in vorkonfigurierten Szenarien funktionieren, die Regel jedoch nicht wie erwartet funktioniert, fahren Sie je nach Ihrer Situation mit einem der folgenden Abschnitte fort:

1. Wenn die Regel zur Verringerung der Angriffsfläche etwas blockiert, das nicht blockiert werden sollte (auch als falsch positives Ergebnis bezeichnet), können Sie zuerst einen Ausschluss der Regel zur Verringerung der [Angriffsfläche hinzufügen.](#add-exclusions-for-a-false-positive)

2. Wenn die Regel zur Verringerung der Angriffsfläche etwas nicht blockiert, das blockiert werden soll (auch als falsch negativ bezeichnet), können Sie mit dem letzten Schritt fortfahren, [diagnosedaten sammeln und das Problem an uns übermitteln.](#collect-diagnostic-data-for-file-submissions)

## <a name="add-exclusions-for-a-false-positive"></a>Hinzufügen von Ausschlüssen für ein falsch positives Ergebnis

Wenn die Regel zur Verringerung der Angriffsfläche etwas blockiert, das nicht blockiert werden sollte (auch als falsch positiv bezeichnet), können Sie Ausschlüsse hinzufügen, um zu verhindern, dass Regeln zur Verringerung der Angriffsfläche die ausgeschlossenen Dateien oder Ordner auswerten.

Informationen zum Hinzufügen eines Ausschlusses finden Sie unter Anpassen der Verringerung der [Angriffsfläche.](customize-attack-surface-reduction.md)

>[!IMPORTANT]
>Sie können einzelne Dateien und Ordner angeben, die ausgeschlossen werden sollen, jedoch keine einzelnen Regeln.
>Dies bedeutet, dass alle ausgeschlossenen Dateien oder Ordner von allen ASR-Regeln ausgeschlossen werden.

## <a name="report-a-false-positive-or-false-negative"></a>Melden eines falsch positiven oder falsch negativen Ergebnisses

Verwenden Sie das [webbasierte Übermittlungsformular Windows Defender Security Intelligence,](https://www.microsoft.com/wdsi/filesubmission) um für den Netzwerkschutz ein falsch negatives oder falsch positives Ergebnis zu melden. Mit einem Windows E5-Abonnement können Sie auch [einen Link zu jeder zugeordneten Warnung bereitstellen.](alerts-queue.md)

## <a name="collect-diagnostic-data-for-file-submissions"></a>Sammeln von Diagnosedaten für Dateiübermittlungen

Wenn Sie ein Problem mit Attack Surface Reduction-Regeln melden, werden Sie aufgefordert, Diagnosedaten zu sammeln und zu übermitteln, die von Microsoft-Support- und -Entwicklungsteams zur Problembehandlung verwendet werden können.

1. Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und wechseln Sie zum Verzeichnis Windows Defender:

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

- [Aktivieren der Regeln zur Verringerung der Angriffsfläche](enable-attack-surface-reduction.md)

- [Auswerten der Regeln zur Verringerung der Angriffsfläche](evaluate-attack-surface-reduction.md)
