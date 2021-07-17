---
title: Microsoft 365 Defender testen
description: Richten Sie Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung ein, um die Sicherheitslösung zum Schutz von Geräten, Identität, Daten und Anwendungen in Ihrer Organisation auszuprobieren und zu testen.
keywords: Microsoft 365 Defender Testversion, testen Sie Microsoft 365 Defender, bewerten Sie Microsoft 365 Defender, Microsoft 365 Defender Evaluierungslabor, Microsoft 365 Defender Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
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
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458428"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="c6dac-104">Erstellen einer Microsoft 365 Defender Testumgebung oder Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="c6dac-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c6dac-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c6dac-105">**Applies to:**</span></span>
- <span data-ttu-id="c6dac-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6dac-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="c6dac-107">Dieser Leitfaden hilft Ihnen beim Einrichten einer Lab-Umgebung mit Benutzern und Gruppen und führt Sie dann durch die Konfiguration der Funktionen in Microsoft 365 Defender, sodass Sie einen Bedrohungsangriff imitieren und ein aussagekräftiges Testergebnis erhalten können.</span><span class="sxs-lookup"><span data-stu-id="c6dac-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="c6dac-108">Der Zweck der Erstellung dieser Testumgebung oder Pilotumgebung besteht darin, die umfassenden und integrierten Microsoft 365 Defender Funktionen zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="c6dac-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="c6dac-109">Erfahren Sie, wie diese intelligente Sicherheitslösung fortschrittliche Bedrohungen in Ihrer Organisation erkennt, verhindert, automatisch untersucht und darauf reagiert.</span><span class="sxs-lookup"><span data-stu-id="c6dac-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="c6dac-110">Sie werden durch die Schritte geführt, um ihre Microsoft 365 Defender Evaluierung basierend auf den empfohlenen Bereitstellungspfaden zu starten.</span><span class="sxs-lookup"><span data-stu-id="c6dac-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="c6dac-111">Das Ziel besteht darin, Sie beim Einrichten der Sicherheitslösung entweder in einer Testumgebung mit einem Testkonto oder in einer Pilotumgebung in der Produktion mit einer Volllizenz zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c6dac-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="c6dac-112">Durch die Vorbereitung Ihrer Testumgebung oder Pilotumgebung können Sie Entscheidungsträgern in Ihrer Organisation Anwendungsfälle für den Sicherheitsvorgang präsentieren.</span><span class="sxs-lookup"><span data-stu-id="c6dac-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="c6dac-113">Wenn Sie ihre Angriffssimulationen abgeschlossen haben und mit den Ergebnissen zufrieden sind, können Sie sie mithilfe von Microsoft Technical Sales Professionals oder Experten in Ihrer Organisation vollständig bereitstellen und in Ihrer Organisation operationalisieren.</span><span class="sxs-lookup"><span data-stu-id="c6dac-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="c6dac-114">Dieser Leitfaden hilft Ihnen dabei:</span><span class="sxs-lookup"><span data-stu-id="c6dac-114">This guide will help you:</span></span>
- <span data-ttu-id="c6dac-115">Einrichten des Lab-Servers und der Computer</span><span class="sxs-lookup"><span data-stu-id="c6dac-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="c6dac-116">Konfigurieren von Active Directory mit Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="c6dac-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="c6dac-117">Einrichten und Konfigurieren von Microsoft Defender for Identity, Microsoft Defender für Office 365, Microsoft Defender für Endpunkt und Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c6dac-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="c6dac-118">Einrichten von lokalen Richtlinien für Ihren Server und Computer</span><span class="sxs-lookup"><span data-stu-id="c6dac-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="c6dac-119">Imitieren eines Bedrohungsangriffs zum Generieren eines Testvorfalls oder einer Warnung in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6dac-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="c6dac-120">Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen für die Laboreinrichtung so genau wie möglich.</span><span class="sxs-lookup"><span data-stu-id="c6dac-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="c6dac-121">Bereitstellungsphasen</span><span class="sxs-lookup"><span data-stu-id="c6dac-121">Deployment phases</span></span>

