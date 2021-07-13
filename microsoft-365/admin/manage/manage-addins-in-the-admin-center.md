---
title: Verwalten von Add-Ins im Admin Center
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
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Erfahren Sie mehr über die Verwendung zentralisierter Add-Ins zum Bereitstellen von Add-Ins für Benutzer und Gruppen in Ihrer Organisation.
ms.openlocfilehash: aad68d37fb23c26ef1a1ca1ba7dfc5d4e2a40bfe
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392863"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="4ee8c-103">Verwalten von Add-Ins im Admin Center</span><span class="sxs-lookup"><span data-stu-id="4ee8c-103">Manage add-ins in the admin center</span></span>

<span data-ttu-id="4ee8c-104">Office-Add-Ins helfen Ihnen, Ihre Dokumente zu personalisieren und den Zugriff auf Informationen im Web zu optimieren (siehe [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="4ee8c-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="4ee8c-105">Nachdem ein Administrator Add-Ins für Benutzer in einer Organisation bereitgestellt hat, kann der Administrator Add-Ins deaktivieren oder aktivieren, bearbeiten, löschen und den Zugriff auf die Add-Ins verwalten.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-105">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="4ee8c-106">Weitere Informationen zum Installieren von Add-Ins aus dem Admin Center finden Sie unter [Bereitstellen von Add-Ins im Admin Center.](./manage-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="4ee8c-106">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="4ee8c-107">Add-In-Status</span><span class="sxs-lookup"><span data-stu-id="4ee8c-107">Add-in states</span></span>

<span data-ttu-id="4ee8c-108">Ein Add-In kann den Status **"Ein"** oder **"Aus"** aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-108">An add-in can be in either the **On** or **Off** state.</span></span>
  
| <span data-ttu-id="4ee8c-109">Status</span><span class="sxs-lookup"><span data-stu-id="4ee8c-109">State</span></span> | <span data-ttu-id="4ee8c-110">Auftreten des Status</span><span class="sxs-lookup"><span data-stu-id="4ee8c-110">How the state occurs</span></span> | <span data-ttu-id="4ee8c-111">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="4ee8c-111">Impact</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="4ee8c-112">**Aktiv**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-112">**Active**</span></span>  <br/> |<span data-ttu-id="4ee8c-113">Der Administrator hat das Add-In hochgeladen und benutzern oder Gruppen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-113">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="4ee8c-114">Die dem Add-In zugewiesenen Benutzer und Gruppen sehen es im jeweiligen Client.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-114">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="4ee8c-115">**Deaktiviert**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-115">**Turned off**</span></span>  <br/> |<span data-ttu-id="4ee8c-116">Der Administrator hat das Add-In deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-116">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="4ee8c-117">Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr auf das Add-In zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-117">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="4ee8c-118">Wenn der Zustand des Add-Ins in "Aktiv" geändert wird, können die Benutzer und Gruppen wieder darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-118">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="4ee8c-119">**Gelöscht**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-119">**Deleted**</span></span>  <br/> |<span data-ttu-id="4ee8c-120">Der Administrator hat das Add-In gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-120">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="4ee8c-121">Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-121">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="4ee8c-122">Erwägen Sie das Löschen eines Add-Ins, wenn es nicht mehr verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-122">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="4ee8c-123">Beispielsweise kann das Deaktivieren eines Add-Ins sinnvoll sein, wenn ein Add-In nur zu bestimmten Zeiten des Jahres verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-123">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="4ee8c-124">Löschen eines Add-Ins</span><span class="sxs-lookup"><span data-stu-id="4ee8c-124">Delete an add-in</span></span>

<span data-ttu-id="4ee8c-125">Sie können auch ein Add-In löschen, das bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-125">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="4ee8c-126">Wechseln Sie im Admin Center zur Seite **Einstellungen**  >  **Dienste & Add-Ins.**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-126">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ee8c-127">Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-127">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="4ee8c-128">Wenn die oben beschriebenen Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt "Zentrale Bereitstellung", indem Sie zu **Einstellungen**  >  **integrierten Apps** wechseln.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-128">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="4ee8c-129">Wählen Sie oben auf der Seite **"Integrierte Apps"** die Option **"Add-Ins" aus.**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="4ee8c-130">Wählen Sie das bereitgestellte Add-In aus.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-130">Select the deployed add-in.</span></span>

3. <span data-ttu-id="4ee8c-131">Klicken Sie auf **"Add-In löschen".**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-131">Click on **Delete Add-In**.</span></span> <span data-ttu-id="4ee8c-132">Entfernen Sie die Add-In-Schaltfläche in der unteren rechten Ecke.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-132">Remove the Add-in button on the bottom-right corner.</span></span>

4. <span data-ttu-id="4ee8c-133">Überprüfen Sie Ihre Auswahl und wählen Sie **Add-In entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-133">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="4ee8c-134">Bearbeiten des Add-In-Zugangs</span><span class="sxs-lookup"><span data-stu-id="4ee8c-134">Edit add-in access</span></span>

<span data-ttu-id="4ee8c-135">Nach der Bereitstellung können Administratoren auch den Benutzerzugriff auf Add-Ins verwalten.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-135">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="4ee8c-136">Wechseln Sie im Admin Center zur Seite **Einstellungen**  >  **Dienste & Add-Ins.**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-136">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ee8c-137">Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-137">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="4ee8c-138">Wenn die oben beschriebenen Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt "Zentrale Bereitstellung", indem Sie zu **Einstellungen**  >  **integrierten Apps** wechseln.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-138">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="4ee8c-139">Wählen Sie oben auf der Seite **"Integrierte Apps"** die Option **"Add-Ins" aus.**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-139">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="4ee8c-140">Wählen Sie das bereitgestellte Add-In aus.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-140">Select the deployed add-in.</span></span>

3. <span data-ttu-id="4ee8c-141">Klicken Sie auf **"Bearbeiten"** unter **Wer Zugriff hat.**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-141">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="4ee8c-142">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-142">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="4ee8c-143">Verhindern von Add-In-Downloads durch Deaktivieren der Office Store auf allen Clients (außer Outlook)</span><span class="sxs-lookup"><span data-stu-id="4ee8c-143">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="4ee8c-144">Outlook Add-In-Installation wird durch einen [anderen Prozess](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)verwaltet.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-144">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="4ee8c-145">Als Organisation möchten Sie möglicherweise verhindern, dass neue Office-Add-Ins aus dem Office Store heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-145">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="4ee8c-146">Dies kann in Verbindung mit der zentralen Bereitstellung verwendet werden, um sicherzustellen, dass nur von der Organisation genehmigte Add-Ins für Benutzer innerhalb Ihrer Organisation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-146">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="4ee8c-147">**So deaktivieren Sie den Add-In-Erwerb**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-147">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="4ee8c-148">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> [Dienste &amp; Add-Ins](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="4ee8c-148">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ee8c-149">Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-149">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="4ee8c-150">Wenn die oben beschriebenen Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt "Zentrale Bereitstellung", indem Sie zu **Einstellungen**  >  **integrierten Apps** wechseln.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-150">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="4ee8c-151">Wählen Sie oben auf der Seite **"Integrierte Apps"** die Option **"Add-Ins" aus.**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-151">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="4ee8c-152">Wählen Sie **Benutzereigene Apps und Dienste aus**.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-152">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="4ee8c-153">Deaktivieren Sie die Option, um Benutzern den Zugriff auf den Office Store zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-153">Clear the option to let users access the Office store.</span></span>

    <span data-ttu-id="4ee8c-154">Dadurch wird verhindert, dass alle Benutzer die folgenden Add-Ins aus dem Store erwerben.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-154">This will prevent all users from acquiring the following add-ins from the store.</span></span>
      
    - <span data-ttu-id="4ee8c-155">Add-Ins für Word, Excel und PowerPoint 2016 aus:</span><span class="sxs-lookup"><span data-stu-id="4ee8c-155">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
        
      - <span data-ttu-id="4ee8c-156">Windows</span><span class="sxs-lookup"><span data-stu-id="4ee8c-156">Windows</span></span>
      - <span data-ttu-id="4ee8c-157">Mac</span><span class="sxs-lookup"><span data-stu-id="4ee8c-157">Mac</span></span>
      - <span data-ttu-id="4ee8c-158">Office</span><span class="sxs-lookup"><span data-stu-id="4ee8c-158">Office</span></span>
        
        
    - <span data-ttu-id="4ee8c-159">Käufe beginnend mit **AppSource**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-159">Acquisitions starting within **AppSource**</span></span>
        
    - <span data-ttu-id="4ee8c-160">Add-Ins in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ee8c-160">Add-ins within Microsoft 365</span></span>
        
    <span data-ttu-id="4ee8c-161">Einem Benutzer, der versucht, auf den Store zuzugreifen, wird die folgende Meldung angezeigt: Leider wurde Microsoft 365 so konfiguriert, dass der **einzelne Erwerb von Office Store-Add-Ins verhindert wird.**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-161">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="4ee8c-162">Unterstützung für das Deaktivieren des Office Store ist in den folgenden Versionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="4ee8c-162">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="4ee8c-163">Windows: 16.0.9001 – Derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-163">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="4ee8c-164">Mac: 16.10.18011401 – Derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-164">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="4ee8c-165">iOS: 2.9.18010804 – Derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-165">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="4ee8c-166">Das Web – derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-166">The web - Currently available.</span></span>
    
<span data-ttu-id="4ee8c-167">Dies hindert einen Administrator nicht daran, die zentrale Bereitstellung zum Zuweisen eines Add-Ins aus dem Office Store zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-167">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>

> [!NOTE] 
> <span data-ttu-id="4ee8c-168">Add-Ins wie Visio Data Visualizer, Bing Karten und People Graph werden weiterhin im Menüband angezeigt, auch wenn ein Administrator die Store deaktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-168">Add-ins such as Visio Data Visualizer, Bing Maps, and People Graph will still show up in the ribbon, even if an admin has disabled the Store.</span></span> <span data-ttu-id="4ee8c-169">Um diese Links zu entfernen, müssen Administratoren die Store über das Gruppenrichtlinienobjekt (Group Policy Object, GPO) deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-169">To remove these links, administrators must disable the Store through Group Policy Object (GPO).</span></span>
  
<span data-ttu-id="4ee8c-170">Um zu verhindern, dass sich ein Benutzer mit einem Microsoft-Konto anmeldet, können Sie die Anmeldung so einschränken, dass nur das Organisationskonto verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="4ee8c-171">Weitere Informationen finden Sie unter [Identität, Authentifizierung und Autorisierung in Office 2016.](/DeployOffice/security/identity-authentication-and-authorization-in-office)</span><span class="sxs-lookup"><span data-stu-id="4ee8c-171">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE] 
> <span data-ttu-id="4ee8c-172">Wenn Benutzer am Zugriff auf den Office Store gehindert werden, wird auch verhindert, dass sie [Office-Add-Ins zu Testzwecken aus einer Netzwerkfreigabe querladen.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="4ee8c-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing from a network share](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="4ee8c-173">Weitere Informationen zur Endbenutzererfahrung mit Add-Ins</span><span class="sxs-lookup"><span data-stu-id="4ee8c-173">More about the end-user experience with add-ins</span></span>

<span data-ttu-id="4ee8c-174">Nachdem Sie ein Add-In bereitgestellt haben, können Ihre Endbenutzer mit der Verwendung in ihren Office-Anwendungen beginnen (siehe ["Start using your Office Add-in").](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="4ee8c-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="4ee8c-175">Das Add-In wird auf allen Plattformen angezeigt, die das Add-In unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="4ee8c-p110">Wenn das Add-In Add-In-Befehle unterstützt, werden diese im Office-Menüband angezeigt. Im folgenden Beispiel wird der Befehl **Zitat suchen** für das Add-In **Zitate** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-p110">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office Menüband mit Suchz zitaten](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="4ee8c-179">Wenn das bereitgestellte Add-In keine Add-In-Befehle unterstützt oder wenn Sie alle bereitgestellten Add-Ins anzeigen möchten, können Sie diese über **Meine Add-Ins** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="4ee8c-180">In Word 2016, Excel 2016 oder PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="4ee8c-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="4ee8c-181">Wählen Sie **\> "Meine Add-Ins einfügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="4ee8c-182">Wählen Sie im Office-Add-In-Fenster die Schaltfläche **Vom Administrator verwaltet** aus.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="4ee8c-183">Doppelklicken Sie auf das Add-In, das Sie zuvor bereitgestellt haben (in diesem Beispiel **Zitate).**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-183">Double-click the add-in you deployed earlier (in this example, **Citations**).</span></span>

    ![Registerkarte "Vom Administrator verwaltet" der Seite "Office-Add-Ins"](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a><span data-ttu-id="4ee8c-185">In Outlook</span><span class="sxs-lookup"><span data-stu-id="4ee8c-185">In Outlook</span></span>

1. <span data-ttu-id="4ee8c-186">Wählen Sie im Menüband **"Start"** die Option **"Add-Ins abrufen" aus.**</span><span class="sxs-lookup"><span data-stu-id="4ee8c-186">On the **Home** ribbon, select **Get Add-ins**.</span></span>

    ![Schaltfläche "Speichern" in Outlook](../../media/getaddinsicon.png)
  
2. <span data-ttu-id="4ee8c-188">Wählen Sie im linken Navigationsbereich **vom Administrator verwaltete** aus.</span><span class="sxs-lookup"><span data-stu-id="4ee8c-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="related-content"></a><span data-ttu-id="4ee8c-189">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="4ee8c-189">Related content</span></span>

<span data-ttu-id="4ee8c-190">[Bereitstellen von Add-Ins im Admin Center](./manage-deployment-of-add-ins.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="4ee8c-190">[Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="4ee8c-191">Weitere Informationen zum Erstellen und Erstellen [von Office-Add-Ins](/office/dev/add-ins/overview/office-add-ins) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="4ee8c-191">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins) (article)</span></span>\
<span data-ttu-id="4ee8c-192">[Verwenden von PowerShell-Cmdlets für die zentrale Bereitstellung zum Verwalten von Add-Ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="4ee8c-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)</span></span>\
<span data-ttu-id="4ee8c-193">[Problembehandlung: Benutzer sehen keine Add-Ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="4ee8c-193">[Troubleshoot: User not seeing add-ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (article)</span></span>\
<span data-ttu-id="4ee8c-194">[Minderjährige und Erwerb von Add-Ins aus dem Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="4ee8c-194">[Minors and acquiring add-ins from the Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (article)</span></span>
