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
ms.openlocfilehash: c2ff6eac3254e855d4858edc218ae5df034352e4
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925659"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>Testen der Verringerung der Angriffsfläche in Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Wenn Sie Teil des Sicherheitsteams Ihrer Organisation sind, können Sie Attack Surface Reduction-Funktionen so konfigurieren, dass sie im Überwachungsmodus ausgeführt werden, um zu sehen, wie sie in Ihrer Organisation funktionieren. Insbesondere können Sie Regeln zur Verringerung der Angriffsfläche, Exploit-Schutz, Netzwerkschutz und kontrollierten Ordnerzugriff im Überwachungsmodus aktivieren. Im Überwachungsmodus können Sie sehen, was passiert *wäre,* wenn Sie das Feature aktiviert hätten.

Sie können den Überwachungsmodus aktivieren, wenn Sie testen, wie die Features in Ihrer Organisation funktionieren. Dadurch wird sichergestellt, dass Ihre Branchen-Apps nicht betroffen sind. Sie können sich auch einen Eindruck davon verschaffen, wie viele verdächtige Dateiänderungsversuche über einen bestimmten Zeitraum erfolgen.

Die Features blockieren oder verhindern nicht, dass Apps, Skripts oder Dateien geändert werden. Das Windows Ereignisprotokoll zeichnet jedoch Ereignisse auf, als wären die Features vollständig aktiviert. Im Überwachungsmodus können Sie das Ereignisprotokoll überprüfen, um festzustellen, welche Auswirkungen das Feature hätte, wenn es aktiviert wäre.

Um die überwachten Einträge zu finden, wechseln Sie zu **Anwendungen und Dienste**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.

Sie können Defender für Endpunkt verwenden, um mehr Details für jedes Ereignis zu erhalten, insbesondere für die Untersuchung von Regeln zur Verringerung der Angriffsfläche. Mithilfe der Defender für Endpunkt-Konsole können Sie [Probleme im Rahmen der Warnungszeitachse und untersuchungsszenarien untersuchen.](investigate-alerts.md)

Sie können gruppenrichtlinien, PowerShell und Konfigurationsdienstanbieter (Configuration Service Providers, CSPs) verwenden, um den Überwachungsmodus zu aktivieren.

> [!TIP]
> Sie können auch die Website Windows Defender Testground unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass die Features funktionieren und wie sie funktionieren.

| Überwachungsoptionen | So aktivieren Sie den Überwachungsmodus | Anzeigen von Ereignissen |
|---------|---------|---------|
| Überwachung gilt für alle Ereignisse | [Kontrollierte Ordnerzugriff aktivieren](enable-controlled-folders.md) | [Kontrollierte Ordnerzugriffsereignisse](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| Überwachung gilt für einzelne Regeln | [Aktivieren der Regeln zur Verringerung der Angriffsfläche](enable-attack-surface-reduction.md) | [Regelereignisse zur Verringerung der Angriffsfläche](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| Überwachung gilt für alle Ereignisse | [Netzwerkschutz aktivieren](enable-network-protection.md) | [Netzwerkschutzereignisse](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| Die Überwachung gilt für einzelne Risikominderungen | [Aktivieren des Exploit-Schutzes](enable-exploit-protection.md) | [Exploit-Schutzereignisse](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


