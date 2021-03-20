---
title: Ausführen des Microsoft 365 Defender-Pilotprojekts
description: Führen Sie Ihr Microsoft 365 Defender-Pilotprojekt in der Produktion aus, um die Vorteile und die Einführung von Microsoft 365 Defender effektiv zu ermitteln.
keywords: Microsoft Threat Protection-Pilotprojekt, Ausführen eines Microsoft Threat Protection-Pilotprojekts, Bewerten von Microsoft Threat Protection in der Produktion, Microsoft Threat Protection-Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c6c373d084c7f7cf12073c6402695af644944bad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910870"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="c3119-104">Ausführen des Microsoft 365 Defender-Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="c3119-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c3119-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c3119-105">**Applies to:**</span></span>
- <span data-ttu-id="c3119-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3119-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="c3119-107">Dieses Handbuch hilft Ihnen bei der Ausführung eines Pilotprojekts, indem Sie Zeiger bereitstellen, um sicherzustellen, dass Sie über einen gut strukturierten Plan verfügen, Sie durch die Verwendung des Angriffssimulationsfeatures führen und schließlich das Pilotprojekt mit wichtigen Take-Aways für Sie zum Reflektieren und Dokumentieren von Ergebnissen enth fen.</span><span class="sxs-lookup"><span data-stu-id="c3119-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Phasen beim Ausführen eines Microsoft 365 Defender-Pilotprojekts](../../media/pilotphases.png)


<span data-ttu-id="c3119-109">Das Ausführen eines Pilotprojekts hilft Ihnen, den Vorteil der Einführung von Microsoft 365 Defender effektiv zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c3119-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="c3119-110">Bevor Sie Microsoft 365 Defender in Ihrer Produktionsumgebung aktivieren und Ihre Verwendungsfälle starten, sollten Sie die Aufgaben für Ihr Pilotprojekt ermitteln und die Erfolgskriterien festlegen.</span><span class="sxs-lookup"><span data-stu-id="c3119-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="c3119-111">Verwenden dieses Pilotspielbuchs</span><span class="sxs-lookup"><span data-stu-id="c3119-111">How to use this pilot playbook</span></span>

<span data-ttu-id="c3119-112">Dieses Handbuch bietet eine Übersicht über Microsoft 365 Defender und schrittweise Anweisungen zum Einrichten Ihres Pilotprojekts.</span><span class="sxs-lookup"><span data-stu-id="c3119-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="c3119-113">Microsoft 365 Defender ist eine einheitliche Vor- und Nachverletzungssuite für die Unternehmensverteidigung, die Schutz, Erkennung, Verhinderung, Untersuchung und Reaktion auf Endpunkte, Identitäten, E-Mails und Anwendungen nativ koordiniert, um integrierten Schutz vor komplexen Angriffen zu bieten.</span><span class="sxs-lookup"><span data-stu-id="c3119-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="c3119-114">Dazu werden die folgenden Funktionen in einer einzigen Sicherheitslösung kombiniert und orchestriert:</span><span class="sxs-lookup"><span data-stu-id="c3119-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="c3119-115">Microsoft Defender for Endpoint, der neue Name für Microsoft Defender Advanced Threat Protection (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="c3119-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="c3119-116">Microsoft Defender für Office 365, der neue Name für Office 365 ATP (E-Mail)</span><span class="sxs-lookup"><span data-stu-id="c3119-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="c3119-117">Microsoft Defender for Identity, der neue Name für Azure ATP (Identity)</span><span class="sxs-lookup"><span data-stu-id="c3119-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="c3119-118">Microsoft Cloud App Security (Apps)</span><span class="sxs-lookup"><span data-stu-id="c3119-118">Microsoft Cloud App Security (apps)</span></span>

