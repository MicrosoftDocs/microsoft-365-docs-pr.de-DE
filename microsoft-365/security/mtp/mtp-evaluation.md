---
title: Microsoft 365 Defender testen
description: Richten Sie Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung ein, um die Sicherheitslösung zum Schutz von Geräten, Identitäten, Daten und Anwendungen in Ihrer Organisation auszuprobieren und zu testen.
keywords: Testversion von Microsoft Threat Protection, Testen von Microsoft Threat Protection, Bewerten von Microsoft Threat Protection, Microsoft Threat Protection-Evaluierungslabor, Microsoft Threat Protection-Pilot, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Wartung, erweiterte Suche
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930210"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="e7c3d-104">Erstellen einer Microsoft 365 Defender-Testumgebung oder -Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="e7c3d-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e7c3d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e7c3d-105">**Applies to:**</span></span>
- <span data-ttu-id="e7c3d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7c3d-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="e7c3d-107">Dieses Handbuch unterstützt Sie beim Einrichten einer Laborumgebung mit Benutzern und Gruppen und führt Sie dann durch die Konfiguration der Funktionen in Microsoft 365 Defender, sodass Sie einen Bedrohungsangriff imitieren und ein aussagekräftiges Testergebnis erhalten können.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="e7c3d-108">Der Zweck der Erstellung dieser Testumgebung oder Pilotumgebung besteht im Veranschaulichen der umfassenden und integrierten Microsoft 365 Defender-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="e7c3d-109">Erfahren Sie, wie diese intelligente Sicherheitslösung erweiterte Bedrohungen in Ihrer Organisation erkennt, verhindert, automatisch untersucht und darauf reagiert.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="e7c3d-110">Sie werden durch die Schritte zum Starten der Microsoft 365 Defender-Evaluierung basierend auf den empfohlenen Bereitstellungspfaden geführt.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="e7c3d-111">Das Ziel ist es, Sie beim Einrichten der Sicherheitslösung entweder in einer Testumgebung mit einem Testkonto oder in einer Pilotumgebung in der Produktion mit einer Volllizenz zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="e7c3d-112">Durch die Vorbereitung ihrer Testumgebung oder Pilotumgebung können Sie Entscheidungsträgern in Ihrer Organisation Verwendungsfälle für Sicherheitsoperation präsentieren.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="e7c3d-113">Wenn Sie mit der Ausführung Ihrer Angriffssimulationen fertig sind und mit den Ergebnissen zufrieden sind, können Sie sie mithilfe von Technischen Vertriebsexperten oder Experten in Ihrer Organisation vollständig in Ihrer Organisation bereitstellen und operationalisieren.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="e7c3d-114">Dieses Handbuch hilft Ihnen dabei:</span><span class="sxs-lookup"><span data-stu-id="e7c3d-114">This guide will help you:</span></span>
- <span data-ttu-id="e7c3d-115">Einrichten des Laborservers und der Computer</span><span class="sxs-lookup"><span data-stu-id="e7c3d-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="e7c3d-116">Konfigurieren von Active Directory mit Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="e7c3d-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="e7c3d-117">Einrichten und Konfigurieren von Microsoft Defender for Identity, Microsoft Defender für Office 365, Microsoft Defender for Endpoint und Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e7c3d-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="e7c3d-118">Einrichten lokaler Richtlinien für Ihren Server und Ihre Computer</span><span class="sxs-lookup"><span data-stu-id="e7c3d-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="e7c3d-119">Imitieren eines Bedrohungsangriffs, um einen Testvorfall oder eine Warnung in Microsoft 365 Defender zu generieren</span><span class="sxs-lookup"><span data-stu-id="e7c3d-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="e7c3d-120">Befolgen Sie für optimale Ergebnisse die Anweisungen zum Einrichten der Übung so genau wie möglich.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="e7c3d-121">Bereitstellungsphasen</span><span class="sxs-lookup"><span data-stu-id="e7c3d-121">Deployment phases</span></span>

