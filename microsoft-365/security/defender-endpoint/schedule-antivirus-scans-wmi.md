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
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a><span data-ttu-id="60424-104">Planen von Antivirusscans mit Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="60424-104">Schedule antivirus scans using Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="60424-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="60424-105">**Applies to:**</span></span>

- [<span data-ttu-id="60424-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="60424-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="60424-107">In diesem Artikel wird beschrieben, wie Sie geplante Scans mithilfe von WMI konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="60424-107">This article describes how to configure scheduled scans using WMI.</span></span> <span data-ttu-id="60424-108">Weitere Informationen zum Planen von Scans und zu Scantypen finden Sie unter [Konfigurieren geplanter schneller oder vollständiger Microsoft Defender Antivirus Scans.](schedule-antivirus-scans.md)</span><span class="sxs-lookup"><span data-stu-id="60424-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="60424-109">Verwenden von Windows Management Instruction (WMI) zum Planen von Scans</span><span class="sxs-lookup"><span data-stu-id="60424-109">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="60424-110">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="60424-110">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="60424-111">Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="60424-111">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="60424-112">WMI zum Planen von Scans, wenn ein Endpunkt nicht verwendet wird</span><span class="sxs-lookup"><span data-stu-id="60424-112">WMI for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="60424-113">Verwenden Sie die [Set-Methode der MSFT_MpPreference-Klasse](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="60424-113">Use the [Set method of the MSFT_MpPreference class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="60424-114">Weitere Informationen zu APIs und zulässigen Parametern finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="60424-114">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="60424-115">Wenn Sie Scans für Zeiten planen, in denen Endpunkte nicht verwendet werden, berücksichtigen Scans nicht die CPU-Drosselungskonfiguration und nutzen die verfügbaren Ressourcen, um den Scan so schnell wie möglich abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="60424-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="60424-116">WMI für die Planung von Scans zum Abschließen der Wartung</span><span class="sxs-lookup"><span data-stu-id="60424-116">WMI for scheduling scans to complete remediation</span></span>

<span data-ttu-id="60424-117">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="60424-117">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="60424-118">Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="60424-118">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="wmi-for-scheduling-daily-scans"></a><span data-ttu-id="60424-119">WMI zum Planen von täglichen Scans</span><span class="sxs-lookup"><span data-stu-id="60424-119">WMI for scheduling daily scans</span></span>

<span data-ttu-id="60424-120">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="60424-120">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="60424-121">Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="60424-121">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

