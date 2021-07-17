---
title: Pilot-Microsoft Cloud App Security mit Microsoft 365 Defender, Erstellen von Pilotgruppen, Konfigurieren der Steuerung des bedingten Zugriffs, Testen von Funktionen, Einrichten im Rahmen Microsoft 365 Defender
description: Richten Sie Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung ein, um die Sicherheitslösung zum Schutz von Geräten, Identität, Daten und Anwendungen zu testen und zu testen.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e061bf213ee929f91a48b03c71b9654a7ea76b8c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458048"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a><span data-ttu-id="a5f53-103">Pilot-Microsoft Cloud App Security mit Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5f53-103">Pilot Microsoft Cloud App Security with Microsoft 365 Defender</span></span>


<span data-ttu-id="a5f53-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a5f53-104">**Applies to:**</span></span>
- <span data-ttu-id="a5f53-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5f53-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="a5f53-106">Dieser Artikel ist [Schritt 3 von 3](eval-defender-mcas-overview.md) beim Einrichten der Evaluierungsumgebung für Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="a5f53-106">This article is [Step 3 of 3](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="a5f53-107">Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a5f53-107">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="a5f53-108">Führen Sie die folgenden Schritte aus, um das Pilotprojekt für Microsoft Cloud App Security einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a5f53-108">Use the following steps to setup and configure the pilot for Microsoft Cloud App Security.</span></span>


![Schritte für pilotierende Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-pilot-steps.png)