<span data-ttu-id="c6dac-122">Es gibt drei Phasen beim Erstellen einer Microsoft 365 Defender Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="c6dac-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Bereitstellungsphasen: Vorbereiten, Einrichten, Onboarding](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="c6dac-124">Phase</span><span class="sxs-lookup"><span data-stu-id="c6dac-124">Phase</span></span> | <span data-ttu-id="c6dac-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6dac-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="c6dac-126">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="c6dac-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="c6dac-127">Erfahren Sie, was Sie berücksichtigen müssen, wenn Sie Microsoft 365 Defender in einer Testumgebung oder Pilotumgebung bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="c6dac-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="c6dac-128">– Projektbeteiligten und Abmeldung</span><span class="sxs-lookup"><span data-stu-id="c6dac-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="c6dac-129">– Überlegungen zur Umgebung</span><span class="sxs-lookup"><span data-stu-id="c6dac-129">- Environment considerations</span></span> <br><span data-ttu-id="c6dac-130">– Zugriff</span><span class="sxs-lookup"><span data-stu-id="c6dac-130">- Access</span></span> <br><span data-ttu-id="c6dac-131">– Azure Active Directory Einrichten</span><span class="sxs-lookup"><span data-stu-id="c6dac-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="c6dac-132">- Konfigurationsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="c6dac-132">- Configuration order</span></span>
|[<span data-ttu-id="c6dac-133">Phase 2: Setup</span><span class="sxs-lookup"><span data-stu-id="c6dac-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="c6dac-134">Führen Sie die ersten Schritte aus, um auf Microsoft 365 Security Center zuzugreifen, um Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="c6dac-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="c6dac-135">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="c6dac-135">You'll be guided to:</span></span><br><br><span data-ttu-id="c6dac-136">– Registrieren für Microsoft 365 E5 Testversion</span><span class="sxs-lookup"><span data-stu-id="c6dac-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="c6dac-137">- Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="c6dac-137">- Configure domain</span></span><br><span data-ttu-id="c6dac-138">– Zuweisen Microsoft 365 E5 Lizenzen</span><span class="sxs-lookup"><span data-stu-id="c6dac-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="c6dac-139">– Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="c6dac-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="c6dac-140">Phase 3: Konfigurieren & Onboarding</span><span class="sxs-lookup"><span data-stu-id="c6dac-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="c6dac-141">Konfigurieren Sie die einzelnen Microsoft 365 Defender Säulen und integrieren Sie Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="c6dac-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="c6dac-142">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="c6dac-142">You'll be guided to:</span></span><br><br><span data-ttu-id="c6dac-143">– Konfigurieren von Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="c6dac-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="c6dac-144">- Konfigurieren Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c6dac-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="c6dac-145">– Konfigurieren von Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="c6dac-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="c6dac-146">– Konfigurieren von Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c6dac-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="c6dac-147">Nachdem Sie diesen Leitfaden abgeschlossen haben, hätten Sie die beteiligten Beteiligten und die erforderlichen Genehmigungen identifiziert, die richtigen Zugriffsberechtigungen haben, sich für testversionsbasierte, konfigurierte Domänen und jede der Microsoft 365 Defender Säulen angemeldet haben, und Ihre Endpunkte werden in den Dienst integriert.</span><span class="sxs-lookup"><span data-stu-id="c6dac-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="c6dac-148">Wichtige Funktionen</span><span class="sxs-lookup"><span data-stu-id="c6dac-148">Key capabilities</span></span>

<span data-ttu-id="c6dac-149">Obwohl Microsoft 365 Defender viele Funktionen bietet, besteht der Hauptzweck dieses Bereitstellungshandbuchs darin, Ihnen die ersten Schritte beim Onboarding von Geräten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c6dac-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="c6dac-150">Zusätzlich zum Onboarding können Sie mit dieser Anleitung mit den folgenden Funktionen beginnen.</span><span class="sxs-lookup"><span data-stu-id="c6dac-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="c6dac-151">Funktion</span><span class="sxs-lookup"><span data-stu-id="c6dac-151">Capability</span></span> | <span data-ttu-id="c6dac-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6dac-152">Description</span></span> 
:---|:---
<span data-ttu-id="c6dac-153">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="c6dac-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="c6dac-154">Trägt dazu bei, Ihre gesamte Office 365 Bedrohungen vor heutigen Bedrohungen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="c6dac-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="c6dac-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="c6dac-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="c6dac-156">Identifiziert und erkennt Bedrohungen für kompromittierte Identitäten und böswillige Insideraktionen.</span><span class="sxs-lookup"><span data-stu-id="c6dac-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="c6dac-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c6dac-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="c6dac-158">Bietet umfassende Sichtbarkeit, Kontrolle der Daten-Reise und Erkennung von Cyberbedrohungen über Clouddienste hinweg.</span><span class="sxs-lookup"><span data-stu-id="c6dac-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="c6dac-159">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c6dac-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="c6dac-160">Verhindert, erkennt und bietet Reaktionsfunktionen auf fortgeschrittene Bedrohungen mit umfassender Endpunktsicherheit.</span><span class="sxs-lookup"><span data-stu-id="c6dac-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="c6dac-161">Im Bereich</span><span class="sxs-lookup"><span data-stu-id="c6dac-161">In scope</span></span>

<span data-ttu-id="c6dac-162">Die folgenden Aufgaben sind in diesem Leitfaden enthalten:</span><span class="sxs-lookup"><span data-stu-id="c6dac-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="c6dac-163">Einrichten Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c6dac-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="c6dac-164">Einrichten Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6dac-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="c6dac-165">Registrieren Sie sich für Microsoft 365 E5 Testversion, oder verwenden Sie Ihre Volllizenz, wenn Sie ein Pilotprojekt ausführen</span><span class="sxs-lookup"><span data-stu-id="c6dac-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="c6dac-166">Domäne konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c6dac-166">Configure domain</span></span>
    -   <span data-ttu-id="c6dac-167">Zuweisen Microsoft 365 E5 Lizenzen</span><span class="sxs-lookup"><span data-stu-id="c6dac-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="c6dac-168">Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="c6dac-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="c6dac-169">Konfigurieren aller Microsoft 365 Defender Säulen basierend auf bewährten Methoden</span><span class="sxs-lookup"><span data-stu-id="c6dac-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="c6dac-170">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="c6dac-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="c6dac-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="c6dac-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="c6dac-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c6dac-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="c6dac-173">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c6dac-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="c6dac-174">Nicht inbegriffen</span><span class="sxs-lookup"><span data-stu-id="c6dac-174">Out of scope</span></span>

<span data-ttu-id="c6dac-175">Der Umfang dieses Bereitstellungshandbuchs wird nicht behandelt:</span><span class="sxs-lookup"><span data-stu-id="c6dac-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="c6dac-176">Konfiguration von Drittanbieterlösungen, die in Microsoft 365 Defender integriert werden können</span><span class="sxs-lookup"><span data-stu-id="c6dac-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="c6dac-177">Penetrationstests in der Produktionsumgebung</span><span class="sxs-lookup"><span data-stu-id="c6dac-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="c6dac-178">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c6dac-178">Next step</span></span>
<span data-ttu-id="c6dac-179">[Phase 1: Vorbereiten](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="c6dac-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="c6dac-180">Vorbereiten ihrer Microsoft 365 Defender Testumgebung oder Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="c6dac-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
