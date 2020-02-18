---
title: Verwenden von Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites (öffentliche Vorschau)
f1.keywords:
- NOCSH
ms.author: krowley
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Sie können Bezeichnungen auf Microsoft Teams, Office 365-Gruppen und SharePoint-Websites anwenden.
ms.openlocfilehash: 297ccd3e17f6c5a747e18a46747e6f2c23311df0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069798"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="1d8cf-103">Verwenden von Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites (öffentliche Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1d8cf-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="1d8cf-104">Wenn Sie im [Microsoft 365 Compliance Center](https://protection.office.com/) Vertraulichkeitsbezeichnungen erstellen, können Sie diese jetzt auf Microsoft Teams, Office 365-Gruppen und SharePoint-Websites anwenden.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="1d8cf-105">Sie können den Bezeichnungen Richtlinien zuordnen, um Folgendes zu steuern:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="1d8cf-106">Öffentliche/private-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1d8cf-106">Public/private settings</span></span>
- <span data-ttu-id="1d8cf-107">Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="1d8cf-107">Guest access</span></span>
- <span data-ttu-id="1d8cf-108">Zugriff von nicht verwalteten Geräten aus</span><span class="sxs-lookup"><span data-stu-id="1d8cf-108">Access from unmanaged devices</span></span>

<span data-ttu-id="1d8cf-109">Wenn Sie eine Bezeichnung auf ein Team oder eine Gruppe anwenden, wird die Bezeichnung automatisch auf die verbundene SharePoint-Teamwebsite und umgekehrt angewendet.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="1d8cf-110">Außerdem können Sie Vertraulichkeitsbezeichnungen jetzt auch für Office-Dateien in SharePoint und OneDrive aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-110">You can now also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="1d8cf-111">Weitere Informationen finden Sie unter [Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive (öffentliche Vorschau)](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-111">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="1d8cf-112">Informationen zur öffentlichen Vorschau für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="1d8cf-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="1d8cf-113">Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites werden schrittweise für Mandanten bereitgestellt und können sich vor der endgültigen Version ändern.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are gradually rolling out to tenants and might change before final release.</span></span>

<span data-ttu-id="1d8cf-114">Diese öffentliche Vorschau kann nicht mit Office 365-Netzwerken für die Inhaltsübermittlung (Content Delivery Network, CDN) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="overview"></a><span data-ttu-id="1d8cf-115">Übersicht</span><span class="sxs-lookup"><span data-stu-id="1d8cf-115">Overview</span></span>

<span data-ttu-id="1d8cf-116">Wenn Sie Vertraulichkeitsbezeichnungen veröffentlichen, haben alle Benutzer in Office 365 Zugriff auf dieselbe Liste von Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-116">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="1d8cf-117">Die folgenden Bilder verdeutlichen:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-117">These images show:</span></span>

- <span data-ttu-id="1d8cf-118">Wie die Liste aussieht, wenn eine neue Teamwebsite in SharePoint erstellt wird</span><span class="sxs-lookup"><span data-stu-id="1d8cf-118">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="1d8cf-119">Wann die Liste in Word angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="1d8cf-119">When you view the list in Word</span></span>

<span data-ttu-id="1d8cf-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-120">For example:</span></span>

![Eine Vertraulichkeitsbezeichnung beim Erstellen einer Teamwebsite in SharePoint](../media/sensitivity-label-new-team-site.png)

![Eine in der Word-Desktop-App angezeigte Vertraulichkeitsbezeichnung](../media/sensitivity-label-word.png)

## <a name="enable-this-preview"></a><span data-ttu-id="1d8cf-123">Aktivieren dieser Vorschau</span><span class="sxs-lookup"><span data-stu-id="1d8cf-123">Enable this preview</span></span>

