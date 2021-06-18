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
# <a name="review-microsoft-defender-antivirus-scan-results"></a><span data-ttu-id="cdde5-104">Überprüfen Microsoft Defender Antivirus Scanergebnisse</span><span class="sxs-lookup"><span data-stu-id="cdde5-104">Review Microsoft Defender Antivirus scan results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cdde5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cdde5-105">**Applies to:**</span></span>

- [<span data-ttu-id="cdde5-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cdde5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cdde5-107">Nachdem ein Microsoft Defender Antivirus Scan abgeschlossen ist, unabhängig davon, ob es sich um eine [bedarfsgesteuerte](run-scan-microsoft-defender-antivirus.md) oder [geplante Überprüfung](scheduled-catch-up-scans-microsoft-defender-antivirus.md)handelt, werden die Ergebnisse aufgezeichnet, und Sie können die Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cdde5-107">After a Microsoft Defender Antivirus scan completes, whether it is an [on-demand](run-scan-microsoft-defender-antivirus.md) or [scheduled scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md), the results are recorded and you can view the results.</span></span> 


## <a name="use-configuration-manager-to-review-scan-results"></a><span data-ttu-id="cdde5-108">Verwenden von Configuration Manager zum Überprüfen der Scanergebnisse</span><span class="sxs-lookup"><span data-stu-id="cdde5-108">Use Configuration Manager to review scan results</span></span>

<span data-ttu-id="cdde5-109">Weitere Informationen finden Sie [unter Überwachen Endpoint Protection Status.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="cdde5-109">See [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span>

## <a name="use-powershell-cmdlets-to-review-scan-results"></a><span data-ttu-id="cdde5-110">Verwenden von PowerShell-Cmdlets zum Überprüfen der Scanergebnisse</span><span class="sxs-lookup"><span data-stu-id="cdde5-110">Use PowerShell cmdlets to review scan results</span></span>

<span data-ttu-id="cdde5-111">Das folgende Cmdlet gibt jede Erkennung auf dem Endpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="cdde5-111">The following cmdlet will return each detection on the endpoint.</span></span> <span data-ttu-id="cdde5-112">Wenn mehrere Erkennungen derselben Bedrohung vorhanden sind, wird jede Erkennung basierend auf dem Zeitpunkt der jeweiligen Erkennung separat aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="cdde5-112">If there are multiple detections of the same threat, each detection will be listed separately, based on the time of each detection:</span></span>

```PowerShell
Get-MpThreatDetection
```

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="Screenshot der PowerShell-Cmdlets und -Ausgaben":::

<span data-ttu-id="cdde5-114">Sie können angeben, dass die Ausgabe so beschränkt werden `-ThreatID` soll, dass nur die Erkennungen für eine bestimmte Bedrohung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cdde5-114">You can specify `-ThreatID` to limit the output to only show the detections for a specific threat.</span></span>

<span data-ttu-id="cdde5-115">Wenn Sie Bedrohungserkennungen auflisten, aber Erkennungen derselben Bedrohung in einem einzigen Element kombinieren möchten, können Sie das folgende Cmdlet verwenden:</span><span class="sxs-lookup"><span data-stu-id="cdde5-115">If you want to list threat detections, but combine detections of the same threat into a single item, you can use the following cmdlet:</span></span>

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="PowerShell-Code":::

<span data-ttu-id="cdde5-117">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="cdde5-117">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a><span data-ttu-id="cdde5-118">Verwenden Windows Management Instruction (WMI) zum Überprüfen der Scanergebnisse</span><span class="sxs-lookup"><span data-stu-id="cdde5-118">Use Windows Management Instruction (WMI) to review scan results</span></span>

<span data-ttu-id="cdde5-119">Verwenden Sie die [ **Get-Methode** der **Klassen MSFT_MpThreat** und **MSFT_MpThreatDetection.**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="cdde5-119">Use the [**Get** method of the **MSFT_MpThreat** and **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) classes.</span></span>


## <a name="related-articles"></a><span data-ttu-id="cdde5-120">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="cdde5-120">Related articles</span></span>

- [<span data-ttu-id="cdde5-121">Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus Überprüfungen und Korrekturen</span><span class="sxs-lookup"><span data-stu-id="cdde5-121">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cdde5-122">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="cdde5-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)