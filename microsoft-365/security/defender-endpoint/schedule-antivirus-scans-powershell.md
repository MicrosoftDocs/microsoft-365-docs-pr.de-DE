---
title: Planen von Antivirusscans mithilfe von PowerShell
description: Planen von Antivirusscans mithilfe von PowerShell
keywords: Schnellscan, vollständiger Scan, Antivirus, Zeitplan, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 73ba654dd312c63651f0cf43244796e94e8ad55b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879715"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>Planen von Antivirusscans mithilfe von PowerShell

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

In diesem Artikel wird beschrieben, wie Sie geplante Scans mithilfe von PowerShell-Cmdlets konfigurieren. Weitere Informationen zum Planen von Scans und zu Scantypen finden Sie unter [Konfigurieren geplanter schneller oder vollständiger Microsoft Defender Antivirus Scans.](schedule-antivirus-scans.md) 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>Verwenden von PowerShell-Cmdlets zum Planen von Scans

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Weitere Informationen finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/) Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus.

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>PowerShell-Cmdlets zum Planen von Scans, wenn ein Endpunkt nicht verwendet wird

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Weitere Informationen finden Sie unter [PowerShell-Cmdlets verwenden, um Microsoft Defender Antivirus zu konfigurieren und auszuführen](use-powershell-cmdlets-microsoft-defender-antivirus.md) und unter [Defender-Cmdlets](/powershell/module/defender/).

> [!NOTE]
> Wenn Sie Scans für Zeiten planen, in denen Endpunkte nicht verwendet werden, berücksichtigen Scans nicht die CPU-Drosselungskonfiguration und nutzen die verfügbaren Ressourcen, um den Scan so schnell wie möglich abzuschließen.

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>PowerShell-Cmdlets für die Planung von Scans zum Abschließen der Wartung

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/)

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>PowerShell-Cmdlets zum Planen von täglichen Scans

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen von Microsoft Defender Antivirus-](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/)


