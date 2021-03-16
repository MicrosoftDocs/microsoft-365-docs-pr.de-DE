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
ms.openlocfilehash: f2d1a2062d43af750a84984aab66329ed6a4db22
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819702"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="119f5-103">Verwalten von Personen, die Microsoft 365-Gruppen erstellen können</span><span class="sxs-lookup"><span data-stu-id="119f5-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="119f5-104">Standardmäßig können alle Benutzer Microsoft 365-Gruppen erstellen.</span><span class="sxs-lookup"><span data-stu-id="119f5-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="119f5-105">Dies ist der empfohlene Ansatz, weil er es den Benutzern ermöglicht, ohne Unterstützung durch die IT mit der Zusammenarbeit zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="119f5-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="119f5-106">Wenn Sie in Ihrem Unternehmen einschränken müssen, wer Gruppen erstellen kann, verwenden Sie dazu die Verfahren in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="119f5-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="119f5-107">Wenn Sie einschränken, wer eine Gruppe erstellen kann, wirkt sich dies auf alle Dienste aus, die für den Zugriff auf Gruppen angewiesen sind, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="119f5-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="119f5-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="119f5-108">Outlook</span></span>
- <span data-ttu-id="119f5-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="119f5-109">SharePoint</span></span>
- <span data-ttu-id="119f5-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="119f5-110">Yammer</span></span>
- <span data-ttu-id="119f5-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="119f5-111">Microsoft Teams</span></span>
- <span data-ttu-id="119f5-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="119f5-112">Microsoft Stream</span></span>
- <span data-ttu-id="119f5-113">Planner</span><span class="sxs-lookup"><span data-stu-id="119f5-113">Planner</span></span>
- <span data-ttu-id="119f5-114">Power BI (klassisch)</span><span class="sxs-lookup"><span data-stu-id="119f5-114">Power BI (classic)</span></span>
- <span data-ttu-id="119f5-115">Project für das Web / Roadmap</span><span class="sxs-lookup"><span data-stu-id="119f5-115">Project for the web / Roadmap</span></span>

<span data-ttu-id="119f5-116">Sie können die Erstellung von Microsoft 365-Gruppen auf die Mitglieder einer bestimmten Microsoft 365-Gruppe oder Sicherheitsgruppe beschränken.</span><span class="sxs-lookup"><span data-stu-id="119f5-116">You can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span> <span data-ttu-id="119f5-117">Um dies zu konfigurieren, verwenden Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="119f5-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="119f5-118">Dieser Artikel führt Sie durch die erforderlichen Schritte.</span><span class="sxs-lookup"><span data-stu-id="119f5-118">This article walks you through the needed steps.</span></span>

<span data-ttu-id="119f5-119">Durch die in diesem Artikel beschriebenen Schritte wird nicht verhindert, dass Mitglieder mit bestimmten Rollen Gruppen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="119f5-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="119f5-120">Globale Office 365-Administratoren können über beliebige Instrumente Gruppen erstellen, z. B. über das Microsoft 365 Admin Center, Planner, Microsoft Teams, Exchange und SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="119f5-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="119f5-121">Benutzer mit anderen Rollen können Gruppen über begrenzte Instrumente erstellen, die nachstehend aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="119f5-121">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="119f5-122">Exchange-Administrator: Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="119f5-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="119f5-123">Partnersupport der Ebene 1: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="119f5-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="119f5-124">Partnersupport der Ebene 2: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="119f5-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="119f5-125">Verzeichnisautoren: Azure AD</span><span class="sxs-lookup"><span data-stu-id="119f5-125">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="119f5-126">SharePoint-Administrator: SharePoint Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="119f5-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="119f5-127">Microsoft Teams-Dienstadministrator: Microsoft Teams Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="119f5-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="119f5-128">Benutzeradministrator: Microsoft 365 Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="119f5-128">User Administrator: Microsoft 365 Admin center, Azure AD</span></span>

<span data-ttu-id="119f5-129">Wenn Sie Mitglied einer dieser Rollen sind, können Sie Microsoft 365-Gruppen für Benutzer mit eingeschränktem Zugriff erstellen und anschließend den Benutzer als Besitzer der Gruppe zuweisen.</span><span class="sxs-lookup"><span data-stu-id="119f5-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="119f5-130">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="119f5-130">Licensing requirements</span></span>

