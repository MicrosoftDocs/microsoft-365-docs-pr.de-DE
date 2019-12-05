---
title: Verwenden von Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites (öffentliche Vorschau)
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
ms.openlocfilehash: ebe5e00c3458782e1874274cb508326968461ce3
ms.sourcegitcommit: 1bd81cf48c7fab1b8aaf7c3f550ce42ab02136dc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "39822491"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="136f0-103">Verwenden von Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites (öffentliche Vorschau)</span><span class="sxs-lookup"><span data-stu-id="136f0-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="136f0-104">Wenn Sie Sensitivitäts Bezeichnungen im [Microsoft 365 Compliance Center](https://protection.office.com/)erstellen, können Sie diese nun auf Microsoft Teams, Office 365 Gruppen und SharePoint-Websites anwenden.</span><span class="sxs-lookup"><span data-stu-id="136f0-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="136f0-105">Sie können den Beschriftungen Richtlinien zuordnen, um Sie zu steuern:</span><span class="sxs-lookup"><span data-stu-id="136f0-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="136f0-106">Öffentliche/private Einstellungen</span><span class="sxs-lookup"><span data-stu-id="136f0-106">Public/private settings</span></span>
- <span data-ttu-id="136f0-107">Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="136f0-107">Guest access</span></span>
- <span data-ttu-id="136f0-108">Zugriff von nicht verwalteten Geräten</span><span class="sxs-lookup"><span data-stu-id="136f0-108">Access from unmanaged devices</span></span>

<span data-ttu-id="136f0-109">Wenn Sie eine Bezeichnung auf ein Team oder eine Gruppe anwenden, gilt die Bezeichnung automatisch für die verbundene SharePoint-Teamwebsite und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="136f0-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="136f0-110">Nun können Sie auch Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktivieren.</span><span class="sxs-lookup"><span data-stu-id="136f0-110">Now, You can also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="136f0-111">[Weitere Informationen](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="136f0-111">[Learn more](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="136f0-112">Informationen zur öffentlichen Vorschau für Microsoft Teams, Office 365 Gruppen und SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="136f0-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="136f0-113">Vertraulichkeits Bezeichnungen für Microsoft Teams, Office 365 Gruppen und SharePoint-Websites werden schrittweise für Mandanten bereitgestellt und können vor der endgültigen Version geändert werden.</span><span class="sxs-lookup"><span data-stu-id="136f0-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites is gradually rolling out to tenants and might change before final release.</span></span>

<span data-ttu-id="136f0-114">Die öffentliche Vorschau funktioniert nicht mit Office 365 Inhalts Zustellungs Netzwerken (CDNs).</span><span class="sxs-lookup"><span data-stu-id="136f0-114">The public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="overview"></a><span data-ttu-id="136f0-115">Übersicht</span><span class="sxs-lookup"><span data-stu-id="136f0-115">Overview</span></span>

<span data-ttu-id="136f0-116">Wenn Sie Vertraulichkeits Bezeichnungen veröffentlichen, haben Benutzer in Office 365 Zugriff auf dieselbe Liste von Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="136f0-116">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="136f0-117">Diese Bilder zeigen:</span><span class="sxs-lookup"><span data-stu-id="136f0-117">These images show:</span></span>

- <span data-ttu-id="136f0-118">Wie die Liste angezeigt wird, wenn Sie eine neue Teamwebsite aus SharePoint erstellen</span><span class="sxs-lookup"><span data-stu-id="136f0-118">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="136f0-119">Wenn Sie die Liste in Word anzeigen</span><span class="sxs-lookup"><span data-stu-id="136f0-119">When you view the list in Word</span></span>

![Eine Vertraulichkeits Bezeichnung beim Erstellen einer Teamwebsite aus SharePoint](media/sensitivity-label-new-team-site.png)

