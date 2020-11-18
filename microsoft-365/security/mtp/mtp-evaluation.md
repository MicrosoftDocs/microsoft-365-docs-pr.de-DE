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
ms.openlocfilehash: fe0a06dd104f0f0532363ee046f4bad1c03c5400
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130892"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="84491-104">Erstellen eines Microsoft 365 Defender-Testlabors oder einer Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="84491-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="84491-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="84491-105">**Applies to:**</span></span>
- <span data-ttu-id="84491-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84491-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="84491-107">Der Zweck der Erstellung dieser Test Labor-oder Pilotumgebung besteht darin, die umfassenden und integrierten Funktionen von Microsoft 365 Defender zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="84491-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="84491-108">Erfahren Sie, wie diese intelligente Sicherheitslösung erkannt, verhindert, automatisch untersucht und auf Erweiterte Bedrohungen Ihrer Organisation reagiert.</span><span class="sxs-lookup"><span data-stu-id="84491-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="84491-109">Dieses Handbuch führt Sie durch die Schritte zum Starten Ihrer Microsoft 365 Defender-Evaluierung basierend auf den empfohlenen Bereitstellungspfaden.</span><span class="sxs-lookup"><span data-stu-id="84491-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="84491-110">Das Ziel besteht darin, Sie bei der Einrichtung der Sicherheitslösung entweder in einer Testumgebung mit einem Test Konto oder in einer Pilotumgebung in der Produktion mit einer Vollversion zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="84491-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="84491-111">Durch die Vorbereitung Ihrer Test Labor-oder Pilotumgebung können Sie Entscheidungsträgern in Ihrer Organisation bei der Vorgehensweise Sicherheitseinsatz-Anwendungsfällen helfen.</span><span class="sxs-lookup"><span data-stu-id="84491-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="84491-112">Wenn Sie die Angriffssimulationen ausgeführt haben und mit den Ergebnissen zufrieden sind, können Sie Sie in Ihrer Organisation mit Hilfe von technischen Microsoft-Vertriebsexperten oder Experten in Ihrer Organisation vollständig bereitstellen und in Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="84491-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="84491-113">Dieses Handbuch hilft Ihnen dabei:</span><span class="sxs-lookup"><span data-stu-id="84491-113">This guide will help you:</span></span>
- <span data-ttu-id="84491-114">Einrichten des Lab-Servers und der Computer</span><span class="sxs-lookup"><span data-stu-id="84491-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="84491-115">Konfigurieren von Active Directory mit Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="84491-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="84491-116">Einrichten und Konfigurieren von Microsoft Defender für Identity, Microsoft Defender für Office 365, Microsoft Defender for Endpoint und Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="84491-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="84491-117">Einrichten von lokalen Richtlinien für Ihren Server und ihre Computer</span><span class="sxs-lookup"><span data-stu-id="84491-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="84491-118">Simulieren eines Bedrohungs Angriffs zum Generieren eines Test Vorfalls oder einer Warnung in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84491-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="84491-119">Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen im Labor Setup so genau wie möglich.</span><span class="sxs-lookup"><span data-stu-id="84491-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="84491-120">Bereitstellungsphasen</span><span class="sxs-lookup"><span data-stu-id="84491-120">Deployment phases</span></span>

<span data-ttu-id="84491-121">Es gibt drei Phasen, in denen eine Microsoft 365 Defender-Testumgebung erstellt und bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="84491-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

