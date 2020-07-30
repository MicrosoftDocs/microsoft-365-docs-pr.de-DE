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
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502937"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="ce206-104">Behebungsaktionen nach automatisierten Untersuchungen im Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ce206-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="ce206-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ce206-105">**Applies to:**</span></span>
- <span data-ttu-id="ce206-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ce206-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="ce206-107">Wartungsaktionen</span><span class="sxs-lookup"><span data-stu-id="ce206-107">Remediation actions</span></span>

<span data-ttu-id="ce206-108">Während und nach einer automatischen Untersuchung im Microsoft Threat Protection werden Korrekturaktionen für böswillige oder verdächtige Elemente identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ce206-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="ce206-109">Einige Arten von Korrekturaktionen werden auf Geräten durchgeführt, die auch als Endpunkte bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="ce206-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="ce206-110">Für e-Mail-Inhalte werden andere Korrekturaktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ce206-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="ce206-111">Automatische Untersuchungen werden abgeschlossen, nachdem Korrekturaktionen durchgeführt, genehmigt oder abgelehnt wurden.</span><span class="sxs-lookup"><span data-stu-id="ce206-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="ce206-112">In der folgenden Tabelle werden Korrekturaktionen zusammengefasst, die derzeit in Microsoft Threat Protection unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="ce206-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="ce206-113">Geräte (Endpunkt)-Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="ce206-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="ce206-114">Wartungsaktionen für E-Mails</span><span class="sxs-lookup"><span data-stu-id="ce206-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="ce206-115">-Ermittlungs Paket sammeln</span><span class="sxs-lookup"><span data-stu-id="ce206-115">- Collect investigation package</span></span> <br/><span data-ttu-id="ce206-116">-Gerät isolieren (diese Aktion kann rückgängig gemacht werden)</span><span class="sxs-lookup"><span data-stu-id="ce206-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="ce206-117">-Extern Machine</span><span class="sxs-lookup"><span data-stu-id="ce206-117">- Offboard machine</span></span> <br/><span data-ttu-id="ce206-118">-Release Codeausführung</span><span class="sxs-lookup"><span data-stu-id="ce206-118">- Release code execution</span></span> <br/><span data-ttu-id="ce206-119">-Freigabe aus der Quarantäne</span><span class="sxs-lookup"><span data-stu-id="ce206-119">- Release from quarantine</span></span> <br/><span data-ttu-id="ce206-120">-Anforderungs Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce206-120">- Request sample</span></span> <br/><span data-ttu-id="ce206-121">-Einschränken der Codeausführung (diese Aktion kann rückgängig gemacht werden)</span><span class="sxs-lookup"><span data-stu-id="ce206-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="ce206-122">-Antivirus-Scan ausführen</span><span class="sxs-lookup"><span data-stu-id="ce206-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="ce206-123">-Stop und Quarantäne</span><span class="sxs-lookup"><span data-stu-id="ce206-123">- Stop and quarantine</span></span>      |<span data-ttu-id="ce206-124">-Block-URL (Zeit-zu-Klick)</span><span class="sxs-lookup"><span data-stu-id="ce206-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="ce206-125">-Soft Delete-e-Mail-Nachrichten oder-Cluster</span><span class="sxs-lookup"><span data-stu-id="ce206-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="ce206-126">-Quarantäne-e-Mail</span><span class="sxs-lookup"><span data-stu-id="ce206-126">- Quarantine email</span></span><br/><span data-ttu-id="ce206-127">-Isolieren einer e-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="ce206-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="ce206-128">-Externe e-Mail-Weiterleitung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="ce206-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="ce206-129">Behebungsaktionen können im [Wartungs Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)angezeigt werden, unabhängig davon, ob Sie genehmigt wurden oder bereits abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="ce206-129">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="ce206-130">Behebungsaktionen führen zu automatisierten Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="ce206-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="ce206-131">Wenn eine automatische Untersuchung abgeschlossen ist, wird für alle beteiligten Beweise eine Erkenntnis ermittelt, und es werden Korrekturaktionen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ce206-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="ce206-132">In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="ce206-132">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="ce206-133">In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="ce206-133">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="ce206-134">Erkenntnis</span><span class="sxs-lookup"><span data-stu-id="ce206-134">Verdict</span></span>    |<span data-ttu-id="ce206-135">Bereich</span><span class="sxs-lookup"><span data-stu-id="ce206-135">Area</span></span>    |<span data-ttu-id="ce206-136">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="ce206-136">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="ce206-137">Bösartig</span><span class="sxs-lookup"><span data-stu-id="ce206-137">Malicious</span></span>    |<span data-ttu-id="ce206-138">Geräte (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="ce206-138">Devices (endpoints)</span></span>    |<span data-ttu-id="ce206-139">Korrekturaktionen werden automatisch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ce206-139">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="ce206-140">Bösartig</span><span class="sxs-lookup"><span data-stu-id="ce206-140">Malicious</span></span>    |<span data-ttu-id="ce206-141">E-Mail-Inhalt (URLs oder Anlagen)</span><span class="sxs-lookup"><span data-stu-id="ce206-141">Email content (URLs or attachments)</span></span> | <span data-ttu-id="ce206-142">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="ce206-142">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="ce206-143">Verdächtig</span><span class="sxs-lookup"><span data-stu-id="ce206-143">Suspicious</span></span>    |<span data-ttu-id="ce206-144">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="ce206-144">Devices or email content</span></span> |<span data-ttu-id="ce206-145">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="ce206-145">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="ce206-146">Keine Bedrohungen gefunden</span><span class="sxs-lookup"><span data-stu-id="ce206-146">No threats found</span></span>    |<span data-ttu-id="ce206-147">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="ce206-147">Devices or email content</span></span>    |<span data-ttu-id="ce206-148">Es sind keine Korrekturaktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce206-148">No remediation actions are needed</span></span>|

[<span data-ttu-id="ce206-149">Überprüfen einer ausstehenden Aktion im Info-Center</span><span class="sxs-lookup"><span data-stu-id="ce206-149">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="ce206-150">Wenn Sie glauben, dass durch automatisierte Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection etwas übersehen oder fälschlicherweise erkannt wurde, lassen Sie es uns wissen!</span><span class="sxs-lookup"><span data-stu-id="ce206-150">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="ce206-151">[Meldet falsch positive Ergebnisse/negative](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="ce206-151">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ce206-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ce206-152">Next steps</span></span>

- [<span data-ttu-id="ce206-153">Genehmigen oder ablehnen von Aktionen</span><span class="sxs-lookup"><span data-stu-id="ce206-153">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="ce206-154">Erfahren Sie mehr über das Info-Center</span><span class="sxs-lookup"><span data-stu-id="ce206-154">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
