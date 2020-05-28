---
title: Zugreifen auf die und Sichern der Daten eines ehemaligen Mitarbeiters
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: Hier erfahren Sie, wie Sie die Dateien und e-Mails eines Mitarbeiters beibehalten, wenn die Person Ihre Organisation verlässt.
ms.openlocfilehash: 2bf32aa9e7a3dcc76ae2114240bff07d697ce29d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387201"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="4b3ae-103">Zugreifen auf die und Sichern der Daten eines ehemaligen Benutzers</span><span class="sxs-lookup"><span data-stu-id="4b3ae-103">Get access to and back up a former user's data</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4b3ae-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-104">The admin center is changing.</span></span> <span data-ttu-id="4b3ae-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="4b3ae-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end


<span data-ttu-id="4b3ae-106">Wenn ein Mitarbeiter Ihre Organisation verlässt, möchten Sie wahrscheinlich auf Ihre Daten (Dokumente und e-Mails) zugreifen und diese entweder überprüfen, sichern oder an einen neuen Mitarbeiter weitergeben.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-106">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="4b3ae-107">Zugreifen auf OneDrive-Dokumente eines früheren Benutzers</span><span class="sxs-lookup"><span data-stu-id="4b3ae-107">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="4b3ae-108">Wenn Sie die Lizenz eines Benutzers entfernen, aber das Konto nicht löschen, können Sie sich selbst Zugriff auf die Inhalte im OneDrive des Benutzers verschaffen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-108">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="4b3ae-109">Wenn Sie das Konto des Benutzers löschen, haben Sie standardmäßig 30 Tage Zeit, um auf die OneDrive-Daten des früheren Benutzers zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-109">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="4b3ae-110">[Hier erfahren Sie, wie Sie die OneDrive-Aufbewahrung für gelöschte Benutzer festlegen](/onedrive/set-retention).</span><span class="sxs-lookup"><span data-stu-id="4b3ae-110">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="4b3ae-111">Wenn Sie innerhalb dieses Zeitraums kein [Benutzerkonto wiederherstellen](/office365/admin/add-users/restore-user) , wird der OneDrive-Inhalt gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-111">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="4b3ae-112">Um die OneDrive-Dateien eines früheren Benutzers beizubehalten, geben Sie sich zunächst Zugriff auf Ihre OneDrive, und legen Sie dann die Dateien, die Sie behalten möchten, fest.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-112">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="4b3ae-113">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-113">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="4b3ae-114">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="4b3ae-115">Wählen Sie einen Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-115">Select a user.</span></span>

3. <span data-ttu-id="4b3ae-116">Wählen Sie im rechten Bereich **OneDrive**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-116">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="4b3ae-117">Wählen Sie unter **Zugriff auf Dateien abrufen die**Option **Link zu Dateien erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-117">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="4b3ae-118">Wählen Sie den Link aus, um den Dateispeicherort zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-118">Select the link to open the file location.</span></span> <span data-ttu-id="4b3ae-119">Laden Sie die Dateien auf Ihren Computer herunter, **oder wählen Sie "in"** oder " **Kopieren nach** " aus, um Sie in Ihr eigenes OneDrive oder in eine freigegebene Bibliothek zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-119">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="4b3ae-120">Sie können Dateien und Ordner gleichzeitig auf bis zu 500 MB kopieren.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-120">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="4b3ae-121">Wenn Sie Dokumente mit dem Versionsverlauf verschieben oder kopieren, wird nur die neueste Version verschoben.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-121">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4b3ae-122">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="4b3ae-123">Wählen Sie einen Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-123">Select a user.</span></span>

3. <span data-ttu-id="4b3ae-124">Erweitern Sie im rechten Bereich **OneDrive-Einstellungen**, und wählen Sie dann neben **Zugriff**die Option **Access Files**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-124">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="4b3ae-125">Wählen Sie den Link aus, um den Dateispeicherort zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-125">Select the link to open the file location.</span></span> <span data-ttu-id="4b3ae-126">Laden Sie die Dateien auf Ihren Computer herunter, **oder wählen Sie "in"** oder " **Kopieren nach** " aus, um Sie in Ihr eigenes OneDrive oder in eine freigegebene Bibliothek zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-126">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="4b3ae-127">Sie können Dateien und Ordner gleichzeitig auf bis zu 500 MB kopieren.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-127">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="4b3ae-128">Wenn Sie Dokumente mit dem Versionsverlauf verschieben oder kopieren, wird nur die neueste Version verschoben.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-128">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4b3ae-129">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="4b3ae-130">Wählen Sie einen Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-130">Select a user.</span></span>

