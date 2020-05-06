---
title: Auswerten von Microsoft Threat Protection
description: Richten Sie Ihre Microsoft Threat Protection-Testumgebung ein, um zu testen, wie die koordinierte Bedrohungsschutz Lösung zum Schutz von Geräten, Identitäten, Daten und Anwendungen Ihrer Organisation helfen kann.
keywords: Microsoft Threat Protection-Testversion, testen Sie Microsoft Threat Protection, bewerten Sie Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab, Cyber Security, Advanced persistent Threat, Enterprise Security, Devices, Device, Identity, users, Data, Applications, Incidents, Automated Investigation and Remediation, Advanced Hunting
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
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049639"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="6d33b-104">Erstellen einer Microsoft Threat Protection-Testlaborumgebung</span><span class="sxs-lookup"><span data-stu-id="6d33b-104">Create a Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="6d33b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6d33b-105">**Applies to:**</span></span>
- <span data-ttu-id="6d33b-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6d33b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6d33b-107">Der Zweck der Erstellung dieser Testlaborumgebung besteht darin, die umfassenden, integrierten und intelligenten Funktionen von Microsoft Threat Protection in Erkennung, Verhinderung, Untersuchung und Antwort zu veranschaulichen, die Sie in Ihrer Organisation verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6d33b-107">The purpose of creating this trial lab environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="6d33b-108">Dieses Handbuch führt Sie durch die Schritte zum Starten Ihrer Microsoft Threat Protection-Evaluierung basierend auf den empfohlenen Bereitstellungspfaden.</span><span class="sxs-lookup"><span data-stu-id="6d33b-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="6d33b-109">Das Ziel besteht darin, Sie beim Einrichten der integrierten Microsoft Threat Protection-Dienste in einer Testumgebung oder als Machbarkeitsstudie zu unterstützen, wenn Sie Entscheidungsträgern in Ihrer Organisation Sicherheitslösungen präsentieren.</span><span class="sxs-lookup"><span data-stu-id="6d33b-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment or as a proof of concept (POC) when presenting to security solution decision makers in your organization.</span></span> <span data-ttu-id="6d33b-110">Wenn Sie die Angriffssimulationen, die automatische Untersuchung und die Antwort ausgeführt haben und mit den Ergebnissen zufrieden sind, können Sie Sie in Ihrer Produktionsumgebung mit Hilfe von Microsoft Technical Sales-Experten oder Experten in Ihrer Organisation bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6d33b-110">When you’re done running your attack simulations, automated investigation and response, and are satisfied with the results, you can deploy it in your production environment with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="6d33b-111">Dieses Handbuch hilft Ihnen dabei:</span><span class="sxs-lookup"><span data-stu-id="6d33b-111">This guide will help you:</span></span>
- <span data-ttu-id="6d33b-112">Einrichten des Lab-Servers und der Computer</span><span class="sxs-lookup"><span data-stu-id="6d33b-112">Set up your lab server and computers</span></span>
- <span data-ttu-id="6d33b-113">Konfigurieren von Active Directory mit Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="6d33b-113">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="6d33b-114">Einrichten und Konfigurieren von Azure ATP, Office ATP, Microsoft Defender ATP und Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6d33b-114">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="6d33b-115">Einrichten von lokalen Richtlinien für Ihren Server und ihre Computer</span><span class="sxs-lookup"><span data-stu-id="6d33b-115">Setup local policies for your server and computers</span></span>
- <span data-ttu-id="6d33b-116">Simulieren eines Bedrohungs Angriffs zum Generieren eines Test Vorfalls oder einer Warnung in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6d33b-116">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="6d33b-117">Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen im Labor Setup so genau wie möglich.</span><span class="sxs-lookup"><span data-stu-id="6d33b-117">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="6d33b-118">Bereitstellungsphasen</span><span class="sxs-lookup"><span data-stu-id="6d33b-118">Deployment phases</span></span>