![Image of_Microsoft 365 Defender-Lösung für Benutzer, Microsoft Defender for Identity, für Endpunkte Microsoft Defender for Endpoint, für Cloud-Apps, Microsoft Cloud App Security und für Daten, Microsoft Defender für Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="c3119-120">Mit der integrierten Microsoft 365 Defender-Lösung können Sicherheitsexperten die Bedrohungssignale zusammenbringen, die Microsoft Defender for Endpoint, Microsoft Defender für Office 365, Microsoft Defender for Identity und Microsoft Cloud App Security empfangen, und den vollständigen Umfang und die Auswirkungen der Bedrohung bestimmen, wie sie in die Umgebung eintrat, welche Auswirkungen sie hat und wie sie sich derzeit auf die Organisation auswirken.</span><span class="sxs-lookup"><span data-stu-id="c3119-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="c3119-121">Microsoft 365 Defender ergreift automatische Maßnahmen, um den Angriff zu verhindern oder zu beenden und betroffene Postfächer, Endpunkte und Benutzeridentitäten selbst zu beenden.</span><span class="sxs-lookup"><span data-stu-id="c3119-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="c3119-122">Weitere Informationen finden Sie in der [Microsoft 365 Defender-Übersicht.](./microsoft-threat-protection.md)</span><span class="sxs-lookup"><span data-stu-id="c3119-122">See the [Microsoft 365 Defender overview](./microsoft-threat-protection.md) for details.</span></span>



<span data-ttu-id="c3119-123">Die folgende Beispielzeitachse variiert je nach den richtigen Ressourcen in Ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="c3119-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="c3119-124">Einige Erkennungen und Workflows benötigen möglicherweise mehr Lernzeit als die anderen.</span><span class="sxs-lookup"><span data-stu-id="c3119-124">Some detections and workflows might need more learning time than the others.</span></span>

![Beispielzeitachse beim Ausführen eines Microsoft 365 Defender-Pilotprojekts](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="c3119-126">Befolgen Sie die Pilotanweisungen so genau wie möglich, um optimale Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="c3119-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="c3119-127">Pilot-Playbook-Phasen</span><span class="sxs-lookup"><span data-stu-id="c3119-127">Pilot playbook phases</span></span> 

<span data-ttu-id="c3119-128">Es gibt vier Phasen beim Ausführen eines Microsoft 365 Defender-Pilotprojekts:</span><span class="sxs-lookup"><span data-stu-id="c3119-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="c3119-129">Phase</span><span class="sxs-lookup"><span data-stu-id="c3119-129">Phase</span></span> | <span data-ttu-id="c3119-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3119-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="c3119-131">Planung</span><span class="sxs-lookup"><span data-stu-id="c3119-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="c3119-132">~ 1 Tag</span><span class="sxs-lookup"><span data-stu-id="c3119-132">~ 1 day</span></span>| <span data-ttu-id="c3119-133">Erfahren Sie, was Sie berücksichtigen müssen, bevor Sie Ihr Microsoft 365 Defender-Pilotprojekt ausführen:</span><span class="sxs-lookup"><span data-stu-id="c3119-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="c3119-134">– Bereich</span><span class="sxs-lookup"><span data-stu-id="c3119-134">- Scope</span></span> <br> <span data-ttu-id="c3119-135">- Use cases</span><span class="sxs-lookup"><span data-stu-id="c3119-135">- Use cases</span></span> <br><span data-ttu-id="c3119-136">– Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c3119-136">- Requirements</span></span> <br><span data-ttu-id="c3119-137">- Testplan</span><span class="sxs-lookup"><span data-stu-id="c3119-137">- Test plan</span></span> <br> <span data-ttu-id="c3119-138">– Erfolgskriterien</span><span class="sxs-lookup"><span data-stu-id="c3119-138">- Success criteria</span></span> <br> <span data-ttu-id="c3119-139">- Scorecard</span><span class="sxs-lookup"><span data-stu-id="c3119-139">- Scorecard</span></span> 
| [<span data-ttu-id="c3119-140">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="c3119-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="c3119-141">~2 Tage</span><span class="sxs-lookup"><span data-stu-id="c3119-141">~2 days</span></span>|  <span data-ttu-id="c3119-142">Greifen Sie auf Microsoft 365 Security Center zu, um Ihre Microsoft 365 Defender-Pilotumgebung zu einrichten.</span><span class="sxs-lookup"><span data-stu-id="c3119-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="c3119-143">Sie werden geführt zu:</span><span class="sxs-lookup"><span data-stu-id="c3119-143">You'll be guided to:</span></span><br><br><span data-ttu-id="c3119-144">– Identifizieren von Beteiligten und Abmelden für Ihr Pilotprojekt</span><span class="sxs-lookup"><span data-stu-id="c3119-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="c3119-145">– Überlegungen zur Umgebung</span><span class="sxs-lookup"><span data-stu-id="c3119-145">- Environment considerations</span></span> <br><span data-ttu-id="c3119-146">- Access</span><span class="sxs-lookup"><span data-stu-id="c3119-146">- Access</span></span> <br><span data-ttu-id="c3119-147">– Azure Active Directory-Setup</span><span class="sxs-lookup"><span data-stu-id="c3119-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="c3119-148">- Konfigurationsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="c3119-148">- Configuration order</span></span> <br> <span data-ttu-id="c3119-149">- Registrieren für Microsoft 365 E5-Testversion</span><span class="sxs-lookup"><span data-stu-id="c3119-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="c3119-150">- Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="c3119-150">- Configure domain</span></span> <br><span data-ttu-id="c3119-151">– Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="c3119-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="c3119-152">– Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="c3119-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="c3119-153">Angriffssimulation</span><span class="sxs-lookup"><span data-stu-id="c3119-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="c3119-154">~2 Tage</span><span class="sxs-lookup"><span data-stu-id="c3119-154">~2 days</span></span>| <span data-ttu-id="c3119-155">Um einen Angriff zu simulieren, werden Sie geführt zu:</span><span class="sxs-lookup"><span data-stu-id="c3119-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="c3119-156">– Überprüfen der Anforderungen an die Testumgebung</span><span class="sxs-lookup"><span data-stu-id="c3119-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="c3119-157">– Ausführen der Simulation</span><span class="sxs-lookup"><span data-stu-id="c3119-157">-  Run the simulation</span></span> <br><span data-ttu-id="c3119-158">- Untersuchen eines Vorfalls</span><span class="sxs-lookup"><span data-stu-id="c3119-158">- Investigate an incident</span></span> <br><span data-ttu-id="c3119-159">– Beheben des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="c3119-159">- resolve the incident</span></span> 
| [<span data-ttu-id="c3119-160">Schließen und Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="c3119-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="c3119-161">~ 1 Tag</span><span class="sxs-lookup"><span data-stu-id="c3119-161">~ 1 day</span></span>| <span data-ttu-id="c3119-162">Wenn Sie das Ende des Prozesses erreicht haben, werden Sie geführt zu:</span><span class="sxs-lookup"><span data-stu-id="c3119-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="c3119-163">- Gehen Sie durch Die endgültige Ausgabe</span><span class="sxs-lookup"><span data-stu-id="c3119-163">- Go through your final output</span></span><br><span data-ttu-id="c3119-164">– Präsentieren Sie Ihre Ergebnisse ihren Beteiligten</span><span class="sxs-lookup"><span data-stu-id="c3119-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="c3119-165">- Feedback bereitstellen</span><span class="sxs-lookup"><span data-stu-id="c3119-165">- Provide feedback</span></span> <br><span data-ttu-id="c3119-166">– Ausführen der nächsten Schritte</span><span class="sxs-lookup"><span data-stu-id="c3119-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="c3119-167">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c3119-167">Next step</span></span>
|[<span data-ttu-id="c3119-168">Planungsphase</span><span class="sxs-lookup"><span data-stu-id="c3119-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="c3119-169">Planen Ihres Microsoft 365 Defender-Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="c3119-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|