---
title: Verwalten von Personen, die Office 365-Gruppen erstellen können
f1.keywords:
- NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Erfahren Sie, wie Sie steuern können, welche Benutzer Office 365-Gruppen erstellen können.
ms.openlocfilehash: a211cb3b69348a4d4a401a3c318fe019d8fd257f
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277192"
---
# <a name="manage-who-can-create-office-365-groups"></a><span data-ttu-id="92da0-103">Verwalten von Personen, die Office 365-Gruppen erstellen können</span><span class="sxs-lookup"><span data-stu-id="92da0-103">Manage who can create Office 365 Groups</span></span>

  
<span data-ttu-id="92da0-104">Weil es für Benutzer so einfach ist, Office 365-Gruppen selbst zu erstellen, werden Sie vermutlich nicht mit Bitten überflutet, diese Gruppen im Auftrag anderer Personen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92da0-104">Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="92da0-105">Je nach Ihrem Unternehmen möchten Sie jedoch steuern, welche Personen die Möglichkeit zum Erstellen von Gruppen haben sollen.</span><span class="sxs-lookup"><span data-stu-id="92da0-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="92da0-106">In diesem Artikel wird erläutert, wie Sie die Möglichkeit zum Erstellen von Gruppen **in allen Office 365-Diensten, die Gruppen verwenden,** deaktivieren können:</span><span class="sxs-lookup"><span data-stu-id="92da0-106">This article explains how to disable the ability to create groups **in all Office 365 services that use groups**:</span></span> 
  
- <span data-ttu-id="92da0-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="92da0-107">Outlook</span></span>
    
- <span data-ttu-id="92da0-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="92da0-108">SharePoint</span></span>
    
- <span data-ttu-id="92da0-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="92da0-109">Yammer</span></span>
    
- <span data-ttu-id="92da0-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92da0-110">Microsoft Teams</span></span>

- <span data-ttu-id="92da0-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="92da0-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="92da0-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="92da0-112">StaffHub</span></span>
    
- <span data-ttu-id="92da0-113">Planner</span><span class="sxs-lookup"><span data-stu-id="92da0-113">Planner</span></span>
    
- <span data-ttu-id="92da0-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="92da0-114">PowerBI</span></span>

- <span data-ttu-id="92da0-115">Roadmap</span><span class="sxs-lookup"><span data-stu-id="92da0-115">Roadmap</span></span>
    
<span data-ttu-id="92da0-116">Sie können die Erstellung von Office 365-Gruppen auf die Mitglieder einer bestimmten Sicherheitsgruppe beschränken.</span><span class="sxs-lookup"><span data-stu-id="92da0-116">You can restrict Office 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="92da0-117">Um dies zu konfigurieren, verwenden Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92da0-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="92da0-118">Dieser Artikel führt Sie durch die erforderlichen Schritte.</span><span class="sxs-lookup"><span data-stu-id="92da0-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="92da0-119">Durch die in diesem Artikel beschriebenen Schritte wird nicht verhindert, dass Mitglieder mit bestimmten Rollen Gruppen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="92da0-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="92da0-120">Globale Office 365-Administratoren können über beliebige Instrumente Gruppen erstellen, z. B. über das Microsoft 365 Admin Center, Planner, Microsoft Teams, Exchange und SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="92da0-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="92da0-121">Benutzer mit anderen Rollen können Gruppen über begrenzte Instrumente erstellen, die nachstehend aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="92da0-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="92da0-122">Exchange-Administrator: Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="92da0-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="92da0-123">Partnersupport der Ebene 1: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="92da0-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="92da0-124">Partnersupport der Ebene 2: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="92da0-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="92da0-125">Verzeichnisautoren: Azure AD</span><span class="sxs-lookup"><span data-stu-id="92da0-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="92da0-126">SharePoint-Administrator: SharePoint Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="92da0-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="92da0-127">Microsoft Teams-Dienstadministrator: Microsoft Teams Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="92da0-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="92da0-128">Benutzerverwaltungsadministrator: Microsoft 365 Admin Center, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="92da0-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="92da0-129">Wenn Sie Mitglied einer dieser Rollen sind, können Sie Office 365-Gruppen für Benutzer mit eingeschränktem Zugriff erstellen und anschließend den Benutzer als Besitzer der Gruppe zuweisen.</span><span class="sxs-lookup"><span data-stu-id="92da0-129">If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="92da0-130">Benutzer mit dieser Rolle können in Yammer verbundene Gruppen erstellen, und zwar unabhängig von PowerShell-Einstellungen, die eine Erstellung verhindern sollten.</span><span class="sxs-lookup"><span data-stu-id="92da0-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="92da0-131">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="92da0-131">Licensing requirements</span></span>

