---
title: Auswerten des kontrollierten Ordnerzugriffs
description: Erfahren Sie, wie der kontrollierte Ordnerzugriff dazu beitragen kann, Dass Dateien von schädlichen Apps geändert werden.
keywords: Exploit-Schutz, Windows 10, Windows Defender, Ransomware, schützen, auswerten, testen, Demo, testen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 15ea4696052a6c987314e3c7b0dd282a49ed4df8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842914"
---
# <a name="evaluate-controlled-folder-access"></a>Auswerten des kontrollierten Ordnerzugriffs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


[Der kontrollierte Ordnerzugriff](controlled-folders.md) ist ein Feature, das Ihre Dokumente und Dateien vor Änderungen durch verdächtige oder schädliche Apps schützt. Der kontrollierte Ordnerzugriff wird auf Windows Server 2019- und Windows 10-Clients unterstützt.

Es ist besonders hilfreich, um sich vor [Ransomware](https://www.microsoft.com/wdsi/threats/ransomware) zu schützen, die versucht, Ihre Dateien zu verschlüsseln und sie als Host zu halten.

Dieser Artikel hilft Ihnen bei der Auswertung des kontrollierten Ordnerzugriffs. Es wird erläutert, wie Sie den Überwachungsmodus aktivieren, damit Sie das Feature direkt in Ihrer Organisation testen können.

> [!TIP]
> Sie können auch die Microsoft Defender für Endpunkt-Demoszenario-Website unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass das Feature funktioniert und wie es funktioniert.

## <a name="use-audit-mode-to-measure-impact"></a>Verwenden des Überwachungsmodus zum Messen der Auswirkungen

Aktivieren Sie den kontrollierten Ordnerzugriff im Überwachungsmodus, um zu sehen, was passiert *wäre,* wenn er vollständig aktiviert wäre. Testen Sie, wie das Feature in Ihrer Organisation funktioniert, um sicherzustellen, dass es sich nicht auf Ihre Branchen-Apps auswirkt. Sie können sich auch ein Bild davon machen, wie viele verdächtige Dateiänderungsversuche in der Regel über einen bestimmten Zeitraum erfolgen.

Verwenden Sie das folgende PowerShell-Cmdlet, um den Überwachungsmodus zu aktivieren:

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> Wenn Sie die Funktionsweise des kontrollierten Ordnerzugriffs in Ihrer Organisation vollständig überwachen möchten, müssen Sie ein Verwaltungstool verwenden, um diese Einstellung auf Geräten in Ihren Netzwerken bereitzustellen.
Sie können auch Gruppenrichtlinien, Intune, Mdm (Mobile Device Management) oder Microsoft Endpoint Manager verwenden, um die Einstellung zu konfigurieren und bereitzustellen, wie im Thema zum kontrollierten [Ordnerzugriff](controlled-folders.md)beschrieben.

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Überprüfen der Ereignisse des kontrollierten Ordnerzugriffs in Windows Ereignisanzeige

Die folgenden Kontrollierten Ordnerzugriffsereignisse werden in Windows Ereignisanzeige unter dem Ordner "Microsoft/Windows/Windows Defender/Operational" angezeigt.

Ereignis-ID | Beschreibung
-|-
 5007 | Ereignis, wenn Einstellungen geändert werden
 1124 | Überwachtes Ereignis für den kontrollierten Ordnerzugriff
 1123 | Blockiertes Ereignis für den kontrollierten Ordnerzugriff

> [!TIP]
> Sie können ein [Windows Ereignisweiterleitungsabonnement](/windows/win32/wec/setting-up-a-source-initiated-subscription) so konfigurieren, dass die Protokolle zentral erfasst werden. 

## <a name="customize-protected-folders-and-apps"></a>Anpassen geschützter Ordner und Apps

Während der Auswertung möchten Sie möglicherweise der Liste der geschützten Ordner hinzufügen oder bestimmten Apps erlauben, Dateien zu ändern.

Informationen zum Konfigurieren des Features mit Verwaltungstools, einschließlich Gruppenrichtlinien, PowerShell und MDM-Konfigurationsdienstanbietern (Configuration Service Providers, CSPs), finden Sie unter ["Schützen wichtiger Ordner mit kontrollierten Ordnerzugriff".](controlled-folders.md)

## <a name="see-also"></a>Siehe auch

* [Schützen wichtiger Ordner mit kontrollierten Ordnerzugriff](controlled-folders.md)
* [Auswerten des Microsoft Defender für Endpunkt](evaluate-mde.md)
* [Verwenden des Überwachungsmodus](audit-windows-defender.md)
