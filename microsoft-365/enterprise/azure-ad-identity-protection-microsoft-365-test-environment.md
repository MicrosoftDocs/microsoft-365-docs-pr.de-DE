---
title: Azure AD-Schutz für Ihr Unternehmen der Microsoft 365 test Environment.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren von Azure AD-Schutz und analysieren Sie die aktuellen Konten in Ihrer testumgebung Microsoft 365 Enterprise.
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867643"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d7359-103">Azure AD-Schutz für Ihr Unternehmen der Microsoft 365 test Environment.</span><span class="sxs-lookup"><span data-stu-id="d7359-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d7359-p101">Azure AD-Schutz können Sie Identitäten Ihrer Organisation beeinflussen potenzielle Sicherheitsrisiken zu erkennen, konfigurieren Automatische Antworten und untersuchen Vorfälle. In diesem Artikel wird beschrieben, wie zum Aktivieren von Azure AD-Schutz und die Analyse von Ihrer Umgebung Testkonten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d7359-p101">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents. This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="d7359-106">Es gibt zwei Phasen Azure AD-Schutz in Ihrer Microsoft 365 Enterprise-testumgebung einrichten:</span><span class="sxs-lookup"><span data-stu-id="d7359-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="d7359-107">Erstellen der testumgebung Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d7359-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="d7359-108">Aktivieren und Azure Active Directory-Identität Protection verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7359-108">Enable and use Azure AD Identity Protection.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="d7359-110">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d7359-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d7359-111">Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d7359-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d7359-112">Wenn Sie Azure AD-Schutz auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d7359-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d7359-113">Wenn Sie in einer simulierten Enterprise Azure AD-Schutz testen möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d7359-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d7359-p102">Testen von Azure AD-Schutz erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit können Sie Azure AD-Schutz testen und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="d7359-p102">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="d7359-116">Phase 2: Aktivieren und Verwenden von Azure AD-Schutz</span><span class="sxs-lookup"><span data-stu-id="d7359-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="d7359-117">Öffnen Sie eine private Instanz des Browsers, und melden Sie sich bei der Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit dem globalen Administratorkonto der Umgebung testen Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d7359-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="d7359-118">Klicken Sie in der Azure-Portal auf **alle Dienste > Marketplace**.</span><span class="sxs-lookup"><span data-stu-id="d7359-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="d7359-119">Geben Sie **Azure AD-Schutz** , und klicken Sie dann auf.</span><span class="sxs-lookup"><span data-stu-id="d7359-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="d7359-120">Klicken Sie in die **Erste Schritte** Blade unter **Einstellungen**auf **Onboard** , klicken Sie auf **Pin Dashboard**und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d7359-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="d7359-121">Klicken Sie im Azure-Portal **Azure AD-Schutz** auf das Dashboard.</span><span class="sxs-lookup"><span data-stu-id="d7359-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="d7359-p103">Ein **Azure AD Identity Protection-Overview** Blade mit einem Dashboard sollte angezeigt werden. Beachten Sie unter **Sicherheitsrisiken**bestimmt die Anzahl der Benutzerkonten ohne Multi-Factor Authentication-Registrierung. Diese Zahl variiert je nach auf vorherigen Microsoft 365 Enterprise Test Lab Guides, die Sie getan haben.</span><span class="sxs-lookup"><span data-stu-id="d7359-p103">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard. Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration. This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="d7359-125">Klicken Sie auf die Kategorien für **untersuchen** , um festzustellen, ob Benutzer oder Ereignisse, die gefunden wurden vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d7359-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="d7359-126">Weitere Tests und experimentieren finden Sie unter [Simulating Risikoereignisse](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="d7359-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="d7359-127">Finden Sie unter der [Schutz vor Anmeldeinformationen gefährden](identity-azure-ad-identity-protection.md) Schritt in der Phase Identität Informationen und Links zu Azure AD-Schutz in der Produktion bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d7359-127">See the [Protect against credential compromise](identity-azure-ad-identity-protection.md) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="d7359-128">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d7359-128">Next step</span></span>

<span data-ttu-id="d7359-129">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="d7359-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7359-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7359-130">See also</span></span>

[<span data-ttu-id="d7359-131">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="d7359-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="d7359-132">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d7359-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d7359-133">Bereitstellung von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d7359-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d7359-134">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d7359-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
