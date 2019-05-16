---
title: 'Schritt 6: Verwenden von Gruppen zur einfacheren Verwaltung'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen zum Verständnis und zur Konfiguration der Self-Service-Gruppenverwaltung in Azure AD.
ms.openlocfilehash: 67c3a0e45fa253bdaedead03ac1137422ee0f8de
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073605"
---
# <a name="step-6-use-groups-for-easier-management"></a><span data-ttu-id="b05e5-103">Schritt 6: Verwenden von Gruppen zur einfacheren Verwaltung</span><span class="sxs-lookup"><span data-stu-id="b05e5-103">Step 6: Use groups for easier management</span></span>

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="b05e5-104">Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="b05e5-104">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="b05e5-105">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b05e5-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b05e5-106">In diesem Abschnitt identifizieren Sie Azure Active Directory(Azure AD)-Gruppen, die von Gruppenbesitzern anstelle von IT-Administratoren verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="b05e5-106">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="b05e5-107">Diese Funktion, bekannt als *Self-Service-Gruppenverwaltung*, ermöglicht es Gruppenbesitzern, denen keine Administratorrolle zugewiesen ist, Sicherheitsgruppen zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b05e5-107">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="b05e5-p102">Benutzer können die Mitgliedschaft in einer Sicherheitsgruppe anfordern, und die Anforderung wird an den Gruppenbesitzer gesendet, statt an den IT-Administrator. So kann die tägliche Kontrolle über Gruppenmitgliedschaften an die Team-, Projekt- oder Unternehmensbesitzer delegiert werden, die die geschäftliche Verwendung für die Gruppe verstehen und die Mitgliedschaften verwalten können.</span><span class="sxs-lookup"><span data-stu-id="b05e5-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="b05e5-110">Self-Service-Gruppenverwaltung ist nur für Azure AD-Sicherheitsgruppen und Office 365-Gruppen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b05e5-110">Self-service group management is available only for Azure AD security and Office 365 groups.</span></span> <span data-ttu-id="b05e5-111">Sie ist nicht für E-Mail-aktivierte Gruppen, Verteilerlisten oder andere Gruppen verfügbar, die aus den lokalen Active Directory Domain Services (AD DS) synchronisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b05e5-111">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Active Directory Domain Services (AD DS).</span></span>
>

<span data-ttu-id="b05e5-112">Weitere Informationen finden Sie in den [Anweisungen zum Konfigurieren einer Azure AD-Gruppe für Self-Service-Verwaltung](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="b05e5-112">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="b05e5-113">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-self-service-groups) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="b05e5-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this section.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="b05e5-114">Einrichten der dynamischen Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="b05e5-114">Set up dynamic group membership</span></span>

<span data-ttu-id="b05e5-115">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b05e5-115">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b05e5-116">In diesem Abschnitt erstellen Sie eine Reihe von Regeln, die automatisch Benutzerkonten als Mitglieder einer Azure AD-Gruppe hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="b05e5-116">In this section, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="b05e5-117">Dies ist als *dynamische Gruppenmitgliedschaft* bekannt.</span><span class="sxs-lookup"><span data-stu-id="b05e5-117">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="b05e5-118">Die Regeln basieren auf Benutzerkontoattributen, wie Abteilung oder Land.</span><span class="sxs-lookup"><span data-stu-id="b05e5-118">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="b05e5-119">Die Regeln werden wie folgt angewendet:</span><span class="sxs-lookup"><span data-stu-id="b05e5-119">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="b05e5-120">Wenn ein neues Benutzerkonto allen Regeln für die Gruppe entspricht, wird es ein Mitglied.</span><span class="sxs-lookup"><span data-stu-id="b05e5-120">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="b05e5-121">Wenn ein Benutzerkonto kein Mitglied der Gruppe ist, aber sich seine Attribute ändern, sodass es allen Regeln für die Gruppe entspricht, wird es ein Mitglied dieser Gruppe.</span><span class="sxs-lookup"><span data-stu-id="b05e5-121">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="b05e5-122">Wenn ein Benutzerkonto nicht allen Regeln für die Gruppe entspricht, wird es nicht zur Gruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b05e5-122">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="b05e5-123">Wenn ein Benutzerkonto Mitglied der Gruppe ist, aber sich seine Attribute ändern, sodass es nicht mehr allen Regeln für die Gruppe entspricht, wird es als Mitglied der Gruppe entfernt.</span><span class="sxs-lookup"><span data-stu-id="b05e5-123">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="b05e5-p105">Um die dynamische Mitgliedschaft zu verwenden, müssen Sie zuerst die Sätze von Gruppen mit einem gemeinsamen Satz von Benutzerkonto-Attributen bestimmen. Beispielsweise sollten alle Mitglieder der Vertriebsabteilung Teil der Azure AD-Gruppe „Vertrieb“ sein, basierend auf dem Benutzerkonto-Attribut „Abteilung“ = „Vertrieb“.</span><span class="sxs-lookup"><span data-stu-id="b05e5-p105">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="b05e5-126">Lesen Sie die [Anweisungen, um die Regeln für eine dynamische Azure AD-Gruppe zu erstellen und zu konfigurieren](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="b05e5-126">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="b05e5-127">Die Ergebnisse dieses Abschnitts sind:</span><span class="sxs-lookup"><span data-stu-id="b05e5-127">The results of this section are:</span></span>

