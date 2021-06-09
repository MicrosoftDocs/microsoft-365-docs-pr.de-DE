---
title: Korrekturaktionen in Microsoft 365 Defender
description: Erhalten Sie einen Überblick über Korrekturaktionen, die automatisierten Untersuchungen in Microsoft 365 Defender folgen
keywords: automatisch, Untersuchung, Warnung, Trigger, Aktion, Wartung
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c8d3838194c25ba49b2611dc355b21e228291b01
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842528"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="b5f3e-104">Korrekturaktionen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5f3e-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b5f3e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b5f3e-105">**Applies to:**</span></span>
- <span data-ttu-id="b5f3e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5f3e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b5f3e-107">Während und nach einer automatisierten Untersuchung in Microsoft 365 Defender werden Abhilfemaßnahmen für böswillige oder verdächtige Elemente identifiziert.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-107">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="b5f3e-108">Einige Arten von Korrekturmaßnahmen werden auf Geräten ausgeführt, die auch als Endpunkte bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="b5f3e-109">Andere Korrekturmaßnahmen werden für E-Mail-Inhalte ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-109">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="b5f3e-110">Automatisierte Untersuchungen werden abgeschlossen, nachdem Korrekturmaßnahmen ergriffen, genehmigt oder abgelehnt wurden.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-110">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5f3e-111">Ob Korrekturmaßnahmen automatisch oder nur nach Genehmigung durchgeführt werden, hängt von bestimmten Einstellungen ab, z. B. von den Automatisierungsstufen.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-111">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="b5f3e-112">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="b5f3e-112">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="b5f3e-113">Konfigurieren Der Funktionen für automatische Untersuchung und Reaktion in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5f3e-113">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="b5f3e-114">Wie Bedrohungen auf Geräten behoben werden</span><span class="sxs-lookup"><span data-stu-id="b5f3e-114">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="b5f3e-115">Bedrohungen und Abhilfemaßnahmen für E-Mail-& Inhalte für die Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="b5f3e-115">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="b5f3e-116">In der folgenden Tabelle sind Korrekturaktionen zusammengefasst, die derzeit in Microsoft 365 Defender unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-116">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender.</span></span> 

