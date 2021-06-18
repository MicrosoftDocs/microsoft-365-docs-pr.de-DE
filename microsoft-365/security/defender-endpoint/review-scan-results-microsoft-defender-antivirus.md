---
title: Überprüfen der Ergebnisse von Microsoft Defender AV-Scans
description: Überprüfen der Ergebnisse von Scans mit Microsoft Endpoint Configuration Manager, Microsoft Intune oder der Windows-Sicherheit-App
keywords: Scanergebnisse, Korrektur, vollständiger Scan, Schnellscan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: bc7c84e089b08c440512f8a8bf7583f41394f2ca
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007632"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Überprüfen Microsoft Defender Antivirus Scanergebnisse

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Nachdem ein Microsoft Defender Antivirus Scan abgeschlossen ist, unabhängig davon, ob es sich um eine [bedarfsgesteuerte](run-scan-microsoft-defender-antivirus.md) oder [geplante Überprüfung](scheduled-catch-up-scans-microsoft-defender-antivirus.md)handelt, werden die Ergebnisse aufgezeichnet, und Sie können die Ergebnisse anzeigen. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Verwenden von Configuration Manager zum Überprüfen der Scanergebnisse

Weitere Informationen finden Sie [unter Überwachen Endpoint Protection Status.](/configmgr/protect/deploy-use/monitor-endpoint-protection)

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>Verwenden von PowerShell-Cmdlets zum Überprüfen der Scanergebnisse

Das folgende Cmdlet gibt jede Erkennung auf dem Endpunkt zurück. Wenn mehrere Erkennungen derselben Bedrohung vorhanden sind, wird jede Erkennung basierend auf dem Zeitpunkt der jeweiligen Erkennung separat aufgelistet:

```PowerShell
Get-MpThreatDetection
```

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="Screenshot der PowerShell-Cmdlets und -Ausgaben":::

Sie können angeben, dass die Ausgabe so beschränkt werden `-ThreatID` soll, dass nur die Erkennungen für eine bestimmte Bedrohung angezeigt werden.

Wenn Sie Bedrohungserkennungen auflisten, aber Erkennungen derselben Bedrohung in einem einzigen Element kombinieren möchten, können Sie das folgende Cmdlet verwenden:

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="PowerShell-Code":::

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Verwenden Windows Management Instruction (WMI) zum Überprüfen der Scanergebnisse

Verwenden Sie die [ **Get-Methode** der **Klassen MSFT_MpThreat** und **MSFT_MpThreatDetection.**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Verwandte Artikel

- [Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus Überprüfungen und Korrekturen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)