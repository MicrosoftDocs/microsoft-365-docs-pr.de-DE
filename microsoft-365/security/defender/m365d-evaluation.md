---
title: Microsoft 365 Defender testen
description: Richten Sie ihre Microsoft 365 Testumgebung oder Pilotumgebung für Defender ein, um die Sicherheitslösung zum Schutz von Geräten, Identitäten, Daten und Anwendungen in Ihrer Organisation auszuprobieren und zu erleben.
keywords: Microsoft 365 Defender Trial, try Microsoft 365 Defender, evaluate Microsoft 365 Defender, Microsoft 365 Defender evaluation lab, Microsoft 365 Defender pilot, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="73973-104">Erstellen einer Microsoft 365 Testumgebung oder Pilotumgebung für Defender</span><span class="sxs-lookup"><span data-stu-id="73973-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="73973-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="73973-105">**Applies to:**</span></span>
- <span data-ttu-id="73973-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73973-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="73973-107">Dieses Handbuch hilft Ihnen bei der Einrichtung einer Laborumgebung mit Benutzern und Gruppen und führt Sie dann durch die Konfiguration der Funktionen in Microsoft 365 Defender, damit Sie einen Bedrohungsangriff imitieren und ein aussagekräftiges Testergebnis erzielen können.</span><span class="sxs-lookup"><span data-stu-id="73973-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="73973-108">Der Zweck der Erstellung dieser Testumgebung oder Pilotumgebung besteht in der Veranschaulichen der umfassenden und integrierten Microsoft 365 Defender-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="73973-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="73973-109">Erfahren Sie, wie diese intelligente Sicherheitslösung erweiterte Bedrohungen in Ihrer Organisation erkennt, verhindert, automatisch untersucht und reagiert.</span><span class="sxs-lookup"><span data-stu-id="73973-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="73973-110">Sie werden anhand der empfohlenen Bereitstellungspfade durch die Schritte geführt, um Microsoft 365 Defender-Evaluierung zu starten.</span><span class="sxs-lookup"><span data-stu-id="73973-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="73973-111">Das Ziel besteht in der Einrichtung der Sicherheitslösung entweder in einer Laborumgebung mit einem Testkonto oder in einer Pilotumgebung in der Produktion mit volllizenz.</span><span class="sxs-lookup"><span data-stu-id="73973-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="73973-112">Durch die Vorbereitung Ihrer Testumgebung oder Pilotumgebung können Sie Entscheidungsträgern in Ihrer Organisation Verwendungsfälle für Sicherheitsoperation präsentieren.</span><span class="sxs-lookup"><span data-stu-id="73973-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="73973-113">Wenn Sie mit der Ausführung Ihrer Angriffssimulationen fertig sind und mit den Ergebnissen zufrieden sind, können Sie sie in Ihrer Organisation vollständig bereitstellen und mithilfe von Microsoft Technical Sales Professionals oder Experten in Ihrer Organisation operationalisieren.</span><span class="sxs-lookup"><span data-stu-id="73973-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="73973-114">Dieses Handbuch hilft Ihnen dabei:</span><span class="sxs-lookup"><span data-stu-id="73973-114">This guide will help you:</span></span>
- <span data-ttu-id="73973-115">Einrichten des Laborservers und der Computer</span><span class="sxs-lookup"><span data-stu-id="73973-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="73973-116">Konfigurieren von Active Directory mit Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="73973-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="73973-117">Einrichten und Konfigurieren von Microsoft Defender for Identity, Microsoft Defender für Office 365, Microsoft Defender für Endpoint und Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="73973-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="73973-118">Einrichten lokaler Richtlinien für Server und Computer</span><span class="sxs-lookup"><span data-stu-id="73973-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="73973-119">Imitieren eines Bedrohungsangriffs zum Generieren eines Testvorfalls oder einer Warnung in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73973-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="73973-120">Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen zum Einrichten des Labors so genau wie möglich.</span><span class="sxs-lookup"><span data-stu-id="73973-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="73973-121">Bereitstellungsphasen</span><span class="sxs-lookup"><span data-stu-id="73973-121">Deployment phases</span></span>

