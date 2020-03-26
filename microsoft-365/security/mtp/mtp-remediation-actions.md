---
title: Behebungsaktionen nach automatisierten Untersuchungen im Microsoft Threat Protection
description: Erhalten einer Übersicht Überkorrektur Aktionen, die automatisierte Untersuchungen im Microsoft Threat Protection ausführen
keywords: automatisch, Untersuchung, Warnung, Trigger, Aktion, Wartung
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: ca0c557de24320692d903a1136fc434d635f0507
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955591"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="45b39-104">Behebungsaktionen nach automatisierten Untersuchungen im Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="45b39-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="45b39-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="45b39-105">**Applies to:**</span></span>
- <span data-ttu-id="45b39-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="45b39-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="45b39-107">Wartungsaktionen</span><span class="sxs-lookup"><span data-stu-id="45b39-107">Remediation actions</span></span>

<span data-ttu-id="45b39-108">Während und nach einer automatischen Untersuchung im Microsoft Threat Protection werden Korrekturaktionen für böswillige oder verdächtige Elemente identifiziert.</span><span class="sxs-lookup"><span data-stu-id="45b39-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="45b39-109">Einige Arten von Korrekturaktionen werden auf Geräten durchgeführt, die auch als Endpunkte bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="45b39-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="45b39-110">Für e-Mail-Inhalte werden andere Korrekturaktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="45b39-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="45b39-111">Automatische Untersuchungen werden abgeschlossen, nachdem Korrekturaktionen durchgeführt, genehmigt oder abgelehnt wurden.</span><span class="sxs-lookup"><span data-stu-id="45b39-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="45b39-112">In der folgenden Tabelle werden Korrekturaktionen zusammengefasst, die derzeit in Microsoft Threat Protection unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="45b39-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="45b39-113">Geräte (Endpunkt)-Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="45b39-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="45b39-114">Wartungsaktionen für E-Mails</span><span class="sxs-lookup"><span data-stu-id="45b39-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="45b39-115">Quarantänedatei</span><span class="sxs-lookup"><span data-stu-id="45b39-115">Quarantine file</span></span><br/><span data-ttu-id="45b39-116">Registrierungsschlüssel entfernen</span><span class="sxs-lookup"><span data-stu-id="45b39-116">Remove registry key</span></span><br/><span data-ttu-id="45b39-117">Prozess abbrechen</span><span class="sxs-lookup"><span data-stu-id="45b39-117">Kill process</span></span> <br/><span data-ttu-id="45b39-118">Dienst beenden</span><span class="sxs-lookup"><span data-stu-id="45b39-118">Stop service</span></span> <br/><span data-ttu-id="45b39-119">Treiber deaktivieren</span><span class="sxs-lookup"><span data-stu-id="45b39-119">Disable driver</span></span> <br/><span data-ttu-id="45b39-120">Geplante Aufgabe entfernen</span><span class="sxs-lookup"><span data-stu-id="45b39-120">Remove scheduled task</span></span>      |<span data-ttu-id="45b39-121">E-Mail-Nachrichten oder Cluster vorläufig löschen</span><span class="sxs-lookup"><span data-stu-id="45b39-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="45b39-122">URL blockieren (Zeitpunkt des Klickens)</span><span class="sxs-lookup"><span data-stu-id="45b39-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="45b39-123">Externe E-Mail-Weiterleitung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="45b39-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="45b39-124">Behebungsaktionen können im [Wartungs Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)angezeigt werden, unabhängig davon, ob Sie genehmigt wurden oder bereits abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="45b39-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="45b39-125">Behebungsaktionen führen zu automatisierten Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="45b39-125">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="45b39-126">Wenn eine automatische Untersuchung abgeschlossen ist, wird für alle beteiligten Beweise eine Erkenntnis ermittelt, und es werden Korrekturaktionen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="45b39-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="45b39-127">In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="45b39-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="45b39-128">In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="45b39-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="45b39-129">Erkenntnis</span><span class="sxs-lookup"><span data-stu-id="45b39-129">Verdict</span></span>    |<span data-ttu-id="45b39-130">Bereich</span><span class="sxs-lookup"><span data-stu-id="45b39-130">Area</span></span>    |<span data-ttu-id="45b39-131">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="45b39-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="45b39-132">Bösartig</span><span class="sxs-lookup"><span data-stu-id="45b39-132">Malicious</span></span>    |<span data-ttu-id="45b39-133">Geräte (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="45b39-133">Devices (endpoints)</span></span>    |<span data-ttu-id="45b39-134">Korrekturaktionen werden automatisch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="45b39-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="45b39-135">Bösartig</span><span class="sxs-lookup"><span data-stu-id="45b39-135">Malicious</span></span>    |<span data-ttu-id="45b39-136">E-Mail-Inhalt (URLs oder Anlagen)</span><span class="sxs-lookup"><span data-stu-id="45b39-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="45b39-137">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="45b39-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="45b39-138">Verdächtig</span><span class="sxs-lookup"><span data-stu-id="45b39-138">Suspicious</span></span>    |<span data-ttu-id="45b39-139">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="45b39-139">Devices or email content</span></span> |<span data-ttu-id="45b39-140">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="45b39-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="45b39-141">Keine Bedrohungen gefunden</span><span class="sxs-lookup"><span data-stu-id="45b39-141">No threats found</span></span>    |<span data-ttu-id="45b39-142">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="45b39-142">Devices or email content</span></span>    |<span data-ttu-id="45b39-143">Es sind keine Korrekturaktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="45b39-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="45b39-144">Überprüfen einer ausstehenden Aktion im Info-Center</span><span class="sxs-lookup"><span data-stu-id="45b39-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="45b39-145">Wenn Sie glauben, dass durch automatisierte Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection etwas übersehen oder fälschlicherweise erkannt wurde, lassen Sie es uns wissen!</span><span class="sxs-lookup"><span data-stu-id="45b39-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="45b39-146">[Meldet falsch positive Ergebnisse/negative](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="45b39-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="45b39-147">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="45b39-147">Next steps</span></span>

- [<span data-ttu-id="45b39-148">Genehmigen oder ablehnen von Aktionen</span><span class="sxs-lookup"><span data-stu-id="45b39-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="45b39-149">Erfahren Sie mehr über das Info-Center</span><span class="sxs-lookup"><span data-stu-id="45b39-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
