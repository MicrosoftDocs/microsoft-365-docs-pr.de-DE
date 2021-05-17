---
title: Testen der Funktionsweise von Microsoft Defender for Endpoint-Features im Überwachungsmodus
description: Der Überwachungsmodus hilft Ihnen, zu sehen, wie Microsoft Defender for Endpoint Ihre Geräte schützen würde, wenn sie aktiviert wäre.
keywords: exploit guard, audit, auditing, mode, enabled, disabled, test, demo, evaluate, lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ce652d58be2d9ff28d82c088d5471a7bffdf6dc
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570972"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a><span data-ttu-id="e2d73-104">Testen der Funktionsweise von Microsoft Defender for Endpoint-Features im Überwachungsmodus</span><span class="sxs-lookup"><span data-stu-id="e2d73-104">Test how Microsoft Defender for Endpoint features work in audit mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e2d73-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e2d73-105">**Applies to:**</span></span>
- [<span data-ttu-id="e2d73-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e2d73-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e2d73-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2d73-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="e2d73-108">Sie können Angriffsflächenreduzierungsregeln, Exploitschutz, Netzwerkschutz und kontrollierten Ordnerzugriff im Überwachungsmodus aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e2d73-108">You can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="e2d73-109">Im Überwachungsmodus können Sie einen Datensatz darüber *sehen,* was passiert wäre, wenn Sie das Feature aktiviert hätten.</span><span class="sxs-lookup"><span data-stu-id="e2d73-109">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="e2d73-110">Möglicherweise möchten Sie den Überwachungsmodus aktivieren, wenn Sie testen, wie die Features in Ihrer Organisation funktionieren.</span><span class="sxs-lookup"><span data-stu-id="e2d73-110">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="e2d73-111">Dadurch wird sichergestellt, dass Ihre Business-Of-Business-Apps nicht betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="e2d73-111">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="e2d73-112">Sie können auch eine Vorstellung davon erhalten, wie viele verdächtige Dateiänderungsversuche über einen bestimmten Zeitraum erfolgen.</span><span class="sxs-lookup"><span data-stu-id="e2d73-112">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="e2d73-113">Die Features blockieren oder verhindern nicht, dass Apps, Skripts oder Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e2d73-113">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="e2d73-114">Das Ereignisprotokoll Windows jedoch Ereignisse auf, als wären die Features vollständig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e2d73-114">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="e2d73-115">Im Überwachungsmodus können Sie das Ereignisprotokoll überprüfen, um zu sehen, welche Auswirkungen das Feature hätte, wenn es aktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="e2d73-115">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="e2d73-116">Um die überwachten Einträge zu finden, wechseln Sie zu **Anwendungen und** Dienste  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.</span><span class="sxs-lookup"><span data-stu-id="e2d73-116">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="e2d73-117">Sie können Defender for Endpoint verwenden, um mehr Details für jedes Ereignis zu erhalten, insbesondere zum Untersuchen von Regeln zur Reduzierung der Angriffsfläche.</span><span class="sxs-lookup"><span data-stu-id="e2d73-117">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="e2d73-118">Mithilfe der Defender for Endpoint-Konsole können Sie Probleme im Rahmen der Warnungszeitachse und der [Untersuchungsszenarien untersuchen.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="e2d73-118">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="e2d73-119">Sie können Gruppenrichtlinien, PowerShell und Konfigurationsdienstanbieter (CsPs) verwenden, um den Überwachungsmodus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e2d73-119">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="e2d73-120">Sie können auch die Windows Defender Testground-Website unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass die Features funktionieren und wie sie funktionieren.</span><span class="sxs-lookup"><span data-stu-id="e2d73-120">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="e2d73-121">**Überwachungsoptionen**</span><span class="sxs-lookup"><span data-stu-id="e2d73-121">**Audit options**</span></span> | <span data-ttu-id="e2d73-122">**Aktivieren des Überwachungsmodus**</span><span class="sxs-lookup"><span data-stu-id="e2d73-122">**How to enable audit mode**</span></span> | <span data-ttu-id="e2d73-123">**Anzeigen von Ereignissen**</span><span class="sxs-lookup"><span data-stu-id="e2d73-123">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="e2d73-124">Überwachung gilt für alle Ereignisse</span><span class="sxs-lookup"><span data-stu-id="e2d73-124">Audit applies to all events</span></span> | [<span data-ttu-id="e2d73-125">Kontrollierte Ordnerzugriff aktivieren</span><span class="sxs-lookup"><span data-stu-id="e2d73-125">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="e2d73-126">Kontrollierte Ordnerzugriffsereignisse</span><span class="sxs-lookup"><span data-stu-id="e2d73-126">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="e2d73-127">Überwachung gilt für einzelne Regeln</span><span class="sxs-lookup"><span data-stu-id="e2d73-127">Audit applies to individual rules</span></span> | [<span data-ttu-id="e2d73-128">Aktivieren der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="e2d73-128">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="e2d73-129">Attack surface reduction rule events</span><span class="sxs-lookup"><span data-stu-id="e2d73-129">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="e2d73-130">Überwachung gilt für alle Ereignisse</span><span class="sxs-lookup"><span data-stu-id="e2d73-130">Audit applies to all events</span></span> | [<span data-ttu-id="e2d73-131">Aktivieren des Netzwerkschutzes</span><span class="sxs-lookup"><span data-stu-id="e2d73-131">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="e2d73-132">Netzwerkschutzereignisse</span><span class="sxs-lookup"><span data-stu-id="e2d73-132">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="e2d73-133">Überwachung gilt für einzelne Gegenmaßnahmen</span><span class="sxs-lookup"><span data-stu-id="e2d73-133">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="e2d73-134">Aktivieren des Exploit-Schutzes</span><span class="sxs-lookup"><span data-stu-id="e2d73-134">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="e2d73-135">Exploit-Schutzereignisse</span><span class="sxs-lookup"><span data-stu-id="e2d73-135">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a><span data-ttu-id="e2d73-136">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e2d73-136">Related topics</span></span>

* [<span data-ttu-id="e2d73-137">Schützen von Geräten vor Exploits</span><span class="sxs-lookup"><span data-stu-id="e2d73-137">Protect devices from exploits</span></span>](exploit-protection.md)
* [<span data-ttu-id="e2d73-138">Reduzieren von Angriffsoberflächen mit Regeln zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="e2d73-138">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="e2d73-139">Schützen Sie Ihr Netzwerk</span><span class="sxs-lookup"><span data-stu-id="e2d73-139">Protect your network</span></span>](network-protection.md)
* [<span data-ttu-id="e2d73-140">Schützen wichtiger Ordner</span><span class="sxs-lookup"><span data-stu-id="e2d73-140">Protect important folders</span></span>](controlled-folders.md)
