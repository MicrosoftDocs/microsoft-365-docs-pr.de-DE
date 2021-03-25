---
title: Bewerten des kontrollierten Ordnerzugriffs
description: Erfahren Sie, wie der kontrollierte Ordnerzugriff dazu beitragen kann, Dateien vor der Änderung durch schädliche Apps zu schützen.
keywords: Exploit-Schutz, Windows 10, Windows Defender, Ransomware, Schützen, Bewerten, Testen, Demo, Testen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e965e1a882dadfb565231074165507a6727b45c1
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218748"
---
# <a name="evaluate-controlled-folder-access"></a>Bewerten des kontrollierten Ordnerzugriffs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


[Der kontrollierte Ordnerzugriff](controlled-folders.md) ist ein Feature, das Ihre Dokumente und Dateien vor Änderungen durch verdächtige oder schädliche Apps schützt. Der kontrollierte Ordnerzugriff wird auf Windows Server 2019- und Windows 10-Clients unterstützt.

Es ist besonders hilfreich beim Schutz vor [Ransomware,](https://www.microsoft.com/wdsi/threats/ransomware) die versucht, Ihre Dateien zu verschlüsseln und als Host zu halten.

Dieser Artikel hilft Ihnen bei der Auswertung des kontrollierten Ordnerzugriffs. Es wird erläutert, wie Sie den Überwachungsmodus aktivieren, damit Sie das Feature direkt in Ihrer Organisation testen können.

> [!TIP]
> Sie können auch die Microsoft Defender for Endpoint-Demoszenariowebsite unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass das Feature funktioniert und wie es funktioniert.

## <a name="use-audit-mode-to-measure-impact"></a>Verwenden des Überwachungsmodus zum Messen der Auswirkung

Aktivieren Sie den kontrollierten Ordnerzugriff im  Überwachungsmodus, um einen Datensatz zu sehen, was passiert wäre, wenn er vollständig aktiviert wäre. Testen Sie, wie das Feature in Ihrer Organisation funktioniert, um sicherzustellen, dass es sich nicht auf Ihre Unternehmensanwendungen auswirken wird. Sie können auch eine Vorstellung davon erhalten, wie viele verdächtige Dateiänderungsversuche in der Regel über einen bestimmten Zeitraum erfolgen.

Verwenden Sie das folgende PowerShell-Cmdlet, um den Überwachungsmodus zu aktivieren:

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> Wenn Sie vollständig überwachen möchten, wie der kontrollierte Ordnerzugriff in Ihrer Organisation funktioniert, müssen Sie ein Verwaltungstool verwenden, um diese Einstellung auf Geräten in Ihren Netzwerken bereitstellen zu können.
Sie können die Einstellung auch mithilfe von Gruppenrichtlinien, Intune, mobiler Geräteverwaltung (Mobile Device Management, MDM) oder Microsoft Endpoint Manager konfigurieren und bereitstellen, wie im Thema "Zugriff auf hauptgesteuerte Ordner" [beschrieben.](controlled-folders.md)

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Überprüfen von Ereignissen für den kontrollierten Ordnerzugriff in der Windows-Ereignisanzeige

Die folgenden Ereignisse für den kontrollierten Ordnerzugriff werden in der Windows-Ereignisanzeige unter Dem Ordner Microsoft/Windows/Windows Defender/Operational angezeigt.

Ereignis-ID | Beschreibung
-|-
 5007 | Ereignis, wenn Einstellungen geändert werden
 1124 | Überwachtes kontrolliertes Ordnerzugriffsereignis
 1123 | Blockiertes Ereignis für den kontrollierten Ordnerzugriff

> [!TIP]
> Sie können ein [Windows Event Forwarding-Abonnement so konfigurieren,](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) dass die Protokolle zentral erfasst werden. 

## <a name="customize-protected-folders-and-apps"></a>Anpassen geschützter Ordner und Apps

Während der Auswertung können Sie der Liste der geschützten Ordner hinzufügen oder bestimmten Apps das Ändern von Dateien erlauben.

Weitere [Informationen finden](controlled-folders.md) Sie unter Schützen wichtiger Ordner mit kontrolliertem Ordnerzugriff zum Konfigurieren des Features mit Verwaltungstools, einschließlich Gruppenrichtlinien, PowerShell und MDM-Konfigurationsdienstanbietern (CSPs).

## <a name="see-also"></a>Siehe auch

* [Schützen wichtiger Ordner mit kontrolliertem Ordnerzugriff](controlled-folders.md)
* [Bewerten von Microsoft Defender for Endpoint](evaluate-mde.md)
* [Verwenden des Überwachungsmodus](audit-windows-defender.md)
