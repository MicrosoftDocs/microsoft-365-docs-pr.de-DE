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
ms.openlocfilehash: 76a4fe678ce0106c7345dd3bdf504673733b63b6
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266051"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="7f6f8-104">Behebungsaktionen nach automatisierten Untersuchungen im Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7f6f8-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="7f6f8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7f6f8-105">**Applies to:**</span></span>
- <span data-ttu-id="7f6f8-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7f6f8-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="7f6f8-107">Wartungsaktionen</span><span class="sxs-lookup"><span data-stu-id="7f6f8-107">Remediation actions</span></span>

<span data-ttu-id="7f6f8-108">Während und nach einer automatischen Untersuchung im Microsoft Threat Protection werden Korrekturaktionen für böswillige oder verdächtige Elemente identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7f6f8-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="7f6f8-109">Einige Arten von Korrekturaktionen werden auf Geräten durchgeführt, die auch als Endpunkte bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="7f6f8-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="7f6f8-110">Für e-Mail-Inhalte werden andere Korrekturaktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f6f8-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="7f6f8-111">Automatische Untersuchungen werden abgeschlossen, nachdem Korrekturaktionen durchgeführt, genehmigt oder abgelehnt wurden.</span><span class="sxs-lookup"><span data-stu-id="7f6f8-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="7f6f8-112">In der folgenden Tabelle werden Korrekturaktionen zusammengefasst, die derzeit in Microsoft Threat Protection unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="7f6f8-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="7f6f8-113">Geräte (Endpunkt)-Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="7f6f8-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="7f6f8-114">Wartungsaktionen für E-Mails</span><span class="sxs-lookup"><span data-stu-id="7f6f8-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="7f6f8-115">Quarantänedatei</span><span class="sxs-lookup"><span data-stu-id="7f6f8-115">Quarantine file</span></span><br/><span data-ttu-id="7f6f8-116">Registrierungsschlüssel entfernen</span><span class="sxs-lookup"><span data-stu-id="7f6f8-116">Remove registry key</span></span><br/><span data-ttu-id="7f6f8-117">Prozess abbrechen</span><span class="sxs-lookup"><span data-stu-id="7f6f8-117">Kill process</span></span> <br/><span data-ttu-id="7f6f8-118">Dienst beenden</span><span class="sxs-lookup"><span data-stu-id="7f6f8-118">Stop service</span></span> <br/><span data-ttu-id="7f6f8-119">Treiber deaktivieren</span><span class="sxs-lookup"><span data-stu-id="7f6f8-119">Disable driver</span></span> <br/><span data-ttu-id="7f6f8-120">Geplante Aufgabe entfernen</span><span class="sxs-lookup"><span data-stu-id="7f6f8-120">Remove scheduled task</span></span>      |<span data-ttu-id="7f6f8-121">E-Mail-Nachrichten oder Cluster vorläufig löschen</span><span class="sxs-lookup"><span data-stu-id="7f6f8-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="7f6f8-122">URL blockieren (Zeitpunkt des Klickens)</span><span class="sxs-lookup"><span data-stu-id="7f6f8-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="7f6f8-123">Externe E-Mail-Weiterleitung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="7f6f8-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="7f6f8-124">Behebungsaktionen können im [Wartungs Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)angezeigt werden, unabhängig davon, ob Sie genehmigt wurden oder bereits abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="7f6f8-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="verdicts-and-outcomes-following-automated-investigations"></a><span data-ttu-id="7f6f8-125">Urteile und Ergebnisse nach automatisierten Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="7f6f8-125">Verdicts and outcomes following automated investigations</span></span>

<span data-ttu-id="7f6f8-126">Wenn eine automatische Untersuchung abgeschlossen ist, wird für alle beteiligten Beweise eine Erkenntnis ermittelt, und es werden Korrekturaktionen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7f6f8-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="7f6f8-127">In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="7f6f8-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="7f6f8-128">In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="7f6f8-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="7f6f8-129">Erkenntnis</span><span class="sxs-lookup"><span data-stu-id="7f6f8-129">Verdict</span></span>    |<span data-ttu-id="7f6f8-130">Bereich</span><span class="sxs-lookup"><span data-stu-id="7f6f8-130">Area</span></span>   |<span data-ttu-id="7f6f8-131">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="7f6f8-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="7f6f8-132">Bösartig</span><span class="sxs-lookup"><span data-stu-id="7f6f8-132">Malicious</span></span>  |<span data-ttu-id="7f6f8-133">Geräte (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="7f6f8-133">Devices (endpoints)</span></span>    |<span data-ttu-id="7f6f8-134">Korrekturaktionen werden automatisch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f6f8-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="7f6f8-135">Bösartig</span><span class="sxs-lookup"><span data-stu-id="7f6f8-135">Malicious</span></span>  |<span data-ttu-id="7f6f8-136">E-Mail-Inhalt (URLs oder Anlagen)</span><span class="sxs-lookup"><span data-stu-id="7f6f8-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="7f6f8-137">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="7f6f8-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="7f6f8-138">Verdächtig</span><span class="sxs-lookup"><span data-stu-id="7f6f8-138">Suspicious</span></span> |<span data-ttu-id="7f6f8-139">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="7f6f8-139">Devices or email content</span></span> |<span data-ttu-id="7f6f8-140">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="7f6f8-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="7f6f8-141">Bereinigen</span><span class="sxs-lookup"><span data-stu-id="7f6f8-141">Clean</span></span>  |<span data-ttu-id="7f6f8-142">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="7f6f8-142">Devices or email content</span></span>   |<span data-ttu-id="7f6f8-143">Es sind keine Korrekturaktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7f6f8-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="7f6f8-144">Überprüfen einer ausstehenden Aktion im Info-Center</span><span class="sxs-lookup"><span data-stu-id="7f6f8-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="7f6f8-145">Wenn Sie glauben, dass durch automatisierte Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection etwas übersehen oder fälschlicherweise erkannt wurde, lassen Sie es uns wissen!</span><span class="sxs-lookup"><span data-stu-id="7f6f8-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="7f6f8-146">[Meldet falsch positive Ergebnisse/negative](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="7f6f8-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7f6f8-147">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7f6f8-147">Next steps</span></span>

- [<span data-ttu-id="7f6f8-148">Genehmigen oder ablehnen von Aktionen</span><span class="sxs-lookup"><span data-stu-id="7f6f8-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="7f6f8-149">Erfahren Sie mehr über das Info-Center</span><span class="sxs-lookup"><span data-stu-id="7f6f8-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
