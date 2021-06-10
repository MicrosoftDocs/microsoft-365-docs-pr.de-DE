---
title: Auswerten der Regeln zur Verringerung der Angriffsfläche
description: Erfahren Sie, wie Attack Surface Reduction Angriffe mit dem benutzerdefinierten Demotool blockieren und verhindern würde.
keywords: Attack Surface Reduction, Hips, Host Intrusion Prevention System, Schutzregeln, Anti-Exploit, Antiexploit, Exploit, Infektionsschutz, auswerten, testen, Demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5d3cd7893af4c91807782c269231a280b413733e
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861219"
---
# <a name="evaluate-attack-surface-reduction-rules"></a>Auswerten der Regeln zur Verringerung der Angriffsfläche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Regeln zur Verringerung der Angriffsfläche tragen dazu bei, Aktionen zu verhindern, die in der Regel von Schadsoftware verwendet werden, um Geräte oder Netzwerke zu kompromittieren. Regeln zur Verringerung der Angriffsfläche helfen dabei, viele der gängigen Einstiegspunkte zu schließen, die von Schadsoftware und Ransomware verwendet werden. 

Legen Sie Regeln zur Verringerung der Angriffsfläche für Geräte fest, auf denen eine der folgenden Editionen und Versionen von Windows ausgeführt wird:

- Windows 10 Pro, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows 10 Enterprise, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows Server, [Version 1803 (Halbjährlicher Kanal)](/windows-server/get-started/whats-new-in-windows-server-1803) oder höher
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

> [!WARNING]
> Das Aktivieren von Regeln zur Verringerung des Angriffsdiensts auf Windows Server 2016 kann zu unerwarteten Ergebnissen führen und sich auf die Serverleistung auswirken. Es wird nicht empfohlen, Regeln zur Verringerung der Angriffsfläche auf nicht unterstützten Plattformen zu aktivieren oder bereitzustellen.

Erfahren Sie, wie Sie Regeln zur Verringerung der Angriffsfläche auswerten, indem Sie den Überwachungsmodus aktivieren, um das Feature direkt in Ihrer Organisation zu testen.

> [!TIP]
> Sie können auch die Microsoft Defender für Endpunkt-Demoszenario-Website unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass das Feature funktioniert und wie es funktioniert.

## <a name="use-audit-mode-to-measure-impact"></a>Verwenden des Überwachungsmodus zum Messen der Auswirkungen

Aktivieren Sie die Regeln zur Verringerung der Angriffsfläche im Überwachungsmodus, um einen Datensatz von Apps anzuzeigen, die blockiert worden wären, wenn das Feature vollständig aktiviert wäre. Testen Sie, wie das Feature in Ihrer Organisation funktioniert, um sicherzustellen, dass es sich nicht auf Ihre Branchen-Apps auswirkt. Sie können sich auch einen Eindruck davon verschaffen, wie oft die Regeln während der normalen Verwendung ausgelöst werden.

Verwenden Sie das folgende PowerShell-Cmdlet, um eine Regel zur Verringerung der Angriffsfläche im Überwachungsmodus zu aktivieren:

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

Gibt an, wo `<rule ID>` sich ein [GUID-Wert der Regel zur Verringerung der Angriffsfläche befindet.](attack-surface-reduction.md#attack-surface-reduction-rules)

Verwenden Sie das folgende PowerShell-Cmdlet, um alle hinzugefügten Regeln zur Verringerung der Angriffsfläche im Überwachungsmodus zu aktivieren:

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> Wenn Sie die Funktionsweise der Regeln zur Verringerung der Angriffsfläche in Ihrer Organisation vollständig überwachen möchten, müssen Sie ein Verwaltungstool verwenden, um diese Einstellung auf Geräten in Ihren Netzwerken bereitzustellen.

Sie können die Einstellung auch mithilfe von Gruppenrichtlinien, Intune oder Konfigurationsdienstanbietern (CSPs) für die mobile Geräteverwaltung (Mobile Device Management, MDM) konfigurieren und bereitstellen. Weitere Informationen finden Sie im Hauptartikel zu [Attack Surface Reduction-Regeln.](attack-surface-reduction.md)

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Überprüfen von Ereignissen zur Verringerung der Angriffsfläche in Windows Ereignisanzeige

Um Apps zu überprüfen, die blockiert worden wären, öffnen Sie die Ereignisanzeige, und filtern Sie im Microsoft-Windows-Windows Defender/Betriebsprotokoll nach Ereignis-ID 1121. In der folgenden Tabelle sind alle Netzwerkschutzereignisse aufgeführt.

Ereignis-ID | Beschreibung
-|-
 5007 | Ereignis, wenn Einstellungen geändert werden
 1121 | Ereignis, wenn eine Regel zur Verringerung der Angriffsfläche im Blockierungsmodus ausgelöst wird
 1122 | Ereignis, wenn eine Regel zur Verringerung der Angriffsfläche im Überwachungsmodus ausgelöst wird

## <a name="customize-attack-surface-reduction-rules"></a>Anpassen der Regeln zur Verringerung der Angriffsfläche

Während der Auswertung können Sie jede Regel einzeln konfigurieren oder bestimmte Dateien und Prozesse von der Auswertung durch das Feature ausschließen.

Informationen zum Konfigurieren des Features mit Verwaltungstools, einschließlich Gruppenrichtlinien und MDM-CSP-Richtlinien, finden Sie unter Anpassen von Regeln zur Verringerung der [Angriffsfläche.](customize-attack-surface-reduction.md)

## <a name="see-also"></a>Siehe auch

* [Reduzieren von Angriffsflächen mit Regeln zur Verringerung der Angriffsfläche](attack-surface-reduction.md)
* [Verwenden des Überwachungsmodus zum Auswerten Windows Defender](audit-windows-defender.md)
* [Häufig gestellte Fragen zur Verringerung der Angriffsfläche](attack-surface-reduction.md)
