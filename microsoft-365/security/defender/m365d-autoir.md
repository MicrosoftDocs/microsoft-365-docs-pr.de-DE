---
title: Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender
description: Verschaffen Sie sich in Microsoft 365 Defender einen Überblick über automatisierte Untersuchungs- und Reaktionsfunktionen, auch Selbstheilung genannt.
keywords: automatisiert, Untersuchung, Warnung, Trigger, Aktion, Korrektur, Selbstheilung
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
ms.openlocfilehash: 976a79be98efcbb5d7fd3749ddb0cdb282b1e3e3
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274568"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="767d3-104">Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="767d3-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="767d3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="767d3-105">**Applies to:**</span></span>
- <span data-ttu-id="767d3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="767d3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="767d3-107">Wenn Ihre Organisation [Microsoft 365 Defender](microsoft-365-defender.md)verwendet, empfängt Ihr Sicherheitsteam eine Warnung im Microsoft 365 Security Center, wenn eine bösartige oder verdächtige Aktivität oder ein Artefakt erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="767d3-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert within the Microsoft 365 security center whenever a malicious or suspicious activity or artifact is detected.</span></span> <span data-ttu-id="767d3-108">Angesichts des scheinbar nie endenden Bedrohungsflusses, der einfingen kann, stehen Sicherheitsteams häufig vor der Herausforderung, das hohe Benachrichtigungsvolumen zu bewältigen.</span><span class="sxs-lookup"><span data-stu-id="767d3-108">Given the seemingly never-ending flow of threats that can come in, security teams often face the challenge of addressing the high volume of alerts.</span></span> <span data-ttu-id="767d3-109">Glücklicherweise umfasst Microsoft 365 Defender funktionen für die automatisierte Untersuchung und Reaktion (AUTOMATED Investigation and Response, AIR), mit denen Ihr Sicherheitsbetriebsteam Bedrohungen effizienter und effektiver adressieren kann.</span><span class="sxs-lookup"><span data-stu-id="767d3-109">Fortunately, Microsoft 365 Defender includes automated investigation and response (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="767d3-110">Dieser Artikel bietet eine Übersicht über AIR und enthält Links zu den nächsten Schritten und zusätzlichen Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="767d3-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="767d3-111">Sie möchten Microsoft 365 Defender ausprobieren?</span><span class="sxs-lookup"><span data-stu-id="767d3-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="767d3-112">Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="767d3-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="767d3-113">Funktionsweise der automatisierten Untersuchung und Selbstheilung</span><span class="sxs-lookup"><span data-stu-id="767d3-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="767d3-114">Wenn Sicherheitswarnungen ausgelöst werden, ist es an Ihrem Sicherheitsbetriebsteam, diese Warnungen zu betrachten und Schritte zum Schutz Ihrer Organisation zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="767d3-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="767d3-115">Die Priorisierung und Untersuchung von Warnungen kann sehr zeitaufwändig sein, insbesondere dann, wenn ständig neue Benachrichtigungen während einer laufenden Untersuchung eingehen.</span><span class="sxs-lookup"><span data-stu-id="767d3-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="767d3-116">Sicherheitsteams können sich angesichts des enormen Volumens der Bedrohungen, die sie überwachen müssen, überfordert fühlen.</span><span class="sxs-lookup"><span data-stu-id="767d3-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="767d3-117">Automatisierte Untersuchungs- und Reaktionsfunktionen mit Selbstheilung in Microsoft 365 Defender können helfen.</span><span class="sxs-lookup"><span data-stu-id="767d3-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="767d3-118">Sehen Sie sich das folgende Video an, um zu sehen, wie die Selbstheilung funktioniert:</span><span class="sxs-lookup"><span data-stu-id="767d3-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="767d3-119">In Microsoft 365 Defender funktioniert die automatisierte Untersuchung und Reaktion mit Selbstheilungsfunktionen auf Allen Geräten, E-Mail-& und Identitäten.</span><span class="sxs-lookup"><span data-stu-id="767d3-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="767d3-120">In diesem Artikel wird beschrieben, wie automatisierte Untersuchungen und Reaktionen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="767d3-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="767d3-121">Informationen zum Konfigurieren dieser Funktionen finden Sie [unter Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="767d3-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="767d3-122">Ihr eigener virtueller Analyst</span><span class="sxs-lookup"><span data-stu-id="767d3-122">Your own virtual analyst</span></span>

<span data-ttu-id="767d3-123">Stellen Sie sich vor, sie haben einen virtuellen Analysten in Ihrem Sicherheitsteam der Stufe 1 oder Ebene 2.</span><span class="sxs-lookup"><span data-stu-id="767d3-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="767d3-124">Der virtuelle Analyst imitiert die idealen Schritte, die das Sicherheitsteam zur Untersuchung und Behebung von Bedrohungen ausführen würde.</span><span class="sxs-lookup"><span data-stu-id="767d3-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="767d3-125">Der virtuelle Analyst könnte 24 x 7 mit unbegrenzter Kapazität arbeiten und eine erhebliche Anzahl von Untersuchungen und Bedrohungsbehebungen übernehmen.</span><span class="sxs-lookup"><span data-stu-id="767d3-125">The virtual analyst could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="767d3-126">Ein solcher virtueller Analytiker könnte die Reaktionszeit erheblich reduzieren und Ihr Sicherheitsteam für andere wichtige Bedrohungen oder strategische Projekte frei geben.</span><span class="sxs-lookup"><span data-stu-id="767d3-126">Such a virtual analyst could significantly reduce the time to respond, freeing up your security operations team for other important threats or strategic projects.</span></span> <span data-ttu-id="767d3-127">Wenn dieses Szenario nach Science Fiction klingt, ist dies nicht der Fall!</span><span class="sxs-lookup"><span data-stu-id="767d3-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="767d3-128">Ein solcher virtueller Analytiker ist Teil Ihrer Microsoft 365 Defender-Suite, und sein Name ist *automatisierte Untersuchung und Antwort.*</span><span class="sxs-lookup"><span data-stu-id="767d3-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="767d3-129">Automatisierte Untersuchungs- und Reaktionsfunktionen ermöglichen Es Ihrem Sicherheitsteam, die Kapazität Ihrer Organisation zur Verarbeitung von Sicherheitswarnungen und Vorfällen erheblich zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="767d3-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="767d3-130">Mit automatisierter Untersuchung und Reaktion können Sie die Kosten für den Umgang mit Untersuchungs- und Reaktionsaktivitäten reduzieren und das Beste aus Ihrer Bedrohungsschutzsuite nutzen.</span><span class="sxs-lookup"><span data-stu-id="767d3-130">With automated investigation and response, you can reduce the cost of dealing with investigation and response activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="767d3-131">Automatisierte Untersuchungs- und Reaktionsfunktionen unterstützen Ihr Sicherheitsteam durch:</span><span class="sxs-lookup"><span data-stu-id="767d3-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="767d3-132">Bestimmen, ob eine Bedrohung Eine Aktion erfordert.</span><span class="sxs-lookup"><span data-stu-id="767d3-132">Determining whether a threat requires action.</span></span>
2. <span data-ttu-id="767d3-133">Durchführen (oder Empfehlen) der erforderlichen Korrekturaktionen.</span><span class="sxs-lookup"><span data-stu-id="767d3-133">Taking (or recommending) any necessary remediation actions.</span></span>
3. <span data-ttu-id="767d3-134">Bestimmen, ob und welche weiteren Untersuchungen stattfinden sollen.</span><span class="sxs-lookup"><span data-stu-id="767d3-134">Determining whether and what other investigations should occur.</span></span>
4. <span data-ttu-id="767d3-135">Wiederholen des Vorgangs für andere Warnungen.</span><span class="sxs-lookup"><span data-stu-id="767d3-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="767d3-136">Der Prozess der automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="767d3-136">The automated investigation process</span></span>

<span data-ttu-id="767d3-137">Eine Warnung erstellt einen Vorfall, der eine automatisierte Untersuchung starten kann.</span><span class="sxs-lookup"><span data-stu-id="767d3-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="767d3-138">Die automatisierte Untersuchung führt zu einem Urteil für jedes Beweisstück.</span><span class="sxs-lookup"><span data-stu-id="767d3-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="767d3-139">Die Urteile können lauten:</span><span class="sxs-lookup"><span data-stu-id="767d3-139">Verdicts can be:</span></span>
- <span data-ttu-id="767d3-140">*Bösartig*</span><span class="sxs-lookup"><span data-stu-id="767d3-140">*Malicious*</span></span>
- <span data-ttu-id="767d3-141">*Verdächtig*</span><span class="sxs-lookup"><span data-stu-id="767d3-141">*Suspicious*</span></span> 
- <span data-ttu-id="767d3-142">*Keine Bedrohungen gefunden*</span><span class="sxs-lookup"><span data-stu-id="767d3-142">*No threats found*</span></span> 

<span data-ttu-id="767d3-143">Behebungsaktionen für bösartige oder verdächtige Entitäten werden identifiziert.</span><span class="sxs-lookup"><span data-stu-id="767d3-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="767d3-144">Beispiele für Korrekturaktionen sind:</span><span class="sxs-lookup"><span data-stu-id="767d3-144">Examples of remediation actions include:</span></span>

- <span data-ttu-id="767d3-145">Senden einer Datei in Quarantäne</span><span class="sxs-lookup"><span data-stu-id="767d3-145">Sending a file to quarantine</span></span>
- <span data-ttu-id="767d3-146">Beenden eines Prozesses</span><span class="sxs-lookup"><span data-stu-id="767d3-146">Stopping a process</span></span>
- <span data-ttu-id="767d3-147">Isolieren eines Geräts</span><span class="sxs-lookup"><span data-stu-id="767d3-147">Isolating a device</span></span>
- <span data-ttu-id="767d3-148">Blockieren einer URL</span><span class="sxs-lookup"><span data-stu-id="767d3-148">Blocking a URL</span></span> 
- <span data-ttu-id="767d3-149">Andere Aktionen</span><span class="sxs-lookup"><span data-stu-id="767d3-149">Other actions</span></span>

<span data-ttu-id="767d3-150">Weitere Informationen finden Sie unter [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).</span><span class="sxs-lookup"><span data-stu-id="767d3-150">For more information, see See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).</span></span>

