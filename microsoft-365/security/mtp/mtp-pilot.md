---
title: Ausführen des Microsoft 365 -Pilotprojekts
description: Führen Sie Ihr Microsoft 365 -Pilotprojekt in der Produktion aus, um die Vorteile und die Akzeptanz von Microsoft 365 Defender effektiv zu ermitteln.
keywords: Microsoft Threat Protection-Pilotprojekt, Ausführen eines Microsoft Threat Protection-Pilotprojekts, Bewerten von Microsoft Threat Protection in der Produktion, Microsoft Threat Protection-Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Wartung, erweiterte Suche
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
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933030"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="1096d-104">Ausführen des Microsoft 365 -Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="1096d-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1096d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1096d-105">**Applies to:**</span></span>
- <span data-ttu-id="1096d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1096d-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="1096d-107">Dieses Handbuch unterstützt Sie bei der Ausführung eines Pilotprojekts, indem Sie Zeiger bereitstellen, um sicherzustellen, dass Sie über einen gut strukturierten Plan verfügen, Sie durch die Verwendung des Angriffssimulationsfeatures führen und schließlich das Pilotprojekt mit wichtigen Maßnahmen versehen, mit deren Hilfe Sie die Ergebnisse widerspiegeln und dokumentieren können.</span><span class="sxs-lookup"><span data-stu-id="1096d-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Phasen beim Ausführen eines Microsoft 365 Defender-Pilotprojekts](../../media/pilotphases.png)


<span data-ttu-id="1096d-109">Das Ausführen eines Pilotprojekts hilft Ihnen dabei, den Vorteil der Einführung von Microsoft 365 Defender effektiv zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="1096d-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="1096d-110">Bevor Sie Microsoft 365 Defender in Ihrer Produktionsumgebung aktivieren und Ihre Verwendungsfälle starten, empfiehlt es sich, die für Ihr Pilotprojekt auszuführende Aufgabe zu bestimmen und die Erfolgskriterien festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1096d-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="1096d-111">Verwenden dieses Pilotspielbuchs</span><span class="sxs-lookup"><span data-stu-id="1096d-111">How to use this pilot playbook</span></span>

<span data-ttu-id="1096d-112">Dieses Handbuch bietet eine Übersicht über Microsoft 365 Defender und schrittweise Anweisungen zum Einrichten Ihres Pilotprojekts.</span><span class="sxs-lookup"><span data-stu-id="1096d-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="1096d-113">Microsoft 365 Defender ist eine einheitliche Suite vor und nach der Verletzung des Unternehmens, die Schutz, Erkennung, Verhinderung, Untersuchung und Reaktion über Endpunkte, Identitäten, E-Mails und Anwendungen hinweg koordiniert, um integrierten Schutz vor ausgeklügelten Angriffen zu bieten.</span><span class="sxs-lookup"><span data-stu-id="1096d-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="1096d-114">Dazu werden die folgenden Funktionen in einer einzigen Sicherheitslösung kombiniert und orchestriert:</span><span class="sxs-lookup"><span data-stu-id="1096d-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="1096d-115">Microsoft Defender for Endpoint, der neue Name für Microsoft Defender Advanced Threat Protection (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="1096d-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="1096d-116">Microsoft Defender für Office 365, der neue Name für Office 365 ATP (E-Mail)</span><span class="sxs-lookup"><span data-stu-id="1096d-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="1096d-117">Microsoft Defender for Identity, der neue Name für Azure ATP (Identität)</span><span class="sxs-lookup"><span data-stu-id="1096d-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="1096d-118">Microsoft Cloud App Security (Apps)</span><span class="sxs-lookup"><span data-stu-id="1096d-118">Microsoft Cloud App Security (apps)</span></span>

