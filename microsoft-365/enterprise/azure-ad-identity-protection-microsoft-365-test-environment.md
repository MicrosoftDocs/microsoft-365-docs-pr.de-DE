---
title: Azure AD Identitätsschutz für Ihre Microsoft 365 Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie Azure AD Identitätsschutz, und analysieren Sie die aktuellen Konten in Ihrer Microsoft 365 Enterprise-Testumgebung.
ms.openlocfilehash: 3f3740e42c7ec909f44a3c761dfc743359b3f030
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068492"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="06fe3-103">Azure AD Identitätsschutz für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="06fe3-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="06fe3-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="06fe3-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="06fe3-105">Azure Active Directory (Azure AD) Identity Protection ermöglicht Ihnen das Erkennen potenzieller Sicherheitsanfälligkeiten, die sich auf die Identitäten Ihrer Organisation auswirken, automatische Antworten konfigurieren und Vorfälle untersuchen.</span><span class="sxs-lookup"><span data-stu-id="06fe3-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="06fe3-106">In diesem Artikel wird beschrieben, wie Sie Azure AD Identitätsschutz verwenden, um die Analyse Ihrer Test Umgebungs Konten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="06fe3-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="06fe3-107">Es gibt zwei Phasen zum Einrichten Azure AD Identitätsschutzes in Ihrer Microsoft 365 Enterprise-Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="06fe3-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="06fe3-108">Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="06fe3-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="06fe3-109">Verwenden Sie Azure AD Identitätsschutz.</span><span class="sxs-lookup"><span data-stu-id="06fe3-109">Use Azure AD Identity Protection.</span></span>

![Testumgebungsanleitungen für die Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="06fe3-111">Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="06fe3-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="06fe3-112">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="06fe3-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="06fe3-113">Wenn Sie Azure AD Identitätsschutz nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="06fe3-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="06fe3-114">Wenn Sie Azure AD Identitätsschutz in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="06fe3-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="06fe3-115">Für das Testen Azure AD Identitätsschutzes ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="06fe3-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="06fe3-116">Sie wird hier als Option bereitgestellt, damit Sie Azure AD Identitätsschutz testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="06fe3-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="06fe3-117">Phase 2: Verwenden von Azure AD Identitätsschutz</span><span class="sxs-lookup"><span data-stu-id="06fe3-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="06fe3-118">Öffnen Sie eine private Instanz Ihres Browsers, und melden Sie sich beim Azure- [https://portal.azure.com](https://portal.azure.com) Portal unter mit dem globalen Administratorkonto Ihrer Microsoft 365 Enterprise-Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="06fe3-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="06fe3-119">Geben Sie im Azure-Portal **Identity Protection** in das Suchfeld ein, und klicken Sie dann auf **Azure AD Identitätsschutz**.</span><span class="sxs-lookup"><span data-stu-id="06fe3-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="06fe3-120">Klicken Sie im Blatt **Identitätsschutz – Übersicht** auf die einzelnen Berichte, um zu sehen, was Sie berichten.</span><span class="sxs-lookup"><span data-stu-id="06fe3-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="06fe3-121">Klicken Sie unter **Benachrichtigen**auf **Benutzer bei Risiko erkannte Warnungen**.</span><span class="sxs-lookup"><span data-stu-id="06fe3-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="06fe3-122">Wählen Sie im Bereich **Benutzer bei Risiko erkannte Warnungen** die Option **Mittel**aus.</span><span class="sxs-lookup"><span data-stu-id="06fe3-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="06fe3-123">Wenn **e-Mails an die folgenden Benutzer gesendet werden**, klicken Sie auf **einschließen** , und vergewissern Sie sich, dass sich ihr globales Administratorkonto in der Liste der ausgewählten Mitglieder befindet.</span><span class="sxs-lookup"><span data-stu-id="06fe3-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="06fe3-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="06fe3-124">Click **Save**.</span></span>

<span data-ttu-id="06fe3-125">Klicken Sie auf die verschiedenen Richtlinien unter **Protect** , um zu erfahren, wie Sie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="06fe3-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="06fe3-126">Wenn Sie eine Richtlinie erstellen und aktivieren, müssen Sie sicherstellen, dass der Zugriff für einen zu weiten Bereich von Bedingungen nicht blockiert wird, oder Sie können sich nicht selbst als globaler Administrator anmelden.</span><span class="sxs-lookup"><span data-stu-id="06fe3-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="06fe3-127">Weitere Tests und Experimente finden Sie unter [Simulieren von Risikoereignissen](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="06fe3-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="06fe3-128">Weitere Informationen und Links zum Bereitstellen Azure AD Identitätsschutzes in der Produktion finden Sie im Schritt zum [Schutz gegen Anmeldeinformationen](identity-secure-user-sign-ins.md#identity-ident-prot) in der Identitäts Phase.</span><span class="sxs-lookup"><span data-stu-id="06fe3-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="06fe3-129">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="06fe3-129">Next step</span></span>

<span data-ttu-id="06fe3-130">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="06fe3-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="06fe3-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06fe3-131">See also</span></span>

[<span data-ttu-id="06fe3-132">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="06fe3-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="06fe3-133">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="06fe3-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="06fe3-134">Microsoft 365 Enterprise-Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="06fe3-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="06fe3-135">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="06fe3-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