3. <span data-ttu-id="4b3ae-131">Erweitern Sie im rechten Bereich **OneDrive-Einstellungen**, und wählen Sie dann neben **Zugriff**die Option **Access Files**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-131">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="4b3ae-132">Wählen Sie den Link aus, um den Dateispeicherort zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-132">Select the link to open the file location.</span></span> <span data-ttu-id="4b3ae-133">Laden Sie die Dateien auf Ihren Computer herunter, **oder wählen Sie "in"** oder " **Kopieren nach** " aus, um Sie in Ihr eigenes OneDrive oder in eine freigegebene Bibliothek zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-133">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="4b3ae-134">Sie können Dateien und Ordner gleichzeitig auf bis zu 500 MB kopieren.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-134">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="4b3ae-135">Wenn Sie Dokumente mit dem Versionsverlauf verschieben oder kopieren, wird nur die neueste Version verschoben.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-135">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="4b3ae-136">Widerrufen des Administratorzugriffs auf das OneDrive eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="4b3ae-136">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="4b3ae-137">Als globaler Administrator können Sie sich selbst Zugriff auf die Inhalte in der OneDrive eines Benutzers verschaffen, aber Sie möchten Ihren Zugriff möglicherweise entfernen, wenn Sie ihn nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-137">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4b3ae-138">Melden Sie sich beim <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a> als globaler Administrator oder SharePoint-Administrator an.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-138">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="4b3ae-139">Wenn Sie eine Nachricht erhalten, dass Sie keine Berechtigung für den Zugriff auf das Admin Center haben, verfügen Sie nicht über Administratorberechtigungen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-139">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4b3ae-140">Melden Sie sich beim <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> als globaler Administrator oder SharePoint-Administrator an.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-140">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="4b3ae-141">Wenn Sie eine Nachricht erhalten, dass Sie keine Berechtigung für den Zugriff auf das Admin Center haben, verfügen Sie nicht über Administratorberechtigungen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-141">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4b3ae-142">Melden Sie sich beim <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> als globaler Administrator oder SharePoint-Administrator an.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-142">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="4b3ae-143">Wenn Sie eine Nachricht erhalten, dass Sie keine Berechtigung für den Zugriff auf das Admin Center haben, verfügen Sie nicht über Administratorberechtigungen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-143">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="4b3ae-144">Wählen Sie im linken Bereich **Admin Center** \> **SharePoint**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-144">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="4b3ae-145">(Möglicherweise müssen Sie **Alle anzeigen** auswählen, um die Liste der Admin Center anzuzeigen.)</span><span class="sxs-lookup"><span data-stu-id="4b3ae-145">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="4b3ae-146">Wenn das klassische SharePoint Admin Center angezeigt wird, wählen Sie **Jetzt öffnen** am oberen Rand der Seite aus, um das neue SharePoint Admin Center zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-146">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

4. <span data-ttu-id="4b3ae-147">Wählen Sie im linken Bereich **Weitere Features**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-147">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="4b3ae-148">Wählen Sie unter **Benutzerprofile**die Option **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-148">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="4b3ae-149">Wählen Sie unter **Personen**die Option **Benutzerprofile verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-149">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="4b3ae-150">Geben Sie den Namen des Benutzers ein, und wählen Sie **Suchen**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-150">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="4b3ae-151">Klicken Sie mit der rechten Maustaste auf den Benutzer, und wählen Sie dann **Websitesammlungsbesitzer verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-151">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="4b3ae-152">Entfernen Sie die Person, die nicht mehr auf die Daten des Benutzers zugreifen muss, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-152">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="4b3ae-153">Zugreifen auf die Outlook-Daten eines ehemaligen Benutzers</span><span class="sxs-lookup"><span data-stu-id="4b3ae-153">Access the Outlook data of a former user</span></span>

