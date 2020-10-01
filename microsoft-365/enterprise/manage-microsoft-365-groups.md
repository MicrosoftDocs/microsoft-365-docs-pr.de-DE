---
title: Verwalten von Microsoft 365-Gruppen
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
description: Hier erfahren Sie, wie Sie Microsoft 365-Gruppen verwalten.
ms.openlocfilehash: a01bf5dcc0b87cbdce8d7044b666cfb3a16a5aa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328522"
---
# <a name="manage-microsoft-365-groups"></a><span data-ttu-id="1f92e-103">Verwalten von Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="1f92e-103">Manage Microsoft 365 groups</span></span>

<span data-ttu-id="1f92e-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1f92e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1f92e-105">Je nach Konfiguration können Sie Microsoft 365-Gruppen auf verschiedene Arten verwalten.</span><span class="sxs-lookup"><span data-stu-id="1f92e-105">You can manage Microsoft 365 groups in several different ways, depending on your configuration.</span></span> <span data-ttu-id="1f92e-106">Sie können Benutzerkonten im [Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/add-users/), in PowerShell, in Active Directory-Domänendienste (AD DS) oder im [Azure Active Directory (Azure AD) Admin Center](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)verwalten.</span><span class="sxs-lookup"><span data-stu-id="1f92e-106">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), PowerShell, in Active Directory Domain Services (AD DS), or in the [Azure Active Directory (Azure AD) admin center](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span> 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a><span data-ttu-id="1f92e-107">Planen, wo und wie Sie Ihre Gruppen verwalten werden</span><span class="sxs-lookup"><span data-stu-id="1f92e-107">Plan for where and how you will manage your groups</span></span>

<span data-ttu-id="1f92e-108">Wo und wie Sie Ihre Benutzerkonten verwalten können, hängt vom Identitätsmodell ab, das Sie für Ihre Microsoft 365 verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1f92e-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="1f92e-109">Die beiden Gesamt Modelle sind nur in der Cloud und Hybrid.</span><span class="sxs-lookup"><span data-stu-id="1f92e-109">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="1f92e-110">Rein cloudbasiert</span><span class="sxs-lookup"><span data-stu-id="1f92e-110">Cloud-only</span></span>

<span data-ttu-id="1f92e-111">Sie erstellen und verwalten Gruppen mit:</span><span class="sxs-lookup"><span data-stu-id="1f92e-111">You create and manage groups with:</span></span>

- [<span data-ttu-id="1f92e-112">Das Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="1f92e-112">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="1f92e-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f92e-113">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1f92e-114">Azure AD Admin Center</span><span class="sxs-lookup"><span data-stu-id="1f92e-114">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a><span data-ttu-id="1f92e-115">Hybrid</span><span class="sxs-lookup"><span data-stu-id="1f92e-115">Hybrid</span></span>

<span data-ttu-id="1f92e-116">AD DS Gruppen werden mit Microsoft 365 von AD DS synchronisiert, daher müssen Sie lokale AD DS Tools verwenden, um diese Gruppen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="1f92e-116">AD DS groups are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage these groups.</span></span>

<span data-ttu-id="1f92e-117">Sie können auch Azure Ad Gruppen erstellen und verwalten, die von AD DS Gruppen getrennt sind, aber Benutzer und Gruppen aus AD DS enthalten können.</span><span class="sxs-lookup"><span data-stu-id="1f92e-117">You can also create and manage Azure AD groups that are separate from AD DS groups but can contain users and groups from AD DS.</span></span> <span data-ttu-id="1f92e-118">In diesem Fall können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="1f92e-118">In this case, you can use:</span></span>

- [<span data-ttu-id="1f92e-119">Das Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="1f92e-119">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="1f92e-120">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f92e-120">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1f92e-121">Azure AD Admin Center</span><span class="sxs-lookup"><span data-stu-id="1f92e-121">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="1f92e-122">Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="1f92e-122">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="1f92e-123">Azure AD ermöglicht Gruppen, die von Gruppenbesitzern anstelle von IT-Administratoren verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="1f92e-123">Azure AD allows groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="1f92e-124">Diese Funktion, bekannt als *Self-Service-Gruppenverwaltung*, ermöglicht es Gruppenbesitzern, denen keine Administratorrolle zugewiesen ist, Sicherheitsgruppen zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="1f92e-124">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="1f92e-p105">Benutzer können die Mitgliedschaft in einer Sicherheitsgruppe anfordern, und die Anforderung wird an den Gruppenbesitzer gesendet, statt an den IT-Administrator. So kann die tägliche Kontrolle über Gruppenmitgliedschaften an die Team-, Projekt- oder Unternehmensbesitzer delegiert werden, die die geschäftliche Verwendung für die Gruppe verstehen und die Mitgliedschaften verwalten können.</span><span class="sxs-lookup"><span data-stu-id="1f92e-p105">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="1f92e-127">Self-Service-Gruppenverwaltung ist nur für Azure AD-Sicherheitsgruppen und Microsoft 365-Gruppen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1f92e-127">Self-service group management is available only for Azure AD security and Microsoft 365 groups.</span></span> <span data-ttu-id="1f92e-128">Sie ist für e-Mail-aktivierte Gruppen, Verteilerlisten oder Gruppen, die von AD DS synchronisiert wurden, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1f92e-128">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from AD DS.</span></span>
>

<span data-ttu-id="1f92e-129">Weitere Informationen finden Sie in den [Anweisungen zum Konfigurieren einer Azure AD-Gruppe für Self-Service-Verwaltung](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="1f92e-129">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="1f92e-130">Einrichten der dynamischen Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="1f92e-130">Set up dynamic group membership</span></span>

<span data-ttu-id="1f92e-131">Azure Ad unterstützt das Konfigurieren einer Reihe von Regeln, die Benutzerkonten automatisch als Mitglieder einer Azure Ad Gruppe hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="1f92e-131">Azure AD supports configuring a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="1f92e-132">Dies ist als *dynamische Gruppenmitgliedschaft* bekannt.</span><span class="sxs-lookup"><span data-stu-id="1f92e-132">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="1f92e-133">Die Regeln basieren auf Benutzerkontoattributen, wie Abteilung oder Land.</span><span class="sxs-lookup"><span data-stu-id="1f92e-133">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="1f92e-134">Die Regeln werden wie folgt angewendet:</span><span class="sxs-lookup"><span data-stu-id="1f92e-134">Here's how the rules are applied:</span></span>

- <span data-ttu-id="1f92e-135">Wenn ein neues Benutzerkonto allen Regeln für die Gruppe entspricht, wird es ein Mitglied.</span><span class="sxs-lookup"><span data-stu-id="1f92e-135">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="1f92e-136">Wenn ein Benutzerkonto kein Mitglied der Gruppe ist, aber sich seine Attribute ändern, sodass es allen Regeln für die Gruppe entspricht, wird es ein Mitglied dieser Gruppe.</span><span class="sxs-lookup"><span data-stu-id="1f92e-136">If a user account isn't a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="1f92e-137">Wenn ein Benutzerkonto nicht allen Regeln für die Gruppe entspricht, wird es nicht zur Gruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1f92e-137">If a user account doesn't match all the rules for the group, it isn't added to the group.</span></span>
- <span data-ttu-id="1f92e-138">Wenn ein Benutzerkonto Mitglied der Gruppe ist, aber sich seine Attribute ändern, sodass es nicht mehr allen Regeln für die Gruppe entspricht, wird es als Mitglied der Gruppe entfernt.</span><span class="sxs-lookup"><span data-stu-id="1f92e-138">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="1f92e-p108">Um die dynamische Mitgliedschaft zu verwenden, müssen Sie zuerst die Sätze von Gruppen mit einem gemeinsamen Satz von Benutzerkonto-Attributen bestimmen. Beispielsweise sollten alle Mitglieder der Vertriebsabteilung Teil der Azure AD-Gruppe „Vertrieb“ sein, basierend auf dem Benutzerkonto-Attribut „Abteilung“ = „Vertrieb“.</span><span class="sxs-lookup"><span data-stu-id="1f92e-p108">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to "Sales".</span></span>

<span data-ttu-id="1f92e-141">Lesen Sie die [Anweisungen, um die Regeln für eine dynamische Azure AD-Gruppe zu erstellen und zu konfigurieren](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="1f92e-141">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

## <a name="set-up-automatic-licensing"></a><span data-ttu-id="1f92e-142">Einrichten der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="1f92e-142">Set up automatic licensing</span></span>

<span data-ttu-id="1f92e-143">Sie können Sicherheitsgruppen in Azure AD so konfigurieren, dass Lizenzen automatisch aus einer Gruppe von Abonnements für alle Mitglieder der Gruppe zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1f92e-143">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="1f92e-144">Dies wird als *gruppenbasierte Lizenzierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1f92e-144">This is known as *group-based licensing*.</span></span> <span data-ttu-id="1f92e-145">Wenn ein Benutzerkonto der Gruppe hinzugefügt oder aus ihr entfernt wird, werden die Lizenzen für die Gruppenabonnements dem Benutzerkonto automatisch zugewiesen, bzw. die Zuweisung wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="1f92e-145">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="1f92e-146">Für Microsoft 365 Enterprise konfigurieren Sie Azure AD-Sicherheitsgruppen, um die passenden Microsoft 365 Enterprise-Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="1f92e-146">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="1f92e-147">Stellen Sie sicher, dass Sie genug Lizenzen für alle Gruppenmitglieder haben.</span><span class="sxs-lookup"><span data-stu-id="1f92e-147">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="1f92e-148">Wenn keine Lizenzen mehr vorhanden sind, werden neuen Benutzern keine Lizenzen zugewiesen, bis Lizenzen verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="1f92e-148">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="1f92e-149">Sie sollten  nicht die gruppenbasierte Lizenzierung für Gruppen konfigurieren, die Azure Business to Business (B2B)-Konten enthalten.</span><span class="sxs-lookup"><span data-stu-id="1f92e-149">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="1f92e-150">Weitere Informationen finden Sie unter [Grundlegendes zur gruppenbasierten Lizenzierung in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="1f92e-150">For more information, see [Group-based licensing basics in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="1f92e-151">Lesen Sie die [Anweisungen zum Konfigurieren der gruppenbasierten Lizenzierung für eine Azure-Sicherheitsgruppe](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="1f92e-151">See the [instructions to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>
