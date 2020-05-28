---
title: 'Phase 2: Identität'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Die Schritte zur Bereitstellung Ihrer Identitätsinfrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: 6f237f779df16f2a2a03eab29af78a89c5f7a5ae
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371418"
---
# <a name="phase-2-identity"></a><span data-ttu-id="c901a-103">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="c901a-103">Phase 2: Identity</span></span>

![Phase 2: Identität](../media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="c901a-105">In Microsoft 365 Enterprise ebnet eine sorgfältig geplante und ausgeführte Identitätsinfrastruktur den Weg für stärkere Sicherheit und Zugriff auf Produktivitätsarbeitslasten und die zugehörigen Daten nur für authentifizierte Benutzer und Geräte.</span><span class="sxs-lookup"><span data-stu-id="c901a-105">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="c901a-106">Schauen Sie sich dieses Video an, um eine Übersicht über die Identitätsmodelle und Authentifizierung für Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c901a-106">Watch this video for an overview of identity models and authentication for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="c901a-107"><p> </p></span><span class="sxs-lookup"><span data-stu-id="c901a-107"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="c901a-108">Wenn Sie bereits eine Identitätsinfrastruktur bereitgestellt haben, lesen Sie bitte den Artikel [Identitätsbeendigungskriterien](identity-exit-criteria.md) um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c901a-108">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="c901a-109">Informationen zu den Identitätsfeatures jedes Microsoft 365 Enterprise-Plans, zur Rolle von Azure Active Directory (Azure AD), zu lokalen und cloudbasierten Komponenten sowie zu den häufigsten Authentifizierungskonfigurationen finden Sie auf dem [Poster zur Identitätsinfrastruktur](../media/identity-infrastructure/M365E-ID-Infra.pdf).</span><span class="sxs-lookup"><span data-stu-id="c901a-109">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](../media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="c901a-110">[![Poster zur Identitätsinfrastruktur](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="c901a-110">[![The Identity Infrastructure poster](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="c901a-111">Dieses zweiseitige Poster ist eine schnelle Möglichkeit, sich mit den Identitätskonzepten und -konfigurationen für Microsoft 365 Enterprise vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="c901a-111">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="c901a-112">Sie können [dieses Poster herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/identity-infrastructure/M365E-ID-Infra.pdf) und in den Formaten "Brief", "Legal" oder "Tabloid" (27,94 x 43,18 cm) ausdrucken.</span><span class="sxs-lookup"><span data-stu-id="c901a-112">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="c901a-113">Planen und Bereitstellen Ihrer Microsoft 365 Enterprise-Identitätsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="c901a-113">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="c901a-p101">Verwenden Sie die folgenden Schritte zum Planen und Bereitstellen der neuen Identitätsinfrastruktur in der Cloud. Sie können diese Schritte auch zum Anpassen Ihrer vorhandenen lokalen oder Hybrididentitätsinfrastruktur für die Verwendung mit Microsoft 365 Enterprise verwenden.</span><span class="sxs-lookup"><span data-stu-id="c901a-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![Schritt 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="c901a-117">Erstellen und Schützen Ihrer globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="c901a-117">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
|![Schritt 2](../media/stepnumbers/Step2.png)| [<span data-ttu-id="c901a-119">Schützen von Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="c901a-119">Secure your passwords</span></span>](identity-secure-your-passwords.md) |
|![Schritt 3](../media/stepnumbers/Step3.png)| [<span data-ttu-id="c901a-121">Absichern und Verwalten von Benutzeranmeldungen</span><span class="sxs-lookup"><span data-stu-id="c901a-121">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
|![Schritt 4](../media/stepnumbers/Step4.png)| [<span data-ttu-id="c901a-123">Hinzufügen von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="c901a-123">Add your user accounts</span></span>](identity-add-user-accounts.md) |
|![Schritt 5](../media/stepnumbers/Step5.png)| [<span data-ttu-id="c901a-125">Verwenden von Gruppen zur Verwaltung</span><span class="sxs-lookup"><span data-stu-id="c901a-125">Use groups for management</span></span>](identity-use-group-management.md) |
|![Schritt 6](../media/stepnumbers/Step6.png)| [<span data-ttu-id="c901a-127">Konfigurieren der Identitätsgovernance</span><span class="sxs-lookup"><span data-stu-id="c901a-127">Configure identity governance</span></span>](identity-configure-identity-governance.md) |

<span data-ttu-id="c901a-128">Wenn Sie diese Schritte abgeschlossen haben, wechseln Sie zu [Beendigungskriterien](identity-exit-criteria.md) für diese Phase, um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für die Microsoft 365 Enterprise-Identität erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c901a-128">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise identity.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="c901a-129">Empfehlungen für den Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="c901a-129">Identity and device access recommendations</span></span>

<span data-ttu-id="c901a-p102">Microsoft bietet eine Reihe von Empfehlungen für den [Identitäts- und Gerätezugriff](microsoft-365-policies-configurations.md), um sicherzustellen, dass eine sichere und produktive Mitarbeiter. Verwenden Sie für Identität die Standardeinstellungen und Empfehlungen in den folgenden Artikeln zusammen mit den Schritten in dieser Phase:</span><span class="sxs-lookup"><span data-stu-id="c901a-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="c901a-132">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c901a-132">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="c901a-133">Allgemeine Identitäts- und Gerätezugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c901a-133">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="c901a-134">Funktionsweise von Microsoft 365 Enterprise bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="c901a-134">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c901a-135">Erfahren Sie, wie IT-Experten bei Microsoft [Identitäten verwalten und den Zugriff sichern](https://www.microsoft.com/de-DE/itshowcase/managing-user-identities-and-secure-access-at-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c901a-135">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/de-DE/itshowcase/managing-user-identities-and-secure-access-at-microsoft).</span></span>

>[!Note]
><span data-ttu-id="c901a-136">Diese IT Showcase-Ressource ist nur in Englisch verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c901a-136">This IT Showcase resource is only available in English.</span></span>
>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="c901a-137">Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird</span><span class="sxs-lookup"><span data-stu-id="c901a-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c901a-138">Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber multinationales, repräsentatives Unternehmen [eine hybride Identitätsinfrastruktur bereitgestellt hat](contoso-identity.md) (für Microsoft 365-Clouddienste).</span><span class="sxs-lookup"><span data-stu-id="c901a-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![Die Contoso Corporation](../media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="c901a-140">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c901a-140">Next step</span></span>

|||
|:-------|:-----|
|![Schritt 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="c901a-142">Erstellen und Schützen Ihrer globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="c901a-142">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