![Eine Vertraulichkeits Bezeichnung, die in der Word-Desktop-App angezeigt wird](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a><span data-ttu-id="136f0-122">Aktivieren dieser Vorschau mithilfe von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="136f0-122">Enable this preview by using Azure PowerShell</span></span>

1. <span data-ttu-id="136f0-123">Melden Sie sich mit Azure PowerShell als globaler Administrator bei Azure an.</span><span class="sxs-lookup"><span data-stu-id="136f0-123">Sign in to Azure as a global admin by using Azure PowerShell.</span></span> <span data-ttu-id="136f0-124">Anweisungen finden Sie unter [Anmelden mit Azure PowerShell](/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="136f0-124">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="136f0-125">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="136f0-125">Run the following command:</span></span>

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

<span data-ttu-id="136f0-126">Office 365 verwendet die alten Klassifizierungen für neue Gruppen und SharePoint-Websites nicht mehr, wenn Sie diese Vorschau aktivieren.</span><span class="sxs-lookup"><span data-stu-id="136f0-126">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="136f0-127">Wenn Sie [Azure AD Site Klassifizierung](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($Setting ["classificationlist"]) verwendet haben, zeigen vorhandene Gruppen und Websites weiterhin die alten Klassifizierungen an.</span><span class="sxs-lookup"><span data-stu-id="136f0-127">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="136f0-128">Um die neuen Klassifizierungen anzuzeigen, konvertieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="136f0-128">To display the new classifications, convert them.</span></span> <span data-ttu-id="136f0-129">Informationen zum Konvertieren dieser Website finden Sie unter [Wenn Sie klassische Azure AD Site Klassifizierung verwendet](#if-you-used-classic-azure-ad-site-classification)haben.</span><span class="sxs-lookup"><span data-stu-id="136f0-129">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span> 

## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="136f0-130">Festlegen von Standort-und Gruppeneinstellungen beim Erstellen oder Bearbeiten von Vertraulichkeits Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="136f0-130">Set site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="136f0-131">Nachdem Sie die Vorschau aktiviert haben, führen Sie die folgenden Schritte aus, um Vertraulichkeits Bezeichnungen zu erstellen oder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="136f0-131">After you enable the preview, follow these steps to create or edit sensitivity labels.</span></span> <span data-ttu-id="136f0-132">Sie müssen diese Schritte ausführen, damit die neuen Sensitivitäts Bezeichnungen mit Websites und Gruppen arbeiten können, auch wenn bereits Beschriftungen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="136f0-132">You must complete these steps for the new sensitivity labels to work with sites and groups, even if you already have labels defined.</span></span> <span data-ttu-id="136f0-133">Änderungen an diesen Einstellungen können bis zu 24 Stunden synchron dauern.</span><span class="sxs-lookup"><span data-stu-id="136f0-133">Changes to these settings may take up to 24 hours sync.</span></span>

1. <span data-ttu-id="136f0-134">Wählen Sie im Microsoft 365 Compliance Center **Klassifizierungs** > **Sensitivitäts Bezeichnungen**aus.</span><span class="sxs-lookup"><span data-stu-id="136f0-134">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="136f0-135">Wählen Sie **Beschriftung erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="136f0-135">Select **Create a label**.</span></span> <span data-ttu-id="136f0-136">Wenn Sie bereits über eine Bezeichnung verfügen, fahren Sie mit dem nächsten Schritt fort.</span><span class="sxs-lookup"><span data-stu-id="136f0-136">If you already have a label, skip to the next step.</span></span>

3. <span data-ttu-id="136f0-137">Wählen Sie die gewünschten Optionen aus, und wählen Sie dann auf der Registerkarte **Website und Gruppeneinstellungen** Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="136f0-137">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>

    - <span data-ttu-id="136f0-138">Datenschutz (öffentlich/privat): Private bedeutet, dass nur genehmigte Mitglieder in Ihrer Organisation sehen können, was sich innerhalb der Gruppe befindet.</span><span class="sxs-lookup"><span data-stu-id="136f0-138">Privacy (Public/Private): Private means only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="136f0-139">Jeder andere in Ihrer Organisation kann nicht sehen, was in der Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="136f0-139">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="136f0-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="136f0-140">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="136f0-141">Gastzugriff: Sie können steuern, ob Gäste zu einer Gruppe hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="136f0-141">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="136f0-142">Informationen zum Verwalten des Gastzugriffs in Office 365 Gruppen</span><span class="sxs-lookup"><span data-stu-id="136f0-142">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="136f0-143">Nicht verwaltete Geräte: mit dieser Einstellung können Sie den Zugriff auf SharePoint-Inhalte von Geräten blockieren oder begrenzen, die in InTune nicht mit Hybrid-AD verbunden oder kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="136f0-143">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="136f0-144">Wenn Sie nicht verwaltete Geräte auswählen, müssen Sie zu Azure AD gehen, um die Einrichtung der Richtlinie abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="136f0-144">If you select Unmanaged devices, you need to go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="136f0-145">Informationen finden Sie unter [Steuern des Zugriffs von nicht verwalteten Geräten](/sharepoint/control-access-from-unmanaged-devices).</span><span class="sxs-lookup"><span data-stu-id="136f0-145">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

![Die Registerkarte "Website" und "Gruppeneinstellungen"](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="136f0-147">Nur die Standort-und Gruppeneinstellungen werden wirksam, wenn Sie eine Bezeichnung auf ein Team, eine Gruppe oder einen Standort anwenden.</span><span class="sxs-lookup"><span data-stu-id="136f0-147">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="136f0-148">Andere Einstellungen wie Verschlüsselung und Inhalts Markierung werden nicht auf alle Inhalte innerhalb des Teams, der Gruppe oder der Website angewendet.</span><span class="sxs-lookup"><span data-stu-id="136f0-148">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span> <span data-ttu-id="136f0-149">Wenn Sie eine Bezeichnung erstellen und die Einstellungen für die Website und die Gruppe nicht aktivieren, ist die Bezeichnung auch dann verfügbar, wenn Benutzer Teams, Gruppen und Websites erstellen, es wird jedoch nichts tun, wenn Benutzer Sie anwenden.</span><span class="sxs-lookup"><span data-stu-id="136f0-149">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it won't do anything when users apply it.</span></span>

[<span data-ttu-id="136f0-150">Informationen zum Veröffentlichen einer Vertraulichkeits Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="136f0-150">Learn how to publish a sensitivity label</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="136f0-151">Problembehandlung bei der Sensitivitäts Bezeichnungs Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="136f0-151">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="136f0-152">Wenn beim Erstellen eines Teams oder Office 365 Gruppe Probleme auftreten, nachdem Sie diese Einstellungen aktiviert oder die Beschreibung einer Sensitivitäts Bezeichnung geändert haben, speichern Sie die Beschriftung, warten Sie einige Stunden, und versuchen Sie dann erneut, das Team oder die Office 365 Gruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="136f0-152">If you experience issues when you create a Teams or Office 365 group after you enable these settings or make a change to a sensitivity label's description, save the label, wait a few hours, and then try to create the Team or Office 365 group again.</span></span>

<span data-ttu-id="136f0-153">Wenn Sie die neue Sensitivitäts Bezeichnung immer noch nicht in SharePoint Online sehen können, wenden Sie sich umgehend an den Microsoft-Support.</span><span class="sxs-lookup"><span data-stu-id="136f0-153">If you are still not able to see the new sensitivity label from SharePoint Online, then contact Microsoft Support immediately.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="136f0-154">Anwenden einer Vertraulichkeits Bezeichnung auf ein neues Team</span><span class="sxs-lookup"><span data-stu-id="136f0-154">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="136f0-155">Benutzer können Sensitivitäts Bezeichnungen auswählen, wenn Sie neue Teams in Microsoft Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="136f0-155">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="136f0-156">Wenn Sie die Empfindlichkeitsstufe auswählen, ändert sich die Datenschutzeinstellung bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="136f0-156">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="136f0-157">Abhängig von der Einstellung für den Gastzugriff, die Sie für die Bezeichnung ausgewählt haben, können Benutzer Personen außerhalb der Organisation dem Team hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="136f0-157">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

![Die Datenschutzeinstellung beim Erstellen eines neuen Teams](media/privacy-setting-new-team.png)

<span data-ttu-id="136f0-159">Nachdem Sie das Team erstellt haben, wird die Sensitivitäts Bezeichnung in der oberen rechten Ecke aller Kanäle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="136f0-159">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![Die Vertraulichkeits Bezeichnung wird im Team angezeigt.](media/privacy-setting-teams.png)

<span data-ttu-id="136f0-161">Der Dienst wendet die gleiche Vertraulichkeits Bezeichnung automatisch auf die Office 365 Gruppe und die verbundene SharePoint-Teamwebsite an.</span><span class="sxs-lookup"><span data-stu-id="136f0-161">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="136f0-162">Anwenden einer Sensitivitäts Bezeichnung auf eine neue Gruppe</span><span class="sxs-lookup"><span data-stu-id="136f0-162">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="136f0-163">In Outlook im Internet enthält das Feld neue **Vertraulichkeit** veröffentlichte Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="136f0-163">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="136f0-164">Wenn Benutzer weitere Informationen wünschen, können Sie auf das Hilfesymbol klicken, um Details zu den verfügbaren Bezeichnungen und zugehörigen Richtlinien zu lesen.</span><span class="sxs-lookup"><span data-stu-id="136f0-164">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![Erstellen einer Gruppe und Auswählen einer Option unter Sensitivität](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="136f0-166">Anwenden einer Vertraulichkeits Bezeichnung auf eine neue Website</span><span class="sxs-lookup"><span data-stu-id="136f0-166">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="136f0-167">Administratoren und Endbenutzer können Sensitivitäts Bezeichnungen auswählen, wenn Sie moderne Teamwebsites und Kommunikationswebsites erstellen.</span><span class="sxs-lookup"><span data-stu-id="136f0-167">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="136f0-168">Erfahren Sie, wie Sie eine Website im neuen SharePoint Admin Center erstellen.</span><span class="sxs-lookup"><span data-stu-id="136f0-168">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="136f0-169">Wenn Benutzer moderne Team-und Kommunikationswebsites erstellen, ist standardmäßig bereits eine Vertraulichkeits Bezeichnung ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="136f0-169">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="136f0-170">Benutzer können das Hilfesymbol auswählen, um weitere Informationen zu den Beschriftungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="136f0-170">Users can select the help icon to learn more about the labels.</span></span>

![Erstellen einer Website und Auswählen einer Option unter Vertraulichkeit](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="136f0-172">Wenn Benutzer die Website durchsuchen, können Sie den Namen der Bezeichnung und die angewendeten Richtlinien anzeigen.</span><span class="sxs-lookup"><span data-stu-id="136f0-172">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Eine Website, auf der eine Vertraulichkeits Bezeichnung angewendet wurde](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="136f0-174">Verwalten von Sensitivitäts Bezeichnungen im SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="136f0-174">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="136f0-175">Verwenden Sie zum Anzeigen und Bearbeiten der Bezeichnungen die Seite aktive Websites im neuen SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="136f0-175">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![Die Spalte "Vertraulichkeit" auf der Seite "aktive Websites"](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="136f0-177">[Erfahren Sie mehr über das Verwalten von Websites im neuen SharePoint Admin Center](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="136f0-177">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="136f0-178">Ändern von Standort-und Gruppeneinstellungen für eine Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="136f0-178">Change site and group settings for a label</span></span>

<span data-ttu-id="136f0-179">Als bewährte Methode sollten Sie die Einstellungen nicht ändern, nachdem Sie eine Bezeichnung auf mehrere Teams, Gruppen oder Websites angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="136f0-179">As a best practice, don't change settings after you've applied a label to several teams, groups, or sites.</span></span> <span data-ttu-id="136f0-180">Wenn Sie eine Änderung vornehmen müssen, müssen Sie ein Azure AD PowerShell-Skript verwenden, um Updates manuell zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="136f0-180">If you must make a change, you'll need to use an Azure AD PowerShell script to manually apply updates.</span></span> <span data-ttu-id="136f0-181">Mit dieser Methode wird sichergestellt, dass alle vorhandenen Teams, Websites und Gruppen die neue Einstellung erzwingen.</span><span class="sxs-lookup"><span data-stu-id="136f0-181">This method ensures all existing teams, sites, and groups enforce the new setting.</span></span>

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="136f0-182">Unterstützung für die neuen Sensitivitäts Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="136f0-182">Support for the new sensitivity labels</span></span>

<span data-ttu-id="136f0-183">Die folgenden apps und Dienste unterstützen die Sensitivitäts Bezeichnungen in dieser Vorschau:</span><span class="sxs-lookup"><span data-stu-id="136f0-183">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="136f0-184">Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="136f0-184">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="136f0-185">SharePoint</span><span class="sxs-lookup"><span data-stu-id="136f0-185">SharePoint</span></span>
- <span data-ttu-id="136f0-186">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="136f0-186">Outlook on the web</span></span>
- <span data-ttu-id="136f0-187">Teams</span><span class="sxs-lookup"><span data-stu-id="136f0-187">Teams</span></span>
- <span data-ttu-id="136f0-188">SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="136f0-188">SharePoint admin center</span></span>
- <span data-ttu-id="136f0-189">Azure AD Admin Center</span><span class="sxs-lookup"><span data-stu-id="136f0-189">Azure AD admin center</span></span>

<span data-ttu-id="136f0-190">Sie können die folgenden apps und Dienste nicht verwenden, um Office 365 Gruppen mit den neuen Vertraulichkeits Bezeichnungen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="136f0-190">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="136f0-191">Outlook für Mac</span><span class="sxs-lookup"><span data-stu-id="136f0-191">Outlook for the Mac</span></span>
- <span data-ttu-id="136f0-192">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="136f0-192">Outlook mobile</span></span>  
- <span data-ttu-id="136f0-193">Outlook-Desktop für Windows</span><span class="sxs-lookup"><span data-stu-id="136f0-193">Outlook desktop for Windows</span></span>
- <span data-ttu-id="136f0-194">Formulare</span><span class="sxs-lookup"><span data-stu-id="136f0-194">Forms</span></span>  
- <span data-ttu-id="136f0-195">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="136f0-195">Dynamics 365</span></span>  
- <span data-ttu-id="136f0-196">Yammer</span><span class="sxs-lookup"><span data-stu-id="136f0-196">Yammer</span></span>  
- <span data-ttu-id="136f0-197">Stream</span><span class="sxs-lookup"><span data-stu-id="136f0-197">Stream</span></span>  
- <span data-ttu-id="136f0-198">Planner</span><span class="sxs-lookup"><span data-stu-id="136f0-198">Planner</span></span>  
- <span data-ttu-id="136f0-199">Project</span><span class="sxs-lookup"><span data-stu-id="136f0-199">Project</span></span>  
- <span data-ttu-id="136f0-200">PowerBI</span><span class="sxs-lookup"><span data-stu-id="136f0-200">PowerBI</span></span>  
- <span data-ttu-id="136f0-201">Teams-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="136f0-201">Teams admin center</span></span>  
- <span data-ttu-id="136f0-202">Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="136f0-202">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="136f0-203">Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="136f0-203">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="136f0-204">Wenn Sie klassische Azure Ad Website Klassifizierung verwendet haben</span><span class="sxs-lookup"><span data-stu-id="136f0-204">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="136f0-205">Office 365 unterstützt die alten Klassifizierungen für neue Gruppen und SharePoint-Websites nicht mehr, wenn Sie diese Vorschau aktivieren.</span><span class="sxs-lookup"><span data-stu-id="136f0-205">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="136f0-206">Vorhandene Gruppen und Websites zeigen jedoch weiterhin die alten Klassifizierungen an, es sei denn, Sie konvertieren Sie.</span><span class="sxs-lookup"><span data-stu-id="136f0-206">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="136f0-207">Zu den alten Klassifizierungen gehören die von Ihnen festgelegte "moderne" Website Klassifizierung, möglicherweise über Azure AD PowerShell oder die PNP- `ClassificationList` Kernbibliothek, mit der die Werte für die Einstellung definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="136f0-207">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="136f0-208">Beispielsweise in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="136f0-208">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="136f0-209">Weitere Informationen zur alten Klassifizierungsmethode finden Sie unter [SharePoint "Modern" Site Classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="136f0-209">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="136f0-210">Basierend auf Ihrer aktuellen Bereitstellung haben Sie zwei Optionen, um Ihre alten Klassifizierungen in die neuen Klassifizierungen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="136f0-210">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="136f0-211">Wenn Sie für Dateien und e-Mails keine Sensitivitäts Bezeichnungen (Unified Microsoft Information Protection-Bezeichnungen) verwendet haben</span><span class="sxs-lookup"><span data-stu-id="136f0-211">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="136f0-212">Wir empfehlen, dass Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="136f0-212">We recommend that you:</span></span>

1. <span data-ttu-id="136f0-213">Erstellen Sie neue Sensitivitäts Bezeichnungen im Microsoft 365 Compliance Center mit den gleichen Namen wie Ihre vorhandenen Klassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="136f0-213">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="136f0-214">Verwenden Sie PowerShell, um die neuen Bezeichnungen auf vorhandene Office 365 Gruppen und SharePoint-Websites mithilfe der Namenszuordnung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="136f0-214">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="136f0-215">Löschen Sie die alten Klassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="136f0-215">Delete the old classifications.</span></span>

<span data-ttu-id="136f0-216">Apps und Dienste, die die neuen Sensitivitäts Bezeichnungen unterstützen, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="136f0-216">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="136f0-217">Sie erstellen neue Teams, Gruppen und Websites mit den neuen Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="136f0-217">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="136f0-218">Benutzer können weiterhin Gruppen aus apps und Diensten erstellen, die die neuen Bezeichnungen nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="136f0-218">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="136f0-219">Benutzer können diese Gruppen jedoch nicht mit einer Bezeichnung versehen.</span><span class="sxs-lookup"><span data-stu-id="136f0-219">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="136f0-220">Verwenden Sie PowerShell, um die neuen Vertraulichkeits Bezeichnungen auf diese Gruppen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="136f0-220">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="136f0-221">Sie können Ihre alten Klassifizierungen beibehalten. Es wird jedoch dringend empfohlen, die neuen Vertraulichkeits Bezeichnungen für diese Gruppen mithilfe von PowerShell anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="136f0-221">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="136f0-222">Apps und Dienste, die die neuen Sensitivitäts Bezeichnungen unterstützen, werden mit den neuen Beschriftungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="136f0-222">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="136f0-223">Wenn Benutzergruppen aus apps und Diensten erstellen, die die neuen Bezeichnungen nicht unterstützen, können Sie eine Klassifizierung auswählen.</span><span class="sxs-lookup"><span data-stu-id="136f0-223">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="136f0-224">Wenn Sie für Dateien und e-Mails Vertraulichkeits Bezeichnungen (Unified Microsoft Information Protection-Bezeichnungen) verwenden</span><span class="sxs-lookup"><span data-stu-id="136f0-224">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="136f0-225">Sobald Sie diese Vorschau aktiviert haben, wechseln Sie zu jeder Bezeichnung im Microsoft 365 Compliance Center, und wenden Sie die gewünschten Richtlinien für Websites und Gruppen an.</span><span class="sxs-lookup"><span data-stu-id="136f0-225">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="136f0-226">Benutzer beginnen mit dem Anzeigen vorhandener Beschriftungen für Websites und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="136f0-226">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="136f0-227">Vorbereiten der SharePoint Online Verwaltungsshell vor dem neuetikettieren von Office 365 Gruppen</span><span class="sxs-lookup"><span data-stu-id="136f0-227">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="136f0-228">Vergewissern Sie sich vor dem Anwenden neuer Bezeichnungen, dass Sie die neueste SharePoint Online-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="136f0-228">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="136f0-229">Wenn Sie bereits über die neueste Version verfügen, können Sie [Office 365 Gruppen mit neuen Sensitivitäts Bezeichnungen neu bezeichnen](#relabel-office-365-groups-with-new-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="136f0-229">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="136f0-230">So bereiten Sie die SharePoint Online Management-Shell für die Vorschau vor:</span><span class="sxs-lookup"><span data-stu-id="136f0-230">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="136f0-231">Wenn Sie eine frühere Version der SharePoint Online-Verwaltungsshell installiert haben, wechseln Sie zu **Software hinzufügen oder entfernen** , und deinstallieren Sie "SharePoint Online Verwaltungsshell".</span><span class="sxs-lookup"><span data-stu-id="136f0-231">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="136f0-232">Wechseln Sie in einem Webbrowser zur Seite Download Center, und [Laden Sie die neueste SharePoint Online Verwaltungsshell herunter](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="136f0-232">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="136f0-233">Wählen Sie Ihre Sprache aus, und klicken Sie dann auf **herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="136f0-233">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="136f0-234">Wählen Sie zwischen der Datei x64 und x86. msi aus.</span><span class="sxs-lookup"><span data-stu-id="136f0-234">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="136f0-235">Laden Sie die x64-Datei herunter, wenn Sie die 64-Bit-Version von Windows oder die x86-Datei ausführen, wenn Sie die 32-Bit-Version ausführen.</span><span class="sxs-lookup"><span data-stu-id="136f0-235">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="136f0-236">Wenn Sie nicht wissen, finden Sie unter [welche Version des Windows-Betriebssystems soll ich ausführen?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="136f0-236">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="136f0-237">Nachdem Sie die Datei heruntergeladen haben, führen Sie die Datei aus, und führen Sie die Schritte im Setup-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="136f0-237">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="136f0-238">Neuetikettieren von Office 365 Gruppen mit neuen Sensitivitäts Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="136f0-238">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="136f0-239">Stellen Sie sicher, dass Sie die neueste Version der SharePoint Online Management-Shell verwenden.</span><span class="sxs-lookup"><span data-stu-id="136f0-239">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="136f0-240">Anweisungen finden Sie unter [Prepare the SharePoint Online Management Shell, bevor Sie Office 365 Gruppen umetikettieren](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="136f0-240">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="136f0-241">Stellen Sie mithilfe eines Geschäfts-oder Schul Kontos mit globalen Administrator-oder SharePoint-Administratorrechten in Office 365 eine Verbindung mit SharePoint Online Verwaltungsshell her.</span><span class="sxs-lookup"><span data-stu-id="136f0-241">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="136f0-242">Eine Anleitung dazu finden Sie unter [Erste Schritte mit der SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="136f0-242">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="136f0-243">Führen Sie den folgenden Befehl aus, um die Liste der Vertraulichkeits Bezeichnungen und deren GUIDs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="136f0-243">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="136f0-244">Notieren Sie sich die GUID für die Bezeichnung, die Sie überschreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="136f0-244">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="136f0-245">Beispielsweise die Bezeichnung "Allgemein".</span><span class="sxs-lookup"><span data-stu-id="136f0-245">For example, the "General" label.</span></span>

5. <span data-ttu-id="136f0-246">Verwenden Sie den folgenden Befehl, um die Liste der Gruppen abzurufen, die die "allgemeine" Klassifizierung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="136f0-246">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="136f0-247">Wenn Sie diesen Befehl ausführen, stellen Sie eine Verbindung mit Exchange Online PowerShell her und führen das Cmdlet Get-Unifiedgroup aus.</span><span class="sxs-lookup"><span data-stu-id="136f0-247">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. <span data-ttu-id="136f0-248">Fügen Sie für jede Gruppe die neue GUID der Sensitivitäts Bezeichnung hinzu.</span><span class="sxs-lookup"><span data-stu-id="136f0-248">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
