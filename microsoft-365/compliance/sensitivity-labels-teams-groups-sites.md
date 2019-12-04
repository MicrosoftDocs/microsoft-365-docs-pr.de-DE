---
title: Verwenden von Sensitivitäts Bezeichnungen mit Microsoft Teams, Office 365 Gruppen und SharePoint-Websites (öffentliche Vorschau)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Sie können Bezeichnungen auf Microsoft Teams, Office 365 Gruppen und SharePoint-Websites anwenden.
ms.openlocfilehash: 72bdfef27ba20fabb0d59852e4e20425b2747425
ms.sourcegitcommit: 99d759d5c4e7d81266c3ebc087eaa37486cc0bc1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "39818837"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="98ce1-103">Verwenden von Sensitivitäts Bezeichnungen mit Microsoft Teams, Office 365 Gruppen und SharePoint-Websites (öffentliche Vorschau)</span><span class="sxs-lookup"><span data-stu-id="98ce1-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="98ce1-104">Wenn Sie Sensitivitäts Bezeichnungen im [Microsoft 365 Compliance Center](https://protection.office.com/)erstellen, können Sie diese nun auf Microsoft Teams, Office 365 Gruppen und SharePoint-Websites anwenden.</span><span class="sxs-lookup"><span data-stu-id="98ce1-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="98ce1-105">Sie können den Beschriftungen Richtlinien zuordnen, um Sie zu steuern:</span><span class="sxs-lookup"><span data-stu-id="98ce1-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="98ce1-106">Öffentliche/private Einstellungen</span><span class="sxs-lookup"><span data-stu-id="98ce1-106">Public/private settings</span></span>
- <span data-ttu-id="98ce1-107">Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="98ce1-107">Guest access</span></span>
- <span data-ttu-id="98ce1-108">Zugriff von nicht verwalteten Geräten</span><span class="sxs-lookup"><span data-stu-id="98ce1-108">Access from unmanaged devices</span></span>

<span data-ttu-id="98ce1-109">Wenn Sie eine Bezeichnung auf ein Team oder eine Gruppe anwenden, gilt die Bezeichnung automatisch für die verbundene SharePoint-Teamwebsite und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="98ce1-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="98ce1-110">Nun können Sie auch Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktivieren.</span><span class="sxs-lookup"><span data-stu-id="98ce1-110">Now, You can also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="98ce1-111">[Weitere Informationen](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="98ce1-111">[Learn more](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="98ce1-112">Informationen zur öffentlichen Vorschau für Microsoft Teams, Office 365 Gruppen und SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="98ce1-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="98ce1-113">Vertraulichkeits Bezeichnungen für Microsoft Teams, Office 365 Gruppen und SharePoint-Websites werden schrittweise für Mandanten bereitgestellt und können vor der endgültigen Version geändert werden.</span><span class="sxs-lookup"><span data-stu-id="98ce1-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites is gradually rolling out to tenants and might change before final release.</span></span>

<span data-ttu-id="98ce1-114">Die öffentliche Vorschau funktioniert nicht mit Office 365 Inhalts Zustellungs Netzwerken (CDNs).</span><span class="sxs-lookup"><span data-stu-id="98ce1-114">The public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="overview"></a><span data-ttu-id="98ce1-115">Übersicht</span><span class="sxs-lookup"><span data-stu-id="98ce1-115">Overview</span></span>

<span data-ttu-id="98ce1-116">Wenn Sie Vertraulichkeits Bezeichnungen veröffentlichen, haben Benutzer in Office 365 Zugriff auf dieselbe Liste von Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-116">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="98ce1-117">Diese Bilder zeigen:</span><span class="sxs-lookup"><span data-stu-id="98ce1-117">These images show:</span></span>

- <span data-ttu-id="98ce1-118">Wie die Liste angezeigt wird, wenn Sie eine neue Teamwebsite aus SharePoint erstellen</span><span class="sxs-lookup"><span data-stu-id="98ce1-118">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="98ce1-119">Wenn Sie die Liste in Word anzeigen</span><span class="sxs-lookup"><span data-stu-id="98ce1-119">When you view the list in Word</span></span>

![Eine Vertraulichkeits Bezeichnung beim Erstellen einer Teamwebsite aus SharePoint](media/sensitivity-label-new-team-site.png)

