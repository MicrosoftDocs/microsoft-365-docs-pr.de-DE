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
description: Hier erfahren Sie, wie Sie Filter zum Erstellen, bearbeiten oder Löschen einer benutzerdefinierten Benutzeransicht in Microsoft 365 verwenden können.
ms.openlocfilehash: 265aa1a7c22475710a12a93c2bfee0b7749f438b
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44431641"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a><span data-ttu-id="eb212-103">Erstellen, Bearbeiten oder Löschen einer benutzerdefinierten Benutzeransicht in Office 365</span><span class="sxs-lookup"><span data-stu-id="eb212-103">Create, edit, or delete a custom user view in Office 365</span></span>

<span data-ttu-id="eb212-p101">[] Wenn Sie ein globaler Administrator oder als Administrator für die Benutzerverwaltung in Office 365 zuständig sind, können Sie benutzerdefinierte Benutzeransichten erstellen, um eine bestimmte Untermenge von Benutzern anzuzeigen. Diese Ansichten werden zusätzlich zu den Standardansichten angezeigt, die zum Bereitstellungsumfang von Office 365 gehören. Sie können benutzerdefinierte Benutzeransichten erstellen, bearbeiten oder löschen, und die von Ihnen erstellten benutzerdefinierten Ansichten stehen allen Administratoren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="eb212-p101">If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users. These views are in addition to the standard set of views that come with Office 365. You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="eb212-107">Benutzerdefinierte Benutzeransichten im Admin Center</span><span class="sxs-lookup"><span data-stu-id="eb212-107">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="eb212-108">Wenn Sie eine benutzerdefinierte Benutzeransicht erstellen, bearbeiten oder löschen, werden die Änderungen in der **Filter** Liste angezeigt, die alle Administratoren in Ihrem Unternehmen sehen, wenn Sie zur Seite **Benutzer** wechseln.</span><span class="sxs-lookup"><span data-stu-id="eb212-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="eb212-109">Sie können bis zu 50 benutzerdefinierte Ansichten erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb212-109">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="eb212-110">Wenn Sie eine benutzerdefinierte Benutzeransicht erstellen, bearbeiten oder löschen, werden die Änderungen in der Liste **Ansichten** angezeigt, die alle Administratoren in Ihrem Unternehmen sehen, wenn Sie zur Seite **Benutzer** wechseln.</span><span class="sxs-lookup"><span data-stu-id="eb212-110">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="eb212-111">Sie können bis zu 50 benutzerdefinierte Ansichten erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb212-111">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="eb212-112">Wenn Sie eine benutzerdefinierte Benutzeransicht erstellen, bearbeiten oder löschen, werden die Änderungen in der Liste **Ansichten** angezeigt, die alle Administratoren in Ihrem Unternehmen sehen, wenn Sie zur Seite **Benutzer** wechseln.</span><span class="sxs-lookup"><span data-stu-id="eb212-112">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="eb212-113">Sie können bis zu 50 benutzerdefinierte Ansichten erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb212-113">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="eb212-114">Standard user views are displayed by default in the **Filters** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="eb212-114">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="eb212-115">Die Standardfilter umfassen **alle Benutzer**, **lizenzierte Benutzer**, **Gastbenutzer**, **Anmeldungs berechtigte**, **Anmeldungs blockiert**, nicht **lizenzierte Benutzer**, **Benutzer mit Fehlern**, **Abrechnungs Administratoren**, **globale Administratoren**, **Helpdesk**-Administratoren, **Dienstadministratoren**und **Benutzer Verwaltungs Administratoren**.</span><span class="sxs-lookup"><span data-stu-id="eb212-115">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="eb212-116">Standardansichten können weder bearbeitet noch gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="eb212-116">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="eb212-117">Zu Standardansichten müssen noch einige weitere Punkte angemerkt werden:</span><span class="sxs-lookup"><span data-stu-id="eb212-117">A few things to note about standard views:</span></span> 

- <span data-ttu-id="eb212-p106">In einigen Standardansichten wird eine nicht sortierte Liste angezeigt, wenn die Liste mehr als 2.000 Benutzer enthält. Wenn Sie in dieser Liste nach bestimmten Benutzern suchen möchten, müssen Sie das Suchfeld verwenden.</span><span class="sxs-lookup"><span data-stu-id="eb212-p106">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="eb212-120">Wenn Sie Microsoft 365 nicht von Microsoft erworben haben, werden die **Abrechnungs Administratoren** nicht in der Liste Standardansichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb212-120">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="eb212-121">Weitere Informationen finden Sie unter [Zuweisen von Adminrollen](assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="eb212-121">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="eb212-122">Wählen der Filter für die benutzerdefinierte Benutzeransicht</span><span class="sxs-lookup"><span data-stu-id="eb212-122">Choose the filters for your custom user view</span></span>

