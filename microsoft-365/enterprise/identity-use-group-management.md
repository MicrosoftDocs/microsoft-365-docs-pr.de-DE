---
title: 'Schritt 5: Verwenden von Gruppen zur Verwaltung'
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
description: Sie können Gruppen verwenden, um die Verwaltung bestimmter administrativer Aufgaben zu automatisieren.
ms.openlocfilehash: 215bb84cbb0cedc2f1320372ba8239cd51d07c98
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633493"
---
# <a name="step-5-use-groups-for-management"></a><span data-ttu-id="23e43-103">Schritt 5: Verwenden von Gruppen zur Verwaltung</span><span class="sxs-lookup"><span data-stu-id="23e43-103">Step 5: Use groups for management</span></span>

![Phase 2: Identität](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="23e43-105">Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="23e43-105">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="23e43-106">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="23e43-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="23e43-107">In diesem Abschnitt identifizieren Sie Azure Active Directory(Azure AD)-Gruppen, die von Gruppenbesitzern anstelle von IT-Administratoren verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="23e43-107">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="23e43-108">Diese Funktion, bekannt als *Self-Service-Gruppenverwaltung*, ermöglicht es Gruppenbesitzern, denen keine Administratorrolle zugewiesen ist, Sicherheitsgruppen zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="23e43-108">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="23e43-p102">Benutzer können die Mitgliedschaft in einer Sicherheitsgruppe anfordern, und die Anforderung wird an den Gruppenbesitzer gesendet, statt an den IT-Administrator. So kann die tägliche Kontrolle über Gruppenmitgliedschaften an die Team-, Projekt- oder Unternehmensbesitzer delegiert werden, die die geschäftliche Verwendung für die Gruppe verstehen und die Mitgliedschaften verwalten können.</span><span class="sxs-lookup"><span data-stu-id="23e43-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="23e43-111">Self-Service-Gruppenverwaltung ist nur für Azure AD-Sicherheitsgruppen und Office 365-Gruppen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="23e43-111">Self-service group management is available only for Azure AD security and Office 365 groups.</span></span> <span data-ttu-id="23e43-112">Sie ist nicht für E-Mail-aktivierte Gruppen, Verteilerlisten oder andere Gruppen verfügbar, die aus den lokalen Active Directory Domain Services (AD DS) synchronisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="23e43-112">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Active Directory Domain Services (AD DS).</span></span>
>

<span data-ttu-id="23e43-113">Weitere Informationen finden Sie in den [Anweisungen zum Konfigurieren einer Azure AD-Gruppe für Self-Service-Verwaltung](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="23e43-113">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="23e43-114">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-self-service-groups) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="23e43-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this section.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="23e43-115">Einrichten der dynamischen Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="23e43-115">Set up dynamic group membership</span></span>

<span data-ttu-id="23e43-116">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="23e43-116">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="23e43-117">In diesem Abschnitt erstellen Sie eine Reihe von Regeln, die automatisch Benutzerkonten als Mitglieder einer Azure AD-Gruppe hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="23e43-117">In this section, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="23e43-118">Dies ist als *dynamische Gruppenmitgliedschaft* bekannt.</span><span class="sxs-lookup"><span data-stu-id="23e43-118">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="23e43-119">Die Regeln basieren auf Benutzerkontoattributen, wie Abteilung oder Land.</span><span class="sxs-lookup"><span data-stu-id="23e43-119">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="23e43-120">Die Regeln werden wie folgt angewendet:</span><span class="sxs-lookup"><span data-stu-id="23e43-120">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="23e43-121">Wenn ein neues Benutzerkonto allen Regeln für die Gruppe entspricht, wird es ein Mitglied.</span><span class="sxs-lookup"><span data-stu-id="23e43-121">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="23e43-122">Wenn ein Benutzerkonto kein Mitglied der Gruppe ist, aber sich seine Attribute ändern, sodass es allen Regeln für die Gruppe entspricht, wird es ein Mitglied dieser Gruppe.</span><span class="sxs-lookup"><span data-stu-id="23e43-122">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="23e43-123">Wenn ein Benutzerkonto nicht allen Regeln für die Gruppe entspricht, wird es nicht zur Gruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23e43-123">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="23e43-124">Wenn ein Benutzerkonto Mitglied der Gruppe ist, aber sich seine Attribute ändern, sodass es nicht mehr allen Regeln für die Gruppe entspricht, wird es als Mitglied der Gruppe entfernt.</span><span class="sxs-lookup"><span data-stu-id="23e43-124">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="23e43-p105">Um die dynamische Mitgliedschaft zu verwenden, müssen Sie zuerst die Sätze von Gruppen mit einem gemeinsamen Satz von Benutzerkonto-Attributen bestimmen. Beispielsweise sollten alle Mitglieder der Vertriebsabteilung Teil der Azure AD-Gruppe „Vertrieb“ sein, basierend auf dem Benutzerkonto-Attribut „Abteilung“ = „Vertrieb“.</span><span class="sxs-lookup"><span data-stu-id="23e43-p105">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="23e43-127">Lesen Sie die [Anweisungen, um die Regeln für eine dynamische Azure AD-Gruppe zu erstellen und zu konfigurieren](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="23e43-127">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="23e43-128">Die Ergebnisse dieses Abschnitts sind:</span><span class="sxs-lookup"><span data-stu-id="23e43-128">The results of this section are:</span></span>

- <span data-ttu-id="23e43-129">Ein Satz von Azure AD-Gruppen, die für die dynamische Mitgliedschaft konfiguriert werden können</span><span class="sxs-lookup"><span data-stu-id="23e43-129">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="23e43-130">Ein Satz von Regeln für jede dynamische Gruppe</span><span class="sxs-lookup"><span data-stu-id="23e43-130">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="23e43-132">Testumgebungsanleitung: Automatisieren von Lizenzen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="23e43-132">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="23e43-133">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-dyn-groups) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="23e43-133">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this section.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="23e43-134">Einrichten der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="23e43-134">Set up automatic licensing</span></span>

