---
title: Azure AD Identity Protection für Microsoft 365 für Unternehmenstestumgebungen
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
description: Konfigurieren Sie Azure AD Identity Protection, und analysieren Sie die aktuellen Konten in Microsoft 365 Unternehmenstestumgebung.
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905344"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="81f20-103">Azure AD Identity Protection für Microsoft 365 für Unternehmenstestumgebungen</span><span class="sxs-lookup"><span data-stu-id="81f20-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="81f20-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="81f20-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="81f20-105">Sie können Azure Active Directory (Azure AD) Identity Protection verwenden, um potenzielle Sicherheitsrisiken zu erkennen, die sich auf die Identität Ihrer Organisation auswirken, automatisierte Antworten zu konfigurieren und Vorfälle zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="81f20-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="81f20-106">In diesem Artikel wird beschrieben, wie Sie Azure AD Identity Protection zum Anzeigen der Analyse Ihrer Testumgebungskonten verwenden.</span><span class="sxs-lookup"><span data-stu-id="81f20-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="81f20-107">Das Einrichten von Azure AD Identity Protection in Microsoft 365 für Unternehmenstestumgebung umfasst zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="81f20-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="81f20-108">Phase 1: Build out your Microsoft 365 for Enterprise test environment</span><span class="sxs-lookup"><span data-stu-id="81f20-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="81f20-109">Phase 2: Verwenden von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="81f20-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="81f20-111">Eine visuelle Karte zu allen Artikeln im Stapel Microsoft 365 test lab guide für unternehmen finden Sie unter [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="81f20-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="81f20-112">Phase 1: Build out your Microsoft 365 for Enterprise test environment</span><span class="sxs-lookup"><span data-stu-id="81f20-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="81f20-113">Wenn Sie Azure AD Identity Protection nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="81f20-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="81f20-114">Wenn Sie Azure AD Identity Protection in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="81f20-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="81f20-115">Für das Testen von Azure AD Identity Protection ist keine simulierte Unternehmenstestumgebung erforderlich, die ein simuliertes Intranet umfasst, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine ACTIVE Directory Domain Services (AD DS)-Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="81f20-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="81f20-116">Es wird hier als Option bereitgestellt, damit Sie Azure AD Identity Protection testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="81f20-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="81f20-117">Phase 2: Verwenden von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="81f20-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="81f20-118">Öffnen Sie eine private Instanz Ihres Browsers, und melden Sie sich beim Azure-Portal unter mit dem globalen Administratorkonto Ihrer Microsoft 365 [https://portal.azure.com](https://portal.azure.com) für Unternehmenstestumgebung an.</span><span class="sxs-lookup"><span data-stu-id="81f20-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="81f20-119">Geben Sie im Azure-Portal **identitätsschutz** in das Suchfeld ein, und wählen Sie **dann Azure AD Identity Protection aus.**</span><span class="sxs-lookup"><span data-stu-id="81f20-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="81f20-120">Wählen Sie **auf dem Blatt Identity Protection – Overview** jeden Bericht aus, um zu sehen, was berichtet wird.</span><span class="sxs-lookup"><span data-stu-id="81f20-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="81f20-121">Wählen **Sie unter Benachrichtigen** die Option Erkannte **Warnungen für Benutzer mit Risiko aus.**</span><span class="sxs-lookup"><span data-stu-id="81f20-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="81f20-122">Wählen Sie **im Bereich Erkannte Warnungen für** Benutzer mit Risiko die Option Mittel **aus.**</span><span class="sxs-lookup"><span data-stu-id="81f20-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="81f20-123">Wenn **E-Mails an die folgenden Benutzer** gesendet werden, wählen Sie **Eingeschlossen** aus, und stellen Sie sicher, dass Ihr globales Administratorkonto in der Liste der ausgewählten Mitglieder enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="81f20-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="81f20-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="81f20-124">Select **Save**.</span></span>

<span data-ttu-id="81f20-125">Wählen **Sie unter Schützen** verschiedene Polizeien aus, um zu sehen, wie sie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="81f20-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="81f20-126">Wenn Sie eine Richtlinie erstellen und aktivieren, stellen Sie sicher, dass sie nicht den Zugriff für alle Benutzer blockiert, oder Sie können sich möglicherweise nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="81f20-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="81f20-127">Um dies zu verhindern, schließen Sie bestimmte Benutzerkonten aus, z. B. globale Administratoren.</span><span class="sxs-lookup"><span data-stu-id="81f20-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="81f20-128">Weitere Tests und Experimente finden Sie unter [Simulieren von Risikoereignissen](/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="81f20-128">For further testing and experimentation, see [Simulating risk events](/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="81f20-129">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="81f20-129">Next step</span></span>

<span data-ttu-id="81f20-130">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="81f20-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="81f20-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81f20-131">See also</span></span>

[<span data-ttu-id="81f20-132">Identitätsplan</span><span class="sxs-lookup"><span data-stu-id="81f20-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="81f20-133">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="81f20-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="81f20-134">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="81f20-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="81f20-135">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="81f20-135">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)