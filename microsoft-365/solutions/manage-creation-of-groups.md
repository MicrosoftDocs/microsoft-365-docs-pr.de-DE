---
title: Verwalten von Personen, die Microsoft 365-Gruppen erstellen können
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Erfahren Sie, wie Sie steuern können, welche Benutzer Microsoft 365-Gruppen erstellen können.
ms.openlocfilehash: 092ff821911ef0af2b7867e1b870b68b1b6355b3
ms.sourcegitcommit: dcc6bfd228ca9070975ce9eb14574e084f9ed92c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656985"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="505b1-103">Verwalten von Personen, die Microsoft 365-Gruppen erstellen können</span><span class="sxs-lookup"><span data-stu-id="505b1-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="505b1-104">Standardmäßig können alle Benutzer Microsoft 365-Gruppen erstellen.</span><span class="sxs-lookup"><span data-stu-id="505b1-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="505b1-105">Dies ist der empfohlene Ansatz, weil er es den Benutzern ermöglicht, ohne Unterstützung durch die IT mit der Zusammenarbeit zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="505b1-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="505b1-106">Wenn Ihr Unternehmen erfordert, dass Sie einschränken, wer Gruppen erstellen kann, können Sie die Microsoft 365-Gruppenerstellung auf die Mitglieder einer bestimmten Microsoft 365- oder Sicherheitsgruppe beschränken.</span><span class="sxs-lookup"><span data-stu-id="505b1-106">If your business requires that you restrict who can create groups, you can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span>

<span data-ttu-id="505b1-107">Wenn Sie bedenken, dass Benutzer Teams oder Gruppen erstellen, die Ihren Geschäftsstandards nicht entsprechen, sollten Sie die Benutzer zum Abschließen eines Schulungskurses und anschließenden Hinzufügen zur Gruppe der zulässigen Benutzer verwenden.</span><span class="sxs-lookup"><span data-stu-id="505b1-107">If you're concerned about users creating teams or groups that don't comply with your business standards, consider requiring users to complete a training course and then adding them to the group of allowed users.</span></span>

<span data-ttu-id="505b1-108">Wenn Sie einschränken, wer eine Gruppe erstellen kann, wirkt sich dies auf alle Dienste aus, die für den Zugriff auf Gruppen angewiesen sind, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="505b1-108">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="505b1-109">Outlook</span><span class="sxs-lookup"><span data-stu-id="505b1-109">Outlook</span></span>
- <span data-ttu-id="505b1-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="505b1-110">SharePoint</span></span>
- <span data-ttu-id="505b1-111">Yammer</span><span class="sxs-lookup"><span data-stu-id="505b1-111">Yammer</span></span>
- <span data-ttu-id="505b1-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="505b1-112">Microsoft Teams</span></span>
- <span data-ttu-id="505b1-113">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="505b1-113">Microsoft Stream</span></span>
- <span data-ttu-id="505b1-114">Planner</span><span class="sxs-lookup"><span data-stu-id="505b1-114">Planner</span></span>
- <span data-ttu-id="505b1-115">Power BI (klassisch)</span><span class="sxs-lookup"><span data-stu-id="505b1-115">Power BI (classic)</span></span>
- <span data-ttu-id="505b1-116">Project für das Web / Roadmap</span><span class="sxs-lookup"><span data-stu-id="505b1-116">Project for the web / Roadmap</span></span>

<span data-ttu-id="505b1-117">Durch die in diesem Artikel beschriebenen Schritte wird nicht verhindert, dass Mitglieder mit bestimmten Rollen Gruppen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="505b1-117">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="505b1-118">Office 365 Globale Administratoren können Gruppen über das Microsoft 365 Admin Center, Planner, Exchange und SharePoint Online erstellen.</span><span class="sxs-lookup"><span data-stu-id="505b1-118">Office 365 Global admins can create Groups via the Microsoft 365 admin center, Planner, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="505b1-119">Benutzer mit anderen Rollen können Gruppen über begrenzte Instrumente erstellen, die nachstehend aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="505b1-119">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="505b1-120">Exchange-Administrator: Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="505b1-120">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="505b1-121">Partnersupport der Ebene 1: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="505b1-121">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="505b1-122">Partnersupport der Ebene 2: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="505b1-122">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="505b1-123">Verzeichnisautoren: Azure AD</span><span class="sxs-lookup"><span data-stu-id="505b1-123">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="505b1-124">SharePoint-Administrator: SharePoint Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="505b1-124">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="505b1-125">Microsoft Teams-Dienstadministrator: Microsoft Teams Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="505b1-125">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="505b1-126">Benutzeradministrator: Microsoft 365 Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="505b1-126">User Administrator: Microsoft 365 Admin center, Azure AD</span></span>

