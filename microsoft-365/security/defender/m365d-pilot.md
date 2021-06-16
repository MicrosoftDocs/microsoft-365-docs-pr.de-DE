---
title: Ausführen des Pilotprojekts Microsoft 365 Defender-Projekts
description: Führen Sie Ihr Pilotprojekt Microsoft 365 Defender-Projekts in der Produktion aus, um die Vorteile und die Einführung von Microsoft 365 Defender effektiv zu ermitteln.
keywords: Microsoft 365 Defender-Pilotprojekt, Führen Sie ein Pilotprojekt Microsoft 365 Defender-Projekts aus, bewerten Sie Microsoft 365 Defender in der Produktion, Microsoft 365 Defender-Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatische Untersuchung und Behebung, erweiterte Suche
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 3219b329c53c32e02cd29acdd41a48cd93b2e8bb
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930511"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="8ac8f-104">Ausführen des Pilotprojekts Microsoft 365 Defender-Projekts</span><span class="sxs-lookup"><span data-stu-id="8ac8f-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8ac8f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8ac8f-105">**Applies to:**</span></span>
- <span data-ttu-id="8ac8f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ac8f-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="8ac8f-107">Dieser Leitfaden hilft Ihnen bei der Ausführung eines Pilotprojekts, indem Sie Zeiger bereitstellen, um sicherzustellen, dass Sie über einen gut strukturierten Plan verfügen, Sie durch die Verwendung des Angriffssimulationsfeatures führen und schließlich das Pilotprojekt mit wichtigen Take-Aways für Sie starten, um ergebnisse zu berücksichtigen und zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="8ac8f-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Phasen der Ausführung eines Microsoft 365 Defender-Pilotprojekts](../../media/pilotphases.png)


<span data-ttu-id="8ac8f-109">Die Ausführung eines Pilotprojekts hilft Ihnen, den Vorteil der Einführung von Microsoft 365 Defender effektiv zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="8ac8f-109">Running a pilot helps you effectively determine the benefit of adopting Microsoft 365 Defender.</span></span> <span data-ttu-id="8ac8f-110">Bevor Sie Microsoft 365 Defender in Ihrer Produktionsumgebung aktivieren und Ihre Anwendungsfälle starten, sollten Sie die für Ihr Pilotprojekt auszuführenden Aufgaben ermitteln und die Erfolgskriterien festlegen.</span><span class="sxs-lookup"><span data-stu-id="8ac8f-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="8ac8f-111">So verwenden Sie dieses Pilot-Playbook</span><span class="sxs-lookup"><span data-stu-id="8ac8f-111">How to use this pilot playbook</span></span>

