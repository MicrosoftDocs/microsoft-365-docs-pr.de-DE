---
title: Planen von Antivirusscans mithilfe Windows-Verwaltungsinstrumentation
description: Planen von Antivirusscans mithilfe von WMI
keywords: Schnellscan, vollständiger Scan, WMI, Zeitplan, Antivirus
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
ms.openlocfilehash: 1aa174f4601fb57eebbc4fb7c78e1809b9f072c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879708"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>Planen von Antivirusscans mit Windows Management Instrumentation (WMI)

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

In diesem Artikel wird beschrieben, wie Sie geplante Scans mithilfe von WMI konfigurieren. Weitere Informationen zum Planen von Scans und zu Scantypen finden Sie unter [Konfigurieren geplanter schneller oder vollständiger Microsoft Defender Antivirus Scans.](schedule-antivirus-scans.md) 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Verwenden von Windows Management Instruction (WMI) zum Planen von Scans

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>WMI zum Planen von Scans, wenn ein Endpunkt nicht verwendet wird

Verwenden Sie die [Set-Methode der MSFT_MpPreference-Klasse](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ScanOnlyIfIdleEnabled
```

Weitere Informationen zu APIs und zulässigen Parametern finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

> [!NOTE]
> Wenn Sie Scans für Zeiten planen, in denen Endpunkte nicht verwendet werden, berücksichtigen Scans nicht die CPU-Drosselungskonfiguration und nutzen die verfügbaren Ressourcen, um den Scan so schnell wie möglich abzuschließen.


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>WMI für die Planung von Scans zum Abschließen der Wartung

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-daily-scans"></a>WMI zum Planen von täglichen Scans

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ScanScheduleQuickScanTime
```

Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

