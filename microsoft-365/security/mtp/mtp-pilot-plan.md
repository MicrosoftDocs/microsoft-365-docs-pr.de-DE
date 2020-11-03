---
title: Planen des Pilotprojekts "Microsoft 365 Defender"
description: Planen Sie Ihr Pilotprojekt "Microsoft 365 Defender" mit Beteiligten, um die Erwartungen zu verwalten und ein erfolgreiches Ergebnis sicherzustellen.
keywords: Microsoft Threat Protection Pilotprojekt, Plan Pilot Microsoft Threat Protection Project, bewerten von Microsoft Threat Protection in der Produktion, Microsoft Threat Protection Pilotprojekt, Cyber Security, Advanced persistent Threat, Enterprise Security, Devices, Device, Identity, users, Data, Applications, Incidents, Automated Investigation and Remediation, Advanced Hunting
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: ec2bfe52308231577e4f2749e1f4cdf24a36f604
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846020"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="84c45-104">Planen des Pilotprojekts "Microsoft 365 Defender"</span><span class="sxs-lookup"><span data-stu-id="84c45-104">Planning your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="84c45-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="84c45-105">**Applies to:**</span></span>
- <span data-ttu-id="84c45-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84c45-106">Microsoft 365 Defender</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft 365 Defender project" title="Planen des Pilotprojekts "Microsoft 365 Defender"" />
      <br/><span data-ttu-id="84c45-108">Plan</a></span><span class="sxs-lookup"><span data-stu-id="84c45-108">Plan</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Vorbereiten des Testlabors oder der Pilotumgebung für den Microsoft 365 Defender" />
      <br/><span data-ttu-id="84c45-110">Vorbereiten</a></span><span class="sxs-lookup"><span data-stu-id="84c45-110">Prepare</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft 365 Defender attack simulations" title="Ausführen Ihrer Microsoft 365 Defender-Angriffssimulationen" />
     <br/><span data-ttu-id="84c45-112">Angriff simulieren</a></span><span class="sxs-lookup"><span data-stu-id="84c45-112">Simulate attack</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft 365 Defender pilot" title="Schließen Sie Ihr Microsoft 365 Defender-Pilotprojekt, und fassen Sie es zusammen" />
     <br/><span data-ttu-id="84c45-114">Schließen und zusammenfassen</a></span><span class="sxs-lookup"><span data-stu-id="84c45-114">Close and summarize</a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="84c45-115">Sie befinden sich derzeit in der Planungsphase.</span><span class="sxs-lookup"><span data-stu-id="84c45-115">You're currently in the planning phase.</span></span>

<span data-ttu-id="84c45-116">Um sicherzustellen, dass das Pilotprojekt erfolgreich verläuft, ist es wichtig, dass Sie die Genehmigungen ihrer Beteiligten am Anfang sorgfältig planen und erhalten.</span><span class="sxs-lookup"><span data-stu-id="84c45-116">To ensure that your pilot project is a success, it is essential to plan thoroughly with and get approvals from your stakeholders in the beginning.</span></span> <span data-ttu-id="84c45-117">Zu den Planungselementen gehören das Identifizieren von Umfang, Anwendungsfällen, Anforderungen und Erfolgskriterien.</span><span class="sxs-lookup"><span data-stu-id="84c45-117">Elements of planning include identifying scope, use cases, requirements, and success criteria.</span></span>

<span data-ttu-id="84c45-118">In diesem Leitfaden wird erläutert, wie Sie Ihr Pilotprojekt planen.</span><span class="sxs-lookup"><span data-stu-id="84c45-118">This guide walks you through how to plan your pilot project.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="84c45-119">Um optimale Ergebnisse zu erzielen, befolgen Sie die Pilot Anweisungen so genau wie möglich.</span><span class="sxs-lookup"><span data-stu-id="84c45-119">For optimum results, follow the pilot instructions as closely as possible.</span></span>


## <a name="scope"></a><span data-ttu-id="84c45-120">Bereich</span><span class="sxs-lookup"><span data-stu-id="84c45-120">Scope</span></span>

