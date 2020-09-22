---
title: Ausführen des Pilotprojekts "Microsoft Threat Protection"
description: Führen Sie das Microsoft Threat Protection-Pilotprojekt in Production aus, um die Vorteile und die Akzeptanz von Microsoft Threat Protection (MTP) effektiv zu ermitteln.
keywords: Microsoft Threat Protection Pilotprojekt, Ausführen eines Pilotprojekts für Microsoft Threat Protection, bewerten von Microsoft Threat Protection in der Produktion, Microsoft Threat Protection-Pilotprojekt, Cyber Security, Advanced persistent Threat, Enterprise Security, Devices, Device, Identity, users, Data, Applications, Incidents, Automated Investigation and Remediation, Advanced Hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 88d92558d86e0aa2e90ef04d88a3cd4676386f15
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195627"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="7d335-104">Ausführen des Pilotprojekts "Microsoft Threat Protection"</span><span class="sxs-lookup"><span data-stu-id="7d335-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7d335-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7d335-105">**Applies to:**</span></span>
- <span data-ttu-id="7d335-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7d335-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7d335-107">Um den Nutzen und die Akzeptanz von Microsoft Threat Protection (MTP) effektiv zu bestimmen, können Sie ein Pilotprojekt ausführen.</span><span class="sxs-lookup"><span data-stu-id="7d335-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="7d335-108">Vor dem Aktivieren von Microsoft Threat Protection in Ihrer Produktionsumgebung und beginnend mit definierten Anwendungsfällen sollten Sie am besten einen Planungsprozess durchlaufen, um die Aufgaben zu ermitteln, die in diesem Pilotprojekt erfüllt sein müssen, und die Erfolgskriterien.</span><span class="sxs-lookup"><span data-stu-id="7d335-108">Before enabling Microsoft Threat Protection in your production environment and starting with defined use cases, it is best to go through a planning process to determine the tasks that must be accomplished in this pilot project, and the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="7d335-109">Vorgehensweise zum Verwenden dieses Pilot Manuskripts</span><span class="sxs-lookup"><span data-stu-id="7d335-109">How to use this pilot playbook</span></span>

<span data-ttu-id="7d335-110">Dieses Handbuch enthält eine Übersicht über Microsoft Threat Protection und schrittweise Anleitungen zum Einrichten Ihres Pilotprojekts.</span><span class="sxs-lookup"><span data-stu-id="7d335-110">This guide provides an overview of Microsoft Threat Protection and step-by-step guidance on how to set up your pilot project.</span></span> 

![Phasen bei der Ausführung eines Microsoft Threat Protection-Pilotprojekts](../../media/pilotphases.png)

<span data-ttu-id="7d335-112">Das folgende Beispiel Zeitachse variiert je nach den richtigen Ressourcen in Ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="7d335-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="7d335-113">Einige Erkennungen und Workflows benötigen möglicherweise mehr Lern Zeit als die anderen.</span><span class="sxs-lookup"><span data-stu-id="7d335-113">Some detections and workflows might need more learning time than the others.</span></span>