|<span data-ttu-id="b5f3e-117">Abhilfemaßnahmen für Geräte (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="b5f3e-117">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="b5f3e-118">Wartungsaktionen für E-Mails</span><span class="sxs-lookup"><span data-stu-id="b5f3e-118">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="b5f3e-119">- Erfassen des Untersuchungspakets</span><span class="sxs-lookup"><span data-stu-id="b5f3e-119">- Collect investigation package</span></span> <br/><span data-ttu-id="b5f3e-120">- Gerät isolieren (diese Aktion kann rückgängig machen)</span><span class="sxs-lookup"><span data-stu-id="b5f3e-120">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="b5f3e-121">– Offboard-Computer</span><span class="sxs-lookup"><span data-stu-id="b5f3e-121">- Offboard machine</span></span> <br/><span data-ttu-id="b5f3e-122">– Freigeben der Codeausführung</span><span class="sxs-lookup"><span data-stu-id="b5f3e-122">- Release code execution</span></span> <br/><span data-ttu-id="b5f3e-123">– Aus Quarantäne freigeben</span><span class="sxs-lookup"><span data-stu-id="b5f3e-123">- Release from quarantine</span></span> <br/><span data-ttu-id="b5f3e-124">– Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="b5f3e-124">- Request sample</span></span> <br/><span data-ttu-id="b5f3e-125">- Einschränken der Codeausführung (diese Aktion kann rückgängig machen)</span><span class="sxs-lookup"><span data-stu-id="b5f3e-125">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="b5f3e-126">– Ausführen eines Antivirusscans</span><span class="sxs-lookup"><span data-stu-id="b5f3e-126">- Run antivirus scan</span></span> <br/><span data-ttu-id="b5f3e-127">– Beenden und Isolieren</span><span class="sxs-lookup"><span data-stu-id="b5f3e-127">- Stop and quarantine</span></span>      |<span data-ttu-id="b5f3e-128">- Block-URL (Uhrzeit des Klickens)</span><span class="sxs-lookup"><span data-stu-id="b5f3e-128">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="b5f3e-129">– Vorläufiges Löschen von E-Mail-Nachrichten oder Clustern</span><span class="sxs-lookup"><span data-stu-id="b5f3e-129">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="b5f3e-130">– E-Mails unter Quarantäne stellen</span><span class="sxs-lookup"><span data-stu-id="b5f3e-130">- Quarantine email</span></span><br/><span data-ttu-id="b5f3e-131">– Isolieren einer E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="b5f3e-131">- Quarantine an email attachment</span></span><br/><span data-ttu-id="b5f3e-132">– Deaktivieren der externen E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="b5f3e-132">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="b5f3e-133">Korrekturaktionen, unabhängig davon, ob die Genehmigung aussteht oder bereits abgeschlossen ist, können im [Info-Center](m365d-action-center.md)angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-133">Remediation actions, whether pending approval or already complete, can be viewed in the [Action center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="b5f3e-134">Korrekturaktionen, die auf automatisierte Untersuchungen folgen</span><span class="sxs-lookup"><span data-stu-id="b5f3e-134">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="b5f3e-135">Nach Abschluss einer automatisierten Untersuchung wird für jeden beteiligten Nachweis eine Bewertung getroffen.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-135">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="b5f3e-136">Je nach Bewertung werden Korrekturaktionen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-136">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="b5f3e-137">In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-137">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="b5f3e-138">Alles hängt davon ab, wie [die automatisierte Untersuchung und Reaktion konfiguriert ist.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="b5f3e-138">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="b5f3e-139">In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="b5f3e-139">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="b5f3e-140">Erkenntnis</span><span class="sxs-lookup"><span data-stu-id="b5f3e-140">Verdict</span></span>    | <span data-ttu-id="b5f3e-141">Betroffene Entitäten</span><span class="sxs-lookup"><span data-stu-id="b5f3e-141">Affected entities</span></span>    | <span data-ttu-id="b5f3e-142">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="b5f3e-142">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="b5f3e-143">Bösartig</span><span class="sxs-lookup"><span data-stu-id="b5f3e-143">Malicious</span></span>    | <span data-ttu-id="b5f3e-144">Geräte (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="b5f3e-144">Devices (endpoints)</span></span>    | <span data-ttu-id="b5f3e-145">Korrekturmaßnahmen werden automatisch durchgeführt (vorausgesetzt, die [Gerätegruppen](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) Ihrer Organisation sind auf **"Vollständig" festgelegt – Bedrohungen automatisch beheben)**</span><span class="sxs-lookup"><span data-stu-id="b5f3e-145">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="b5f3e-146">Bösartig</span><span class="sxs-lookup"><span data-stu-id="b5f3e-146">Malicious</span></span>    | <span data-ttu-id="b5f3e-147">E-Mail-Inhalt (URLs oder Anlagen)</span><span class="sxs-lookup"><span data-stu-id="b5f3e-147">Email content (URLs or attachments)</span></span> | <span data-ttu-id="b5f3e-148">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-148">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="b5f3e-149">Verdächtig</span><span class="sxs-lookup"><span data-stu-id="b5f3e-149">Suspicious</span></span>    | <span data-ttu-id="b5f3e-150">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="b5f3e-150">Devices or email content</span></span> | <span data-ttu-id="b5f3e-151">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-151">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="b5f3e-152">Keine Bedrohungen gefunden</span><span class="sxs-lookup"><span data-stu-id="b5f3e-152">No threats found</span></span>    | <span data-ttu-id="b5f3e-153">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="b5f3e-153">Devices or email content</span></span>    | <span data-ttu-id="b5f3e-154">Es sind keine Korrekturaktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-154">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="b5f3e-155">Manuell ausgeführte Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="b5f3e-155">Remediation actions that are taken manually</span></span>

<span data-ttu-id="b5f3e-156">Zusätzlich zu Korrekturmaßnahmen, die auf automatisierte Untersuchungen folgen, kann Ihr Sicherheitsteam bestimmte Korrekturmaßnahmen manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="b5f3e-156">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="b5f3e-157">Hierzu gehören:</span><span class="sxs-lookup"><span data-stu-id="b5f3e-157">These include the following:</span></span>

- <span data-ttu-id="b5f3e-158">Manuelle Geräteaktion, z. B. Geräteisolation oder Dateiquarantäne</span><span class="sxs-lookup"><span data-stu-id="b5f3e-158">Manual device action, such as device isolation or file quarantine</span></span>
- <span data-ttu-id="b5f3e-159">Manuelle E-Mail-Aktion, z. B. vorläufiges Löschen von E-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="b5f3e-159">Manual email action, such as soft-deleting email messages</span></span> 
- <span data-ttu-id="b5f3e-160">[Erweiterte Suchaktion](../defender-endpoint/advanced-hunting-overview.md) auf Geräten oder E-Mails</span><span class="sxs-lookup"><span data-stu-id="b5f3e-160">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email</span></span>
- <span data-ttu-id="b5f3e-161">[Explorer-Aktion](../office-365-security/threat-explorer.md) für E-Mail-Inhalte, z. B. Verschieben von E-Mails in Junk, vorläufiges Löschen von E-Mails oder endgültiges Löschen von E-Mails</span><span class="sxs-lookup"><span data-stu-id="b5f3e-161">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email</span></span>
- <span data-ttu-id="b5f3e-162">Manuelle [Liveantwortaktion,](/windows/security/threat-protection/microsoft-defender-atp/live-response) z. B. Löschen einer Datei, Beenden eines Prozesses und Entfernen einer geplanten Aufgabe</span><span class="sxs-lookup"><span data-stu-id="b5f3e-162">Manual [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task</span></span>
- <span data-ttu-id="b5f3e-163">Live-Antwortaktion mit [Microsoft Defender für Endpunkt-APIs,](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)z. B. Isolieren eines Geräts, Ausführen eines Antivirenscans und Abrufen von Informationen zu einer Datei</span><span class="sxs-lookup"><span data-stu-id="b5f3e-163">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file</span></span>

## <a name="next-steps"></a><span data-ttu-id="b5f3e-164">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b5f3e-164">Next steps</span></span>

- [<span data-ttu-id="b5f3e-165">Aufrufen des Aktionszentrums</span><span class="sxs-lookup"><span data-stu-id="b5f3e-165">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="b5f3e-166">Anzeigen und Verwalten von Wartungsaktionen</span><span class="sxs-lookup"><span data-stu-id="b5f3e-166">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="b5f3e-167">Adressen falsch positiver oder falsch negativer Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="b5f3e-167">Address false positives or false negatives</span></span>](m365d-autoir-report-false-positives-negatives.md)
