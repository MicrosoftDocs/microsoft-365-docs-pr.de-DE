---
title: Testen der Funktionsweise von Microsoft Defender für Endpunkt-Features im Überwachungsmodus
description: Der Überwachungsmodus hilft Ihnen zu sehen, wie Microsoft Defender für Endpunkt Ihre Geräte schützen würde, wenn sie aktiviert wäre.
keywords: Exploit-Schutz, Überwachung, Überwachung, Modus, aktiviert, deaktiviert, Testen, Demo, auswerten, Lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985096"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="93aac-104">Testen der Verringerung der Angriffsfläche in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="93aac-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="93aac-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="93aac-105">**Applies to:**</span></span>

- [<span data-ttu-id="93aac-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="93aac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="93aac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93aac-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="93aac-108">Als Teil des Sicherheitsteams Ihrer Organisation können Sie Attack Surface Reduction-Funktionen so konfigurieren, dass sie im Überwachungsmodus ausgeführt werden, um zu sehen, wie sie funktionieren.</span><span class="sxs-lookup"><span data-stu-id="93aac-108">As part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work.</span></span> <span data-ttu-id="93aac-109">Im Überwachungsmodus können Sie Folgendes aktivieren:</span><span class="sxs-lookup"><span data-stu-id="93aac-109">In audit mode, you can enable:</span></span>

- <span data-ttu-id="93aac-110">Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="93aac-110">Attack surface reduction rules</span></span>
- <span data-ttu-id="93aac-111">Exploit-Schutz</span><span class="sxs-lookup"><span data-stu-id="93aac-111">Exploit protection</span></span>
- <span data-ttu-id="93aac-112">Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="93aac-112">Network protection</span></span>
- <span data-ttu-id="93aac-113">Und kontrollierter Ordnerzugriff im Überwachungsmodus</span><span class="sxs-lookup"><span data-stu-id="93aac-113">And controlled folder access in audit mode</span></span>

<span data-ttu-id="93aac-114">Im Überwachungsmodus können Sie sehen, was passiert *wäre,* wenn Sie das Feature aktiviert hätten.</span><span class="sxs-lookup"><span data-stu-id="93aac-114">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="93aac-115">Sie können den Überwachungsmodus aktivieren, wenn Sie testen, wie die Features funktionieren.</span><span class="sxs-lookup"><span data-stu-id="93aac-115">You can enable audit mode when testing how the features will work.</span></span> <span data-ttu-id="93aac-116">Dadurch wird sichergestellt, dass Ihre Branchen-Apps nicht betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="93aac-116">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="93aac-117">Sie können sich auch einen Eindruck davon verschaffen, wie viele verdächtige Dateiänderungsversuche über einen bestimmten Zeitraum erfolgen.</span><span class="sxs-lookup"><span data-stu-id="93aac-117">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="93aac-118">Die Features blockieren oder verhindern nicht, dass Apps, Skripts oder Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="93aac-118">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="93aac-119">Das Windows Ereignisprotokoll zeichnet jedoch Ereignisse auf, als wären die Features vollständig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="93aac-119">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="93aac-120">Im Überwachungsmodus können Sie das Ereignisprotokoll überprüfen, um festzustellen, welche Auswirkungen das Feature hätte, wenn es aktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="93aac-120">With audit mode, you can review the event log to see what affect the feature would have had if it was enabled.</span></span>

<span data-ttu-id="93aac-121">Um die überwachten Einträge zu finden, wechseln Sie zu **Anwendungen und Dienste**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.</span><span class="sxs-lookup"><span data-stu-id="93aac-121">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="93aac-122">Verwenden Sie Defender für Endpunkt, um mehr Details für jedes Ereignis zu erhalten, insbesondere für die Untersuchung von Regeln zur Verringerung der Angriffsfläche.</span><span class="sxs-lookup"><span data-stu-id="93aac-122">Use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="93aac-123">Mithilfe der Defender für Endpunkt-Konsole können Sie [Probleme im Rahmen der Warnungszeitachse und untersuchungsszenarien untersuchen.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="93aac-123">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="93aac-124">Sie können den Überwachungsmodus mithilfe von Gruppenrichtlinien, PowerShell und Konfigurationsdienstanbietern (Configuration Service Providers, CSPs) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="93aac-124">You can enable audit mode using Group Policy, PowerShell, and configuration service providers (CSPs).</span></span>

> [!TIP]
> <span data-ttu-id="93aac-125">Sie können auch die Website Windows Defender Testground unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass die Features funktionieren und wie sie funktionieren.</span><span class="sxs-lookup"><span data-stu-id="93aac-125">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="93aac-126">Überwachungsoptionen</span><span class="sxs-lookup"><span data-stu-id="93aac-126">Audit options</span></span> | <span data-ttu-id="93aac-127">So aktivieren Sie den Überwachungsmodus</span><span class="sxs-lookup"><span data-stu-id="93aac-127">How to enable audit mode</span></span> | <span data-ttu-id="93aac-128">Anzeigen von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="93aac-128">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="93aac-129">Überwachung gilt für alle Ereignisse</span><span class="sxs-lookup"><span data-stu-id="93aac-129">Audit applies to all events</span></span> | [<span data-ttu-id="93aac-130">Kontrollierte Ordnerzugriff aktivieren</span><span class="sxs-lookup"><span data-stu-id="93aac-130">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="93aac-131">Kontrollierte Ordnerzugriffsereignisse</span><span class="sxs-lookup"><span data-stu-id="93aac-131">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="93aac-132">Überwachung gilt für einzelne Regeln</span><span class="sxs-lookup"><span data-stu-id="93aac-132">Audit applies to individual rules</span></span> | [<span data-ttu-id="93aac-133">Aktivieren der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="93aac-133">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="93aac-134">Regelereignisse zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="93aac-134">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="93aac-135">Überwachung gilt für alle Ereignisse</span><span class="sxs-lookup"><span data-stu-id="93aac-135">Audit applies to all events</span></span> | [<span data-ttu-id="93aac-136">Netzwerkschutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="93aac-136">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="93aac-137">Netzwerkschutzereignisse</span><span class="sxs-lookup"><span data-stu-id="93aac-137">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="93aac-138">Die Überwachung gilt für einzelne Risikominderungen</span><span class="sxs-lookup"><span data-stu-id="93aac-138">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="93aac-139">Aktivieren des Exploit-Schutzes</span><span class="sxs-lookup"><span data-stu-id="93aac-139">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="93aac-140">Exploit-Schutzereignisse</span><span class="sxs-lookup"><span data-stu-id="93aac-140">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
