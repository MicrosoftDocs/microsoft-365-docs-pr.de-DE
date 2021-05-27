---
title: Erstellen, Bearbeiten oder Löschen einer benutzerdefinierten Benutzeransicht
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Erfahren Sie, wie Sie mithilfe von Filtern benutzerdefinierte Benutzeransichten in einer Microsoft 365.
ms.openlocfilehash: b4177a561d13d76f6d5a0a1077fe8037d469ee48
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683223"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a><span data-ttu-id="bb9f2-103">Erstellen, Bearbeiten oder Löschen einer benutzerdefinierten Benutzeransicht</span><span class="sxs-lookup"><span data-stu-id="bb9f2-103">Create, edit, or delete a custom user view</span></span>

<span data-ttu-id="bb9f2-104">Wenn Sie ein globaler Administrator oder Benutzerverwaltungsadministrator eines Microsoft 365 Business-Abonnements sind, können Sie benutzerdefinierte Benutzeransichten erstellen, um eine bestimmte Teilmenge von Benutzern anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-104">If you're a global or user management admin of a Microsoft 365 for business subscription,  you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="bb9f2-105">Diese Ansichten sind zusätzlich zum Standardsatz von Ansichten.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-105">These views are in addition to the standard set of views.</span></span> <span data-ttu-id="bb9f2-106">Sie können benutzerdefinierte Benutzeransichten erstellen, bearbeiten oder löschen, und die von Ihnen erstellten benutzerdefinierten Ansichten stehen allen Administratoren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="bb9f2-107">Benutzerdefinierte Benutzeransichten im Admin Center</span><span class="sxs-lookup"><span data-stu-id="bb9f2-107">Custom user views in the admin center</span></span>

<span data-ttu-id="bb9f2-108">Wenn Sie eine benutzerdefinierte Benutzeransicht erstellen, bearbeiten oder löschen, werden die Änderungen in der Filterliste angezeigt, die allen Administratoren in Ihrem Unternehmen angezeigt wird, wenn sie zur Seite Benutzer **wechseln.** </span><span class="sxs-lookup"><span data-stu-id="bb9f2-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="bb9f2-109">Sie können bis zu 50 benutzerdefinierte Ansichten erstellen.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-109">You can create up to 50 custom views.</span></span> 

> [!TIP]
>  <span data-ttu-id="bb9f2-110">Standard user views are displayed by default in the **Filters** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-110">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="bb9f2-111">Zu den Standardfiltern gehören **Alle** Benutzer **,** Lizenzierte Benutzer **,** Gastbenutzer **,** Anmeldung zulässig **,** Anmeldung blockiert , Nicht lizenzierte Benutzer **,** Benutzer mit Fehlern , **Abrechnungsadministratoren**, **globale** Administratoren , **Helpdeskadministratoren**, **Dienstadministratoren** und **Benutzerverwaltungsadministratoren**. </span><span class="sxs-lookup"><span data-stu-id="bb9f2-111">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="bb9f2-112">Standardansichten können weder bearbeitet noch gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-112">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="bb9f2-113">Zu Standardansichten müssen noch einige weitere Punkte angemerkt werden:</span><span class="sxs-lookup"><span data-stu-id="bb9f2-113">A few things to note about standard views:</span></span> 