<span data-ttu-id="8ac8f-112">Dieses Handbuch enthält eine Übersicht über Microsoft 365 Defender und schrittweise Anleitungen zum Einrichten Ihres Pilotprojekts.</span><span class="sxs-lookup"><span data-stu-id="8ac8f-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="8ac8f-113">Microsoft 365 Defender ist eine einheitliche Enterprise Defense Suite vor und nach der Verletzung, die Schutz, Erkennung, Verhinderung, Untersuchung und Reaktion auf Endpunkte, Identitäten, E-Mails und Anwendungen nativ koordiniert, um integrierten Schutz vor komplexen Angriffen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8ac8f-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="8ac8f-114">Dazu werden die folgenden Funktionen in einer einzigen Sicherheitslösung kombiniert und koordiniert:</span><span class="sxs-lookup"><span data-stu-id="8ac8f-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="8ac8f-115">Microsoft Defender für Endpunkt (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="8ac8f-115">Microsoft Defender for Endpoint (endpoints)</span></span>
  - <span data-ttu-id="8ac8f-116">Microsoft Defender für Office 365 (E-Mail)</span><span class="sxs-lookup"><span data-stu-id="8ac8f-116">Microsoft Defender for Office 365 (email)</span></span> 
  - <span data-ttu-id="8ac8f-117">Microsoft Defender for Identity (Identität)</span><span class="sxs-lookup"><span data-stu-id="8ac8f-117">Microsoft Defender for Identity (identity)</span></span> 
  - <span data-ttu-id="8ac8f-118">Microsoft Cloud App Security (Apps)</span><span class="sxs-lookup"><span data-stu-id="8ac8f-118">Microsoft Cloud App Security (apps)</span></span>

![Image of_Microsoft 365 Defender-Lösung für Benutzer, Microsoft Defender for Identity, für Endpunkte Microsoft Defender für Endpunkt, für Cloud-Apps, Microsoft Cloud App Security und für Daten, Microsoft Defender für Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="8ac8f-120">Mit der integrierten Microsoft 365 Defender-Lösung können Sicherheitsexperten die Bedrohungssignale, die Microsoft Defender für Endpunkt, Microsoft Defender für Office 365, Microsoft Defender for Identity und Microsoft Cloud App Security empfangen, zusammenfügen und den vollständigen Umfang und die Auswirkungen der Bedrohung ermitteln, wie sie in die Umgebung gelangt sind, was sie betrifft und wie sie sich derzeit auf die Organisation auswirkt.</span><span class="sxs-lookup"><span data-stu-id="8ac8f-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="8ac8f-121">Microsoft 365 Defender ergreift automatische Maßnahmen, um den Angriff zu verhindern oder zu beenden und die betroffenen Postfächer, Endpunkte und Benutzeridentitäten selbst zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ac8f-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="8ac8f-122">Weitere Informationen finden Sie in der [Übersicht über Microsoft 365 Defender.](microsoft-365-defender.md)</span><span class="sxs-lookup"><span data-stu-id="8ac8f-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>



<span data-ttu-id="8ac8f-123">Die folgende Beispielzeitachse hängt davon ab, ob Sie die richtigen Ressourcen in Ihrer Umgebung haben.</span><span class="sxs-lookup"><span data-stu-id="8ac8f-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="8ac8f-124">Einige Erkennungen und Workflows benötigen möglicherweise mehr Lernzeit als die anderen.</span><span class="sxs-lookup"><span data-stu-id="8ac8f-124">Some detections and workflows might need more learning time than the others.</span></span>

![Beispielzeitachse beim Ausführen eines Microsoft 365 Defender-Pilotprojekts](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="8ac8f-126">Um optimale Ergebnisse zu erzielen, befolgen Sie die Pilotanweisungen so genau wie möglich.</span><span class="sxs-lookup"><span data-stu-id="8ac8f-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="8ac8f-127">Pilot-Playbookphasen</span><span class="sxs-lookup"><span data-stu-id="8ac8f-127">Pilot playbook phases</span></span> 

<span data-ttu-id="8ac8f-128">Es gibt vier Phasen beim Ausführen eines Microsoft 365 Defender-Pilotprojekts:</span><span class="sxs-lookup"><span data-stu-id="8ac8f-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="8ac8f-129">Phase</span><span class="sxs-lookup"><span data-stu-id="8ac8f-129">Phase</span></span> | <span data-ttu-id="8ac8f-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ac8f-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="8ac8f-131">Planung</span><span class="sxs-lookup"><span data-stu-id="8ac8f-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="8ac8f-132">~ 1 Tag</span><span class="sxs-lookup"><span data-stu-id="8ac8f-132">~ 1 day</span></span>| <span data-ttu-id="8ac8f-133">Erfahren Sie, was Sie berücksichtigen müssen, bevor Sie Ihr Microsoft 365 Defender-Pilotprojekt ausführen:</span><span class="sxs-lookup"><span data-stu-id="8ac8f-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="8ac8f-134">– Bereich</span><span class="sxs-lookup"><span data-stu-id="8ac8f-134">- Scope</span></span> <br> <span data-ttu-id="8ac8f-135">– Anwendungsfälle</span><span class="sxs-lookup"><span data-stu-id="8ac8f-135">- Use cases</span></span> <br><span data-ttu-id="8ac8f-136">– Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ac8f-136">- Requirements</span></span> <br><span data-ttu-id="8ac8f-137">– Testplan</span><span class="sxs-lookup"><span data-stu-id="8ac8f-137">- Test plan</span></span> <br> <span data-ttu-id="8ac8f-138">– Erfolgskriterien</span><span class="sxs-lookup"><span data-stu-id="8ac8f-138">- Success criteria</span></span> <br> <span data-ttu-id="8ac8f-139">– Scorecard</span><span class="sxs-lookup"><span data-stu-id="8ac8f-139">- Scorecard</span></span> 
| [<span data-ttu-id="8ac8f-140">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="8ac8f-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="8ac8f-141">~2 Tage</span><span class="sxs-lookup"><span data-stu-id="8ac8f-141">~2 days</span></span>|  <span data-ttu-id="8ac8f-142">Greifen Sie auf Microsoft 365 Security Center zu, um Ihre Microsoft 365 Defender-Pilotumgebung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="8ac8f-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="8ac8f-143">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="8ac8f-143">You'll be guided to:</span></span><br><br><span data-ttu-id="8ac8f-144">– Identifizieren von Beteiligten und Anfordern der Anmeldung für Ihr Pilotprojekt</span><span class="sxs-lookup"><span data-stu-id="8ac8f-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="8ac8f-145">– Überlegungen zur Umgebung</span><span class="sxs-lookup"><span data-stu-id="8ac8f-145">- Environment considerations</span></span> <br><span data-ttu-id="8ac8f-146">– Zugriff</span><span class="sxs-lookup"><span data-stu-id="8ac8f-146">- Access</span></span> <br><span data-ttu-id="8ac8f-147">– Azure Active Directory Einrichten</span><span class="sxs-lookup"><span data-stu-id="8ac8f-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="8ac8f-148">- Konfigurationsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="8ac8f-148">- Configuration order</span></span> <br> <span data-ttu-id="8ac8f-149">– Registrieren für Microsoft 365 E5 Testversion</span><span class="sxs-lookup"><span data-stu-id="8ac8f-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="8ac8f-150">- Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="8ac8f-150">- Configure domain</span></span> <br><span data-ttu-id="8ac8f-151">– Zuweisen Microsoft 365 E5 Lizenzen</span><span class="sxs-lookup"><span data-stu-id="8ac8f-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="8ac8f-152">– Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="8ac8f-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="8ac8f-153">Angriffssimulation</span><span class="sxs-lookup"><span data-stu-id="8ac8f-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="8ac8f-154">~2 Tage</span><span class="sxs-lookup"><span data-stu-id="8ac8f-154">~2 days</span></span>| <span data-ttu-id="8ac8f-155">Um einen Angriff zu simulieren, werden Sie zu Folgendem geführt:</span><span class="sxs-lookup"><span data-stu-id="8ac8f-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="8ac8f-156">– Überprüfen der Anforderungen an die Testumgebung</span><span class="sxs-lookup"><span data-stu-id="8ac8f-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="8ac8f-157">- Ausführen der Simulation</span><span class="sxs-lookup"><span data-stu-id="8ac8f-157">-  Run the simulation</span></span> <br><span data-ttu-id="8ac8f-158">– Untersuchen eines Vorfalls</span><span class="sxs-lookup"><span data-stu-id="8ac8f-158">- Investigate an incident</span></span> <br><span data-ttu-id="8ac8f-159">– Beheben des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="8ac8f-159">- resolve the incident</span></span> 
| [<span data-ttu-id="8ac8f-160">Schließen und Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="8ac8f-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="8ac8f-161">~ 1 Tag</span><span class="sxs-lookup"><span data-stu-id="8ac8f-161">~ 1 day</span></span>| <span data-ttu-id="8ac8f-162">Wenn Sie das Ende des Prozesses erreicht haben, werden Sie zu Folgendem geführt:</span><span class="sxs-lookup"><span data-stu-id="8ac8f-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="8ac8f-163">– Durchlaufen Der endgültigen Ausgabe</span><span class="sxs-lookup"><span data-stu-id="8ac8f-163">- Go through your final output</span></span><br><span data-ttu-id="8ac8f-164">– Präsentieren Ihrer Ergebnisse für Ihre Projektbeteiligten</span><span class="sxs-lookup"><span data-stu-id="8ac8f-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="8ac8f-165">– Feedback geben</span><span class="sxs-lookup"><span data-stu-id="8ac8f-165">- Provide feedback</span></span> <br><span data-ttu-id="8ac8f-166">– Führen Sie die nächsten Schritte aus</span><span class="sxs-lookup"><span data-stu-id="8ac8f-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="8ac8f-167">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="8ac8f-167">Next step</span></span>
|[<span data-ttu-id="8ac8f-168">Planungsphase</span><span class="sxs-lookup"><span data-stu-id="8ac8f-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="8ac8f-169">Planen Ihres Microsoft 365 Defender-Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="8ac8f-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
