---
title: Azure AD Identitätsschutz für Ihre Microsoft 365 for Enterprise-Testumgebung
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
description: Konfigurieren Sie Azure AD Identitätsschutz, und analysieren Sie die aktuellen Konten in Ihrer Microsoft 365 for Enterprise-Testumgebung.
ms.openlocfilehash: bd1e7560e978b13d24e9e93a99a2567adca95c75
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694990"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a93a9-103">Azure AD Identitätsschutz für Ihre Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="a93a9-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a93a9-104">*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="a93a9-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="a93a9-105">Azure Active Directory (Azure AD) Identity Protection ermöglicht Ihnen das Erkennen potenzieller Sicherheitsanfälligkeiten, die sich auf die Identitäten Ihrer Organisation auswirken, automatische Antworten konfigurieren und Vorfälle untersuchen.</span><span class="sxs-lookup"><span data-stu-id="a93a9-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="a93a9-106">In diesem Artikel wird beschrieben, wie Sie Azure AD Identitätsschutz verwenden, um die Analyse Ihrer Test Umgebungs Konten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a93a9-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="a93a9-107">Es gibt zwei Phasen zum Einrichten Azure AD Identitätsschutzes in Ihrer Microsoft 365 for Enterprise-Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="a93a9-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="a93a9-108">Erstellen Sie die Microsoft 365 for Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="a93a9-108">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="a93a9-109">Verwenden Sie Azure AD Identitätsschutz.</span><span class="sxs-lookup"><span data-stu-id="a93a9-109">Use Azure AD Identity Protection.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a93a9-111">Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a93a9-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a93a9-112">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="a93a9-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a93a9-113">Wenn Sie Azure AD Identitätsschutz nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="a93a9-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a93a9-114">Wenn Sie Azure AD Identitätsschutz in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a93a9-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a93a9-115">Für das Testen Azure AD Identitätsschutzes ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="a93a9-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a93a9-116">Sie wird hier als Option bereitgestellt, damit Sie Azure AD Identitätsschutz testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="a93a9-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="a93a9-117">Phase 2: Verwenden von Azure AD Identitätsschutz</span><span class="sxs-lookup"><span data-stu-id="a93a9-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="a93a9-118">Öffnen Sie eine private Instanz Ihres Browsers, und melden Sie sich beim Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit dem globalen Administratorkonto Ihrer Microsoft 365 für Enterprise-Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="a93a9-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="a93a9-119">Geben Sie im Azure-Portal **Identity Protection** in das Suchfeld ein, und klicken Sie dann auf **Azure AD Identitätsschutz**.</span><span class="sxs-lookup"><span data-stu-id="a93a9-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="a93a9-120">Klicken Sie im Blatt **Identitätsschutz – Übersicht** auf die einzelnen Berichte, um zu sehen, was Sie berichten.</span><span class="sxs-lookup"><span data-stu-id="a93a9-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="a93a9-121">Klicken Sie unter **Benachrichtigen**auf **Benutzer bei Risiko erkannte Warnungen**.</span><span class="sxs-lookup"><span data-stu-id="a93a9-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="a93a9-122">Wählen Sie im Bereich **Benutzer bei Risiko erkannte Warnungen** die Option **Mittel**aus.</span><span class="sxs-lookup"><span data-stu-id="a93a9-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="a93a9-123">Wenn **e-Mails an die folgenden Benutzer gesendet werden**, klicken Sie auf **einschließen** , und vergewissern Sie sich, dass sich ihr globales Administratorkonto in der Liste der ausgewählten Mitglieder befindet.</span><span class="sxs-lookup"><span data-stu-id="a93a9-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="a93a9-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a93a9-124">Click **Save**.</span></span>

<span data-ttu-id="a93a9-125">Klicken Sie auf die verschiedenen Richtlinien unter **Protect** , um zu erfahren, wie Sie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="a93a9-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="a93a9-126">Wenn Sie eine Richtlinie erstellen und aktivieren, müssen Sie sicherstellen, dass der Zugriff für einen zu weiten Bereich von Bedingungen nicht blockiert wird, oder Sie können sich nicht selbst als globaler Administrator anmelden.</span><span class="sxs-lookup"><span data-stu-id="a93a9-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="a93a9-127">Weitere Tests und Experimente finden Sie unter [Simulieren von Risikoereignissen](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="a93a9-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="a93a9-128">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="a93a9-128">Next step</span></span>

<span data-ttu-id="a93a9-129">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="a93a9-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a93a9-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a93a9-130">See also</span></span>

[<span data-ttu-id="a93a9-131">Identity-Roadmap</span><span class="sxs-lookup"><span data-stu-id="a93a9-131">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="a93a9-132">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a93a9-132">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a93a9-133">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a93a9-133">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a93a9-134">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="a93a9-134">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