- <span data-ttu-id="bb9f2-p104">In einigen Standardansichten wird eine nicht sortierte Liste angezeigt, wenn die Liste mehr als 2.000 Benutzer enthält. Wenn Sie in dieser Liste nach bestimmten Benutzern suchen möchten, müssen Sie das Suchfeld verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-p104">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="bb9f2-116">Wenn Sie keine Microsoft 365 von Microsoft erwerben, werden **Abrechnungsadministratoren** nicht in der Standardansichtsliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-116">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="bb9f2-117">Weitere Informationen finden Sie unter [Zuweisen von Adminrollen](assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="bb9f2-117">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="bb9f2-118">Wählen der Filter für die benutzerdefinierte Benutzeransicht</span><span class="sxs-lookup"><span data-stu-id="bb9f2-118">Choose the filters for your custom user view</span></span>

<span data-ttu-id="bb9f2-119">Sie können ihre benutzerdefinierten Ansichten im Benutzerdefinierten **Filterbereich erstellen und** bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-119">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="bb9f2-120">Wenn Sie mehrere Filteroptionen auswählen, erhalten Sie Ergebnisse mit Benutzern, die allen ausgewählten Filterkriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-120">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="bb9f2-121">Im folgende Beispiel wird gezeigt, wie Sie eine benutzerdefinierte Ansicht mit dem Namen "Kanadische Benutzer" erstellen, die alle Benutzer, die sich in Kanada befinden, in einer bestimmten Domäne enthält.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-121">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="bb9f2-122">**A – Domäne** Wenn Sie über mehrere Domänen für Ihre Organisation verfügen, können Sie aus einer Dropdownliste der verfügbaren Domänen auswählen.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-122">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="bb9f2-123">**B – Anmeldestatus** Wählen Sie Benutzer aus, die zugelassen oder blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-123">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="bb9f2-124">**C – Speicherort** Wählen Sie einen Speicherort aus einer Dropdownliste mit Ländern aus.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-124">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="bb9f2-125">**D – Zugewiesene Produktlizenz** Wählen Sie aus einer Dropdownliste der Lizenzen aus, die in Ihrer Organisation verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-125">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="bb9f2-126">Verwenden Sie diesen Filter, um Benutzer anzuzeigen, denen die ausgewählte Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-126">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="bb9f2-127">Benutzer können auch über weitere Lizenzen verfügen.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-127">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="bb9f2-128">Sie können auch nach weiteren Benutzerprofildetails filtern, die in Ihrer Organisation verwendet werden, z. B. Abteilung, Ort, Bundesland oder Kanton, Land oder Region oder Position.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-128">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="bb9f2-129">**Weitere Bedingungen:**</span><span class="sxs-lookup"><span data-stu-id="bb9f2-129">**Other conditions:**</span></span>
  
- <span data-ttu-id="bb9f2-130">**Nur synchronisierte Benutzer:** Wählen Sie dieses Feld aus, um alle Benutzer anzuzeigen, die mit dem lokalen Active Directory-Dienst synchronisiert sind. Es spielt keine Rolle, ob die Benutzer aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-130">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="bb9f2-131">**Benutzer mit Fehlern:** Wählen Sie dieses Feld aus, um Benutzer mit möglichen Bereitstellungsfehlern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-131">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="bb9f2-p108">**Benutzer ohne Lizenzen:** Wählen Sie dieses Feld aus, um nach allen Benutzern zu suchen, denen keine Lizenz zugewiesen ist. Die Ergebnisse für diese Ansicht können auch Benutzer umfassen, die ein Exchange-Postfach, aber keine Lizenz besitzen. Um speziell diese Benutzer nachzuverfolgen, verwenden Sie den Filter **Benutzer mit Exchange-Postfächern oder -Archiven und keinen Lizenzen**. Die Ergebnisse dieser Ansicht können auch Benutzer umfassen, die über ein Exchange-Archiv, jedoch nicht über eine Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-p108">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="bb9f2-136">**Nicht lizenzierte Benutzer mit Exchange Postfächern oder Archiven** Aktivieren Sie dieses Feld, um Benutzerkonten zu zeigen, die in Exchange Online erstellt wurden und über ein Exchange-Postfach verfügen, aber keine Microsoft 365 wurden.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-136">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="bb9f2-137">Die Ergebnisse dieses Filters enthalten Benutzer, die über ein Exchange-Archiv verfügen oder einem solchen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-137">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="bb9f2-138">Der **Filter Nicht lizenzierte Benutzer mit Exchange funktioniert,** wenn:</span><span class="sxs-lookup"><span data-stu-id="bb9f2-138">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="bb9f2-139">Das Postfach wurde kürzlich von freigegeben für **benutzer** **konvertiert** und verfügt über keine Lizenz.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-139">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="bb9f2-140">Das Postfach wurde kürzlich zu einer Microsoft 365 es wurde jedoch keine Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-140">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="bb9f2-141">Das Postfach wurde mithilfe von PowerShell erstellt, und es wurde keine Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-141">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="bb9f2-142">Ein neues Postfach, das lokal mit einem New-RemoteMailbox erstellt wurde, wird für den Benutzer bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-142">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="bb9f2-143">Wenn Sie eine benutzerdefinierte Ansicht mit über 2.000 Benutzern erstellen, ist die daraus resultierende Benutzerliste nicht sortiert.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="bb9f2-144">Verwenden Sie in diesem Fall das Suchfeld, um Benutzer zu finden oder Ihre benutzerdefinierte Ansicht zu bearbeiten, um die Suche zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="bb9f2-145">Erstellen einer benutzerdefinierten Benutzeransicht</span><span class="sxs-lookup"><span data-stu-id="bb9f2-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bb9f2-146">Wechseln Sie im Admin Center zu **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-146">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bb9f2-147">Wechseln Sie im Admin Center zu **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-147">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bb9f2-148">Wechseln Sie im Admin Center zu **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-148">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span>  

::: moniker-end
    
2. <span data-ttu-id="bb9f2-149">Wählen Sie **auf der Seite** Aktive Benutzer Die Option **Filter** aus, und wählen Sie Neuer **Filter aus.**</span><span class="sxs-lookup"><span data-stu-id="bb9f2-149">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="bb9f2-150">Geben Sie **auf der** Seite Benutzerdefinierter Filter den Namen für den Filter ein, wählen Sie die Bedingungen für den benutzerdefinierten Filter aus, und wählen Sie dann **Hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="bb9f2-150">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="bb9f2-151">Ihre benutzerdefinierte Ansicht ist jetzt in der Dropdownliste der Filter enthalten.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-151">Your custom view is now included in the drop-down list of filters.</span></span>

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="bb9f2-152">Bearbeiten oder Löschen einer benutzerdefinierten Benutzeransicht</span><span class="sxs-lookup"><span data-stu-id="bb9f2-152">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bb9f2-153">Wechseln Sie im Admin Center zu **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-153">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bb9f2-154">Wechseln Sie im Admin Center zu **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-154">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bb9f2-155">Wechseln Sie im Admin Center zu **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-155">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

::: moniker-end 
    
2. <span data-ttu-id="bb9f2-156">Wählen Sie **auf der** Seite Aktive Benutzer die Option **Filter** aus, wählen Sie den Filter aus, den Sie ändern möchten, und wählen Sie dann Filter **bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="bb9f2-156">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="bb9f2-157">Sie können nur benutzerdefinierte Ansichten bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-157">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="bb9f2-158">Bearbeiten Sie **auf der** Seite Benutzerdefinierter Filter die Informationen nach Bedarf, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="bb9f2-158">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="bb9f2-159">Wenn Sie den Filter löschen möchten, wählen Sie am unteren Rand der Seite Löschen **aus.**</span><span class="sxs-lookup"><span data-stu-id="bb9f2-159">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 

## <a name="related-content"></a><span data-ttu-id="bb9f2-160">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="bb9f2-160">Related content</span></span>

<span data-ttu-id="bb9f2-161">[Übersicht über Microsoft 365 Admin Center](../../business-video/admin-center-overview.md) (Video)</span><span class="sxs-lookup"><span data-stu-id="bb9f2-161">[Overview of the Microsoft 365 admin center](../../business-video/admin-center-overview.md) (video)</span></span>\
<span data-ttu-id="bb9f2-162">[Informationen zu Administratorrollen](../add-users/about-admin-roles.md) (Video)</span><span class="sxs-lookup"><span data-stu-id="bb9f2-162">[About admin roles](../add-users/about-admin-roles.md) (video)</span></span>\
<span data-ttu-id="bb9f2-163">[Anpassen des Microsoft 365 Design für Ihre Organisation](../setup/customize-your-organization-theme.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="bb9f2-163">[Customize the Microsoft 365 theme for your organization](../setup/customize-your-organization-theme.md) (article)</span></span>


     