- <span data-ttu-id="b05e5-128">Ein Satz von Azure AD-Gruppen, die für die dynamische Mitgliedschaft konfiguriert werden können</span><span class="sxs-lookup"><span data-stu-id="b05e5-128">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="b05e5-129">Ein Satz von Regeln für jede dynamische Gruppe</span><span class="sxs-lookup"><span data-stu-id="b05e5-129">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b05e5-131">Testumgebungsanleitung: Automatisieren von Lizenzen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="b05e5-131">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="b05e5-132">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-dyn-groups) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="b05e5-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this section.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="b05e5-133">Einrichten der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="b05e5-133">Set up automatic licensing</span></span>

<span data-ttu-id="b05e5-134">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b05e5-134">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b05e5-135">In diesem Abschnitt konfigurieren Sie Sicherheitsgruppen in Azure AD, um automatisch Lizenzen aus einer Gruppe von Abonnements zu allen Mitgliedern der Gruppe zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="b05e5-135">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="b05e5-136">Dies wird als *gruppenbasierte Lizenzierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b05e5-136">This is known as *group-based licensing*.</span></span> <span data-ttu-id="b05e5-137">Wenn ein Benutzerkonto der Gruppe hinzugefügt oder aus ihr entfernt wird, werden die Lizenzen für die Gruppenabonnements dem Benutzerkonto automatisch zugewiesen oder aus ihm entfernt.</span><span class="sxs-lookup"><span data-stu-id="b05e5-137">If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="b05e5-138">Für Microsoft 365 Enterprise konfigurieren Sie Azure AD-Sicherheitsgruppen, um beide Lizenzen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="b05e5-138">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="b05e5-139">Office 365 Enterprise E3 oder E5</span><span class="sxs-lookup"><span data-stu-id="b05e5-139">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="b05e5-140">Enterprise Mobility + Security (EMS) E3 oder E5</span><span class="sxs-lookup"><span data-stu-id="b05e5-140">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="b05e5-p107">Suchen Sie unter Verwendung der Gruppen, die Sie in Schritt 2 identifiziert haben, nach Gruppen, die eine Liste der Konten enthalten, wobei alle Benutzer in dieser Gruppe Office 365- und EMS-Lizenzen haben müssen. Stellen Sie sicher, dass Sie genug Lizenzen für alle Gruppenmitglieder haben. Wenn keine Lizenzen mehr vorhanden sind, werden neuen Benutzern keine Lizenzen zugewiesen, bis Lizenzen verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="b05e5-p107">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="b05e5-144">Sie sollten  nicht die *gruppenbasierte Lizenzierung* für Gruppen konfigurieren, die Azure Business to Business (B2B)-Konten enthalten.</span><span class="sxs-lookup"><span data-stu-id="b05e5-144">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="b05e5-145">Weitere Informationen finden Sie unter [Grundlagen der gruppenbasierten Lizenzierung in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="b05e5-145">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="b05e5-146">Lesen Sie die [Schritte zum Konfigurieren der gruppenbasierten Lizenzierung für eine Azure-Sicherheitsgruppe](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="b05e5-146">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="b05e5-147">Die Ergebnisse dieses Abschnitts sind:</span><span class="sxs-lookup"><span data-stu-id="b05e5-147">The results of this section are:</span></span>

- <span data-ttu-id="b05e5-148">Sie haben identifiziert, welche Sicherheitsgruppen für die gruppenbasierte Lizenzierung geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="b05e5-148">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="b05e5-149">Sie haben diese Gruppen für gruppenbasierte Lizenzierung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="b05e5-149">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b05e5-151">Testumgebungsanleitung: Automatisieren von Lizenzen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="b05e5-151">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="b05e5-152">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-group-license) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="b05e5-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="b05e5-153">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b05e5-153">Next step</span></span>

[<span data-ttu-id="b05e5-154">Beendigungskriterien für die Identitätsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="b05e5-154">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)
