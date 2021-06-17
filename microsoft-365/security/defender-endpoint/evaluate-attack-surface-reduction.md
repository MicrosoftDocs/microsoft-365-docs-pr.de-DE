---
title: Auswerten der Regeln zur Verringerung der Angriffsfläche
description: Erfahren Sie, wie Attack Surface Reduction Angriffe mit dem benutzerdefinierten Demotool blockieren und verhindern würde.
keywords: Attack Surface Reduction, Hips, Host Intrusion Prevention System, Schutzregeln, Anti-Exploit, Antiexploit, Exploit, Infektionsschutz, auswerten, testen, Demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a5fa8e46de0a6561d3377ce77e38bd59aa97f3c4
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984724"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="2ed90-104">Auswerten der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="2ed90-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ed90-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2ed90-105">**Applies to:**</span></span>

- [<span data-ttu-id="2ed90-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2ed90-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="2ed90-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ed90-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2ed90-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="2ed90-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2ed90-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="2ed90-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="2ed90-110">Regeln zur Verringerung der Angriffsfläche tragen dazu bei, Aktionen zu verhindern, die in der Regel von Schadsoftware verwendet werden, um Geräte oder Netzwerke zu kompromittieren.</span><span class="sxs-lookup"><span data-stu-id="2ed90-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="2ed90-111">Regeln zur Verringerung der Angriffsfläche helfen dabei, viele der gängigen Einstiegspunkte zu schließen, die von Schadsoftware und Ransomware verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ed90-111">Attack surface reduction rules help close off many of the common entry points used by malware and ransomware.</span></span>

<span data-ttu-id="2ed90-112">Legen Sie Regeln zur Verringerung der Angriffsfläche für Geräte fest, auf denen eine der folgenden Editionen und Versionen von Windows ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="2ed90-112">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="2ed90-113">Windows 10 Pro, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher</span><span class="sxs-lookup"><span data-stu-id="2ed90-113">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="2ed90-114">Windows 10 Enterprise, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher</span><span class="sxs-lookup"><span data-stu-id="2ed90-114">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="2ed90-115">Windows Server, [Version 1803 (Halbjährlicher Kanal)](/windows-server/get-started/whats-new-in-windows-server-1803) oder höher</span><span class="sxs-lookup"><span data-stu-id="2ed90-115">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="2ed90-116">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2ed90-116">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

> [!WARNING]
> <span data-ttu-id="2ed90-117">Das Aktivieren von Regeln zur Verringerung des Angriffsdiensts auf Windows Server 2016 kann zu unerwarteten Ergebnissen führen und sich auf die Serverleistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="2ed90-117">Enabling attack service reduction rules on Windows Server 2016 might lead to unexpected results, and impact server performance.</span></span> <span data-ttu-id="2ed90-118">Es wird nicht empfohlen, Regeln zur Verringerung der Angriffsfläche auf nicht unterstützten Plattformen zu aktivieren oder bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2ed90-118">We do not recommend enabling or deploying attack surface reduction rules to unsupported platforms.</span></span>

<span data-ttu-id="2ed90-119">Erfahren Sie, wie Sie Regeln zur Verringerung der Angriffsfläche auswerten, indem [Sie den Überwachungsmodus aktivieren,](audit-windows-defender.md) um das Feature direkt in Ihrer Organisation zu testen.</span><span class="sxs-lookup"><span data-stu-id="2ed90-119">Learn how to evaluate attack surface reduction rules by [enabling audit mode](audit-windows-defender.md) to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="2ed90-120">Sie können auch die Microsoft Defender für Endpunkt-Demoszenario-Website unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass das Feature funktioniert und wie es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2ed90-120">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="2ed90-121">Verwenden des Überwachungsmodus zum Messen der Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="2ed90-121">Use audit mode to measure impact</span></span>

<span data-ttu-id="2ed90-122">Aktivieren Sie die Regeln zur Verringerung der Angriffsfläche im Überwachungsmodus, um einen Datensatz von Apps anzuzeigen, die blockiert worden wären, wenn das Feature vollständig aktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="2ed90-122">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="2ed90-123">Testen Sie, wie das Feature in Ihrer Organisation funktioniert, um sicherzustellen, dass es sich nicht auf Ihre Branchen-Apps auswirkt.</span><span class="sxs-lookup"><span data-stu-id="2ed90-123">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="2ed90-124">Sie können sich auch einen Eindruck davon verschaffen, wie oft die Regeln während der normalen Verwendung ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="2ed90-124">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="2ed90-125">Verwenden Sie das folgende PowerShell-Cmdlet, um eine Regel zur Verringerung der Angriffsfläche im Überwachungsmodus zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="2ed90-125">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="2ed90-126">Gibt an, wo `<rule ID>` sich ein [GUID-Wert der Regel zur Verringerung der Angriffsfläche befindet.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="2ed90-126">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="2ed90-127">Verwenden Sie das folgende PowerShell-Cmdlet, um alle hinzugefügten Regeln zur Verringerung der Angriffsfläche im Überwachungsmodus zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="2ed90-127">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="2ed90-128">Wenn Sie die Funktionsweise der Regeln zur Verringerung der Angriffsfläche in Ihrer Organisation vollständig überwachen möchten, müssen Sie ein Verwaltungstool verwenden, um diese Einstellung auf Geräten in Ihren Netzwerken bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2ed90-128">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="2ed90-129">Sie können die Einstellung auch mithilfe von Gruppenrichtlinien, Intune oder Konfigurationsdienstanbietern (CSPs) für die mobile Geräteverwaltung (Mobile Device Management, MDM) konfigurieren und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2ed90-129">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="2ed90-130">Weitere Informationen finden Sie im Hauptartikel zu [Attack Surface Reduction-Regeln.](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="2ed90-130">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="2ed90-131">Überprüfen von Ereignissen zur Verringerung der Angriffsfläche in Windows Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="2ed90-131">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="2ed90-132">Um Apps zu überprüfen, die blockiert worden wären, öffnen Sie die Ereignisanzeige, und filtern Sie im Microsoft-Windows-Windows Defender/Betriebsprotokoll nach Ereignis-ID 1121.</span><span class="sxs-lookup"><span data-stu-id="2ed90-132">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="2ed90-133">In der folgenden Tabelle sind alle Netzwerkschutzereignisse aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="2ed90-133">The following table lists all network protection events.</span></span>

<span data-ttu-id="2ed90-134">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2ed90-134">Event ID</span></span> | <span data-ttu-id="2ed90-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ed90-135">Description</span></span>
-|-
 <span data-ttu-id="2ed90-136">5007</span><span class="sxs-lookup"><span data-stu-id="2ed90-136">5007</span></span> | <span data-ttu-id="2ed90-137">Ereignis, wenn Einstellungen geändert werden</span><span class="sxs-lookup"><span data-stu-id="2ed90-137">Event when settings are changed</span></span>
 <span data-ttu-id="2ed90-138">1121</span><span class="sxs-lookup"><span data-stu-id="2ed90-138">1121</span></span> | <span data-ttu-id="2ed90-139">Ereignis, wenn eine Regel zur Verringerung der Angriffsfläche im Blockierungsmodus ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="2ed90-139">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="2ed90-140">1122</span><span class="sxs-lookup"><span data-stu-id="2ed90-140">1122</span></span> | <span data-ttu-id="2ed90-141">Ereignis, wenn eine Regel zur Verringerung der Angriffsfläche im Überwachungsmodus ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="2ed90-141">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="2ed90-142">Anpassen der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="2ed90-142">Customize attack surface reduction rules</span></span>

<span data-ttu-id="2ed90-143">Während der Auswertung können Sie jede Regel einzeln konfigurieren oder bestimmte Dateien und Prozesse von der Auswertung durch das Feature ausschließen.</span><span class="sxs-lookup"><span data-stu-id="2ed90-143">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="2ed90-144">Informationen zum Konfigurieren des Features mit Verwaltungstools, einschließlich Gruppenrichtlinien und MDM-CSP-Richtlinien, finden Sie unter Anpassen von Regeln zur Verringerung der [Angriffsfläche.](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="2ed90-144">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ed90-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ed90-145">See also</span></span>

- [<span data-ttu-id="2ed90-146">Reduzieren von Angriffsflächen mit Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="2ed90-146">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
- [<span data-ttu-id="2ed90-147">Verwenden des Überwachungsmodus zum Auswerten Windows Defender</span><span class="sxs-lookup"><span data-stu-id="2ed90-147">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
- [<span data-ttu-id="2ed90-148">Häufig gestellte Fragen zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="2ed90-148">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
