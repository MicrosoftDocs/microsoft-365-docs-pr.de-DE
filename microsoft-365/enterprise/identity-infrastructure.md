---
title: 'Phase 2: Identität'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Die Schritte zur Bereitstellung der Identitätsinfrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: e96b255809e4fc788804905a7c90ac7e2b336429
ms.sourcegitcommit: 12b019f149e5a34448ad2774be29468a4f27cce7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998685"
---
# <a name="phase-2-identity"></a><span data-ttu-id="e8dcd-103">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="e8dcd-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="e8dcd-104">In Microsoft 365 Enterprise ebnet eine sorgfältig geplante und ausgeführte Identitätsinfrastruktur den Weg für stärkere Sicherheit und Zugriff auf Produktivitätsarbeitslasten und die zugehörigen Daten nur für authentifizierte Benutzer und Geräte.</span><span class="sxs-lookup"><span data-stu-id="e8dcd-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="e8dcd-105">Wenn Sie bereits eine Identitätsinfrastruktur bereitgestellt haben, lesen Sie bitte den Artikel [Identitätsbeendigungskriterien](identity-exit-criteria.md) um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e8dcd-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="e8dcd-106">Planen und Bereitstellen Ihrer Microsoft 365 Enterprise-Identitätsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="e8dcd-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="e8dcd-p101">Verwenden Sie die folgenden Schritte zum Planen und Bereitstellen der neuen Identitätsinfrastruktur in der Cloud. Sie können diese Schritte auch zum Anpassen Ihrer vorhandenen lokalen oder Hybrididentitätsinfrastruktur für die Verwendung mit Microsoft 365 Enterprise verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8dcd-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 


|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="e8dcd-109">Planen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="e8dcd-109">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="e8dcd-110">Synchronisieren von Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="e8dcd-110">Synchronize directories</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="e8dcd-111">Anpassen der Office 365-Anmeldeseite</span><span class="sxs-lookup"><span data-stu-id="e8dcd-111">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="e8dcd-112">Überwachen des Synchronisierungsstatus</span><span class="sxs-lookup"><span data-stu-id="e8dcd-112">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="e8dcd-113">Schützen von globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="e8dcd-113">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="e8dcd-114">Einrichten von globalen Administratoren bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="e8dcd-114">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="e8dcd-115">Planen der mehrstufigen Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e8dcd-115">Set up multi-factor authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="e8dcd-116">Vereinfachen der Benutzeranmeldung</span><span class="sxs-lookup"><span data-stu-id="e8dcd-116">Simplify user sign-in</span></span>](identity-single-sign-on.md) |
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="e8dcd-117">Vereinfachen der Kennwortaktualisierungen</span><span class="sxs-lookup"><span data-stu-id="e8dcd-117">Simplify password updates</span></span>](identity-password-writeback.md) |
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="e8dcd-118">Vereinfachen der Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="e8dcd-118">Simplify password resets</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="e8dcd-119">Einrichten der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="e8dcd-119">Set up automatic licensing</span></span>](identity-group-based-licensing.md) |
|![](./media/stepnumbers/Step12.png)| [<span data-ttu-id="e8dcd-120">Einrichten der dynamischen Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="e8dcd-120">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="e8dcd-121">Überwachen der Mandanten- und Anmeldeaktivität</span><span class="sxs-lookup"><span data-stu-id="e8dcd-121">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="e8dcd-122">Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="e8dcd-122">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="e8dcd-123">Schutz vor Kompromittierung von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="e8dcd-123">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |
|![](./media/stepnumbers/Step16.png)| [<span data-ttu-id="e8dcd-124">Bereitstellen eines sicheren Remotezugriffs für Benutzer</span><span class="sxs-lookup"><span data-stu-id="e8dcd-124">Provide secure remote access to users</span></span>](identity-azure-ad-application-proxy.md) |

<span data-ttu-id="e8dcd-125">Wenn Sie diese Schritte abgeschlossen haben, wechseln Sie zu [Beendigungskriterien](identity-exit-criteria.md) für diese Phase, um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e8dcd-125">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="e8dcd-126">Funktionsweise von Microsoft 365 Enterprise bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="e8dcd-126">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="e8dcd-127">Erfahren Sie anhand der folgenden Ressourcen, wie IT-Experten bei Microsoft die Identitätsfunktionen von Microsoft 365 Enterprise geplant und bereitgestellt haben:</span><span class="sxs-lookup"><span data-stu-id="e8dcd-127">Learn how IT experts at Microsoft planned for and deployed the identity capabilities of Microsoft 365 Enterprise with these resources:</span></span>

- [<span data-ttu-id="e8dcd-128">Verwalten von Benutzeridentitäten und sicherer Zugriff bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="e8dcd-128">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="e8dcd-129">Erhöhter Zugriff dank Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="e8dcd-129">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="next-step"></a><span data-ttu-id="e8dcd-130">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e8dcd-130">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="e8dcd-131">Planen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="e8dcd-131">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