<span data-ttu-id="84c45-121">Der Bereich des Pilotprojekts bestimmt, wie breit der Test ist, basierend auf Ihrer Umgebung und den zulässigen Testmethoden.</span><span class="sxs-lookup"><span data-stu-id="84c45-121">The scope of the pilot will determine how broad the test will be, based on your environment and acceptable testing methods.</span></span> <span data-ttu-id="84c45-122">Hier sind einige Beispiel Bereiche, die zu prüfen sind:</span><span class="sxs-lookup"><span data-stu-id="84c45-122">Here are some example scopes to consider:</span></span>
- <span data-ttu-id="84c45-123">Entwicklungs-oder Testumgebung mit Endpunkten, Servern, Domänencontrollern.</span><span class="sxs-lookup"><span data-stu-id="84c45-123">Development or test environment which includes endpoints, servers, domain controllers.</span></span>
- <span data-ttu-id="84c45-124">Produktionsumgebung mit Microsoft 365, Azure, Active Directory Diensten, Endpunkten und Servern</span><span class="sxs-lookup"><span data-stu-id="84c45-124">Production environment with Microsoft 365, Azure, Active Directory services, endpoints, and servers</span></span>

>[!NOTE]
><span data-ttu-id="84c45-125">Wenn Sie noch nicht über die vollständigen Lizenzen verfügen, können Sie Testlizenzen zur [Evaluierung von Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) erhalten – planen, vorbereiten, einrichten, konfigurieren und Ausführen des Pilotprojekts.</span><span class="sxs-lookup"><span data-stu-id="84c45-125">If you don’t have the full licenses yet, you can get trial licenses to [evaluate Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) – plan, prepare, setup, configure, and run your pilot project.</span></span> <span data-ttu-id="84c45-126">Ihre Beteiligten werden eine wichtige Rolle dabei spielen, den Prozess von Anfang bis Ende zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="84c45-126">Your stakeholders will play a big role in helping facilitate the process from start to finish.</span></span>