<span data-ttu-id="119f5-131">Um verwalten zu können, wer Gruppen erstellt, benötigen die folgenden Personen ihnen zugewiesene Azure AD Premium-Lizenzen oder Azure AD Basic EDU-Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="119f5-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="119f5-132">Der Administrator, der die Einstellungen für die Gruppenerstellung konfiguriert</span><span class="sxs-lookup"><span data-stu-id="119f5-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="119f5-133">Die Mitglieder der Gruppe, die Gruppen erstellen dürfen</span><span class="sxs-lookup"><span data-stu-id="119f5-133">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="119f5-134">Weitere Details zum Zuweisen von Azure-Lizenzen finden Sie unter [Zuweisen oder Entfernen von Lizenzen im Azure Active Directory-Portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span><span class="sxs-lookup"><span data-stu-id="119f5-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="119f5-135">Die folgenden Personen benötigen keine ihnen zugewiesene Azure AD Premium-Lizenzen oder Azure AD Basic EDU-Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="119f5-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="119f5-136">Personen, die Mitglieder von Microsoft 365-Gruppen sind und keine Möglichkeit haben, andere Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="119f5-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="119f5-137">Schritt 1: Erstellen einer Gruppe für Benutzer, die Microsoft 365-Gruppen erstellen müssen</span><span class="sxs-lookup"><span data-stu-id="119f5-137">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="119f5-138">Zum Steuern des Personenkreises, der Gruppen erstellen kann, kann in Ihrer Organisation nur eine Gruppe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="119f5-138">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="119f5-139">Sie können jedoch andere Gruppen als Mitglieder dieser Gruppe schachteln.</span><span class="sxs-lookup"><span data-stu-id="119f5-139">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="119f5-140">Administratoren mit den oben aufgeführten Rollen müssen nicht Mitglieder dieser Gruppe sein: Sie behalten ihre Fähigkeit, Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="119f5-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="119f5-141">Wechseln Sie im Admin Center zur Seite [Gruppen](https://admin.microsoft.com/adminportal/home#/groups).</span><span class="sxs-lookup"><span data-stu-id="119f5-141">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="119f5-142">Klicken Sie auf **Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="119f5-142">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="119f5-143">Wählen Sie den gewünschten Gruppentyp aus.</span><span class="sxs-lookup"><span data-stu-id="119f5-143">Choose the group type you want.</span></span> <span data-ttu-id="119f5-144">Vergessen Sie nicht den Namen der Gruppe!</span><span class="sxs-lookup"><span data-stu-id="119f5-144">Remember the name of the group!</span></span> <span data-ttu-id="119f5-145">Sie benötigen ihn später noch.</span><span class="sxs-lookup"><span data-stu-id="119f5-145">You'll need it later.</span></span>

4. <span data-ttu-id="119f5-146">Schließen Sie die Einrichtung der Gruppe ab, indem Sie Personen oder andere Gruppen hinzufügen, denen Sie in Ihrer Organisation das Erstellen von Gruppen erlauben möchten.</span><span class="sxs-lookup"><span data-stu-id="119f5-146">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="119f5-147">Ausführliche Anleitungen finden Sie unter [Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span><span class="sxs-lookup"><span data-stu-id="119f5-147">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="119f5-148">Schritt 2: Ausführen von PowerShell-Befehlen</span><span class="sxs-lookup"><span data-stu-id="119f5-148">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="119f5-149">Sie müssen die Vorschau-Version von [Azure Active Directory PowerShell für Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) verwenden (Modulname **AzureADPreview**), um die Einstellung für den Gastzugriff auf Gruppenebene zu ändern:</span><span class="sxs-lookup"><span data-stu-id="119f5-149">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="119f5-150">Wenn Sie zuvor noch keine Version des Azure AD PowerShell-Moduls installiert haben, lesen Sie [Installieren des Azure AD-Moduls](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true), und folgen Sie den Anweisungen zum Installieren der öffentlichen Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="119f5-150">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="119f5-151">Wenn Sie die allgemein verfügbare Version 2.0 des Azure AD PowerShell-Moduls (AzureAD) installiert haben, müssen Sie sie deinstallieren, indem Sie `Uninstall-Module AzureAD` in ihrer PowerShell-Sitzung ausführen, und dann mit `Install-Module AzureADPreview` die Vorschauversion installieren.</span><span class="sxs-lookup"><span data-stu-id="119f5-151">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="119f5-152">Wenn Sie die Vorschauversion bereits installiert haben, führen Sie `Install-Module AzureADPreview` aus, um sicherzustellen, dass es sich um die neueste Version dieses Moduls handelt.</span><span class="sxs-lookup"><span data-stu-id="119f5-152">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="119f5-153">Kopieren Sie das folgende Skript in einen Text-Editor wie Editor oder [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="119f5-153">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="119f5-154">Ersetzen Sie *\<GroupName\>* durch den Namen der Gruppe, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="119f5-154">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="119f5-155">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="119f5-155">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="119f5-156">Speichern Sie die Datei als "GroupCreators.ps1".</span><span class="sxs-lookup"><span data-stu-id="119f5-156">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="119f5-157">Gehen Sie im PowerShell-Fenster zu dem Speicherort, an dem Sie die Datei gespeichert haben (geben Sie "CD <FileLocation>" ein).</span><span class="sxs-lookup"><span data-stu-id="119f5-157">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="119f5-158">Führen Sie das Skript aus, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="119f5-158">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="119f5-159">und [melden sich bei der entsprechenden Aufforderung mit Ihrem Administratorkonto an](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription).</span><span class="sxs-lookup"><span data-stu-id="119f5-159">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="119f5-160">Die letzte Zeile des Skripts enthält die aktualisierten Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="119f5-160">The last line of the script will display the updated settings:</span></span>

![So sehen Ihre Einstellungen aus, wenn Sie fertig sind.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="119f5-162">Wenn Sie später die verwendete Gruppe ändern möchten, können Sie das Skript mit dem Namen der neuen Gruppe erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="119f5-162">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="119f5-163">Wenn Sie die Einschränkung für die Gruppenerstellung deaktivieren und wieder allen Benutzern das Erstellen von Gruppen gestatten möchten, legen Sie $GroupName auf "" und $AllowGroupCreation auf "True" fest, und führen Sie das Skript erneut aus.</span><span class="sxs-lookup"><span data-stu-id="119f5-163">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="119f5-164">Schritt 3: Überprüfen der ordnungsgemäßen Funktion</span><span class="sxs-lookup"><span data-stu-id="119f5-164">Step 3: Verify that it works</span></span>

<span data-ttu-id="119f5-165">Es kann dreißig Minuten oder länger dauern, bis Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="119f5-165">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="119f5-166">Sie können die neuen Einstellungen auf folgende Weise prüfen:</span><span class="sxs-lookup"><span data-stu-id="119f5-166">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="119f5-167">Melden Sie sich bei Microsoft 365 mit dem Benutzerkonto einer Person an, der es NICHT möglich sein sollte, Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="119f5-167">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="119f5-168">Also einer Person, die nicht Mitglied der von Ihnen erstellten Gruppe oder ein Administrator ist.</span><span class="sxs-lookup"><span data-stu-id="119f5-168">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="119f5-169">Wählen Sie die Kachel **Planner** aus.</span><span class="sxs-lookup"><span data-stu-id="119f5-169">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="119f5-170">Wählen Sie in Planner in der linken Navigationsleiste **Neuer Plan** aus, um einen Plan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="119f5-170">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="119f5-171">Jetzt sollte eine Nachricht angezeigt werden, die besagt, dass die Erstellung von Plänen und Gruppen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="119f5-171">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="119f5-172">Wiederholen Sie den Vorgang mit einem Mitglied der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="119f5-172">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="119f5-173">Sollte es Mitgliedern der Gruppe nicht möglich sein, Gruppen zu erstellen, überprüfen Sie, ob Sie nicht durch ihre [OWA-Postfachrichtlinie](https://go.microsoft.com/fwlink/?linkid=852135) daran gehindert werden.</span><span class="sxs-lookup"><span data-stu-id="119f5-173">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>

## <a name="related-topics"></a><span data-ttu-id="119f5-174">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="119f5-174">Related topics</span></span>

[<span data-ttu-id="119f5-175">Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="119f5-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="119f5-176">Erstellen eines Plans für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="119f5-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="119f5-177">Erste Schritte mit Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="119f5-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="119f5-178">Einrichten der Self-Service-Gruppenverwaltung in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="119f5-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="119f5-179">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="119f5-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="119f5-180">Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen</span><span class="sxs-lookup"><span data-stu-id="119f5-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