![Eine Vertraulichkeits Bezeichnung, die in der Word-Desktop-App angezeigt wird](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a><span data-ttu-id="98ce1-122">Aktivieren dieser Vorschau mithilfe von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ce1-122">Enable this preview by using Azure PowerShell</span></span>

1. <span data-ttu-id="98ce1-123">Melden Sie sich mit Azure PowerShell als globaler Administrator bei Azure an.</span><span class="sxs-lookup"><span data-stu-id="98ce1-123">Sign in to Azure as a global admin by using Azure PowerShell.</span></span> <span data-ttu-id="98ce1-124">Anweisungen finden Sie unter [Anmelden mit Azure PowerShell](/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="98ce1-124">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="98ce1-125">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="98ce1-125">Run the following command:</span></span>

```powershell
  Connect-AzureAD
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

<span data-ttu-id="98ce1-126">Office 365 verwendet die alten Klassifizierungen für neue Gruppen und SharePoint-Websites nicht mehr, wenn Sie diese Vorschau aktivieren.</span><span class="sxs-lookup"><span data-stu-id="98ce1-126">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="98ce1-127">Wenn Sie [Azure AD Site Klassifizierung](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($Setting ["classificationlist"]) verwendet haben, zeigen vorhandene Gruppen und Websites weiterhin die alten Klassifizierungen an.</span><span class="sxs-lookup"><span data-stu-id="98ce1-127">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="98ce1-128">Um die neuen Klassifizierungen anzuzeigen, konvertieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="98ce1-128">To display the new classifications, convert them.</span></span> <span data-ttu-id="98ce1-129">Informationen zum Konvertieren dieser Website finden Sie unter [Wenn Sie klassische Azure AD Site Klassifizierung verwendet](#if-you-used-classic-azure-ad-site-classification)haben.</span><span class="sxs-lookup"><span data-stu-id="98ce1-129">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span>

## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="98ce1-130">Festlegen von Standort-und Gruppeneinstellungen beim Erstellen (oder bearbeiten) von Sensitivitäts Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="98ce1-130">Set site and group settings when you create (or edit) sensitivity labels</span></span>

<span data-ttu-id="98ce1-131">Nachdem Sie die Vorschau aktiviert haben, führen Sie die folgenden Schritte aus, um Sensitivitäts Bezeichnungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-131">After you enable the preview, follow these steps to create sensitivity labels.</span></span> <span data-ttu-id="98ce1-132">Änderungen an diesen Einstellungen können bis zu 24 Stunden synchron dauern.</span><span class="sxs-lookup"><span data-stu-id="98ce1-132">Changes to these settings may take up to 24 hours sync.</span></span>

1. <span data-ttu-id="98ce1-133">Wählen Sie im Microsoft 365 Compliance Center **Klassifizierungs** > **Sensitivitäts Bezeichnungen**aus.</span><span class="sxs-lookup"><span data-stu-id="98ce1-133">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="98ce1-134">Wählen Sie **Beschriftung erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="98ce1-134">Select **Create a label**.</span></span>

3. <span data-ttu-id="98ce1-135">Wählen Sie die gewünschten Optionen aus, und wählen Sie dann auf der Registerkarte **Website und Gruppeneinstellungen** Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="98ce1-135">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>

    - <span data-ttu-id="98ce1-136">Datenschutz (öffentlich/privat): Private bedeutet, dass nur genehmigte Mitglieder in Ihrer Organisation sehen können, was sich innerhalb der Gruppe befindet.</span><span class="sxs-lookup"><span data-stu-id="98ce1-136">Privacy (Public/Private): Private means only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="98ce1-137">Jeder andere in Ihrer Organisation kann nicht sehen, was in der Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="98ce1-137">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="98ce1-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98ce1-138">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="98ce1-139">Gastzugriff: Sie können steuern, ob Gäste zu einer Gruppe hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="98ce1-139">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="98ce1-140">Informationen zum Verwalten des Gastzugriffs in Office 365 Gruppen</span><span class="sxs-lookup"><span data-stu-id="98ce1-140">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="98ce1-141">Nicht verwaltete Geräte: mit dieser Einstellung können Sie den Zugriff auf SharePoint-Inhalte von Geräten blockieren oder begrenzen, die in InTune nicht mit Hybrid-AD verbunden oder kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="98ce1-141">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="98ce1-142">Wenn Sie nicht verwaltete Geräte auswählen, müssen Sie zu Azure AD gehen, um die Einrichtung der Richtlinie abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-142">If you select Unmanaged devices, you need to go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="98ce1-143">Informationen finden Sie unter [Steuern des Zugriffs von nicht verwalteten Geräten](/sharepoint/control-access-from-unmanaged-devices).</span><span class="sxs-lookup"><span data-stu-id="98ce1-143">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

![Die Registerkarte "Website" und "Gruppeneinstellungen"](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="98ce1-145">Nur die Standort-und Gruppeneinstellungen werden wirksam, wenn Sie eine Bezeichnung auf ein Team, eine Gruppe oder einen Standort anwenden.</span><span class="sxs-lookup"><span data-stu-id="98ce1-145">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="98ce1-146">Andere Einstellungen wie Verschlüsselung und Inhalts Markierung werden nicht auf alle Inhalte innerhalb des Teams, der Gruppe oder der Website angewendet.</span><span class="sxs-lookup"><span data-stu-id="98ce1-146">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span> <span data-ttu-id="98ce1-147">Wenn Sie eine Bezeichnung erstellen und die Einstellungen für die Website und die Gruppe nicht aktivieren, ist die Bezeichnung auch dann verfügbar, wenn Benutzer Teams, Gruppen und Websites erstellen, es wird jedoch nichts tun, wenn Benutzer Sie anwenden.</span><span class="sxs-lookup"><span data-stu-id="98ce1-147">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it won't do anything when users apply it.</span></span>

[<span data-ttu-id="98ce1-148">Informationen zum Veröffentlichen einer Vertraulichkeits Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="98ce1-148">Learn how to publish a sensitivity label</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="98ce1-149">Anwenden einer Vertraulichkeits Bezeichnung auf ein neues Team</span><span class="sxs-lookup"><span data-stu-id="98ce1-149">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="98ce1-150">Benutzer können Sensitivitäts Bezeichnungen auswählen, wenn Sie neue Teams in Microsoft Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-150">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="98ce1-151">Wenn Sie die Empfindlichkeitsstufe auswählen, ändert sich die Datenschutzeinstellung bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="98ce1-151">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="98ce1-152">Abhängig von der Einstellung für den Gastzugriff, die Sie für die Bezeichnung ausgewählt haben, können Benutzer Personen außerhalb der Organisation dem Team hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-152">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

![Die Datenschutzeinstellung beim Erstellen eines neuen Teams](media/privacy-setting-new-team.png)

<span data-ttu-id="98ce1-154">Nachdem Sie das Team erstellt haben, wird die Sensitivitäts Bezeichnung in der oberen rechten Ecke aller Kanäle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98ce1-154">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![Die Vertraulichkeits Bezeichnung wird im Team angezeigt.](media/privacy-setting-teams.png)

<span data-ttu-id="98ce1-156">Der Dienst wendet die gleiche Vertraulichkeits Bezeichnung automatisch auf die Office 365 Gruppe und die verbundene SharePoint-Teamwebsite an.</span><span class="sxs-lookup"><span data-stu-id="98ce1-156">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="98ce1-157">Anwenden einer Sensitivitäts Bezeichnung auf eine neue Gruppe</span><span class="sxs-lookup"><span data-stu-id="98ce1-157">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="98ce1-158">In Outlook im Internet enthält das Feld neue **Vertraulichkeit** veröffentlichte Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-158">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="98ce1-159">Wenn Benutzer weitere Informationen wünschen, können Sie auf das Hilfesymbol klicken, um Details zu den verfügbaren Bezeichnungen und zugehörigen Richtlinien zu lesen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-159">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![Erstellen einer Gruppe und Auswählen einer Option unter Sensitivität](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="98ce1-161">Anwenden einer Vertraulichkeits Bezeichnung auf eine neue Website</span><span class="sxs-lookup"><span data-stu-id="98ce1-161">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="98ce1-162">Administratoren und Endbenutzer können Sensitivitäts Bezeichnungen auswählen, wenn Sie moderne Teamwebsites und Kommunikationswebsites erstellen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-162">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="98ce1-163">Erfahren Sie, wie Sie eine Website im neuen SharePoint Admin Center erstellen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-163">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="98ce1-164">Wenn Benutzer moderne Team-und Kommunikationswebsites erstellen, ist standardmäßig bereits eine Vertraulichkeits Bezeichnung ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="98ce1-164">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="98ce1-165">Benutzer können das Hilfesymbol auswählen, um weitere Informationen zu den Beschriftungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="98ce1-165">Users can select the help icon to learn more about the labels.</span></span>

![Erstellen einer Website und Auswählen einer Option unter Vertraulichkeit](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="98ce1-167">Wenn Benutzer die Website durchsuchen, können Sie den Namen der Bezeichnung und die angewendeten Richtlinien anzeigen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-167">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Eine Website, auf der eine Vertraulichkeits Bezeichnung angewendet wurde](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="98ce1-169">Verwalten von Sensitivitäts Bezeichnungen im SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="98ce1-169">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="98ce1-170">Verwenden Sie zum Anzeigen und Bearbeiten der Bezeichnungen die Seite aktive Websites im neuen SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="98ce1-170">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![Die Spalte "Vertraulichkeit" auf der Seite "aktive Websites"](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="98ce1-172">[Erfahren Sie mehr über das Verwalten von Websites im neuen SharePoint Admin Center](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="98ce1-172">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="98ce1-173">Ändern von Standort-und Gruppeneinstellungen für eine Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="98ce1-173">Change site and group settings for a label</span></span>

<span data-ttu-id="98ce1-174">Als bewährte Methode sollten Sie die Einstellungen nicht ändern, nachdem Sie eine Bezeichnung auf mehrere Teams, Gruppen oder Websites angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="98ce1-174">As a best practice, don't change settings after you've applied a label to several teams, groups, or sites.</span></span> <span data-ttu-id="98ce1-175">Wenn Sie eine Änderung vornehmen müssen, müssen Sie ein Azure AD PowerShell-Skript verwenden, um Updates manuell zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-175">If you must make a change, you'll need to use an Azure AD PowerShell script to manually apply updates.</span></span> <span data-ttu-id="98ce1-176">Mit dieser Methode wird sichergestellt, dass alle vorhandenen Teams, Websites und Gruppen die neue Einstellung erzwingen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-176">This method ensures all existing teams, sites, and groups enforce the new setting.</span></span>

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="98ce1-177">Unterstützung für die neuen Sensitivitäts Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="98ce1-177">Support for the new sensitivity labels</span></span>

<span data-ttu-id="98ce1-178">Die folgenden apps und Dienste unterstützen die Sensitivitäts Bezeichnungen in dieser Vorschau:</span><span class="sxs-lookup"><span data-stu-id="98ce1-178">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="98ce1-179">Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="98ce1-179">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="98ce1-180">SharePoint</span><span class="sxs-lookup"><span data-stu-id="98ce1-180">SharePoint</span></span>
- <span data-ttu-id="98ce1-181">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="98ce1-181">Outlook on the web</span></span>
- <span data-ttu-id="98ce1-182">Teams</span><span class="sxs-lookup"><span data-stu-id="98ce1-182">Teams</span></span>
- <span data-ttu-id="98ce1-183">SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="98ce1-183">SharePoint admin center</span></span>
- <span data-ttu-id="98ce1-184">Azure AD Admin Center</span><span class="sxs-lookup"><span data-stu-id="98ce1-184">Azure AD admin center</span></span>

<span data-ttu-id="98ce1-185">Sie können die folgenden apps und Dienste nicht verwenden, um Office 365 Gruppen mit den neuen Vertraulichkeits Bezeichnungen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="98ce1-185">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="98ce1-186">Outlook für Mac</span><span class="sxs-lookup"><span data-stu-id="98ce1-186">Outlook for the Mac</span></span>
- <span data-ttu-id="98ce1-187">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="98ce1-187">Outlook mobile</span></span>  
- <span data-ttu-id="98ce1-188">Outlook-Desktop für Windows</span><span class="sxs-lookup"><span data-stu-id="98ce1-188">Outlook desktop for Windows</span></span>
- <span data-ttu-id="98ce1-189">Formulare</span><span class="sxs-lookup"><span data-stu-id="98ce1-189">Forms</span></span>  
- <span data-ttu-id="98ce1-190">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="98ce1-190">Dynamics 365</span></span>  
- <span data-ttu-id="98ce1-191">Yammer</span><span class="sxs-lookup"><span data-stu-id="98ce1-191">Yammer</span></span>  
- <span data-ttu-id="98ce1-192">Stream</span><span class="sxs-lookup"><span data-stu-id="98ce1-192">Stream</span></span>  
- <span data-ttu-id="98ce1-193">Planner</span><span class="sxs-lookup"><span data-stu-id="98ce1-193">Planner</span></span>  
- <span data-ttu-id="98ce1-194">Project</span><span class="sxs-lookup"><span data-stu-id="98ce1-194">Project</span></span>  
- <span data-ttu-id="98ce1-195">PowerBI</span><span class="sxs-lookup"><span data-stu-id="98ce1-195">PowerBI</span></span>  
- <span data-ttu-id="98ce1-196">Teams-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="98ce1-196">Teams admin center</span></span>  
- <span data-ttu-id="98ce1-197">Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="98ce1-197">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="98ce1-198">Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="98ce1-198">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="98ce1-199">Wenn Sie klassische Azure Ad Website Klassifizierung verwendet haben</span><span class="sxs-lookup"><span data-stu-id="98ce1-199">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="98ce1-200">Office 365 unterstützt die alten Klassifizierungen für neue Gruppen und SharePoint-Websites nicht mehr, wenn Sie diese Vorschau aktivieren.</span><span class="sxs-lookup"><span data-stu-id="98ce1-200">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="98ce1-201">Vorhandene Gruppen und Websites zeigen jedoch weiterhin die alten Klassifizierungen an, es sei denn, Sie konvertieren Sie.</span><span class="sxs-lookup"><span data-stu-id="98ce1-201">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="98ce1-202">Zu den alten Klassifizierungen gehören die von Ihnen festgelegte "moderne" Website Klassifizierung, möglicherweise über Azure AD PowerShell oder die PNP- `ClassificationList` Kernbibliothek, mit der die Werte für die Einstellung definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="98ce1-202">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="98ce1-203">Beispielsweise in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="98ce1-203">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="98ce1-204">Weitere Informationen zur alten Klassifizierungsmethode finden Sie unter [SharePoint "Modern" Site Classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="98ce1-204">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="98ce1-205">Basierend auf Ihrer aktuellen Bereitstellung haben Sie zwei Optionen, um Ihre alten Klassifizierungen in die neuen Klassifizierungen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="98ce1-205">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="98ce1-206">Wenn Sie für Dateien und e-Mails keine Sensitivitäts Bezeichnungen (Unified Microsoft Information Protection-Bezeichnungen) verwendet haben</span><span class="sxs-lookup"><span data-stu-id="98ce1-206">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="98ce1-207">Wir empfehlen, dass Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="98ce1-207">We recommend that you:</span></span>

1. <span data-ttu-id="98ce1-208">Erstellen Sie neue Sensitivitäts Bezeichnungen im Microsoft 365 Compliance Center mit den gleichen Namen wie Ihre vorhandenen Klassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-208">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="98ce1-209">Verwenden Sie PowerShell, um die neuen Bezeichnungen auf vorhandene Office 365 Gruppen und SharePoint-Websites mithilfe der Namenszuordnung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="98ce1-209">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="98ce1-210">Löschen Sie die alten Klassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-210">Delete the old classifications.</span></span>

<span data-ttu-id="98ce1-211">Apps und Dienste, die die neuen Sensitivitäts Bezeichnungen unterstützen, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98ce1-211">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="98ce1-212">Sie erstellen neue Teams, Gruppen und Websites mit den neuen Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-212">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="98ce1-213">Benutzer können weiterhin Gruppen aus apps und Diensten erstellen, die die neuen Bezeichnungen nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-213">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="98ce1-214">Benutzer können diese Gruppen jedoch nicht mit einer Bezeichnung versehen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-214">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="98ce1-215">Verwenden Sie PowerShell, um die neuen Vertraulichkeits Bezeichnungen auf diese Gruppen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="98ce1-215">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="98ce1-216">Sie können Ihre alten Klassifizierungen beibehalten. Es wird jedoch dringend empfohlen, die neuen Vertraulichkeits Bezeichnungen für diese Gruppen mithilfe von PowerShell anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="98ce1-216">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="98ce1-217">Apps und Dienste, die die neuen Sensitivitäts Bezeichnungen unterstützen, werden mit den neuen Beschriftungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="98ce1-217">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="98ce1-218">Wenn Benutzergruppen aus apps und Diensten erstellen, die die neuen Bezeichnungen nicht unterstützen, können Sie eine Klassifizierung auswählen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-218">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="98ce1-219">Wenn Sie für Dateien und e-Mails Vertraulichkeits Bezeichnungen (Unified Microsoft Information Protection-Bezeichnungen) verwenden</span><span class="sxs-lookup"><span data-stu-id="98ce1-219">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="98ce1-220">Sobald Sie diese Vorschau aktiviert haben, wechseln Sie zu jeder Bezeichnung im Microsoft 365 Compliance Center, und wenden Sie die gewünschten Richtlinien für Websites und Gruppen an.</span><span class="sxs-lookup"><span data-stu-id="98ce1-220">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="98ce1-221">Benutzer beginnen mit dem Anzeigen vorhandener Beschriftungen für Websites und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-221">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="98ce1-222">Vorbereiten der SharePoint Online Verwaltungsshell vor dem neuetikettieren von Office 365 Gruppen</span><span class="sxs-lookup"><span data-stu-id="98ce1-222">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="98ce1-223">Vergewissern Sie sich vor dem Anwenden neuer Bezeichnungen, dass Sie die neueste SharePoint Online-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-223">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="98ce1-224">Wenn Sie bereits über die neueste Version verfügen, können Sie [Office 365 Gruppen mit neuen Sensitivitäts Bezeichnungen neu bezeichnen](#relabel-office-365-groups-with-new-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="98ce1-224">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="98ce1-225">So bereiten Sie die SharePoint Online Management-Shell für die Vorschau vor:</span><span class="sxs-lookup"><span data-stu-id="98ce1-225">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="98ce1-226">Wenn Sie eine frühere Version der SharePoint Online-Verwaltungsshell installiert haben, wechseln Sie zu **Software hinzufügen oder entfernen** , und deinstallieren Sie "SharePoint Online Verwaltungsshell".</span><span class="sxs-lookup"><span data-stu-id="98ce1-226">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="98ce1-227">Wechseln Sie in einem Webbrowser zur Seite Download Center, und [Laden Sie die neueste SharePoint Online Verwaltungsshell herunter](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="98ce1-227">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="98ce1-228">Wählen Sie Ihre Sprache aus, und klicken Sie dann auf **herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="98ce1-228">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="98ce1-229">Wählen Sie zwischen der Datei x64 und x86. msi aus.</span><span class="sxs-lookup"><span data-stu-id="98ce1-229">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="98ce1-230">Laden Sie die x64-Datei herunter, wenn Sie die 64-Bit-Version von Windows oder die x86-Datei ausführen, wenn Sie die 32-Bit-Version ausführen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-230">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="98ce1-231">Wenn Sie nicht wissen, finden Sie unter [welche Version des Windows-Betriebssystems soll ich ausführen?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="98ce1-231">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="98ce1-232">Nachdem Sie die Datei heruntergeladen haben, führen Sie die Datei aus, und führen Sie die Schritte im Setup-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="98ce1-232">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="98ce1-233">Neuetikettieren von Office 365 Gruppen mit neuen Sensitivitäts Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="98ce1-233">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="98ce1-234">Stellen Sie sicher, dass Sie die neueste Version der SharePoint Online Management-Shell verwenden.</span><span class="sxs-lookup"><span data-stu-id="98ce1-234">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="98ce1-235">Anweisungen finden Sie unter [Prepare the SharePoint Online Management Shell, bevor Sie Office 365 Gruppen umetikettieren](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="98ce1-235">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="98ce1-236">Stellen Sie mithilfe eines Geschäfts-oder Schul Kontos mit globalen Administrator-oder SharePoint-Administratorrechten in Office 365 eine Verbindung mit SharePoint Online Verwaltungsshell her.</span><span class="sxs-lookup"><span data-stu-id="98ce1-236">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="98ce1-237">Eine Anleitung dazu finden Sie unter [Erste Schritte mit der SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="98ce1-237">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="98ce1-238">Führen Sie den folgenden Befehl aus, um die Liste der Vertraulichkeits Bezeichnungen und deren GUIDs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-238">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="98ce1-239">Notieren Sie sich die GUID für die Bezeichnung, die Sie überschreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="98ce1-239">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="98ce1-240">Beispielsweise die Bezeichnung "Allgemein".</span><span class="sxs-lookup"><span data-stu-id="98ce1-240">For example, the "General" label.</span></span>

5. <span data-ttu-id="98ce1-241">Verwenden Sie den folgenden Befehl, um die Liste der Gruppen abzurufen, die die "allgemeine" Klassifizierung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="98ce1-241">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="98ce1-242">Wenn Sie diesen Befehl ausführen, stellen Sie eine Verbindung mit Exchange Online PowerShell her und führen das Cmdlet Get-Unifiedgroup aus.</span><span class="sxs-lookup"><span data-stu-id="98ce1-242">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. <span data-ttu-id="98ce1-243">Fügen Sie für jede Gruppe die neue GUID der Sensitivitäts Bezeichnung hinzu.</span><span class="sxs-lookup"><span data-stu-id="98ce1-243">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