![Bereitstellungsphasen: vorbereiten, einrichten, Onboard](../../media/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="84491-123">Phase</span><span class="sxs-lookup"><span data-stu-id="84491-123">Phase</span></span> | <span data-ttu-id="84491-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84491-124">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="84491-125">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="84491-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="84491-126">Erfahren Sie, was Sie bei der Bereitstellung von Microsoft 365 Defender in einer Test Labor-oder Pilotumgebung berücksichtigen müssen:</span><span class="sxs-lookup"><span data-stu-id="84491-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="84491-127">-Stakeholder und Sign-Off</span><span class="sxs-lookup"><span data-stu-id="84491-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="84491-128">-Umgebungs Überlegungen</span><span class="sxs-lookup"><span data-stu-id="84491-128">- Environment considerations</span></span> <br><span data-ttu-id="84491-129">-Access</span><span class="sxs-lookup"><span data-stu-id="84491-129">- Access</span></span> <br><span data-ttu-id="84491-130">-Azure-Active Directory-Setup</span><span class="sxs-lookup"><span data-stu-id="84491-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="84491-131">-Konfigurations Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="84491-131">- Configuration order</span></span>
|[<span data-ttu-id="84491-132">Phase 2: Setup</span><span class="sxs-lookup"><span data-stu-id="84491-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="84491-133">Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, um die Testumgebung für das Microsoft 365 Defender-Testlabor oder die Pilotumgebung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="84491-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="84491-134">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="84491-134">You'll be guided to:</span></span><br><br><span data-ttu-id="84491-135">-Registrieren für Microsoft 365 E5-Testversion</span><span class="sxs-lookup"><span data-stu-id="84491-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="84491-136">-Domäne konfigurieren</span><span class="sxs-lookup"><span data-stu-id="84491-136">- Configure domain</span></span><br><span data-ttu-id="84491-137">-Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="84491-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="84491-138">-Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="84491-138">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="84491-139">Phase 3: Konfigurieren von & Onboard</span><span class="sxs-lookup"><span data-stu-id="84491-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="84491-140">Konfigurieren Sie die einzelnen Microsoft 365 Defender-Pfeiler und Onboard-Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="84491-140">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="84491-141">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="84491-141">You'll be guided to:</span></span><br><br><span data-ttu-id="84491-142">-Konfigurieren von Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="84491-142">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="84491-143">-Konfigurieren der Microsoft Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="84491-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="84491-144">-Konfigurieren von Microsoft Defender für Identity</span><span class="sxs-lookup"><span data-stu-id="84491-144">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="84491-145">-Konfigurieren von Microsoft Defender für Endpoint</span><span class="sxs-lookup"><span data-stu-id="84491-145">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="84491-146">Im Bereich</span><span class="sxs-lookup"><span data-stu-id="84491-146">In scope</span></span>

<span data-ttu-id="84491-147">Die folgenden Aufgaben liegen im Bereich dieses Handbuchs:</span><span class="sxs-lookup"><span data-stu-id="84491-147">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="84491-148">Einrichten von Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="84491-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="84491-149">Einrichten von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84491-149">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="84491-150">Registrieren Sie sich für die Microsoft 365 E5-Testversion, oder verwenden Sie Ihre vollständige Lizenz, wenn Sie ein Pilotprojekt betreiben.</span><span class="sxs-lookup"><span data-stu-id="84491-150">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="84491-151">Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="84491-151">Configure domain</span></span>
    -   <span data-ttu-id="84491-152">Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="84491-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="84491-153">Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="84491-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="84491-154">Konfigurieren aller Microsoft 365 Defender-Säulen basierend auf bewährten Methoden</span><span class="sxs-lookup"><span data-stu-id="84491-154">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="84491-155">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="84491-155">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="84491-156">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="84491-156">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="84491-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="84491-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="84491-158">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="84491-158">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="84491-159">Nicht inbegriffen</span><span class="sxs-lookup"><span data-stu-id="84491-159">Out of scope</span></span>

<span data-ttu-id="84491-160">Im Rahmen dieses Bereitstellungshandbuchs liegen folgende Schritte vor:</span><span class="sxs-lookup"><span data-stu-id="84491-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="84491-161">Konfiguration von Drittanbieterlösungen, die in Microsoft 365 Defender integriert werden können</span><span class="sxs-lookup"><span data-stu-id="84491-161">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="84491-162">Penetrationstests in der Produktionsumgebung</span><span class="sxs-lookup"><span data-stu-id="84491-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="84491-163">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="84491-163">Next step</span></span>
<span data-ttu-id="84491-164">[Phase 1: Vorbereiten](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="84491-164">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="84491-165">Vorbereiten des Testlabors oder der Pilotumgebung für den Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84491-165">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
