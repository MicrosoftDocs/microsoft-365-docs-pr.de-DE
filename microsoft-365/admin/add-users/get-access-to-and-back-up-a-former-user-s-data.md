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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: Hier erfahren Sie, wie Sie die Dateien und e-Mails eines Mitarbeiters beibehalten, wenn die Person Ihre Organisation verlässt.
ms.openlocfilehash: 2b608b51060e746d0b69fd887882b51735578496
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43105759"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="9ab65-103">Zugreifen auf die und Sichern der Daten eines ehemaligen Mitarbeiters</span><span class="sxs-lookup"><span data-stu-id="9ab65-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="9ab65-104">Wenn ein Mitarbeiter Ihre Organisation verlässt, möchten Sie wahrscheinlich auf Ihre Daten (Dokumente und e-Mails) zugreifen und diese entweder überprüfen, sichern oder an einen neuen Mitarbeiter weitergeben.</span><span class="sxs-lookup"><span data-stu-id="9ab65-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="9ab65-105">Zugreifen auf OneDrive-Dokumente eines früheren Benutzers</span><span class="sxs-lookup"><span data-stu-id="9ab65-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="9ab65-106">Wenn Sie die Lizenz eines Benutzers entfernen, aber das Konto nicht löschen, können Sie sich selbst Zugriff auf die Inhalte im OneDrive des Benutzers verschaffen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="9ab65-107">Wenn Sie das Konto des Benutzers löschen, haben Sie standardmäßig 30 Tage Zeit, um auf die OneDrive-Daten des früheren Benutzers zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-107">If you delete the user's account, you have 30 days by default to access the former user’s OneDrive data.</span></span> <span data-ttu-id="9ab65-108">[Hier erfahren Sie, wie Sie die OneDrive-Aufbewahrung für gelöschte Benutzer festlegen](/onedrive/set-retention).</span><span class="sxs-lookup"><span data-stu-id="9ab65-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="9ab65-109">Wenn Sie innerhalb dieses Zeitraums kein [Benutzerkonto wiederherstellen](/office365/admin/add-users/restore-user) , wird der OneDrive-Inhalt gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9ab65-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="9ab65-110">Um die OneDrive-Dateien eines früheren Benutzers beizubehalten, geben Sie sich zunächst Zugriff auf Ihre OneDrive, und legen Sie dann die Dateien, die Sie behalten möchten, fest.</span><span class="sxs-lookup"><span data-stu-id="9ab65-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="9ab65-111">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-111">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="9ab65-112">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="9ab65-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="9ab65-113">Wählen Sie einen Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-113">Select a user.</span></span>

3. <span data-ttu-id="9ab65-114">Wählen Sie im rechten Bereich **OneDrive**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-114">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="9ab65-115">Wählen Sie unter **Zugriff auf Dateien abrufen die**Option **Link zu Dateien erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-115">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="9ab65-116">Wählen Sie den Link aus, um den Dateispeicherort zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-116">Select the link to open the file location.</span></span> <span data-ttu-id="9ab65-117">Laden Sie die Dateien auf Ihren Computer herunter, **oder wählen Sie "in"** oder " **Kopieren nach** " aus, um Sie in Ihr eigenes OneDrive oder in eine freigegebene Bibliothek zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="9ab65-117">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="9ab65-118">Sie können Dateien und Ordner gleichzeitig auf bis zu 500 MB kopieren.</span><span class="sxs-lookup"><span data-stu-id="9ab65-118">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="9ab65-119">Wenn Sie Dokumente mit dem Versionsverlauf verschieben oder kopieren, wird nur die neueste Version verschoben.</span><span class="sxs-lookup"><span data-stu-id="9ab65-119">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9ab65-120">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="9ab65-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="9ab65-121">Wählen Sie einen Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-121">Select a user.</span></span>

3. <span data-ttu-id="9ab65-122">Erweitern Sie im rechten Bereich **OneDrive-Einstellungen**, und wählen Sie dann neben **Zugriff**die Option **Access Files**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-122">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="9ab65-123">Wählen Sie den Link aus, um den Dateispeicherort zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-123">Select the link to open the file location.</span></span> <span data-ttu-id="9ab65-124">Laden Sie die Dateien auf Ihren Computer herunter, **oder wählen Sie "in"** oder " **Kopieren nach** " aus, um Sie in Ihr eigenes OneDrive oder in eine freigegebene Bibliothek zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="9ab65-124">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="9ab65-125">Sie können Dateien und Ordner gleichzeitig auf bis zu 500 MB kopieren.</span><span class="sxs-lookup"><span data-stu-id="9ab65-125">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="9ab65-126">Wenn Sie Dokumente mit dem Versionsverlauf verschieben oder kopieren, wird nur die neueste Version verschoben.</span><span class="sxs-lookup"><span data-stu-id="9ab65-126">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9ab65-127">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="9ab65-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="9ab65-128">Wählen Sie einen Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-128">Select a user.</span></span>

