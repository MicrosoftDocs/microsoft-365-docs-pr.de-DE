---
title: Ausführen des Pilotprojekts "Microsoft 365 Defender"
description: Führen Sie das Microsoft 365 Defender-Pilotprojekt in Production aus, um die Vorteile und die Akzeptanz von Microsoft 365 Defender effektiv zu ermitteln.
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
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: f01e918d35ce77d9239c200355c7b4c48c9e2b84
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659316"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="fbd4b-104">Ausführen des Pilotprojekts "Microsoft 365 Defender"</span><span class="sxs-lookup"><span data-stu-id="fbd4b-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fbd4b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fbd4b-105">**Applies to:**</span></span>
- <span data-ttu-id="fbd4b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbd4b-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="fbd4b-107">Dieses Handbuch unterstützt Sie bei der Ausführung eines Pilotprojekts durch Zeiger, um sicherzustellen, dass Sie über einen gut strukturierten Plan verfügen, der Sie durch die Verwendung der Funktion "Angriffssimulation" führen und schließlich das Pilotprojekt mit wichtigen Take-Aways zum reflektieren und Dokumentieren von Ergebnissen abschließen.</span><span class="sxs-lookup"><span data-stu-id="fbd4b-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Phasen bei der Ausführung eines Microsoft 365 Defender-Pilotprojekts](../../media/pilotphases.png)


<span data-ttu-id="fbd4b-109">Wenn Sie ein Pilotprojekt durchführen, können Sie den Vorteil der optieren von Microsoft 365 Defender effektiv ermitteln.</span><span class="sxs-lookup"><span data-stu-id="fbd4b-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="fbd4b-110">Bevor Sie Microsoft 365 Defender in Ihrer Produktionsumgebung aktivieren und ihre Anwendungsfälle starten, sollten Sie die für ihr Pilotprojekt zu erledigenden Aufgaben bestimmen und die Erfolgskriterien festlegen.</span><span class="sxs-lookup"><span data-stu-id="fbd4b-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="fbd4b-111">Vorgehensweise zum Verwenden dieses Pilot Manuskripts</span><span class="sxs-lookup"><span data-stu-id="fbd4b-111">How to use this pilot playbook</span></span>

<span data-ttu-id="fbd4b-112">Dieses Handbuch enthält eine Übersicht über Microsoft 365 Defender und Schritt-für-Schritt-Anleitungen zum Einrichten Ihres Pilotprojekts.</span><span class="sxs-lookup"><span data-stu-id="fbd4b-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="fbd4b-113">Microsoft 365 Defender ist eine einheitliche, vor-und nach Verletzung der Enterprise Defense-Suite, die den Schutz, die Erkennung, Verhinderung, Untersuchung und Antwort über alle Endpunkte, Identitäten, e-Mails und Anwendungen hinweg einheitlich koordiniert und einen integrierten Schutz vor anspruchsvollen Angriffen bietet.</span><span class="sxs-lookup"><span data-stu-id="fbd4b-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="fbd4b-114">Dies geschieht durch kombinieren und orchestrieren der folgenden Funktionen in einer einzigen Sicherheitslösung:</span><span class="sxs-lookup"><span data-stu-id="fbd4b-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="fbd4b-115">Microsoft Defender für Endpoint, der neue Name für Microsoft Defender Advanced Threat Protection (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="fbd4b-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="fbd4b-116">Microsoft Defender für Office 365, der neue Name für Office 365 ATP (e-Mail)</span><span class="sxs-lookup"><span data-stu-id="fbd4b-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="fbd4b-117">Microsoft Defender for Identity, der neue Name für Azure ATP (Identity)</span><span class="sxs-lookup"><span data-stu-id="fbd4b-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="fbd4b-118">Microsoft Cloud-App-Sicherheit (Apps)</span><span class="sxs-lookup"><span data-stu-id="fbd4b-118">Microsoft Cloud App Security (apps)</span></span>

