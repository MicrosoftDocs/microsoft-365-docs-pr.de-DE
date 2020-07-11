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
description: Hier erfahren Sie, wie Sie Add-Ins für Benutzer und Gruppen in Ihrer Organisation mithilfe einer zentralisierten Bereitstellung im Admin Center bereitstellen können.
ms.openlocfilehash: caaea8404c099f56704d21684323a4b20e61f52d
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103099"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="353ae-103">Verwalten von Add-Ins im Admin Center</span><span class="sxs-lookup"><span data-stu-id="353ae-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="353ae-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="353ae-104">The admin center is changing.</span></span> <span data-ttu-id="353ae-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="353ae-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="353ae-106">Office-Add-Ins unterstützen Sie bei der Personalisierung Ihrer Dokumente und bei der Optimierung der Art und Weise, wie Sie auf Informationen im Internet zugreifen (siehe [Start mit Ihrem Office-Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="353ae-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="353ae-107">Nachdem ein Administrator Add-Ins für Benutzer in einer Organisation bereitgestellt hat, kann der Administrator Add-Ins aus-oder einschalten, bearbeiten, löschen und den Zugriff auf die Add-Ins verwalten.</span><span class="sxs-lookup"><span data-stu-id="353ae-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="353ae-108">Weitere Informationen zum Installieren von Add-Ins aus dem Admin Center finden Sie unter [Deploy Add-Ins in the Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="353ae-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="353ae-109">Add-In-Status</span><span class="sxs-lookup"><span data-stu-id="353ae-109">Add-in states</span></span>

<span data-ttu-id="353ae-110">Ein Add-in kann entweder im Status **on** oder **Off** liegen.</span><span class="sxs-lookup"><span data-stu-id="353ae-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="353ae-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="353ae-111">**State**</span></span>|<span data-ttu-id="353ae-112">**Wie der Status eintritt**</span><span class="sxs-lookup"><span data-stu-id="353ae-112">**How the state occurs**</span></span>|<span data-ttu-id="353ae-113">**Auswirkung**</span><span class="sxs-lookup"><span data-stu-id="353ae-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="353ae-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="353ae-114">**Active**</span></span>  <br/> |<span data-ttu-id="353ae-115">Der Administrator hat das Add-in hochgeladen und Benutzern oder Gruppen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="353ae-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="353ae-116">Die dem Add-In zugewiesenen Benutzer und Gruppen sehen es im jeweiligen Client.</span><span class="sxs-lookup"><span data-stu-id="353ae-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="353ae-117">**Deaktiviert**</span><span class="sxs-lookup"><span data-stu-id="353ae-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="353ae-118">Der Administrator hat das Add-In deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="353ae-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="353ae-119">Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr auf das Add-In zugreifen.</span><span class="sxs-lookup"><span data-stu-id="353ae-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="353ae-120">Wenn der Zustand des Add-Ins in "Aktiv" geändert wird, können die Benutzer und Gruppen wieder darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="353ae-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="353ae-121">**Gelöscht**</span><span class="sxs-lookup"><span data-stu-id="353ae-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="353ae-122">Der Administrator hat das Add-In gelöscht.</span><span class="sxs-lookup"><span data-stu-id="353ae-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="353ae-123">Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="353ae-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="353ae-124">Sie sollten ein Add-in in einem Fall löschen, wenn es von keinem mehr verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="353ae-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="353ae-125">Beispielsweise kann das Deaktivieren eines Add-ins sinnvoll sein, wenn ein Add-in nur zu bestimmten Jahreszeiten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="353ae-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="353ae-126">Löschen eines Add-Ins</span><span class="sxs-lookup"><span data-stu-id="353ae-126">Delete an add-in</span></span>

<span data-ttu-id="353ae-127">Sie können auch ein Add-in löschen, das bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="353ae-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="353ae-128">Wechseln Sie im Admin Center zur Seite **Einstellungen**für  >  **Dienste &-Add-ins** .</span><span class="sxs-lookup"><span data-stu-id="353ae-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="353ae-129">Wählen Sie das bereitgestellte Add-in aus.</span><span class="sxs-lookup"><span data-stu-id="353ae-129">Select the deployed add-in.</span></span>

