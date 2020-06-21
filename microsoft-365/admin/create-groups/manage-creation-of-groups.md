---
title: Verwalten von Personen, die Gruppen erstellen können
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Erfahren Sie, wie Sie steuern, welche Benutzer Microsoft 365-Gruppen erstellen können.
ms.openlocfilehash: b64e7ac96c5a0e38583d00f8a61bd47c5304cf45
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761674"
---
# <a name="manage-who-can-create-groups"></a><span data-ttu-id="52400-103">Verwalten von Personen, die Gruppen erstellen können</span><span class="sxs-lookup"><span data-stu-id="52400-103">Manage who can create Groups</span></span>

  
<span data-ttu-id="52400-104">Da es für Benutzer so einfach ist, Microsoft 365-Gruppen zu erstellen, werden Sie nicht mit Anforderungen überschwemmt, um Sie im Namen anderer Personen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="52400-104">Because it's so easy for users to create Microsoft 365 groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="52400-105">Je nach Ihrem Unternehmen möchten Sie jedoch steuern, welche Personen die Möglichkeit zum Erstellen von Gruppen haben sollen.</span><span class="sxs-lookup"><span data-stu-id="52400-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="52400-106">In diesem Artikel wird erklärt, wie Sie die Möglichkeit zum Erstellen von Gruppen in allen Microsoft 365-Diensten, die Gruppen verwenden, deaktivieren, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="52400-106">This article explains how to disable the ability to create groups in all Microsoft 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="52400-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="52400-107">Outlook</span></span>
    
- <span data-ttu-id="52400-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="52400-108">SharePoint</span></span>
    
- <span data-ttu-id="52400-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="52400-109">Yammer</span></span>
    
- <span data-ttu-id="52400-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52400-110">Microsoft Teams</span></span>

- <span data-ttu-id="52400-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="52400-111">Microsoft Stream</span></span>

- <span data-ttu-id="52400-112">Planner</span><span class="sxs-lookup"><span data-stu-id="52400-112">Planner</span></span>
    
- <span data-ttu-id="52400-113">PowerBI</span><span class="sxs-lookup"><span data-stu-id="52400-113">PowerBI</span></span>

- <span data-ttu-id="52400-114">Projekt für das Internet und Roadmap</span><span class="sxs-lookup"><span data-stu-id="52400-114">Project for the web and Roadmap</span></span>
    
<span data-ttu-id="52400-115">Sie können die Erstellung von Microsoft 365-Gruppen auf die Mitglieder einer bestimmten Sicherheitsgruppe einschränken.</span><span class="sxs-lookup"><span data-stu-id="52400-115">You can restrict Microsoft 365 group creation to the members of a particular security group.</span></span> <span data-ttu-id="52400-116">Um dies zu konfigurieren, verwenden Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52400-116">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="52400-117">Dieser Artikel führt Sie durch die erforderlichen Schritte.</span><span class="sxs-lookup"><span data-stu-id="52400-117">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="52400-118">Durch die in diesem Artikel beschriebenen Schritte wird nicht verhindert, dass Mitglieder mit bestimmten Rollen Gruppen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="52400-118">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="52400-119">Globale Administratoren können Gruppen über beliebige Mittel erstellen, beispielsweise das Microsoft 365 Admin Center, den Planer, Teams, Exchange und SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="52400-119">Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="52400-120">Benutzer mit anderen Rollen können Gruppen über begrenzte Instrumente erstellen, die nachstehend aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="52400-120">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="52400-121">Exchange-Administrator: Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="52400-121">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="52400-122">Partnersupport der Ebene 1: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="52400-122">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="52400-123">Partnersupport der Ebene 2: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="52400-123">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="52400-124">Verzeichnisautoren: Azure AD</span><span class="sxs-lookup"><span data-stu-id="52400-124">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="52400-125">SharePoint-Administrator: SharePoint Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="52400-125">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="52400-126">Microsoft Teams-Dienstadministrator: Microsoft Teams Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="52400-126">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="52400-127">Benutzerverwaltungsadministrator: Microsoft 365 Admin Center, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="52400-127">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="52400-128">Wenn Sie Mitglied einer dieser Rollen sind, können Sie Microsoft 365-Gruppen für eingeschränkte Benutzer erstellen und dann den Benutzer als Besitzer der Gruppe zuweisen.</span><span class="sxs-lookup"><span data-stu-id="52400-128">If you're a member of one of these roles, you can create Microsoft 365 groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="52400-129">Benutzer mit dieser Rolle können in Yammer verbundene Gruppen erstellen, und zwar unabhängig von PowerShell-Einstellungen, die eine Erstellung verhindern sollten.</span><span class="sxs-lookup"><span data-stu-id="52400-129">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="52400-130">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="52400-130">Licensing requirements</span></span>