<span data-ttu-id="eb212-123">Sie können Ihre benutzerdefinierten Ansichten im **benutzerdefinierten Filter** Bereich erstellen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="eb212-123">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="eb212-124">Wenn Sie mehrere Filteroptionen auswählen, erhalten Sie Ergebnisse mit Benutzern, die allen ausgewählten Filterkriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="eb212-124">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="eb212-125">Im folgende Beispiel wird gezeigt, wie Sie eine benutzerdefinierte Ansicht mit dem Namen "Kanadische Benutzer" erstellen, die alle Benutzer, die sich in Kanada befinden, in einer bestimmten Domäne enthält.</span><span class="sxs-lookup"><span data-stu-id="eb212-125">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="eb212-126">**A-Domäne** Wenn Sie mehrere Domänen für Ihre Organisation haben, können Sie aus einer Dropdownliste mit verfügbaren Domänen auswählen.</span><span class="sxs-lookup"><span data-stu-id="eb212-126">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="eb212-127">**B-Anmeldestatus** Wählen Sie Benutzer, die zugelassen oder blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="eb212-127">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="eb212-128">**C-Standort** Wählen Sie einen Speicherort aus einer Dropdownliste mit Ländern aus.</span><span class="sxs-lookup"><span data-stu-id="eb212-128">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="eb212-129">**D-zugewiesene Produktlizenz** Wählen Sie aus einer Dropdownliste mit Lizenzen aus, die in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="eb212-129">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="eb212-130">Verwenden Sie diesen Filter, um Benutzer anzuzeigen, denen die ausgewählte Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="eb212-130">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="eb212-131">Benutzer können auch über weitere Lizenzen verfügen.</span><span class="sxs-lookup"><span data-stu-id="eb212-131">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="eb212-132">Sie können auch nach weiteren Benutzerprofildetails filtern, die in Ihrer Organisation verwendet werden, z. B. Abteilung, Ort, Bundesland oder Kanton, Land oder Region oder Position.</span><span class="sxs-lookup"><span data-stu-id="eb212-132">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="eb212-133">**Weitere Bedingungen:**</span><span class="sxs-lookup"><span data-stu-id="eb212-133">**Other conditions:**</span></span>
  
