---
title: 'Schritt 7: Konfigurieren der Identitätsgovernance'
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
description: Identitätsgovernance für Ihren Azure AD-Mandanten verstehen und konfigurieren.
ms.openlocfilehash: 7ba54db29335f4f8f6eefff0cafbdefe3c522d7a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082012"
---
# <a name="step-7-configure-identity-governance"></a><span data-ttu-id="d080a-103">Schritt 7: Konfigurieren der Identitätsgovernance</span><span class="sxs-lookup"><span data-stu-id="d080a-103">Step 7: Configure identity governance</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="d080a-104">Bei der Identitätsgovernance geht es um den Schutz, die Kontrolle und die Überwachung von Zugriffen auf kritische Ressourcen bei gleichzeitiger Sicherstellung der Mitarbeiterproduktivität.</span><span class="sxs-lookup"><span data-stu-id="d080a-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="d080a-105">Beispielsweise können Sie mit Identitätsgovernance sicherstellen, dass die richtigen Benutzer den richtigen Zugriff auf die richtigen Ressourcen haben, und feststellen, ob sich dieser Zugriff im Laufe der Zeit ändert.</span><span class="sxs-lookup"><span data-stu-id="d080a-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="d080a-106">Weitere Informationen über Identitätsgovernance für Azure Active Directory (Azure AD) finden Sie in [diesem Artikel](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="d080a-106">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>


<span data-ttu-id="d080a-107">*Dies ist optional und gilt nur für die Version E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d080a-107">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="d080a-108">Einrichten von Azure AD-Zugriffsüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="d080a-108">Set up Azure AD access reviews</span></span>

<span data-ttu-id="d080a-109">*Dies ist optional und gilt nur für die E5-Version von Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d080a-109">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d080a-110">In diesem Schritt richten Sie Azure AD Zugriffsüberprüfungen ein, mit denen Sie den Zugriff eines Benutzers überprüfen können, um sicherzustellen, dass nur die richtigen Personen weiterhin Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="d080a-110">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="d080a-111">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d080a-111">For example:</span></span>

- <span data-ttu-id="d080a-112">Wenn ein neuer Mitarbeiter in Ihre Organisation eintritt, müssen Sie sicherstellen, dass er den richtigen Zugriff hat, um produktiv zu sein.</span><span class="sxs-lookup"><span data-stu-id="d080a-112">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="d080a-113">Wenn dieser Mitarbeiter in andere Teams, Standorte oder Abteilungen wechselt, müssen Sie sicherstellen, dass sein Zugang zu früheren Teams, Standorten oder Abteilungen bei Bedarf entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="d080a-113">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="d080a-114">Wenn dieser Mitarbeiter oder ein Gast Ihre Organisation verlässt, müssen Sie sicherstellen, dass sein Zugang entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="d080a-114">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="d080a-115">Dies ist besonders wichtig, falls Ihre Organisation Sicherheitsprüfungen unterzogen wird, um festzustellen, ob Benutzerkonten zu viel Zugriff haben. Ein Verstoß gegen branchenspezifische oder regionale Vorschriften kann zu Geldstrafen führen.</span><span class="sxs-lookup"><span data-stu-id="d080a-115">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="d080a-116">Weitere Informationen über Azure AD-Zugriffsüberprüfungen finden Sie in [diesem Artikel](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span><span class="sxs-lookup"><span data-stu-id="d080a-116">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="d080a-117">Azure AD Privileged Identity Management (PIM) bietet zusätzliche Steuerungselemente zum Sichern des Zugriffs und Verwalten der Zugriffsrechte für Ressourcen in Azure AD, Azure und anderen Microsoft Cloud-Services.</span><span class="sxs-lookup"><span data-stu-id="d080a-117">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="d080a-118">Azure AD PIM stellt einen umfassenden Satz an Steuerungselementen bereit, mit deren Hilfe Sie Unternehmensressourcen wie z. B. Verzeichnis-, Office 365- und Azure-Ressourcenrollen schützen können.</span><span class="sxs-lookup"><span data-stu-id="d080a-118">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="d080a-119">Wie bei anderen Formen des Zugriffs können Organisationen mithilfe von Zugriffsüberprüfungen eine periodische erneute Zertifizierung für alle Benutzer mit Administratorrollen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d080a-119">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="d080a-120">Azure AD PIM ist nur in Verbindung mit der E5-Version von Microsoft 365 Enterprise verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d080a-120">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="d080a-121">In diesen Artikeln finden Sie Informationen zur Konfiguration verschiedener Arten von Zugriffsüberprüfungen:</span><span class="sxs-lookup"><span data-stu-id="d080a-121">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="d080a-122">Gruppen und Apps</span><span class="sxs-lookup"><span data-stu-id="d080a-122">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="d080a-123">Azure AD-Rollen</span><span class="sxs-lookup"><span data-stu-id="d080a-123">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="d080a-124">Azure-Ressourcenrollen</span><span class="sxs-lookup"><span data-stu-id="d080a-124">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="d080a-125">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-access-reviews) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="d080a-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="d080a-126">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d080a-126">Next step</span></span>

[<span data-ttu-id="d080a-127">Beendigungskriterien für die Identitätsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="d080a-127">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

