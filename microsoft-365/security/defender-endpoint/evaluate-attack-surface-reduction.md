---
title: Auswerten der Regeln zur Verringerung der Angriffsfläche
description: Erfahren Sie, wie die Reduzierung der Angriffsfläche Angriffe mit dem benutzerdefinierten Demotool blockieren und verhindern würde.
keywords: Attack surface reduction, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, evaluate, test, demo
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
ms.openlocfilehash: 07573fd92643ce5fdf3e9140031bf5f15ae8f7aa
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570339"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="c366b-104">Auswerten der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="c366b-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c366b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c366b-105">**Applies to:**</span></span>
- [<span data-ttu-id="c366b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c366b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="c366b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c366b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c366b-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="c366b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c366b-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c366b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="c366b-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span><span class="sxs-lookup"><span data-stu-id="c366b-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="c366b-111">Legen Sie Regeln zur Reduzierung der Angriffsfläche für Geräte mit einer der folgenden Editionen und Versionen von Windows ein:</span><span class="sxs-lookup"><span data-stu-id="c366b-111">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="c366b-112">Windows 10 Pro, [Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) oder höher</span><span class="sxs-lookup"><span data-stu-id="c366b-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="c366b-113">Windows 10 Enterprise, [Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) oder höher</span><span class="sxs-lookup"><span data-stu-id="c366b-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="c366b-114">Windows Server, [Version 1803 (Halbjährskanal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) oder höher</span><span class="sxs-lookup"><span data-stu-id="c366b-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="c366b-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c366b-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="c366b-116">Erfahren Sie, wie Sie Regeln zur Reduzierung der Angriffsfläche auswerten, indem Sie den Überwachungsmodus aktivieren, um das Feature direkt in Ihrer Organisation zu testen.</span><span class="sxs-lookup"><span data-stu-id="c366b-116">Learn how to evaluate attack surface reduction rules by enabling audit mode to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="c366b-117">Sie können auch die Microsoft Defender for Endpoint-Demoszenariowebsite unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass das Feature funktioniert und wie es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="c366b-117">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="c366b-118">Verwenden des Überwachungsmodus zum Messen der Auswirkung</span><span class="sxs-lookup"><span data-stu-id="c366b-118">Use audit mode to measure impact</span></span>

<span data-ttu-id="c366b-119">Aktivieren Sie Regeln zur Reduzierung der Angriffsfläche im Überwachungsmodus, um einen Datensatz mit Apps anzeigen zu können, die blockiert worden wären, wenn das Feature vollständig aktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="c366b-119">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="c366b-120">Testen Sie, wie das Feature in Ihrer Organisation funktioniert, um sicherzustellen, dass es sich nicht auf Ihre Unternehmensanwendungen auswirken wird.</span><span class="sxs-lookup"><span data-stu-id="c366b-120">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="c366b-121">Sie können auch eine Vorstellung davon erhalten, wie oft die Regeln während der normalen Verwendung löschen.</span><span class="sxs-lookup"><span data-stu-id="c366b-121">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="c366b-122">Verwenden Sie das folgende PowerShell-Cmdlet, um eine Regel zur Reduzierung der Angriffsfläche im Überwachungsmodus zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="c366b-122">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="c366b-123">Dabei `<rule ID>` ist ein [GUID-Wert der Regel zur Reduzierung der Angriffsfläche .](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="c366b-123">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="c366b-124">Verwenden Sie das folgende PowerShell-Cmdlet, um alle hinzugefügten Regeln zur Reduzierung der Angriffsfläche im Überwachungsmodus zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="c366b-124">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="c366b-125">Wenn Sie vollständig überwachen möchten, wie Regeln zur Reduzierung der Angriffsfläche in Ihrer Organisation funktionieren, müssen Sie ein Verwaltungstool verwenden, um diese Einstellung auf Geräten in Ihren Netzwerken bereitstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="c366b-125">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="c366b-126">Sie können die Einstellung auch mithilfe von Gruppenrichtlinien, Intune oder Konfigurationsdienstanbietern für die mobile Geräteverwaltung (Mobile Device Management, MDM) konfigurieren und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c366b-126">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="c366b-127">Weitere Informationen finden Sie im Hauptartikel [attack surface reduction rules.](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="c366b-127">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="c366b-128">Überprüfen von Ereignissen zur Reduzierung der Angriffsfläche in der Windows-Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="c366b-128">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="c366b-129">Öffnen Sie die Ereignisanzeige, und filtern Sie im Microsoft-Windows-Windows Defender/Operational-Protokoll nach Ereignis-ID 1121, um apps zu überprüfen, die blockiert worden wären.</span><span class="sxs-lookup"><span data-stu-id="c366b-129">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="c366b-130">In der folgenden Tabelle sind alle Netzwerkschutzereignisse aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c366b-130">The following table lists all network protection events.</span></span>

<span data-ttu-id="c366b-131">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c366b-131">Event ID</span></span> | <span data-ttu-id="c366b-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c366b-132">Description</span></span>
-|-
 <span data-ttu-id="c366b-133">5007</span><span class="sxs-lookup"><span data-stu-id="c366b-133">5007</span></span> | <span data-ttu-id="c366b-134">Ereignis, wenn Einstellungen geändert werden</span><span class="sxs-lookup"><span data-stu-id="c366b-134">Event when settings are changed</span></span>
 <span data-ttu-id="c366b-135">1121</span><span class="sxs-lookup"><span data-stu-id="c366b-135">1121</span></span> | <span data-ttu-id="c366b-136">Ereignis, wenn eine Regel zur Reduzierung der Angriffsfläche im Blockmodus gestartet wird</span><span class="sxs-lookup"><span data-stu-id="c366b-136">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="c366b-137">1122</span><span class="sxs-lookup"><span data-stu-id="c366b-137">1122</span></span> | <span data-ttu-id="c366b-138">Ereignis, wenn eine Regel zur Reduzierung der Angriffsfläche im Überwachungsmodus gestartet wird</span><span class="sxs-lookup"><span data-stu-id="c366b-138">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="c366b-139">Anpassen der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="c366b-139">Customize attack surface reduction rules</span></span>

<span data-ttu-id="c366b-140">Während der Auswertung können Sie jede Regel einzeln konfigurieren oder bestimmte Dateien und Prozesse von der Auswertung durch das Feature ausschließen.</span><span class="sxs-lookup"><span data-stu-id="c366b-140">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="c366b-141">Informationen zum Konfigurieren des Features mit Verwaltungstools, einschließlich Gruppenrichtlinien und MDM-CSP-Richtlinien, finden Sie unter [Customize attack surface reduction rules.](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="c366b-141">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="c366b-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c366b-142">See also</span></span>

* [<span data-ttu-id="c366b-143">Reduzieren von Angriffsoberflächen mit Regeln zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="c366b-143">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="c366b-144">Verwenden des Überwachungsmodus zum Auswerten Windows Defender</span><span class="sxs-lookup"><span data-stu-id="c366b-144">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
* [<span data-ttu-id="c366b-145">FAQ zu Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="c366b-145">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
