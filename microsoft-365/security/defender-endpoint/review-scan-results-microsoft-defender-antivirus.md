---
title: Überprüfen der Ergebnisse von Microsoft Defender AV-Scans
description: Überprüfen der Ergebnisse von Scans mit Microsoft Endpoint Configuration Manager, Microsoft Intune oder der Windows Security App
keywords: Scanergebnisse, Korrektur, vollständiger Scan, Schnellscan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b8a299f41541be878a9e9023ab330ea973646fd
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764145"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Überprüfen der Microsoft Defender Antivirus-Scanergebnisse

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Nach Abschluss einer Microsoft Defender [Antivirus-Überprüfung,](run-scan-microsoft-defender-antivirus.md) unabhängig davon, ob es sich um eine bedarfs- oder geplante Überprüfung [handelt,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)werden die Ergebnisse aufgezeichnet, und Sie können die Ergebnisse anzeigen. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Überprüfen der Scanergebnisse mithilfe von Configuration Manager

Weitere [Informationen finden Sie unter Überwachen des Endpoint Protection-Status](/configmgr/protect/deploy-use/monitor-endpoint-protection).

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>Verwenden von PowerShell-Cmdlets zum Überprüfen der Scanergebnisse

Das folgende Cmdlet gibt jede Erkennung auf dem Endpunkt zurück. Wenn es mehrere Erkennungen derselben Bedrohung gibt, wird jede Erkennung basierend auf dem Zeitpunkt jeder Erkennung separat aufgelistet:

```PowerShell
Get-MpThreatDetection
```

![Screenshot von PowerShell-Cmdlets und -Ausgaben](images/defender/wdav-get-mpthreatdetection.png)

Sie können angeben, dass die Ausgabe so begrenzt wird, dass nur die `-ThreatID` Erkennungen für eine bestimmte Bedrohung angezeigt werden.

Wenn Sie Bedrohungserkennungen auflisten möchten, aber Erkennungen derselben Bedrohung in einem einzigen Element kombinieren möchten, können Sie das folgende Cmdlet verwenden:

```PowerShell
Get-MpThreat
```

![Screenshot von PowerShell](images/defender/wdav-get-mpthreat.png)

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Überprüfen der Scanergebnisse mithilfe von Windows Management Instruction (WMI)

Verwenden Sie [ **die Get-Methode** der **MSFT_MpThreat** und **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) Klassen.


## <a name="related-articles"></a>Verwandte Artikel

- [Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus-Scans und -Korrekturen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)