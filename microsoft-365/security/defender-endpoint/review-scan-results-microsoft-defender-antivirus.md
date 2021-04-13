---
title: Überprüfen der Ergebnisse von Microsoft Defender AV-Scans
description: Überprüfen der Ergebnisse von Scans mit Microsoft Endpoint Configuration Manager, Microsoft Intune oder der Windows Security App
keywords: Scanergebnisse, Korrektur, vollständiger Scan, Schnellscan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8fe2810ce18589d3131aa17f25ccfb01ec26b892
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690569"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a><span data-ttu-id="80b0f-104">Überprüfen der Microsoft Defender Antivirus-Scanergebnisse</span><span class="sxs-lookup"><span data-stu-id="80b0f-104">Review Microsoft Defender Antivirus scan results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="80b0f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="80b0f-105">**Applies to:**</span></span>

- [<span data-ttu-id="80b0f-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="80b0f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="80b0f-107">Nach Abschluss einer Microsoft Defender [Antivirus-Überprüfung,](run-scan-microsoft-defender-antivirus.md) unabhängig davon, ob es sich um eine bedarfs- oder geplante Überprüfung [handelt,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)werden die Ergebnisse aufgezeichnet, und Sie können die Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="80b0f-107">After a Microsoft Defender Antivirus scan completes, whether it is an [on-demand](run-scan-microsoft-defender-antivirus.md) or [scheduled scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md), the results are recorded and you can view the results.</span></span> 


## <a name="use-configuration-manager-to-review-scan-results"></a><span data-ttu-id="80b0f-108">Überprüfen der Scanergebnisse mithilfe von Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="80b0f-108">Use Configuration Manager to review scan results</span></span>

<span data-ttu-id="80b0f-109">Weitere [Informationen finden Sie unter Überwachen des Endpoint Protection-Status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="80b0f-109">See [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span>

## <a name="use-powershell-cmdlets-to-review-scan-results"></a><span data-ttu-id="80b0f-110">Verwenden von PowerShell-Cmdlets zum Überprüfen der Scanergebnisse</span><span class="sxs-lookup"><span data-stu-id="80b0f-110">Use PowerShell cmdlets to review scan results</span></span>

<span data-ttu-id="80b0f-111">Das folgende Cmdlet gibt jede Erkennung auf dem Endpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="80b0f-111">The following cmdlet will return each detection on the endpoint.</span></span> <span data-ttu-id="80b0f-112">Wenn es mehrere Erkennungen derselben Bedrohung gibt, wird jede Erkennung basierend auf dem Zeitpunkt jeder Erkennung separat aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="80b0f-112">If there are multiple detections of the same threat, each detection will be listed separately, based on the time of each detection:</span></span>

```PowerShell
Get-MpThreatDetection
```

![Screenshot von PowerShell-Cmdlets und -Ausgaben](images/defender/wdav-get-mpthreatdetection.png)

<span data-ttu-id="80b0f-114">Sie können angeben, dass die Ausgabe so begrenzt wird, dass nur die `-ThreatID` Erkennungen für eine bestimmte Bedrohung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="80b0f-114">You can specify `-ThreatID` to limit the output to only show the detections for a specific threat.</span></span>

<span data-ttu-id="80b0f-115">Wenn Sie Bedrohungserkennungen auflisten möchten, aber Erkennungen derselben Bedrohung in einem einzigen Element kombinieren möchten, können Sie das folgende Cmdlet verwenden:</span><span class="sxs-lookup"><span data-stu-id="80b0f-115">If you want to list threat detections, but combine detections of the same threat into a single item, you can use the following cmdlet:</span></span>

```PowerShell
Get-MpThreat
```

![Screenshot von PowerShell](images/defender/wdav-get-mpthreat.png)

<span data-ttu-id="80b0f-117">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="80b0f-117">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a><span data-ttu-id="80b0f-118">Überprüfen der Scanergebnisse mithilfe von Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="80b0f-118">Use Windows Management Instruction (WMI) to review scan results</span></span>

<span data-ttu-id="80b0f-119">Verwenden Sie [ **die Get-Methode** der **MSFT_MpThreat** und **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) Klassen.</span><span class="sxs-lookup"><span data-stu-id="80b0f-119">Use the [**Get** method of the **MSFT_MpThreat** and **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) classes.</span></span>


## <a name="related-articles"></a><span data-ttu-id="80b0f-120">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="80b0f-120">Related articles</span></span>

- [<span data-ttu-id="80b0f-121">Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus-Scans und -Korrekturen</span><span class="sxs-lookup"><span data-stu-id="80b0f-121">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="80b0f-122">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="80b0f-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)