![Image of_Microsoft 365 Defender-Lösung für Benutzer, Microsoft Defender for Identity, für Endpunkte von Microsoft Defender für Endpoint, für Cloud-apps, Microsoft Cloud-App-Sicherheit und für Daten, Microsoft Defender für Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="fbd4b-120">Mit der integrierten Microsoft 365 Defender-Lösung können Sicherheitsexperten die Bedrohungs Signale, die Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Defender for Identity und Microsoft Cloud App Security erhält, zusammenfügen und den vollständigen Umfang und die Auswirkungen der Bedrohung bestimmen, wie Sie in die Umgebung eingedrungen ist, welche Auswirkungen Sie hat und wie Sie sich derzeit auf die Organisation auswirkt.</span><span class="sxs-lookup"><span data-stu-id="fbd4b-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="fbd4b-121">Microsoft 365 Defender unternimmt automatische Aktionen zum verhindern oder Beenden des Angriffs und zur Selbstheilung betroffener Postfächer, Endpunkte und Benutzeridentitäten.</span><span class="sxs-lookup"><span data-stu-id="fbd4b-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="fbd4b-122">Ausführliche Informationen finden Sie in der [Microsoft 365 Defender-Übersicht](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) .</span><span class="sxs-lookup"><span data-stu-id="fbd4b-122">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>



<span data-ttu-id="fbd4b-123">Das folgende Beispiel Zeitachse variiert je nach den richtigen Ressourcen in Ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="fbd4b-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="fbd4b-124">Einige Erkennungen und Workflows benötigen möglicherweise mehr Lern Zeit als die anderen.</span><span class="sxs-lookup"><span data-stu-id="fbd4b-124">Some detections and workflows might need more learning time than the others.</span></span>

![Beispiel Zeitachse in Ausführung eines Microsoft 365 Defender-Pilotprojekts](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="fbd4b-126">Um optimale Ergebnisse zu erzielen, befolgen Sie die Pilot Anweisungen so genau wie möglich.</span><span class="sxs-lookup"><span data-stu-id="fbd4b-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="fbd4b-127">Phasen des Pilot Textbuch</span><span class="sxs-lookup"><span data-stu-id="fbd4b-127">Pilot playbook phases</span></span> 

<span data-ttu-id="fbd4b-128">Bei der Ausführung eines Microsoft 365 Defender-Pilotprojekts gibt es vier Phasen:</span><span class="sxs-lookup"><span data-stu-id="fbd4b-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="fbd4b-129">Phase</span><span class="sxs-lookup"><span data-stu-id="fbd4b-129">Phase</span></span> | <span data-ttu-id="fbd4b-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbd4b-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="fbd4b-131">Planung</span><span class="sxs-lookup"><span data-stu-id="fbd4b-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="fbd4b-132">~ 1 Tag</span><span class="sxs-lookup"><span data-stu-id="fbd4b-132">~ 1 day</span></span>| <span data-ttu-id="fbd4b-133">Hier erfahren Sie, was Sie vor der Ausführung Ihres Microsoft 365 Defender-Pilotprojekts besprechen sollten:</span><span class="sxs-lookup"><span data-stu-id="fbd4b-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="fbd4b-134">-Scope</span><span class="sxs-lookup"><span data-stu-id="fbd4b-134">- Scope</span></span> <br> <span data-ttu-id="fbd4b-135">-Anwendungsfälle</span><span class="sxs-lookup"><span data-stu-id="fbd4b-135">- Use cases</span></span> <br><span data-ttu-id="fbd4b-136">– Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fbd4b-136">- Requirements</span></span> <br><span data-ttu-id="fbd4b-137">-Testplan</span><span class="sxs-lookup"><span data-stu-id="fbd4b-137">- Test plan</span></span> <br> <span data-ttu-id="fbd4b-138">-Erfolgskriterien</span><span class="sxs-lookup"><span data-stu-id="fbd4b-138">- Success criteria</span></span> <br> <span data-ttu-id="fbd4b-139">-Scorecard</span><span class="sxs-lookup"><span data-stu-id="fbd4b-139">- Scorecard</span></span> 
| [<span data-ttu-id="fbd4b-140">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="fbd4b-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="fbd4b-141">~ 2 Tage</span><span class="sxs-lookup"><span data-stu-id="fbd4b-141">~2 days</span></span>|  <span data-ttu-id="fbd4b-142">Greifen Sie auf das Microsoft 365 Security Center zu, um Ihre Microsoft 365 Defender-Pilotumgebung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="fbd4b-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="fbd4b-143">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="fbd4b-143">You'll be guided to:</span></span><br><br><span data-ttu-id="fbd4b-144">-Identifizieren von Beteiligten und suchen der Anmeldung für ihr Pilotprojekt</span><span class="sxs-lookup"><span data-stu-id="fbd4b-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="fbd4b-145">-Umgebungs Überlegungen</span><span class="sxs-lookup"><span data-stu-id="fbd4b-145">- Environment considerations</span></span> <br><span data-ttu-id="fbd4b-146">-Access</span><span class="sxs-lookup"><span data-stu-id="fbd4b-146">- Access</span></span> <br><span data-ttu-id="fbd4b-147">-Azure-Active Directory-Setup</span><span class="sxs-lookup"><span data-stu-id="fbd4b-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="fbd4b-148">-Konfigurations Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="fbd4b-148">- Configuration order</span></span> <br> <span data-ttu-id="fbd4b-149">-Registrieren für Microsoft 365 E5-Testversion</span><span class="sxs-lookup"><span data-stu-id="fbd4b-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="fbd4b-150">-Domäne konfigurieren</span><span class="sxs-lookup"><span data-stu-id="fbd4b-150">- Configure domain</span></span> <br><span data-ttu-id="fbd4b-151">-Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="fbd4b-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="fbd4b-152">-Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="fbd4b-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="fbd4b-153">Angriffssimulation</span><span class="sxs-lookup"><span data-stu-id="fbd4b-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="fbd4b-154">~ 2 Tage</span><span class="sxs-lookup"><span data-stu-id="fbd4b-154">~2 days</span></span>| <span data-ttu-id="fbd4b-155">Um einen Angriff zu simulieren, werden Sie zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="fbd4b-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="fbd4b-156">-Überprüfen der Anforderungen an die Testumgebung</span><span class="sxs-lookup"><span data-stu-id="fbd4b-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="fbd4b-157">-Simulation ausführen</span><span class="sxs-lookup"><span data-stu-id="fbd4b-157">-  Run the simulation</span></span> <br><span data-ttu-id="fbd4b-158">-Untersuchen eines Vorfalls</span><span class="sxs-lookup"><span data-stu-id="fbd4b-158">- Investigate an incident</span></span> <br><span data-ttu-id="fbd4b-159">-Beheben des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="fbd4b-159">- resolve the incident</span></span> 
| [<span data-ttu-id="fbd4b-160">Schließen und Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="fbd4b-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="fbd4b-161">~ 1 Tag</span><span class="sxs-lookup"><span data-stu-id="fbd4b-161">~ 1 day</span></span>| <span data-ttu-id="fbd4b-162">Wenn Sie das Ende des Prozesses erreicht haben, werden Sie zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="fbd4b-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="fbd4b-163">– Durchlaufen der endgültigen Ausgabe</span><span class="sxs-lookup"><span data-stu-id="fbd4b-163">- Go through your final output</span></span><br><span data-ttu-id="fbd4b-164">-Präsentieren ihrer Ausgaben für Ihre Stakeholder</span><span class="sxs-lookup"><span data-stu-id="fbd4b-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="fbd4b-165">-Feedback geben</span><span class="sxs-lookup"><span data-stu-id="fbd4b-165">- Provide feedback</span></span> <br><span data-ttu-id="fbd4b-166">– Nächste Schritte ausführen</span><span class="sxs-lookup"><span data-stu-id="fbd4b-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="fbd4b-167">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="fbd4b-167">Next step</span></span>
|[<span data-ttu-id="fbd4b-168">Planungsphase</span><span class="sxs-lookup"><span data-stu-id="fbd4b-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="fbd4b-169">Planen des Pilotprojekts für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbd4b-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
