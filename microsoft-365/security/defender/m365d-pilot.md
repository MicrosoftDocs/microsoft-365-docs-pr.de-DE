---
title: Ausführen des Pilotprojekts Microsoft 365 Defender-Projekts
description: Führen Sie Ihr Microsoft 365 Defender-Projekt in der Produktion aus, um die Vorteile und die Akzeptanz von Defender Microsoft 365 bestimmen.
keywords: Microsoft 365 Defender-Pilot, Ausführen eines Pilotprojekts Microsoft 365 Defender-Projekt, Evaluieren von Microsoft 365 Defender in der Produktion, Microsoft 365 Defender-Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Geräte, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
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
ms.openlocfilehash: b1616b39597a90ff8e8f7b4c92f29f75c62fea18
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934429"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="f815f-104">Ausführen des Pilotprojekts Microsoft 365 Defender-Projekts</span><span class="sxs-lookup"><span data-stu-id="f815f-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f815f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f815f-105">**Applies to:**</span></span>
- <span data-ttu-id="f815f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f815f-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="f815f-107">Dieses Handbuch hilft Ihnen bei der Ausführung eines Pilotprojekts, indem Sie Zeiger bereitstellen, um sicherzustellen, dass Sie über einen gut strukturierten Plan verfügen, Sie durch die Verwendung des Angriffssimulationsfeatures führen und schließlich das Pilotprojekt mit wichtigen Take-Aways für Sie zum Reflektieren und Dokumentieren von Ergebnissen enth fen.</span><span class="sxs-lookup"><span data-stu-id="f815f-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Phasen beim Ausführen eines Microsoft 365 Defender-Pilot](../../media/pilotphases.png)


<span data-ttu-id="f815f-109">Das Ausführen eines Pilotprojekts hilft Ihnen, den Nutzen der Einführung von Microsoft 365 zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="f815f-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="f815f-110">Bevor Sie Microsoft 365 Defender in Ihrer Produktionsumgebung aktivieren und Ihre Verwendungsfälle starten, sollten Sie die Aufgaben für Ihr Pilotprojekt ermitteln und die Erfolgskriterien festlegen.</span><span class="sxs-lookup"><span data-stu-id="f815f-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="f815f-111">Verwenden dieses Pilotspielbuchs</span><span class="sxs-lookup"><span data-stu-id="f815f-111">How to use this pilot playbook</span></span>

<span data-ttu-id="f815f-112">Dieses Handbuch bietet eine Übersicht über Microsoft 365 Defender und schrittweise Anweisungen zum Einrichten Ihres Pilotprojekts.</span><span class="sxs-lookup"><span data-stu-id="f815f-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="f815f-113">Microsoft 365 Defender ist eine einheitliche Vor- und Nachverletzungs-Enterprise-Defense-Suite, die Schutz, Erkennung, Verhinderung, Untersuchung und Reaktion auf Endpunkte, Identitäten, E-Mails und Anwendungen nativ koordiniert, um integrierten Schutz vor komplexen Angriffen zu bieten.</span><span class="sxs-lookup"><span data-stu-id="f815f-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="f815f-114">Dazu werden die folgenden Funktionen in einer einzigen Sicherheitslösung kombiniert und orchestriert:</span><span class="sxs-lookup"><span data-stu-id="f815f-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="f815f-115">Microsoft Defender for Endpoint (Endpoints)</span><span class="sxs-lookup"><span data-stu-id="f815f-115">Microsoft Defender for Endpoint (endpoints)</span></span>
  - <span data-ttu-id="f815f-116">Microsoft Defender für Office 365 (E-Mail)</span><span class="sxs-lookup"><span data-stu-id="f815f-116">Microsoft Defender for Office 365 (email)</span></span> 
  - <span data-ttu-id="f815f-117">Microsoft Defender for Identity (Identity)</span><span class="sxs-lookup"><span data-stu-id="f815f-117">Microsoft Defender for Identity (identity)</span></span> 
  - <span data-ttu-id="f815f-118">Microsoft Cloud App Security (Apps)</span><span class="sxs-lookup"><span data-stu-id="f815f-118">Microsoft Cloud App Security (apps)</span></span>

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="f815f-120">Mit der integrierten Microsoft 365 Defender-Lösung können Sicherheitsexperten die Bedrohungssignale, die Microsoft Defender for Endpoint, Microsoft Defender für Office 365, Microsoft Defender for Identity und Microsoft Cloud App Security empfangen, zusammenbringen und den umfang und die Auswirkungen der Bedrohung, den Ein-/Aus-Umgebungs-, Denk- und Wirkungsbereich der Bedrohung bestimmen.</span><span class="sxs-lookup"><span data-stu-id="f815f-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="f815f-121">Microsoft 365 Defender ergreift automatische Maßnahmen, um den Angriff zu verhindern oder zu beenden und betroffene Postfächer, Endpunkte und Benutzeridentitäten selbst zu beenden.</span><span class="sxs-lookup"><span data-stu-id="f815f-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="f815f-122">Weitere Informationen [finden Microsoft 365 defender overview.](microsoft-365-defender.md)</span><span class="sxs-lookup"><span data-stu-id="f815f-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>



