---
title: Zuweisen von Administratorrollen zum Microsoft 365 Admin Center
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Erfahren Sie, wie Sie einem Benutzer oder mehreren Benutzern in Ihrem Unternehmen Administratorrollen zuweisen, damit sie bestimmte Aufgaben im Admin Center ausführen können.
ms.openlocfilehash: c723053d8d1a39bf0f996840bc418ffe299db089
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023989"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="0291f-103">Zuweisen von Administratorrollen</span><span class="sxs-lookup"><span data-stu-id="0291f-103">Assign admin roles</span></span>

<span data-ttu-id="0291f-104">Wenn Sie die Person sind, die Ihr Microsoft Business-Abonnement erworben hat, sind Sie der globale Administrator. Dies bedeutet, dass Sie unbegrenzte Kontrolle über die Produkte in Ihren Abonnements haben und auf die meisten Daten zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="0291f-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="0291f-105">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0291f-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="0291f-106">Wenn Sie neue Benutzer hinzufügen und ihnen keine Administratorrolle zuweisen,  befinden sie sich in der Benutzerrolle und verfügen nicht über Administratorrechte für die Microsoft Admin Center.</span><span class="sxs-lookup"><span data-stu-id="0291f-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="0291f-107">Wenn Sie jedoch Hilfe beim Erledigen von Aufgaben benötigen, können Sie einem Benutzer eine Administratorrolle zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0291f-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="0291f-108">Wenn Sie z. B. eine Person benötigen, die beim Zurücksetzen von Kennwörtern helfen soll, sollten Sie ihnen nicht die globale Administratorrolle zuweisen, sondern ihnen die Administratorrolle kennwort zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0291f-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="0291f-109">Zu viele globale Administratoren mit unbegrenztem Zugriff auf Ihre Daten und Ihr Onlinegeschäft zu ernennen, stellt ein Sicherheitsrisiko dar.</span><span class="sxs-lookup"><span data-stu-id="0291f-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

## <a name="watch-add-an-adminbrbr"></a><span data-ttu-id="0291f-110">Watch: Add an admin.</span><span class="sxs-lookup"><span data-stu-id="0291f-110">Watch: Add an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="0291f-111">Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../../business-video/index.yml) an.</span><span class="sxs-lookup"><span data-stu-id="0291f-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="assign-admin-roles"></a><span data-ttu-id="0291f-112">Zuweisen von Administratorrollen</span><span class="sxs-lookup"><span data-stu-id="0291f-112">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="0291f-113">Sie können einer Rolle auf 2 unterschiedliche Weise Benutzer zuweisen:</span><span class="sxs-lookup"><span data-stu-id="0291f-113">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="0291f-114">Sie können zu den Details des Benutzers wechseln und **Rollen** verwalten, um dem Benutzer eine Rolle zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="0291f-114">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="0291f-115">Sie können auch zu **Rollen** wechseln und die Rolle auswählen und dann mehrere Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0291f-115">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="0291f-116">Zuweisen von Administratorrollen zu Benutzern mithilfe von Rollen</span><span class="sxs-lookup"><span data-stu-id="0291f-116">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="0291f-117">Wechseln Sie im Admin Center zu **Rollen**.</span><span class="sxs-lookup"><span data-stu-id="0291f-117">In the admin center, go to **Roles**.</span></span> <span data-ttu-id="0291f-118">Wählen Sie **die Registerkarten Azure AD** oder **Intune** aus, um die für Ihre Organisation verfügbaren Administratorrollen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="0291f-118">Choose the **Azure AD** or **Intune** tabs to view the admin roles available for your organization.</span></span>
2. <span data-ttu-id="0291f-119">Wählen Sie die Administratorrolle aus, der Sie den Benutzer zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="0291f-119">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="0291f-120">Wählen **Sie Zugewiesene Administratoren** Hinzufügen > **aus.**</span><span class="sxs-lookup"><span data-stu-id="0291f-120">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="0291f-121">Geben Sie den **Anzeigenamen oder** Benutzernamen des Benutzers **ein,** und wählen Sie dann den Benutzer aus der Liste der Vorschläge aus.</span><span class="sxs-lookup"><span data-stu-id="0291f-121">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="0291f-122">Fügen Sie mehrere Benutzer hinzu, bis Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="0291f-122">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="0291f-123">Wählen **Sie Speichern** aus, und dann wird der Benutzer der Liste der zugewiesenen Administratoren hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0291f-123">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="0291f-124">Zuweisen eines Benutzers zu einer Administratorrolle über "Aktive Benutzer"</span><span class="sxs-lookup"><span data-stu-id="0291f-124">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="0291f-125">Wechseln Sie im Admin Center zu **Seite Aktive** > [Benutzer.](https://go.microsoft.com/fwlink/p/?linkid=834822)</span><span class="sxs-lookup"><span data-stu-id="0291f-125">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="0291f-126">Wählen Sie **auf der Seite** Aktive Benutzer den Benutzer aus, dessen Administratorrolle Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="0291f-126">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="0291f-127">Wählen Sie im Flyoutbereich unter **Rollen** die Option Rollen **verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="0291f-127">In the flyout pane, under **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="0291f-128">Wählen Sie die Administratorrolle aus, die Sie dem Benutzer zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="0291f-128">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="0291f-129">Wenn die gesuchte Rolle nicht angezeigt wird, wählen Sie **am** Ende der Liste Alle anzeigen aus.</span><span class="sxs-lookup"><span data-stu-id="0291f-129">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0291f-130">Wechseln Sie im Admin Center zu der Seite **Benutzer** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="0291f-130">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="0291f-131">Wählen Sie **auf der Seite** Aktive Benutzer den Benutzer aus, dessen Administratorrolle Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="0291f-131">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="0291f-132">Wählen Sie im Flyoutbereich neben **Rollen** die Option **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="0291f-132">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="0291f-133">Wenn die Option Bearbeiten  nicht angezeigt wird, verfügen Sie nicht über die Berechtigung zum Bearbeiten und können anderen Personen keine Administratorrollen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0291f-133">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="0291f-134">Bitten Sie einen globalen Administrator in Ihrem Unternehmen, Ihnen Rollen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="0291f-134">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="0291f-135">In einem kleinen Unternehmen ist der Geschäftsbesitzer (die Person, die Ihr Abonnement erworben hat) ein globaler Administrator. In einem großen Unternehmen sind die wichtigsten Mitarbeiter der IT-Abteilung globale Administratoren.</span><span class="sxs-lookup"><span data-stu-id="0291f-135">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="0291f-136">Wählen **Sie Angepasster Administrator** aus, um eine Liste der Rollen zu sehen, die wir für Sie angepasst haben.</span><span class="sxs-lookup"><span data-stu-id="0291f-136">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="0291f-137">Eine Beschreibung der einzelnen Rollen finden Sie unter [Informationen zu Administratorrollen.](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0291f-137">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0291f-138">Wechseln Sie im Admin Center zu der Seite **Benutzer** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="0291f-138">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="0291f-139">Wählen Sie **auf der Seite** Aktive Benutzer den Benutzer aus, dessen Administratorrolle Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="0291f-139">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="0291f-140">Wählen Sie im Flyoutbereich neben **Rollen** die Option **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="0291f-140">In the flyout pane, next to **Roles**, select **Edit**.</span></span>

    <span data-ttu-id="0291f-141">Wenn die Option Bearbeiten  nicht angezeigt wird, verfügen Sie nicht über die Berechtigung zum Bearbeiten und können anderen Personen keine Administratorrollen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0291f-141">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="0291f-142">Bitten Sie einen globalen Administrator in Ihrem Unternehmen, Ihnen Rollen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="0291f-142">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="0291f-143">In einem kleinen Unternehmen ist der Geschäftsbesitzer (die Person, die Ihr Abonnement erworben hat) ein globaler Administrator. In einem großen Unternehmen sind die wichtigsten Mitarbeiter der IT-Abteilung globale Administratoren.</span><span class="sxs-lookup"><span data-stu-id="0291f-143">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="0291f-144">Wählen **Sie Angepasster Administrator** aus, um eine Liste der Rollen zu sehen, die wir für Sie angepasst haben.</span><span class="sxs-lookup"><span data-stu-id="0291f-144">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="0291f-145">Eine Beschreibung der einzelnen Rollen finden Sie unter [Informationen zu Administratorrollen.](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0291f-145">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="0291f-146">Zuweisen von Administratorrollen zu mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="0291f-146">Assign admin roles to multiple users</span></span>

