---
title: Testen der Funktionsweise von Microsoft Defender for Endpoint-Features im Überwachungsmodus
description: Der Überwachungsmodus hilft Ihnen, zu sehen, wie Microsoft Defender for Endpoint Ihre Geräte schützen würde, wenn sie aktiviert wäre.
keywords: exploit guard, audit, auditing, mode, enabled, disabled, test, demo, evaluate, lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: dda0e58e587add2693f8448dd0833ce17706786c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067352"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a>Testen der Funktionsweise von Microsoft Defender for Endpoint-Features im Überwachungsmodus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Sie können Angriffsflächenreduzierungsregeln, Exploitschutz, Netzwerkschutz und kontrollierten Ordnerzugriff im Überwachungsmodus aktivieren. Im Überwachungsmodus können Sie einen Datensatz darüber *sehen,* was passiert wäre, wenn Sie das Feature aktiviert hätten.

Möglicherweise möchten Sie den Überwachungsmodus aktivieren, wenn Sie testen, wie die Features in Ihrer Organisation funktionieren. Dadurch wird sichergestellt, dass Ihre Business-Of-Business-Apps nicht betroffen sind. Sie können auch eine Vorstellung davon erhalten, wie viele verdächtige Dateiänderungsversuche über einen bestimmten Zeitraum erfolgen.

Die Features blockieren oder verhindern nicht, dass Apps, Skripts oder Dateien geändert werden. Im Windows-Ereignisprotokoll werden jedoch Ereignisse aufgezeichnet, als wären die Features vollständig aktiviert. Im Überwachungsmodus können Sie das Ereignisprotokoll überprüfen, um zu sehen, welche Auswirkungen das Feature hätte, wenn es aktiviert wäre.

Um die überwachten Einträge zu finden, wechseln Sie zu **Anwendungen und** Dienste  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.

Sie können Defender for Endpoint verwenden, um mehr Details für jedes Ereignis zu erhalten, insbesondere zum Untersuchen von Regeln zur Reduzierung der Angriffsfläche. Mithilfe der Defender for Endpoint-Konsole können Sie Probleme im Rahmen der Warnungszeitachse und der [Untersuchungsszenarien untersuchen.](investigate-alerts.md)

Sie können Gruppenrichtlinien, PowerShell und Konfigurationsdienstanbieter (CsPs) verwenden, um den Überwachungsmodus zu aktivieren.

> [!TIP]
> Sie können auch die Windows Defender Testground-Website unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass die Features funktionieren und wie sie funktionieren.

 **Überwachungsoptionen** | **Aktivieren des Überwachungsmodus** | **Anzeigen von Ereignissen**
|---------|---------|---------|
| Überwachung gilt für alle Ereignisse | [Aktivieren des kontrollierten Ordnerzugriffs](enable-controlled-folders.md) | [Kontrollierte Ordnerzugriffsereignisse](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| Überwachung gilt für einzelne Regeln | [Aktivieren von Regeln zur Reduzierung der Angriffsfläche](enable-attack-surface-reduction.md) | [Attack surface reduction rule events](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| Überwachung gilt für alle Ereignisse | [Aktivieren des Netzwerkschutzes](enable-network-protection.md) | [Netzwerkschutzereignisse](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| Überwachung gilt für einzelne Gegenmaßnahmen | [Aktivieren des Exploitschutzes](enable-exploit-protection.md) | [Exploit-Schutzereignisse](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a>Verwandte Themen

* [Schützen von Geräten vor Exploits](exploit-protection.md)
* [Reduzieren von Angriffsoberflächen mit Regeln zur Reduzierung der Angriffsfläche](attack-surface-reduction.md)
* [Schützen Ihres Netzwerks](network-protection.md)
* [Schützen wichtiger Ordner](controlled-folders.md)
