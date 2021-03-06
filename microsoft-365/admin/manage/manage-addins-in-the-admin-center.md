---
title: Verwalten von Add-Ins im Admin Center
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Erfahren Sie mehr über die Verwendung von zentralisierten Add-Ins zum Bereitstellen von Add-Ins für Benutzer und Gruppen in Ihrer Organisation.
ms.openlocfilehash: b888c0f329e3f1f36f5aa566df7efbab07cd1f5f
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509134"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="0163e-103">Verwalten von Add-Ins im Admin Center</span><span class="sxs-lookup"><span data-stu-id="0163e-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0163e-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="0163e-104">The admin center is changing.</span></span> <span data-ttu-id="0163e-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="0163e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="0163e-106">Office-Add-Ins helfen Ihnen, Ihre Dokumente zu personalisieren und den Zugriff auf Informationen im Web zu optimieren (siehe [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="0163e-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="0163e-107">Nachdem ein Administrator Add-Ins für Benutzer in einer Organisation bereitgestellt hat, kann der Administrator Add-Ins deaktivieren oder aktivieren, bearbeiten, löschen und den Zugriff auf die Add-Ins verwalten.</span><span class="sxs-lookup"><span data-stu-id="0163e-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="0163e-108">Weitere Informationen zum Installieren von Add-Ins aus dem Admin Center finden Sie unter [Deploy add-ins in the Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="0163e-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="0163e-109">Add-In-Status</span><span class="sxs-lookup"><span data-stu-id="0163e-109">Add-in states</span></span>

<span data-ttu-id="0163e-110">Ein Add-In kann den Status **Ein** oder **Aus** haben.</span><span class="sxs-lookup"><span data-stu-id="0163e-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="0163e-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="0163e-111">**State**</span></span>|<span data-ttu-id="0163e-112">**Wie der Status eintritt**</span><span class="sxs-lookup"><span data-stu-id="0163e-112">**How the state occurs**</span></span>|<span data-ttu-id="0163e-113">**Auswirkung**</span><span class="sxs-lookup"><span data-stu-id="0163e-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0163e-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="0163e-114">**Active**</span></span>  <br/> |<span data-ttu-id="0163e-115">Der Administrator hat das Add-In hochgeladen und Benutzern oder Gruppen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0163e-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="0163e-116">Die dem Add-In zugewiesenen Benutzer und Gruppen sehen es im jeweiligen Client.</span><span class="sxs-lookup"><span data-stu-id="0163e-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="0163e-117">**Deaktiviert**</span><span class="sxs-lookup"><span data-stu-id="0163e-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="0163e-118">Der Administrator hat das Add-In deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0163e-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="0163e-119">Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr auf das Add-In zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0163e-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="0163e-120">Wenn der Zustand des Add-Ins in "Aktiv" geändert wird, können die Benutzer und Gruppen wieder darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0163e-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="0163e-121">**Gelöscht**</span><span class="sxs-lookup"><span data-stu-id="0163e-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="0163e-122">Der Administrator hat das Add-In gelöscht.</span><span class="sxs-lookup"><span data-stu-id="0163e-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="0163e-123">Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0163e-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="0163e-124">Erwägen Sie das Löschen eines Add-Ins, wenn es nicht mehr verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0163e-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="0163e-125">Beispielsweise kann das Deaktivieren eines Add-Ins sinnvoll sein, wenn ein Add-In nur zu bestimmten Zeiten des Jahres verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0163e-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="0163e-126">Löschen eines Add-Ins</span><span class="sxs-lookup"><span data-stu-id="0163e-126">Delete an add-in</span></span>

<span data-ttu-id="0163e-127">Sie können auch ein bereitgestelltes Add-In löschen.</span><span class="sxs-lookup"><span data-stu-id="0163e-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="0163e-128">Wechseln Sie im Admin Center zur Seite  >  **Einstellungendienste & Add-Ins.**</span><span class="sxs-lookup"><span data-stu-id="0163e-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="0163e-129">Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0163e-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="0163e-130">Wenn die oben genannten Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt Zentrale Bereitstellung, indem Sie zu **Integrierte**  >  **Apps für Einstellungen wechseln.**</span><span class="sxs-lookup"><span data-stu-id="0163e-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="0163e-131">Wählen Sie oben auf der Seite Integrierte **Apps** die Option **Add-Ins aus.**</span><span class="sxs-lookup"><span data-stu-id="0163e-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="0163e-132">Wählen Sie das bereitgestellte Add-In aus.</span><span class="sxs-lookup"><span data-stu-id="0163e-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="0163e-133">Klicken Sie auf **Add-In löschen.**</span><span class="sxs-lookup"><span data-stu-id="0163e-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="0163e-134">Entfernen Sie die Add-In-Schaltfläche in der unteren rechten Ecke.</span><span class="sxs-lookup"><span data-stu-id="0163e-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="0163e-135">Überprüfen Sie Ihre Auswahl und wählen Sie **Add-In entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="0163e-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="0163e-136">Bearbeiten des Add-In-Zugangs</span><span class="sxs-lookup"><span data-stu-id="0163e-136">Edit add-in access</span></span>

<span data-ttu-id="0163e-137">Nach der Bereitstellung können Administratoren auch den Benutzerzugriff auf Add-Ins verwalten.</span><span class="sxs-lookup"><span data-stu-id="0163e-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="0163e-138">Wechseln Sie im Admin Center zur Seite  >  **Einstellungendienste & Add-Ins.**</span><span class="sxs-lookup"><span data-stu-id="0163e-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="0163e-139">Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0163e-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="0163e-140">Wenn die oben genannten Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt Zentrale Bereitstellung, indem Sie zu **Integrierte**  >  **Apps für Einstellungen wechseln.**</span><span class="sxs-lookup"><span data-stu-id="0163e-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="0163e-141">Wählen Sie oben auf der Seite Integrierte **Apps** die Option **Add-Ins aus.**</span><span class="sxs-lookup"><span data-stu-id="0163e-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="0163e-142">Wählen Sie das bereitgestellte Add-In aus.</span><span class="sxs-lookup"><span data-stu-id="0163e-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="0163e-143">Klicken Sie unter **Wer** **hat Zugriff auf Bearbeiten.**</span><span class="sxs-lookup"><span data-stu-id="0163e-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="0163e-144">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="0163e-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="0163e-145">Verhindern von Add-In-Downloads durch Deaktivieren des Office Store für alle Clients (außer Outlook)</span><span class="sxs-lookup"><span data-stu-id="0163e-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="0163e-146">Die Outlook-Add-In-Installation wird von einem anderen [Prozess verwaltet.](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0163e-146">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="0163e-147">Als Organisation möchten Sie möglicherweise verhindern, dass neue Office-Add-Ins aus dem Office Store heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="0163e-147">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="0163e-148">Dies kann in Verbindung mit der zentralen Bereitstellung verwendet werden, um sicherzustellen, dass nur von der Organisation genehmigte Add-Ins für Benutzer in Ihrer Organisation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0163e-148">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="0163e-149">**So deaktivieren Sie den Add-In-Erwerb**</span><span class="sxs-lookup"><span data-stu-id="0163e-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="0163e-150">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> [Dienste &amp; Add-Ins](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="0163e-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="0163e-151">Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0163e-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="0163e-152">Wenn die oben genannten Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt Zentrale Bereitstellung, indem Sie zu **Integrierte**  >  **Apps für Einstellungen wechseln.**</span><span class="sxs-lookup"><span data-stu-id="0163e-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="0163e-153">Wählen Sie oben auf der Seite Integrierte **Apps** die Option **Add-Ins aus.**</span><span class="sxs-lookup"><span data-stu-id="0163e-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="0163e-154">Wählen Sie **Benutzereigene Apps und Dienste aus**.</span><span class="sxs-lookup"><span data-stu-id="0163e-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="0163e-155">Deaktivieren Sie die Option, um Benutzern den Zugriff auf den Office Store zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="0163e-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="0163e-156">Dadurch wird verhindert, dass alle Benutzer die folgenden Add-Ins aus dem Store abrufen.</span><span class="sxs-lookup"><span data-stu-id="0163e-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="0163e-157">Add-Ins für Word, Excel und PowerPoint 2016 von:</span><span class="sxs-lookup"><span data-stu-id="0163e-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="0163e-158">Windows</span><span class="sxs-lookup"><span data-stu-id="0163e-158">Windows</span></span>
    
  - <span data-ttu-id="0163e-159">Mac</span><span class="sxs-lookup"><span data-stu-id="0163e-159">Mac</span></span>
    
  - <span data-ttu-id="0163e-160">Office</span><span class="sxs-lookup"><span data-stu-id="0163e-160">Office</span></span>
    
    
- <span data-ttu-id="0163e-161">Käufe, die in **AppSource beginnen**</span><span class="sxs-lookup"><span data-stu-id="0163e-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="0163e-162">Add-Ins in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0163e-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="0163e-163">Einem Benutzer, der versucht, auf den Store zu zugreifen, wird die folgende Meldung angezeigt: Microsoft 365 wurde leider so konfiguriert, dass der einzelne Erwerb von **Office Store-Add-Ins verhindert wird.**</span><span class="sxs-lookup"><span data-stu-id="0163e-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="0163e-164">Unterstützung für das Deaktivieren des Office Store ist in den folgenden Versionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0163e-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="0163e-165">Windows: 16.0.9001 – Derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0163e-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="0163e-166">Mac: 16.10.18011401 – Derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0163e-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="0163e-167">iOS: 2.9.18010804 – Derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0163e-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="0163e-168">Das Web – Derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0163e-168">The web - Currently available.</span></span>
    
<span data-ttu-id="0163e-169">Dies verhindert nicht, dass ein Administrator die zentrale Bereitstellung zum Zuweisen eines Add-Ins aus dem Office Store verwendet.</span><span class="sxs-lookup"><span data-stu-id="0163e-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="0163e-170">Um zu verhindern, dass sich ein Benutzer mit einem Microsoft-Konto anmeldet, können Sie die Anmeldung auf die Verwendung des Organisationskontos beschränken.</span><span class="sxs-lookup"><span data-stu-id="0163e-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="0163e-171">Weitere Informationen finden Sie unter [Identität, Authentifizierung und Autorisierung in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="0163e-171">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

> [!NOTE]
> <span data-ttu-id="0163e-172">Wenn Benutzer nicht auf den Office Store zugreifen können, wird auch verhindert, dass sie [Office-Add-Ins](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)zu Testzwecken querladen.</span><span class="sxs-lookup"><span data-stu-id="0163e-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="0163e-173">Weitere Informationen zur Endbenutzererfahrung mit Add-Ins</span><span class="sxs-lookup"><span data-stu-id="0163e-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="0163e-174">Nachdem Sie ein Add-In bereitgestellt haben, können Ihre Endbenutzer damit beginnen, es in ihren Office-Anwendungen zu verwenden (siehe [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="0163e-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="0163e-175">Das Add-In wird auf allen Plattformen angezeigt, die vom Add-In unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="0163e-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="0163e-p110">Wenn das Add-In Add-In-Befehle unterstützt, werden diese im Office-Menüband angezeigt. Im folgenden Beispiel wird der Befehl **Zitat suchen** für das Add-In **Zitate** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0163e-p110">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office-Menüband mit Suchzitate](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="0163e-179">Wenn das bereitgestellte Add-In keine Add-In-Befehle unterstützt oder Sie alle bereitgestellten Add-Ins anzeigen möchten, können Sie sie über **Meine Add-Ins anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="0163e-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="0163e-180">In Word 2016, Excel 2016 oder PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="0163e-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="0163e-181">Wählen **Sie Meine \> Add-Ins einfügen aus.**</span><span class="sxs-lookup"><span data-stu-id="0163e-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="0163e-182">Wählen Sie im Office-Add-In-Fenster die Schaltfläche **Vom Administrator verwaltet** aus.</span><span class="sxs-lookup"><span data-stu-id="0163e-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="0163e-183">Doppelklicken Sie auf das Add-In, das Sie zuvor bereitgestellt haben (in diesem Beispiel **Zitate** ).</span><span class="sxs-lookup"><span data-stu-id="0163e-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="0163e-184">![Registerkarte Verwaltete Administratoren der Office-Add-Ins-Seite](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="0163e-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="0163e-185">In Outlook</span><span class="sxs-lookup"><span data-stu-id="0163e-185">In Outlook</span></span>

1. <span data-ttu-id="0163e-186">Wählen Sie **auf dem Menüband** Start die Option **Add-Ins erhalten aus.**</span><span class="sxs-lookup"><span data-stu-id="0163e-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="0163e-187">![Schaltfläche "Speichern" in Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="0163e-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="0163e-188">Wählen Sie im linken Navigationsbereich **vom Administrator verwaltete** aus.</span><span class="sxs-lookup"><span data-stu-id="0163e-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="0163e-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0163e-189">Learn more</span></span>

[<span data-ttu-id="0163e-190">Bereitstellen von Add-Ins im Admin Center</span><span class="sxs-lookup"><span data-stu-id="0163e-190">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="0163e-191">Weitere Informationen zum Erstellen von [Office-Add-Ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)</span><span class="sxs-lookup"><span data-stu-id="0163e-191">Learn more about creating and building [Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="0163e-192">[Verwenden Sie powerShell-Cmdlets für die zentrale Bereitstellung, um Add-Ins zu verwalten.](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="0163e-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="0163e-193">Problembehandlung: Benutzer sieht keine Add-Ins</span><span class="sxs-lookup"><span data-stu-id="0163e-193">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="0163e-194">Minderjährige und Erwerben von Add-Ins aus dem Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="0163e-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
