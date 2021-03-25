---
title: Korrekturaktionen in Microsoft 365 Defender
description: Erhalten Sie eine Übersicht über Abhilfemaßnahmen, die automatisierte Untersuchungen in Microsoft 365 Defender durchführen
keywords: automatisch, Untersuchung, Warnung, Trigger, Aktion, Wartung
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fa73756aa9f350793c00a7e4a960c215627b712f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064712"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="15b5a-104">Korrekturaktionen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15b5a-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="15b5a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="15b5a-105">**Applies to:**</span></span>
- <span data-ttu-id="15b5a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15b5a-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="15b5a-107">Wartungsaktionen</span><span class="sxs-lookup"><span data-stu-id="15b5a-107">Remediation actions</span></span>

<span data-ttu-id="15b5a-108">Während und nach einer automatisierten Untersuchung in Microsoft 365 Defender werden Korrekturaktionen für schädliche oder verdächtige Elemente identifiziert.</span><span class="sxs-lookup"><span data-stu-id="15b5a-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="15b5a-109">Einige Arten von Korrekturaktionen werden auf Geräten, auch als Endpunkte bezeichnet, ergriffen.</span><span class="sxs-lookup"><span data-stu-id="15b5a-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="15b5a-110">Andere Korrekturaktionen werden für E-Mail-Inhalte ergriffen.</span><span class="sxs-lookup"><span data-stu-id="15b5a-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="15b5a-111">Automatisierte Untersuchungen werden abgeschlossen, nachdem Korrekturmaßnahmen ergriffen, genehmigt oder abgelehnt wurden.</span><span class="sxs-lookup"><span data-stu-id="15b5a-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15b5a-112">Ob Korrekturaktionen automatisch oder nur nach Genehmigung ausgeführt werden, hängt von bestimmten Einstellungen ab, z. B. von automatisierungsstufen.</span><span class="sxs-lookup"><span data-stu-id="15b5a-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="15b5a-113">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="15b5a-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="15b5a-114">Konfigurieren Der automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15b5a-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="15b5a-115">Wie Bedrohungen auf Geräten behoben werden</span><span class="sxs-lookup"><span data-stu-id="15b5a-115">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="15b5a-116">Bedrohungen und Abhilfemaßnahmen für E-Mail-& Inhalte der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="15b5a-116">Threats and remediation actions on email & collaboration content</span></span>](../defender-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="15b5a-117">In der folgenden Tabelle sind Korrekturaktionen zusammengefasst, die derzeit in Microsoft 365 Defender unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="15b5a-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="15b5a-118">Korrekturaktionen für Geräte (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="15b5a-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="15b5a-119">Wartungsaktionen für E-Mails</span><span class="sxs-lookup"><span data-stu-id="15b5a-119">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="15b5a-120">– Untersuchungspaket sammeln</span><span class="sxs-lookup"><span data-stu-id="15b5a-120">- Collect investigation package</span></span> <br/><span data-ttu-id="15b5a-121">- Gerät isolieren (diese Aktion kann rückgängig gemacht werden)</span><span class="sxs-lookup"><span data-stu-id="15b5a-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="15b5a-122">- Offboardcomputer</span><span class="sxs-lookup"><span data-stu-id="15b5a-122">- Offboard machine</span></span> <br/><span data-ttu-id="15b5a-123">- Ausführung von Releasecode</span><span class="sxs-lookup"><span data-stu-id="15b5a-123">- Release code execution</span></span> <br/><span data-ttu-id="15b5a-124">– Isolieren aus Quarantäne</span><span class="sxs-lookup"><span data-stu-id="15b5a-124">- Release from quarantine</span></span> <br/><span data-ttu-id="15b5a-125">- Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="15b5a-125">- Request sample</span></span> <br/><span data-ttu-id="15b5a-126">- Codeausführung einschränken (diese Aktion kann rückgängig gemacht werden)</span><span class="sxs-lookup"><span data-stu-id="15b5a-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="15b5a-127">– Ausführen der Antivirenscans</span><span class="sxs-lookup"><span data-stu-id="15b5a-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="15b5a-128">- Beenden und Isolieren</span><span class="sxs-lookup"><span data-stu-id="15b5a-128">- Stop and quarantine</span></span>      |<span data-ttu-id="15b5a-129">- Blockieren der URL (Zeitpunkt des Klicks)</span><span class="sxs-lookup"><span data-stu-id="15b5a-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="15b5a-130">– Soft delete email messages or clusters</span><span class="sxs-lookup"><span data-stu-id="15b5a-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="15b5a-131">- Quarantäne-E-Mail</span><span class="sxs-lookup"><span data-stu-id="15b5a-131">- Quarantine email</span></span><br/><span data-ttu-id="15b5a-132">- Isolieren einer E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="15b5a-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="15b5a-133">- Deaktivieren der externen E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="15b5a-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="15b5a-134">Korrekturaktionen, unabhängig davon, ob die Genehmigung aussteht oder bereits abgeschlossen ist, können im [Action Center angezeigt werden.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="15b5a-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="15b5a-135">Abhilfemaßnahmen, die automatisierten Untersuchungen folgen</span><span class="sxs-lookup"><span data-stu-id="15b5a-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="15b5a-136">Wenn eine automatisierte Untersuchung abgeschlossen ist, wird für jeden beteiligten Nachweis ein Urteil erzielt.</span><span class="sxs-lookup"><span data-stu-id="15b5a-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="15b5a-137">Je nach Urteil werden Korrekturaktionen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="15b5a-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="15b5a-138">In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="15b5a-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="15b5a-139">Alles hängt davon ab, [wie die automatisierte Untersuchung und Reaktion konfiguriert ist.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="15b5a-139">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="15b5a-140">In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="15b5a-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="15b5a-141">Erkenntnis</span><span class="sxs-lookup"><span data-stu-id="15b5a-141">Verdict</span></span>    | <span data-ttu-id="15b5a-142">Bereich</span><span class="sxs-lookup"><span data-stu-id="15b5a-142">Area</span></span>    | <span data-ttu-id="15b5a-143">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="15b5a-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="15b5a-144">Bösartig</span><span class="sxs-lookup"><span data-stu-id="15b5a-144">Malicious</span></span>    | <span data-ttu-id="15b5a-145">Geräte (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="15b5a-145">Devices (endpoints)</span></span>    | <span data-ttu-id="15b5a-146">Behebungsaktionen werden automatisch ausgeführt (vorausgesetzt, [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) die Gerätegruppen Ihrer Organisation sind auf Vollständig festgelegt – Bedrohungen werden automatisch **behoben)**</span><span class="sxs-lookup"><span data-stu-id="15b5a-146">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="15b5a-147">Bösartig</span><span class="sxs-lookup"><span data-stu-id="15b5a-147">Malicious</span></span>    | <span data-ttu-id="15b5a-148">E-Mail-Inhalt (URLs oder Anlagen)</span><span class="sxs-lookup"><span data-stu-id="15b5a-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="15b5a-149">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="15b5a-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="15b5a-150">Verdächtig</span><span class="sxs-lookup"><span data-stu-id="15b5a-150">Suspicious</span></span>    | <span data-ttu-id="15b5a-151">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="15b5a-151">Devices or email content</span></span> | <span data-ttu-id="15b5a-152">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="15b5a-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="15b5a-153">Keine Bedrohungen gefunden</span><span class="sxs-lookup"><span data-stu-id="15b5a-153">No threats found</span></span>    | <span data-ttu-id="15b5a-154">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="15b5a-154">Devices or email content</span></span>    | <span data-ttu-id="15b5a-155">Es sind keine Korrekturaktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="15b5a-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="15b5a-156">Manuelle Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="15b5a-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="15b5a-157">Zusätzlich zu Abhilfemaßnahmen, die automatisierten Untersuchungen folgen, kann Ihr Sicherheitsbetriebsteam bestimmte Korrekturaktionen manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="15b5a-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="15b5a-158">Dazu gehören die folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="15b5a-158">These include the following actions:</span></span>

- <span data-ttu-id="15b5a-159">Manuelle Geräteaktion, z. B. Geräteisolation oder Dateiquarantäne.</span><span class="sxs-lookup"><span data-stu-id="15b5a-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="15b5a-160">Manuelle E-Mail-Aktion, z. B. das soft-deleting von E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="15b5a-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="15b5a-161">[Erweiterte Suche auf](../defender-endpoint/advanced-hunting-overview.md) Geräten oder E-Mails.</span><span class="sxs-lookup"><span data-stu-id="15b5a-161">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email.</span></span>
- <span data-ttu-id="15b5a-162">[Explorer-Aktion](../defender-365-security/threat-explorer.md) für E-Mail-Inhalte, z. B. das Verschieben von E-Mails in Junk- oder Soft-Deleting-E-Mails oder das Löschen von E-Mails.</span><span class="sxs-lookup"><span data-stu-id="15b5a-162">[Explorer](../defender-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="15b5a-163">Manuelle [Liveantwortaktion,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) z. B. Löschen einer Datei, Beenden eines Prozesses und Entfernen einer geplanten Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="15b5a-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="15b5a-164">Liveantwortaktion mit [Microsoft Defender for Endpoint-APIs,](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)z. B. Isolieren eines Geräts, Ausführen einer Antivirenscans und Abrufen von Informationen zu einer Datei.</span><span class="sxs-lookup"><span data-stu-id="15b5a-164">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="15b5a-165">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="15b5a-165">Next steps</span></span>

- [<span data-ttu-id="15b5a-166">Aufrufen des Aktionszentrums</span><span class="sxs-lookup"><span data-stu-id="15b5a-166">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="15b5a-167">Anzeigen und Verwalten von Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="15b5a-167">View and manage remediation actions</span></span>]( m365d-autoir-actions.md)
- [<span data-ttu-id="15b5a-168">Behandeln falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="15b5a-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](m365d-autoir-report-false-positives-negatives.md)
