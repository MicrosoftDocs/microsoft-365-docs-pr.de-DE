---
title: Wiederherstellen einer gelöschten Office 365-Gruppe
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 'Hier erfahren Sie, wie Sie eine Office 365-Gruppe über das Exchange Admin Center wiederherstellen. '
ms.openlocfilehash: c88f10df27e5f3a0af79c93c7d0e347c5646abc9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352436"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="0e623-103">Wiederherstellen einer gelöschten Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="0e623-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="0e623-104">Wenn Sie der Besitzer einer Office 365-Gruppe sind, können Sie die Gruppe selbst wiederherstellen, indem Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="0e623-104">If you are the owner of an Office 365 group, you can restore the group yourself by following these steps.</span></span>

1. <span data-ttu-id="0e623-105">Wählen Sie auf der Seite [Gelöschte Gruppen](https://outlook.office.com/people/group/deleted)die Option **Gruppen verwalten** unter dem Knoten **Gruppen** und dann **Gelöscht** aus.</span><span class="sxs-lookup"><span data-stu-id="0e623-105">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="0e623-106">Klicken Sie auf die Schaltfläche **Wiederherstellen** neben der Gruppe, die Sie wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0e623-106">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="0e623-107">Wenn die gelöschte Gruppe hier nicht angezeigt wird, wenden Sie sich an einen Administrator.</span><span class="sxs-lookup"><span data-stu-id="0e623-107">If the deleted group doesn't appear here, contact an administrator.</span></span>
  
<span data-ttu-id="0e623-108">Wenn Sie ein Benutzer sind, der eine Office 365-Gruppe wiederherstellen möchte, bitten Sie einen Administrator, diese Schritte für Sie auszuführen, oder wenden Sie sich an Ihren Helpdesk.</span><span class="sxs-lookup"><span data-stu-id="0e623-108">If you're a user who wants to restore an Office 365 group, ask an administrator to do these steps for you or contact your help desk.</span></span>  
   
<span data-ttu-id="0e623-109">Wenn Sie eine Gruppe gelöscht haben, wird Sie standardmäßig 30 Tage lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="0e623-109">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="0e623-110">Dieser 30-Tage-Zeitraum wird als Aufbewahrungsfrist für das vorläufige Löschen betrachtet, weil ein Wiederherstellen der Gruppe während dieses Zeitraums noch möglich ist.</span><span class="sxs-lookup"><span data-stu-id="0e623-110">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="0e623-111">Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0e623-111">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>
  
<span data-ttu-id="0e623-112">Wenn ein Benutzer während der Aufbewahrungsfrist für das vorläufige Löschen versucht, auf die Website zuzugreifen, wird eine "404 _Verboten_"-Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e623-112">During the "soft-delete" period, if a user tries to access the site they will get a 404 _forbidden_ message.</span></span> <span data-ttu-id="0e623-113">Wenn ein Benutzer nach Ablauf dieses Zeitraums versucht, auf die Website zuzugreifen, wird eine "404 _Nicht gefunden_"-Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e623-113">After this period, if a user tries to access the site, they will get a 404 _not found_ message.</span></span>
  
<span data-ttu-id="0e623-114">Beim Wiederherstellen einer Gruppe werden folgende Inhalte wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="0e623-114">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="0e623-115">Objekte, Eigenschaften und Mitglieder von Office 365-Gruppen in Azure Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="0e623-115">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="0e623-116">E-Mail-Adressen von Gruppen.</span><span class="sxs-lookup"><span data-stu-id="0e623-116">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="0e623-117">Der freigegebene Posteingang und Kalender in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0e623-117">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="0e623-118">Die SharePoint Online-Teamwebsite und die entsprechenden Dateien.</span><span class="sxs-lookup"><span data-stu-id="0e623-118">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="0e623-119">OneNote-Notizbuch</span><span class="sxs-lookup"><span data-stu-id="0e623-119">OneNote notebook</span></span>
    
- <span data-ttu-id="0e623-120">Planner</span><span class="sxs-lookup"><span data-stu-id="0e623-120">Planner</span></span>
    
- <span data-ttu-id="0e623-121">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0e623-121">Teams</span></span>

- <span data-ttu-id="0e623-122">Yammer-Gruppe und Gruppeninhalt (wenn die Office 365-Gruppe aus Yammer erstellt wurde)</span><span class="sxs-lookup"><span data-stu-id="0e623-122">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>
    
<span data-ttu-id="0e623-123">Sie können eine [Endgültiges Löschen einer Office 365-Gruppe](#permanently-delete-an-office-365-group), wenn Sie nicht warten möchten, bis der Aufbewahrungszeitraum von 30 Tagen abläuft und der Inhalt dann endgültig gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="0e623-123">You can also [Permanently delete an Office 365 group](#permanently-delete-an-office-365-group) if you can't wait the 30 days for the retention period to expire for the content to be permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="0e623-124">Auch der Besitzer der gelöschten Office 365-Gruppe kann die Gruppe wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="0e623-124">The owner of the deleted Office 365 group is also able to restore the group.</span></span> <span data-ttu-id="0e623-125">Informationen zum Wiederherstellen einer Office 365-Gruppe mit Besitzer- und ohne Administratorberechtigung finden Sie unter [Wiederherstellen einer Office 365-Gruppe mithilfe von PowerShell](#restore-an-office-365-group-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="0e623-125">To restore an office 365 group using owner permission without administrator permission, see [Restore an Office 365 Group using PowerShell](#restore-an-office-365-group-using-powershell).</span></span>

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a><span data-ttu-id="0e623-126">Wiederherstellen einer Office 365-Gruppe über das Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="0e623-126">Restore an Office 365 Group using the Exchange admin center</span></span>

<span data-ttu-id="0e623-127">Sie benötigen globale Administratorberechtigungen für Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e623-127">You must have Office 365 global administrator permissions.</span></span>

1. <span data-ttu-id="0e623-128">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="0e623-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="0e623-129">Wählen Sie im Exchange Admin Center die Optionen **Empfänger** und dann **Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="0e623-129">In the Exchange admin center, select **recipients**, and then choose **groups**.</span></span> <span data-ttu-id="0e623-130">Sie können anzeigen, ob die Gruppe aktiv ist oder vorläufig gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="0e623-130">You can view whether the group is Active or soft-deleted.</span></span> <span data-ttu-id="0e623-131">Wenn die Gruppe endgültig gelöscht wurde, wird sie definitiv nicht mehr aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e623-131">If the group has been permanently deleted, it won't be listed at all.</span></span>
  
3. <span data-ttu-id="0e623-132">Um die genaue Zeit anzuzeigen, zu der die Gruppe vorläufig gelöscht wurde, wählen Sie die Gruppe aus, und zeigen Sie die Informationen im rechten Bereich an.</span><span class="sxs-lookup"><span data-stu-id="0e623-132">To view the exact time when the group was soft-deleted, select the group and view the info in the right pane.</span></span>
      
4. <span data-ttu-id="0e623-133">Wählen Sie die Gruppe, die Sie wiederherstellen möchten, und dann das Symbol "Wiederherstellen" aus.</span><span class="sxs-lookup"><span data-stu-id="0e623-133">Select the group you want to restore, and then select the restore icon.</span></span>
    
    ![Wählen Sie die Gruppe, die Sie wiederherstellen möchten, und dann das Symbol "Wiederherstellen" aus.](../../media/restore-group.png)
  
5. <span data-ttu-id="0e623-135">Wählen Sie "Aktualisieren" aus.</span><span class="sxs-lookup"><span data-stu-id="0e623-135">Select refresh</span></span> ![Aktualisieren (Symbol)](../../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) <span data-ttu-id="0e623-137">aus, um die Informationen auf der Seite zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0e623-137">to update the information on the page.</span></span> <span data-ttu-id="0e623-138">Ihre Gruppe wird als "Aktiv" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e623-138">Your group will show as Active.</span></span> <span data-ttu-id="0e623-139">Alle Formulare und Formulardaten, die mit Ihrer Gruppe verbunden sind, werden ebenfalls wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="0e623-139">Any forms and form data associated with your group will also be restored.</span></span>
    
## <a name="restore-an-office-365-group-using-powershell"></a><span data-ttu-id="0e623-140">Wiederherstellen einer Office 365-Gruppe mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e623-140">Restore an Office 365 Group using PowerShell</span></span>

<span data-ttu-id="0e623-141">Sie müssen über globale Administratorberechtigungen für Office 365 verfügen oder ein ehemaliger Besitzer der gelöschten Office 365-Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="0e623-141">You must have Office 365 global administrator permissions, or be a former owner of the deleted Office 365 group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e623-142">Wenn Sie in PowerShell zum Löschen einer Gruppe "Remove-MsolGroup" verwenden, wird die Gruppe endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="0e623-142">If you use Remove-MsolGroup in PowerShell to delete a group, this will delete the group permanently.</span></span> <span data-ttu-id="0e623-143">Wenn Sie PowerShell zum Löschen von Gruppen verwenden, empfiehlt sich die Verwendung von **Remove-AzureADMSGroup**, um die Office 365-Gruppe vorläufig zu löschen.</span><span class="sxs-lookup"><span data-stu-id="0e623-143">When using PowerShell to delete groups, it's best practice to use **Remove-AzureADMSGroup** to soft-delete the Office 365 group.</span></span> <span data-ttu-id="0e623-144">Auf diese Weise können Sie die Gruppe bei Bedarf wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="0e623-144">That way you can restore it if needed.</span></span> 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="0e623-145">Installieren der Vorschauversion von Azure Active Directory PowerShell für Graph</span><span class="sxs-lookup"><span data-stu-id="0e623-145">Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e623-146">Sie können nicht gleichzeitig Preview- und GA-Version auf demselben Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="0e623-146">You cannot install both the preview and GA versions on the same computer at the same time.</span></span>
  
<span data-ttu-id="0e623-147">Als bewährte Methode empfehlen wir, *immer* die neueste Version zu verwenden: Deinstallieren Sie also die alte AzureADPreview- bzw. AzureAD-Version, und holen Sie sich die aktuellste Version.</span><span class="sxs-lookup"><span data-stu-id="0e623-147">As a best practice, we recommend *always* staying current, i.e. uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
 
1. <span data-ttu-id="0e623-148">Geben Sie in der Suchleiste "Windows PowerShell" ein.</span><span class="sxs-lookup"><span data-stu-id="0e623-148">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="0e623-149">Klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0e623-149">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
  
2. <span data-ttu-id="0e623-150">Überprüfen Sie die installierten Module:</span><span class="sxs-lookup"><span data-stu-id="0e623-150">Review your installed modules:</span></span>
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. <span data-ttu-id="0e623-151">Führen Sie zum Deinstallieren einer früheren Version von AzureADPreview oder AzureAD diesen Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="0e623-151">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
```
   Uninstall-Module AzureADPreview
```

<span data-ttu-id="0e623-152">oder</span><span class="sxs-lookup"><span data-stu-id="0e623-152">or</span></span>
  
```
   Uninstall-Module AzureAD
```

4. <span data-ttu-id="0e623-153">Führen Sie zum Installieren der aktuellsten Version von AzureADPreview diesen Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="0e623-153">To install the latest version of AzureADPreview, run this command:</span></span>
  
```
   Install-Module AzureADPreview
```



<span data-ttu-id="0e623-154">Geben Sie in der Nachricht über ein nicht vertrauenswürdiges Repository **J** ein. Die Installation des neuen Moduls dauert etwa eine Minute.</span><span class="sxs-lookup"><span data-stu-id="0e623-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>
  
### <a name="restore-the-deleted-group"></a><span data-ttu-id="0e623-155">Wiederherstellen der gelöschten Gruppe</span><span class="sxs-lookup"><span data-stu-id="0e623-155">Restore the deleted group</span></span>
  
1. <span data-ttu-id="0e623-156">Haben Sie das **AzureADPreview**-Modul installiert, wie im vorstehenden Abschnitt "Installieren der Preview-Version des Azure Active Directory-Moduls für Windows PowerShell" beschrieben?</span><span class="sxs-lookup"><span data-stu-id="0e623-156">Did you install the **AzureADPreview** module, as instructed in the previoius section "Install the preview version of the Azure Active Directory Module for Windows PowerShell"?</span></span>  <span data-ttu-id="0e623-157">Das Fehlen der aktuellsten **Preview**-Version ist der Hauptgrund, warum diese Schritte nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="0e623-157">Not having the most current **preview** version is the #1 reason these steps don't work for people.</span></span> 
    
2. <span data-ttu-id="0e623-158">Falls noch nicht geschehen, öffnen Sie ein Windows PowerShell-Fenster auf dem Computer (es spielt keine Rolle, ob es sich um ein normales Windows PowerShell-Fenster handelt oder eines, das Sie durch Auswählen von **Als Administrator ausführen** geöffnet haben).</span><span class="sxs-lookup"><span data-stu-id="0e623-158">If you haven't already, open a Windows PowerShell window on your computer (it doesn't matter if it's a normal Windows PowerShell window, or one you opened by selecting **Run as administrator**).</span></span>
    
3. <span data-ttu-id="0e623-159">Führen Sie die folgenden Befehle aus. Drücken Sie dazu nach jedem Befehl die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="0e623-159">Run the following commands by pressing **Enter** after each one:</span></span> 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  <span data-ttu-id="0e623-160">Geben Sie auf dem angezeigten Bildschirm **Bei Ihrem Konto anmelden** den Benutzernamen und das Kennwort Ihres Administratorkontos ein, um eine Verbindung mit Ihrem Azure AD-Dienst herzustellen, und wählen Sie **Anmelden** aus.</span><span class="sxs-lookup"><span data-stu-id="0e623-160">On the **Sign in to your Account** screen that opens, enter your administrative account user name and password to connect you to your Azure AD service, and select **Sign in**.</span></span>
  
4. <span data-ttu-id="0e623-161">Führen Sie den folgenden Befehl aus, um alle vorläufig gelöschten Office 365-Gruppen in Ihrer Organisation anzuzeigen, die noch innerhalb des Aufbewahrungszeitraums von 30 Tagen für das vorläufige Löschen liegen:</span><span class="sxs-lookup"><span data-stu-id="0e623-161">Run this command to display all soft-deleted Office 365 groups in your organization that are still within the 30 day soft-deletion period:</span></span>
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. <span data-ttu-id="0e623-162">Notieren Sie sich die Objekt-ID der Gruppe(n), die Sie wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0e623-162">Take note of the object ID of the group, or groups, you want to restore.</span></span> <span data-ttu-id="0e623-163">Wenn die Gruppe, nach der Sie suchen, nicht in dieser Liste enthalten ist, wurde sie wahrscheinlich bereits endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="0e623-163">If you don't see the group you're looking for on this list then it has likely been permanently purged already.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="0e623-164">Wenn eine neue Gruppe mit demselben Alias oder derselben SMTP-Adresse wie Ihre gelöschte Gruppe erstellt wurde, müssen Sie diese neue Gruppe löschen, um Ihre gelöschte Gruppe wiederherstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="0e623-164">If a new group has been created with the same alias or SMTP address as your deleted group, you will have to delete that new group before you'll be able to restore your deleted group.</span></span> 
  
6. <span data-ttu-id="0e623-165">Führen Sie zum Wiederherstellen dieser Gruppe den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="0e623-165">To restore that group, run this command:</span></span>
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. <span data-ttu-id="0e623-166">Dieser Vorgang dauert in der Regel nur ein paar Minuten, in einigen seltenen Fällen kann die vollständige Wiederherstellung jedoch bis zu 24 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="0e623-166">This process usually takes just a few minutes but in a few rare cases it can take as long as 24 hours to be completely restored.</span></span> <span data-ttu-id="0e623-167">Führen Sie in PowerShell den folgenden Befehl aus, um zu überprüfen, ob die Gruppe erfolgreich wiederhergestellt wurde:</span><span class="sxs-lookup"><span data-stu-id="0e623-167">To verify that the group has been successfully restored, run this command in PowerShell:</span></span>
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

<span data-ttu-id="0e623-p110">Sobald die Wiederherstellung erfolgreich abgeschlossen wurde, sollte die Gruppe wieder in Outlook und Outlook im Web im Navigationsbereich angezeigt werden. Alle wiederhergestellten Inhalte (einschließlich SharePoint und Planner) sollten den Mitgliedern der Gruppe wieder zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="0e623-p110">Once the restore has successfully completed, the group should reappear on the navigation pane in Outlook and Outlook on the web. All restored content, including SharePoint and Planner, should be available to the group members again.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="0e623-170">Endgültiges Löschen einer Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="0e623-170">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="0e623-171">Manchmal möchten Sie vielleicht eine Gruppe endgültig löschen, ohne den Ablauf der 30-Tage-Frist für das vorläufige Löschen abzuwarten.</span><span class="sxs-lookup"><span data-stu-id="0e623-171">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="0e623-172">Starten Sie hierzu PowerShell, und führen Sie den folgenden Befehl aus, um die Objekt-ID der Gruppe abzurufen:</span><span class="sxs-lookup"><span data-stu-id="0e623-172">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="0e623-173">Notieren Sie sich die Objekt-ID der Gruppe(n), die Sie endgültig löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="0e623-173">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="0e623-174">Durch das endgültige Löschen der Gruppe werden die Gruppe und alle zugehörigen Daten für immer entfernt.</span><span class="sxs-lookup"><span data-stu-id="0e623-174">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="0e623-175">Führen Sie in PowerShell den folgenden Befehl aus, um die Gruppe endgültig zu löschen:</span><span class="sxs-lookup"><span data-stu-id="0e623-175">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="0e623-p112">Führen Sie zur Bestätigung, dass die Gruppe erfolgreich endgültig gelöscht wurde, das Cmdlet  *Get-AzureADMSDeletedGroup*  erneut aus, um sicherzustellen, dass die Gruppe nicht mehr in der Liste vorläufig gelöschter Gruppen angezeigt wird. In einigen Fällen kann es bis zu 24 Stunden dauern, bis die Gruppe und alle zugehörigen Daten endgültig gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="0e623-p112">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="0e623-178">Haben Sie Fragen zu Office 365-Gruppen?</span><span class="sxs-lookup"><span data-stu-id="0e623-178">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="0e623-179">Besuchen Sie die [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups), um Fragen zu posten und an Unterhaltungen zu Office 365-Gruppen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="0e623-179">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="0e623-180">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="0e623-180">Related articles</span></span>

[<span data-ttu-id="0e623-181">Verwalten von Office 365-Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e623-181">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="0e623-182">Löschen von Gruppen mit dem Cmdlet "Remove-UnifiedGroup"</span><span class="sxs-lookup"><span data-stu-id="0e623-182">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="0e623-183">Verwalten Ihrer gruppenabhängigen Teamwebsiteeinstellungen</span><span class="sxs-lookup"><span data-stu-id="0e623-183">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="0e623-184">Löschen einer Gruppe in Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0e623-184">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
