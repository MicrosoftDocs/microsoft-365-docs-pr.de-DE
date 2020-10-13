---
title: Microsoft Threat Protection evaluieren
description: Richten Sie Ihr Microsoft Threat Protection-Test Labor oder Ihre Pilotumgebung ein, um die Sicherheitslösung zum Schutz von Geräten, Identitäten, Daten und Anwendungen in Ihrer Organisation zu testen und zu erleben.
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
ms.openlocfilehash: d3f63c8ac4ba82a80c365dce564bbd8d3dd4da4b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447119"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="c625e-104">Erstellen eines Microsoft Threat Protection-Testlabors oder einer Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="c625e-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c625e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c625e-105">**Applies to:**</span></span>
- <span data-ttu-id="c625e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c625e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c625e-107">Der Zweck der Erstellung dieser Test Labor-oder Pilotumgebung besteht darin, die umfassenden und integrierten Microsoft Threat Protection-Funktionen zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="c625e-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="c625e-108">Erfahren Sie, wie diese intelligente Sicherheitslösung erkannt, verhindert, automatisch untersucht und auf Erweiterte Bedrohungen Ihrer Organisation reagiert.</span><span class="sxs-lookup"><span data-stu-id="c625e-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="c625e-109">Dieses Handbuch führt Sie durch die Schritte zum Starten Ihrer Microsoft Threat Protection-Evaluierung basierend auf den empfohlenen Bereitstellungspfaden.</span><span class="sxs-lookup"><span data-stu-id="c625e-109">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="c625e-110">Das Ziel besteht darin, Sie bei der Einrichtung der Sicherheitslösung entweder in einer Testumgebung mit einem Test Konto oder in einer Pilotumgebung in der Produktion mit einer Vollversion zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c625e-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="c625e-111">Durch die Vorbereitung Ihrer Test Labor-oder Pilotumgebung können Sie Entscheidungsträgern in Ihrer Organisation bei der Vorgehensweise Sicherheitseinsatz-Anwendungsfällen helfen.</span><span class="sxs-lookup"><span data-stu-id="c625e-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="c625e-112">Wenn Sie die Angriffssimulationen ausgeführt haben und mit den Ergebnissen zufrieden sind, können Sie Sie in Ihrer Organisation mit Hilfe von technischen Microsoft-Vertriebsexperten oder Experten in Ihrer Organisation vollständig bereitstellen und in Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="c625e-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="c625e-113">Dieses Handbuch hilft Ihnen dabei:</span><span class="sxs-lookup"><span data-stu-id="c625e-113">This guide will help you:</span></span>
- <span data-ttu-id="c625e-114">Einrichten des Lab-Servers und der Computer</span><span class="sxs-lookup"><span data-stu-id="c625e-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="c625e-115">Konfigurieren von Active Directory mit Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="c625e-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="c625e-116">Einrichten und Konfigurieren von Azure ATP, Office ATP, Microsoft Defender ATP und Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c625e-116">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="c625e-117">Einrichten von lokalen Richtlinien für Ihren Server und ihre Computer</span><span class="sxs-lookup"><span data-stu-id="c625e-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="c625e-118">Simulieren eines Bedrohungs Angriffs zum Generieren eines Test Vorfalls oder einer Warnung in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c625e-118">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="c625e-119">Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen im Labor Setup so genau wie möglich.</span><span class="sxs-lookup"><span data-stu-id="c625e-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="c625e-120">Bereitstellungsphasen</span><span class="sxs-lookup"><span data-stu-id="c625e-120">Deployment phases</span></span>

