---
title: Verwalten von Microsoft 365 Identity Governance
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Erfahren Sie mehr über die Verwendung von Microsoft 365 Identity Governance-Features.
ms.openlocfilehash: d5bcafb5b452e693bf3ff706c436a9986eeeae76
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328514"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="43931-103">Verwalten von Microsoft 365 Identity Governance</span><span class="sxs-lookup"><span data-stu-id="43931-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="43931-104">Bei der Identitätsgovernance geht es um den Schutz, die Kontrolle und die Überwachung von Zugriffen auf kritische Ressourcen bei gleichzeitiger Sicherstellung der Mitarbeiterproduktivität.</span><span class="sxs-lookup"><span data-stu-id="43931-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="43931-105">Beispielsweise können Sie mit Identitätsgovernance sicherstellen, dass die richtigen Benutzer den richtigen Zugriff auf die richtigen Ressourcen haben, und feststellen, ob sich dieser Zugriff im Laufe der Zeit ändert.</span><span class="sxs-lookup"><span data-stu-id="43931-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="43931-106">Weitere Informationen finden Sie in dieser [Übersicht über Identity Governance für Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="43931-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="43931-107">Einrichten von Azure AD-Zugriffsüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="43931-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="43931-108">Mit Azure AD Zugriffsüberprüfungen können Sie den Zugriff eines Benutzers überprüfen, um sicherzustellen, dass nur die richtigen Personen weiterhin Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="43931-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="43931-109">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="43931-109">For example:</span></span>

- <span data-ttu-id="43931-110">Wenn ein neuer Mitarbeiter in Ihre Organisation eintritt, müssen Sie sicherstellen, dass er den richtigen Zugriff hat, um produktiv zu sein.</span><span class="sxs-lookup"><span data-stu-id="43931-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="43931-111">Wenn dieser Mitarbeiter in andere Teams, Standorte oder Abteilungen wechselt, müssen Sie sicherstellen, dass sein Zugang zu früheren Teams, Standorten oder Abteilungen bei Bedarf entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="43931-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="43931-112">Wenn dieser Mitarbeiter oder ein Gast Ihre Organisation verlässt, müssen Sie sicherstellen, dass sein Zugang entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="43931-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="43931-113">Dies ist besonders wichtig, falls Ihre Organisation Sicherheitsprüfungen unterzogen wird, um festzustellen, ob Benutzerkonten zu viel Zugriff haben. Ein Verstoß gegen branchenspezifische oder regionale Vorschriften kann zu Geldstrafen führen.</span><span class="sxs-lookup"><span data-stu-id="43931-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="43931-114">Weitere Informationen finden Sie in der [Übersicht über Access Reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span><span class="sxs-lookup"><span data-stu-id="43931-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="43931-115">Azure AD Privileged Identity Management (PIM) bietet zusätzliche Steuerungselemente zum Sichern des Zugriffs und Verwalten der Zugriffsrechte für Ressourcen in Azure AD, Azure und anderen Microsoft Cloud-Services.</span><span class="sxs-lookup"><span data-stu-id="43931-115">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="43931-116">Azure AD PIM stellt einen umfassenden Satz an Steuerungselementen bereit, mit deren Hilfe Sie Unternehmensressourcen wie z. B. Verzeichnis-, Office 365- und Azure-Ressourcenrollen schützen können.</span><span class="sxs-lookup"><span data-stu-id="43931-116">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="43931-117">Wie bei anderen Formen des Zugriffs können Organisationen mithilfe von Zugriffsüberprüfungen eine periodische erneute Zertifizierung für alle Benutzer mit Administratorrollen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="43931-117">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="43931-118">Azure AD PIM ist nur in Verbindung mit der E5-Version von Microsoft 365 Enterprise verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43931-118">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="43931-119">In diesen Artikeln finden Sie Informationen zur Konfiguration verschiedener Arten von Zugriffsüberprüfungen:</span><span class="sxs-lookup"><span data-stu-id="43931-119">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="43931-120">Gruppen und Apps</span><span class="sxs-lookup"><span data-stu-id="43931-120">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="43931-121">Azure AD-Rollen</span><span class="sxs-lookup"><span data-stu-id="43931-121">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="43931-122">Azure-Ressourcenrollen</span><span class="sxs-lookup"><span data-stu-id="43931-122">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="43931-123">Einrichten Azure AD Berechtigungsverwaltung</span><span class="sxs-lookup"><span data-stu-id="43931-123">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="43931-124">Wiht Azure AD Verwaltung von Berechtigungen können Sie den Identitäts-und Zugriffs Lebenszyklus in der Größenordnung verwalten, indem Sie Zugriffs Anforderungs Workflows, Zugriffs Zuweisungen, BEWERTUNGEN und Ablaufzeit automatisieren.</span><span class="sxs-lookup"><span data-stu-id="43931-124">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="43931-125">Ihre Mitarbeiter benötigen Zugriff auf verschiedene Gruppen, Anwendungen und Websites, um Ihre Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="43931-125">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="43931-126">Die Verwaltung dieses Zugriffs kann eine Herausforderung darstellen, da sich die Anforderungen ändern, neue Anwendungen hinzugefügt werden oder Benutzer zusätzliche Zugriffsrechte benötigen.</span><span class="sxs-lookup"><span data-stu-id="43931-126">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="43931-127">Wenn Sie mit anderen Organisationen zusammenarbeiten, wissen Sie möglicherweise nicht, wer in der anderen Organisation Zugriff auf die Ressourcen Ihrer Organisation benötigt, und dass externe Benutzer nicht wissen, welche Anwendungen, Gruppen oder Websites Ihre Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="43931-127">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="43931-128">Azure AD Verwaltung von Berechtigungen kann Ihnen helfen, den Zugriff auf Gruppen, Anwendungen und SharePoint-Websites für interne und externe Benutzer effizienter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="43931-128">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="43931-129">Weitere Informationen finden Sie in der [Übersicht über Azure AD Berechtigungsverwaltung](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span><span class="sxs-lookup"><span data-stu-id="43931-129">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
