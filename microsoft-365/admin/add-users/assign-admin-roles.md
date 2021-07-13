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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Erfahren Sie, wie Sie einem Benutzer oder mehreren Benutzern in Ihrem Unternehmen Administratorrollen zuweisen, damit diese bestimmte Aufgaben im Admin Center ausführen können.
ms.openlocfilehash: 575d1d8c6b0ffce40877fb41d28df82c24e84d04
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393775"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="93a98-103">Administratorrollen zuweisen</span><span class="sxs-lookup"><span data-stu-id="93a98-103">Assign admin roles</span></span>

<span data-ttu-id="93a98-104">Wenn Sie die Person sind, die Ihr Microsoft Business-Abonnement erworben hat, sind Sie der globale Administrator. Dies bedeutet, dass Sie unbegrenzte Kontrolle über die Produkte in Ihren Abonnements haben und auf die meisten Daten zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="93a98-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="93a98-105">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="93a98-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="93a98-106">Wenn Sie neue Benutzer hinzufügen, wenn Sie ihnen keine Administratorrolle zuweisen, befinden sie sich in der *Benutzerrolle* und verfügen über keine Administratorrechte für eines der Microsoft Admin Center.</span><span class="sxs-lookup"><span data-stu-id="93a98-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="93a98-107">Wenn Sie jedoch Hilfe benötigen, um Dies zu erledigen, können Sie einem Benutzer eine Administratorrolle zuweisen.</span><span class="sxs-lookup"><span data-stu-id="93a98-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="93a98-108">Wenn Sie beispielsweise jemanden benötigen, der beim Zurücksetzen von Kennwörtern helfen soll, sollten Sie ihm nicht die globale Administratorrolle zuweisen, sie sollten ihm die Kennwortadministratorrolle zuweisen.</span><span class="sxs-lookup"><span data-stu-id="93a98-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="93a98-109">Zu viele globale Administratoren mit unbegrenztem Zugriff auf Ihre Daten und Ihr Onlinegeschäft zu ernennen, stellt ein Sicherheitsrisiko dar.</span><span class="sxs-lookup"><span data-stu-id="93a98-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

## <a name="watch-add-an-adminbrbr"></a><span data-ttu-id="93a98-110">Überwachung: Hinzufügen eines Administrators</span><span class="sxs-lookup"><span data-stu-id="93a98-110">Watch: Add an admin</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="93a98-111">Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../../business-video/index.yml) an.</span><span class="sxs-lookup"><span data-stu-id="93a98-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="assign-admin-roles"></a><span data-ttu-id="93a98-112">Administratorrollen zuweisen</span><span class="sxs-lookup"><span data-stu-id="93a98-112">Assign admin roles</span></span> 

