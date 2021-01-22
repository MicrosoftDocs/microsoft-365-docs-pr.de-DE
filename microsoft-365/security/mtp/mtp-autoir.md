---
title: Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender
description: Erhalten Sie einen Überblick über die automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender, die auch selbsterklingend genannt werden.
keywords: automatisiert, Untersuchung, Warnung, Trigger, Aktion, Problembehebung, Selbstbehebung
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930330"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="03522-104">Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03522-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="03522-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="03522-105">**Applies to:**</span></span>
- <span data-ttu-id="03522-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03522-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="03522-107">Möchten Sie Microsoft 365 Defender erleben?</span><span class="sxs-lookup"><span data-stu-id="03522-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="03522-108">Sie können [es in einer Laborumgebung auswerten oder](https://aka.ms/mtp-trial-lab) ihr Pilotprojekt in der Produktion [ausführen.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="03522-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="03522-109">Funktionsweise der automatischen Untersuchung und Selbsthilfe</span><span class="sxs-lookup"><span data-stu-id="03522-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="03522-110">Wenn Sicherheitswarnungen ausgelöst werden, ist es an Ihrem Sicherheitsteam, diese Warnungen zu betrachten und Maßnahmen zum Schutz Ihrer Organisation zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="03522-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="03522-111">Die Priorisierung und Untersuchung von Warnungen kann sehr zeitaufwändig sein, insbesondere dann, wenn ständig neue Benachrichtigungen während einer laufenden Untersuchung eingehen.</span><span class="sxs-lookup"><span data-stu-id="03522-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="03522-112">Sicherheitsteams können sich angesichts des enormen Volumens der Bedrohungen, die sie überwachen müssen, überfordert fühlen.</span><span class="sxs-lookup"><span data-stu-id="03522-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="03522-113">Automatisierte Untersuchungs- und Reaktionsfunktionen mit Selbsterl sung in Microsoft 365 Defender können hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="03522-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="03522-114">Sehen Sie sich das folgende Video an, um zu sehen, wie die Selbstrehung funktioniert:</span><span class="sxs-lookup"><span data-stu-id="03522-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="03522-115">In Microsoft 365 Defender funktioniert die automatisierte Untersuchung und Reaktion mit Selbsterklingungsfunktionen auf Ihren Geräten, E-Mail& Inhalten und Identitäten.</span><span class="sxs-lookup"><span data-stu-id="03522-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="03522-116">In diesem Artikel wird die Funktionsweise der automatischen Untersuchung und Reaktion beschrieben.</span><span class="sxs-lookup"><span data-stu-id="03522-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="03522-117">Informationen zum Konfigurieren dieser Funktionen finden Sie unter [Konfigurieren automatisierter Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="03522-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="03522-118">Ihr eigener virtueller Analyst</span><span class="sxs-lookup"><span data-stu-id="03522-118">Your own virtual analyst</span></span>

<span data-ttu-id="03522-119">Stellen Sie sich vor, Sie haben in Ihrem Sicherheitsteam auf Ebene 1/Ebene 2 einen virtuellen Analysten.</span><span class="sxs-lookup"><span data-stu-id="03522-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="03522-120">Der virtuelle Analyst imitiert die idealen Schritte, die das Sicherheitsteam zur Untersuchung und Behebung von Bedrohungen ausführen würde.</span><span class="sxs-lookup"><span data-stu-id="03522-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="03522-121">Der virtuelle Assistent kann rund um die Uhr mit unbegrenzter Kapazität arbeiten und eine hohe Anzahl von Untersuchungen und Bedrohungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="03522-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="03522-122">Ein solcher virtueller Assistent kann die Reaktionszeit erheblich reduzieren, sodass Ihr Sicherheitsteam andere wichtige strategische Projekte übernehmen kann.</span><span class="sxs-lookup"><span data-stu-id="03522-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="03522-123">Wenn dieses Szenario nach Science Fiction klingt, ist dies nicht der Fall!</span><span class="sxs-lookup"><span data-stu-id="03522-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="03522-124">Ein solcher virtueller Analyst ist Teil Ihrer Microsoft 365 Defender-Suite, und sein Name ist eine *automatisierte Untersuchung und Reaktion.*</span><span class="sxs-lookup"><span data-stu-id="03522-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="03522-125">Die automatisierte Untersuchung und Reaktion ermöglicht es Ihrem Sicherheitsteam, die Kapazität Ihrer Organisation für die Verarbeitung von Sicherheitswarnungen und Vorfällen erheblich zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="03522-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="03522-126">Mit einer automatisierten Untersuchung und Reaktion können Sie die Kosten für den Umgang mit Untersuchungs- und Korrekturaktivitäten reduzieren und Ihre Bedrohungsschutzsuite voll auslasten.</span><span class="sxs-lookup"><span data-stu-id="03522-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="03522-127">Automatisierte Untersuchung und Reaktion hilft Ihrem Sicherheitsteam durch:</span><span class="sxs-lookup"><span data-stu-id="03522-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="03522-128">Ermitteln, ob eine Bedrohung eine Aktion erfordert;</span><span class="sxs-lookup"><span data-stu-id="03522-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="03522-129">Durchführen (oder Empfehlen) aller erforderlichen Wartungsmaßnahmen;</span><span class="sxs-lookup"><span data-stu-id="03522-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="03522-130">Ermitteln, welche weiteren Untersuchungen stattfinden sollten und</span><span class="sxs-lookup"><span data-stu-id="03522-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="03522-131">Wiederholen des Vorgangs für andere Warnungen.</span><span class="sxs-lookup"><span data-stu-id="03522-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="03522-132">Der Prozess der automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="03522-132">The automated investigation process</span></span>

<span data-ttu-id="03522-133">**Warnung** > **Vorfall** > **automatische Untersuchung** > **Urteil** > **Wartungsaktion**</span><span class="sxs-lookup"><span data-stu-id="03522-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="03522-134">Eine ausgelöste Warnung erstellt einen Vorfall, der eine automatisierte Untersuchung starten kann.</span><span class="sxs-lookup"><span data-stu-id="03522-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="03522-135">Diese Untersuchung kann zu einer oder mehreren Wartungsaktionen führen.</span><span class="sxs-lookup"><span data-stu-id="03522-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="03522-136">In Microsoft 365 Defender korreliert jede automatisierte Untersuchung Signale in Microsoft Defender for Identity, Microsoft Defender für Endpoint und Defender für Office 365, wie in der folgenden Tabelle zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="03522-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="03522-137">Entitäten</span><span class="sxs-lookup"><span data-stu-id="03522-137">Entities</span></span> |<span data-ttu-id="03522-138">Dienste für den Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="03522-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="03522-139">Geräte (auch als Endpunkte bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="03522-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="03522-140">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="03522-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="03522-141">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="03522-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="03522-142">E-Mail-Inhalte (Dateien und Nachrichten in Postfächern)</span><span class="sxs-lookup"><span data-stu-id="03522-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="03522-143">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="03522-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="03522-144">Jede Untersuchung generiert Für jeden untersuchten Beweis eine Prüfung *(* Bösartig *,* verdächtig oder keine Bedrohungen gefunden).</span><span class="sxs-lookup"><span data-stu-id="03522-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="03522-145">Je nach Art der Bedrohung und der resultierenden Bekündung werden Korrekturaktionen automatisch oder nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03522-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="03522-146">Ausstehende und abgeschlossene Aktionen werden im [Info-Center](mtp-action-center.md) aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="03522-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="03522-147">Während eine Untersuchung läuft, werden alle anderen zugehörigen Warnungen zur Untersuchung hinzugefügt, bis diese abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="03522-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="03522-148">Wenn eine beschuldigte Entität an anderer Stelle angezeigt wird, wird auch diese Entität in die automatische Untersuchung aufgenommen, und es wird ein allgemeines Sicherheitsplaybook ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03522-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="03522-149">Nicht jede Warnung löst eine automatisierte Untersuchung aus, und nicht jede Untersuchung führt zu automatisierten Abhilfemaßnahmen. Dies alles hängt davon ab, wie die automatisierte Untersuchung und Reaktion für Ihre Organisation konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="03522-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="03522-150">Weitere [Informationen finden Sie unter Konfigurieren automatisierter Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="03522-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="03522-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="03522-151">Next steps</span></span>

- [<span data-ttu-id="03522-152">Sehen Sie sich die Voraussetzungen für die automatisierte Untersuchung und Reaktion in Microsoft 365 Defender an.</span><span class="sxs-lookup"><span data-stu-id="03522-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="03522-153">Konfigurieren der automatisierten Untersuchung und Reaktion für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="03522-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="03522-154">Erfahren Sie mehr über das Info-Center</span><span class="sxs-lookup"><span data-stu-id="03522-154">Learn more about the Action center</span></span>](mtp-action-center.md)