<span data-ttu-id="92da0-132">Um verwalten zu können, wer Gruppen erstellt, benötigen die folgenden Personen ihnen zugewiesene Azure AD Premium-Lizenzen oder Azure AD Basic EDU-Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="92da0-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="92da0-133">Der Administrator, der die Einstellungen für die Gruppenerstellung konfiguriert</span><span class="sxs-lookup"><span data-stu-id="92da0-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="92da0-134">Die Mitglieder der Sicherheitsgruppe, die Gruppen erstellen dürfen</span><span class="sxs-lookup"><span data-stu-id="92da0-134">The members of the security group who are allowed to create Groups</span></span>

<span data-ttu-id="92da0-135">Die folgenden Personen benötigen keine ihnen zugewiesene Azure AD Premium-Lizenzen oder Azure AD Basic EDU-Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="92da0-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="92da0-136">Personen, die Mitglieder von Office 365-Gruppen sind und keine Möglichkeit haben, andere Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92da0-136">People who are members of Office 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a><span data-ttu-id="92da0-137">Schritt 1: Erstellen einer Sicherheitsgruppe für Benutzer, die Office 365-Gruppen erstellen müssen</span><span class="sxs-lookup"><span data-stu-id="92da0-137">Step 1: Create a security group for users who need to create Office 365 Groups</span></span>

<span data-ttu-id="92da0-138">Zum Steuern des Personenkreises, der Gruppen erstellen kann, kann in Ihrer Organisation nur eine Sicherheitsgruppe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="92da0-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="92da0-139">Sie können jedoch andere Sicherheitsgruppen als Mitglieder dieser Gruppe schachteln.</span><span class="sxs-lookup"><span data-stu-id="92da0-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="92da0-140">Beispiel: Die Gruppe namens "Gruppenerstellung zulassen" ist die designierte Sicherheitsgruppe, und die Gruppen namens "Microsoft Planner-Benutzer" und "Exchange Online-Benutzer" sind Mitglieder dieser Gruppe.</span><span class="sxs-lookup"><span data-stu-id="92da0-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="92da0-141">Administratoren mit den oben aufgeführten Rollen müssen nicht Mitglieder dieser Gruppe sein: Sie behalten ihre Fähigkeit, Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92da0-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92da0-142">Achten Sie darauf, mithilfe einer **Sicherheitsgruppe** einzuschränken, wer Gruppen erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="92da0-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="92da0-143">Dann können Mitglieder nämlich keine Gruppe auf SharePoint erstellen, weil dort auf eine Sicherheitsgruppe überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="92da0-143">If you try to use an Office 365 Group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="92da0-144">Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.</span><span class="sxs-lookup"><span data-stu-id="92da0-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="92da0-145">Klicken Sie auf **Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="92da0-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="92da0-146">Wählen Sie als Gruppentyp die Option **Sicherheit** aus.</span><span class="sxs-lookup"><span data-stu-id="92da0-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="92da0-147">Vergessen Sie nicht den Namen der Gruppe!</span><span class="sxs-lookup"><span data-stu-id="92da0-147">Remember the name of the group!</span></span> <span data-ttu-id="92da0-148">Sie benötigen ihn später noch.</span><span class="sxs-lookup"><span data-stu-id="92da0-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="92da0-149">Schließen Sie die Einrichtung der Sicherheitsgruppe ab, indem Sie Personen oder andere Sicherheitsgruppen hinzufügen, denen Sie in Ihrer Organisation das Erstellen von Gruppen erlauben möchten.</span><span class="sxs-lookup"><span data-stu-id="92da0-149">Finish setting up the security group, adding people or other security groups who you want to be able to create Groups in your org.</span></span>
    