![Beispiel Zeitachse bei der Ausführung eines Microsoft Threat Protection-Pilotprojekts](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="7d335-115">Um optimale Ergebnisse zu erzielen, befolgen Sie die Pilot Anweisungen so genau wie möglich.</span><span class="sxs-lookup"><span data-stu-id="7d335-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="7d335-116">Phasen des Pilot Textbuch</span><span class="sxs-lookup"><span data-stu-id="7d335-116">Pilot playbook phases</span></span> 

<span data-ttu-id="7d335-117">Bei der Ausführung eines Microsoft Threat Protection-Pilotprojekts gibt es vier Phasen:</span><span class="sxs-lookup"><span data-stu-id="7d335-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="7d335-118">Phase</span><span class="sxs-lookup"><span data-stu-id="7d335-118">Phase</span></span> | <span data-ttu-id="7d335-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d335-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="7d335-120">![Planung](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="7d335-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="7d335-121">Planung</span><span class="sxs-lookup"><span data-stu-id="7d335-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="7d335-122">Erfahren Sie, was Sie vor der Ausführung Ihres Microsoft Threat Protection-Pilotprojekts zu prüfen haben:</span><span class="sxs-lookup"><span data-stu-id="7d335-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="7d335-123">-Scope</span><span class="sxs-lookup"><span data-stu-id="7d335-123">- Scope</span></span> <br> <span data-ttu-id="7d335-124">-Anwendungsfälle</span><span class="sxs-lookup"><span data-stu-id="7d335-124">- Use cases</span></span> <br><span data-ttu-id="7d335-125">– Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d335-125">- Requirements</span></span> <br><span data-ttu-id="7d335-126">-Testplan</span><span class="sxs-lookup"><span data-stu-id="7d335-126">- Test plan</span></span> <br> <span data-ttu-id="7d335-127">-Erfolgskriterien</span><span class="sxs-lookup"><span data-stu-id="7d335-127">- Success criteria</span></span> <br> <span data-ttu-id="7d335-128">-Scorecard</span><span class="sxs-lookup"><span data-stu-id="7d335-128">- Scorecard</span></span> 
| <span data-ttu-id="7d335-129">![Vorbereitung](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="7d335-129">![Preparation](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="7d335-130">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="7d335-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="7d335-131">Greifen Sie auf das Microsoft 365 Security Center zu, um Ihre Microsoft Threat Protection-Pilotumgebung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="7d335-131">Access Microsoft 365 Security Center to setup your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="7d335-132">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="7d335-132">You will be guided to:</span></span><br><br><span data-ttu-id="7d335-133">-Identifizieren von Beteiligten und suchen der Anmeldung für ihr Pilotprojekt</span><span class="sxs-lookup"><span data-stu-id="7d335-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="7d335-134">-Umgebungs Überlegungen</span><span class="sxs-lookup"><span data-stu-id="7d335-134">- Environment considerations</span></span> <br><span data-ttu-id="7d335-135">-Access</span><span class="sxs-lookup"><span data-stu-id="7d335-135">- Access</span></span> <br><span data-ttu-id="7d335-136">-Azure-Active Directory-Setup</span><span class="sxs-lookup"><span data-stu-id="7d335-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="7d335-137">-Konfigurations Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="7d335-137">- Configuration order</span></span> <br> <span data-ttu-id="7d335-138">-Registrieren für Microsoft 365 E5-Testversion</span><span class="sxs-lookup"><span data-stu-id="7d335-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="7d335-139">-Domäne konfigurieren</span><span class="sxs-lookup"><span data-stu-id="7d335-139">- Configure domain</span></span> <br><span data-ttu-id="7d335-140">-Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="7d335-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="7d335-141">-Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="7d335-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="7d335-142">![Angriffssimulation](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="7d335-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="7d335-143">Angriffssimulation</span><span class="sxs-lookup"><span data-stu-id="7d335-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="7d335-144">Um einen Angriff zu simulieren, werden Sie zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="7d335-144">To simulate an attack, you will be guided to:</span></span><br><br><span data-ttu-id="7d335-145">-Überprüfen der Anforderungen an die Testumgebung</span><span class="sxs-lookup"><span data-stu-id="7d335-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="7d335-146">-Simulation ausführen</span><span class="sxs-lookup"><span data-stu-id="7d335-146">-  Run the simulation</span></span> <br><span data-ttu-id="7d335-147">-Untersuchen eines Vorfalls</span><span class="sxs-lookup"><span data-stu-id="7d335-147">- Investigate an incident</span></span> <br><span data-ttu-id="7d335-148">-Beheben des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="7d335-148">- resolve the incident</span></span> 
| <span data-ttu-id="7d335-149">![Schließen und Zusammenfassung](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="7d335-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="7d335-150">Schließen und Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="7d335-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="7d335-151">Wenn Sie das Ende des Prozesses erreicht haben, werden Sie zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="7d335-151">When you've reached the end of the process, you will be guided to:</span></span><br><br><span data-ttu-id="7d335-152">– Durchlaufen der endgültigen Ausgabe</span><span class="sxs-lookup"><span data-stu-id="7d335-152">- Go through your final output</span></span><br><span data-ttu-id="7d335-153">-Präsentieren ihrer Ausgaben für Ihre Stakeholder</span><span class="sxs-lookup"><span data-stu-id="7d335-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="7d335-154">-Feedback geben</span><span class="sxs-lookup"><span data-stu-id="7d335-154">- Provide feedback</span></span> <br><span data-ttu-id="7d335-155">– Nächste Schritte ausführen</span><span class="sxs-lookup"><span data-stu-id="7d335-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="7d335-156">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="7d335-156">Next step</span></span>
|<span data-ttu-id="7d335-157">![Planungsphase](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="7d335-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="7d335-158">Planungsphase</span><span class="sxs-lookup"><span data-stu-id="7d335-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="7d335-159">Planen Ihres Microsoft Threat Protection-Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="7d335-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
