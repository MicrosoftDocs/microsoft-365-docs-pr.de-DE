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
# <a name="schedule-antivirus-scans-using-powershell"></a><span data-ttu-id="978c3-104">Planen von Antivirusscans mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="978c3-104">Schedule antivirus scans using PowerShell</span></span>

<span data-ttu-id="978c3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="978c3-105">**Applies to:**</span></span>

- [<span data-ttu-id="978c3-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="978c3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="978c3-107">In diesem Artikel wird beschrieben, wie Sie geplante Scans mithilfe von PowerShell-Cmdlets konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="978c3-107">This article describes how to configure scheduled scans using PowerShell cmdlets.</span></span> <span data-ttu-id="978c3-108">Weitere Informationen zum Planen von Scans und zu Scantypen finden Sie unter [Konfigurieren geplanter schneller oder vollständiger Microsoft Defender Antivirus Scans.](schedule-antivirus-scans.md)</span><span class="sxs-lookup"><span data-stu-id="978c3-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="978c3-109">Verwenden von PowerShell-Cmdlets zum Planen von Scans</span><span class="sxs-lookup"><span data-stu-id="978c3-109">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="978c3-110">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="978c3-110">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="978c3-111">Weitere Informationen finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/) Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="978c3-111">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="978c3-112">PowerShell-Cmdlets zum Planen von Scans, wenn ein Endpunkt nicht verwendet wird</span><span class="sxs-lookup"><span data-stu-id="978c3-112">PowerShell cmdlets for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="978c3-113">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="978c3-113">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="978c3-114">Weitere Informationen finden Sie unter [PowerShell-Cmdlets verwenden, um Microsoft Defender Antivirus zu konfigurieren und auszuführen](use-powershell-cmdlets-microsoft-defender-antivirus.md) und unter [Defender-Cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="978c3-114">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

> [!NOTE]
> <span data-ttu-id="978c3-115">Wenn Sie Scans für Zeiten planen, in denen Endpunkte nicht verwendet werden, berücksichtigen Scans nicht die CPU-Drosselungskonfiguration und nutzen die verfügbaren Ressourcen, um den Scan so schnell wie möglich abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="978c3-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="978c3-116">PowerShell-Cmdlets für die Planung von Scans zum Abschließen der Wartung</span><span class="sxs-lookup"><span data-stu-id="978c3-116">PowerShell cmdlets for scheduling scans to complete remediation</span></span>

<span data-ttu-id="978c3-117">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="978c3-117">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="978c3-118">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="978c3-118">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a><span data-ttu-id="978c3-119">PowerShell-Cmdlets zum Planen von täglichen Scans</span><span class="sxs-lookup"><span data-stu-id="978c3-119">PowerShell cmdlets for scheduling daily scans</span></span>

<span data-ttu-id="978c3-120">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="978c3-120">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="978c3-121">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen von Microsoft Defender Antivirus-](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="978c3-121">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>