<span data-ttu-id="f815f-123">Die folgende Beispielzeitachse variiert je nach den richtigen Ressourcen in Ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="f815f-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="f815f-124">Einige Erkennungen und Workflows benötigen möglicherweise mehr Lernzeit als die anderen.</span><span class="sxs-lookup"><span data-stu-id="f815f-124">Some detections and workflows might need more learning time than the others.</span></span>

![Beispielzeitachse beim Ausführen eines Microsoft 365 Defender-Pilot](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="f815f-126">Befolgen Sie die Pilotanweisungen so genau wie möglich, um optimale Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="f815f-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="f815f-127">Pilot-Playbook-Phasen</span><span class="sxs-lookup"><span data-stu-id="f815f-127">Pilot playbook phases</span></span> 

<span data-ttu-id="f815f-128">Es gibt vier Phasen beim Ausführen eines Microsoft 365 Defender-Piloten:</span><span class="sxs-lookup"><span data-stu-id="f815f-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="f815f-129">Phase</span><span class="sxs-lookup"><span data-stu-id="f815f-129">Phase</span></span> | <span data-ttu-id="f815f-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f815f-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="f815f-131">Planung</span><span class="sxs-lookup"><span data-stu-id="f815f-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="f815f-132">~ 1 Tag</span><span class="sxs-lookup"><span data-stu-id="f815f-132">~ 1 day</span></span>| <span data-ttu-id="f815f-133">Erfahren Sie, was Sie berücksichtigen müssen, bevor Sie Ihr Microsoft 365 Defender-Pilotprojekt ausführen:</span><span class="sxs-lookup"><span data-stu-id="f815f-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="f815f-134">– Bereich</span><span class="sxs-lookup"><span data-stu-id="f815f-134">- Scope</span></span> <br> <span data-ttu-id="f815f-135">- Use cases</span><span class="sxs-lookup"><span data-stu-id="f815f-135">- Use cases</span></span> <br><span data-ttu-id="f815f-136">– Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f815f-136">- Requirements</span></span> <br><span data-ttu-id="f815f-137">- Testplan</span><span class="sxs-lookup"><span data-stu-id="f815f-137">- Test plan</span></span> <br> <span data-ttu-id="f815f-138">– Erfolgskriterien</span><span class="sxs-lookup"><span data-stu-id="f815f-138">- Success criteria</span></span> <br> <span data-ttu-id="f815f-139">- Scorecard</span><span class="sxs-lookup"><span data-stu-id="f815f-139">- Scorecard</span></span> 
| [<span data-ttu-id="f815f-140">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="f815f-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="f815f-141">~2 Tage</span><span class="sxs-lookup"><span data-stu-id="f815f-141">~2 days</span></span>|  <span data-ttu-id="f815f-142">Access Microsoft 365 Security Center zum Einrichten ihrer Microsoft 365 Defender-Pilotumgebung.</span><span class="sxs-lookup"><span data-stu-id="f815f-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="f815f-143">Sie werden geführt zu:</span><span class="sxs-lookup"><span data-stu-id="f815f-143">You'll be guided to:</span></span><br><br><span data-ttu-id="f815f-144">– Identifizieren von Beteiligten und Abmelden für Ihr Pilotprojekt</span><span class="sxs-lookup"><span data-stu-id="f815f-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="f815f-145">– Überlegungen zur Umgebung</span><span class="sxs-lookup"><span data-stu-id="f815f-145">- Environment considerations</span></span> <br><span data-ttu-id="f815f-146">- Access</span><span class="sxs-lookup"><span data-stu-id="f815f-146">- Access</span></span> <br><span data-ttu-id="f815f-147">- Azure Active Directory Setup</span><span class="sxs-lookup"><span data-stu-id="f815f-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="f815f-148">- Konfigurationsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="f815f-148">- Configuration order</span></span> <br> <span data-ttu-id="f815f-149">– Registrieren für Microsoft 365 E5 Testversion</span><span class="sxs-lookup"><span data-stu-id="f815f-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="f815f-150">- Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="f815f-150">- Configure domain</span></span> <br><span data-ttu-id="f815f-151">- Zuweisen Microsoft 365 E5 Lizenzen</span><span class="sxs-lookup"><span data-stu-id="f815f-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="f815f-152">– Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="f815f-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="f815f-153">Angriffssimulator</span><span class="sxs-lookup"><span data-stu-id="f815f-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="f815f-154">~2 Tage</span><span class="sxs-lookup"><span data-stu-id="f815f-154">~2 days</span></span>| <span data-ttu-id="f815f-155">Um einen Angriff zu simulieren, werden Sie geführt zu:</span><span class="sxs-lookup"><span data-stu-id="f815f-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="f815f-156">– Überprüfen der Anforderungen an die Testumgebung</span><span class="sxs-lookup"><span data-stu-id="f815f-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="f815f-157">– Ausführen der Simulation</span><span class="sxs-lookup"><span data-stu-id="f815f-157">-  Run the simulation</span></span> <br><span data-ttu-id="f815f-158">- Untersuchen eines Vorfalls</span><span class="sxs-lookup"><span data-stu-id="f815f-158">- Investigate an incident</span></span> <br><span data-ttu-id="f815f-159">– Beheben des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="f815f-159">- resolve the incident</span></span> 
| [<span data-ttu-id="f815f-160">Schließen und Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="f815f-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="f815f-161">~ 1 Tag</span><span class="sxs-lookup"><span data-stu-id="f815f-161">~ 1 day</span></span>| <span data-ttu-id="f815f-162">Wenn Sie das Ende des Prozesses erreicht haben, werden Sie geführt zu:</span><span class="sxs-lookup"><span data-stu-id="f815f-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="f815f-163">- Gehen Sie durch Die endgültige Ausgabe</span><span class="sxs-lookup"><span data-stu-id="f815f-163">- Go through your final output</span></span><br><span data-ttu-id="f815f-164">– Präsentieren Sie Ihre Ergebnisse ihren Beteiligten</span><span class="sxs-lookup"><span data-stu-id="f815f-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="f815f-165">- Feedback bereitstellen</span><span class="sxs-lookup"><span data-stu-id="f815f-165">- Provide feedback</span></span> <br><span data-ttu-id="f815f-166">– Ausführen der nächsten Schritte</span><span class="sxs-lookup"><span data-stu-id="f815f-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="f815f-167">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f815f-167">Next step</span></span>
|[<span data-ttu-id="f815f-168">Planungsphase</span><span class="sxs-lookup"><span data-stu-id="f815f-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="f815f-169">Planen Ihres Microsoft 365 Defender-Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="f815f-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
