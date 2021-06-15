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
ms.openlocfilehash: c2ff6eac3254e855d4858edc218ae5df034352e4
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925659"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a8538-104">Testen der Verringerung der Angriffsfläche in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a8538-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a8538-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a8538-105">**Applies to:**</span></span>
- [<span data-ttu-id="a8538-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a8538-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a8538-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a8538-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="a8538-108">Wenn Sie Teil des Sicherheitsteams Ihrer Organisation sind, können Sie Attack Surface Reduction-Funktionen so konfigurieren, dass sie im Überwachungsmodus ausgeführt werden, um zu sehen, wie sie in Ihrer Organisation funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a8538-108">If you're part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work in your organization.</span></span> <span data-ttu-id="a8538-109">Insbesondere können Sie Regeln zur Verringerung der Angriffsfläche, Exploit-Schutz, Netzwerkschutz und kontrollierten Ordnerzugriff im Überwachungsmodus aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a8538-109">In particular, you can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="a8538-110">Im Überwachungsmodus können Sie sehen, was passiert *wäre,* wenn Sie das Feature aktiviert hätten.</span><span class="sxs-lookup"><span data-stu-id="a8538-110">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="a8538-111">Sie können den Überwachungsmodus aktivieren, wenn Sie testen, wie die Features in Ihrer Organisation funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a8538-111">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="a8538-112">Dadurch wird sichergestellt, dass Ihre Branchen-Apps nicht betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="a8538-112">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="a8538-113">Sie können sich auch einen Eindruck davon verschaffen, wie viele verdächtige Dateiänderungsversuche über einen bestimmten Zeitraum erfolgen.</span><span class="sxs-lookup"><span data-stu-id="a8538-113">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="a8538-114">Die Features blockieren oder verhindern nicht, dass Apps, Skripts oder Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a8538-114">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="a8538-115">Das Windows Ereignisprotokoll zeichnet jedoch Ereignisse auf, als wären die Features vollständig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a8538-115">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="a8538-116">Im Überwachungsmodus können Sie das Ereignisprotokoll überprüfen, um festzustellen, welche Auswirkungen das Feature hätte, wenn es aktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="a8538-116">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="a8538-117">Um die überwachten Einträge zu finden, wechseln Sie zu **Anwendungen und Dienste**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.</span><span class="sxs-lookup"><span data-stu-id="a8538-117">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="a8538-118">Sie können Defender für Endpunkt verwenden, um mehr Details für jedes Ereignis zu erhalten, insbesondere für die Untersuchung von Regeln zur Verringerung der Angriffsfläche.</span><span class="sxs-lookup"><span data-stu-id="a8538-118">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="a8538-119">Mithilfe der Defender für Endpunkt-Konsole können Sie [Probleme im Rahmen der Warnungszeitachse und untersuchungsszenarien untersuchen.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="a8538-119">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="a8538-120">Sie können gruppenrichtlinien, PowerShell und Konfigurationsdienstanbieter (Configuration Service Providers, CSPs) verwenden, um den Überwachungsmodus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a8538-120">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="a8538-121">Sie können auch die Website Windows Defender Testground unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass die Features funktionieren und wie sie funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a8538-121">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="a8538-122">Überwachungsoptionen</span><span class="sxs-lookup"><span data-stu-id="a8538-122">Audit options</span></span> | <span data-ttu-id="a8538-123">So aktivieren Sie den Überwachungsmodus</span><span class="sxs-lookup"><span data-stu-id="a8538-123">How to enable audit mode</span></span> | <span data-ttu-id="a8538-124">Anzeigen von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="a8538-124">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="a8538-125">Überwachung gilt für alle Ereignisse</span><span class="sxs-lookup"><span data-stu-id="a8538-125">Audit applies to all events</span></span> | [<span data-ttu-id="a8538-126">Kontrollierte Ordnerzugriff aktivieren</span><span class="sxs-lookup"><span data-stu-id="a8538-126">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="a8538-127">Kontrollierte Ordnerzugriffsereignisse</span><span class="sxs-lookup"><span data-stu-id="a8538-127">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="a8538-128">Überwachung gilt für einzelne Regeln</span><span class="sxs-lookup"><span data-stu-id="a8538-128">Audit applies to individual rules</span></span> | [<span data-ttu-id="a8538-129">Aktivieren der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="a8538-129">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="a8538-130">Regelereignisse zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="a8538-130">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="a8538-131">Überwachung gilt für alle Ereignisse</span><span class="sxs-lookup"><span data-stu-id="a8538-131">Audit applies to all events</span></span> | [<span data-ttu-id="a8538-132">Netzwerkschutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="a8538-132">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="a8538-133">Netzwerkschutzereignisse</span><span class="sxs-lookup"><span data-stu-id="a8538-133">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="a8538-134">Die Überwachung gilt für einzelne Risikominderungen</span><span class="sxs-lookup"><span data-stu-id="a8538-134">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="a8538-135">Aktivieren des Exploit-Schutzes</span><span class="sxs-lookup"><span data-stu-id="a8538-135">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="a8538-136">Exploit-Schutzereignisse</span><span class="sxs-lookup"><span data-stu-id="a8538-136">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


