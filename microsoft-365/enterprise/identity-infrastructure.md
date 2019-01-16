---
title: 'Phase 2: Identität'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Die Schritte zur Bereitstellung der Identitätsinfrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: 7b5d62f5c09a1ea6d46449b113bff59dbf07ebad
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867964"
---
# <a name="phase-2-identity"></a><span data-ttu-id="2d394-103">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="2d394-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="2d394-104">In Microsoft 365 Enterprise ebnet eine sorgfältig geplante und ausgeführte Identitätsinfrastruktur den Weg für stärkere Sicherheit und Zugriff auf Produktivitätsarbeitslasten und die zugehörigen Daten nur für authentifizierte Benutzer und Geräte.</span><span class="sxs-lookup"><span data-stu-id="2d394-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="2d394-105">Wenn Sie bereits eine Identitätsinfrastruktur bereitgestellt haben, lesen Sie bitte den Artikel [Identitätsbeendigungskriterien](identity-exit-criteria.md) um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2d394-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="2d394-106">Planen und Bereitstellen Ihrer Microsoft 365 Enterprise-Identitätsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="2d394-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="2d394-p101">Verwenden Sie die folgenden Schritte zum Planen und Bereitstellen der neuen Identitätsinfrastruktur in der Cloud. Sie können diese Schritte auch zum Anpassen Ihrer vorhandenen lokalen oder Hybrididentitätsinfrastruktur für die Verwendung mit Microsoft 365 Enterprise verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d394-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="2d394-109">Planen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="2d394-109">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="2d394-110">Schützen von globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="2d394-110">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="2d394-111">Einrichten von globalen Administratoren bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="2d394-111">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="2d394-112">Vereinfachen der Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="2d394-112">Simplify password resets</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="2d394-113">Einrichten der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2d394-113">Set up multi-factor authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="2d394-114">Schutz vor Kompromittierung von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="2d394-114">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="2d394-115">Synchronisieren von Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="2d394-115">Synchronize directories</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="2d394-116">Überwachen des Synchronisierungsstatus</span><span class="sxs-lookup"><span data-stu-id="2d394-116">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="2d394-117">Vereinfachen der Kennwortaktualisierungen</span><span class="sxs-lookup"><span data-stu-id="2d394-117">Simplify password updates</span></span>](identity-password-writeback.md) |
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="2d394-118">Vereinfachen der Benutzeranmeldung</span><span class="sxs-lookup"><span data-stu-id="2d394-118">Simplify user sign-in</span></span>](identity-single-sign-on.md) |
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="2d394-119">Anpassen der Office 365-Anmeldeseite</span><span class="sxs-lookup"><span data-stu-id="2d394-119">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |
|![](./media/stepnumbers/Step12.png)| [<span data-ttu-id="2d394-120">Einrichten der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="2d394-120">Set up automatic licensing</span></span>](identity-group-based-licensing.md) |
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="2d394-121">Überwachen der Mandanten- und Anmeldeaktivität</span><span class="sxs-lookup"><span data-stu-id="2d394-121">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="2d394-122">Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="2d394-122">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="2d394-123">Einrichten der dynamischen Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="2d394-123">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |

<span data-ttu-id="2d394-124">Wenn Sie diese Schritte abgeschlossen haben, wechseln Sie zu [Beendigungskriterien](identity-exit-criteria.md) für diese Phase, um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2d394-124">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="2d394-125">Empfehlungen für den Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="2d394-125">Identity and device access prerequisites</span></span>

<span data-ttu-id="2d394-p102">Microsoft bietet eine Reihe von Empfehlungen für den [Identitäts- und Gerätezugriff](microsoft-365-policies-configurations.md), um sicherzustellen, dass eine sichere und produktive Mitarbeiter. Verwenden Sie für Identität die Standardeinstellungen und Empfehlungen in den folgenden Artikeln zusammen mit den Schritten in dieser Phase:</span><span class="sxs-lookup"><span data-stu-id="2d394-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="2d394-128">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2d394-128">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="2d394-129">Allgemeine Identitäts- und Gerätezugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2d394-129">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="2d394-130">Funktionsweise von Microsoft 365 Enterprise bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="2d394-130">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2d394-131">Erfahren Sie anhand der folgenden Ressourcen, wie IT-Experten bei Microsoft die Identitätsfunktionen von Microsoft 365 Enterprise geplant und bereitgestellt haben:</span><span class="sxs-lookup"><span data-stu-id="2d394-131">Learn how IT experts at Microsoft planned for and deployed the identity capabilities of Microsoft 365 Enterprise with these resources:</span></span>

- [<span data-ttu-id="2d394-132">Verwalten von Benutzeridentitäten und sicherer Zugriff bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="2d394-132">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="2d394-133">Erhöhter Zugriff dank Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="2d394-133">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="2d394-134">Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird</span><span class="sxs-lookup"><span data-stu-id="2d394-134">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2d394-135">Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber multinationales, repräsentatives Unternehmen [eine hybride Identitätsinfrastruktur bereitgestellt hat](contoso-identity.md) (für Microsoft 365-Clouddienste).</span><span class="sxs-lookup"><span data-stu-id="2d394-135">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="2d394-136">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="2d394-136">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="2d394-137">Planen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="2d394-137">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
