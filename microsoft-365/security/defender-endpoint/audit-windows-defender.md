---
title: Testen der Funktionsweise von Microsoft Defender für Endpunkt-Features im Überwachungsmodus
description: Der Überwachungsmodus hilft Ihnen zu sehen, wie Microsoft Defender für Endpunkt Ihre Geräte schützen würde, wenn sie aktiviert wäre.
keywords: Exploit-Schutz, Überwachung, Überwachung, Modus, aktiviert, deaktiviert, Testen, Demo, auswerten, Lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985096"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>Testen der Verringerung der Angriffsfläche in Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Als Teil des Sicherheitsteams Ihrer Organisation können Sie Attack Surface Reduction-Funktionen so konfigurieren, dass sie im Überwachungsmodus ausgeführt werden, um zu sehen, wie sie funktionieren. Im Überwachungsmodus können Sie Folgendes aktivieren:

- Regeln zur Verringerung der Angriffsfläche
- Exploit-Schutz
- Netzwerkschutz
- Und kontrollierter Ordnerzugriff im Überwachungsmodus

Im Überwachungsmodus können Sie sehen, was passiert *wäre,* wenn Sie das Feature aktiviert hätten.

Sie können den Überwachungsmodus aktivieren, wenn Sie testen, wie die Features funktionieren. Dadurch wird sichergestellt, dass Ihre Branchen-Apps nicht betroffen sind. Sie können sich auch einen Eindruck davon verschaffen, wie viele verdächtige Dateiänderungsversuche über einen bestimmten Zeitraum erfolgen.

Die Features blockieren oder verhindern nicht, dass Apps, Skripts oder Dateien geändert werden. Das Windows Ereignisprotokoll zeichnet jedoch Ereignisse auf, als wären die Features vollständig aktiviert. Im Überwachungsmodus können Sie das Ereignisprotokoll überprüfen, um festzustellen, welche Auswirkungen das Feature hätte, wenn es aktiviert wäre.

Um die überwachten Einträge zu finden, wechseln Sie zu **Anwendungen und Dienste**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.

Verwenden Sie Defender für Endpunkt, um mehr Details für jedes Ereignis zu erhalten, insbesondere für die Untersuchung von Regeln zur Verringerung der Angriffsfläche. Mithilfe der Defender für Endpunkt-Konsole können Sie [Probleme im Rahmen der Warnungszeitachse und untersuchungsszenarien untersuchen.](investigate-alerts.md)

Sie können den Überwachungsmodus mithilfe von Gruppenrichtlinien, PowerShell und Konfigurationsdienstanbietern (Configuration Service Providers, CSPs) aktivieren.

> [!TIP]
> Sie können auch die Website Windows Defender Testground unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass die Features funktionieren und wie sie funktionieren.

| Überwachungsoptionen | So aktivieren Sie den Überwachungsmodus | Anzeigen von Ereignissen |
|---------|---------|---------|
| Überwachung gilt für alle Ereignisse | [Kontrollierte Ordnerzugriff aktivieren](enable-controlled-folders.md) | [Kontrollierte Ordnerzugriffsereignisse](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| Überwachung gilt für einzelne Regeln | [Aktivieren der Regeln zur Verringerung der Angriffsfläche](enable-attack-surface-reduction.md) | [Regelereignisse zur Verringerung der Angriffsfläche](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| Überwachung gilt für alle Ereignisse | [Netzwerkschutz aktivieren](enable-network-protection.md) | [Netzwerkschutzereignisse](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| Die Überwachung gilt für einzelne Risikominderungen | [Aktivieren des Exploit-Schutzes](enable-exploit-protection.md) | [Exploit-Schutzereignisse](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
