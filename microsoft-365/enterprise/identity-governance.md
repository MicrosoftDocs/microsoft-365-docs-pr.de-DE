---
title: 'Schritt 7: Konfigurieren der Identitätsgovernance'
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
description: Identitätsgovernance für Ihren Azure AD-Mandanten verstehen und konfigurieren.
ms.openlocfilehash: 1c0eab574e5436dd0c88a0b46d1916281bcf0577
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047358"
---
# <a name="step-7-configure-identity-governance"></a><span data-ttu-id="b0a7e-103">Schritt 7: Konfigurieren der Identitätsgovernance</span><span class="sxs-lookup"><span data-stu-id="b0a7e-103">Step 7: Configure identity governance</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="b0a7e-104">Bei der Identitätsgovernance geht es um den Schutz, die Kontrolle und die Überwachung von Zugriffen auf kritische Ressourcen bei gleichzeitiger Sicherstellung der Mitarbeiterproduktivität.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="b0a7e-105">Beispielsweise können Sie mit Identitätsgovernance sicherstellen, dass die richtigen Benutzer den richtigen Zugriff auf die richtigen Ressourcen haben, und feststellen, ob sich dieser Zugriff im Laufe der Zeit ändert.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="b0a7e-106">Weitere Informationen über Identitätsgovernance für Azure Active Directory (Azure AD) finden Sie in [diesem Artikel](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="b0a7e-106">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>

<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="b0a7e-107">Zugriffsüberprüfungen in Azure AD einrichten</span><span class="sxs-lookup"><span data-stu-id="b0a7e-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="b0a7e-108">*Dies ist optional und gilt nur für die E5-Version von Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b0a7e-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b0a7e-109">In diesem Schritt richten Sie Azure AD Zugriffsüberprüfungen ein, mit denen Sie den Zugriff eines Benutzers überprüfen können, um sicherzustellen, dass nur die richtigen Personen weiterhin Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-109">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="b0a7e-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b0a7e-110">For example:</span></span>

- <span data-ttu-id="b0a7e-111">Wenn ein neuer Mitarbeiter in Ihre Organisation eintritt, müssen Sie sicherstellen, dass er den richtigen Zugriff hat, um produktiv zu sein.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-111">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="b0a7e-112">Wenn dieser Mitarbeiter in andere Teams, Standorte oder Abteilungen wechselt, müssen Sie sicherstellen, dass sein Zugang zu früheren Teams, Standorten oder Abteilungen bei Bedarf entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-112">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="b0a7e-113">Wenn dieser Mitarbeiter oder ein Gast Ihre Organisation verlässt, müssen Sie sicherstellen, dass sein Zugang entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-113">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="b0a7e-114">Dies ist besonders wichtig, falls Ihre Organisation Sicherheitsprüfungen unterzogen wird, um festzustellen, ob Benutzerkonten zu viel Zugriff haben. Ein Verstoß gegen branchenspezifische oder regionale Vorschriften kann zu Geldstrafen führen.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-114">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="b0a7e-115">Weitere Informationen über Azure AD-Zugriffsüberprüfungen finden Sie in [diesem Artikel](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span><span class="sxs-lookup"><span data-stu-id="b0a7e-115">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="b0a7e-116">In diesen Artikeln finden Sie Informationen zur Konfiguration verschiedener Arten von Zugriffsüberprüfungen:</span><span class="sxs-lookup"><span data-stu-id="b0a7e-116">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="b0a7e-117">Gruppen und Apps</span><span class="sxs-lookup"><span data-stu-id="b0a7e-117">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="b0a7e-118">Azure AD-Rollen</span><span class="sxs-lookup"><span data-stu-id="b0a7e-118">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="b0a7e-119">Azure-Ressourcenrollen</span><span class="sxs-lookup"><span data-stu-id="b0a7e-119">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="b0a7e-120">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-access-reviews) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-120">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="b0a7e-121">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b0a7e-121">Next step</span></span>

[<span data-ttu-id="b0a7e-122">Beendigungskriterien für die Identitätsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="b0a7e-122">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