<span data-ttu-id="767d3-151">Je [nachdem, wie automatisierte Untersuchungs-](m365d-configure-auto-investigation-response.md) und Reaktionsfunktionen für Ihre Organisation konfiguriert sind, werden Korrekturaktionen automatisch oder nur nach Genehmigung durch Ihr Sicherheitsteam ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="767d3-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="767d3-152">Alle Aktionen, ob ausstehend oder abgeschlossen, werden im [Aktionscenter aufgelistet.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="767d3-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="767d3-153">Während eine Untersuchung läuft, werden alle anderen zugehörigen Warnungen zur Untersuchung hinzugefügt, bis diese abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="767d3-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="767d3-154">Wenn eine betroffene Entität an anderer Stelle gesehen wird, erweitert die automatisierte Untersuchung ihren Umfang, um diese Entität zu umfassen, und der Untersuchungsprozess wiederholt sich.</span><span class="sxs-lookup"><span data-stu-id="767d3-154">If an affected entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="767d3-155">In Microsoft 365 Defender korreliert jede automatisierte Untersuchung Signale über Microsoft Defender for Identity, Microsoft Defender for Endpoint und Microsoft Defender für Office 365, wie in der folgenden Tabelle zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="767d3-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="767d3-156">Entitäten</span><span class="sxs-lookup"><span data-stu-id="767d3-156">Entities</span></span> |<span data-ttu-id="767d3-157">Dienste für den Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="767d3-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="767d3-158">Geräte (auch als Endpunkte oder Computer bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="767d3-158">Devices (also referred to as endpoints or machines)</span></span> |[<span data-ttu-id="767d3-159">Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="767d3-159">Defender for Endpoint</span></span>](../defender-endpoint/automated-investigations.md) |      
|<span data-ttu-id="767d3-160">Lokale Active Directory-Benutzer, Entitätsverhalten und Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="767d3-160">On-premises Active Directory users, entity behavior, and activities</span></span>     |[<span data-ttu-id="767d3-161">Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="767d3-161">Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="767d3-162">E-Mail-Inhalt (E-Mail-Nachrichten, die Dateien und URLs enthalten können)</span><span class="sxs-lookup"><span data-stu-id="767d3-162">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="767d3-163">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="767d3-163">Defender for Office 365</span></span>](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> <span data-ttu-id="767d3-164">Nicht jede Warnung löst eine automatisierte Untersuchung aus, und nicht jede Untersuchung führt zu automatisierten Korrekturaktionen.</span><span class="sxs-lookup"><span data-stu-id="767d3-164">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions.</span></span> <span data-ttu-id="767d3-165">Es hängt davon ab, wie die automatisierte Untersuchung und Reaktion für Ihre Organisation konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="767d3-165">It depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="767d3-166">Weitere [Informationen finden Sie unter Configure automated investigation and response capabilities](m365d-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="767d3-166">See [Configure automated investigation and response capabilities](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="viewing-a-list-of-investigations"></a><span data-ttu-id="767d3-167">Anzeigen einer Liste von Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="767d3-167">Viewing a list of investigations</span></span>

<span data-ttu-id="767d3-168">Wenn Sie Untersuchungen anzeigen möchten, wechseln Sie zur **Seite Vorfälle.**</span><span class="sxs-lookup"><span data-stu-id="767d3-168">To view investigations, go to the **Incidents** page.</span></span> <span data-ttu-id="767d3-169">Wählen Sie einen Vorfall aus, und wählen Sie dann die Registerkarte **Untersuchungen** aus. Weitere Informationen finden Sie unter [Details und Ergebnisse einer automatisierten Untersuchung.](m365d-autoir-results.md)</span><span class="sxs-lookup"><span data-stu-id="767d3-169">Select an incident, and then select the **Investigations** tab. To learn more, see [Details and results of an automated investigation](m365d-autoir-results.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="767d3-170">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="767d3-170">Next steps</span></span>

- [<span data-ttu-id="767d3-171">Sehen Sie sich die Voraussetzungen für eine automatisierte Untersuchung und Reaktion an.</span><span class="sxs-lookup"><span data-stu-id="767d3-171">See the prerequisites for automated investigation and response</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="767d3-172">Konfigurieren der automatisierten Untersuchung und Reaktion für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="767d3-172">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="767d3-173">Erfahren Sie mehr über das Info-Center</span><span class="sxs-lookup"><span data-stu-id="767d3-173">Learn more about the Action center</span></span>](m365d-action-center.md)
