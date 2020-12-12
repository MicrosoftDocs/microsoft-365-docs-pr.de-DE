---
title: Auswerten von Microsoft 365 Defender
description: Richten Sie Ihre Microsoft 365 Defender Test Lab oder Pilotumgebung ein, um die Sicherheitslösung zum Schutz von Geräten, Identitäten, Daten und Anwendungen in Ihrer Organisation zu testen und zu erleben.
keywords: Microsoft Threat Protection-Testversion, testen Sie Microsoft Threat Protection, bewerten Sie Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab, Microsoft Threat Protection Pilot, Cyber Security, Advanced persistent Threat, Enterprise Security, Devices, Device, Identity, users, Data, Applications, Incidents, Automated Investigation and Remediation, Advanced Hunting
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659633"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="89be1-104">Erstellen eines Microsoft 365 Defender-Testlabors oder einer Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="89be1-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="89be1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="89be1-105">**Applies to:**</span></span>
- <span data-ttu-id="89be1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89be1-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="89be1-107">Dieses Handbuch hilft Ihnen beim Einrichten einer Lab-Umgebung mit Benutzern und Gruppen und führt Sie durch die Konfiguration der Funktionen in Microsoft 365 Defender, sodass Sie einen Bedrohungs Angriff nachahmen und ein aussagekräftiges Testergebnis erhalten können.</span><span class="sxs-lookup"><span data-stu-id="89be1-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="89be1-108">Der Zweck der Erstellung dieser Test Labor-oder Pilotumgebung besteht darin, die umfassenden und integrierten Funktionen von Microsoft 365 Defender zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="89be1-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="89be1-109">Erfahren Sie, wie diese intelligente Sicherheitslösung erkannt, verhindert, automatisch untersucht und auf Erweiterte Bedrohungen Ihrer Organisation reagiert.</span><span class="sxs-lookup"><span data-stu-id="89be1-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="89be1-110">Sie werden durch die Schritte zum Starten Ihrer Microsoft 365 Defender-Evaluierung basierend auf den empfohlenen Bereitstellungspfaden geführt.</span><span class="sxs-lookup"><span data-stu-id="89be1-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="89be1-111">Das Ziel besteht darin, Sie bei der Einrichtung der Sicherheitslösung entweder in einer Testumgebung mit einem Test Konto oder in einer Pilotumgebung in der Produktion mit einer Vollversion zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="89be1-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="89be1-112">Durch die Vorbereitung Ihrer Test Labor-oder Pilotumgebung können Sie Entscheidungsträgern in Ihrer Organisation bei der Vorgehensweise Sicherheitseinsatz-Anwendungsfällen helfen.</span><span class="sxs-lookup"><span data-stu-id="89be1-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="89be1-113">Wenn Sie die Angriffssimulationen ausgeführt haben und mit den Ergebnissen zufrieden sind, können Sie Sie in Ihrer Organisation mit Hilfe von technischen Microsoft-Vertriebsexperten oder Experten in Ihrer Organisation vollständig bereitstellen und in Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="89be1-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="89be1-114">Dieses Handbuch hilft Ihnen dabei:</span><span class="sxs-lookup"><span data-stu-id="89be1-114">This guide will help you:</span></span>
- <span data-ttu-id="89be1-115">Einrichten des Lab-Servers und der Computer</span><span class="sxs-lookup"><span data-stu-id="89be1-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="89be1-116">Konfigurieren von Active Directory mit Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="89be1-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="89be1-117">Einrichten und Konfigurieren von Microsoft Defender für Identity, Microsoft Defender für Office 365, Microsoft Defender for Endpoint und Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="89be1-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="89be1-118">Einrichten von lokalen Richtlinien für Ihren Server und ihre Computer</span><span class="sxs-lookup"><span data-stu-id="89be1-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="89be1-119">Simulieren eines Bedrohungs Angriffs zum Generieren eines Test Vorfalls oder einer Warnung in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89be1-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="89be1-120">Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen im Labor Setup so genau wie möglich.</span><span class="sxs-lookup"><span data-stu-id="89be1-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="89be1-121">Bereitstellungsphasen</span><span class="sxs-lookup"><span data-stu-id="89be1-121">Deployment phases</span></span>

