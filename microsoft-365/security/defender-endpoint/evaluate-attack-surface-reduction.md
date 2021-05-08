---
title: Auswerten der Regeln zur Verringerung der Angriffsfläche
description: Erfahren Sie, wie die Reduzierung der Angriffsfläche Angriffe mit dem benutzerdefinierten Demotool blockieren und verhindern würde.
keywords: Attack surface reduction, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, evaluate, test, demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 73b23427ff401f2a37c399131d6aa01330ff9de5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245300"
---
# <a name="evaluate-attack-surface-reduction-rules"></a>Auswerten der Regeln zur Verringerung der Angriffsfläche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks. Regeln zur Reduzierung der Angriffsfläche helfen dabei, viele der häufig von Schadsoftware und Ransomware verwendeten Einstiegspunkte zu schließen. 

Legen Sie Regeln zur Reduzierung der Angriffsfläche für Geräte mit einer der folgenden Editionen und Versionen von Windows:

- Windows 10 Pro, Version [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows 10 Enterprise, Version [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows Server, [Version 1803 (Halbjährskanal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) oder höher
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Erfahren Sie, wie Sie Regeln zur Reduzierung der Angriffsfläche auswerten, indem Sie den Überwachungsmodus aktivieren, um das Feature direkt in Ihrer Organisation zu testen.

> [!TIP]
> Sie können auch die Microsoft Defender for Endpoint-Demoszenariowebsite unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass das Feature funktioniert und wie es funktioniert.

## <a name="use-audit-mode-to-measure-impact"></a>Verwenden des Überwachungsmodus zum Messen der Auswirkung

Aktivieren Sie Regeln zur Reduzierung der Angriffsfläche im Überwachungsmodus, um einen Datensatz mit Apps anzeigen zu können, die blockiert worden wären, wenn das Feature vollständig aktiviert wäre. Testen Sie, wie das Feature in Ihrer Organisation funktioniert, um sicherzustellen, dass es sich nicht auf Ihre Unternehmensanwendungen auswirken wird. Sie können auch eine Vorstellung davon erhalten, wie oft die Regeln während der normalen Verwendung löschen.

Verwenden Sie das folgende PowerShell-Cmdlet, um eine Regel zur Reduzierung der Angriffsfläche im Überwachungsmodus zu aktivieren:

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

Dabei `<rule ID>` ist ein [GUID-Wert der Regel zur Reduzierung der Angriffsfläche .](attack-surface-reduction.md#attack-surface-reduction-rules)

Verwenden Sie das folgende PowerShell-Cmdlet, um alle hinzugefügten Regeln zur Reduzierung der Angriffsfläche im Überwachungsmodus zu aktivieren:

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> Wenn Sie vollständig überwachen möchten, wie Regeln zur Reduzierung der Angriffsfläche in Ihrer Organisation funktionieren, müssen Sie ein Verwaltungstool verwenden, um diese Einstellung auf Geräten in Ihren Netzwerken bereitstellen zu können.

Sie können die Einstellung auch mithilfe von Gruppenrichtlinien, Intune oder Konfigurationsdienstanbietern für die mobile Geräteverwaltung (Mobile Device Management, MDM) konfigurieren und bereitstellen. Weitere Informationen finden Sie im Hauptartikel [attack surface reduction rules.](attack-surface-reduction.md)

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Überprüfen von Ereignissen zur Reduzierung der Angriffsfläche in Windows Ereignisanzeige

Um Apps zu überprüfen, die blockiert wurden, öffnen Sie die Ereignisanzeige, und filtern Sie im Microsoft-Windows-Windows Defender/Operational-Protokoll nach Ereignis-ID 1121. In der folgenden Tabelle sind alle Netzwerkschutzereignisse aufgeführt.

Ereignis-ID | Beschreibung
-|-
 5007 | Ereignis, wenn Einstellungen geändert werden
 1121 | Ereignis, wenn eine Regel zur Reduzierung der Angriffsfläche im Blockmodus gestartet wird
 1122 | Ereignis, wenn eine Regel zur Reduzierung der Angriffsfläche im Überwachungsmodus gestartet wird

## <a name="customize-attack-surface-reduction-rules"></a>Anpassen der Regeln zur Verringerung der Angriffsfläche

Während der Auswertung können Sie jede Regel einzeln konfigurieren oder bestimmte Dateien und Prozesse von der Auswertung durch das Feature ausschließen.

Informationen zum Konfigurieren des Features mit Verwaltungstools, einschließlich Gruppenrichtlinien und MDM-CSP-Richtlinien, finden Sie unter [Customize attack surface reduction rules.](customize-attack-surface-reduction.md)

## <a name="see-also"></a>Siehe auch

* [Reduzieren von Angriffsoberflächen mit Regeln zur Reduzierung der Angriffsfläche](attack-surface-reduction.md)
* [Verwenden des Überwachungsmodus zum Auswerten Windows Defender](audit-windows-defender.md)
* [FAQ zu Verringerung der Angriffsfläche](attack-surface-reduction.md)