<span data-ttu-id="73973-122">Es gibt drei Phasen beim Erstellen einer Microsoft 365 Defender-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="73973-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Bereitstellungsphasen: Vorbereiten, Einrichten, Onboarding](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="73973-124">Phase</span><span class="sxs-lookup"><span data-stu-id="73973-124">Phase</span></span> | <span data-ttu-id="73973-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="73973-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="73973-126">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="73973-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="73973-127">Erfahren Sie, was Sie bei der Bereitstellung Microsoft 365 Defender in einer Testumgebung oder Pilotumgebung berücksichtigen müssen:</span><span class="sxs-lookup"><span data-stu-id="73973-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="73973-128">– Beteiligte und Abmelden</span><span class="sxs-lookup"><span data-stu-id="73973-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="73973-129">– Überlegungen zur Umgebung</span><span class="sxs-lookup"><span data-stu-id="73973-129">- Environment considerations</span></span> <br><span data-ttu-id="73973-130">- Access</span><span class="sxs-lookup"><span data-stu-id="73973-130">- Access</span></span> <br><span data-ttu-id="73973-131">- Azure Active Directory Setup</span><span class="sxs-lookup"><span data-stu-id="73973-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="73973-132">- Konfigurationsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="73973-132">- Configuration order</span></span>
|[<span data-ttu-id="73973-133">Phase 2: Setup</span><span class="sxs-lookup"><span data-stu-id="73973-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="73973-134">Ergreifen Sie die ersten Schritte, um auf Microsoft 365 Security Center zu zugreifen, um Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung zu einrichten.</span><span class="sxs-lookup"><span data-stu-id="73973-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="73973-135">Sie werden geführt zu:</span><span class="sxs-lookup"><span data-stu-id="73973-135">You'll be guided to:</span></span><br><br><span data-ttu-id="73973-136">– Registrieren für Microsoft 365 E5 Testversion</span><span class="sxs-lookup"><span data-stu-id="73973-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="73973-137">- Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="73973-137">- Configure domain</span></span><br><span data-ttu-id="73973-138">- Zuweisen Microsoft 365 E5 Lizenzen</span><span class="sxs-lookup"><span data-stu-id="73973-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="73973-139">– Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="73973-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="73973-140">Phase 3: Konfigurieren & Onboard</span><span class="sxs-lookup"><span data-stu-id="73973-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="73973-141">Konfigurieren Sie Microsoft 365 Defender-Säule und onboard-Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="73973-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="73973-142">Sie werden geführt zu:</span><span class="sxs-lookup"><span data-stu-id="73973-142">You'll be guided to:</span></span><br><br><span data-ttu-id="73973-143">- Konfigurieren von Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="73973-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="73973-144">- Konfigurieren Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="73973-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="73973-145">- Konfigurieren von Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="73973-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="73973-146">- Konfigurieren von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="73973-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="73973-147">Nachdem Sie dieses Handbuch abgeschlossen haben, hätten Sie die beteiligten Beteiligten und die erforderlichen Genehmigungen identifiziert, über die richtigen Zugriffsberechtigungen verfügen, sich für Testversionen registrieren, Domänen und jede der Microsoft 365 Defender-Säulen konfiguriert, und Ihre Endpunkte werden in den Dienst eingebunden.</span><span class="sxs-lookup"><span data-stu-id="73973-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="73973-148">Wichtige Funktionen</span><span class="sxs-lookup"><span data-stu-id="73973-148">Key capabilities</span></span>

<span data-ttu-id="73973-149">Während Microsoft 365 Defender viele Funktionen bietet, besteht der Hauptzweck dieses Bereitstellungshandbuchs in der Einführung in das Onboarding von Geräten.</span><span class="sxs-lookup"><span data-stu-id="73973-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="73973-150">Zusätzlich zum Onboarding werden Sie in diesem Leitfaden mit den folgenden Funktionen gestartet.</span><span class="sxs-lookup"><span data-stu-id="73973-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="73973-151">Funktion</span><span class="sxs-lookup"><span data-stu-id="73973-151">Capability</span></span> | <span data-ttu-id="73973-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="73973-152">Description</span></span> 
:---|:---
<span data-ttu-id="73973-153">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="73973-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="73973-154">Schützt Ihre gesamte Office 365 vor heutigen Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="73973-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="73973-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="73973-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="73973-156">Identifiziert und erkennt Bedrohungen für gefährdete Identitäten und böswillige Insideraktionen.</span><span class="sxs-lookup"><span data-stu-id="73973-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="73973-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="73973-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="73973-158">Bietet umfassende Sichtbarkeit, steuern Sie den Datenverkehr und erkennen Cyberangriffe über Clouddienste hinweg.</span><span class="sxs-lookup"><span data-stu-id="73973-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="73973-159">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="73973-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="73973-160">Verhindert, erkennt und stellt Reaktionsfunktionen für erweiterte Bedrohungen mit umfassender Endpunktsicherheit bereit.</span><span class="sxs-lookup"><span data-stu-id="73973-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="73973-161">Im Bereich</span><span class="sxs-lookup"><span data-stu-id="73973-161">In scope</span></span>

<span data-ttu-id="73973-162">Die folgenden Aufgaben sind für dieses Handbuch im Bereich:</span><span class="sxs-lookup"><span data-stu-id="73973-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="73973-163">Einrichten Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="73973-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="73973-164">Einrichten von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73973-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="73973-165">Registrieren Sie sich für Microsoft 365 E5 Testversion, oder verwenden Sie Ihre Volllizenz, wenn Sie ein Pilotprojekt ausführen</span><span class="sxs-lookup"><span data-stu-id="73973-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="73973-166">Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="73973-166">Configure domain</span></span>
    -   <span data-ttu-id="73973-167">Zuweisen Microsoft 365 E5 Lizenzen</span><span class="sxs-lookup"><span data-stu-id="73973-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="73973-168">Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="73973-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="73973-169">Konfigurieren aller Microsoft 365 defender-Säulen basierend auf bewährten Methoden</span><span class="sxs-lookup"><span data-stu-id="73973-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="73973-170">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="73973-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="73973-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="73973-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="73973-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="73973-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="73973-173">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="73973-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="73973-174">Nicht inbegriffen</span><span class="sxs-lookup"><span data-stu-id="73973-174">Out of scope</span></span>

<span data-ttu-id="73973-175">Die folgenden Informationen sind nicht in diesem Bereitstellungshandbuch beschrieben:</span><span class="sxs-lookup"><span data-stu-id="73973-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="73973-176">Konfiguration von Drittanbieterlösungen, die in Defender integriert Microsoft 365 können</span><span class="sxs-lookup"><span data-stu-id="73973-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="73973-177">Penetrationstests in der Produktionsumgebung</span><span class="sxs-lookup"><span data-stu-id="73973-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="73973-178">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="73973-178">Next step</span></span>
<span data-ttu-id="73973-179">[Phase 1: Vorbereiten](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="73973-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="73973-180">Vorbereiten ihrer Microsoft 365 Testumgebung oder Pilotumgebung für Defender</span><span class="sxs-lookup"><span data-stu-id="73973-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