<span data-ttu-id="84c45-127">Die Typen der auszuwertenden Betriebssysteme sollten auch basierend auf der organisatorischen Verfassung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="84c45-127">The types of operating systems to be evaluated should also be defined based on the organizational makeup.</span></span> <span data-ttu-id="84c45-128">Dies kann Folgendes umfassen: [Mac-Endpunkte](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux-Server](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10-Endpunkte](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span><span class="sxs-lookup"><span data-stu-id="84c45-128">This may include the following: [Mac endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux Servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span></span>

## <a name="use-cases"></a><span data-ttu-id="84c45-129">Anwendungsfälle</span><span class="sxs-lookup"><span data-stu-id="84c45-129">Use cases</span></span>

<span data-ttu-id="84c45-130">Anwendungsfälle stellen Anweisungen dar, wie das zu testende Tool von den vorgesehenen Benutzern verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="84c45-130">Use cases represent statements of how the tool being tested is meant to be consumed by its intended users.</span></span> <span data-ttu-id="84c45-131">Diese können als Benutzergeschichten aus der Sicht einer bestimmten Person formuliert werden, beispielsweise als SOC-Analyst.</span><span class="sxs-lookup"><span data-stu-id="84c45-131">These can be formulated as user stories from the point of view of a particular persona, such as a SOC analyst.</span></span> <span data-ttu-id="84c45-132">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="84c45-132">For example:</span></span>
- <span data-ttu-id="84c45-133">Als SOC-Analyst muss ich Warnungen und Ereignisse für Geräte, Benutzer und Postfächer in meinem Netzwerk anzeigen, korrelieren, bewerten und verwalten.</span><span class="sxs-lookup"><span data-stu-id="84c45-133">As a SOC analyst, I need to view, correlate, assess and manage alerts and events across devices, users, and mailboxes in my network.</span></span> <span data-ttu-id="84c45-134">[Vorfallverwaltung]</span><span class="sxs-lookup"><span data-stu-id="84c45-134">[Incident management]</span></span>
- <span data-ttu-id="84c45-135">Als SOC-Analyst muss ich das Tool und den Prozess zum automatischen untersuchen und reagieren auf böswillige Ereignisse in meinem Netzwerk haben.</span><span class="sxs-lookup"><span data-stu-id="84c45-135">As a SOC analyst, I must have the tool and process to automatically investigate and respond to malicious events in my network.</span></span> <span data-ttu-id="84c45-136">[Auto IR]</span><span class="sxs-lookup"><span data-stu-id="84c45-136">[Auto IR]</span></span>
- <span data-ttu-id="84c45-137">Als SOC-Analyst muss ich Daten aus meiner Umgebung suchen, um bekannte und potenzielle Bedrohungen sowie verdächtige Aktivitäten zu finden.</span><span class="sxs-lookup"><span data-stu-id="84c45-137">As a SOC analyst, I must search data from my environment to find known and potential threats, and suspicious activities.</span></span> <span data-ttu-id="84c45-138">[Erweiterte Suche]</span><span class="sxs-lookup"><span data-stu-id="84c45-138">[Advanced Hunting]</span></span>

<span data-ttu-id="84c45-139">Beachten Sie, dass diese Anwendungsfälle innerhalb der Parameter des definierten Bereichs erstellt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="84c45-139">Keep in mind that these use cases should be created within the parameters of the defined scope.</span></span> <span data-ttu-id="84c45-140">Wenn beispielsweise der Testumfang keine Evaluierung von Tools wie Microsoft Cloud App Security umfasst, sollten Anwendungsfälle, die sich auf diese als Datenquelle stützen, nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="84c45-140">If, for example, the scope of testing does not include an evaluation of tools such as Microsoft Cloud App Security, then use cases that rely on this as a data source should not be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="84c45-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84c45-141">Requirements</span></span>

<span data-ttu-id="84c45-142">In der Liste der Anwendungsfälle können Sie mit dem Erstellen von Anforderungen beginnen.</span><span class="sxs-lookup"><span data-stu-id="84c45-142">From the list of use cases, you can start to create requirements.</span></span> <span data-ttu-id="84c45-143">Anforderungen umfassen Features, die ein Tool zum erfüllen der Anwendungsfälle benötigen muss.</span><span class="sxs-lookup"><span data-stu-id="84c45-143">Requirements include features a tool must have to satisfy the use cases.</span></span> <span data-ttu-id="84c45-144">Diese Anforderungen können in Kategorien wie Konfiguration und Wartung, Unterstützung für Integrationen und funktionsspezifische Anforderungen wie die Jagd Fähigkeit und die Möglichkeit zum Erstellen von benutzerdefinierten Warnungen aufgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="84c45-144">These requirements can be broken down into categories such as configuration and maintenance, support for integrations, and feature-specific requirements like hunting ability and the ability to build custom alerts.</span></span>

## <a name="test-plan"></a><span data-ttu-id="84c45-145">Testplan</span><span class="sxs-lookup"><span data-stu-id="84c45-145">Test plan</span></span>

<span data-ttu-id="84c45-146">Je nach Anforderungen können unterschiedliche Testmethoden geeignet sein.</span><span class="sxs-lookup"><span data-stu-id="84c45-146">Depending on the requirements, different methods of testing may be appropriate.</span></span> <span data-ttu-id="84c45-147">Wenn beispielsweise die Effizienz der automatischen Behebung bewertet werden soll, muss der Testplan Schritte zum Generieren des Verhaltens (s) enthalten, das eine automatisierte Korrekturaktion in Microsoft 365 Defender auslösen würde.</span><span class="sxs-lookup"><span data-stu-id="84c45-147">For instance, if the requirement is to evaluate the efficacy of Automated Remediation, the test plan needs to include steps to generate the behavior(s) that would trigger an automated remediation action within Microsoft 365 Defender.</span></span> <span data-ttu-id="84c45-148">Wenn die Anforderung ein bestimmtes Verhalten oder einen Angriff erkennen soll, kann der Test weitere Schritte beinhalten.</span><span class="sxs-lookup"><span data-stu-id="84c45-148">If the requirement is to detect a particular behavior or attack, then the test may involve more steps.</span></span> <span data-ttu-id="84c45-149">Der Punkt besteht darin, dass ein Plan vorhanden ist, mit dem die Anforderungen genau getestet werden.</span><span class="sxs-lookup"><span data-stu-id="84c45-149">The point is to have a plan in place to accurately test against your requirements.</span></span>

## <a name="success-criteria"></a><span data-ttu-id="84c45-150">Erfolgskriterien</span><span class="sxs-lookup"><span data-stu-id="84c45-150">Success criteria</span></span>

<span data-ttu-id="84c45-151">Die Erfolgskriterien sind letztendlich das balkenset, das anhand des Tests gemessen wird.</span><span class="sxs-lookup"><span data-stu-id="84c45-151">Success criteria is ultimately the bar set to measure against what you are testing.</span></span> <span data-ttu-id="84c45-152">Unabhängig davon, ob Sie Microsoft 365 Defender (oder eine andere Technologie für diese Angelegenheit) für andere Tools oder für sich selbst testen, muss es einige quantifizierbare Kriterien geben, um den vom Tool bereitgestellten Wert zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="84c45-152">Whether you are testing Microsoft 365 Defender (or any other technology for that matter) against other tools or by itself, there must be some quantifiable criteria to determine the value the tool provides.</span></span> <span data-ttu-id="84c45-153">Basierend auf dem Umfang, den Anforderungen und dem Testplan bestimmen die Erfolgskriterien, wie der Test bewertet wird.</span><span class="sxs-lookup"><span data-stu-id="84c45-153">Based on the scope, requirements, and testing plan, the success criteria will determine how to score the test.</span></span> <span data-ttu-id="84c45-154">Dies sollte ein geringerer Pass oder ein fehlgeschlagener oder ein größerer Teil eines gewichteten Scorings sein, das auf Ihren Anforderungen basiert.</span><span class="sxs-lookup"><span data-stu-id="84c45-154">This should be less of a pass or fail and more of a weighted scoring based on your needs.</span></span> <span data-ttu-id="84c45-155">Um beispielsweise erfolgreich zu sein, muss ein Tool möglicherweise in bestimmten von Ihnen identifizierten kritischen Bereichen über 80% Punkten.</span><span class="sxs-lookup"><span data-stu-id="84c45-155">For example, to be successful, a tool may need to score above 80% in certain critical areas you identify.</span></span>

## <a name="scorecard"></a><span data-ttu-id="84c45-156">Scorecard</span><span class="sxs-lookup"><span data-stu-id="84c45-156">Scorecard</span></span>

<span data-ttu-id="84c45-157">Eine Möglichkeit, alle Elemente Ihres Plans zusammenzuführen, kann das Erstellen einer Scorecard sein.</span><span class="sxs-lookup"><span data-stu-id="84c45-157">One way to bring all elements of your plan together can be to create a scorecard.</span></span> <span data-ttu-id="84c45-158">Eine Beispiel-Scorecard finden Sie weiter unten:</span><span class="sxs-lookup"><span data-stu-id="84c45-158">See a sample scorecard below:</span></span>

| <span data-ttu-id="84c45-159">Anwendungsfall</span><span class="sxs-lookup"><span data-stu-id="84c45-159">Use case</span></span> | <span data-ttu-id="84c45-160">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84c45-160">Requirements</span></span> | <span data-ttu-id="84c45-161">Konfigurationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="84c45-161">Configuration requirements</span></span> | <span data-ttu-id="84c45-162">Testplan</span><span class="sxs-lookup"><span data-stu-id="84c45-162">Test plan</span></span> | <span data-ttu-id="84c45-163">Erwartetes Ergebnis</span><span class="sxs-lookup"><span data-stu-id="84c45-163">Expected outcome</span></span> | <span data-ttu-id="84c45-164">Test Status</span><span class="sxs-lookup"><span data-stu-id="84c45-164">Test status</span></span> | <span data-ttu-id="84c45-165">Bewertung</span><span class="sxs-lookup"><span data-stu-id="84c45-165">Score</span></span> | <span data-ttu-id="84c45-166">Notes</span><span class="sxs-lookup"><span data-stu-id="84c45-166">Notes</span></span> |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|<span data-ttu-id="84c45-167">Vorfallverwaltung</span><span class="sxs-lookup"><span data-stu-id="84c45-167">Incident management</span></span>|<span data-ttu-id="84c45-168">-Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84c45-168">-  Microsoft 365 Defender</span></span>  </br></br><span data-ttu-id="84c45-169">-Microsoft Defender für Identity</span><span class="sxs-lookup"><span data-stu-id="84c45-169">- Microsoft Defender for Identity</span></span> </br></br><span data-ttu-id="84c45-170">-Microsoft Defender für Endpoint</span><span class="sxs-lookup"><span data-stu-id="84c45-170">- Microsoft Defender for Endpoint</span></span> </br></br><span data-ttu-id="84c45-171">-Microsoft Cloud-App-Sicherheit (optional)</span><span class="sxs-lookup"><span data-stu-id="84c45-171">- Microsoft Cloud App Security (optional)</span></span>|<span data-ttu-id="84c45-172">Weitere Informationen finden Sie unter [Voraussetzungen](https://aka.ms/mtp-trial-lab) für Vorbereitung, Einrichtung und Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="84c45-172">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> |[<span data-ttu-id="84c45-173">Angriff simulieren</span><span class="sxs-lookup"><span data-stu-id="84c45-173">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="84c45-174">Untersuchen des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="84c45-174">Investigate the incident</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |<span data-ttu-id="84c45-175">Ermittler können den Umfang und die Auswirkungen des Vorfalls verstehen und den Vorfall verwalten.</span><span class="sxs-lookup"><span data-stu-id="84c45-175">Investigators can understand the scope and impact of the incident and manage the incident</span></span>||||
|<span data-ttu-id="84c45-176">AutoIR</span><span class="sxs-lookup"><span data-stu-id="84c45-176">AutoIR</span></span>|<span data-ttu-id="84c45-177">-Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84c45-177">-   Microsoft 365 Defender</span></span> </br></br><span data-ttu-id="84c45-178">-Microsoft Defender für Identity</span><span class="sxs-lookup"><span data-stu-id="84c45-178">- Microsoft Defender for Identity</span></span> </br></br><span data-ttu-id="84c45-179">-Microsoft Defender für Endpoint</span><span class="sxs-lookup"><span data-stu-id="84c45-179">- Microsoft Defender for Endpoint</span></span> |<span data-ttu-id="84c45-180">Weitere Informationen finden Sie unter [Voraussetzungen](https://aka.ms/mtp-trial-lab) für Vorbereitung, Einrichtung und Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="84c45-180">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> <br><span data-ttu-id="84c45-181">AutoIR aktivieren</span><span class="sxs-lookup"><span data-stu-id="84c45-181">Enable AutoIR</span></span>  |[<span data-ttu-id="84c45-182">Angriff simulieren</span><span class="sxs-lookup"><span data-stu-id="84c45-182">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="84c45-183">Automatische Untersuchung</span><span class="sxs-lookup"><span data-stu-id="84c45-183">Automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |<span data-ttu-id="84c45-184">Warnungen und Vorfälle werden automatisch von Microsoft 365 Defender behoben.</span><span class="sxs-lookup"><span data-stu-id="84c45-184">Alerts and incidents are automatically remediated by Microsoft 365 Defender</span></span>||||
|<span data-ttu-id="84c45-185">Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="84c45-185">Advanced hunting</span></span>|<span data-ttu-id="84c45-186">-Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84c45-186">- Microsoft 365 Defender</span></span> </br></br><span data-ttu-id="84c45-187">-Microsoft Defender für Endpoint</span><span class="sxs-lookup"><span data-stu-id="84c45-187">- Microsoft Defender for Endpoint</span></span> </br></br><span data-ttu-id="84c45-188">-Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="84c45-188">-Microsoft Defender for Office 365</span></span> |<span data-ttu-id="84c45-189">Weitere Informationen finden Sie unter [Voraussetzungen](https://aka.ms/mtp-trial-lab) für Vorbereitung, Einrichtung und Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="84c45-189">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span>|[<span data-ttu-id="84c45-190">Erweitertes Jagd Szenario</span><span class="sxs-lookup"><span data-stu-id="84c45-190">Advanced hunting scenario</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |<span data-ttu-id="84c45-191">Ermittler können Daten über erweitertes suchen, pivotieren für betroffene Entitäten und durch Erstellen von benutzerdefinierten Erkennungen finden.</span><span class="sxs-lookup"><span data-stu-id="84c45-191">Investigators can find data through advanced hunting, pivoting to impacted entities, and by creating custom detections</span></span>||||



## <a name="next-step"></a><span data-ttu-id="84c45-192">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="84c45-192">Next step</span></span>
|<span data-ttu-id="84c45-193">![Vorbereitungsphase](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="84c45-193">![Preparation phase](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="84c45-194">Vorbereitungsphase</span><span class="sxs-lookup"><span data-stu-id="84c45-194">Preparation phase</span></span>](prepare-mtpeval.md) | <span data-ttu-id="84c45-195">Vorbereiten der Pilotumgebung für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84c45-195">Prepare your Microsoft 365 Defender pilot environment</span></span>
|:-------|:-----|