<span data-ttu-id="e7c3d-122">Es gibt drei Phasen beim Erstellen einer Microsoft 365 Defender-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Bereitstellungsphasen: Vorbereiten, Einrichten, Onboarding](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="e7c3d-124">Phase</span><span class="sxs-lookup"><span data-stu-id="e7c3d-124">Phase</span></span> | <span data-ttu-id="e7c3d-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7c3d-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="e7c3d-126">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="e7c3d-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="e7c3d-127">Erfahren Sie, was Sie bei der Bereitstellung von Microsoft 365 Defender in einer Testumgebung oder Pilotumgebung berücksichtigen müssen:</span><span class="sxs-lookup"><span data-stu-id="e7c3d-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="e7c3d-128">– Projektbeteiligten und Abmelden</span><span class="sxs-lookup"><span data-stu-id="e7c3d-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="e7c3d-129">– Überlegungen zur Umgebung</span><span class="sxs-lookup"><span data-stu-id="e7c3d-129">- Environment considerations</span></span> <br><span data-ttu-id="e7c3d-130">– Zugriff</span><span class="sxs-lookup"><span data-stu-id="e7c3d-130">- Access</span></span> <br><span data-ttu-id="e7c3d-131">– Azure Active Directory Setup</span><span class="sxs-lookup"><span data-stu-id="e7c3d-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="e7c3d-132">– Konfigurationsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="e7c3d-132">- Configuration order</span></span>
|[<span data-ttu-id="e7c3d-133">Phase 2: Einrichten</span><span class="sxs-lookup"><span data-stu-id="e7c3d-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="e7c3d-134">Machen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center, um Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung zu einrichten.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="e7c3d-135">Sie werden geführt zu:</span><span class="sxs-lookup"><span data-stu-id="e7c3d-135">You'll be guided to:</span></span><br><br><span data-ttu-id="e7c3d-136">– Registrieren für Die Testversion von Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e7c3d-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="e7c3d-137">- Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="e7c3d-137">- Configure domain</span></span><br><span data-ttu-id="e7c3d-138">– Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="e7c3d-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="e7c3d-139">– Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="e7c3d-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="e7c3d-140">Phase 3: Konfigurieren & Onboarding</span><span class="sxs-lookup"><span data-stu-id="e7c3d-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="e7c3d-141">Konfigurieren Sie die einzelnen Microsoft 365 Defender-Säulen- und Onboard-Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="e7c3d-142">Sie werden geführt zu:</span><span class="sxs-lookup"><span data-stu-id="e7c3d-142">You'll be guided to:</span></span><br><br><span data-ttu-id="e7c3d-143">- Konfigurieren von Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="e7c3d-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="e7c3d-144">– Konfigurieren von Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e7c3d-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="e7c3d-145">– Konfigurieren von Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e7c3d-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="e7c3d-146">- Konfigurieren von Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e7c3d-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="e7c3d-147">Nachdem Sie dieses Handbuch abgeschlossen haben, hätten Sie die beteiligten Beteiligten und die erforderlichen Genehmigungen identifiziert, über die richtigen Zugriffsberechtigungen verfügen, sich für die Testversion registrieren, Domänen und jede der Microsoft 365 Defender-Säulen konfiguriert, und Ihre Endpunkte werden in den Dienst eingebunden.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="e7c3d-148">Wichtige Funktionen</span><span class="sxs-lookup"><span data-stu-id="e7c3d-148">Key capabilities</span></span>

<span data-ttu-id="e7c3d-149">Obwohl Microsoft 365 Defender viele Funktionen bietet, besteht der Hauptzweck dieses Bereitstellungshandbuchs im Einstieg in das Onboarding von Geräten.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="e7c3d-150">Zusätzlich zum Onboarding erhalten Sie in diesem Leitfaden die ersten Schritte mit den folgenden Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="e7c3d-151">Funktion</span><span class="sxs-lookup"><span data-stu-id="e7c3d-151">Capability</span></span> | <span data-ttu-id="e7c3d-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7c3d-152">Description</span></span> 
:---|:---
<span data-ttu-id="e7c3d-153">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="e7c3d-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="e7c3d-154">Schützt Ihre gesamte Office 365-Envrionment vor heutigen Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="e7c3d-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e7c3d-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="e7c3d-156">Identifiziert und erkennt Bedrohungen für gefährdete Identitäten und böswillige Insideraktionen.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="e7c3d-157">Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e7c3d-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="e7c3d-158">Bietet umfassende Transparenz, kontrolle über den Datenverkehr und erkennt Cyberbedrohungen über Clouddienste hinweg.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="e7c3d-159">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e7c3d-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="e7c3d-160">Verhindert, erkennt und bietet Reaktionsfunktionen für erweiterte Bedrohungen mit umfassender Endpunktsicherheit.</span><span class="sxs-lookup"><span data-stu-id="e7c3d-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="e7c3d-161">Im Bereich</span><span class="sxs-lookup"><span data-stu-id="e7c3d-161">In scope</span></span>

<span data-ttu-id="e7c3d-162">Die folgenden Aufgaben sind in diesem Leitfaden beschrieben:</span><span class="sxs-lookup"><span data-stu-id="e7c3d-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="e7c3d-163">Einrichten von Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e7c3d-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="e7c3d-164">Einrichten von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7c3d-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="e7c3d-165">Registrieren Sie sich für die Testversion von Microsoft 365 E5, oder verwenden Sie Ihre Volllizenz, wenn Sie ein Pilotprojekt ausführen</span><span class="sxs-lookup"><span data-stu-id="e7c3d-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="e7c3d-166">Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="e7c3d-166">Configure domain</span></span>
    -   <span data-ttu-id="e7c3d-167">Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="e7c3d-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="e7c3d-168">Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="e7c3d-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="e7c3d-169">Konfigurieren aller Microsoft 365 Defender-Säulen basierend auf bewährten Methoden</span><span class="sxs-lookup"><span data-stu-id="e7c3d-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="e7c3d-170">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="e7c3d-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="e7c3d-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e7c3d-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="e7c3d-172">Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e7c3d-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="e7c3d-173">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e7c3d-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="e7c3d-174">Nicht inbegriffen</span><span class="sxs-lookup"><span data-stu-id="e7c3d-174">Out of scope</span></span>

<span data-ttu-id="e7c3d-175">Die folgenden Themen werden in diesem Bereitstellungshandbuch nicht beschrieben:</span><span class="sxs-lookup"><span data-stu-id="e7c3d-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="e7c3d-176">Konfiguration von Drittanbieterlösungen, die in Microsoft 365 Defender integriert werden können</span><span class="sxs-lookup"><span data-stu-id="e7c3d-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="e7c3d-177">Penetrationstests in der Produktionsumgebung</span><span class="sxs-lookup"><span data-stu-id="e7c3d-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="e7c3d-178">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e7c3d-178">Next step</span></span>
<span data-ttu-id="e7c3d-179">[Phase 1: Vorbereiten](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="e7c3d-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="e7c3d-180">Vorbereiten ihrer Microsoft 365 Defender-Testumgebung oder -Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="e7c3d-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