<span data-ttu-id="1d8cf-124">Sie müssen die Vorschauversion von [Azure Active Directory PowerShell für Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (Modulname **AzureADPreview**) verwenden, um diese Vorschau von Vertraulichkeitsbezeichnungen mit Microsoft Teams, Office 365-Gruppen und SharePoint-Websites zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-124">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (module name **AzureADPreview**) to enable this preview of sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites:</span></span>

- <span data-ttu-id="1d8cf-125">Wenn Sie zuvor noch keine Version des Azure AD PowerShell-Moduls installiert haben, lesen Sie [Installieren des Azure AD-Moduls](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module), und folgen Sie den Anweisungen zum Installieren der öffentlichen Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-125">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="1d8cf-126">Wenn Sie die allgemein verfügbare Version 2.0 des Azure AD PowerShell-Moduls (AzureAD) installiert haben, müssen Sie sie deinstallieren, indem Sie `Uninstall-Module AzureAD` in ihrer PowerShell-Sitzung ausführen, und dann mit `Install-Module AzureADPreview` die Vorschauversion installieren.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-126">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="1d8cf-127">Wenn Sie die Vorschauversion bereits installiert haben, führen Sie `Install-Module AzureADPreview` aus, um sicherzustellen, dass es sich um die neueste Version dieses Moduls handelt.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-127">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="1d8cf-128">Jetzt sind Sie bereit zum Aktivieren der Vorschau der Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-128">You're now ready to enable the preview of sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites:</span></span>

1. <span data-ttu-id="1d8cf-129">Stellen Sie in einer PowerShell-Sitzung unter Verwendung eines Geschäfts-, Schul-, oder Unikontos mit globalen Administratorberechtigungen eine Verbindung mit Azure Active Directory her.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-129">In a PowerShell session, using a work or school account that has global admin privileges, connect to Azure Active Directory.</span></span> <span data-ttu-id="1d8cf-130">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-130">For example, run:</span></span>
    
    ```powershell
    Connect-AzureAD
    ````
    
    <span data-ttu-id="1d8cf-131">Vollständige Anweisungen finden Sie unter [Herstellen einer Verbindung mit Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-131">For full instructions, see [Connect to Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad).</span></span>

2. <span data-ttu-id="1d8cf-132">Führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-132">Run the following commands:</span></span>
    
    ```powershell
    $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
    if ($setting -eq $null)
    {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
    }
    else
    {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
    }
    ```
    
    > [!NOTE]
    > <span data-ttu-id="1d8cf-133">Wenn Sie diese Vorschau aktivieren, verwendet Office 365 die alten Klassifizierungen nicht mehr für neue Gruppen und SharePoint-Websites.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-133">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="1d8cf-134">Wenn Sie die [Azure Ad-Websiteklassifizierung](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]) verwendet haben, zeigen vorhandene Gruppen und Websites weiterhin die alten Klassifizierungen an.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-134">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="1d8cf-135">Um die neuen Klassifizierungen anzuzeigen, konvertieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-135">To display the new classifications, convert them.</span></span> <span data-ttu-id="1d8cf-136">Informationen zur Konvertierung finden Sie unter [Sie haben die klassische Azure AD-Websiteklassifizierung verwendet](#if-you-used-classic-azure-ad-site-classification).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-136">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span> 

3. <span data-ttu-id="1d8cf-137">Stellen Sie in derselben PowerShell-Sitzung nun mithilfe eines Geschäfts-, Schul- oder Unikontos, das über globale Administratorberechtigungen verfügt, eine Verbindung mit dem Security & Compliance Center her.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-137">In the same PowerShell session, now connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="1d8cf-138">Anweisungen hierzu finden Sie unter [Herstellen einer Verbindung mit Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-138">For instructions, see [Connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

4. <span data-ttu-id="1d8cf-139">Führen Sie die folgenden Befehle aus, um Ihre Bezeichnungen mit Azure AD zu synchronisieren, damit sie mit Office 365-Gruppen verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-139">Run the following commands to synchronize your labels to Azure AD, so that they can used with Office 365 groups:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```
## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="1d8cf-140">Festlegen von Website- und Gruppeneinstellungen beim Erstellen oder Bearbeiten von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="1d8cf-140">Set site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="1d8cf-141">Nachdem Sie die Vorschau aktiviert haben, führen Sie die folgenden Schritte aus, um Vertraulichkeitsbezeichnungen zu erstellen oder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-141">After you enable the preview, use the following steps to create or edit sensitivity labels.</span></span> <span data-ttu-id="1d8cf-142">Sie müssen diese Schritte ausführen, damit die neuen Vertraulichkeitsbezeichnungen mit Websites und Gruppen verwendet werden können, auch wenn Sie bereits Bezeichnungen definiert haben.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-142">You must complete these steps for the new sensitivity labels to work with sites and groups, even if you already have labels defined.</span></span> <span data-ttu-id="1d8cf-143">Die Synchronisierung der Änderungen an diesen Einstellungen kann bis zu 24 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-143">Changes to these settings might take up to 24 hours to synchronize.</span></span>

1. <span data-ttu-id="1d8cf-144">Wählen Sie im Microsoft 365 Compliance Center **Klassifizierung** > **Vertraulichkeitsbezeichnungen** aus.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-144">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="1d8cf-145">Wählen Sie **Bezeichnung erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-145">Select **Create a label**.</span></span> <span data-ttu-id="1d8cf-146">Wenn Sie bereits über eine Bezeichnung verfügen, fahren Sie mit dem nächsten Schritt fort.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-146">If you already have a label, skip to the next step.</span></span>

3. <span data-ttu-id="1d8cf-147">Wählen Sie die gewünschten Optionen und dann auf der Registerkarte **Website- und Gruppeneinstellungen** die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-147">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>
    
    - <span data-ttu-id="1d8cf-148">Datenschutz (Öffentlich/Privat): "Privat" bedeutet, dass nur genehmigte Mitglieder in Ihrer Organisation die Inhalte der Gruppe sehen können.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-148">Privacy (Public/Private): Private means that only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="1d8cf-149">Alle anderen Benutzer in Ihrer Organisation können keine Inhalte der Gruppe anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-149">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="1d8cf-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d8cf-150">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="1d8cf-151">Gastzugriff: Sie können steuern, ob Gäste einer Gruppe hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-151">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="1d8cf-152">Weitere Informationen zum Verwalten des Gastzugriffs in Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="1d8cf-152">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="1d8cf-153">Nicht verwaltete Geräte: Mit dieser Einstellung können Sie den Zugriff auf SharePoint-Inhalte von Geräten aus, die keine in Azure AD eingebundenen Hybridgeräte oder nicht Intune-konform sind, blockieren oder einschränken.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-153">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="1d8cf-154">Wenn Sie "Nicht verwaltete Geräte" auswählen, müssen Sie zu Azure AD wechseln, um das Einrichten der Richtlinie abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-154">If you select Unmanaged devices, you must go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="1d8cf-155">Informationen hierzu finden Sie unter [Steuern des Zugriffs von nicht verwalteten Geräten aus](/sharepoint/control-access-from-unmanaged-devices).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-155">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>
    
    ![Die Registerkarte "Website- und Gruppeneinstellungen"](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="1d8cf-157">Wenn Sie eine Bezeichnung auf ein Team, eine Gruppe oder eine Website anwenden, werden nur die Website- und Gruppeneinstellungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-157">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="1d8cf-158">Andere Einstellungen (z. B. Verschlüsselung und Inhaltskennzeichnung) werden nicht auf alle Inhalte innerhalb des Teams, der Gruppen oder der Website angewendet.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-158">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="1d8cf-159">Ähnlich verhält es sich, wenn Sie eine Bezeichnung erstellen und Website- und Gruppeneinstellungen nicht aktivieren. Die Bezeichnung ist dann weiterhin verfügbar, wenn Benutzer Teams, Gruppen und Websites erstellen, aber die Klassifizierung erfolgt ohne Anwendung irgendwelcher Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-159">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it will classify without applying any settings.</span></span>

[<span data-ttu-id="1d8cf-160">Weitere Informationen zum Veröffentlichen von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="1d8cf-160">Learn more about publishing sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="sensitivity-label-management"></a><span data-ttu-id="1d8cf-161">Verwaltung von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="1d8cf-161">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="1d8cf-162">Das Erstellen, Ändern und Löschen von Vertraulichkeitsbezeichnungen, die Sie für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites verwenden, erfordert eine sorgfältige Abstimmung mit der Veröffentlichung von Bezeichnungsrichtlinien für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-162">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="1d8cf-163">Vermeiden Sie Erstellungsfehler für Websites und Gruppen, die sich auf alle Benutzer auswirken, indem Sie die nachstehenden Anweisungen beachten.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-163">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="1d8cf-164">**Erstellen und Veröffentlichen von Bezeichnungen:**</span><span class="sxs-lookup"><span data-stu-id="1d8cf-164">**Creating and publishing labels:**</span></span>

<span data-ttu-id="1d8cf-165">Nach der Erstellung und Veröffentlichung einer Vertraulichkeitsbezeichnung kann es bis zu 24 Stunden dauern, bis die Bezeichnung für Benutzer in Teams, Gruppen und Websites sichtbar wird.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-165">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="1d8cf-166">Führen Sie die folgenden Schritte aus, um eine Bezeichnung für alle Benutzer im Mandanten zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-166">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="1d8cf-167">Erstellen Sie die Vertraulichkeitsbezeichnung, und veröffentlichen Sie sie nur für einige Benutzerkonten im Mandanten.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-167">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="1d8cf-168">Warten Sie 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-168">Wait for 24 hours.</span></span>

3. <span data-ttu-id="1d8cf-169">Nach Ablauf dieser 24 Stunden erstellen Sie mit einem der in Schritt 1 angegebenen Benutzerkonten ein Team, eine Office 365-Gruppe oder eine SharePoint-Website mit der Bezeichnung, die Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-169">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="1d8cf-170">Wenn während des Erstellungsvorgangs für Schritt 3 keine Fehler auftreten, veröffentlichen Sie die Bezeichnung für alle Benutzer in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-170">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="1d8cf-171">Wenn Fehler auftreten, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-171">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="1d8cf-172">**Ändern und Löschen von veröffentlichten Bezeichnungen:**</span><span class="sxs-lookup"><span data-stu-id="1d8cf-172">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="1d8cf-173">Wenn Sie eine Vertraulichkeitsbezeichnung ändern oder löschen, die in einer oder mehreren Bezeichnungsrichtlinien enthalten ist, kann dies zu Erstellungsfehlern für alle Teams, Gruppen und Websites führen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-173">If you modify or delete a sensitivity label that is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="1d8cf-174">Folgen Sie dieser Anleitung, um dieses Problem zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-174">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="1d8cf-175">Entfernen Sie die Vertraulichkeitsbezeichnung aus allen Bezeichnungsrichtlinien, in denen die Bezeichnung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-175">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="1d8cf-176">Warten Sie 48 Stunden.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-176">Wait for 48 hours.</span></span>

3. <span data-ttu-id="1d8cf-177">Versuchen Sie nach 48 Stunden, ein Team, eine Gruppe oder eine Website zu erstellen, und vergewissern Sie sich, dass die Bezeichnung nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-177">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="1d8cf-178">Wenn die Vertraulichkeitsbezeichnung nicht angezeigt wird, können Sie sie jetzt bedenkenlos ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-178">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="1d8cf-179">Wird die Bezeichnung weiterhin angezeigt, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-179">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="1d8cf-180">Problembehandlung bei der Bereitstellung von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="1d8cf-180">Troubleshoot sensitivity label deployment</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="1d8cf-181">Bezeichnungen sind nach der Veröffentlichung nicht sichtbar</span><span class="sxs-lookup"><span data-stu-id="1d8cf-181">Labels not visible after publishing</span></span>
<span data-ttu-id="1d8cf-182">Wenn beim Erstellen eines Teams oder einer Office 365-Gruppe Probleme auftreten, nachdem Sie diese Einstellungen aktiviert oder die Beschreibung einer Vertraulichkeitsbezeichnung geändert haben, speichern Sie die Bezeichnung, warten Sie ein paar Stunden, und versuchen Sie dann erneut, das Team oder die Gruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-182">If you experience issues when you create a team or Office 365 group after you enable these settings or modify a sensitivity label's description, save the label, wait a few hours, and then try to create the team or group again.</span></span> <span data-ttu-id="1d8cf-183">Informationen hierzu finden Sie unter [Planen des Rollouts nach Erstellung oder Änderung einer Vertraulichkeitsbezeichnung](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-183">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="1d8cf-184">Wenn die neue Vertraulichkeitsbezeichnung in SharePoint Online weiterhin nicht angezeigt wird, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-184">If you are still not able to see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="1d8cf-185">Fehler beim Erstellen von Teams, Gruppen oder SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="1d8cf-185">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="1d8cf-186">Wenn während der öffentlichen Vorschau Erstellungsfehler auftreten, haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-186">If you experience creation errors during the public preview, you have two options:</span></span>

- <span data-ttu-id="1d8cf-187">Stellen Sie sicher, dass Vertraulichkeitsbezeichnungen für keinen Benutzer obligatorisch sind.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-187">Ensure that sensitivity labels are not mandatory for any user.</span></span>

- <span data-ttu-id="1d8cf-188">Sie können Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites unter Verwendung der Anweisungen im Abschnitt [Aktivieren dieser Vorschau](#enable-this-preview) auf dieser Seite deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-188">You can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from the [Enable this preview](#enable-this-preview) section on this page.</span></span> <span data-ttu-id="1d8cf-189">Wenn Sie die Vorschau jedoch deaktivieren, müssen Sie nach der Zeile `$setting["EnableMIPLabels"] = "True"` suchen und den Wert **True** in **False** ändern.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-189">However, to disable the preview, search for the line `$setting["EnableMIPLabels"] = "True"`, and change the **True** value to **False**.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="1d8cf-190">Anwenden einer Vertraulichkeitsbezeichnung auf ein neues Team</span><span class="sxs-lookup"><span data-stu-id="1d8cf-190">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="1d8cf-191">Benutzer können Vertraulichkeitsbezeichnungen auswählen, wenn sie neue Teams in Microsoft Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-191">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="1d8cf-192">Beim Auswählen der Vertraulichkeitsstufe werden die Datenschutzeinstellung bei Bedarf entsprechend geändert.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-192">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="1d8cf-193">Abhängig von der für die Bezeichnung festgelegten Einstellung für den Gastzugriff können Benutzer Personen außerhalb der Organisation zum Team hinzufügen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-193">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="1d8cf-194">Weitere Informationen Vertraulichkeitsbezeichnungen für Teams</span><span class="sxs-lookup"><span data-stu-id="1d8cf-194">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![Datenschutzeinstellung beim Erstellen eines neuen Teams](../media/privacy-setting-new-team.png)

<span data-ttu-id="1d8cf-196">Nachdem Sie das Team erstellt haben, wird die Vertraulichkeitsbezeichnung in der oberen rechten Ecke aller Kanäle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-196">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![Die Vertraulichkeitsbezeichnung wird im Team angezeigt](../media/privacy-setting-teams.png)

<span data-ttu-id="1d8cf-198">Der Dienst wendet auf die Office 365-Gruppe und die verbundene SharePoint-Teamwebsite automatisch die gleiche Vertraulichkeitsbezeichnung an.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-198">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="1d8cf-199">Anwenden einer Vertraulichkeitsbezeichnung auf eine neue Gruppe</span><span class="sxs-lookup"><span data-stu-id="1d8cf-199">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="1d8cf-200">In Outlook im Web enthält das neue Feld **Vertraulichkeit** veröffentlichte Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-200">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="1d8cf-201">Wenn Benutzer weitere Informationen benötigen, können sie auf das Hilfesymbol klicken, um Details zu den verfügbaren Bezeichnungen und den zugehörigen Richtlinien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-201">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![Erstellen einer Gruppe und Auswählen einer Option unter "Vertraulichkeit"](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="1d8cf-203">Anwenden einer Vertraulichkeitsbezeichnung auf eine neue Website</span><span class="sxs-lookup"><span data-stu-id="1d8cf-203">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="1d8cf-204">Administratoren und Endbenutzer können beim Erstellen moderner Teamwebsites und Kommunikationswebsites Vertraulichkeitsbezeichnungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-204">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

<span data-ttu-id="1d8cf-205">[Weitere Informationen zum Erstellen einer Website im neuen SharePoint Admin Center](/sharepoint/create-site-collection).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-205">[Learn how to create a site in the new SharePoint admin center](/sharepoint/create-site-collection)</span></span>

<span data-ttu-id="1d8cf-206">Wenn Benutzer moderne Teamwebsites und Kommunikationswebsites erstellen, ist standardmäßig bereits eine Vertraulichkeitsbezeichnung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-206">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="1d8cf-207">Benutzer können das Hilfesymbol auswählen, um weitere Informationen zu den Bezeichnungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-207">Users can select the help icon to learn more about the labels.</span></span>

![Erstellen einer Website und Auswählen einer Option unter "Vertraulichkeit"](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="1d8cf-209">Wenn Benutzer zu der Website navigieren, werden der Name der Bezeichnung und die angewendeten Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-209">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Eine Website, auf die eine Vertraulichkeitsbezeichnung angewendet wurde](../media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="1d8cf-211">Verwalten von Vertraulichkeitsbezeichnungen im SharePoint Online Admin Center</span><span class="sxs-lookup"><span data-stu-id="1d8cf-211">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="1d8cf-212">Wenn Sie die Bezeichnung anzeigen und bearbeiten möchten, verwenden Sie die Seite "Aktive Websites" im neuen SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-212">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![Die Spalte "Vertraulichkeit" auf der Seite "Aktive Websites"](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="1d8cf-214">[Weitere Informationen zum Verwalten von Websites im neuen SharePoint Admin Center](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-214">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="1d8cf-215">Ändern von Website- und Gruppeneinstellungen für eine Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="1d8cf-215">Change site and group settings for a label</span></span>

<span data-ttu-id="1d8cf-216">Wenn Sie eine Änderung an den Website- und Gruppeneinstellungen für eine Bezeichnung vornehmen, müssen Sie die folgenden PowerShell-Befehle ausführen, damit Ihre Teams, Websites und Gruppen die neuen Einstellungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-216">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="1d8cf-217">Es wird empfohlen, die Website- und Gruppeneinstellungen für eine Bezeichnung nicht zu ändern, nachdem Sie die Bezeichnung auf mehrere Teams, Gruppen oder Websites angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-217">As a best practice, don't the change site and group settings for a label after you've applied the label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="1d8cf-218">Führen Sie die folgenden Befehle aus, um eine Verbindung mit PowerShell im Office 365 Security & Compliance Center herzustellen und die Liste der Vertraulichkeitsbezeichnungen und deren GUIDs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-218">Run the following commands to connect to Office 365 Security & Compliance Center PowerShell and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. <span data-ttu-id="1d8cf-219">Notieren Sie sich die GUID für die Bezeichnung(en), die Sie geändert haben.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-219">Make a note of the GUID for the label or labels you have changed.</span></span>

3. <span data-ttu-id="1d8cf-220">Stellen Sie jetzt eine Verbindung mit Exchange Online PowerShell her, und führen Sie das Cmdlet "Get-UnifiedGroup" aus. Geben Sie dabei die GUID der Bezeichnung anstelle der Beispiel-GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" an:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-220">Now connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. <span data-ttu-id="1d8cf-221">Wenden Sie die Vertraulichkeitsbezeichnung für jede Gruppe unter Verwendung der Bezeichnungs-GUID anstelle der Beispiel-GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" erneut an:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-221">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="1d8cf-222">Unterstützung der neuen Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="1d8cf-222">Support for the new sensitivity labels</span></span>

<span data-ttu-id="1d8cf-223">Die folgenden Apps und Dienste unterstützen die Vertraulichkeitsbezeichnungen in dieser Vorschau:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-223">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="1d8cf-224">Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1d8cf-224">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="1d8cf-225">SharePoint</span><span class="sxs-lookup"><span data-stu-id="1d8cf-225">SharePoint</span></span>
- <span data-ttu-id="1d8cf-226">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="1d8cf-226">Outlook on the web</span></span>
- <span data-ttu-id="1d8cf-227">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d8cf-227">Teams</span></span>
- <span data-ttu-id="1d8cf-228">SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="1d8cf-228">SharePoint admin center</span></span>
- <span data-ttu-id="1d8cf-229">Azure AD Admin Center</span><span class="sxs-lookup"><span data-stu-id="1d8cf-229">Azure AD admin center</span></span>

<span data-ttu-id="1d8cf-230">Die folgenden Apps und Dienste können Sie nicht verwenden, um Office 365-Gruppen mit den neuen Vertraulichkeitsbezeichnungen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-230">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="1d8cf-231">Outlook für Mac</span><span class="sxs-lookup"><span data-stu-id="1d8cf-231">Outlook for the Mac</span></span>
- <span data-ttu-id="1d8cf-232">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="1d8cf-232">Outlook mobile</span></span>  
- <span data-ttu-id="1d8cf-233">Outlook Desktop für Windows</span><span class="sxs-lookup"><span data-stu-id="1d8cf-233">Outlook desktop for Windows</span></span>
- <span data-ttu-id="1d8cf-234">Forms</span><span class="sxs-lookup"><span data-stu-id="1d8cf-234">Forms</span></span>  
- <span data-ttu-id="1d8cf-235">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1d8cf-235">Dynamics 365</span></span>  
- <span data-ttu-id="1d8cf-236">Yammer</span><span class="sxs-lookup"><span data-stu-id="1d8cf-236">Yammer</span></span>  
- <span data-ttu-id="1d8cf-237">Stream</span><span class="sxs-lookup"><span data-stu-id="1d8cf-237">Stream</span></span>  
- <span data-ttu-id="1d8cf-238">Planner</span><span class="sxs-lookup"><span data-stu-id="1d8cf-238">Planner</span></span>  
- <span data-ttu-id="1d8cf-239">Project</span><span class="sxs-lookup"><span data-stu-id="1d8cf-239">Project</span></span>  
- <span data-ttu-id="1d8cf-240">PowerBI</span><span class="sxs-lookup"><span data-stu-id="1d8cf-240">PowerBI</span></span>  
- <span data-ttu-id="1d8cf-241">Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="1d8cf-241">Teams admin center</span></span>  
- <span data-ttu-id="1d8cf-242">Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="1d8cf-242">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="1d8cf-243">Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="1d8cf-243">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="1d8cf-244">Sie haben die klassische Azure AD-Websiteklassifizierung verwendet</span><span class="sxs-lookup"><span data-stu-id="1d8cf-244">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="1d8cf-245">Wenn Sie diese Vorschau aktivieren, unterstützt Office 365 die alten Klassifizierungen nicht mehr für neue Gruppen und SharePoint-Websites.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-245">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="1d8cf-246">Bei vorhandenen Gruppen und Websites werden die alten Klassifizierungen jedoch weiterhin angezeigt, es sei denn, Sie konvertieren sie.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-246">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="1d8cf-247">Alte Klassifizierungen schließen die Klassifizierung von "modernen" Websites ein, die Sie möglicherweise über Azure AD PowerShell oder die PnP Core-Bibliothek eingerichtet haben, in der Werte für die `ClassificationList`-Einstellung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-247">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="1d8cf-248">Beispielsweise in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-248">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="1d8cf-249">Weitere Informationen zur alten Klassifizierungsmethode finden Sie unter ["" ](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-249">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="1d8cf-250">Basierend auf Ihrer aktuellen Bereitstellung stehen Ihnen zwei Optionen zum Konvertieren Ihrer alten Klassifizierungen in die neuen Klassifizierungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-250">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="1d8cf-251">Sie haben noch nie Vertraulichkeitsbezeichnungen (einheitliche Microsoft Information Protection-Bezeichnungen) für Dateien und E-Mail verwendet</span><span class="sxs-lookup"><span data-stu-id="1d8cf-251">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="1d8cf-252">Wir empfehlen, dass Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="1d8cf-252">We recommend that you:</span></span>

1. <span data-ttu-id="1d8cf-253">Erstellen Sie im Microsoft 365 Compliance Center neue Vertraulichkeitsbezeichnungen mit denselben Namen wie Ihre vorhandenen Klassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-253">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="1d8cf-254">Verwenden Sie PowerShell, um die neuen Bezeichnungen mithilfe von Namenszuordnung auf vorhandene Office 365-Gruppen und SharePoint-Websites anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-254">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="1d8cf-255">Löschen Sie die alten Klassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-255">Delete the old classifications.</span></span>

<span data-ttu-id="1d8cf-256">Apps und Dienste, die die neuen Vertraulichkeitsbezeichnungen unterstützen, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-256">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="1d8cf-257">Sie erstellen neue Teams, Gruppen und Websites mit den neuen Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-257">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="1d8cf-258">Benutzer können weiterhin Gruppen aus Apps und Diensten erstellen, die die neuen Bezeichnungen nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-258">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="1d8cf-259">Benutzer können jedoch keine Bezeichnung auf diese Gruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-259">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="1d8cf-260">Verwenden Sie PowerShell, um die neuen Vertraulichkeitsbezeichnungen auf diese Gruppen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-260">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="1d8cf-261">Sie können Ihre alten Klassifizierungen beibehalten. Allerdings wird dringend empfohlen, PowerShell zu verwenden, um auf diese Gruppen die neuen Vertraulichkeitsbezeichnungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-261">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="1d8cf-262">Apps und Dienste, die die neuen Vertraulichkeitsbezeichnungen unterstützen, werden mit den neuen Bezeichnungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-262">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="1d8cf-263">Wenn Benutzer Gruppen aus Apps und Diensten erstellen, die die neuen Bezeichnungen nicht unterstützen, können sie eine Klassifizierung auswählen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-263">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="1d8cf-264">Sie verwenden bereits Vertraulichkeitsbezeichnungen (einheitliche Microsoft Information Protection-Bezeichnungen) für Dateien und E-Mail</span><span class="sxs-lookup"><span data-stu-id="1d8cf-264">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="1d8cf-265">Nachdem Sie diese Vorschau aktiviert haben, wechseln Sie zu den einzelnen Bezeichnungen im Microsoft 365 Compliance Center, und wenden Sie die gewünschten Richtlinien für Websites und Gruppen an.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-265">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="1d8cf-266">Benutzer sehen nun Ihre vorhandenen Bezeichnungen, die für Websites und Gruppen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-266">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="1d8cf-267">Vorbereiten der SharePoint Online-Verwaltungsshell vor dem Anwenden neuer Bezeichnungen auf Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="1d8cf-267">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="1d8cf-268">Bevor Sie neue Bezeichnungen anwenden, stellen Sie sicher, dass Sie die neueste SharePoint Online-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-268">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="1d8cf-269">Wenn Sie bereits über die neueste Version verfügen, können Sie fortfahren und [Office 365-Gruppen neue Vertraulichkeitsbezeichnungen zuweisen](#relabel-office-365-groups-with-new-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-269">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="1d8cf-270">So bereiten Sie die SharePoint Online-Verwaltungsshell für die Vorschau vor</span><span class="sxs-lookup"><span data-stu-id="1d8cf-270">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="1d8cf-271">Wenn Sie eine frühere Version der SharePoint Online-Verwaltungsshell installiert haben, wechseln Sie zu **Software hinzufügen oder entfernen**, und deinstallieren Sie die "SharePoint Online-Verwaltungsshell".</span><span class="sxs-lookup"><span data-stu-id="1d8cf-271">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="1d8cf-272">Wechseln Sie in einem Webbrowser zur Download Center-Seite, und [laden Sie die neueste SharePoint Online-Verwaltungsshell herunter](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-272">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="1d8cf-273">Wählen Sie die gewünschte Sprache aus, und klicken Sie auf **Download**.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-273">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="1d8cf-274">Wählen Sie zwischen der x64- und der x86-Version der MSI-Datei aus.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-274">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="1d8cf-275">Laden Sie die x64-Datei herunter, wenn Sie die 64-Bit-Version von Windows ausführen, bzw. die x86-Datei, wenn Sie die 32-Bit-Version ausführen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-275">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="1d8cf-276">Wenn Sie sich nicht sicher sind, ziehen Sie [Welche Version des Windows-Betriebssystems verwende ich?](https://support.microsoft.com/help/13443/windows-which-operating-system) zurate.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-276">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="1d8cf-277">Nachdem Sie die Datei heruntergeladen haben, führen Sie sie aus, und folgen Sie den Schritten im Setup-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-277">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="1d8cf-278">Zuweisen der neuen Vertraulichkeitsbezeichnungen zu Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="1d8cf-278">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="1d8cf-279">Stellen Sie sicher, dass Sie die neueste Version der SharePoint Online-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-279">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="1d8cf-280">Anweisungen finden Sie unter [Vorbereiten der SharePoint Online-Verwaltungsshell vor dem Anwenden neuer Bezeichnungen auf Office 365-Gruppen](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-280">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="1d8cf-281">Stellen Sie unter Verwendung eines Geschäfts-, Schul- oder Unikontos, das über globale Administrator- oder SharePoint-Administratorberechtigungen in Office 365 verfügt, eine Verbindung mit der SharePoint Online-Verwaltungsshell her.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-281">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="1d8cf-282">Eine Anleitung dazu finden Sie unter [Erste Schritte mit der SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="1d8cf-282">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="1d8cf-283">Führen Sie den folgenden Befehl aus, um die Liste der Vertraulichkeitsbezeichnungen und deren GUIDs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-283">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="1d8cf-284">Notieren Sie sich die GUID für die Bezeichnung, die Sie überschreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-284">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="1d8cf-285">Beispielsweise die Bezeichnung "Allgemein".</span><span class="sxs-lookup"><span data-stu-id="1d8cf-285">For example, the "General" label.</span></span>

5. <span data-ttu-id="1d8cf-286">Verwenden Sie den folgenden Befehl, um die Liste der Gruppen abzurufen, die die Klassifizierung "Allgemein" aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-286">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="1d8cf-287">Wenn Sie diesen Befehl ausführen, stellen Sie eine Verbindung mit Exchange Online PowerShell her und führen das Cmdlet "Get-UnifiedGroup" aus.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-287">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="1d8cf-288">Fügen Sie für jede Gruppe die neue Vertraulichkeitsbezeichnungs-GUID hinzu.</span><span class="sxs-lookup"><span data-stu-id="1d8cf-288">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