3. <span data-ttu-id="353ae-130">Klicken Sie auf **Add-in löschen**.</span><span class="sxs-lookup"><span data-stu-id="353ae-130">Click on **Delete Add-In**.</span></span> <span data-ttu-id="353ae-131">Entfernen Sie die Add-In-Schaltfläche in der unteren rechten Ecke.</span><span class="sxs-lookup"><span data-stu-id="353ae-131">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="353ae-132">Überprüfen Sie Ihre Auswahl und wählen Sie **Add-In entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="353ae-132">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="353ae-133">Bearbeiten des Add-In-Zugangs</span><span class="sxs-lookup"><span data-stu-id="353ae-133">Edit add-in access</span></span>

<span data-ttu-id="353ae-134">Nach der Bereitstellung können Administratoren auch den Benutzer Zugriff auf Add-Ins verwalten.</span><span class="sxs-lookup"><span data-stu-id="353ae-134">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="353ae-135">Wechseln Sie im Admin Center zur Seite **Einstellungen**für  >  **Dienste &-Add-ins** .</span><span class="sxs-lookup"><span data-stu-id="353ae-135">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="353ae-136">Wählen Sie das bereitgestellte Add-in aus.</span><span class="sxs-lookup"><span data-stu-id="353ae-136">Select the deployed add-in.</span></span>

