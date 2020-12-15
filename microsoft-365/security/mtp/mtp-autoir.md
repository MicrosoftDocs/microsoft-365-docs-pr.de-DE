---
title: Automatische Untersuchung und Antwort in Microsoft 365 Defender
description: Erhalten Sie einen Überblick über die automatisierten Ermittlungs-und Antwortfunktionen, die auch als Selbstheilung bezeichnet werden, in Microsoft 365 Defender
keywords: automatisiert, Untersuchung, Warnung, Trigger, Aktion, Korrektur, Selbstheilung
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 7c28b7f3ac797f7402cfdb1f604fcef1e142a31b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683307"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="0e558-104">Automatische Untersuchung und Antwort in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e558-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0e558-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0e558-105">**Applies to:**</span></span>
- <span data-ttu-id="0e558-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e558-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="0e558-107">Möchten Sie Microsoft 365 Defender erfahren?</span><span class="sxs-lookup"><span data-stu-id="0e558-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="0e558-108">Sie können [es in einer Laborumgebung auswerten](https://aka.ms/mtp-trial-lab) oder [ihr Pilotprojekt in der Produktion ausführen](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="0e558-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="0e558-109">Funktionsweise der automatischen Untersuchung und Selbstheilung</span><span class="sxs-lookup"><span data-stu-id="0e558-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="0e558-110">Wenn Sicherheitswarnungen ausgelöst werden, liegt es an Ihrem Sicherheits Betriebsteam, diese Warnungen zu untersuchen und Maßnahmen zum Schutz Ihrer Organisation zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="0e558-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="0e558-111">Die Priorisierung und Untersuchung von Warnungen kann sehr zeitaufwändig sein, insbesondere dann, wenn ständig neue Benachrichtigungen während einer laufenden Untersuchung eingehen.</span><span class="sxs-lookup"><span data-stu-id="0e558-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="0e558-112">Sicherheitsteams können sich angesichts des enormen Volumens der Bedrohungen, die sie überwachen müssen, überfordert fühlen.</span><span class="sxs-lookup"><span data-stu-id="0e558-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="0e558-113">Automatisierte Ermittlungs-und Antwortfunktionen mit Selbstheilung in Microsoft 365 Defender können helfen.</span><span class="sxs-lookup"><span data-stu-id="0e558-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="0e558-114">Sehen Sie sich das folgende Video an, um zu erfahren, wie die Selbstheilung funktioniert:</span><span class="sxs-lookup"><span data-stu-id="0e558-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="0e558-115">In Microsoft 365 Defender funktioniert die automatische Untersuchung und Antwort mit Selbstheilungsfunktionen auf Ihren Geräten, e-Mail-& Inhalt und Identitäten.</span><span class="sxs-lookup"><span data-stu-id="0e558-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="0e558-116">In diesem Artikel wird beschrieben, wie automatisierte Untersuchungen und Antworten funktionieren.</span><span class="sxs-lookup"><span data-stu-id="0e558-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="0e558-117">Informationen zum Konfigurieren dieser Funktionen finden Sie unter [Configure Automated Investigation and Response Capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="0e558-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="0e558-118">Ihr eigener virtueller Analyst</span><span class="sxs-lookup"><span data-stu-id="0e558-118">Your own virtual analyst</span></span>

<span data-ttu-id="0e558-119">Stellen Sie sich vor, Sie haben in Ihrem Sicherheitsteam auf Ebene 1/Ebene 2 einen virtuellen Analysten.</span><span class="sxs-lookup"><span data-stu-id="0e558-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="0e558-120">Der virtuelle Analyst imitiert die idealen Schritte, die das Sicherheitsteam zur Untersuchung und Behebung von Bedrohungen ausführen würde.</span><span class="sxs-lookup"><span data-stu-id="0e558-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="0e558-121">Der virtuelle Assistent kann rund um die Uhr mit unbegrenzter Kapazität arbeiten und eine hohe Anzahl von Untersuchungen und Bedrohungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="0e558-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="0e558-122">Ein solcher virtueller Assistent kann die Reaktionszeit erheblich reduzieren, sodass Ihr Sicherheitsteam andere wichtige strategische Projekte übernehmen kann.</span><span class="sxs-lookup"><span data-stu-id="0e558-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="0e558-123">Wenn dieses Szenario wie Science Fiction klingt, ist es nicht!</span><span class="sxs-lookup"><span data-stu-id="0e558-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="0e558-124">Ein solcher virtueller Analyst ist Teil Ihrer Microsoft 365 Defender-Suite, und sein Name ist die *Automatische Untersuchung und Antwort*.</span><span class="sxs-lookup"><span data-stu-id="0e558-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="0e558-125">Durch die automatische Untersuchung und Antwort kann Ihr Sicherheits Betriebsteam die Kapazität Ihres Unternehmens zur Bewältigung von Sicherheitswarnungen und Vorfällen drastisch erhöhen.</span><span class="sxs-lookup"><span data-stu-id="0e558-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="0e558-126">Mit automatisierter Untersuchung und Antwort können Sie die Kosten für den Umgang mit Ermittlungs-und Korrekturmaßnahmen senken und ihre Bedrohungsschutz-Suite optimal nutzen.</span><span class="sxs-lookup"><span data-stu-id="0e558-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="0e558-127">die automatische Untersuchung und Antwort hilft Ihrem Security Operations-Team mit:</span><span class="sxs-lookup"><span data-stu-id="0e558-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="0e558-128">Ermitteln, ob eine Bedrohung eine Aktion erfordert;</span><span class="sxs-lookup"><span data-stu-id="0e558-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="0e558-129">Durchführen (oder Empfehlen) aller erforderlichen Wartungsmaßnahmen;</span><span class="sxs-lookup"><span data-stu-id="0e558-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="0e558-130">Ermitteln, welche weiteren Untersuchungen stattfinden sollten und</span><span class="sxs-lookup"><span data-stu-id="0e558-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="0e558-131">Wiederholen des Vorgangs für andere Warnungen.</span><span class="sxs-lookup"><span data-stu-id="0e558-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="0e558-132">Der Prozess der automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="0e558-132">The automated investigation process</span></span>

<span data-ttu-id="0e558-133">**Warnung** > **Vorfall** > **automatische Untersuchung** > **Urteil** > **Wartungsaktion**</span><span class="sxs-lookup"><span data-stu-id="0e558-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="0e558-134">Bei einer ausgelösten Warnung wird ein Vorfall erstellt, der eine automatisierte Untersuchung starten kann.</span><span class="sxs-lookup"><span data-stu-id="0e558-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="0e558-135">Diese Untersuchung kann zu einer oder mehreren Wartungsaktionen führen.</span><span class="sxs-lookup"><span data-stu-id="0e558-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="0e558-136">In Microsoft 365 Defender korreliert jede automatisierte Untersuchung Signale in Microsoft Defender for Identity, Microsoft Defender for Endpoint und Defender für Office 365, wie in der folgenden Tabelle zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="0e558-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="0e558-137">Entitäten</span><span class="sxs-lookup"><span data-stu-id="0e558-137">Entities</span></span> |<span data-ttu-id="0e558-138">Dienste für den Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="0e558-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="0e558-139">Geräte (auch als Endpunkte bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="0e558-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="0e558-140">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0e558-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="0e558-141">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="0e558-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="0e558-142">E-Mail-Inhalte (Dateien und Nachrichten in Postfächern)</span><span class="sxs-lookup"><span data-stu-id="0e558-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="0e558-143">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="0e558-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="0e558-144">Bei jeder Untersuchung werden Urteile (*böswillige*, *verdächtige* oder *nicht gefundene Bedrohungen*) für jedes untersuchte Beweisstück generiert.</span><span class="sxs-lookup"><span data-stu-id="0e558-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="0e558-145">Je nach Art der Bedrohung und dem daraus resultierenden Urteil werden Korrekturaktionen automatisch oder nach Genehmigung durch das Sicherheits Betriebsteam Ihrer Organisation durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e558-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="0e558-146">Ausstehende und abgeschlossene Aktionen werden im [Info-Center](mtp-action-center.md) aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="0e558-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="0e558-147">Während eine Untersuchung läuft, werden alle anderen zugehörigen Warnungen zur Untersuchung hinzugefügt, bis diese abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0e558-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="0e558-148">Wenn eine beschuldigte Entität an anderer Stelle angezeigt wird, wird auch diese Entität in die automatische Untersuchung aufgenommen, und es wird ein allgemeines Sicherheitsplaybook ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e558-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="0e558-149">Nicht jede Warnung löst eine automatisierte Untersuchung aus, und nicht jede Untersuchung führt zu automatisierten Korrekturaktionen. Dies hängt davon ab, wie die automatische Untersuchung und Antwort für Ihre Organisation konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="0e558-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="0e558-150">Weitere Informationen finden Sie unter [Configure Automated Investigation and Response Capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="0e558-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="0e558-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0e558-151">Next steps</span></span>

- [<span data-ttu-id="0e558-152">Weitere Informationen finden Sie unter Voraussetzungen für automatisierte Untersuchungen und Antworten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e558-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="0e558-153">Konfigurieren der automatischen Untersuchung und Reaktion für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="0e558-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="0e558-154">Erfahren Sie mehr über das Info-Center</span><span class="sxs-lookup"><span data-stu-id="0e558-154">Learn more about the Action center</span></span>](mtp-action-center.md)