<span data-ttu-id="93a98-113">Sie können einer Rolle auf zwei verschiedene Arten Benutzer zuweisen:</span><span class="sxs-lookup"><span data-stu-id="93a98-113">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="93a98-114">Sie können zu den Details des Benutzers wechseln und **Rollen verwalten,** um dem Benutzer eine Rolle zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="93a98-114">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="93a98-115">Sie können auch zu **"Rollen"** wechseln und die Rolle auswählen und dann mehrere Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="93a98-115">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="93a98-116">Zuweisen von Administratorrollen zu Benutzern mithilfe von Rollen</span><span class="sxs-lookup"><span data-stu-id="93a98-116">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="93a98-117">Wechseln Sie im Admin Center zu **"Rollen".**</span><span class="sxs-lookup"><span data-stu-id="93a98-117">In the admin center, go to **Roles**.</span></span> <span data-ttu-id="93a98-118">Wählen Sie die **Registerkarten Azure AD** oder **Intune** aus, um die für Ihre Organisation verfügbaren Administratorrollen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="93a98-118">Choose the **Azure AD** or **Intune** tabs to view the admin roles available for your organization.</span></span>
2. <span data-ttu-id="93a98-119">Wählen Sie die Administratorrolle aus, der Sie den Benutzer zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="93a98-119">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="93a98-120">Wählen Sie **"Zugewiesene Administratoren**  >  **hinzufügen"** aus.</span><span class="sxs-lookup"><span data-stu-id="93a98-120">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="93a98-121">Geben Sie den **Anzeigenamen** oder **Benutzernamen** des Benutzers ein, und wählen Sie dann den Benutzer aus der Liste der Vorschläge aus.</span><span class="sxs-lookup"><span data-stu-id="93a98-121">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="93a98-122">Fügen Sie mehrere Benutzer hinzu, bis Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="93a98-122">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="93a98-123">Wählen Sie **"Speichern"** aus, und dann wird der Benutzer der Liste der zugewiesenen Administratoren hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="93a98-123">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="93a98-124">Zuweisen eines Benutzers zu einer Administratorrolle über "Aktive Benutzer"</span><span class="sxs-lookup"><span data-stu-id="93a98-124">Assign a user to an admin role from Active users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="93a98-125">Wechseln Sie im Admin  Center zur Seite > ["Aktive Benutzer von](https://go.microsoft.com/fwlink/p/?linkid=834822) Benutzern".</span><span class="sxs-lookup"><span data-stu-id="93a98-125">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="93a98-126">Wechseln Sie im Admin Center zu der Seite **Benutzer** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="93a98-126">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="93a98-127">Wechseln Sie im Admin Center zu der Seite **Benutzer** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="93a98-127">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="93a98-128">Wählen Sie auf der Seite **"Aktive Benutzer"** den Benutzer aus, dessen Administratorrolle Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="93a98-128">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="93a98-129">Wählen Sie im Flyoutbereich unter **"Rollen"** die Option **"Rollen verwalten"** aus.</span><span class="sxs-lookup"><span data-stu-id="93a98-129">In the flyout pane, under **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="93a98-130">Wählen Sie die Administratorrolle aus, die Sie dem Benutzer zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="93a98-130">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="93a98-131">Wenn die gesuchte Rolle nicht angezeigt wird, wählen Sie **"Alle anzeigen"** am Ende der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="93a98-131">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="93a98-132">Zuweisen von Administratorrollen zu mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="93a98-132">Assign admin roles to multiple users</span></span>

<span data-ttu-id="93a98-133">Wenn Sie PowerShell kennen, lesen [Sie "Zuweisen von Rollen zu Benutzerkonten mit PowerShell".](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="93a98-133">If you know PowerShell, see [Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md).</span></span> <span data-ttu-id="93a98-134">PowerShell ist ideal für die Zuweisung von Rollen zu mehreren hundert Benutzern geeignet.</span><span class="sxs-lookup"><span data-stu-id="93a98-134">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="93a98-135">Verwenden Sie die folgenden Anweisungen, um dutzenden Benutzern Rollen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="93a98-135">Use the following instructions to assign roles to tens of users.</span></span>

## <a name="check-admin-roles-in-your-organization"></a><span data-ttu-id="93a98-136">Überprüfen von Administratorrollen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="93a98-136">Check admin roles in your organization</span></span>

<span data-ttu-id="93a98-137">Möglicherweise verfügen Sie nicht über die richtigen Berechtigungen, um anderen Benutzern Administratorrollen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="93a98-137">You might not have the correct permissions to assign admin roles to other users.</span></span> <span data-ttu-id="93a98-138">Stellen Sie sicher, dass Sie über die richtigen Berechtigungen verfügen, oder bitten Sie einen anderen Administrator, Rollen für Sie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="93a98-138">Check to make sure you have the correct permissions or ask another admin to assign roles for you.</span></span>

<span data-ttu-id="93a98-139">Sie können Administratorrollenberechtigungen auf zwei verschiedene Arten überprüfen:</span><span class="sxs-lookup"><span data-stu-id="93a98-139">You can check admin role permissions in 2 different ways:</span></span>

- <span data-ttu-id="93a98-140">Sie können zu den Details des Benutzers wechseln und auf der **Seite "Konto"** unter **"Rollen"** suchen.</span><span class="sxs-lookup"><span data-stu-id="93a98-140">You can go to the user's details and look under **Roles** on the **Account** page.</span></span>
- <span data-ttu-id="93a98-141">Sie können auch zu **"Rollen"** wechseln und die Administratorrolle auswählen und die zugewiesenen Administratoren auswählen, um zu sehen, welche Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="93a98-141">Or you can go to **Roles** and select the admin role, and select assigned admins to see which users are assigned.</span></span>

## <a name="related-content"></a><span data-ttu-id="93a98-142">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="93a98-142">Related content</span></span>

<span data-ttu-id="93a98-143">[Informationen zu Microsoft 365 Administratorrollen](about-admin-roles.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="93a98-143">[About Microsoft 365 admin roles](about-admin-roles.md) (article)</span></span>\
<span data-ttu-id="93a98-144">[Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="93a98-144">[Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (article)</span></span>\
<span data-ttu-id="93a98-145">[Zuweisen von Rollen zu Benutzerkonten mit PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="93a98-145">[Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (article)</span></span>\
<span data-ttu-id="93a98-146">[Autorisieren oder Entfernen von Partnerbeziehungen](../misc/add-partner.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="93a98-146">[Authorize or remove partner relationships](../misc/add-partner.md) (article)</span></span>