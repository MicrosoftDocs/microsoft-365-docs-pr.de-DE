---
title: Microsoft Threat Protection evaluieren
description: Richten Sie Ihr Microsoft Threat Protection-Test Labor oder Ihre Pilotumgebung ein, um zu testen, wie die koordinierte Bedrohungsschutz Lösung zum Schutz von Geräten, Identitäten, Daten und Anwendungen Ihrer Organisation helfen kann.
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 202a5900dedece865f1aa328735477293a8a19c0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201771"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="90299-104">Erstellen eines Microsoft Threat Protection-Testlabors oder einer Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="90299-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="90299-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="90299-105">**Applies to:**</span></span>
- <span data-ttu-id="90299-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90299-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="90299-107">Der Zweck der Erstellung dieser Test Labor-oder Pilotumgebung besteht darin, die umfassenden, integrierten und intelligenten Funktionen von Microsoft Threat Protection in Erkennung, Verhinderung, Untersuchung und Antwort zu veranschaulichen, die Sie in Ihrer Organisation verwenden können.</span><span class="sxs-lookup"><span data-stu-id="90299-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="90299-108">Dieses Handbuch führt Sie durch die Schritte zum Starten Ihrer Microsoft Threat Protection-Evaluierung basierend auf den empfohlenen Bereitstellungspfaden.</span><span class="sxs-lookup"><span data-stu-id="90299-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="90299-109">Das Ziel besteht darin, Sie beim Einrichten der integrierten Microsoft Threat Protection-Dienste in einer Testumgebung bei der Verwendung eines Testkontos oder in einer Pilotumgebung in der Produktion bei Verwendung einer Vollversion zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="90299-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment when using a trial account, or in a pilot environment in production when using a full license.</span></span> <span data-ttu-id="90299-110">Die Ergebnisse von sind hilfreich bei der Darstellung von Sicherheitseinsatz-Anwendungsfällen für Entscheidungsträger der Sicherheitslösung in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="90299-110">The results of which will be useful in presenting security operation use cases to security solution decision makers in your organization.</span></span> <span data-ttu-id="90299-111">Wenn Sie die Angriffssimulationen ausgeführt haben und mit den Ergebnissen zufrieden sind, können Sie Sie in Ihrer Organisation mit Hilfe von technischen Microsoft-Vertriebsexperten oder Experten in Ihrer Organisation vollständig bereitstellen und in Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="90299-111">When you’re done running your attack simulations, and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="90299-112">Dieses Handbuch hilft Ihnen dabei:</span><span class="sxs-lookup"><span data-stu-id="90299-112">This guide will help you:</span></span>
- <span data-ttu-id="90299-113">Einrichten des Lab-Servers und der Computer</span><span class="sxs-lookup"><span data-stu-id="90299-113">Set up your lab server and computers</span></span>
- <span data-ttu-id="90299-114">Konfigurieren von Active Directory mit Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="90299-114">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="90299-115">Einrichten und Konfigurieren von Azure ATP, Office ATP, Microsoft Defender ATP und Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="90299-115">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="90299-116">Einrichten von lokalen Richtlinien für Ihren Server und ihre Computer</span><span class="sxs-lookup"><span data-stu-id="90299-116">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="90299-117">Simulieren eines Bedrohungs Angriffs zum Generieren eines Test Vorfalls oder einer Warnung in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90299-117">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="90299-118">Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen im Labor Setup so genau wie möglich.</span><span class="sxs-lookup"><span data-stu-id="90299-118">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="90299-119">Bereitstellungsphasen</span><span class="sxs-lookup"><span data-stu-id="90299-119">Deployment phases</span></span>