<span data-ttu-id="89be1-122">Es gibt drei Phasen beim Erstellen einer Testumgebung für Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="89be1-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Bereitstellungsphasen: vorbereiten, einrichten, Onboard](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="89be1-124">Phase</span><span class="sxs-lookup"><span data-stu-id="89be1-124">Phase</span></span> | <span data-ttu-id="89be1-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89be1-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="89be1-126">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="89be1-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="89be1-127">Erfahren Sie, was Sie bei der Bereitstellung von Microsoft 365 Defender in einer Test Labor-oder Pilotumgebung berücksichtigen müssen:</span><span class="sxs-lookup"><span data-stu-id="89be1-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="89be1-128">-Stakeholder und Sign-Off</span><span class="sxs-lookup"><span data-stu-id="89be1-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="89be1-129">-Umgebungs Überlegungen</span><span class="sxs-lookup"><span data-stu-id="89be1-129">- Environment considerations</span></span> <br><span data-ttu-id="89be1-130">-Access</span><span class="sxs-lookup"><span data-stu-id="89be1-130">- Access</span></span> <br><span data-ttu-id="89be1-131">-Azure-Active Directory-Setup</span><span class="sxs-lookup"><span data-stu-id="89be1-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="89be1-132">-Konfigurations Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="89be1-132">- Configuration order</span></span>
|[<span data-ttu-id="89be1-133">Phase 2: Setup</span><span class="sxs-lookup"><span data-stu-id="89be1-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="89be1-134">Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, um die Testumgebung für das Microsoft 365 Defender-Testlabor oder die Pilotumgebung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="89be1-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="89be1-135">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="89be1-135">You'll be guided to:</span></span><br><br><span data-ttu-id="89be1-136">-Registrieren für Microsoft 365 E5-Testversion</span><span class="sxs-lookup"><span data-stu-id="89be1-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="89be1-137">-Domäne konfigurieren</span><span class="sxs-lookup"><span data-stu-id="89be1-137">- Configure domain</span></span><br><span data-ttu-id="89be1-138">-Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="89be1-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="89be1-139">-Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="89be1-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="89be1-140">Phase 3: Konfigurieren von & Onboard</span><span class="sxs-lookup"><span data-stu-id="89be1-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="89be1-141">Konfigurieren Sie die einzelnen Microsoft 365 Defender-Pfeiler und Onboard-Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="89be1-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="89be1-142">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="89be1-142">You'll be guided to:</span></span><br><br><span data-ttu-id="89be1-143">-Konfigurieren von Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="89be1-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="89be1-144">-Konfigurieren der Microsoft Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="89be1-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="89be1-145">-Konfigurieren von Microsoft Defender für Identity</span><span class="sxs-lookup"><span data-stu-id="89be1-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="89be1-146">-Konfigurieren von Microsoft Defender für Endpoint</span><span class="sxs-lookup"><span data-stu-id="89be1-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="89be1-147">Nachdem Sie dieses Handbuch abgeschlossen haben, hätten Sie die beteiligten Beteiligten und die erforderlichen Genehmigungen identifiziert, über die richtigen Zugriffsberechtigungen verfügen, sich für eine Testversion angemeldet haben, konfigurierte Domänen und alle Microsoft 365 Defender-Säulen haben und die Endpunkte an den Dienst weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="89be1-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="89be1-148">Wichtige Funktionen</span><span class="sxs-lookup"><span data-stu-id="89be1-148">Key capabilities</span></span>

<span data-ttu-id="89be1-149">Während Microsoft 365 Defender zahlreiche Funktionen bietet, besteht der Hauptzweck dieses Bereitstellungshandbuchs darin, Ihnen den Einstieg in die Onboarding-Geräte zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="89be1-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="89be1-150">Neben dem Onboarding erhalten Sie in diesem Leitfaden zunächst die folgenden Funktionen.</span><span class="sxs-lookup"><span data-stu-id="89be1-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="89be1-151">Funktion</span><span class="sxs-lookup"><span data-stu-id="89be1-151">Capability</span></span> | <span data-ttu-id="89be1-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89be1-152">Description</span></span> 
:---|:---
<span data-ttu-id="89be1-153">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="89be1-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="89be1-154">Schützt Ihr gesamtes Office 365 Umgebung vor den Bedrohungen von heute</span><span class="sxs-lookup"><span data-stu-id="89be1-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="89be1-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="89be1-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="89be1-156">Identifiziert und erkennt Bedrohungen für kompromittierte Identitäten und böswillige Insider Aktionen.</span><span class="sxs-lookup"><span data-stu-id="89be1-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="89be1-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="89be1-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="89be1-158">Bietet umfangreiche Sichtbarkeit, steuert Daten Reisen und erkennt Bedrohungen in Cloud-Diensten.</span><span class="sxs-lookup"><span data-stu-id="89be1-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="89be1-159">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="89be1-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="89be1-160">Verhindert, erkennt und stellt Reaktionsfunktionen für erweiterte Bedrohungen mit umfassender Endpunktsicherheit bereit.</span><span class="sxs-lookup"><span data-stu-id="89be1-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="89be1-161">Im Bereich</span><span class="sxs-lookup"><span data-stu-id="89be1-161">In scope</span></span>

<span data-ttu-id="89be1-162">Die folgenden Aufgaben liegen im Bereich dieses Handbuchs:</span><span class="sxs-lookup"><span data-stu-id="89be1-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="89be1-163">Einrichten von Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="89be1-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="89be1-164">Einrichten von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89be1-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="89be1-165">Registrieren Sie sich für die Microsoft 365 E5-Testversion, oder verwenden Sie Ihre vollständige Lizenz, wenn Sie ein Pilotprojekt betreiben.</span><span class="sxs-lookup"><span data-stu-id="89be1-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="89be1-166">Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="89be1-166">Configure domain</span></span>
    -   <span data-ttu-id="89be1-167">Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="89be1-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="89be1-168">Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="89be1-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="89be1-169">Konfigurieren aller Microsoft 365 Defender-Säulen basierend auf bewährten Methoden</span><span class="sxs-lookup"><span data-stu-id="89be1-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="89be1-170">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="89be1-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="89be1-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="89be1-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="89be1-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="89be1-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="89be1-173">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="89be1-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="89be1-174">Nicht inbegriffen</span><span class="sxs-lookup"><span data-stu-id="89be1-174">Out of scope</span></span>

<span data-ttu-id="89be1-175">Im Rahmen dieses Bereitstellungshandbuchs liegen folgende Schritte vor:</span><span class="sxs-lookup"><span data-stu-id="89be1-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="89be1-176">Konfiguration von Drittanbieterlösungen, die in Microsoft 365 Defender integriert werden können</span><span class="sxs-lookup"><span data-stu-id="89be1-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="89be1-177">Penetrationstests in der Produktionsumgebung</span><span class="sxs-lookup"><span data-stu-id="89be1-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="89be1-178">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="89be1-178">Next step</span></span>
<span data-ttu-id="89be1-179">[Phase 1: Vorbereiten](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="89be1-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="89be1-180">Vorbereiten des Testlabors oder der Pilotumgebung für den Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89be1-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
