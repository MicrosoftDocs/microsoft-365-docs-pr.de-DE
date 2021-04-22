---
title: Microsoft 365 Defender testen
description: Richten Sie Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung ein, um die Sicherheitslösung zum Schutz von Geräten, Identität, Daten und Anwendungen in Ihrer Organisation auszuprobieren und zu erleben.
keywords: Microsoft 365 Defender-Testversion, Testen von Microsoft 365 Defender, Evaluieren von Microsoft 365 Defender, Microsoft 365 Defender-Evaluierungslabor, Microsoft 365 Defender-Pilot, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Korrektur, erweiterte Suche
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933169"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="1a2fe-104">Erstellen einer Microsoft 365 Defender-Testumgebung oder Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="1a2fe-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1a2fe-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1a2fe-105">**Applies to:**</span></span>
- <span data-ttu-id="1a2fe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a2fe-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="1a2fe-107">Dieses Handbuch hilft Ihnen bei der Einrichtung einer Laborumgebung mit Benutzern und Gruppen und führt Sie dann durch die Konfiguration der Funktionen in Microsoft 365 Defender, damit Sie einen Bedrohungsangriff imitieren und ein aussagekräftiges Testergebnis erhalten können.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="1a2fe-108">Das Erstellen dieser Testumgebung oder Pilotumgebung dient dazu, die umfassenden und integrierten Microsoft 365 Defender-Funktionen zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="1a2fe-109">Erfahren Sie, wie diese intelligente Sicherheitslösung erweiterte Bedrohungen in Ihrer Organisation erkennt, verhindert, automatisch untersucht und reagiert.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="1a2fe-110">Sie werden durch die Schritte geführt, um Ihre Microsoft 365 Defender-Evaluierung basierend auf den empfohlenen Bereitstellungspfaden zu starten.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="1a2fe-111">Das Ziel besteht in der Einrichtung der Sicherheitslösung entweder in einer Laborumgebung mit einem Testkonto oder in einer Pilotumgebung in der Produktion mit volllizenz.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="1a2fe-112">Durch die Vorbereitung Ihrer Testumgebung oder Pilotumgebung können Sie Entscheidungsträgern in Ihrer Organisation Verwendungsfälle für Sicherheitsoperation präsentieren.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="1a2fe-113">Wenn Sie mit der Ausführung Ihrer Angriffssimulationen fertig sind und mit den Ergebnissen zufrieden sind, können Sie sie in Ihrer Organisation vollständig bereitstellen und mithilfe von Microsoft Technical Sales Professionals oder Experten in Ihrer Organisation operationalisieren.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="1a2fe-114">Dieses Handbuch hilft Ihnen dabei:</span><span class="sxs-lookup"><span data-stu-id="1a2fe-114">This guide will help you:</span></span>
- <span data-ttu-id="1a2fe-115">Einrichten des Laborservers und der Computer</span><span class="sxs-lookup"><span data-stu-id="1a2fe-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="1a2fe-116">Konfigurieren von Active Directory mit Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="1a2fe-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="1a2fe-117">Einrichten und Konfigurieren von Microsoft Defender for Identity, Microsoft Defender für Office 365, Microsoft Defender for Endpoint und Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1a2fe-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="1a2fe-118">Einrichten lokaler Richtlinien für Server und Computer</span><span class="sxs-lookup"><span data-stu-id="1a2fe-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="1a2fe-119">Imitieren eines Bedrohungsangriffs zum Generieren eines Testvorfalls oder einer Warnung in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a2fe-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="1a2fe-120">Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen zum Einrichten des Labors so genau wie möglich.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="1a2fe-121">Bereitstellungsphasen</span><span class="sxs-lookup"><span data-stu-id="1a2fe-121">Deployment phases</span></span>

