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
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 232d19cb0bcb6a2f91c1bdad15d842ec7396499c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201051"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="1883f-104">Behebungsaktionen nach automatisierten Untersuchungen im Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1883f-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1883f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1883f-105">**Applies to:**</span></span>
- <span data-ttu-id="1883f-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1883f-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="1883f-107">Wartungsaktionen</span><span class="sxs-lookup"><span data-stu-id="1883f-107">Remediation actions</span></span>

<span data-ttu-id="1883f-108">Während und nach einer automatischen Untersuchung im Microsoft Threat Protection werden Korrekturaktionen für böswillige oder verdächtige Elemente identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1883f-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="1883f-109">Einige Arten von Korrekturaktionen werden auf Geräten durchgeführt, die auch als Endpunkte bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="1883f-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="1883f-110">Für e-Mail-Inhalte werden andere Korrekturaktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1883f-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="1883f-111">Automatische Untersuchungen werden abgeschlossen, nachdem Korrekturaktionen durchgeführt, genehmigt oder abgelehnt wurden.</span><span class="sxs-lookup"><span data-stu-id="1883f-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="1883f-112">In der folgenden Tabelle werden Korrekturaktionen zusammengefasst, die derzeit in Microsoft Threat Protection unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="1883f-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="1883f-113">Geräte (Endpunkt)-Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="1883f-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="1883f-114">Wartungsaktionen für E-Mails</span><span class="sxs-lookup"><span data-stu-id="1883f-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="1883f-115">-Ermittlungs Paket sammeln</span><span class="sxs-lookup"><span data-stu-id="1883f-115">- Collect investigation package</span></span> <br/><span data-ttu-id="1883f-116">-Gerät isolieren (diese Aktion kann rückgängig gemacht werden)</span><span class="sxs-lookup"><span data-stu-id="1883f-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="1883f-117">-Extern Machine</span><span class="sxs-lookup"><span data-stu-id="1883f-117">- Offboard machine</span></span> <br/><span data-ttu-id="1883f-118">-Release Codeausführung</span><span class="sxs-lookup"><span data-stu-id="1883f-118">- Release code execution</span></span> <br/><span data-ttu-id="1883f-119">-Freigabe aus der Quarantäne</span><span class="sxs-lookup"><span data-stu-id="1883f-119">- Release from quarantine</span></span> <br/><span data-ttu-id="1883f-120">-Anforderungs Beispiel</span><span class="sxs-lookup"><span data-stu-id="1883f-120">- Request sample</span></span> <br/><span data-ttu-id="1883f-121">-Einschränken der Codeausführung (diese Aktion kann rückgängig gemacht werden)</span><span class="sxs-lookup"><span data-stu-id="1883f-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="1883f-122">-Antivirus-Scan ausführen</span><span class="sxs-lookup"><span data-stu-id="1883f-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="1883f-123">-Stop und Quarantäne</span><span class="sxs-lookup"><span data-stu-id="1883f-123">- Stop and quarantine</span></span>      |<span data-ttu-id="1883f-124">-Block-URL (Zeit-zu-Klick)</span><span class="sxs-lookup"><span data-stu-id="1883f-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="1883f-125">-Soft Delete-e-Mail-Nachrichten oder-Cluster</span><span class="sxs-lookup"><span data-stu-id="1883f-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="1883f-126">-Quarantäne-e-Mail</span><span class="sxs-lookup"><span data-stu-id="1883f-126">- Quarantine email</span></span><br/><span data-ttu-id="1883f-127">-Isolieren einer e-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="1883f-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="1883f-128">-Externe e-Mail-Weiterleitung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="1883f-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="1883f-129">Korrekturaktionen, die ausstehende Genehmigung oder bereits abgeschlossen sind, können im [Wartungs Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1883f-129">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="1883f-130">Behebungsaktionen führen zu automatisierten Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="1883f-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="1883f-131">Wenn eine automatisierte Untersuchung abgeschlossen ist, wird ein Urteil für alle Beteiligten Belege getroffen.</span><span class="sxs-lookup"><span data-stu-id="1883f-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="1883f-132">Je nach dem Urteil werden Korrekturaktionen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1883f-132">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="1883f-133">In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="1883f-133">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="1883f-134">Alles hängt davon ab [, wie die automatische Untersuchung und Antwort konfiguriert ist](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="1883f-134">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="1883f-135">In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="1883f-135">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="1883f-136">Erkenntnis</span><span class="sxs-lookup"><span data-stu-id="1883f-136">Verdict</span></span>    |<span data-ttu-id="1883f-137">Bereich</span><span class="sxs-lookup"><span data-stu-id="1883f-137">Area</span></span>    |<span data-ttu-id="1883f-138">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="1883f-138">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="1883f-139">Bösartig</span><span class="sxs-lookup"><span data-stu-id="1883f-139">Malicious</span></span>    |<span data-ttu-id="1883f-140">Geräte (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="1883f-140">Devices (endpoints)</span></span>    |<span data-ttu-id="1883f-141">Korrekturaktionen werden automatisch durchgeführt (vorausgesetzt, die [Gerätegruppen](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) Ihrer Organisation werden **automatisch vollständig behobene Bedrohungen**).</span><span class="sxs-lookup"><span data-stu-id="1883f-141">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
|<span data-ttu-id="1883f-142">Bösartig</span><span class="sxs-lookup"><span data-stu-id="1883f-142">Malicious</span></span>    |<span data-ttu-id="1883f-143">E-Mail-Inhalt (URLs oder Anlagen)</span><span class="sxs-lookup"><span data-stu-id="1883f-143">Email content (URLs or attachments)</span></span> | <span data-ttu-id="1883f-144">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="1883f-144">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="1883f-145">Verdächtig</span><span class="sxs-lookup"><span data-stu-id="1883f-145">Suspicious</span></span>    |<span data-ttu-id="1883f-146">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="1883f-146">Devices or email content</span></span> |<span data-ttu-id="1883f-147">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="1883f-147">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="1883f-148">Keine Bedrohungen gefunden</span><span class="sxs-lookup"><span data-stu-id="1883f-148">No threats found</span></span>    |<span data-ttu-id="1883f-149">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="1883f-149">Devices or email content</span></span>    |<span data-ttu-id="1883f-150">Es sind keine Korrekturaktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1883f-150">No remediation actions are needed</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="1883f-151">Ob Korrekturaktionen automatisch oder nur bei Genehmigung vorgenommen werden, hängt von bestimmten Einstellungen ab, beispielsweise von den Gerätegruppen Richtlinien Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="1883f-151">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as your organization's device group policies.</span></span> <span data-ttu-id="1883f-152">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="1883f-152">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="1883f-153">Konfigurieren von automatisierten Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1883f-153">Configure automated investigation and response capabilities in Microsoft Threat Protection</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="1883f-154">So beheben Sie Bedrohungen auf Geräten</span><span class="sxs-lookup"><span data-stu-id="1883f-154">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a><span data-ttu-id="1883f-155">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1883f-155">Next steps</span></span>

- [<span data-ttu-id="1883f-156">Aufrufen des Aktionszentrums</span><span class="sxs-lookup"><span data-stu-id="1883f-156">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="1883f-157">Genehmigen oder Ablehnen ausstehender Aktionen</span><span class="sxs-lookup"><span data-stu-id="1883f-157">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="1883f-158">Behandeln von falsch positiven/negativen Ergebnissen in automatisierten Ermittlungs-und Antwortfunktionen</span><span class="sxs-lookup"><span data-stu-id="1883f-158">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
