---
title: Verwenden von Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites (öffentliche Vorschau)
f1.keywords:
- NOCSH
ms.author: cabailey
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
ms.openlocfilehash: 611876b7e403c8d877c602d21967675adef2d061
ms.sourcegitcommit: 45ee610a380db113c2a50f6ea82d30137498babb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288565"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="03106-103">Verwenden von Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites (öffentliche Vorschau)</span><span class="sxs-lookup"><span data-stu-id="03106-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="03106-104">Wenn Sie im [Microsoft 365 Compliance Center](https://protection.office.com/) Vertraulichkeitsbezeichnungen erstellen, können Sie diese jetzt auf die folgenden Container anwenden: Microsoft Teams, Office 365-Gruppen und SharePoint-Websites.</span><span class="sxs-lookup"><span data-stu-id="03106-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="03106-105">Verwenden Sie Vertraulichkeitsbezeichnungen, um die folgenden Optionen für diese Container zu steuern:</span><span class="sxs-lookup"><span data-stu-id="03106-105">Use label settings to control the following options for these containers:</span></span>

- <span data-ttu-id="03106-106">Datenschutz für mit einer Office 365-Gruppe verbundene Teamwebsites (öffentlich oder privat)</span><span class="sxs-lookup"><span data-stu-id="03106-106">Privacy of Office 365 group-connected teams sites (public or private)</span></span>
- <span data-ttu-id="03106-107">Zugriff externer Benutzer</span><span class="sxs-lookup"><span data-stu-id="03106-107">External users access</span></span>
- <span data-ttu-id="03106-108">Zugriff von nicht verwalteten Geräten aus</span><span class="sxs-lookup"><span data-stu-id="03106-108">Access from unmanaged devices</span></span> 

<span data-ttu-id="03106-109">Wenn Sie diese Bezeichnung auf einen der unterstützten Container anwenden, wendet die Bezeichnung die konfigurierten Optionen automatisch auf die verbundene SharePoint- oder Teamwebsite an.</span><span class="sxs-lookup"><span data-stu-id="03106-109">When you apply this label to one of the supported containers, the label automatically applies the configured options to the connected SharePoint site or team site.</span></span> 

<span data-ttu-id="03106-110">Der Inhalt in diesen Containern erbt die Bezeichnung jedoch nicht für Einstellungen wie Bezeichnungsnamen, visuelle Markierungen oder Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="03106-110">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="03106-111">Informationen zum Anwenden von Bezeichnungen auf Dateien in SharePoint- oder Teamwebsites finden Sie unter [Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="03106-111">To label files in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="03106-112">Informationen zur öffentlichen Vorschau für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="03106-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="03106-113">Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites werden schrittweise für Mandanten bereitgestellt und können sich vor der endgültigen Version ändern.</span><span class="sxs-lookup"><span data-stu-id="03106-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are gradually rolling out to tenants and might change before final release.</span></span> <span data-ttu-id="03106-114">Diese öffentliche Vorschau kann nicht mit Office 365-Netzwerken für die Inhaltsübermittlung (Content Delivery Network, CDN) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="03106-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="03106-115">Bevor Sie diese Vorschau aktivieren und Vertraulichkeitsbezeichnungen für die neuen Einstellungen konfigurieren, können die Benutzer Vertraulichkeitsbezeichnungen in ihren Apps anzeigen und anwenden.</span><span class="sxs-lookup"><span data-stu-id="03106-115">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="03106-116">Beispielsweise aus Word:</span><span class="sxs-lookup"><span data-stu-id="03106-116">For example, from Word:</span></span>

![Eine in der Word-Desktop-App angezeigte Vertraulichkeitsbezeichnung](../media/sensitivity-label-word.png)

<span data-ttu-id="03106-118">Nachdem Sie diese Vorschau aktiviert und konfiguriert haben, können Benutzer Vertraulichkeitsbezeichnungen außerdem für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites anzeigen und anwenden.</span><span class="sxs-lookup"><span data-stu-id="03106-118">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="03106-119">Beispielsweise, wenn eine neue Teamwebsite in SharePoint erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="03106-119">For example, when you create a new team site from SharePoint:</span></span>

![Eine Vertraulichkeitsbezeichnung beim Erstellen einer Teamwebsite in SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="03106-121">Aktivieren dieser Vorschau und Synchronisieren von Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="03106-121">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="03106-122">Da dieses Feature die Azure AD-Funktionen nutzt, folgen Sie zum Aktivieren der Vorschau den Anweisungen in der Azure AD-Dokumentation: [Zuweisen von Vertraulichkeitsbezeichnungen zu Office 365-Gruppen in Azure Active Directory (Vorschau)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="03106-122">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Office 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="03106-123">Stellen Sie in einer PowerShell-Sitzung mithilfe eines Geschäfts-, Schul- oder Unikontos, das über globale Administratorberechtigungen verfügt, eine Verbindung mit dem Security & Compliance Center her.</span><span class="sxs-lookup"><span data-stu-id="03106-123">In a PowerShell session, connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="03106-124">Anweisungen hierzu finden Sie unter [Herstellen einer Verbindung mit Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="03106-124">For instructions, see [Connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="03106-125">Führen Sie die folgenden Befehle aus, um Ihre Bezeichnungen mit Azure AD zu synchronisieren, damit sie mit Office 365-Gruppen verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="03106-125">Run the following commands to synchronize your labels to Azure AD, so that they can be used with Office 365 groups:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="03106-126">Konfigurieren von Website- und Gruppeneinstellungen beim Erstellen oder Bearbeiten von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="03106-126">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="03106-127">Sie können jetzt Vertraulichkeitsbezeichnungen erstellen oder bearbeiten, die für Websites und Gruppen verfügbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="03106-127">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="03106-128">Durch Aktivieren der Vorschau wird eine neue Seite im Assistenten für Vertraulichkeitsbezeichnungen verfügbar: **Website- und Gruppeneinstellungen**</span><span class="sxs-lookup"><span data-stu-id="03106-128">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="03106-129">Wenn Sie Hilfe beim Erstellen oder Bearbeiten einer Vertraulichkeitsbezeichnung benötigen, lesen Sie die Anweisungen unter [Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="03106-129">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="03106-130">Auf dieser neuen Seite **Website- und Gruppeneinstellungen** können Sie die Einstellungen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="03106-130">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="03106-131">**Datenschutz für mit einer Office 365-Gruppe verbundene Teamwebsites**: Die Standardeinstellung **Öffentlich** wird automatisch ausgewählt. Das bedeutet, dass jeder in Ihrer Organisation auf die Teamwebsite zugreifen kann, auf die diese Bezeichnung angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="03106-131">**Privacy of Office 365 group-connected teams sites**: The default setting of **Public** is automatically selected, which means anyone in your organization can access the team site where this label is applied.</span></span> <span data-ttu-id="03106-132">Wählen Sie **Privat** aus, wenn nur genehmigte Mitglieder in Ihrer Organisation auf die Teamwebsite der Gruppe zugreifen können sollen.</span><span class="sxs-lookup"><span data-stu-id="03106-132">Select **Private** when you want only approved members in your organization to access the group's team site.</span></span> 
    
    <span data-ttu-id="03106-133">Die ausgewählte Einstellung ersetzt möglicherweise für die Gruppe konfigurierte frühere Datenschutzeinstellungen und sperrt den Datenschutzwert, sodass er nur geändert werden kann, wenn zuvor die Vertraulichkeitsbezeichnung von der Teamwebsite oder Gruppe entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="03106-133">The setting selected replaces a previous privacy setting that might be configured for the group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the team site or group.</span></span> <span data-ttu-id="03106-134">Nachdem Sie die Vertraulichkeitsbezeichnung entfernt haben, bleibt die Datenschutzeinstellung der Bezeichnung erhalten, Sie können sie aber jetzt bei Bedarf ändern.</span><span class="sxs-lookup"><span data-stu-id="03106-134">After you remove the sensitivity label, the privacy setting from the label remains and you can now change it if necessary.</span></span>

- <span data-ttu-id="03106-135">**Zugriff für externe Benutzer**: Steuern Sie, ob der Gruppenbesitzer [Gäste zur Gruppe hinzufügen](/office365/admin/create-groups/manage-guest-access-in-groups) kann.</span><span class="sxs-lookup"><span data-stu-id="03106-135">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="03106-136">**Nicht verwaltete Geräte**: Erlauben Sie für [nicht verwaltete Geräte](/sharepoint/control-access-from-unmanaged-devices) vollen Zugriff oder nur Webzugriff, bzw. blockieren Sie den Zugriff vollständig.</span><span class="sxs-lookup"><span data-stu-id="03106-136">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> 

![Die Registerkarte "Website- und Gruppeneinstellungen"](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="03106-138">Wenn Sie eine Bezeichnung auf ein Team, eine Gruppe oder eine Website anwenden, werden nur diese Website- und Gruppeneinstellungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="03106-138">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="03106-139">Andere Bezeichnungseinstellungen (z. B. Verschlüsselung und Inhaltskennzeichnung) werden nicht auf die Inhalte innerhalb des Teams, der Gruppen oder der Website angewendet.</span><span class="sxs-lookup"><span data-stu-id="03106-139">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="03106-140">Ähnlich verhält es sich, wenn Sie eine Bezeichnung erstellen und diese Website- und Gruppeneinstellungen nicht aktivieren. Die Bezeichnung ist dann weiterhin verfügbar, wenn Benutzer Teams, Gruppen und Websites erstellen, aber nur der Bezeichnungsname wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="03106-140">Similarly, if you create a label and don't turn on these site and group settings, the label will still be available when users create teams, groups, and sites, but only the label name will be applied.</span></span>

<span data-ttu-id="03106-141">Wenn Ihre Bezeichnung noch nicht veröffentlicht wurde, veröffentlichen Sie es jetzt, indem Sie [die Bezeichnung einer Bezeichnungsrichtlinie hinzufügen](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="03106-141">If your label isn't already published, now publish it by [adding it to a label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="03106-142">Verwaltung von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="03106-142">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="03106-143">Das Erstellen, Ändern und Löschen von Vertraulichkeitsbezeichnungen, die Sie für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites verwenden, erfordert eine sorgfältige Abstimmung mit der Veröffentlichung von Bezeichnungsrichtlinien für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="03106-143">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="03106-144">Vermeiden Sie Erstellungsfehler für Websites und Gruppen, die sich auf alle Benutzer auswirken, indem Sie die nachstehenden Anweisungen beachten.</span><span class="sxs-lookup"><span data-stu-id="03106-144">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="03106-145">**Erstellen und Veröffentlichen von Bezeichnungen:**</span><span class="sxs-lookup"><span data-stu-id="03106-145">**Creating and publishing labels:**</span></span>

<span data-ttu-id="03106-146">Nach der Erstellung und Veröffentlichung einer Vertraulichkeitsbezeichnung kann es bis zu 24 Stunden dauern, bis die Bezeichnung für Benutzer in Teams, Gruppen und Websites sichtbar wird.</span><span class="sxs-lookup"><span data-stu-id="03106-146">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="03106-147">Führen Sie die folgenden Schritte aus, um eine Bezeichnung für alle Benutzer im Mandanten zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="03106-147">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="03106-148">Erstellen Sie die Vertraulichkeitsbezeichnung, und veröffentlichen Sie sie nur für einige Benutzerkonten im Mandanten.</span><span class="sxs-lookup"><span data-stu-id="03106-148">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="03106-149">Warten Sie 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="03106-149">Wait for 24 hours.</span></span>

3. <span data-ttu-id="03106-150">Nach Ablauf dieser 24 Stunden erstellen Sie mit einem der in Schritt 1 angegebenen Benutzerkonten ein Team, eine Office 365-Gruppe oder eine SharePoint-Website mit der Bezeichnung, die Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="03106-150">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="03106-151">Wenn während des Erstellungsvorgangs für Schritt 3 keine Fehler auftreten, veröffentlichen Sie die Bezeichnung für alle Benutzer in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="03106-151">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="03106-152">Wenn Fehler auftreten, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="03106-152">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="03106-153">**Ändern und Löschen von veröffentlichten Bezeichnungen:**</span><span class="sxs-lookup"><span data-stu-id="03106-153">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="03106-154">Wenn Sie eine Vertraulichkeitsbezeichnung ändern oder löschen, die in einer oder mehreren Bezeichnungsrichtlinien enthalten ist, kann dies zu Erstellungsfehlern für alle Teams, Gruppen und Websites führen.</span><span class="sxs-lookup"><span data-stu-id="03106-154">If you modify or delete a sensitivity label that is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="03106-155">Folgen Sie dieser Anleitung, um dieses Problem zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="03106-155">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="03106-156">Entfernen Sie die Vertraulichkeitsbezeichnung aus allen Bezeichnungsrichtlinien, in denen die Bezeichnung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="03106-156">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="03106-157">Warten Sie 48 Stunden.</span><span class="sxs-lookup"><span data-stu-id="03106-157">Wait for 48 hours.</span></span>

3. <span data-ttu-id="03106-158">Versuchen Sie nach 48 Stunden, ein Team, eine Gruppe oder eine Website zu erstellen, und vergewissern Sie sich, dass die Bezeichnung nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="03106-158">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="03106-159">Wenn die Vertraulichkeitsbezeichnung nicht angezeigt wird, können Sie sie jetzt bedenkenlos ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="03106-159">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="03106-160">Wird die Bezeichnung weiterhin angezeigt, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="03106-160">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-office-365-groups"></a><span data-ttu-id="03106-161">Zuweisen von Vertraulichkeitsbezeichnungen zu Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="03106-161">Assign sensitivity labels to Office 365 groups</span></span>

<span data-ttu-id="03106-162">Jetzt können Sie die Vertraulichkeitsbezeichnungen auf Office 365-Gruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="03106-162">You're now ready to apply the sensitivity label or labels to Office 365 groups.</span></span> <span data-ttu-id="03106-163">Kehren Sie für weitere Anweisungen zur Azure AD-Dokumentation zurück:</span><span class="sxs-lookup"><span data-stu-id="03106-163">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="03106-164">Zuweisen einer Bezeichnung zu einer neuen Gruppe im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="03106-164">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="03106-165">Zuweisen einer Bezeichnung zu einer vorhandenen Gruppe im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="03106-165">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="03106-166">[Entfernen einer Bezeichnung von einer vorhandenen Gruppe im Azure-Portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="03106-166">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="03106-167">Anwenden einer Vertraulichkeitsbezeichnung auf ein neues Team</span><span class="sxs-lookup"><span data-stu-id="03106-167">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="03106-168">Benutzer können Vertraulichkeitsbezeichnungen auswählen, wenn sie neue Teams in Microsoft Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="03106-168">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="03106-169">Beim Auswählen der Vertraulichkeitsstufe werden die Datenschutzeinstellung bei Bedarf entsprechend geändert.</span><span class="sxs-lookup"><span data-stu-id="03106-169">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="03106-170">Abhängig von der für die Bezeichnung festgelegten Einstellung für den externen Benutzerzugriff können Benutzer Personen außerhalb der Organisation zum Team hinzufügen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="03106-170">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="03106-171">Weitere Informationen Vertraulichkeitsbezeichnungen für Teams</span><span class="sxs-lookup"><span data-stu-id="03106-171">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![Datenschutzeinstellung beim Erstellen eines neuen Teams](../media/privacy-setting-new-team.png)

<span data-ttu-id="03106-173">Nachdem Sie das Team erstellt haben, wird die Vertraulichkeitsbezeichnung in der oberen rechten Ecke aller Kanäle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="03106-173">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![Die Vertraulichkeitsbezeichnung wird im Team angezeigt](../media/privacy-setting-teams.png)

<span data-ttu-id="03106-175">Der Dienst wendet auf die Office 365-Gruppe und die verbundene SharePoint-Teamwebsite automatisch die gleiche Vertraulichkeitsbezeichnung an.</span><span class="sxs-lookup"><span data-stu-id="03106-175">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="03106-176">Anwenden einer Vertraulichkeitsbezeichnung auf eine neue Gruppe in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="03106-176">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="03106-177">Wenn Sie in Outlook im Web eine neue Gruppe erstellen, können Sie die Option **Vertraulichkeit** für veröffentlichte Bezeichnungen auswählen oder ändern:</span><span class="sxs-lookup"><span data-stu-id="03106-177">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![Erstellen einer Gruppe und Auswählen einer Option unter "Vertraulichkeit"](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="03106-179">Anwenden einer Vertraulichkeitsbezeichnung auf eine neue Website</span><span class="sxs-lookup"><span data-stu-id="03106-179">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="03106-180">Administratoren und Endbenutzer können [beim Erstellen moderner Teamwebsites und Kommunikationswebsites](/sharepoint/create-site-collection) Vertraulichkeitsbezeichnungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="03106-180">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection).</span></span>

<span data-ttu-id="03106-181">Wenn Benutzer moderne Teamwebsites und Kommunikationswebsites erstellen, ist standardmäßig bereits eine Vertraulichkeitsbezeichnung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="03106-181">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="03106-182">Benutzer können das Hilfesymbol auswählen, um weitere Informationen zu den Bezeichnungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="03106-182">Users can select the help icon to learn more about the labels.</span></span>

![Erstellen einer Website und Auswählen einer Option unter "Vertraulichkeit"](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="03106-184">Wenn Benutzer zu der Website navigieren, werden der Name der Bezeichnung und die angewendeten Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="03106-184">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Eine Website, auf die eine Vertraulichkeitsbezeichnung angewendet wurde](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="03106-186">Anzeigen von Vertraulichkeitsbezeichnungen im SharePoint Online Admin Center</span><span class="sxs-lookup"><span data-stu-id="03106-186">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="03106-187">Zum Anzeigen der angewendeten Vertraulichkeitsbezeichnungen verwenden Sie die Seite **Aktive Websites** im neuen SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="03106-187">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="03106-188">Möglicherweise müssen Sie zuerst die Spalte **Vertraulichkeit** hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="03106-188">You might need to first add the **Sensitivity** column:</span></span>

![Die Spalte "Vertraulichkeit" auf der Seite "Aktive Websites"](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="03106-190">[Weitere Informationen zum Verwalten von Websites im neuen SharePoint Admin Center](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="03106-190">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="03106-191">Ändern von Website- und Gruppeneinstellungen für eine Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="03106-191">Change site and group settings for a label</span></span>

<span data-ttu-id="03106-192">Wenn Sie eine Änderung an den Website- und Gruppeneinstellungen für eine Bezeichnung vornehmen, müssen Sie die folgenden PowerShell-Befehle ausführen, damit Ihre Teams, Websites und Gruppen die neuen Einstellungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="03106-192">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="03106-193">Es wird empfohlen, die Website- und Gruppeneinstellungen für eine Bezeichnung nicht zu ändern, nachdem Sie die Bezeichnung auf mehrere Teams, Gruppen oder Websites angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="03106-193">As a best practice, don't the change site and group settings for a label after you've applied the label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="03106-194">Führen Sie die folgenden Befehle aus, um eine Verbindung mit PowerShell im Office 365 Security & Compliance Center herzustellen und die Liste der Vertraulichkeitsbezeichnungen und deren GUIDs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="03106-194">Run the following commands to connect to Office 365 Security & Compliance Center PowerShell and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. <span data-ttu-id="03106-195">Notieren Sie sich die GUID für die Bezeichnung(en), die Sie geändert haben.</span><span class="sxs-lookup"><span data-stu-id="03106-195">Make a note of the GUID for the label or labels you have changed.</span></span>

3. <span data-ttu-id="03106-196">Stellen Sie jetzt eine Verbindung mit Exchange Online PowerShell her, und führen Sie das Cmdlet "Get-UnifiedGroup" aus. Geben Sie dabei die GUID der Bezeichnung anstelle der Beispiel-GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" an:</span><span class="sxs-lookup"><span data-stu-id="03106-196">Now connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. <span data-ttu-id="03106-197">Wenden Sie die Vertraulichkeitsbezeichnung für jede Gruppe unter Verwendung der Bezeichnungs-GUID anstelle der Beispiel-GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" erneut an:</span><span class="sxs-lookup"><span data-stu-id="03106-197">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="03106-198">Unterstützung der Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="03106-198">Support for the sensitivity labels</span></span>

<span data-ttu-id="03106-199">Sie können die Vertraulichkeitsbezeichnungen, die Sie für die Website- und Gruppeneinstellungen konfiguriert haben, mit den folgenden Apps und Diensten verwenden:</span><span class="sxs-lookup"><span data-stu-id="03106-199">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="03106-200">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="03106-200">SharePoint Online</span></span>
- <span data-ttu-id="03106-201">Teams</span><span class="sxs-lookup"><span data-stu-id="03106-201">Teams</span></span>
- <span data-ttu-id="03106-202">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="03106-202">Outlook on the web</span></span>
- <span data-ttu-id="03106-203">SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="03106-203">SharePoint admin center</span></span>
- <span data-ttu-id="03106-204">Azure AD Admin Center</span><span class="sxs-lookup"><span data-stu-id="03106-204">Azure AD admin center</span></span>

<span data-ttu-id="03106-205">In folgenden anderen Apps und Diensten können Sie die Vertraulichkeitsbezeichnungen, die Sie für die Website- und Gruppeneinstellungen konfiguriert haben, derzeit nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="03106-205">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="03106-206">Outlook für Mac</span><span class="sxs-lookup"><span data-stu-id="03106-206">Outlook for the Mac</span></span>
- <span data-ttu-id="03106-207">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="03106-207">Outlook mobile</span></span>
- <span data-ttu-id="03106-208">Outlook Desktop für Windows</span><span class="sxs-lookup"><span data-stu-id="03106-208">Outlook desktop for Windows</span></span>
- <span data-ttu-id="03106-209">Forms</span><span class="sxs-lookup"><span data-stu-id="03106-209">Forms</span></span>
- <span data-ttu-id="03106-210">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="03106-210">Dynamics 365</span></span>
- <span data-ttu-id="03106-211">Yammer</span><span class="sxs-lookup"><span data-stu-id="03106-211">Yammer</span></span>
- <span data-ttu-id="03106-212">Stream</span><span class="sxs-lookup"><span data-stu-id="03106-212">Stream</span></span>
- <span data-ttu-id="03106-213">Planner</span><span class="sxs-lookup"><span data-stu-id="03106-213">Planner</span></span>
- <span data-ttu-id="03106-214">Project</span><span class="sxs-lookup"><span data-stu-id="03106-214">Project</span></span>
- <span data-ttu-id="03106-215">PowerBI</span><span class="sxs-lookup"><span data-stu-id="03106-215">PowerBI</span></span>
- <span data-ttu-id="03106-216">Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="03106-216">Teams admin center</span></span>
- <span data-ttu-id="03106-217">Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="03106-217">Microsoft 365 admin center</span></span>
- <span data-ttu-id="03106-218">Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="03106-218">Exchange admin center</span></span>


## <a name="classic-azure-ad-site-classification"></a><span data-ttu-id="03106-219">Klassische Azure AD-Websiteklassifizierung</span><span class="sxs-lookup"><span data-stu-id="03106-219">Classic Azure AD site classification</span></span>

<span data-ttu-id="03106-220">Wenn Sie diese Vorschau aktivieren, unterstützt Office 365 die alten Klassifizierungen nicht mehr für neue Gruppen und SharePoint-Websites.</span><span class="sxs-lookup"><span data-stu-id="03106-220">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="03106-221">Bei vorhandenen Gruppen und Websites werden die alten Klassifizierungen jedoch weiterhin angezeigt, es sei denn, Sie konvertieren sie, um Vertraulichkeitsbezeichnungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="03106-221">However, existing groups and sites still display the old classifications unless you convert them to use sensitivity labels.</span></span> <span data-ttu-id="03106-222">Alte Klassifizierungen schließen die Klassifizierung von "modernen" Websites ein, die Sie möglicherweise über Azure AD PowerShell oder die PnP Core-Bibliothek eingerichtet haben, in der Werte für die `ClassificationList`-Einstellung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="03106-222">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="03106-223">Beispielsweise in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="03106-223">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="03106-224">Weitere Informationen zur alten Klassifizierungsmethode finden Sie unter ["" ](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="03106-224">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="03106-225">Um Ihre alten Klassifizierungen in Vertraulichkeitsbezeichnungen umzuwandeln, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="03106-225">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="03106-226">Verwenden vorhandener Bezeichnungen: Geben Sie die gewünschten Bezeichnungseinstellungen für Websites und Gruppen an, indem Sie bereits veröffentlichte Vertraulichkeitsbezeichnungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="03106-226">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="03106-227">Erstellen neuer Bezeichnungen: Geben Sie die gewünschten Bezeichnungseinstellungen für Websites und Gruppen an, indem Sie neue Vertraulichkeitsbezeichnungen mit den gleichen Namen wie Ihre bestehenden Klassifizierungen erstellen und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="03106-227">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="03106-228">Gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="03106-228">Then:</span></span> 

1. <span data-ttu-id="03106-229">Verwenden Sie PowerShell, um die Vertraulichkeitsbezeichnungen mithilfe von Namenszuordnung auf vorhandene Office 365-Gruppen und SharePoint-Websites anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="03106-229">Use PowerShell to apply the sensitivity labels to existing Office 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="03106-230">Entsprechende Anweisungen finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="03106-230">See the next section for instructions.</span></span>

2. <span data-ttu-id="03106-231">Entfernen Sie die alten Klassifizierungen der bestehenden Gruppen und Websites.</span><span class="sxs-lookup"><span data-stu-id="03106-231">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="03106-232">Sie können Benutzer zwar nicht daran hindern, neue Gruppen in Apps und Diensten, die noch keine Vertraulichkeitsbezeichnungen unterstützen, zu erstellen, aber Sie können wiederholt ein PowerShell-Skript ausführen, um nach neuen Gruppen zu suchen, die von Benutzern mit den alten Klassifizierungen erstellt wurden, und diese in Vertraulichkeitsbezeichnungen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="03106-232">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-office-365-groups-to-sensitivity-labels"></a><span data-ttu-id="03106-233">Verwenden von PowerShell, um Klassifizierungen für Office 365-Gruppen in Vertraulichkeitsbezeichnungen zu konvertieren</span><span class="sxs-lookup"><span data-stu-id="03106-233">Use PowerShell to convert classifications for Office 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="03106-234">Stellen Sie sicher, dass Sie die Version 16.0.19418.12000 oder höher der SharePoint Online-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="03106-234">Ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="03106-235">Wenn Sie bereits über die neueste Version verfügen, fahren Sie mit Schritt 4 fort.</span><span class="sxs-lookup"><span data-stu-id="03106-235">If you already have the latest version, skip to step 4.</span></span>

2. <span data-ttu-id="03106-236">Wenn Sie eine frühere Version der SharePoint-Online-Verwaltungsshell aus dem PowerShell-Katalog installiert haben, können Sie das Modul aktualisieren, indem Sie das folgende Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="03106-236">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>
    
    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

3. <span data-ttu-id="03106-237">Wenn Sie eine frühere Version der SharePoint Online-Verwaltungsshell installiert haben, wechseln Sie im Microsoft Download Center zu **Software hinzufügen oder entfernen**, und deinstallieren Sie die "SharePoint Online-Verwaltungsshell".</span><span class="sxs-lookup"><span data-stu-id="03106-237">If you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span> <span data-ttu-id="03106-238">Installieren Sie dann die neueste SharePoint-Online-Verwaltungsshell über das [Download Center](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="03106-238">Then, install the latest SharePoint Online Management Shell from the [Download Center](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="03106-239">Stellen Sie unter Verwendung eines Geschäfts-, Schul- oder Unikontos, das über globale Administrator- oder SharePoint-Administratorberechtigungen in Office 365 verfügt, eine Verbindung mit der SharePoint Online-Verwaltungsshell her.</span><span class="sxs-lookup"><span data-stu-id="03106-239">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="03106-240">Eine Anleitung dazu finden Sie unter [Erste Schritte mit der SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="03106-240">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

5. <span data-ttu-id="03106-241">Führen Sie die folgenden Befehle aus, um die Liste der Vertraulichkeitsbezeichnungen und deren GUIDs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="03106-241">Run the following commands to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

6. <span data-ttu-id="03106-242">Notieren Sie sich die GUIDs für die Vertraulichkeitsbezeichnungen, die Sie auf Ihre Office 365-Gruppen anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="03106-242">Make a note of the GUIDs for the sensitivity labels you want to apply to your Office 365 groups.</span></span>

7. <span data-ttu-id="03106-243">Verwenden Sie den folgenden Befehl als Beispiel, um die Liste der Gruppen abzurufen, die derzeit die Klassifizierung "Allgemein" aufweisen:</span><span class="sxs-lookup"><span data-stu-id="03106-243">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="03106-244">Fügen Sie für jede Gruppe die neue Vertraulichkeitsbezeichnungs-GUID hinzu.</span><span class="sxs-lookup"><span data-stu-id="03106-244">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="03106-245">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="03106-245">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="03106-246">Überwachen von Vertraulichkeitsbezeichnungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="03106-246">Auditing sensitivity label activities</span></span>

<span data-ttu-id="03106-247">Wenn jemand ein Dokument auf eine Website hochlädt, die mit einer Vertraulichkeitsbezeichnung geschützt ist, und das Dokument eine Vertraulichkeitsbezeichnung mit [höherer Priorität](sensitivity-labels.md#label-priority-order-matters) als die auf die Website angewendete Vertraulichkeitsbezeichnung aufweist, wird diese Aktion nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="03106-247">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="03106-248">Angenommen, Sie haben die Bezeichnung **Allgemein** auf eine SharePoint-Website angewendet, und jemand lädt ein Dokument mit der Bezeichnung **Vertraulich** auf diese Site hoch.</span><span class="sxs-lookup"><span data-stu-id="03106-248">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="03106-249">Da eine Vertraulichkeitsbezeichnung mit einer höheren Priorität Inhalte kennzeichnet, die eine höhere Vertraulichkeitsstufe aufweisen, als Inhalte mit einer niedrigeren Priorität, könnte dies ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="03106-249">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="03106-250">Die Aktion wird zwar nicht blockiert, sie wird jedoch überwacht, sodass Sie Dokumente mit abweichender Bezeichnungspriorität identifizieren und bei Bedarf Maßnahmen ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="03106-250">Although the action isn't blocked, it is audited, so you can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="03106-251">Löschen oder verschieben Sie zum Beispiel das hochgeladene Dokument von der Website.</span><span class="sxs-lookup"><span data-stu-id="03106-251">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="03106-252">Es würde kein Sicherheitsrisiko darstellen, wenn die auf ein Dokument angewendete Vertraulichkeitsbezeichnung eine niedrigere Priorität aufweist als die auf die Website angewendete Vertraulichkeitsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="03106-252">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="03106-253">Angenommen, ein Dokument, das als **Allgemein** bezeichnet ist, wird auf eine Website hochgeladen, die mit **Vertraulich** bezeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="03106-253">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="03106-254">In diesem Szenario wird kein Überwachungsereignis erzeugt.</span><span class="sxs-lookup"><span data-stu-id="03106-254">In this scenario, an auditing event isn't generated.</span></span>

<span data-ttu-id="03106-255">Um das Überwachungsprotokoll nach diesem Ereignis zu durchsuchen, suchen Sie nach **Konflikt in Bezug auf die Vertraulichkeitsbezeichnung eines Dokuments** aus der Kategorie **Datei- und Seitenaktivitäten**.</span><span class="sxs-lookup"><span data-stu-id="03106-255">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="03106-256">Wenn jemand einer Website oder Gruppe eine Vertraulichkeitsbezeichnung hinzufügt oder eine Vertraulichkeitsbezeichnung von einer Website oder Gruppe entfernt, werden diese Aktivitäten ebenfalls überwacht.</span><span class="sxs-lookup"><span data-stu-id="03106-256">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited.</span></span> <span data-ttu-id="03106-257">Diese Ereignisse sind in der Kategorie [Vertraulichkeitsbezeichnungsaktivitäten](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) zu finden.</span><span class="sxs-lookup"><span data-stu-id="03106-257">These events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> 

<span data-ttu-id="03106-258">Anweisungen zum Durchsuchen des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="03106-258">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="03106-259">Problembehandlung bei der Bereitstellung von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="03106-259">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="03106-260">Sie haben Probleme mit Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites?</span><span class="sxs-lookup"><span data-stu-id="03106-260">Having problems with sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="03106-261">Überprüfen Sie die Folgendes:</span><span class="sxs-lookup"><span data-stu-id="03106-261">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="03106-262">Bezeichnungen sind nach der Veröffentlichung nicht sichtbar</span><span class="sxs-lookup"><span data-stu-id="03106-262">Labels not visible after publishing</span></span>
<span data-ttu-id="03106-263">Wenn beim Erstellen eines Teams oder einer Office 365-Gruppe Probleme auftreten, nachdem Sie diese Einstellungen aktiviert oder die Beschreibung einer Vertraulichkeitsbezeichnung geändert haben, warten Sie nach dem Speichern der Bezeichnungsänderungen ein paar Stunden, und versuchen Sie dann erneut, das Team oder die Gruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="03106-263">If you experience issues when you create a team or Office 365 group after you enable these settings or modify a sensitivity label's description, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="03106-264">Informationen hierzu finden Sie unter [Planen des Rollouts nach Erstellung oder Änderung einer Vertraulichkeitsbezeichnung](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="03106-264">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="03106-265">Wenn die neue Vertraulichkeitsbezeichnung in SharePoint Online weiterhin nicht angezeigt wird, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="03106-265">If you are still not able to see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="03106-266">Fehler beim Erstellen von Teams, Gruppen oder SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="03106-266">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="03106-267">Wenn während der öffentlichen Vorschau Erstellungsfehler auftreten, haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="03106-267">If you experience creation errors during the public preview, you have two options:</span></span>

- <span data-ttu-id="03106-268">Stellen Sie sicher, dass Vertraulichkeitsbezeichnungen für keinen Benutzer obligatorisch sind.</span><span class="sxs-lookup"><span data-stu-id="03106-268">Ensure that sensitivity labels are not mandatory for any user.</span></span>

- <span data-ttu-id="03106-269">Sie können Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites unter Verwendung der Anweisungen im Abschnitt [Aktivieren der Unterstützung von Vertraulichkeitsbezeichnungen in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell) deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="03106-269">You can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="03106-270">Um die Vorschau zu deaktivieren, müssen Sie jedoch in Schritt 5 die Funktion mit `$setting["EnableMIPLabels"] = "False"` deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="03106-270">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