- <span data-ttu-id="a5f53-110">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="a5f53-110">Step 1.</span></span> [<span data-ttu-id="a5f53-111">Erstellen der Pilotgruppe – Einschränken der Pilotbereitstellung auf bestimmte Benutzergruppen</span><span class="sxs-lookup"><span data-stu-id="a5f53-111">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [<span data-ttu-id="a5f53-112">Schritt 2. Konfigurieren des Schutzes – App-Steuerung für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="a5f53-112">Step 2. Configure protection — Conditional Access App Control</span></span>](#step-2-configure-protection--conditional-access-app-control)
- [<span data-ttu-id="a5f53-113">Schritt 3. Testen von Funktionen – Exemplarische Lernprogramme zum Schutz Ihrer Umgebung</span><span class="sxs-lookup"><span data-stu-id="a5f53-113">Step 3. Try out capabilities — Walk through tutorials for protecting your environment</span></span>](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a><span data-ttu-id="a5f53-114">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="a5f53-114">Step 1.</span></span> <span data-ttu-id="a5f53-115">Erstellen der Pilotgruppe – Einschränken der Pilotbereitstellung auf bestimmte Benutzergruppen</span><span class="sxs-lookup"><span data-stu-id="a5f53-115">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>

<span data-ttu-id="a5f53-116">mit Microsoft Cloud App Security können Sie die Bereitstellung einschränken.</span><span class="sxs-lookup"><span data-stu-id="a5f53-116">Microsoft Cloud App Security enables you to scope your deployment.</span></span> <span data-ttu-id="a5f53-117">Mit der Bereichsdefinition können Sie bestimmte Benutzergruppen auswählen, die für Apps überwacht oder von der Überwachung ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a5f53-117">Scoping allows you to select certain user groups to be monitored for apps or excluded from monitoring.</span></span> <span data-ttu-id="a5f53-118">Sie können Benutzergruppen einschließen oder ausschließen.</span><span class="sxs-lookup"><span data-stu-id="a5f53-118">You can include or exclude user groups.</span></span> <span data-ttu-id="a5f53-119">Informationen zum Umfang der Pilotbereitstellung finden Sie unter ["Bereichsbereitstellung".](/cloud-app-security/scoped-deployment)</span><span class="sxs-lookup"><span data-stu-id="a5f53-119">To scope your pilot deployment, see [Scoped Deployment](/cloud-app-security/scoped-deployment).</span></span>


## <a name="step-2-configure-protection--conditional-access-app-control"></a><span data-ttu-id="a5f53-120">Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="a5f53-120">Step 2.</span></span> <span data-ttu-id="a5f53-121">Konfigurieren des Schutzes – App-Steuerung für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="a5f53-121">Configure protection — Conditional Access App Control</span></span>

<span data-ttu-id="a5f53-122">Einer der leistungsstärksten Schutzmaßnahmen, die Sie konfigurieren können, ist die App-Steuerung für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="a5f53-122">One of the most powerful protections you can configure is Conditional Access App Control.</span></span> <span data-ttu-id="a5f53-123">Dies erfordert die Integration in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a5f53-123">This requires integration with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="a5f53-124">Damit können Sie Richtlinien für bedingten Zugriff, einschließlich verwandter Richtlinien (z. B. das Anfordern von fehlerfreien Geräten), auf Cloud-Apps anwenden, die Sie sanktioniert haben.</span><span class="sxs-lookup"><span data-stu-id="a5f53-124">It allows you to apply Conditional Access policies, including related policies (like requiring healthy devices), to cloud apps you've sanctioned.</span></span> 

<span data-ttu-id="a5f53-125">Der erste Schritt bei der Verwendung von Microsoft Cloud App Security zum Verwalten von SaaS-Apps besteht darin, diese zu ermitteln und dann Ihrem Azure AD-Mandanten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a5f53-125">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="a5f53-126">Wenn Sie Hilfe bei der Ermittlung benötigen, lesen [Sie "Entdecken und Verwalten von SaaS-Apps in Ihrem Netzwerk".](/cloud-app-security/tutorial-shadow-it)</span><span class="sxs-lookup"><span data-stu-id="a5f53-126">If you need help with discovery, see [Discover and manage SaaS apps in your network](/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="a5f53-127">Nachdem Sie Apps entdeckt haben, [fügen Sie diese Ihrem Azure AD-Mandanten hinzu.](/azure/active-directory/manage-apps/add-application-portal)</span><span class="sxs-lookup"><span data-stu-id="a5f53-127">After you've discovered apps, [add these to your Azure AD tenant](/azure/active-directory/manage-apps/add-application-portal).</span></span>

<span data-ttu-id="a5f53-128">Sie können beginnen, diese zu verwalten, indem Sie folgendermaßen vorgehen:</span><span class="sxs-lookup"><span data-stu-id="a5f53-128">You can begin to manage these by doing the following:</span></span>

- <span data-ttu-id="a5f53-129">Erstellen Sie zunächst in Azure AD eine neue Richtlinie für bedingten Zugriff, und konfigurieren Sie sie für "App-Steuerung für bedingten Zugriff verwenden".</span><span class="sxs-lookup"><span data-stu-id="a5f53-129">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="a5f53-130">Dadurch wird die Anforderung an Cloud App Security weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a5f53-130">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="a5f53-131">Sie können eine Richtlinie erstellen und dieser Richtlinie alle SaaS-Apps hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a5f53-131">You can create one policy and add all SaaS apps to this policy.</span></span>
- <span data-ttu-id="a5f53-132">Erstellen Sie als Nächstes in Cloud App Security Sitzungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="a5f53-132">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="a5f53-133">Erstellen Sie eine Richtlinie für jedes Steuerelement, das Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a5f53-133">Create one policy for each control you want to apply.</span></span>

<span data-ttu-id="a5f53-134">Weitere Informationen, einschließlich unterstützter Apps und Clients, finden Sie unter ["Schützen von Apps mit Microsoft Cloud App Security App-Steuerung für bedingten Zugriff".](/cloud-app-security/proxy-intro-aad)</span><span class="sxs-lookup"><span data-stu-id="a5f53-134">For more information, including supported apps and clients, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).</span></span> 

<span data-ttu-id="a5f53-135">Beispiele für Richtlinien finden Sie unter ["Empfohlene Microsoft Cloud App Security Richtlinien für SaaS-Apps".](../office-365-security/mcas-saas-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a5f53-135">For example policies, see [Recommended Microsoft Cloud App Security policies for SaaS apps](../office-365-security/mcas-saas-access-policies.md).</span></span> <span data-ttu-id="a5f53-136">Diese Richtlinien basieren auf einer Reihe [allgemeiner Identitäts- und Gerätezugriffsrichtlinien,](../office-365-security/microsoft-365-policies-configurations.md) die als Ausgangspunkt für alle Kunden empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="a5f53-136">These policies build on a set of [common identity and device access policies](../office-365-security/microsoft-365-policies-configurations.md) that are recommended as a starting point for all customers.</span></span> 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a><span data-ttu-id="a5f53-137">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="a5f53-137">Step 3.</span></span> <span data-ttu-id="a5f53-138">Testen von Funktionen – Exemplarische Lernprogramme zum Schutz Ihrer Umgebung</span><span class="sxs-lookup"><span data-stu-id="a5f53-138">Try out capabilities — Walk through tutorials for protecting your environment</span></span> 

<span data-ttu-id="a5f53-139">Die Microsoft Cloud App Security Dokumentation enthält eine Reihe von Lernprogrammen, die Ihnen helfen, Risiken zu erkennen und Ihre Umgebung zu schützen.</span><span class="sxs-lookup"><span data-stu-id="a5f53-139">The Microsoft Cloud App Security documentation includes a series of tutorials to help you discover risk and protect your environment.</span></span> 

<span data-ttu-id="a5f53-140">Testen Sie Cloud App Security Lernprogramme:</span><span class="sxs-lookup"><span data-stu-id="a5f53-140">Try out Cloud App Security tutorials:</span></span>

- [<span data-ttu-id="a5f53-141">Erkennen verdächtiger Benutzeraktivitäten</span><span class="sxs-lookup"><span data-stu-id="a5f53-141">Detect suspicious user activity</span></span>](/cloud-app-security/tutorial-suspicious-activity)
- [<span data-ttu-id="a5f53-142">Untersuchen riskanter Benutzer</span><span class="sxs-lookup"><span data-stu-id="a5f53-142">Investigate risky users</span></span>](/cloud-app-security/tutorial-ueba)
- [<span data-ttu-id="a5f53-143">Untersuchen riskanter OAuth-Apps</span><span class="sxs-lookup"><span data-stu-id="a5f53-143">Investigate risky OAuth apps</span></span>](/cloud-app-security/investigate-risky-oauth)
- [<span data-ttu-id="a5f53-144">Ermitteln und Schützen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="a5f53-144">Discover and protect sensitive information</span></span>](/cloud-app-security/tutorial-dlp)
- [<span data-ttu-id="a5f53-145">Schützen von Apps in Ihrer Organisation in Echtzeit</span><span class="sxs-lookup"><span data-stu-id="a5f53-145">Protect any app in your organization in real time</span></span>](/cloud-app-security/tutorial-proxy)
- [<span data-ttu-id="a5f53-146">Blockieren von Downloads vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="a5f53-146">Block downloads of sensitive information</span></span>](/cloud-app-security/use-case-proxy-block-session-aad)
- [<span data-ttu-id="a5f53-147">Schützen Ihrer Dateien mit Administratorquarantäne</span><span class="sxs-lookup"><span data-stu-id="a5f53-147">Protect your files with admin quarantine</span></span>](/cloud-app-security/use-case-admin-quarantine)
- [<span data-ttu-id="a5f53-148">Erfordert eine schrittweise Authentifizierung bei riskanten Aktionen</span><span class="sxs-lookup"><span data-stu-id="a5f53-148">Require step-up authentication upon risky action</span></span>](/cloud-app-security/tutorial-step-up-authentication)

## <a name="next-steps"></a><span data-ttu-id="a5f53-149">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a5f53-149">Next steps</span></span>

[<span data-ttu-id="a5f53-150">Untersuchen und Reagieren mithilfe von Microsoft 365 Defender in einer Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="a5f53-150">Investigate and respond using Microsoft 365 Defender in a pilot environment</span></span>](eval-defender-investigate-respond.md)

<span data-ttu-id="a5f53-151">Kehren Sie zur Übersicht für ["Auswerten Microsoft Cloud App Security"](eval-defender-mcas-overview.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="a5f53-151">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="a5f53-152">Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a5f53-152">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>