<span data-ttu-id="0291f-147">Wenn Sie PowerShell kennen, lesen Sie Zuweisen von Rollen [zu Benutzerkonten mit PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="0291f-147">If you know PowerShell, see [Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md).</span></span> <span data-ttu-id="0291f-148">PowerShell ist ideal für die Zuweisung von Rollen zu mehreren hundert Benutzern geeignet.</span><span class="sxs-lookup"><span data-stu-id="0291f-148">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="0291f-149">Verwenden Sie die folgenden Anweisungen, um dutzenden Benutzern Rollen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0291f-149">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a><span data-ttu-id="0291f-150">Überprüfen von Administratorrollen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="0291f-150">Check admin roles in your organization</span></span>

<span data-ttu-id="0291f-151">Möglicherweise verfügen Sie nicht über die richtigen Berechtigungen zum Zuweisen von Administratorrollen zu anderen Benutzern.</span><span class="sxs-lookup"><span data-stu-id="0291f-151">You might not have the correct permissions to assign admin roles to other users.</span></span> <span data-ttu-id="0291f-152">Überprüfen Sie, ob Sie über die richtigen Berechtigungen verfügen, oder bitten Sie einen anderen Administrator, Ihnen Rollen zu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0291f-152">Check to make sure you have the correct permissions or ask another admin to assign roles for you.</span></span>

<span data-ttu-id="0291f-153">Sie können die Administratorrolleberechtigungen auf zwei verschiedene Arten überprüfen:</span><span class="sxs-lookup"><span data-stu-id="0291f-153">You can check admin role permissions in 2 different ways:</span></span>

- <span data-ttu-id="0291f-154">Sie können zu den Details des Benutzers wechseln und auf der Seite Konto unter **Rollen** **suchen.**</span><span class="sxs-lookup"><span data-stu-id="0291f-154">You can go to the user's details and look under **Roles** on the **Account** page.</span></span>
- <span data-ttu-id="0291f-155">Sie können auch zu **Rollen** wechseln und die Administratorrolle auswählen und zugewiesene Administratoren auswählen, um zu sehen, welche Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="0291f-155">Or you can go to **Roles** and select the admin role, and select assigned admins to see which users are assigned.</span></span>

::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="0291f-156">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="0291f-156">Related articles</span></span>

[<span data-ttu-id="0291f-157">Informationen zu Microsoft 365-Administratorrollen</span><span class="sxs-lookup"><span data-stu-id="0291f-157">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

[<span data-ttu-id="0291f-158">Administratorrollenberechtigungen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0291f-158">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)

[<span data-ttu-id="0291f-159">Zuweisen von Rollen zu Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="0291f-159">Assign roles to user accounts with PowerShell</span></span>](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)

[<span data-ttu-id="0291f-160">Autorisieren oder Entfernen von Partnerbeziehungen</span><span class="sxs-lookup"><span data-stu-id="0291f-160">Authorize or remove partner relationships</span></span>](../misc/add-partner.md)