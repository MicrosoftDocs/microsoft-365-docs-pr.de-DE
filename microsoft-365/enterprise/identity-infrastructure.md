---
title: 'Phase 2: Identität'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Die Schritte zur Bereitstellung der Identitätsinfrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: 07f95a249912826b80e0654cac4063b3d5763267
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981950"
---
# <a name="phase-2-identity"></a><span data-ttu-id="8419c-103">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="8419c-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="8419c-104">In Microsoft 365 Enterprise ebnet eine sorgfältig geplante und ausgeführte Identitätsinfrastruktur den Weg für stärkere Sicherheit und Zugriff auf Produktivitätsarbeitslasten und die zugehörigen Daten nur für authentifizierte Benutzer und Geräte.</span><span class="sxs-lookup"><span data-stu-id="8419c-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="8419c-105">Schauen Sie sich dieses Video an, um eine Übersicht über die Identitätsmodelle und Authentifizierung für Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8419c-105">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="8419c-106">Wenn Sie bereits eine Identitätsinfrastruktur bereitgestellt haben, lesen Sie bitte den Artikel [Identitätsbeendigungskriterien](identity-exit-criteria.md) um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="8419c-106">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="8419c-107">Informationen zu den Identitätsfeatures jedes Microsoft 365 Enterprise-Plans, zur Rolle von Azure Active Directory (Azure AD), zu lokalen und cloudbasierten Komponenten sowie zu den häufigsten Authentifizierungskonfigurationen finden Sie auf dem [Poster zur Identitätsinfrastruktur](media/identity-infrastructure/M365E-ID-Infra.pdf).</span><span class="sxs-lookup"><span data-stu-id="8419c-107">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="8419c-108">[![Poster zur Identitätsinfrastruktur](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="8419c-108">[![The Identity Infrastructure poster](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="8419c-109">Dieses zweiseitige Poster ist eine schnelle Möglichkeit, sich mit den Identitätskonzepten und -konfigurationen für Microsoft 365 Enterprise vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="8419c-109">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="8419c-110">Sie können [dieses Poster herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) und in den Formaten "Brief", "Legal" oder "Tabloid" (27,94 x 43,18 cm) ausdrucken.</span><span class="sxs-lookup"><span data-stu-id="8419c-110">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="8419c-111">Planen und Bereitstellen Ihrer Microsoft 365 Enterprise-Identitätsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="8419c-111">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="8419c-p101">Verwenden Sie die folgenden Schritte zum Planen und Bereitstellen der neuen Identitätsinfrastruktur in der Cloud. Sie können diese Schritte auch zum Anpassen Ihrer vorhandenen lokalen oder Hybrididentitätsinfrastruktur für die Verwendung mit Microsoft 365 Enterprise verwenden.</span><span class="sxs-lookup"><span data-stu-id="8419c-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="8419c-114">Planen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="8419c-114">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="8419c-115">Sichern Ihrer privilegierten Identitäten</span><span class="sxs-lookup"><span data-stu-id="8419c-115">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="8419c-116">Konfigurieren der Hybrididentität</span><span class="sxs-lookup"><span data-stu-id="8419c-116">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="8419c-117">Konfigurieren der sicheren Benutzerauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="8419c-117">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="8419c-118">Vereinfachen des Zugriffs für Benutzer</span><span class="sxs-lookup"><span data-stu-id="8419c-118">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="8419c-119">Verwenden von Gruppen zur einfacheren Verwaltung</span><span class="sxs-lookup"><span data-stu-id="8419c-119">Use groups for easier management</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="8419c-120">Konfigurieren der Identitätsgovernance</span><span class="sxs-lookup"><span data-stu-id="8419c-120">Configure identity governance</span></span>](identity-governance.md) |

<span data-ttu-id="8419c-121">Wenn Sie diese Schritte abgeschlossen haben, wechseln Sie zu [Beendigungskriterien](identity-exit-criteria.md) für diese Phase, um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für die Microsoft 365 Enterprise-Identität erfüllen.</span><span class="sxs-lookup"><span data-stu-id="8419c-121">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="8419c-122">Empfehlungen für den Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="8419c-122">Identity and device access recommendations</span></span>

<span data-ttu-id="8419c-p102">Microsoft bietet eine Reihe von Empfehlungen für den [Identitäts- und Gerätezugriff](microsoft-365-policies-configurations.md), um sicherzustellen, dass eine sichere und produktive Mitarbeiter. Verwenden Sie für Identität die Standardeinstellungen und Empfehlungen in den folgenden Artikeln zusammen mit den Schritten in dieser Phase:</span><span class="sxs-lookup"><span data-stu-id="8419c-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="8419c-125">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8419c-125">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="8419c-126">Allgemeine Identitäts- und Gerätezugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8419c-126">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="8419c-127">Funktionsweise von Microsoft 365 Enterprise bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="8419c-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="8419c-128">Erfahren Sie, wie IT-Experten bei Microsoft [Identitäten verwalten und den Zugriff sichern](https://www.microsoft.com/de-DE/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span><span class="sxs-lookup"><span data-stu-id="8419c-128">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/de-DE/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="8419c-129">Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird</span><span class="sxs-lookup"><span data-stu-id="8419c-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="8419c-130">Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber multinationales, repräsentatives Unternehmen [eine hybride Identitätsinfrastruktur bereitgestellt hat](contoso-identity.md) (für Microsoft 365-Clouddienste).</span><span class="sxs-lookup"><span data-stu-id="8419c-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="8419c-131">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="8419c-131">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="8419c-132">Planen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="8419c-132">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