<span data-ttu-id="c625e-121">Es gibt drei Phasen, in denen eine Microsoft Threat Protection-Testumgebung erstellt und bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="c625e-121">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="c625e-122">Phase</span><span class="sxs-lookup"><span data-stu-id="c625e-122">Phase</span></span> | <span data-ttu-id="c625e-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c625e-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="c625e-124">![Phase 1: Vorbereiten](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="c625e-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="c625e-125">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="c625e-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="c625e-126">Erfahren Sie, was Sie bei der Bereitstellung von Microsoft Threat Protection in einer Test Labor-oder Pilotumgebung berücksichtigen müssen:</span><span class="sxs-lookup"><span data-stu-id="c625e-126">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="c625e-127">-Stakeholder und Sign-Off</span><span class="sxs-lookup"><span data-stu-id="c625e-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="c625e-128">-Umgebungs Überlegungen</span><span class="sxs-lookup"><span data-stu-id="c625e-128">- Environment considerations</span></span> <br><span data-ttu-id="c625e-129">-Access</span><span class="sxs-lookup"><span data-stu-id="c625e-129">- Access</span></span> <br><span data-ttu-id="c625e-130">-Azure-Active Directory-Setup</span><span class="sxs-lookup"><span data-stu-id="c625e-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="c625e-131">-Konfigurations Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="c625e-131">- Configuration order</span></span>
|  <span data-ttu-id="c625e-132">![Phase 2: Setup](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="c625e-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="c625e-133">Phase 2: Setup</span><span class="sxs-lookup"><span data-stu-id="c625e-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="c625e-134">Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, um Ihre Microsoft Threat Protection-Testumgebung oder Pilotumgebung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="c625e-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="c625e-135">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="c625e-135">You'll be guided to:</span></span><br><br><span data-ttu-id="c625e-136">-Registrieren für Microsoft 365 E5-Testversion</span><span class="sxs-lookup"><span data-stu-id="c625e-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="c625e-137">-Domäne konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c625e-137">- Configure domain</span></span><br><span data-ttu-id="c625e-138">-Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="c625e-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="c625e-139">-Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="c625e-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="c625e-140">![Phase 3: Konfigurieren von & Onboard](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="c625e-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="c625e-141">Phase 3: Konfigurieren von & Onboard</span><span class="sxs-lookup"><span data-stu-id="c625e-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="c625e-142">Konfigurieren Sie die einzelnen Microsoft Threat Protection-Pfeiler und Onboard-Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="c625e-142">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="c625e-143">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="c625e-143">You'll be guided to:</span></span><br><br><span data-ttu-id="c625e-144">-Konfigurieren Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c625e-144">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="c625e-145">-Konfigurieren der Microsoft Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c625e-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="c625e-146">-Konfigurieren von Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c625e-146">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="c625e-147">-Konfigurieren von Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c625e-147">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="c625e-148">Im Bereich</span><span class="sxs-lookup"><span data-stu-id="c625e-148">In scope</span></span>

<span data-ttu-id="c625e-149">Die folgenden Aufgaben liegen im Bereich dieses Handbuchs:</span><span class="sxs-lookup"><span data-stu-id="c625e-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="c625e-150">Einrichten von Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c625e-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="c625e-151">Einrichten von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c625e-151">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="c625e-152">Registrieren Sie sich für die Microsoft 365 E5-Testversion, oder verwenden Sie Ihre vollständige Lizenz, wenn Sie ein Pilotprojekt betreiben.</span><span class="sxs-lookup"><span data-stu-id="c625e-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="c625e-153">Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="c625e-153">Configure domain</span></span>
    -   <span data-ttu-id="c625e-154">Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="c625e-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="c625e-155">Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="c625e-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="c625e-156">Konfigurieren aller Microsoft Threat Protection-Säulen basierend auf bewährten Methoden</span><span class="sxs-lookup"><span data-stu-id="c625e-156">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="c625e-157">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c625e-157">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="c625e-158">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c625e-158">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="c625e-159">Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c625e-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="c625e-160">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c625e-160">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="c625e-161">Nicht inbegriffen</span><span class="sxs-lookup"><span data-stu-id="c625e-161">Out of scope</span></span>

<span data-ttu-id="c625e-162">Im Rahmen dieses Bereitstellungshandbuchs liegen folgende Schritte vor:</span><span class="sxs-lookup"><span data-stu-id="c625e-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="c625e-163">Konfiguration von Drittanbieterlösungen, die sich möglicherweise in Microsoft Threat Protection integrieren lassen</span><span class="sxs-lookup"><span data-stu-id="c625e-163">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="c625e-164">Penetrationstests in der Produktionsumgebung</span><span class="sxs-lookup"><span data-stu-id="c625e-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="c625e-165">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c625e-165">Next step</span></span>
<span data-ttu-id="c625e-166">![Phase 1: Vorbereiten](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="c625e-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="c625e-167">[Phase 1: Vorbereiten](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="c625e-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="c625e-168">Vorbereiten Ihrer Testlabor-oder Pilotumgebung für den Microsoft Threat Protection-Test</span><span class="sxs-lookup"><span data-stu-id="c625e-168">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