3. <span data-ttu-id="9ab65-129">Erweitern Sie im rechten Bereich **OneDrive-Einstellungen**, und wählen Sie dann neben **Zugriff**die Option **Access Files**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-129">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="9ab65-130">Wählen Sie den Link aus, um den Dateispeicherort zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-130">Select the link to open the file location.</span></span> <span data-ttu-id="9ab65-131">Laden Sie die Dateien auf Ihren Computer herunter, **oder wählen Sie "in"** oder " **Kopieren nach** " aus, um Sie in Ihr eigenes OneDrive oder in eine freigegebene Bibliothek zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="9ab65-131">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="9ab65-132">Sie können Dateien und Ordner gleichzeitig auf bis zu 500 MB kopieren.</span><span class="sxs-lookup"><span data-stu-id="9ab65-132">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="9ab65-133">Wenn Sie Dokumente mit dem Versionsverlauf verschieben oder kopieren, wird nur die neueste Version verschoben.</span><span class="sxs-lookup"><span data-stu-id="9ab65-133">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="9ab65-134">Widerrufen des Administratorzugriffs auf das OneDrive eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="9ab65-134">Revoke admin access to a user’s OneDrive</span></span>

<span data-ttu-id="9ab65-135">Als globaler Administrator können Sie sich selbst Zugriff auf die Inhalte in der OneDrive eines Benutzers verschaffen, aber Sie möchten Ihren Zugriff möglicherweise entfernen, wenn Sie ihn nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-135">As global admin, you can give yourself access to the content in a user’s OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9ab65-136">Melden Sie sich beim <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a> als globaler Administrator oder SharePoint-Administrator an.</span><span class="sxs-lookup"><span data-stu-id="9ab65-136">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="9ab65-137">Wenn Sie eine Nachricht erhalten, dass Sie keine Berechtigung für den Zugriff auf das Admin Center haben, verfügen Sie nicht über Administratorberechtigungen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9ab65-137">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9ab65-138">Melden Sie sich beim <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> als globaler Administrator oder SharePoint-Administrator an.</span><span class="sxs-lookup"><span data-stu-id="9ab65-138">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="9ab65-139">Wenn Sie eine Nachricht erhalten, dass Sie keine Berechtigung für den Zugriff auf das Admin Center haben, verfügen Sie nicht über Administratorberechtigungen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9ab65-139">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9ab65-140">Melden Sie sich beim <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> als globaler Administrator oder SharePoint-Administrator an.</span><span class="sxs-lookup"><span data-stu-id="9ab65-140">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="9ab65-141">Wenn Sie eine Nachricht erhalten, dass Sie keine Berechtigung für den Zugriff auf das Admin Center haben, verfügen Sie nicht über Administratorberechtigungen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9ab65-141">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="9ab65-142">Wählen Sie im linken Bereich **Admin Center** \> **SharePoint**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-142">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="9ab65-143">(Möglicherweise müssen Sie **Alle anzeigen** auswählen, um die Liste der Admin Center anzuzeigen.)</span><span class="sxs-lookup"><span data-stu-id="9ab65-143">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="9ab65-144">Wenn das klassische SharePoint Admin Center angezeigt wird, wählen Sie **Jetzt öffnen** am oberen Rand der Seite aus, um das neue SharePoint Admin Center zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-144">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

4. <span data-ttu-id="9ab65-145">Wählen Sie im linken Bereich **Weitere Features**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-145">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="9ab65-146">Wählen Sie unter **Benutzerprofile**die Option **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-146">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="9ab65-147">Wählen Sie unter **Personen**die Option **Benutzerprofile verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-147">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="9ab65-148">Geben Sie den Namen des Benutzers ein, und wählen Sie **Suchen**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-148">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="9ab65-149">Klicken Sie mit der rechten Maustaste auf den Benutzer, und wählen Sie dann **Websitesammlungsbesitzer verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-149">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="9ab65-150">Entfernen Sie die Person, die nicht mehr auf die Daten des Benutzers zugreifen muss, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-150">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="9ab65-151">Zugreifen auf die Outlook-Daten eines ehemaligen Benutzers</span><span class="sxs-lookup"><span data-stu-id="9ab65-151">Access the Outlook data of a former user</span></span>

