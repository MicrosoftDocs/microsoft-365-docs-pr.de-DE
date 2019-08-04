---
title: 'Phase 2: Identität'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Die Schritte zur Bereitstellung der Identitätsinfrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: 6acd462a0fcd4169a42a0b1d0e1738ffcba597f5
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073895"
---
# <a name="phase-2-identity"></a><span data-ttu-id="13133-103">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="13133-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="13133-104">In Microsoft 365 Enterprise ebnet eine sorgfältig geplante und ausgeführte Identitätsinfrastruktur den Weg für stärkere Sicherheit und Zugriff auf Produktivitätsarbeitslasten und die zugehörigen Daten nur für authentifizierte Benutzer und Geräte.</span><span class="sxs-lookup"><span data-stu-id="13133-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="13133-105">Wenn Sie bereits eine Identitätsinfrastruktur bereitgestellt haben, lesen Sie bitte den Artikel [Identitätsbeendigungskriterien](identity-exit-criteria.md) um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="13133-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="13133-106">Planen und Bereitstellen Ihrer Microsoft 365 Enterprise-Identitätsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="13133-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="13133-107">Bevor Sie beginnen, schauen Sie sich dieses Video an, um eine Übersicht über die Identitätsmodelle und Authentifizierung für Microsoft 365 zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="13133-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="13133-p101">Verwenden Sie die folgenden Schritte zum Planen und Bereitstellen der neuen Identitätsinfrastruktur in der Cloud. Sie können diese Schritte auch zum Anpassen Ihrer vorhandenen lokalen oder Hybrididentitätsinfrastruktur für die Verwendung mit Microsoft 365 Enterprise verwenden.</span><span class="sxs-lookup"><span data-stu-id="13133-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="13133-110">Planen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="13133-110">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="13133-111">Sichern Ihrer privilegierten Identitäten</span><span class="sxs-lookup"><span data-stu-id="13133-111">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="13133-112">Konfigurieren der Hybrididentität</span><span class="sxs-lookup"><span data-stu-id="13133-112">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="13133-113">Konfigurieren der sicheren Benutzerauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="13133-113">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="13133-114">Vereinfachen des Zugriffs für Benutzer</span><span class="sxs-lookup"><span data-stu-id="13133-114">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="13133-115">Verwenden von Gruppen zur einfacheren Verwaltung</span><span class="sxs-lookup"><span data-stu-id="13133-115">Use groups for easier management</span></span>](identity-self-service-group-management.md) |

<span data-ttu-id="13133-116">Wenn Sie diese Schritte abgeschlossen haben, wechseln Sie zu [Beendigungskriterien](identity-exit-criteria.md) für diese Phase, um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="13133-116">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="13133-117">Empfehlungen für den Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="13133-117">Identity and device access recommendations</span></span>

<span data-ttu-id="13133-p102">Microsoft bietet eine Reihe von Empfehlungen für den [Identitäts- und Gerätezugriff](microsoft-365-policies-configurations.md), um sicherzustellen, dass eine sichere und produktive Mitarbeiter. Verwenden Sie für Identität die Standardeinstellungen und Empfehlungen in den folgenden Artikeln zusammen mit den Schritten in dieser Phase:</span><span class="sxs-lookup"><span data-stu-id="13133-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="13133-120">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="13133-120">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="13133-121">Allgemeine Identitäts- und Gerätezugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="13133-121">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="13133-122">Funktionsweise von Microsoft 365 Enterprise bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="13133-122">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="13133-123">Erfahren Sie, wie IT-Experten bei Microsoft [Identitäten verwalten und den Zugriff sichern](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span><span class="sxs-lookup"><span data-stu-id="13133-123">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="13133-124">Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird</span><span class="sxs-lookup"><span data-stu-id="13133-124">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="13133-125">Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber multinationales, repräsentatives Unternehmen [eine hybride Identitätsinfrastruktur bereitgestellt hat](contoso-identity.md) (für Microsoft 365-Clouddienste).</span><span class="sxs-lookup"><span data-stu-id="13133-125">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="13133-126">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="13133-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="13133-127">Planen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="13133-127">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