<span data-ttu-id="92da0-150">Ausführliche Anleitungen finden Sie unter [Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center](../email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="92da0-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
  
## <a name="step-2-install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="92da0-151">Schritt 2: Installieren der Vorschauversion von Azure Active Directory PowerShell für Graph</span><span class="sxs-lookup"><span data-stu-id="92da0-151">Step 2: Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

<span data-ttu-id="92da0-152">Diese Verfahren erfordern die Vorschauversion von Azure Active Directory PowerShell für Graph.</span><span class="sxs-lookup"><span data-stu-id="92da0-152">These procedures require the preview version of the Azure Active Directory PowerShell for Graph.</span></span> <span data-ttu-id="92da0-153">Die GA-Version funktioniert dann nicht.</span><span class="sxs-lookup"><span data-stu-id="92da0-153">The GA version will not work.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="92da0-154">Sie können die Preview- und die GA-Version nicht gleichzeitig auf demselben Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="92da0-154">You cannot install both the preview and GA versions on the same computer at the same time.</span></span> <span data-ttu-id="92da0-155">Sie können das Modul unter Windows 10, Windows Server 2016 installieren.</span><span class="sxs-lookup"><span data-stu-id="92da0-155">You can install the module on Windows 10, Windows Server 2016.</span></span>

  
<span data-ttu-id="92da0-156">Als bewährte Methode empfehlen wir, *immer* die neueste Version zu verwenden: Deinstallieren Sie die alte AzureADPreview- bzw. AzureAD-Version, und holen Sie sich die aktuellste Version.</span><span class="sxs-lookup"><span data-stu-id="92da0-156">As a best practice, we recommend  *always*  staying current: uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
1. <span data-ttu-id="92da0-157">Geben Sie in der Suchleiste "Windows PowerShell" ein.</span><span class="sxs-lookup"><span data-stu-id="92da0-157">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="92da0-158">Klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="92da0-158">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
    
    ![Öffnen Sie PowerShell mit „Als Administrator ausführen“.](../media/52517af8-c7b0-4c8f-b2f3-0f82f9d5ace1.png)
    
3. <span data-ttu-id="92da0-160">Setzen Sie die Richtlinie mithilfe der [Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)auf RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="92da0-160">Set the policy to RemoteSigned by using [Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).</span></span>
    
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
  
4. <span data-ttu-id="92da0-161">Überprüfen Sie das installierte Modul:</span><span class="sxs-lookup"><span data-stu-id="92da0-161">Check installed module:</span></span>
    
    ```
    Get-InstalledModule -Name "AzureAD*"
    ```

5. <span data-ttu-id="92da0-162">Führen Sie zum Deinstallieren einer früheren Version von AzureADPreview oder AzureAD diesen Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="92da0-162">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
    ```
    Uninstall-Module AzureADPreview
    ```

    <span data-ttu-id="92da0-163">oder</span><span class="sxs-lookup"><span data-stu-id="92da0-163">or</span></span>
  
    ```
    Uninstall-Module AzureAD
    ```

6. <span data-ttu-id="92da0-164">Führen Sie zum Installieren der aktuellsten Version von AzureADPreview diesen Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="92da0-164">To install the latest version of AzureADPreview, run this command:</span></span>
  
    ```
    Install-Module AzureADPreview
    ```

    <span data-ttu-id="92da0-165">Geben Sie in der Nachricht über ein nicht vertrauenswürdiges Repository **J** ein. Die Installation des neuen Moduls dauert etwa eine Minute.</span><span class="sxs-lookup"><span data-stu-id="92da0-165">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>

<span data-ttu-id="92da0-166">Lassen Sie das PowerShell-Fenster für Schritt 3 (nachstehend) geöffnet.</span><span class="sxs-lookup"><span data-stu-id="92da0-166">Leave the PowerShell window open for Step 3, below.</span></span>
  
## <a name="step-3-run-powershell-commands"></a><span data-ttu-id="92da0-167">Schritt 3: Ausführen von PowerShell-Befehlen</span><span class="sxs-lookup"><span data-stu-id="92da0-167">Step 3: Run PowerShell commands</span></span>

<span data-ttu-id="92da0-168">Kopieren Sie das folgende Skript in einen Text-Editor wie Editor oder [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="92da0-168">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="92da0-169">Ersetzen Sie *\<SecurityGroupName\>* durch den Namen der Sicherheitsgruppe, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="92da0-169">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="92da0-170">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="92da0-170">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="92da0-171">Speichern Sie die Datei als "GroupCreators.ps1".</span><span class="sxs-lookup"><span data-stu-id="92da0-171">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="92da0-172">Gehen Sie im PowerShell-Fenster zu dem Speicherort, an dem Sie die Datei gespeichert haben (geben Sie "CD <FileLocation>" ein).</span><span class="sxs-lookup"><span data-stu-id="92da0-172">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="92da0-173">Führen Sie das Skript aus, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="92da0-173">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="92da0-174">und [melden sich bei der entsprechenden Aufforderung mit Ihrem Administratorkonto an](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription).</span><span class="sxs-lookup"><span data-stu-id="92da0-174">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="92da0-175">Die letzte Zeile des Skripts enthält die aktualisierten Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="92da0-175">The last line of the script will display the updated settings:</span></span>

![So sehen Ihre Einstellungen aus, wenn Sie fertig sind.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="92da0-177">Wenn Sie später die verwendete Sicherheitsgruppe ändern möchten, können Sie das Skript mit dem Namen der neuen Sicherheitsgruppe erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="92da0-177">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="92da0-178">Wenn Sie die Einschränkung für die Gruppenerstellung deaktivieren und wieder allen Benutzern das Erstellen von Gruppen gestatten möchten, legen Sie $GroupName auf "" und $AllowGroupCreation auf "True" fest, und führen Sie das Skript erneut aus.</span><span class="sxs-lookup"><span data-stu-id="92da0-178">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="92da0-179">Schritt 4: Überprüfen, ob alles ordnungsgemäß funktioniert</span><span class="sxs-lookup"><span data-stu-id="92da0-179">Step 4: Verify that it works</span></span>

1. <span data-ttu-id="92da0-180">Melden Sie sich bei Office 365 mit dem Benutzerkonto einer Person an, der es NICHT möglich sein sollte, Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92da0-180">Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="92da0-181">Also einer Person, die nicht Mitglied der von Ihnen erstellten Sicherheitsgruppe oder ein Administrator ist.</span><span class="sxs-lookup"><span data-stu-id="92da0-181">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="92da0-182">Wählen Sie die Kachel **Planner** aus.</span><span class="sxs-lookup"><span data-stu-id="92da0-182">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="92da0-183">Wählen Sie in Planner in der linken Navigationsleiste **Neuer Plan** aus, um einen Plan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92da0-183">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="92da0-184">Jetzt sollte eine Nachricht angezeigt werden, die besagt, dass die Erstellung von Plänen und Gruppen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="92da0-184">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="92da0-185">Wiederholen Sie den Vorgang mit einem Mitglied der Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="92da0-185">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="92da0-186">Sollte es Mitgliedern der Sicherheitsgruppe nicht möglich sein, Gruppen zu erstellen, überprüfen Sie, ob Sie nicht durch ihre [OWA-Postfachrichtlinie](https://go.microsoft.com/fwlink/?linkid=852135) daran gehindert werden.</span><span class="sxs-lookup"><span data-stu-id="92da0-186">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="92da0-187">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="92da0-187">Related articles</span></span>

[<span data-ttu-id="92da0-188">Erste Schritte mit Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="92da0-188">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="92da0-189">Einrichten der Self-Service-Gruppenverwaltung in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="92da0-189">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="92da0-190">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="92da0-190">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="92da0-191">Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen</span><span class="sxs-lookup"><span data-stu-id="92da0-191">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