<span data-ttu-id="9ab65-152">Zum Speichern der E-Mail-Nachrichten, Kalender, Aufgaben und Kontakte des ehemaligen Mitarbeiters exportieren Sie die Informationen in eine Outlook-Datendatei (PST).</span><span class="sxs-lookup"><span data-stu-id="9ab65-152">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="9ab65-153">[Fügen Sie die e-Mail-Adresse des ehemaligen Mitarbeiters](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) zu Ihrem Outlook hinzu (wenn Sie [das Kennwort des Benutzers zurücksetzen](reset-passwords.md), können Sie es nur auf einen bestimmten Wert festlegen.)</span><span class="sxs-lookup"><span data-stu-id="9ab65-153">[Add the former employee's email](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="9ab65-154">Wählen Sie in Outlook **Datei**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-154">In Outlook, select **File**.</span></span>
    
    ![So sieht das Menüband in Outlook 2016 aus.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="9ab65-156">Wählen **Sie &amp; Open Export** \> **Import/Export**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-156">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Befehl 'Importieren/Exportieren' in der Backstage-Ansicht](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="9ab65-158">Wählen Sie **in eine Datei exportieren**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-158">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Option zum Exportieren in eine Datei im Import/Export-Assistenten](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="9ab65-160">Wählen Sie **Outlook-Datendatei (PST)** aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-160">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="9ab65-161">Wählen Sie das Konto aus, das Sie exportieren möchten, indem Sie den Namen oder die e-Mail-Adresse wie Postfach-Anne Weiler oder Anne@contoso.com auswählen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-161">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="9ab65-162">Wenn Sie den gesamten Inhalt des Kontos exportieren möchten, einschließlich aller E-Mails, Kalender, Kontakte, Aufgaben und Notizen, stellen Sie sicher, dass das Kontrollkästchen **Unterordner einbeziehen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9ab65-162">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9ab65-p108">Sie können immer ein Konto gleichzeitig exportieren. Wenn Sie mehrere Konten exportieren möchten, wiederholen Sie nach dem Export des einen Kontos diese Schritte.</span><span class="sxs-lookup"><span data-stu-id="9ab65-p108">You can export one account at a time. If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Dialogfeld 'Outlook-Datendatei exportieren' mit ausgewähltem Ordner der obersten Ebene und aktiviertem 'Unterordner einbeziehen'](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="9ab65-166">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-166">Select **Next**.</span></span>
    
8. <span data-ttu-id="9ab65-167">Wählen Sie **Durchsuchen** aus, um die Outlook-Datendatei (PST) zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9ab65-167">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="9ab65-168">Geben Sie einen *Dateinamen*ein, und wählen Sie dann **OK** aus, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-168">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9ab65-169">Wenn Sie zuvor bereits Daten exportiert haben, werden der Pfad und Dateiname des vorherigen Ordners angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ab65-169">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="9ab65-170">Geben Sie einen *anderen Dateinamen* ein, bevor Sie **OK**auswählen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-170">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="9ab65-171">Wenn Sie in eine vorhandene Outlook-Datendatei (PST) exportieren möchten, geben Sie unter **Optionen** an, was beim Export von Elementen geschehen soll, die in der Datei bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="9ab65-171">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="9ab65-172">Wählen Sie **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-172">Select **Finish**.</span></span>
    
<span data-ttu-id="9ab65-173">Outlook beginnt den Exportvorgang sofort, es sei denn, es wird eine neue Outlook-Datendatei (PST) erstellt oder eine kennwortgeschützte Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ab65-173">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="9ab65-174">Wenn Sie eine Outlook-Datendatei (PST) erstellen, können Sie diese optional mit einem Kennwort schützen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-174">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="9ab65-175">Wenn das Dialogfeld **Outlook-Datendatei erstellen** angezeigt wird, geben Sie das *Kennwort* in die Felder **Kennwort** und **Kennwort bestätigen** ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-175">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="9ab65-176">Geben Sie im Dialogfeld **Kennwort für Outlook-Datendatei** das *Kennwort*ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-176">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="9ab65-177">Wenn Sie in eine vorhandene Outlook-Datendatei (PST) exportieren, die kennwortgeschützt ist, geben Sie im Dialogfeld **Kennwort für Outlook-Datendatei** das *Kennwort*ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-177">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="9ab65-178">Weitere Informationen finden Sie unter [exportieren oder Sichern von e-Mails, Kontakten und Kalendern in eine Outlook. PST-Datei](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="9ab65-178">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="9ab65-179">Standardmäßig ist Ihre e-Mail für einen Zeitraum von 12 Monaten offline verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9ab65-179">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="9ab65-180">Weitere Informationen finden Sie unter Vorgehensweise zum [verbessern der offline verfügbaren Daten](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span><span class="sxs-lookup"><span data-stu-id="9ab65-180">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="9ab65-181">Gewähren eines anderen Benutzers auf die e-Mail-Adresse eines ehemaligen Benutzers</span><span class="sxs-lookup"><span data-stu-id="9ab65-181">Give another user access to a former user's email</span></span> 

<span data-ttu-id="9ab65-182">Um den Zugriff auf e-Mail-Nachrichten, Kalender, Aufgaben und Kontakte des ehemaligen Mitarbeiters an einen anderen Mitarbeiter zu ermöglichen, importieren Sie die Informationen in den Outlook-Posteingang eines anderen Mitarbeiters.</span><span class="sxs-lookup"><span data-stu-id="9ab65-182">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="9ab65-183">Sie können auch [das Postfach des früheren Benutzers in ein freigegebenes Postfach konvertieren](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) oder die [e-Mail-Adresse eines ehemaligen Mitarbeiters an einen anderen Mitarbeiter weiterleiten](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="9ab65-183">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="9ab65-184">Wechseln Sie in Outlook zu **Datei** \> **Open &amp; Export** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="9ab65-184">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="9ab65-185">Hiermit wird der Import/Export-Assistent geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9ab65-185">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="9ab65-186">Wählen Sie **aus einem anderen Programm oder einer anderen Datei importieren aus**, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-186">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Import/Export-Assistent](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="9ab65-188">Wählen Sie **Outlook-Datendatei (PST)** aus, und wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-188">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="9ab65-189">Navigieren Sie zu der PST-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9ab65-189">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="9ab65-190">Wählen Sie unter **Optionen** aus, wie Duplikate behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-190">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="9ab65-191">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-191">Select **Next**.</span></span>
    
7. <span data-ttu-id="9ab65-192">Wenn der Outlook-Datendatei (PST) ein Kennwort zugewiesen wurde, geben Sie das Kennwort ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-192">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="9ab65-193">Legen Sie die Optionen für den Import von Elementen fest.</span><span class="sxs-lookup"><span data-stu-id="9ab65-193">Set the options for importing items.</span></span> <span data-ttu-id="9ab65-194">Im Normalfall müssen die Standardeinstellungen nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9ab65-194">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="9ab65-195">Wählen Sie **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="9ab65-195">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="9ab65-196">Die Schritte bleiben für den Zugriff auf OneDrive-und e-Mail-Daten eines vorhandenen Benutzers unverändert.</span><span class="sxs-lookup"><span data-stu-id="9ab65-196">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="9ab65-197">Wenn Sie nur einige Elemente aus einer Outlook-Datendatei (PST) importieren oder wiederherstellen möchten, können Sie die Outlook-Datendatei öffnen.</span><span class="sxs-lookup"><span data-stu-id="9ab65-197">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="9ab65-198">Ziehen Sie dann im Navigationsbereich die Elemente aus den Outlook-Datendatei Ordnern in Ihre vorhandenen Outlook-Ordner.</span><span class="sxs-lookup"><span data-stu-id="9ab65-198">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="9ab65-199">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="9ab65-199">Related articles</span></span>
[<span data-ttu-id="9ab65-200">Entfernen eines ehemaligen Mitarbeiters aus Office 365</span><span class="sxs-lookup"><span data-stu-id="9ab65-200">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="9ab65-201">Hinzufügen und Entfernen von Administratoren für ein OneDrive-Konto</span><span class="sxs-lookup"><span data-stu-id="9ab65-201">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="9ab65-202">Wiederherstellen eines gelöschten OneDrive</span><span class="sxs-lookup"><span data-stu-id="9ab65-202">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="9ab65-203">OneDrive-Aufbewahrung und-Löschung</span><span class="sxs-lookup"><span data-stu-id="9ab65-203">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
