---
title: Azure AD Identitätsschutz für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie Azure AD Identitätsschutz, und analysieren Sie die aktuellen Konten in Ihrer Microsoft 365 Enterprise-Testumgebung.
ms.openlocfilehash: a21b20f4ca774ad38990e44abc18d666426e74d5
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640404"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b9e9d-103">Azure AD Identitätsschutz für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="b9e9d-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b9e9d-104">Mit Azure AD Identity Protection können Sie potenzielle Sicherheitsrisiken erkennen, die sich auf die Identitäten Ihrer Organisation auswirken, automatisierte Antworten konfigurieren und Vorfälle untersuchen.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-104">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="b9e9d-105">In diesem Artikel wird beschrieben, wie Sie Azure AD Identitätsschutz aktivieren und die Analyse Ihrer Test Umgebungs Konten anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-105">This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="b9e9d-106">Es gibt zwei Phasen zum Einrichten Azure AD Identitätsschutzes in Ihrer Microsoft 365 Enterprise-Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="b9e9d-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="b9e9d-107">Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="b9e9d-108">Aktivieren und verwenden Sie Azure AD Identity Protection.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-108">Enable and use Azure AD Identity Protection.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b9e9d-110">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-110">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b9e9d-111">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="b9e9d-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b9e9d-112">Wenn Sie Azure AD Identitätsschutz nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="b9e9d-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b9e9d-113">Wenn Sie Azure AD Identitätsschutz in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b9e9d-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9e9d-114">Für das Testen Azure AD Identitätsschutzes ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-114">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b9e9d-115">Sie wird hier als Option bereitgestellt, damit Sie Azure AD Identitätsschutz testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-115">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="b9e9d-116">Phase 2: Aktivieren und Verwenden von Azure AD Identitätsschutz</span><span class="sxs-lookup"><span data-stu-id="b9e9d-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="b9e9d-117">Öffnen Sie eine private Instanz Ihres Browsers, und melden Sie sich beim Azure- [https://portal.azure.com](https://portal.azure.com) Portal unter mit dem globalen Administratorkonto Ihrer Microsoft 365 Enterprise-Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="b9e9d-118">Klicken Sie im Azure-Portal auf **alle Dienste #a0 Marketplace**.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="b9e9d-119">Geben Sie **Azure AD Identitätsschutz** ein, und klicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="b9e9d-120">Klicken Sie auf dem Blade **Erste Schritte** unter **Einstellungen**auf **Onboard** , klicken Sie auf **an Dashboard anheften**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="b9e9d-121">Klicken Sie im Azure-Portal im Dashboard auf **Azure AD Identitätsschutz** .</span><span class="sxs-lookup"><span data-stu-id="b9e9d-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="b9e9d-122">Es sollte ein **Azure AD-Blatt mit Identitätsschutz – Übersicht** mit einem Dashboard angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-122">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard.</span></span> <span data-ttu-id="b9e9d-123">Beachten Sie bei **Sicherheitsanfälligkeiten**, dass die Anzahl der Benutzerkonten ohne mehrstufige Authentifizierungs Registrierung ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-123">Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration.</span></span> <span data-ttu-id="b9e9d-124">Diese Nummer variiert je nach den zuvor durchgeführten Microsoft 365 Enterprise Test Lab Guides.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-124">This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="b9e9d-125">Klicken Sie durch die Kategorien für **untersuchen** , um zu ermitteln, ob Benutzer oder Ereignisse erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="b9e9d-126">Weitere Tests und Experimente finden Sie unter [Simulieren von Risikoereignissen](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="b9e9d-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="b9e9d-127">Weitere Informationen und Links zum Bereitstellen Azure AD Identitätsschutzes in der Produktion finden Sie im Schritt zum [Schutz gegen Anmeldeinformationen](identity-secure-user-sign-ins.md#identity-ident-prot) in der Identitäts Phase.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-127">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="b9e9d-128">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b9e9d-128">Next step</span></span>

<span data-ttu-id="b9e9d-129">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9e9d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9e9d-130">See also</span></span>

[<span data-ttu-id="b9e9d-131">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="b9e9d-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="b9e9d-132">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b9e9d-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b9e9d-133">Microsoft 365 Enterprise-Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="b9e9d-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b9e9d-134">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b9e9d-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