![Abbildung of_Microsoft 365 Defender-Lösung für Benutzer, Microsoft Defender for Identity, für Endpunkte Microsoft Defender für Endpunkte, für Cloud-Apps, Microsoft Cloud App Security und für Daten, Microsoft Defender für Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="1096d-120">Mit der integrierten Microsoft 365 Defender-Lösung können Sicherheitsexperten die Bedrohungssignale zusammenbringen, die Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Defender for Identity und Microsoft Cloud App Security erhalten, und den vollständigen Umfang und die Auswirkungen der Bedrohung bestimmen, wie sie in die Umgebung eintrat, was sie beeinflusst und wie sie sich aktuell auf die Organisation auswirken.</span><span class="sxs-lookup"><span data-stu-id="1096d-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="1096d-121">Microsoft 365 Defender ergreift automatische Maßnahmen, um den Angriff zu verhindern oder zu stoppen und betroffene Postfächer, Endpunkte und Benutzeridentitäten selbst zu löschen.</span><span class="sxs-lookup"><span data-stu-id="1096d-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="1096d-122">Weitere Informationen finden Sie in der [Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) Defender-Übersicht.</span><span class="sxs-lookup"><span data-stu-id="1096d-122">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>



<span data-ttu-id="1096d-123">Die folgende Beispielzeitachse hängt davon ab, ob sie über die richtigen Ressourcen in Ihrer Umgebung verfügen.</span><span class="sxs-lookup"><span data-stu-id="1096d-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="1096d-124">Einige Erkennungen und Workflows benötigen möglicherweise mehr Lernzeit als die anderen.</span><span class="sxs-lookup"><span data-stu-id="1096d-124">Some detections and workflows might need more learning time than the others.</span></span>

![Beispielzeitachse bei der Ausführung eines Microsoft 365 Defender-Pilotprojekts](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="1096d-126">Befolgen Sie die Pilotanweisungen so genau wie möglich, um optimale Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="1096d-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="1096d-127">Phasen des Pilotspielbuchs</span><span class="sxs-lookup"><span data-stu-id="1096d-127">Pilot playbook phases</span></span> 

<span data-ttu-id="1096d-128">Es gibt vier Phasen beim Ausführen eines Microsoft 365 Defender-Pilotprojekts:</span><span class="sxs-lookup"><span data-stu-id="1096d-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="1096d-129">Phase</span><span class="sxs-lookup"><span data-stu-id="1096d-129">Phase</span></span> | <span data-ttu-id="1096d-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1096d-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="1096d-131">Planung</span><span class="sxs-lookup"><span data-stu-id="1096d-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="1096d-132">~ 1 Tag</span><span class="sxs-lookup"><span data-stu-id="1096d-132">~ 1 day</span></span>| <span data-ttu-id="1096d-133">Erfahren Sie, was Sie berücksichtigen müssen, bevor Sie Ihr Microsoft 365 Defender-Pilotprojekt ausführen:</span><span class="sxs-lookup"><span data-stu-id="1096d-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="1096d-134">– Bereich</span><span class="sxs-lookup"><span data-stu-id="1096d-134">- Scope</span></span> <br> <span data-ttu-id="1096d-135">– Verwendungsfälle</span><span class="sxs-lookup"><span data-stu-id="1096d-135">- Use cases</span></span> <br><span data-ttu-id="1096d-136">– Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1096d-136">- Requirements</span></span> <br><span data-ttu-id="1096d-137">– Testplan</span><span class="sxs-lookup"><span data-stu-id="1096d-137">- Test plan</span></span> <br> <span data-ttu-id="1096d-138">– Erfolgskriterien</span><span class="sxs-lookup"><span data-stu-id="1096d-138">- Success criteria</span></span> <br> <span data-ttu-id="1096d-139">- Scorecard</span><span class="sxs-lookup"><span data-stu-id="1096d-139">- Scorecard</span></span> 
| [<span data-ttu-id="1096d-140">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="1096d-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="1096d-141">~2 Tage</span><span class="sxs-lookup"><span data-stu-id="1096d-141">~2 days</span></span>|  <span data-ttu-id="1096d-142">Greifen Sie auf das Microsoft 365 Security Center zu, um Ihre Microsoft 365 Defender-Pilotumgebung zu einrichten.</span><span class="sxs-lookup"><span data-stu-id="1096d-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="1096d-143">Sie werden geführt zu:</span><span class="sxs-lookup"><span data-stu-id="1096d-143">You'll be guided to:</span></span><br><br><span data-ttu-id="1096d-144">– Identifizieren von Beteiligten und Abmelden für Ihr Pilotprojekt</span><span class="sxs-lookup"><span data-stu-id="1096d-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="1096d-145">– Überlegungen zur Umgebung</span><span class="sxs-lookup"><span data-stu-id="1096d-145">- Environment considerations</span></span> <br><span data-ttu-id="1096d-146">– Zugriff</span><span class="sxs-lookup"><span data-stu-id="1096d-146">- Access</span></span> <br><span data-ttu-id="1096d-147">– Azure Active Directory Setup</span><span class="sxs-lookup"><span data-stu-id="1096d-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="1096d-148">– Konfigurationsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="1096d-148">- Configuration order</span></span> <br> <span data-ttu-id="1096d-149">– Registrieren für die Testversion von Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1096d-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="1096d-150">- Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="1096d-150">- Configure domain</span></span> <br><span data-ttu-id="1096d-151">– Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="1096d-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="1096d-152">– Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="1096d-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="1096d-153">Angriffssimulation</span><span class="sxs-lookup"><span data-stu-id="1096d-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="1096d-154">~2 Tage</span><span class="sxs-lookup"><span data-stu-id="1096d-154">~2 days</span></span>| <span data-ttu-id="1096d-155">Um einen Angriff zu simulieren, werden Sie geführt zu:</span><span class="sxs-lookup"><span data-stu-id="1096d-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="1096d-156">– Überprüfen der Anforderungen an die Testumgebung</span><span class="sxs-lookup"><span data-stu-id="1096d-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="1096d-157">– Ausführen der Simulation</span><span class="sxs-lookup"><span data-stu-id="1096d-157">-  Run the simulation</span></span> <br><span data-ttu-id="1096d-158">– Untersuchen eines Vorfalls</span><span class="sxs-lookup"><span data-stu-id="1096d-158">- Investigate an incident</span></span> <br><span data-ttu-id="1096d-159">– Beheben des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="1096d-159">- resolve the incident</span></span> 
| [<span data-ttu-id="1096d-160">Schließen und Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1096d-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="1096d-161">~ 1 Tag</span><span class="sxs-lookup"><span data-stu-id="1096d-161">~ 1 day</span></span>| <span data-ttu-id="1096d-162">Wenn Sie das Ende des Prozesses erreicht haben, werden Sie geführt zu:</span><span class="sxs-lookup"><span data-stu-id="1096d-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="1096d-163">– Durchgehen der endgültigen Ausgabe</span><span class="sxs-lookup"><span data-stu-id="1096d-163">- Go through your final output</span></span><br><span data-ttu-id="1096d-164">– Präsentieren Ihrer Ergebnisse für Ihre Projektbeteiligten</span><span class="sxs-lookup"><span data-stu-id="1096d-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="1096d-165">– Feedback geben</span><span class="sxs-lookup"><span data-stu-id="1096d-165">- Provide feedback</span></span> <br><span data-ttu-id="1096d-166">– Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1096d-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="1096d-167">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="1096d-167">Next step</span></span>
|[<span data-ttu-id="1096d-168">Planungsphase</span><span class="sxs-lookup"><span data-stu-id="1096d-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="1096d-169">Planen Ihres Microsoft 365 Defender-Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="1096d-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