- <span data-ttu-id="eb212-134">**Nur synchronisierte Benutzer:** Wählen Sie dieses Feld aus, um alle Benutzer anzuzeigen, die mit dem lokalen Active Directory-Dienst synchronisiert sind. Es spielt keine Rolle, ob die Benutzer aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="eb212-134">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="eb212-135">**Benutzer mit Fehlern:** Wählen Sie dieses Feld aus, um Benutzer mit möglichen Bereitstellungsfehlern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="eb212-135">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="eb212-p110">**Benutzer ohne Lizenzen:** Wählen Sie dieses Feld aus, um nach allen Benutzern zu suchen, denen keine Lizenz zugewiesen ist. Die Ergebnisse für diese Ansicht können auch Benutzer umfassen, die ein Exchange-Postfach, aber keine Lizenz besitzen. Um speziell diese Benutzer nachzuverfolgen, verwenden Sie den Filter **Benutzer mit Exchange-Postfächern oder -Archiven und keinen Lizenzen**. Die Ergebnisse dieser Ansicht können auch Benutzer umfassen, die über ein Exchange-Archiv, jedoch nicht über eine Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="eb212-p110">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="eb212-140">Nicht **lizenzierte Benutzer mit Exchange-Postfächern oder-Archiven** Aktivieren Sie dieses Kontrollkästchen, um Benutzerkonten anzuzeigen, die in Exchange Online erstellt wurden und über ein Exchange-Postfach verfügen, dem aber keine Microsoft 365-Lizenz zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="eb212-140">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="eb212-141">Die Ergebnisse dieses Filters enthalten Benutzer, die über ein Exchange-Archiv verfügen oder einem solchen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="eb212-141">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="eb212-142">Die nicht **lizenzierten Benutzer mit Exchange-Post** Fach Filter funktionieren in folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="eb212-142">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="eb212-143">Das Postfach wurde kürzlich von **freigegebener** **Benutzer** konvertiert und verfügt über keine Lizenz.</span><span class="sxs-lookup"><span data-stu-id="eb212-143">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="eb212-144">Das Postfach wurde kürzlich zu Microsoft 365 migriert, aber es wurde keine Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="eb212-144">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="eb212-145">Das Postfach wurde mithilfe von PowerShell erstellt, und es wurde keine Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="eb212-145">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="eb212-146">Ein neues Postfach, das lokal mit einem New-Remote Mailbox-Cmdlet erstellt wurde, wird für den Benutzer bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="eb212-146">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="eb212-147">Wenn Sie eine benutzerdefinierte Ansicht mit über 2.000 Benutzern erstellen, ist die daraus resultierende Benutzerliste nicht sortiert.</span><span class="sxs-lookup"><span data-stu-id="eb212-147">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="eb212-148">Verwenden Sie in diesem Fall das Suchfeld, um nach Benutzern zu suchen oder Ihre benutzerdefinierte Ansicht zu bearbeiten, um die Suche zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="eb212-148">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="eb212-149">Erstellen einer benutzerdefinierten Benutzeransicht</span><span class="sxs-lookup"><span data-stu-id="eb212-149">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="eb212-150">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="eb212-150">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="eb212-151">Klicken Sie auf der Seite **aktive Benutzer** auf **Filter** , und wählen Sie **Neuer Filter**aus.</span><span class="sxs-lookup"><span data-stu-id="eb212-151">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="eb212-152">Geben Sie auf der Seite **benutzerdefinierter Filter** den Namen für den Filter ein, wählen Sie die Bedingungen für den benutzerdefinierten Filter aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="eb212-152">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="eb212-153">Ihre benutzerdefinierte Ansicht ist jetzt in der Dropdownliste mit den Filtern enthalten.</span><span class="sxs-lookup"><span data-stu-id="eb212-153">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="eb212-154">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="eb212-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="eb212-155">Wählen Sie auf der Seite **aktive Benutzer** die Option **Ansichten** aus, und wählen Sie **benutzerdefinierte Ansicht hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="eb212-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="eb212-156">Geben Sie auf der Seite **benutzerdefinierte Ansicht** den Namen für den Filter ein, wählen Sie die Bedingungen für den benutzerdefinierten Filter aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="eb212-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="eb212-157">Ihre benutzerdefinierte Ansicht ist jetzt in der Dropdownliste mit den Filtern enthalten.</span><span class="sxs-lookup"><span data-stu-id="eb212-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="eb212-158">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="eb212-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="eb212-159">Wählen Sie auf der Seite **aktive Benutzer** die Option **Ansichten** aus, und wählen Sie **benutzerdefinierte Ansicht hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="eb212-159">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="eb212-160">Geben Sie auf der Seite **benutzerdefinierte Ansicht** den Namen für den Filter ein, wählen Sie die Bedingungen für den benutzerdefinierten Filter aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="eb212-160">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="eb212-161">Ihre benutzerdefinierte Ansicht ist jetzt in der Dropdownliste mit den Filtern enthalten.</span><span class="sxs-lookup"><span data-stu-id="eb212-161">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="eb212-162">Bearbeiten oder Löschen einer benutzerdefinierten Benutzeransicht</span><span class="sxs-lookup"><span data-stu-id="eb212-162">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="eb212-163">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="eb212-163">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="eb212-164">Wählen Sie auf der Seite **aktive Benutzer** die Option **Filter**aus, wählen Sie den Filter aus, den Sie ändern möchten, und klicken Sie dann auf **Filter bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="eb212-164">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="eb212-165">Sie können nur benutzerdefinierte Ansichten bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="eb212-165">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="eb212-166">Bearbeiten Sie auf der Seite **benutzerdefinierter Filter** die Informationen nach Bedarf, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="eb212-166">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="eb212-167">Oder wählen Sie zum Löschen des Filters am unteren Rand der Seite die Option **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="eb212-167">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="eb212-168">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="eb212-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="eb212-169">Wählen Sie auf der Seite **aktive Benutzer** die Option **Ansichten**aus, wählen Sie den Filter aus, den Sie ändern möchten, und klicken Sie dann auf **diese Ansicht bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="eb212-169">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="eb212-170">Sie können nur benutzerdefinierte Ansichten bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="eb212-170">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="eb212-171">Bearbeiten Sie auf der Seite **benutzerdefinierte Ansicht** die Informationen nach Bedarf, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="eb212-171">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="eb212-172">Wenn Sie den Filter löschen möchten, wählen Sie unten auf der Seite die Option **benutzerdefinierte Ansicht löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="eb212-172">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="eb212-173">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="eb212-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="eb212-174">Wählen Sie auf der Seite **aktive Benutzer** die Option **Ansichten**aus, wählen Sie den Filter aus, den Sie ändern möchten, und klicken Sie dann auf **diese Ansicht bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="eb212-174">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="eb212-175">Sie können nur benutzerdefinierte Ansichten bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="eb212-175">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="eb212-176">Bearbeiten Sie auf der Seite **benutzerdefinierte Ansicht** die Informationen nach Bedarf, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="eb212-176">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="eb212-177">Wenn Sie den Filter löschen möchten, wählen Sie unten auf der Seite die Option **benutzerdefinierte Ansicht löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="eb212-177">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     