<span data-ttu-id="505b1-127">Wenn Sie Mitglied einer dieser Rollen sind, können Sie Microsoft 365-Gruppen für Benutzer mit eingeschränktem Zugriff erstellen und anschließend den Benutzer als Besitzer der Gruppe zuweisen.</span><span class="sxs-lookup"><span data-stu-id="505b1-127">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="505b1-128">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="505b1-128">Licensing requirements</span></span>

<span data-ttu-id="505b1-129">Um verwalten zu können, wer Gruppen erstellt, benötigen die folgenden Personen ihnen zugewiesene Azure AD Premium-Lizenzen oder Azure AD Basic EDU-Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="505b1-129">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="505b1-130">Der Administrator, der die Einstellungen für die Gruppenerstellung konfiguriert</span><span class="sxs-lookup"><span data-stu-id="505b1-130">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="505b1-131">Die Mitglieder der Gruppe, die Gruppen erstellen dürfen</span><span class="sxs-lookup"><span data-stu-id="505b1-131">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="505b1-132">Weitere Details zum Zuweisen von Azure-Lizenzen finden Sie unter [Zuweisen oder Entfernen von Lizenzen im Azure Active Directory-Portal](/azure/active-directory/fundamentals/license-users-groups).</span><span class="sxs-lookup"><span data-stu-id="505b1-132">See [Assign or remove licenses in the Azure Active Directory portal](/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="505b1-133">Die folgenden Personen benötigen keine ihnen zugewiesene Azure AD Premium-Lizenzen oder Azure AD Basic EDU-Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="505b1-133">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="505b1-134">Personen, die Mitglieder von Microsoft 365-Gruppen sind und keine Möglichkeit haben, andere Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="505b1-134">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="505b1-135">Schritt 1: Erstellen einer Gruppe für Benutzer, die Microsoft 365-Gruppen erstellen müssen</span><span class="sxs-lookup"><span data-stu-id="505b1-135">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="505b1-136">Zum Steuern des Personenkreises, der Gruppen erstellen kann, kann in Ihrer Organisation nur eine Gruppe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="505b1-136">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="505b1-137">Sie können jedoch andere Gruppen als Mitglieder dieser Gruppe schachteln.</span><span class="sxs-lookup"><span data-stu-id="505b1-137">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="505b1-138">Administratoren mit den oben aufgeführten Rollen müssen nicht Mitglieder dieser Gruppe sein: Sie behalten ihre Fähigkeit, Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="505b1-138">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="505b1-139">Wechseln Sie im Admin Center zur Seite [Gruppen](https://admin.microsoft.com/adminportal/home#/groups).</span><span class="sxs-lookup"><span data-stu-id="505b1-139">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="505b1-140">Klicken Sie auf **Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="505b1-140">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="505b1-141">Wählen Sie den gewünschten Gruppentyp aus.</span><span class="sxs-lookup"><span data-stu-id="505b1-141">Choose the group type you want.</span></span> <span data-ttu-id="505b1-142">Vergessen Sie nicht den Namen der Gruppe!</span><span class="sxs-lookup"><span data-stu-id="505b1-142">Remember the name of the group!</span></span> <span data-ttu-id="505b1-143">Sie benötigen ihn später noch.</span><span class="sxs-lookup"><span data-stu-id="505b1-143">You'll need it later.</span></span>

4. <span data-ttu-id="505b1-144">Schließen Sie die Einrichtung der Gruppe ab, indem Sie Personen oder andere Gruppen hinzufügen, denen Sie in Ihrer Organisation das Erstellen von Gruppen erlauben möchten.</span><span class="sxs-lookup"><span data-stu-id="505b1-144">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="505b1-145">Ausführliche Anleitungen finden Sie unter [Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center](../admin/email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="505b1-145">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../admin/email/create-edit-or-delete-a-security-group.md).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="505b1-146">Schritt 2: Ausführen von PowerShell-Befehlen</span><span class="sxs-lookup"><span data-stu-id="505b1-146">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="505b1-147">Sie müssen die Vorschau-Version von [Azure Active Directory PowerShell für Graph (AzureAD)](/powershell/azure/active-directory/install-adv2) verwenden (Modulname **AzureADPreview**), um die Einstellung für den Gastzugriff auf Gruppenebene zu ändern:</span><span class="sxs-lookup"><span data-stu-id="505b1-147">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="505b1-148">Wenn Sie zuvor noch keine Version des Azure AD PowerShell-Moduls installiert haben, lesen Sie [Installieren des Azure AD-Moduls](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview), und folgen Sie den Anweisungen zum Installieren der öffentlichen Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="505b1-148">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="505b1-149">Wenn Sie die allgemein verfügbare Version 2.0 des Azure AD PowerShell-Moduls (AzureAD) installiert haben, müssen Sie sie deinstallieren, indem Sie `Uninstall-Module AzureAD` in ihrer PowerShell-Sitzung ausführen, und dann mit `Install-Module AzureADPreview` die Vorschauversion installieren.</span><span class="sxs-lookup"><span data-stu-id="505b1-149">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="505b1-150">Wenn Sie die Vorschauversion bereits installiert haben, führen Sie `Install-Module AzureADPreview` aus, um sicherzustellen, dass es sich um die neueste Version dieses Moduls handelt.</span><span class="sxs-lookup"><span data-stu-id="505b1-150">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="505b1-151">Kopieren Sie das folgende Skript in einen Text-Editor wie Editor oder [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="505b1-151">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="505b1-152">Ersetzen Sie *\<GroupName\>* durch den Namen der Gruppe, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="505b1-152">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="505b1-153">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="505b1-153">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="505b1-154">Speichern Sie die Datei als "GroupCreators.ps1".</span><span class="sxs-lookup"><span data-stu-id="505b1-154">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="505b1-155">Gehen Sie im PowerShell-Fenster zu dem Speicherort, an dem Sie die Datei gespeichert haben (geben Sie "CD <FileLocation>" ein).</span><span class="sxs-lookup"><span data-stu-id="505b1-155">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="505b1-156">Führen Sie das Skript aus, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="505b1-156">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="505b1-157">und [melden sich bei der entsprechenden Aufforderung mit Ihrem Administratorkonto an](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription).</span><span class="sxs-lookup"><span data-stu-id="505b1-157">and [sign in with your administrator account](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

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

<span data-ttu-id="505b1-158">Die letzte Zeile des Skripts enthält die aktualisierten Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="505b1-158">The last line of the script will display the updated settings:</span></span>

![Screenshot der PowerShell-Skriptausgabe.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="505b1-160">Wenn Sie später die verwendete Gruppe ändern möchten, können Sie das Skript mit dem Namen der neuen Gruppe erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="505b1-160">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="505b1-161">Wenn Sie die Einschränkung für die Gruppenerstellung deaktivieren und wieder allen Benutzern das Erstellen von Gruppen gestatten möchten, legen Sie $GroupName auf "" und $AllowGroupCreation auf "True" fest, und führen Sie das Skript erneut aus.</span><span class="sxs-lookup"><span data-stu-id="505b1-161">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="505b1-162">Schritt 3: Überprüfen der ordnungsgemäßen Funktion</span><span class="sxs-lookup"><span data-stu-id="505b1-162">Step 3: Verify that it works</span></span>

<span data-ttu-id="505b1-163">Es kann dreißig Minuten oder länger dauern, bis Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="505b1-163">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="505b1-164">Sie können die neuen Einstellungen auf folgende Weise prüfen:</span><span class="sxs-lookup"><span data-stu-id="505b1-164">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="505b1-165">Melden Sie sich bei Microsoft 365 mit dem Benutzerkonto einer Person an, der es NICHT möglich sein sollte, Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="505b1-165">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="505b1-166">Also einer Person, die nicht Mitglied der von Ihnen erstellten Gruppe oder ein Administrator ist.</span><span class="sxs-lookup"><span data-stu-id="505b1-166">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="505b1-167">Wählen Sie die Kachel **Planner** aus.</span><span class="sxs-lookup"><span data-stu-id="505b1-167">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="505b1-168">Wählen Sie in Planner in der linken Navigationsleiste **Neuer Plan** aus, um einen Plan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="505b1-168">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="505b1-169">Jetzt sollte eine Nachricht angezeigt werden, die besagt, dass die Erstellung von Plänen und Gruppen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="505b1-169">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="505b1-170">Wiederholen Sie den Vorgang mit einem Mitglied der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="505b1-170">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="505b1-171">Sollte es Mitgliedern der Gruppe nicht möglich sein, Gruppen zu erstellen, überprüfen Sie, ob Sie nicht durch ihre [OWA-Postfachrichtlinie](/powershell/module/exchange/set-owamailboxpolicy) daran gehindert werden.</span><span class="sxs-lookup"><span data-stu-id="505b1-171">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="505b1-172">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="505b1-172">Related topics</span></span>

[<span data-ttu-id="505b1-173">Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="505b1-173">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="505b1-174">Erstellen eines Plans für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="505b1-174">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="505b1-175">Erste Schritte mit Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="505b1-175">Getting started with Office 365 PowerShell</span></span>](../enterprise/getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="505b1-176">Einrichten der Self-Service-Gruppenverwaltung in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="505b1-176">Set up self-service group management in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="505b1-177">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="505b1-177">Set-ExecutionPolicy</span></span>](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="505b1-178">Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen</span><span class="sxs-lookup"><span data-stu-id="505b1-178">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
