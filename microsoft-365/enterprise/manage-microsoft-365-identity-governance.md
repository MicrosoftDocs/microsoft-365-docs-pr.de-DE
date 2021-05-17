---
title: Verwalten Microsoft 365 Identitätsverwaltung
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
description: Erfahren Sie mehr über die Verwendung Microsoft 365 Identitätsverwaltungsfeatures.
ms.openlocfilehash: 6a97ca24c609724a2cab93feec9e90f25d3361e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910954"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="37b5e-103">Verwalten Microsoft 365 Identitätsverwaltung</span><span class="sxs-lookup"><span data-stu-id="37b5e-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="37b5e-104">Bei der Identitätsgovernance geht es um den Schutz, die Kontrolle und die Überwachung von Zugriffen auf kritische Ressourcen bei gleichzeitiger Sicherstellung der Mitarbeiterproduktivität.</span><span class="sxs-lookup"><span data-stu-id="37b5e-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="37b5e-105">Beispielsweise können Sie mit Identitätsgovernance sicherstellen, dass die richtigen Benutzer den richtigen Zugriff auf die richtigen Ressourcen haben, und feststellen, ob sich dieser Zugriff im Laufe der Zeit ändert.</span><span class="sxs-lookup"><span data-stu-id="37b5e-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="37b5e-106">Weitere Informationen finden Sie in dieser Übersicht über die Identitätsverwaltung [für Azure Active Directory (Azure AD)](/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="37b5e-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="37b5e-107">Einrichten von Azure AD-Zugriffsüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="37b5e-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="37b5e-108">Mit Azure AD-Zugriffsüberprüfungen können Sie den Zugriff eines Benutzers überprüfen, um sicherzustellen, dass nur die richtigen Personen weiterhin Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="37b5e-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="37b5e-109">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="37b5e-109">For example:</span></span>

- <span data-ttu-id="37b5e-110">Wenn ein neuer Mitarbeiter in Ihre Organisation eintritt, müssen Sie sicherstellen, dass er den richtigen Zugriff hat, um produktiv zu sein.</span><span class="sxs-lookup"><span data-stu-id="37b5e-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="37b5e-111">Wenn dieser Mitarbeiter in andere Teams, Standorte oder Abteilungen wechselt, müssen Sie sicherstellen, dass sein Zugang zu früheren Teams, Standorten oder Abteilungen bei Bedarf entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="37b5e-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="37b5e-112">Wenn dieser Mitarbeiter oder ein Gast Ihre Organisation verlässt, müssen Sie sicherstellen, dass sein Zugang entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="37b5e-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="37b5e-113">Dies ist besonders wichtig, falls Ihre Organisation Sicherheitsprüfungen unterzogen wird, um festzustellen, ob Benutzerkonten zu viel Zugriff haben. Ein Verstoß gegen branchenspezifische oder regionale Vorschriften kann zu Geldstrafen führen.</span><span class="sxs-lookup"><span data-stu-id="37b5e-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="37b5e-114">Weitere Informationen finden Sie in der [Übersicht über Zugriffsüberprüfungen](/azure/active-directory/governance/access-reviews-overview).</span><span class="sxs-lookup"><span data-stu-id="37b5e-114">For more information, see the [overview of access reviews](/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="37b5e-115">In diesen Artikeln finden Sie Informationen zur Konfiguration verschiedener Arten von Zugriffsüberprüfungen:</span><span class="sxs-lookup"><span data-stu-id="37b5e-115">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="37b5e-116">Gruppen und Apps</span><span class="sxs-lookup"><span data-stu-id="37b5e-116">Groups and apps</span></span>](/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="37b5e-117">Azure AD-Rollen</span><span class="sxs-lookup"><span data-stu-id="37b5e-117">Azure AD roles</span></span>](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="37b5e-118">Azure-Ressourcenrollen</span><span class="sxs-lookup"><span data-stu-id="37b5e-118">Azure resource roles</span></span>](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="37b5e-119">Einrichten der Azure AD-Berechtigungsverwaltung</span><span class="sxs-lookup"><span data-stu-id="37b5e-119">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="37b5e-120">Wiht Azure AD-Berechtigungsverwaltung, können Sie den Identitäts- und Zugriffslebenszyklus im großen Maßstab verwalten, indem Sie Zugriffsanforderungsworkflows, Zugriffszuweisungen, Überprüfungen und Ablauf automatisieren.</span><span class="sxs-lookup"><span data-stu-id="37b5e-120">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="37b5e-121">Ihre Mitarbeiter benötigen Zugriff auf verschiedene Gruppen, Anwendungen und Websites, um ihre Aufgabe ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="37b5e-121">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="37b5e-122">Die Verwaltung dieses Zugriffs kann schwierig sein, da sich die Anforderungen ändern, neue Anwendungen hinzugefügt werden oder Benutzer zusätzliche Zugriffsrechte benötigen.</span><span class="sxs-lookup"><span data-stu-id="37b5e-122">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="37b5e-123">Wenn Sie mit anderen Organisationen zusammenarbeiten, wissen Sie möglicherweise nicht, wer in der anderen Organisation Zugriff auf die Ressourcen Ihrer Organisation benötigt, und externe Benutzer wissen nicht, welche Anwendungen, Gruppen oder Websites Ihre Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="37b5e-123">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="37b5e-124">Azure AD-Berechtigungsverwaltung kann Ihnen dabei helfen, den Zugriff auf Gruppen, Anwendungen und SharePoint für interne und externe Benutzer effizienter zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="37b5e-124">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="37b5e-125">Weitere Informationen finden Sie in [der Übersicht über die Azure AD-Berechtigungsverwaltung](/azure/active-directory/governance/entitlement-management-overview).</span><span class="sxs-lookup"><span data-stu-id="37b5e-125">For more information, see the [overview of Azure AD entitlement management](/azure/active-directory/governance/entitlement-management-overview).</span></span>