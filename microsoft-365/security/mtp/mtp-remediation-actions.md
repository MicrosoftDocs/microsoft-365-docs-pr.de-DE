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
ms.localizationpriority: medium
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
ms.openlocfilehash: 7dd95e8d7fe6424e294fbc9500fb908819463678
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928628"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="c0d51-104">Korrekturaktionen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0d51-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c0d51-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c0d51-105">**Applies to:**</span></span>
- <span data-ttu-id="c0d51-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0d51-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="c0d51-107">Wartungsaktionen</span><span class="sxs-lookup"><span data-stu-id="c0d51-107">Remediation actions</span></span>

<span data-ttu-id="c0d51-108">Während und nach einer automatisierten Untersuchung in Microsoft 365 Defender werden Korrekturaktionen für schädliche oder verdächtige Elemente identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c0d51-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="c0d51-109">Einige Arten von Korrekturaktionen werden auf Geräten, auch als Endpunkte bezeichnet, ergriffen.</span><span class="sxs-lookup"><span data-stu-id="c0d51-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="c0d51-110">Andere Korrekturaktionen werden für E-Mail-Inhalte ergriffen.</span><span class="sxs-lookup"><span data-stu-id="c0d51-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="c0d51-111">Automatisierte Untersuchungen werden abgeschlossen, nachdem Korrekturmaßnahmen ergriffen, genehmigt oder abgelehnt wurden.</span><span class="sxs-lookup"><span data-stu-id="c0d51-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0d51-112">Ob Korrekturaktionen automatisch oder nur nach Genehmigung ausgeführt werden, hängt von bestimmten Einstellungen ab, z. B. von automatisierungsstufen.</span><span class="sxs-lookup"><span data-stu-id="c0d51-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="c0d51-113">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="c0d51-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="c0d51-114">Konfigurieren Der automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0d51-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="c0d51-115">Wie Bedrohungen auf Geräten behoben werden</span><span class="sxs-lookup"><span data-stu-id="c0d51-115">How threats are remediated on devices</span></span>](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [<span data-ttu-id="c0d51-116">Bedrohungen und Abhilfemaßnahmen für E-Mail-& Inhalte der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="c0d51-116">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="c0d51-117">In der folgenden Tabelle sind Korrekturaktionen zusammengefasst, die derzeit in Microsoft 365 Defender unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="c0d51-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="c0d51-118">Korrekturaktionen für Geräte (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="c0d51-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="c0d51-119">Wartungsaktionen für E-Mails</span><span class="sxs-lookup"><span data-stu-id="c0d51-119">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="c0d51-120">– Untersuchungspaket sammeln</span><span class="sxs-lookup"><span data-stu-id="c0d51-120">- Collect investigation package</span></span> <br/><span data-ttu-id="c0d51-121">- Gerät isolieren (diese Aktion kann rückgängig gemacht werden)</span><span class="sxs-lookup"><span data-stu-id="c0d51-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="c0d51-122">- Offboardcomputer</span><span class="sxs-lookup"><span data-stu-id="c0d51-122">- Offboard machine</span></span> <br/><span data-ttu-id="c0d51-123">- Ausführung von Releasecode</span><span class="sxs-lookup"><span data-stu-id="c0d51-123">- Release code execution</span></span> <br/><span data-ttu-id="c0d51-124">– Isolieren aus Quarantäne</span><span class="sxs-lookup"><span data-stu-id="c0d51-124">- Release from quarantine</span></span> <br/><span data-ttu-id="c0d51-125">- Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="c0d51-125">- Request sample</span></span> <br/><span data-ttu-id="c0d51-126">- Codeausführung einschränken (diese Aktion kann rückgängig gemacht werden)</span><span class="sxs-lookup"><span data-stu-id="c0d51-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="c0d51-127">– Ausführen der Antivirenscans</span><span class="sxs-lookup"><span data-stu-id="c0d51-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="c0d51-128">- Beenden und Isolieren</span><span class="sxs-lookup"><span data-stu-id="c0d51-128">- Stop and quarantine</span></span>      |<span data-ttu-id="c0d51-129">- Blockieren der URL (Zeitpunkt des Klicks)</span><span class="sxs-lookup"><span data-stu-id="c0d51-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="c0d51-130">– Soft delete email messages or clusters</span><span class="sxs-lookup"><span data-stu-id="c0d51-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="c0d51-131">- Quarantäne-E-Mail</span><span class="sxs-lookup"><span data-stu-id="c0d51-131">- Quarantine email</span></span><br/><span data-ttu-id="c0d51-132">- Isolieren einer E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="c0d51-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="c0d51-133">- Deaktivieren der externen E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="c0d51-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="c0d51-134">Korrekturaktionen, unabhängig davon, ob die Genehmigung aussteht oder bereits abgeschlossen ist, können im [Action Center angezeigt werden.](./mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="c0d51-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](./mtp-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="c0d51-135">Abhilfemaßnahmen, die automatisierten Untersuchungen folgen</span><span class="sxs-lookup"><span data-stu-id="c0d51-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="c0d51-136">Wenn eine automatisierte Untersuchung abgeschlossen ist, wird für jeden beteiligten Nachweis ein Urteil erzielt.</span><span class="sxs-lookup"><span data-stu-id="c0d51-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="c0d51-137">Je nach Urteil werden Korrekturaktionen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c0d51-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="c0d51-138">In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="c0d51-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="c0d51-139">Alles hängt davon ab, [wie die automatisierte Untersuchung und Reaktion konfiguriert ist.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="c0d51-139">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="c0d51-140">In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="c0d51-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="c0d51-141">Erkenntnis</span><span class="sxs-lookup"><span data-stu-id="c0d51-141">Verdict</span></span>    | <span data-ttu-id="c0d51-142">Bereich</span><span class="sxs-lookup"><span data-stu-id="c0d51-142">Area</span></span>    | <span data-ttu-id="c0d51-143">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="c0d51-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="c0d51-144">Bösartig</span><span class="sxs-lookup"><span data-stu-id="c0d51-144">Malicious</span></span>    | <span data-ttu-id="c0d51-145">Geräte (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="c0d51-145">Devices (endpoints)</span></span>    | <span data-ttu-id="c0d51-146">Behebungsaktionen werden automatisch ausgeführt (vorausgesetzt, [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) die Gerätegruppen Ihrer Organisation sind auf Vollständig festgelegt – Bedrohungen werden automatisch **behoben)**</span><span class="sxs-lookup"><span data-stu-id="c0d51-146">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="c0d51-147">Bösartig</span><span class="sxs-lookup"><span data-stu-id="c0d51-147">Malicious</span></span>    | <span data-ttu-id="c0d51-148">E-Mail-Inhalt (URLs oder Anlagen)</span><span class="sxs-lookup"><span data-stu-id="c0d51-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="c0d51-149">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="c0d51-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="c0d51-150">Verdächtig</span><span class="sxs-lookup"><span data-stu-id="c0d51-150">Suspicious</span></span>    | <span data-ttu-id="c0d51-151">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="c0d51-151">Devices or email content</span></span> | <span data-ttu-id="c0d51-152">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="c0d51-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="c0d51-153">Keine Bedrohungen gefunden</span><span class="sxs-lookup"><span data-stu-id="c0d51-153">No threats found</span></span>    | <span data-ttu-id="c0d51-154">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="c0d51-154">Devices or email content</span></span>    | <span data-ttu-id="c0d51-155">Es sind keine Korrekturaktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c0d51-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="c0d51-156">Manuelle Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="c0d51-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="c0d51-157">Zusätzlich zu Abhilfemaßnahmen, die automatisierten Untersuchungen folgen, kann Ihr Sicherheitsbetriebsteam bestimmte Korrekturaktionen manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="c0d51-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="c0d51-158">Dazu gehören die folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="c0d51-158">These include the following actions:</span></span>

- <span data-ttu-id="c0d51-159">Manuelle Geräteaktion, z. B. Geräteisolation oder Dateiquarantäne.</span><span class="sxs-lookup"><span data-stu-id="c0d51-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="c0d51-160">Manuelle E-Mail-Aktion, z. B. das soft-deleting von E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="c0d51-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="c0d51-161">[Erweiterte Suche auf](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) Geräten oder E-Mails.</span><span class="sxs-lookup"><span data-stu-id="c0d51-161">[Advanced hunting](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) action on devices or email.</span></span>
- <span data-ttu-id="c0d51-162">[Explorer-Aktion](../office-365-security/threat-explorer.md) für E-Mail-Inhalte, z. B. das Verschieben von E-Mails in Junk- oder Soft-Deleting-E-Mails oder das Löschen von E-Mails.</span><span class="sxs-lookup"><span data-stu-id="c0d51-162">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="c0d51-163">Manuelle [Liveantwortaktion,](/windows/security/threat-protection/microsoft-defender-atp/live-response) z. B. Löschen einer Datei, Beenden eines Prozesses und Entfernen einer geplanten Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="c0d51-163">Manual [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="c0d51-164">Liveantwortaktion mit [Microsoft Defender for Endpoint-APIs,](/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)z. B. Isolieren eines Geräts, Ausführen einer Antivirenscans und Abrufen von Informationen zu einer Datei.</span><span class="sxs-lookup"><span data-stu-id="c0d51-164">Live response action with [Microsoft Defender for Endpoint APIs](/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="c0d51-165">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c0d51-165">Next steps</span></span>

- [<span data-ttu-id="c0d51-166">Aufrufen des Aktionszentrums</span><span class="sxs-lookup"><span data-stu-id="c0d51-166">Visit the Action center</span></span>](./mtp-action-center.md)
- [<span data-ttu-id="c0d51-167">Anzeigen und Verwalten von Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="c0d51-167">View and manage remediation actions</span></span>](./mtp-autoir-actions.md)
- [<span data-ttu-id="c0d51-168">Behandeln falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="c0d51-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)