<span data-ttu-id="23e43-135">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="23e43-135">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="23e43-136">In diesem Abschnitt konfigurieren Sie Sicherheitsgruppen in Azure AD, um automatisch Lizenzen aus einer Gruppe von Abonnements zu allen Mitgliedern der Gruppe zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="23e43-136">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="23e43-137">Dies wird als *gruppenbasierte Lizenzierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="23e43-137">This is known as *group-based licensing*.</span></span> <span data-ttu-id="23e43-138">Wenn ein Benutzerkonto der Gruppe hinzugefügt oder aus ihr entfernt wird, werden die Lizenzen für die Gruppenabonnements dem Benutzerkonto automatisch zugewiesen, bzw. die Zuweisung wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="23e43-138">If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="23e43-139">Für Microsoft 365 Enterprise konfigurieren Sie Azure AD-Sicherheitsgruppen, um die passenden Microsoft 365 Enterprise-Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="23e43-139">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="23e43-140">Stellen Sie sicher, dass Sie genug Lizenzen für alle Gruppenmitglieder haben.</span><span class="sxs-lookup"><span data-stu-id="23e43-140">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="23e43-141">Wenn keine Lizenzen mehr vorhanden sind, werden neuen Benutzern keine Lizenzen zugewiesen, bis Lizenzen verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="23e43-141">If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="23e43-142">Sie sollten  nicht die *gruppenbasierte Lizenzierung* für Gruppen konfigurieren, die Azure Business to Business (B2B)-Konten enthalten.</span><span class="sxs-lookup"><span data-stu-id="23e43-142">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="23e43-143">Weitere Informationen finden Sie unter [Grundlagen der gruppenbasierten Lizenzierung in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="23e43-143">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="23e43-144">Lesen Sie die [Schritte zum Konfigurieren der gruppenbasierten Lizenzierung für eine Azure-Sicherheitsgruppe](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="23e43-144">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="23e43-145">Die Ergebnisse dieses Abschnitts sind:</span><span class="sxs-lookup"><span data-stu-id="23e43-145">The results of this section are:</span></span>

- <span data-ttu-id="23e43-146">Sie haben identifiziert, welche Sicherheitsgruppen für die gruppenbasierte Lizenzierung geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="23e43-146">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="23e43-147">Sie haben diese Gruppen für gruppenbasierte Lizenzierung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="23e43-147">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="23e43-149">Testumgebungsanleitung: Automatisieren von Lizenzen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="23e43-149">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="23e43-150">Als Zwischenprüfung können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-group-license) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="23e43-150">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this section.</span></span>

|||
|:-------|:-----|
|![Schritt 6](../media/stepnumbers/Step6.png)| [<span data-ttu-id="23e43-152">Konfigurieren der Identitätsgovernance</span><span class="sxs-lookup"><span data-stu-id="23e43-152">Configure identity governance</span></span>](identity-configure-identity-governance.md) |