<span data-ttu-id="90299-120">Es gibt drei Phasen, in denen eine Microsoft Threat Protection-Testumgebung erstellt und bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="90299-120">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="90299-121">Phase</span><span class="sxs-lookup"><span data-stu-id="90299-121">Phase</span></span> | <span data-ttu-id="90299-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90299-122">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="90299-123">![Phase 1: Vorbereiten](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="90299-123">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="90299-124">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="90299-124">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="90299-125">Erfahren Sie, was Sie bei der Bereitstellung von Microsoft Threat Protection in einer Test Labor-oder Pilotumgebung berücksichtigen müssen:</span><span class="sxs-lookup"><span data-stu-id="90299-125">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="90299-126">-Stakeholder und Sign-Off</span><span class="sxs-lookup"><span data-stu-id="90299-126">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="90299-127">-Umgebungs Überlegungen</span><span class="sxs-lookup"><span data-stu-id="90299-127">- Environment considerations</span></span> <br><span data-ttu-id="90299-128">-Access</span><span class="sxs-lookup"><span data-stu-id="90299-128">- Access</span></span> <br><span data-ttu-id="90299-129">-Azure-Active Directory-Setup</span><span class="sxs-lookup"><span data-stu-id="90299-129">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="90299-130">-Konfigurations Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="90299-130">- Configuration order</span></span>
|  <span data-ttu-id="90299-131">![Phase 2: Setup](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="90299-131">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="90299-132">Phase 2: Setup</span><span class="sxs-lookup"><span data-stu-id="90299-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="90299-133">Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, um Ihre Microsoft Threat Protection-Testumgebung oder Pilotumgebung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="90299-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="90299-134">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="90299-134">You'll be guided to:</span></span><br><br><span data-ttu-id="90299-135">-Registrieren für Microsoft 365 E5-Testversion</span><span class="sxs-lookup"><span data-stu-id="90299-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="90299-136">-Domäne konfigurieren</span><span class="sxs-lookup"><span data-stu-id="90299-136">- Configure domain</span></span><br><span data-ttu-id="90299-137">-Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="90299-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="90299-138">-Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="90299-138">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="90299-139">![Phase 3: Konfigurieren von & Onboard](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="90299-139">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="90299-140">Phase 3: Konfigurieren von & Onboard</span><span class="sxs-lookup"><span data-stu-id="90299-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="90299-141">Konfigurieren Sie die einzelnen Microsoft Threat Protection-Pfeiler und Onboard-Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="90299-141">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="90299-142">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="90299-142">You'll be guided to:</span></span><br><br><span data-ttu-id="90299-143">-Konfigurieren Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90299-143">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="90299-144">-Konfigurieren der Microsoft Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="90299-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="90299-145">-Konfigurieren von Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90299-145">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="90299-146">-Konfigurieren von Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90299-146">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="90299-147">Im Bereich</span><span class="sxs-lookup"><span data-stu-id="90299-147">In scope</span></span>

<span data-ttu-id="90299-148">Die folgenden Aufgaben liegen im Bereich dieses Handbuchs:</span><span class="sxs-lookup"><span data-stu-id="90299-148">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="90299-149">Einrichten von Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="90299-149">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="90299-150">Einrichten von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90299-150">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="90299-151">Registrieren Sie sich für die Microsoft 365 E5-Testversion, oder verwenden Sie Ihre vollständige Lizenz, wenn Sie ein Pilotprojekt betreiben.</span><span class="sxs-lookup"><span data-stu-id="90299-151">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="90299-152">Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="90299-152">Configure domain</span></span>
    -   <span data-ttu-id="90299-153">Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="90299-153">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="90299-154">Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="90299-154">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="90299-155">Konfigurieren aller Microsoft Threat Protection-Säulen basierend auf bewährten Methoden</span><span class="sxs-lookup"><span data-stu-id="90299-155">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="90299-156">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90299-156">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="90299-157">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90299-157">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="90299-158">Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="90299-158">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="90299-159">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90299-159">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="90299-160">Nicht inbegriffen</span><span class="sxs-lookup"><span data-stu-id="90299-160">Out of scope</span></span>

<span data-ttu-id="90299-161">Im Rahmen dieses Bereitstellungshandbuchs liegen folgende Schritte vor:</span><span class="sxs-lookup"><span data-stu-id="90299-161">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="90299-162">Konfiguration von Drittanbieterlösungen, die sich möglicherweise in Microsoft Threat Protection integrieren lassen</span><span class="sxs-lookup"><span data-stu-id="90299-162">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="90299-163">Penetrationstests in der Produktionsumgebung</span><span class="sxs-lookup"><span data-stu-id="90299-163">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="90299-164">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="90299-164">Next step</span></span>
<span data-ttu-id="90299-165">![Phase 1: Vorbereiten](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="90299-165">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="90299-166">[Phase 1: Vorbereiten](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="90299-166">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="90299-167">Vorbereiten Ihrer Testlabor-oder Pilotumgebung für den Microsoft Threat Protection-Test</span><span class="sxs-lookup"><span data-stu-id="90299-167">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