<span data-ttu-id="6d33b-119">Es gibt drei Phasen, in denen eine Microsoft Threat Protection-Testumgebung erstellt und bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="6d33b-119">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="6d33b-120">Phase</span><span class="sxs-lookup"><span data-stu-id="6d33b-120">Phase</span></span> | <span data-ttu-id="6d33b-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d33b-121">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="6d33b-122">![Phase 1: Vorbereiten](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="6d33b-122">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="6d33b-123">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="6d33b-123">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="6d33b-124">Erfahren Sie, was Sie bei der Bereitstellung von Microsoft Threat Protection in einer Testlaborumgebung berücksichtigen müssen:</span><span class="sxs-lookup"><span data-stu-id="6d33b-124">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab environment:</span></span> <br><br><span data-ttu-id="6d33b-125">-Stakeholder und Sign-Off</span><span class="sxs-lookup"><span data-stu-id="6d33b-125">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="6d33b-126">-Umgebungs Überlegungen</span><span class="sxs-lookup"><span data-stu-id="6d33b-126">- Environment considerations</span></span> <br><span data-ttu-id="6d33b-127">-Access</span><span class="sxs-lookup"><span data-stu-id="6d33b-127">- Access</span></span> <br><span data-ttu-id="6d33b-128">-Azure-Active Directory-Setup</span><span class="sxs-lookup"><span data-stu-id="6d33b-128">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="6d33b-129">-Konfigurations Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="6d33b-129">- Configuration order</span></span>
|  <span data-ttu-id="6d33b-130">![Phase 2: Setup](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="6d33b-130">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="6d33b-131">Phase 2: Setup</span><span class="sxs-lookup"><span data-stu-id="6d33b-131">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="6d33b-132">Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, um Ihre Microsoft Threat Protection-Test Umgebungsumgebung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="6d33b-132">Take the initial steps to access Microsoft 365 Security Center to setup your Microsoft Threat Protection trial lab environment.</span></span> <span data-ttu-id="6d33b-133">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="6d33b-133">You will be guided to:</span></span><br><br><span data-ttu-id="6d33b-134">-Registrieren für Microsoft 365 E5-Testversion</span><span class="sxs-lookup"><span data-stu-id="6d33b-134">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="6d33b-135">-Domäne konfigurieren</span><span class="sxs-lookup"><span data-stu-id="6d33b-135">- Configure domain</span></span><br><span data-ttu-id="6d33b-136">-Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="6d33b-136">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="6d33b-137">-Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="6d33b-137">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="6d33b-138">![Phase 3: Konfigurieren von & Onboard](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="6d33b-138">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="6d33b-139">Phase 3: Konfigurieren von & Onboard</span><span class="sxs-lookup"><span data-stu-id="6d33b-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="6d33b-140">Konfigurieren Sie die einzelnen Microsoft Threat Protection-Pfeiler und Onboard-Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="6d33b-140">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="6d33b-141">Sie werden zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="6d33b-141">You will be guided to:</span></span><br><br><span data-ttu-id="6d33b-142">-Konfigurieren Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6d33b-142">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="6d33b-143">-Konfigurieren der Microsoft Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6d33b-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="6d33b-144">-Konfigurieren von Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6d33b-144">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="6d33b-145">-Konfigurieren von Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6d33b-145">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="6d33b-146">Im Bereich</span><span class="sxs-lookup"><span data-stu-id="6d33b-146">In scope</span></span>

<span data-ttu-id="6d33b-147">Im folgenden finden Sie einen Bereich für dieses Test Lab-Umgebungs Handbuch:</span><span class="sxs-lookup"><span data-stu-id="6d33b-147">The following is in scope for this trial lab environment guide:</span></span>
-   <span data-ttu-id="6d33b-148">Einrichten von Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6d33b-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="6d33b-149">Einrichten von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6d33b-149">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="6d33b-150">Registrieren für Microsoft 365 E5-Testversion</span><span class="sxs-lookup"><span data-stu-id="6d33b-150">Sign up for Microsoft 365 E5 Trial</span></span>
    -   <span data-ttu-id="6d33b-151">Konfigurieren der Domäne</span><span class="sxs-lookup"><span data-stu-id="6d33b-151">Configure domain</span></span>
    -   <span data-ttu-id="6d33b-152">Zuweisen von Microsoft 365 E5-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="6d33b-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="6d33b-153">Abschließen des Setup-Assistenten im Portal</span><span class="sxs-lookup"><span data-stu-id="6d33b-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="6d33b-154">Konfigurieren aller Microsoft Threat Protection-Säulen basierend auf bewährten Methoden</span><span class="sxs-lookup"><span data-stu-id="6d33b-154">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="6d33b-155">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6d33b-155">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="6d33b-156">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6d33b-156">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="6d33b-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6d33b-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="6d33b-158">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6d33b-158">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="6d33b-159">Nicht inbegriffen</span><span class="sxs-lookup"><span data-stu-id="6d33b-159">Out of scope</span></span>

<span data-ttu-id="6d33b-160">Im Rahmen dieses Bereitstellungshandbuchs liegen folgende Schritte vor:</span><span class="sxs-lookup"><span data-stu-id="6d33b-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="6d33b-161">Konfiguration von Drittanbieterlösungen, die in Microsoft Defender ATP integriert werden können</span><span class="sxs-lookup"><span data-stu-id="6d33b-161">Configuration of third-party solutions that might integrate with Microsoft Defender ATP</span></span>
-   <span data-ttu-id="6d33b-162">Penetrationstests in der Produktionsumgebung</span><span class="sxs-lookup"><span data-stu-id="6d33b-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="6d33b-163">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="6d33b-163">Next step</span></span>
|||
|:-------|:-----|
|<span data-ttu-id="6d33b-164">![Phase 1: Vorbereiten](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="6d33b-164">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="6d33b-165">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="6d33b-165">Phase 1: Prepare</span></span>](prepare-mtpeval.md) | <span data-ttu-id="6d33b-166">Vorbereiten der Microsoft Threat Protection-Evaluierungslabor Umgebung</span><span class="sxs-lookup"><span data-stu-id="6d33b-166">Prepare your Microsoft Threat Protection evaluation lab environment</span></span>