<span data-ttu-id="52400-131">Um verwalten zu können, wer Gruppen erstellt, benötigen die folgenden Personen ihnen zugewiesene Azure AD Premium-Lizenzen oder Azure AD Basic EDU-Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="52400-131">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="52400-132">Der Administrator, der die Einstellungen für die Gruppenerstellung konfiguriert</span><span class="sxs-lookup"><span data-stu-id="52400-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="52400-133">Die Mitglieder der Sicherheitsgruppe, die Gruppen erstellen dürfen</span><span class="sxs-lookup"><span data-stu-id="52400-133">The members of the security group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="52400-134">Weitere Informationen zum Zuweisen von Azure-Lizenzen finden Sie unter [zuweisen oder Entfernen von Lizenzen im Azure Active Directory-Portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) .</span><span class="sxs-lookup"><span data-stu-id="52400-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="52400-135">Die folgenden Personen benötigen keine ihnen zugewiesene Azure AD Premium-Lizenzen oder Azure AD Basic EDU-Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="52400-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="52400-136">Personen, die Mitglied von Microsoft 365-Gruppen sind und nicht die Möglichkeit haben, andere Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="52400-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="52400-137">Schritt 1: Erstellen einer Sicherheitsgruppe für Benutzer, die Microsoft 365-Gruppen erstellen müssen</span><span class="sxs-lookup"><span data-stu-id="52400-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="52400-138">Zum Steuern des Personenkreises, der Gruppen erstellen kann, kann in Ihrer Organisation nur eine Sicherheitsgruppe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52400-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="52400-139">Sie können jedoch andere Sicherheitsgruppen als Mitglieder dieser Gruppe schachteln.</span><span class="sxs-lookup"><span data-stu-id="52400-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="52400-140">Beispiel: Die Gruppe namens "Gruppenerstellung zulassen" ist die designierte Sicherheitsgruppe, und die Gruppen namens "Microsoft Planner-Benutzer" und "Exchange Online-Benutzer" sind Mitglieder dieser Gruppe.</span><span class="sxs-lookup"><span data-stu-id="52400-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="52400-141">Administratoren mit den oben aufgeführten Rollen müssen nicht Mitglieder dieser Gruppe sein: Sie behalten ihre Fähigkeit, Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="52400-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52400-142">Achten Sie darauf, mithilfe einer **Sicherheitsgruppe** einzuschränken, wer Gruppen erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="52400-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="52400-143">Wenn Sie versuchen, eine Microsoft 365-Gruppe zu verwenden, können Mitglieder keine Gruppe aus SharePoint erstellen, da Sie nach einer Sicherheitsgruppe sucht.</span><span class="sxs-lookup"><span data-stu-id="52400-143">If you try to use a Microsoft 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="52400-144">Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.</span><span class="sxs-lookup"><span data-stu-id="52400-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="52400-145">Klicken Sie auf **Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="52400-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="52400-146">Wählen Sie als Gruppentyp die Option **Sicherheit** aus.</span><span class="sxs-lookup"><span data-stu-id="52400-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="52400-147">Vergessen Sie nicht den Namen der Gruppe!</span><span class="sxs-lookup"><span data-stu-id="52400-147">Remember the name of the group!</span></span> <span data-ttu-id="52400-148">Sie benötigen ihn später noch.</span><span class="sxs-lookup"><span data-stu-id="52400-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="52400-149">Schließen Sie die Einrichtung der Sicherheitsgruppe ab, und fügen Sie Personen oder andere Sicherheitsgruppen hinzu, die in Ihrer Organisation Gruppen erstellen können sollen.</span><span class="sxs-lookup"><span data-stu-id="52400-149">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="52400-150">Ausführliche Anleitungen finden Sie unter [Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center](../email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="52400-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="52400-151">Schritt 2: Ausführen von PowerShell-Befehlen</span><span class="sxs-lookup"><span data-stu-id="52400-151">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="52400-152">Sie müssen die Vorschau-Version von [Azure Active Directory PowerShell für Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) verwenden (Modulname **AzureADPreview**), um die Einstellung für den Gastzugriff auf Gruppenebene zu ändern:</span><span class="sxs-lookup"><span data-stu-id="52400-152">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="52400-153">Wenn Sie zuvor noch keine Version des Azure AD PowerShell-Moduls installiert haben, lesen Sie [Installieren des Azure AD-Moduls](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module), und folgen Sie den Anweisungen zum Installieren der öffentlichen Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="52400-153">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="52400-154">Wenn Sie die allgemein verfügbare Version 2.0 des Azure AD PowerShell-Moduls (AzureAD) installiert haben, müssen Sie sie deinstallieren, indem Sie `Uninstall-Module AzureAD` in ihrer PowerShell-Sitzung ausführen, und dann mit `Install-Module AzureADPreview` die Vorschauversion installieren.</span><span class="sxs-lookup"><span data-stu-id="52400-154">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="52400-155">Wenn Sie die Vorschauversion bereits installiert haben, führen Sie `Install-Module AzureADPreview` aus, um sicherzustellen, dass es sich um die neueste Version dieses Moduls handelt.</span><span class="sxs-lookup"><span data-stu-id="52400-155">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="52400-156">Kopieren Sie das folgende Skript in einen Text-Editor wie Editor oder [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="52400-156">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="52400-157">Ersetzen *\<SecurityGroupName\>* Sie durch den Namen der Sicherheitsgruppe, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="52400-157">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="52400-158">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="52400-158">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="52400-159">Speichern Sie die Datei als "GroupCreators.ps1".</span><span class="sxs-lookup"><span data-stu-id="52400-159">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="52400-160">Gehen Sie im PowerShell-Fenster zu dem Speicherort, an dem Sie die Datei gespeichert haben (geben Sie "CD <FileLocation>" ein).</span><span class="sxs-lookup"><span data-stu-id="52400-160">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="52400-161">Führen Sie das Skript aus, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="52400-161">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="52400-162">und [melden sich bei der entsprechenden Aufforderung mit Ihrem Administratorkonto an](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription).</span><span class="sxs-lookup"><span data-stu-id="52400-162">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

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
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="52400-163">Die letzte Zeile des Skripts enthält die aktualisierten Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="52400-163">The last line of the script will display the updated settings:</span></span>

![So sehen Ihre Einstellungen aus, wenn Sie fertig sind.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="52400-165">Wenn Sie später die verwendete Sicherheitsgruppe ändern möchten, können Sie das Skript mit dem Namen der neuen Sicherheitsgruppe erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="52400-165">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="52400-166">Wenn Sie die Einschränkung für die Gruppenerstellung deaktivieren und wieder allen Benutzern das Erstellen von Gruppen gestatten möchten, legen Sie $GroupName auf "" und $AllowGroupCreation auf "True" fest, und führen Sie das Skript erneut aus.</span><span class="sxs-lookup"><span data-stu-id="52400-166">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="52400-167">Schritt 3: Überprüfen der ordnungsgemäßen Funktion</span><span class="sxs-lookup"><span data-stu-id="52400-167">Step 3: Verify that it works</span></span>

<span data-ttu-id="52400-168">Änderungen können dreißig Minuten oder mehr dauern, um wirksam zu werden.</span><span class="sxs-lookup"><span data-stu-id="52400-168">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="52400-169">Sie können die neuen Einstellungen überprüfen, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="52400-169">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="52400-170">Melden Sie sich mit einem Benutzerkonto von Personen an, die nicht in der Lage sein sollen, Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="52400-170">Sign in with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="52400-171">Also einer Person, die nicht Mitglied der von Ihnen erstellten Sicherheitsgruppe oder ein Administrator ist.</span><span class="sxs-lookup"><span data-stu-id="52400-171">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="52400-172">Wählen Sie die Kachel **Planner** aus.</span><span class="sxs-lookup"><span data-stu-id="52400-172">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="52400-173">Wählen Sie in Planner in der linken Navigationsleiste **Neuer Plan** aus, um einen Plan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="52400-173">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="52400-174">Jetzt sollte eine Nachricht angezeigt werden, die besagt, dass die Erstellung von Plänen und Gruppen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="52400-174">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="52400-175">Wiederholen Sie den Vorgang mit einem Mitglied der Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="52400-175">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="52400-176">Sollte es Mitgliedern der Sicherheitsgruppe nicht möglich sein, Gruppen zu erstellen, überprüfen Sie, ob Sie nicht durch ihre [OWA-Postfachrichtlinie](https://go.microsoft.com/fwlink/?linkid=852135) daran gehindert werden.</span><span class="sxs-lookup"><span data-stu-id="52400-176">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="52400-177">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="52400-177">Related articles</span></span>

[<span data-ttu-id="52400-178">Erste Schritte mit Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="52400-178">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="52400-179">Einrichten der Self-Service-Gruppenverwaltung in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="52400-179">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="52400-180">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="52400-180">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="52400-181">Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen</span><span class="sxs-lookup"><span data-stu-id="52400-181">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