<span data-ttu-id="4b3ae-154">Zum Speichern der E-Mail-Nachrichten, Kalender, Aufgaben und Kontakte des ehemaligen Mitarbeiters exportieren Sie die Informationen in eine Outlook-Datendatei (PST).</span><span class="sxs-lookup"><span data-stu-id="4b3ae-154">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="4b3ae-155">[Fügen Sie die e-Mail-Adresse des ehemaligen Mitarbeiters](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) zu Ihrem Outlook hinzu (wenn Sie [das Kennwort des Benutzers zurücksetzen](reset-passwords.md), können Sie es nur auf einen bestimmten Wert festlegen.)</span><span class="sxs-lookup"><span data-stu-id="4b3ae-155">[Add the former employee's email](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="4b3ae-156">Wählen Sie in Outlook **Datei**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-156">In Outlook, select **File**.</span></span>
    
    ![So sieht das Menüband in Outlook 2016 aus.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="4b3ae-158">Wählen Sie **Open &amp; Export** \> **Import/Export**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-158">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Befehl 'Importieren/Exportieren' in der Backstage-Ansicht](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="4b3ae-160">Wählen Sie **in eine Datei exportieren**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-160">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Option zum Exportieren in eine Datei im Import/Export-Assistenten](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="4b3ae-162">Wählen Sie **Outlook-Datendatei (PST)** aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-162">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="4b3ae-163">Wählen Sie das Konto aus, das Sie exportieren möchten, indem Sie den Namen oder die e-Mail-Adresse wie Postfach-Anne Weiler oder Anne@contoso.com auswählen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-163">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="4b3ae-164">Wenn Sie den gesamten Inhalt des Kontos exportieren möchten, einschließlich aller E-Mails, Kalender, Kontakte, Aufgaben und Notizen, stellen Sie sicher, dass das Kontrollkästchen **Unterordner einbeziehen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-164">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4b3ae-p109">Sie können immer ein Konto gleichzeitig exportieren. Wenn Sie mehrere Konten exportieren möchten, wiederholen Sie nach dem Export des einen Kontos diese Schritte.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-p109">You can export one account at a time. If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Dialogfeld 'Outlook-Datendatei exportieren' mit ausgewähltem Ordner der obersten Ebene und aktiviertem 'Unterordner einbeziehen'](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="4b3ae-168">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-168">Select **Next**.</span></span>
    
8. <span data-ttu-id="4b3ae-169">Wählen Sie **Durchsuchen** aus, um die Outlook-Datendatei (PST) zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-169">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="4b3ae-170">Geben Sie einen *Dateinamen*ein, und wählen Sie dann **OK** aus, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-170">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4b3ae-171">Wenn Sie zuvor bereits Daten exportiert haben, werden der Pfad und Dateiname des vorherigen Ordners angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-171">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="4b3ae-172">Geben Sie einen *anderen Dateinamen* ein, bevor Sie **OK**auswählen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-172">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="4b3ae-173">Wenn Sie in eine vorhandene Outlook-Datendatei (PST) exportieren möchten, geben Sie unter **Optionen** an, was beim Export von Elementen geschehen soll, die in der Datei bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-173">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="4b3ae-174">Wählen Sie **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-174">Select **Finish**.</span></span>
    
<span data-ttu-id="4b3ae-175">Outlook beginnt den Exportvorgang sofort, es sei denn, es wird eine neue Outlook-Datendatei (PST) erstellt oder eine kennwortgeschützte Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-175">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="4b3ae-176">Wenn Sie eine Outlook-Datendatei (PST) erstellen, können Sie diese optional mit einem Kennwort schützen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-176">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="4b3ae-177">Wenn das Dialogfeld **Outlook-Datendatei erstellen** angezeigt wird, geben Sie das *Kennwort* in die Felder **Kennwort** und **Kennwort bestätigen** ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-177">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="4b3ae-178">Geben Sie im Dialogfeld **Kennwort für Outlook-Datendatei** das *Kennwort*ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-178">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="4b3ae-179">Wenn Sie in eine vorhandene Outlook-Datendatei (PST) exportieren, die kennwortgeschützt ist, geben Sie im Dialogfeld **Kennwort für Outlook-Datendatei** das *Kennwort*ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-179">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="4b3ae-180">Weitere Informationen finden Sie unter [exportieren oder Sichern von e-Mails, Kontakten und Kalendern in eine Outlook. PST-Datei](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-180">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="4b3ae-181">Standardmäßig ist Ihre e-Mail für einen Zeitraum von 12 Monaten offline verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-181">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="4b3ae-182">Weitere Informationen finden Sie unter Vorgehensweise zum [verbessern der offline verfügbaren Daten](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span><span class="sxs-lookup"><span data-stu-id="4b3ae-182">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="4b3ae-183">Gewähren eines anderen Benutzers auf die e-Mail-Adresse eines ehemaligen Benutzers</span><span class="sxs-lookup"><span data-stu-id="4b3ae-183">Give another user access to a former user's email</span></span> 

<span data-ttu-id="4b3ae-184">Um den Zugriff auf e-Mail-Nachrichten, Kalender, Aufgaben und Kontakte des ehemaligen Mitarbeiters an einen anderen Mitarbeiter zu ermöglichen, importieren Sie die Informationen in den Outlook-Posteingang eines anderen Mitarbeiters.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-184">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="4b3ae-185">Sie können auch [das Postfach des früheren Benutzers in ein freigegebenes Postfach konvertieren](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) oder die [e-Mail-Adresse eines ehemaligen Mitarbeiters an einen anderen Mitarbeiter weiterleiten](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="4b3ae-185">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="4b3ae-186">Wechseln Sie in Outlook zu **Datei** \> **Open &amp; Export** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-186">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="4b3ae-187">Hiermit wird der Import/Export-Assistent geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-187">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="4b3ae-188">Wählen Sie **aus einem anderen Programm oder einer anderen Datei importieren aus**, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-188">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Import/Export-Assistent](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="4b3ae-190">Wählen Sie **Outlook-Datendatei (PST)** aus, und wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-190">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="4b3ae-191">Navigieren Sie zu der PST-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-191">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="4b3ae-192">Wählen Sie unter **Optionen** aus, wie Duplikate behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-192">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="4b3ae-193">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-193">Select **Next**.</span></span>
    
7. <span data-ttu-id="4b3ae-194">Wenn der Outlook-Datendatei (PST) ein Kennwort zugewiesen wurde, geben Sie das Kennwort ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-194">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="4b3ae-195">Legen Sie die Optionen für den Import von Elementen fest.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-195">Set the options for importing items.</span></span> <span data-ttu-id="4b3ae-196">Im Normalfall müssen die Standardeinstellungen nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-196">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="4b3ae-197">Wählen Sie **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-197">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="4b3ae-198">Die Schritte bleiben für den Zugriff auf OneDrive-und e-Mail-Daten eines vorhandenen Benutzers unverändert.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-198">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="4b3ae-199">Wenn Sie nur einige Elemente aus einer Outlook-Datendatei (PST) importieren oder wiederherstellen möchten, können Sie die Outlook-Datendatei öffnen.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-199">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="4b3ae-200">Ziehen Sie dann im Navigationsbereich die Elemente aus den Outlook-Datendatei Ordnern in Ihre vorhandenen Outlook-Ordner.</span><span class="sxs-lookup"><span data-stu-id="4b3ae-200">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="4b3ae-201">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="4b3ae-201">Related articles</span></span>
[<span data-ttu-id="4b3ae-202">Entfernen eines ehemaligen Mitarbeiters aus Office 365</span><span class="sxs-lookup"><span data-stu-id="4b3ae-202">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="4b3ae-203">Hinzufügen und Entfernen von Administratoren für ein OneDrive-Konto</span><span class="sxs-lookup"><span data-stu-id="4b3ae-203">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="4b3ae-204">Wiederherstellen eines gelöschten OneDrive</span><span class="sxs-lookup"><span data-stu-id="4b3ae-204">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="4b3ae-205">OneDrive-Aufbewahrung und-Löschung</span><span class="sxs-lookup"><span data-stu-id="4b3ae-205">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
