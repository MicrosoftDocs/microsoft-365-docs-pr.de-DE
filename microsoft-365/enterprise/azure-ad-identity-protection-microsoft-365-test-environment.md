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
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487708"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="04555-103">Azure AD Identitätsschutz für Ihre Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="04555-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="04555-104">*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="04555-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="04555-105">Sie können Azure Active Directory (Azure AD) Identity Protection verwenden, um potenzielle Sicherheitsrisiken zu erkennen, die sich auf die Identitäten Ihrer Organisation auswirken, automatisierte Antworten konfigurieren und Vorfälle untersuchen.</span><span class="sxs-lookup"><span data-stu-id="04555-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="04555-106">In diesem Artikel wird beschrieben, wie Sie Azure AD Identitätsschutz verwenden, um die Analyse Ihrer Test Umgebungs Konten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04555-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="04555-107">Das Einrichten Azure AD Identitätsschutzes in Ihrer Microsoft 365 for Enterprise-Testumgebung umfasst zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="04555-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="04555-108">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="04555-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="04555-109">Phase 2: Verwenden von Azure AD Identitätsschutz</span><span class="sxs-lookup"><span data-stu-id="04555-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="04555-111">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="04555-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="04555-112">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="04555-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="04555-113">Wenn Sie Azure AD Identitätsschutz nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="04555-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="04555-114">Wenn Sie Azure AD Identitätsschutz in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="04555-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="04555-115">Für das Testen Azure AD Identitätsschutzes ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="04555-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="04555-116">Sie wird hier als Option bereitgestellt, damit Sie Azure AD Identitätsschutz testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="04555-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="04555-117">Phase 2: Verwenden von Azure AD Identitätsschutz</span><span class="sxs-lookup"><span data-stu-id="04555-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="04555-118">Öffnen Sie eine private Instanz Ihres Browsers, und melden Sie sich beim Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit dem globalen Administratorkonto Ihrer Microsoft 365 für Enterprise-Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="04555-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="04555-119">Geben Sie im Azure-Portal **Identity Protection** in das Suchfeld ein, und wählen Sie dann **Azure AD Identitätsschutz**aus.</span><span class="sxs-lookup"><span data-stu-id="04555-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="04555-120">Wählen Sie im Blatt **Identitätsschutz – Übersicht** die einzelnen Berichte aus, um die Berichterstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04555-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="04555-121">Wählen Sie unter **Benachrichtigen**die Option **Benutzer bei Risiko erkannte Warnungen**aus.</span><span class="sxs-lookup"><span data-stu-id="04555-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="04555-122">Wählen Sie im Bereich **Benutzer bei Risiko erkannte Warnungen** die Option **Mittel**aus.</span><span class="sxs-lookup"><span data-stu-id="04555-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="04555-123">Wenn **e-Mails an die folgenden Benutzer gesendet werden**, wählen Sie **einschließen** aus, und stellen Sie sicher, dass sich ihr globales Administratorkonto in der Liste der ausgewählten Mitglieder befindet.</span><span class="sxs-lookup"><span data-stu-id="04555-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="04555-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="04555-124">Select **Save**.</span></span>

<span data-ttu-id="04555-125">Wählen Sie unter **Protect**verschiedene Policies aus, um zu sehen, wie Sie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="04555-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="04555-126">Wenn Sie eine Richtlinie erstellen und aktivieren, müssen Sie sicherstellen, dass der Zugriff nicht für alle Benutzer blockiert wird, oder Sie können sich möglicherweise nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="04555-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="04555-127">Um dies zu verhindern, schließen Sie bestimmte Benutzerkonten wie globale Administratoren aus.</span><span class="sxs-lookup"><span data-stu-id="04555-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="04555-128">Weitere Tests und Experimente finden Sie unter [Simulieren von Risikoereignissen](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="04555-128">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="04555-129">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="04555-129">Next step</span></span>

<span data-ttu-id="04555-130">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="04555-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="04555-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04555-131">See also</span></span>

[<span data-ttu-id="04555-132">Identity-Roadmap</span><span class="sxs-lookup"><span data-stu-id="04555-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="04555-133">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="04555-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="04555-134">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="04555-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="04555-135">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="04555-135">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