<span data-ttu-id="1a2fe-122">Es gibt drei Phasen beim Erstellen einer Microsoft 365 Defender-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Bereitstellungsphasen: Vorbereiten, Einrichten, Onboarding](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="1a2fe-124">Phase</span><span class="sxs-lookup"><span data-stu-id="1a2fe-124">Phase</span></span> | <span data-ttu-id="1a2fe-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a2fe-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="1a2fe-126">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="1a2fe-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="1a2fe-127">Erfahren Sie, was Sie bei der Bereitstellung von Microsoft 365 Defender in einer Testumgebung oder Pilotumgebung berücksichtigen müssen:</span><span class="sxs-lookup"><span data-stu-id="1a2fe-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="1a2fe-128">– Beteiligte und Abmelden</span><span class="sxs-lookup"><span data-stu-id="1a2fe-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="1a2fe-129">– Überlegungen zur Umgebung</span><span class="sxs-lookup"><span data-stu-id="1a2fe-129">- Environment considerations</span></span> <br><span data-ttu-id="1a2fe-130">- Access</span><span class="sxs-lookup"><span data-stu-id="1a2fe-130">- Access</span></span> <br><span data-ttu-id="1a2fe-131">– Azure Active Directory-Setup</span><span class="sxs-lookup"><span data-stu-id="1a2fe-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="1a2fe-132">- Konfigurationsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="1a2fe-132">- Configuration order</span></span>
|[<span data-ttu-id="1a2fe-133">Phase 2: Setup</span><span class="sxs-lookup"><span data-stu-id="1a2fe-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="1a2fe-134">Gehen Sie zunächst auf Microsoft 365 Security Center zu, um Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung zu einrichten.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="1a2fe-135">Sie werden geführt zu:</span><span class="sxs-lookup"><span data-stu-id="1a2fe-135">You'll be guided to:</span></span><br><br><span data-ttu-id="1a2fe-136">- Registrieren für Microsoft 365 E5-Testversion</span><span class="sxs-lookup"><span data-stu-id="1a2fe-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="1a2fe-137">- Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="1a2fe-137">- Configure domain</span></span><br><span data-ttu-id="1a2fe-138">– Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="1a2fe-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="1a2fe-139">– Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="1a2fe-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="1a2fe-140">Phase 3: Konfigurieren & Onboard</span><span class="sxs-lookup"><span data-stu-id="1a2fe-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="1a2fe-141">Konfigurieren Sie die einzelnen Microsoft 365 Defender-Säulen und onboard-Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="1a2fe-142">Sie werden geführt zu:</span><span class="sxs-lookup"><span data-stu-id="1a2fe-142">You'll be guided to:</span></span><br><br><span data-ttu-id="1a2fe-143">- Konfigurieren von Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="1a2fe-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="1a2fe-144">- Konfigurieren von Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1a2fe-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="1a2fe-145">- Konfigurieren von Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="1a2fe-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="1a2fe-146">- Konfigurieren von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1a2fe-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="1a2fe-147">Nachdem Sie dieses Handbuch abgeschlossen haben, hätten Sie die beteiligten Beteiligten und die erforderlichen Genehmigungen identifiziert, über die richtigen Zugriffsberechtigungen verfügen, sich für die Testversion angemeldet, Domänen und die einzelnen Microsoft 365 Defender-Säulen konfiguriert, und Ihre Endpunkte werden in den Dienst eingebunden.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="1a2fe-148">Wichtige Funktionen</span><span class="sxs-lookup"><span data-stu-id="1a2fe-148">Key capabilities</span></span>

<span data-ttu-id="1a2fe-149">Obwohl Microsoft 365 Defender viele Funktionen bietet, besteht der Hauptzweck dieses Bereitstellungshandbuchs in der Einführung in das Onboarding von Geräten.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="1a2fe-150">Zusätzlich zum Onboarding werden Sie in diesem Leitfaden mit den folgenden Funktionen gestartet.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="1a2fe-151">Funktion</span><span class="sxs-lookup"><span data-stu-id="1a2fe-151">Capability</span></span> | <span data-ttu-id="1a2fe-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a2fe-152">Description</span></span> 
:---|:---
<span data-ttu-id="1a2fe-153">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="1a2fe-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="1a2fe-154">Schützt Ihre gesamte Office 365-Neid vor heutigen Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="1a2fe-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="1a2fe-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="1a2fe-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="1a2fe-156">Identifiziert und erkennt Bedrohungen für gefährdete Identitäten und böswillige Insideraktionen.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="1a2fe-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1a2fe-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="1a2fe-158">Bietet umfassende Sichtbarkeit, steuern Sie den Datenverkehr und erkennen Cyberangriffe über Clouddienste hinweg.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="1a2fe-159">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1a2fe-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="1a2fe-160">Verhindert, erkennt und stellt Reaktionsfunktionen für erweiterte Bedrohungen mit umfassender Endpunktsicherheit bereit.</span><span class="sxs-lookup"><span data-stu-id="1a2fe-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="1a2fe-161">Im Bereich</span><span class="sxs-lookup"><span data-stu-id="1a2fe-161">In scope</span></span>

<span data-ttu-id="1a2fe-162">Die folgenden Aufgaben sind für dieses Handbuch im Bereich:</span><span class="sxs-lookup"><span data-stu-id="1a2fe-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="1a2fe-163">Einrichten von Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1a2fe-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="1a2fe-164">Einrichten von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a2fe-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="1a2fe-165">Registrieren Sie sich für Microsoft 365 E5-Testversion, oder verwenden Sie Ihre Volllizenz, wenn Sie ein Pilotprojekt ausführen</span><span class="sxs-lookup"><span data-stu-id="1a2fe-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="1a2fe-166">Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="1a2fe-166">Configure domain</span></span>
    -   <span data-ttu-id="1a2fe-167">Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="1a2fe-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="1a2fe-168">Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="1a2fe-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="1a2fe-169">Konfigurieren aller Microsoft 365 Defender-Säulen basierend auf bewährten Methoden</span><span class="sxs-lookup"><span data-stu-id="1a2fe-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="1a2fe-170">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="1a2fe-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="1a2fe-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="1a2fe-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="1a2fe-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1a2fe-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="1a2fe-173">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1a2fe-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="1a2fe-174">Nicht inbegriffen</span><span class="sxs-lookup"><span data-stu-id="1a2fe-174">Out of scope</span></span>

<span data-ttu-id="1a2fe-175">Die folgenden Informationen sind nicht in diesem Bereitstellungshandbuch beschrieben:</span><span class="sxs-lookup"><span data-stu-id="1a2fe-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="1a2fe-176">Konfiguration von Drittanbieterlösungen, die in Microsoft 365 Defender integriert werden können</span><span class="sxs-lookup"><span data-stu-id="1a2fe-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="1a2fe-177">Penetrationstests in der Produktionsumgebung</span><span class="sxs-lookup"><span data-stu-id="1a2fe-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="1a2fe-178">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="1a2fe-178">Next step</span></span>
<span data-ttu-id="1a2fe-179">[Phase 1: Vorbereiten](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="1a2fe-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="1a2fe-180">Vorbereiten Ihrer Microsoft 365 Defender-Testumgebung oder Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="1a2fe-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
