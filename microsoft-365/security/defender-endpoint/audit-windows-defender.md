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
ms.technology: mde
ms.date: 06/02/2021
ms.topic: article
ms.openlocfilehash: 10351d97ba72945f929e042dc72a37724a1df291
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769605"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="33233-104">Testen der Verringerung der Angriffsfläche in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="33233-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="33233-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="33233-105">**Applies to:**</span></span>
- [<span data-ttu-id="33233-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="33233-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="33233-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33233-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="33233-108">Wenn Sie Teil des Sicherheitsteams Ihrer Organisation sind, können Sie Attack Surface Reduction-Funktionen so konfigurieren, dass sie im Überwachungsmodus ausgeführt werden, um zu sehen, wie sie in Ihrer Organisation funktionieren.</span><span class="sxs-lookup"><span data-stu-id="33233-108">If you're part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work in your organization.</span></span> <span data-ttu-id="33233-109">Insbesondere können Sie Regeln zur Verringerung der Angriffsfläche, Exploit-Schutz, Netzwerkschutz und kontrollierten Ordnerzugriff im Überwachungsmodus aktivieren.</span><span class="sxs-lookup"><span data-stu-id="33233-109">In particular, you can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="33233-110">Im Überwachungsmodus können Sie sehen, was passiert *wäre,* wenn Sie das Feature aktiviert hätten.</span><span class="sxs-lookup"><span data-stu-id="33233-110">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="33233-111">Sie können den Überwachungsmodus aktivieren, wenn Sie testen, wie die Features in Ihrer Organisation funktionieren.</span><span class="sxs-lookup"><span data-stu-id="33233-111">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="33233-112">Dadurch wird sichergestellt, dass Ihre Branchen-Apps nicht betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="33233-112">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="33233-113">Sie können sich auch einen Eindruck davon verschaffen, wie viele verdächtige Dateiänderungsversuche über einen bestimmten Zeitraum erfolgen.</span><span class="sxs-lookup"><span data-stu-id="33233-113">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="33233-114">Die Features blockieren oder verhindern nicht, dass Apps, Skripts oder Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="33233-114">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="33233-115">Das Windows Ereignisprotokoll zeichnet jedoch Ereignisse auf, als wären die Features vollständig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="33233-115">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="33233-116">Im Überwachungsmodus können Sie das Ereignisprotokoll überprüfen, um festzustellen, welche Auswirkungen das Feature hätte, wenn es aktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="33233-116">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="33233-117">Um die überwachten Einträge zu finden, wechseln Sie zu **Anwendungen und Dienste**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.</span><span class="sxs-lookup"><span data-stu-id="33233-117">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="33233-118">Sie können Defender für Endpunkt verwenden, um mehr Details für jedes Ereignis zu erhalten, insbesondere für die Untersuchung von Regeln zur Verringerung der Angriffsfläche.</span><span class="sxs-lookup"><span data-stu-id="33233-118">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="33233-119">Mithilfe der Defender für Endpunkt-Konsole können Sie [Probleme im Rahmen der Warnungszeitachse und untersuchungsszenarien untersuchen.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="33233-119">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="33233-120">Sie können gruppenrichtlinien, PowerShell und Konfigurationsdienstanbieter (Configuration Service Providers, CSPs) verwenden, um den Überwachungsmodus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="33233-120">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="33233-121">Sie können auch die Windows Defender Testground-Website unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass die Features funktionieren und wie sie funktionieren.</span><span class="sxs-lookup"><span data-stu-id="33233-121">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="33233-122">**Überwachungsoptionen**</span><span class="sxs-lookup"><span data-stu-id="33233-122">**Audit options**</span></span> | <span data-ttu-id="33233-123">**So aktivieren Sie den Überwachungsmodus**</span><span class="sxs-lookup"><span data-stu-id="33233-123">**How to enable audit mode**</span></span> | <span data-ttu-id="33233-124">**Anzeigen von Ereignissen**</span><span class="sxs-lookup"><span data-stu-id="33233-124">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="33233-125">Überwachung gilt für alle Ereignisse</span><span class="sxs-lookup"><span data-stu-id="33233-125">Audit applies to all events</span></span> | [<span data-ttu-id="33233-126">Kontrollierte Ordnerzugriff aktivieren</span><span class="sxs-lookup"><span data-stu-id="33233-126">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="33233-127">Kontrollierte Ordnerzugriffsereignisse</span><span class="sxs-lookup"><span data-stu-id="33233-127">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="33233-128">Überwachung gilt für einzelne Regeln</span><span class="sxs-lookup"><span data-stu-id="33233-128">Audit applies to individual rules</span></span> | [<span data-ttu-id="33233-129">Aktivieren der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="33233-129">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="33233-130">Regelereignisse zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="33233-130">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="33233-131">Überwachung gilt für alle Ereignisse</span><span class="sxs-lookup"><span data-stu-id="33233-131">Audit applies to all events</span></span> | [<span data-ttu-id="33233-132">Netzwerkschutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="33233-132">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="33233-133">Netzwerkschutzereignisse</span><span class="sxs-lookup"><span data-stu-id="33233-133">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="33233-134">Die Überwachung gilt für einzelne Risikominderungen</span><span class="sxs-lookup"><span data-stu-id="33233-134">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="33233-135">Aktivieren des Exploit-Schutzes</span><span class="sxs-lookup"><span data-stu-id="33233-135">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="33233-136">Exploit-Schutzereignisse</span><span class="sxs-lookup"><span data-stu-id="33233-136">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