3. <span data-ttu-id="353ae-137">Klicken Sie unter **Wer hat Zugriff**auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="353ae-137">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="353ae-138">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="353ae-138">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="353ae-139">Verhindern von Add-in-Downloads durch Deaktivieren der Office Store für alle Clients (außer Outlook)</span><span class="sxs-lookup"><span data-stu-id="353ae-139">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="353ae-140">Die Outlook-Add-in-Installation wird von einem [anderen Prozess](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)verwaltet.</span><span class="sxs-lookup"><span data-stu-id="353ae-140">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="353ae-141">Als Organisation möchten Sie möglicherweise verhindern, dass neue Office-Add-Ins aus dem Office Store heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="353ae-141">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="353ae-142">Dies kann in Verbindung mit einer zentralisierten Bereitstellung verwendet werden, um sicherzustellen, dass nur von der Organisation genehmigte Add-Ins für Benutzer in Ihrer Organisation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="353ae-142">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="353ae-143">**So deaktivieren Sie die Add-in-Akquisition**</span><span class="sxs-lookup"><span data-stu-id="353ae-143">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="353ae-144">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> [Dienste &amp; Add-Ins](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="353ae-144">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>
    
3. <span data-ttu-id="353ae-145">Wählen Sie **Benutzereigene Apps und Dienste aus**.</span><span class="sxs-lookup"><span data-stu-id="353ae-145">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="353ae-146">Deaktivieren Sie die Option, um Benutzern den Zugriff auf den Office Store zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="353ae-146">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="353ae-147">Dadurch wird verhindert, dass alle Benutzer die folgenden Add-Ins aus dem Speicher erwerben.</span><span class="sxs-lookup"><span data-stu-id="353ae-147">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="353ae-148">Add-Ins für Word, Excel und PowerPoint 2016 von:</span><span class="sxs-lookup"><span data-stu-id="353ae-148">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="353ae-149">Windows</span><span class="sxs-lookup"><span data-stu-id="353ae-149">Windows</span></span>
    
  - <span data-ttu-id="353ae-150">Mac</span><span class="sxs-lookup"><span data-stu-id="353ae-150">Mac</span></span>
    
  - <span data-ttu-id="353ae-151">Office</span><span class="sxs-lookup"><span data-stu-id="353ae-151">Office</span></span>
    
    
- <span data-ttu-id="353ae-152">Übernahmen, die in **AppSource** beginnen</span><span class="sxs-lookup"><span data-stu-id="353ae-152">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="353ae-153">Add-Ins in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="353ae-153">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="353ae-154">Ein Benutzer, der versucht, auf den Store zuzugreifen, wird die folgende Meldung angezeigt: **Sorry, Microsoft 365 wurde so konfiguriert, dass die einzelne Akquisition von Office Store-Add-Ins verhindert wird.**</span><span class="sxs-lookup"><span data-stu-id="353ae-154">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="353ae-155">Unterstützung für das Deaktivieren des Office Store ist in den folgenden Versionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="353ae-155">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="353ae-156">Windows: 16.0.9001 – derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="353ae-156">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="353ae-157">Mac: 16.10.18011401 – derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="353ae-157">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="353ae-158">iOS: 2.9.18010804-derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="353ae-158">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="353ae-159">Das derzeit verfügbare Internet.</span><span class="sxs-lookup"><span data-stu-id="353ae-159">The web - Currently available.</span></span>
    
<span data-ttu-id="353ae-160">Dies hindert einen Administrator nicht daran, ein Add-in aus dem Office Store mithilfe einer zentralisierten Bereitstellung zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="353ae-160">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="353ae-161">Wenn Sie verhindern möchten, dass sich ein Benutzer mit einem Microsoft-Konto anmeldet, können Sie die Anmeldung einschränken, sodass nur das organisationskonto verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="353ae-161">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="353ae-162">Weitere Informationen finden Sie unter [Identity, Authentication und Authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="353ae-162">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="353ae-163">Weitere Informationen zur Benutzeroberfläche mit Add-ins</span><span class="sxs-lookup"><span data-stu-id="353ae-163">More about the end user experience with add-ins</span></span>

<span data-ttu-id="353ae-164">Nachdem Sie ein Add-in bereitgestellt haben, können Ihre Endbenutzer damit beginnen, es in Ihren Office-Anwendungen zu verwenden (siehe [Start mit der Office-Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="353ae-164">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="353ae-165">Das Add-in wird auf allen Plattformen angezeigt, die das Add-in unterstützt.</span><span class="sxs-lookup"><span data-stu-id="353ae-165">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="353ae-166">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span><span class="sxs-lookup"><span data-stu-id="353ae-166">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="353ae-167">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span><span class="sxs-lookup"><span data-stu-id="353ae-167">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office-Menüband mit Such Zitaten](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="353ae-169">Wenn das bereitgestellte Add-in keine Add-in-Befehle unterstützt oder wenn Sie alle bereitgestellten Add-Ins anzeigen möchten, können Sie diese über **Meine Add-ins**anzeigen.</span><span class="sxs-lookup"><span data-stu-id="353ae-169">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="353ae-170">In Word 2016, Excel 2016 oder PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="353ae-170">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="353ae-171">Wählen **Sie \> Meine Add-Ins einfügen**aus.</span><span class="sxs-lookup"><span data-stu-id="353ae-171">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="353ae-172">Wählen Sie im Office-Add-In-Fenster die Schaltfläche **Vom Administrator verwaltet** aus.</span><span class="sxs-lookup"><span data-stu-id="353ae-172">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="353ae-173">Doppelklicken Sie auf das Add-In, das Sie zuvor bereitgestellt haben (in diesem Beispiel **Zitate** ).</span><span class="sxs-lookup"><span data-stu-id="353ae-173">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="353ae-174">![Registerkarte "verwalteter Administrator" der Seite "Office-Add-Ins"](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="353ae-174">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="353ae-175">In Outlook</span><span class="sxs-lookup"><span data-stu-id="353ae-175">In Outlook</span></span>

1. <span data-ttu-id="353ae-176">Wählen Sie im Menüband **Start** die Option **Add-Ins abrufen**aus.</span><span class="sxs-lookup"><span data-stu-id="353ae-176">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="353ae-177">![Schaltfläche "Speichern" in Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="353ae-177">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="353ae-178">Wählen Sie im linken Navigationsbereich **vom Administrator verwaltete** aus.</span><span class="sxs-lookup"><span data-stu-id="353ae-178">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="353ae-179">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="353ae-179">Learn more</span></span>

[<span data-ttu-id="353ae-180">Bereitstellen von Add-Ins im Admin Center</span><span class="sxs-lookup"><span data-stu-id="353ae-180">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="353ae-181">Weitere Informationen zum Erstellen von [Office-Add-Ins](https://go.microsoft.com/fwlink/p/?linkid=846362)</span><span class="sxs-lookup"><span data-stu-id="353ae-181">Learn more about creating and building [Office Add-ins](https://go.microsoft.com/fwlink/p/?linkid=846362).</span></span>
  
<span data-ttu-id="353ae-182">[Verwenden Sie PowerShell-Cmdlets für zentralisierte Bereitstellung zum Verwalten von Add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span><span class="sxs-lookup"><span data-stu-id="353ae-182">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="353ae-183">Problembehandlung: Benutzer können keine Add-Ins sehen</span><span class="sxs-lookup"><span data-stu-id="353ae-183">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="353ae-184">Minderjährige und Erwerb von Add-Ins aus dem Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="353ae-184">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)