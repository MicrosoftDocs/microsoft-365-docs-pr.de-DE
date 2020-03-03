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
ms.openlocfilehash: 1e08df688a62d6c15ef0100b5379e62482ed7b50
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372033"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="4eed5-103">Verwenden von Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites (öffentliche Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4eed5-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="4eed5-104">Wenn Sie im [Microsoft 365 Compliance Center](https://protection.office.com/) Vertraulichkeitsbezeichnungen erstellen, können Sie diese jetzt auf die folgenden Container anwenden: Microsoft Teams, Office 365-Gruppen und SharePoint-Websites.</span><span class="sxs-lookup"><span data-stu-id="4eed5-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="4eed5-105">Verwenden Sie Vertraulichkeitsbezeichnungen, um die folgenden Optionen für diese Container zu steuern:</span><span class="sxs-lookup"><span data-stu-id="4eed5-105">Use label settings to control the following options for these containers:</span></span>

- <span data-ttu-id="4eed5-106">Datenschutz (öffentlich oder privat) für mit einer Office 365-Gruppe verbundene Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="4eed5-106">Privacy (public or private) of Office 365 group-connected teams sites</span></span>
- <span data-ttu-id="4eed5-107">Zugriff externer Benutzer</span><span class="sxs-lookup"><span data-stu-id="4eed5-107">External users access</span></span>
- <span data-ttu-id="4eed5-108">Zugriff von nicht verwalteten Geräten aus</span><span class="sxs-lookup"><span data-stu-id="4eed5-108">Access from unmanaged devices</span></span> 

<span data-ttu-id="4eed5-109">Wenn Sie diese Bezeichnung auf einen der unterstützten Container anwenden, wendet die Bezeichnung die konfigurierten Optionen automatisch auf die verbundene SharePoint- oder Teamwebsite an.</span><span class="sxs-lookup"><span data-stu-id="4eed5-109">When you apply this label to one of the supported containers, the label automatically applies the configured options to the connected SharePoint site or team site.</span></span> 

<span data-ttu-id="4eed5-110">Der Inhalt in diesen Containern erbt die Bezeichnung jedoch nicht für Einstellungen wie Bezeichnungsnamen, visuelle Markierungen oder Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="4eed5-110">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="4eed5-111">Informationen zum Anwenden von Bezeichnungen auf Dateien in SharePoint- oder Teamwebsites finden Sie unter [Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="4eed5-111">To label files in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="4eed5-112">Informationen zur öffentlichen Vorschau für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="4eed5-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="4eed5-113">Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites werden schrittweise für Mandanten bereitgestellt und können sich vor der endgültigen Version ändern.</span><span class="sxs-lookup"><span data-stu-id="4eed5-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are gradually rolling out to tenants and might change before final release.</span></span> <span data-ttu-id="4eed5-114">Diese öffentliche Vorschau kann nicht mit Office 365-Netzwerken für die Inhaltsübermittlung (Content Delivery Network, CDN) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4eed5-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="4eed5-115">Bevor Sie diese Vorschau aktivieren und Vertraulichkeitsbezeichnungen für die neuen Einstellungen konfigurieren, können die Benutzer Vertraulichkeitsbezeichnungen in ihren Apps anzeigen und anwenden.</span><span class="sxs-lookup"><span data-stu-id="4eed5-115">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="4eed5-116">Beispielsweise aus Word:</span><span class="sxs-lookup"><span data-stu-id="4eed5-116">For example, from Word:</span></span>

![Eine in der Word-Desktop-App angezeigte Vertraulichkeitsbezeichnung](../media/sensitivity-label-word.png)

<span data-ttu-id="4eed5-118">Nachdem Sie diese Vorschau aktiviert und konfiguriert haben, können Benutzer Vertraulichkeitsbezeichnungen außerdem für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites anzeigen und anwenden.</span><span class="sxs-lookup"><span data-stu-id="4eed5-118">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="4eed5-119">Beispielsweise, wenn eine neue Teamwebsite in SharePoint erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="4eed5-119">For example, when you create a new team site from SharePoint:</span></span>

![Eine Vertraulichkeitsbezeichnung beim Erstellen einer Teamwebsite in SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="4eed5-121">Aktivieren dieser Vorschau und Synchronisieren von Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="4eed5-121">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="4eed5-122">Da dieses Feature die Azure AD-Funktionen nutzt, folgen Sie zum Aktivieren der Vorschau den Anweisungen in der Azure AD-Dokumentation: [Zuweisen von Vertraulichkeitsbezeichnungen zu Office 365-Gruppen in Azure Active Directory (Vorschau)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="4eed5-122">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Office 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="4eed5-123">Stellen Sie in einer PowerShell-Sitzung mithilfe eines Geschäfts-, Schul- oder Unikontos, das über globale Administratorberechtigungen verfügt, eine Verbindung mit dem Security & Compliance Center her.</span><span class="sxs-lookup"><span data-stu-id="4eed5-123">In a PowerShell session, connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="4eed5-124">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4eed5-124">For example:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```
    
    <span data-ttu-id="4eed5-125">Vollständige Anweisungen hierzu finden Sie unter [Herstellen einer Verbindung mit Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="4eed5-125">For full instructions, see [Connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="4eed5-126">Führen Sie den folgenden Befehl aus, um Ihre Vertraulichkeitsbezeichnungen mit Azure AD zu synchronisieren, damit sie mit Office 365-Gruppen verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="4eed5-126">Run the following command to synchronize your sensitivity labels to Azure AD, so that they can be used with Office 365 groups:</span></span>
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="4eed5-127">Konfigurieren von Website- und Gruppeneinstellungen beim Erstellen oder Bearbeiten von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="4eed5-127">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="4eed5-128">Sie können jetzt Vertraulichkeitsbezeichnungen erstellen oder bearbeiten, die für Websites und Gruppen verfügbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="4eed5-128">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="4eed5-129">Durch Aktivieren der Vorschau wird eine neue Seite im Assistenten für Vertraulichkeitsbezeichnungen verfügbar: **Website- und Gruppeneinstellungen**</span><span class="sxs-lookup"><span data-stu-id="4eed5-129">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="4eed5-130">Wenn Sie Hilfe beim Erstellen oder Bearbeiten einer Vertraulichkeitsbezeichnung benötigen, lesen Sie die Anweisungen unter [Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="4eed5-130">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="4eed5-131">Auf dieser neuen Seite **Website- und Gruppeneinstellungen** können Sie die Einstellungen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4eed5-131">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="4eed5-132">**Datenschutz für mit einer Office 365-Gruppe verbundene Teamwebsites**: Die Standardeinstellung **Öffentlich** wird automatisch ausgewählt. Das bedeutet, dass jeder in Ihrer Organisation auf die Teamwebsite zugreifen kann, auf die diese Bezeichnung angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4eed5-132">**Privacy of Office 365 group-connected teams sites**: The default setting of **Public** is automatically selected, which means anyone in your organization can access the team site where this label is applied.</span></span> <span data-ttu-id="4eed5-133">Wählen Sie **Privat** aus, wenn nur genehmigte Mitglieder in Ihrer Organisation auf die Teamwebsite der Gruppe zugreifen können sollen.</span><span class="sxs-lookup"><span data-stu-id="4eed5-133">Select **Private** when you want only approved members in your organization to access the group's team site.</span></span> 
    
    <span data-ttu-id="4eed5-134">Die ausgewählte Einstellung ersetzt möglicherweise für die Gruppe konfigurierte frühere Datenschutzeinstellungen und sperrt den Datenschutzwert, sodass er nur geändert werden kann, wenn zuvor die Vertraulichkeitsbezeichnung von der Teamwebsite oder Gruppe entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="4eed5-134">The setting selected replaces a previous privacy setting that might be configured for the group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the team site or group.</span></span> <span data-ttu-id="4eed5-135">Nachdem Sie die Vertraulichkeitsbezeichnung entfernt haben, bleibt die Datenschutzeinstellung der Bezeichnung erhalten, Sie können sie aber jetzt bei Bedarf ändern.</span><span class="sxs-lookup"><span data-stu-id="4eed5-135">After you remove the sensitivity label, the privacy setting from the label remains and you can now change it if necessary.</span></span>

- <span data-ttu-id="4eed5-136">**Zugriff für externe Benutzer**: Steuern Sie, ob der Gruppenbesitzer [Gäste zur Gruppe hinzufügen](/office365/admin/create-groups/manage-guest-access-in-groups) kann.</span><span class="sxs-lookup"><span data-stu-id="4eed5-136">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="4eed5-137">**Nicht verwaltete Geräte**: Erlauben Sie für [nicht verwaltete Geräte](/sharepoint/control-access-from-unmanaged-devices) vollen Zugriff oder nur Webzugriff, bzw. blockieren Sie den Zugriff vollständig.</span><span class="sxs-lookup"><span data-stu-id="4eed5-137">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> 

![Die Registerkarte "Website- und Gruppeneinstellungen"](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="4eed5-139">Wenn Sie eine Bezeichnung auf ein Team, eine Gruppe oder eine Website anwenden, werden nur diese Website- und Gruppeneinstellungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="4eed5-139">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="4eed5-140">Andere Bezeichnungseinstellungen (z. B. Verschlüsselung und Inhaltskennzeichnung) werden nicht auf die Inhalte innerhalb des Teams, der Gruppen oder der Website angewendet.</span><span class="sxs-lookup"><span data-stu-id="4eed5-140">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="4eed5-141">Ähnlich verhält es sich, wenn Sie eine Bezeichnung erstellen und diese Website- und Gruppeneinstellungen nicht aktivieren. Die Bezeichnung ist dann weiterhin verfügbar, wenn Benutzer Teams, Gruppen und Websites erstellen, aber nur der Bezeichnungsname wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="4eed5-141">Similarly, if you create a label and don't turn on these site and group settings, the label will still be available when users create teams, groups, and sites, but only the label name will be applied.</span></span>

<span data-ttu-id="4eed5-142">Wenn Ihre Vertraulichkeitskennzeichnung noch nicht veröffentlicht wurde, veröffentlichen Sie diese jetzt, indem Sie sie[einer Richtlinie für Vertraulichkeitskennzeichnungen hinzufügen](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="4eed5-142">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="4eed5-143">Diejenigen Benutzer, denen eine Richtlinie zur Vertraulichkeitskennzeichnung zugeordnet ist, die diese Kennzeichnung beinhaltet, können diese für Websites und Gruppen auswählen.</span><span class="sxs-lookup"><span data-stu-id="4eed5-143">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="4eed5-144">Verwaltung von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="4eed5-144">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="4eed5-145">Das Erstellen, Ändern und Löschen von Vertraulichkeitsbezeichnungen, die Sie für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites verwenden, erfordert eine sorgfältige Abstimmung mit der Veröffentlichung von Bezeichnungsrichtlinien für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4eed5-145">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="4eed5-146">Vermeiden Sie Erstellungsfehler für Websites und Gruppen, die sich auf alle Benutzer auswirken, indem Sie die nachstehenden Anweisungen beachten.</span><span class="sxs-lookup"><span data-stu-id="4eed5-146">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="4eed5-147">**Erstellen und Veröffentlichen von Bezeichnungen:**</span><span class="sxs-lookup"><span data-stu-id="4eed5-147">**Creating and publishing labels:**</span></span>

<span data-ttu-id="4eed5-148">Nach der Erstellung und Veröffentlichung einer Vertraulichkeitsbezeichnung kann es bis zu 24 Stunden dauern, bis die Bezeichnung für Benutzer in Teams, Gruppen und Websites sichtbar wird.</span><span class="sxs-lookup"><span data-stu-id="4eed5-148">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="4eed5-149">Führen Sie die folgenden Schritte aus, um eine Bezeichnung für alle Benutzer im Mandanten zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="4eed5-149">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="4eed5-150">Erstellen Sie die Vertraulichkeitsbezeichnung, und veröffentlichen Sie sie nur für einige Benutzerkonten im Mandanten.</span><span class="sxs-lookup"><span data-stu-id="4eed5-150">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="4eed5-151">Warten Sie 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="4eed5-151">Wait for 24 hours.</span></span>

3. <span data-ttu-id="4eed5-152">Nach Ablauf dieser 24 Stunden erstellen Sie mit einem der in Schritt 1 angegebenen Benutzerkonten ein Team, eine Office 365-Gruppe oder eine SharePoint-Website mit der Bezeichnung, die Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="4eed5-152">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="4eed5-153">Wenn während des Erstellungsvorgangs für Schritt 3 keine Fehler auftreten, veröffentlichen Sie die Bezeichnung für alle Benutzer in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="4eed5-153">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="4eed5-154">Wenn Fehler auftreten, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="4eed5-154">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="4eed5-155">**Ändern und Löschen von veröffentlichten Bezeichnungen:**</span><span class="sxs-lookup"><span data-stu-id="4eed5-155">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="4eed5-156">Wenn Sie eine Vertraulichkeitsbezeichnung ändern oder löschen, die in einer oder mehreren Bezeichnungsrichtlinien enthalten ist, kann dies zu Erstellungsfehlern für alle Teams, Gruppen und Websites führen.</span><span class="sxs-lookup"><span data-stu-id="4eed5-156">If you modify or delete a sensitivity label that is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="4eed5-157">Folgen Sie dieser Anleitung, um dieses Problem zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="4eed5-157">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="4eed5-158">Entfernen Sie die Vertraulichkeitsbezeichnung aus allen Bezeichnungsrichtlinien, in denen die Bezeichnung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="4eed5-158">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="4eed5-159">Warten Sie 48 Stunden.</span><span class="sxs-lookup"><span data-stu-id="4eed5-159">Wait for 48 hours.</span></span>

3. <span data-ttu-id="4eed5-160">Versuchen Sie nach 48 Stunden, ein Team, eine Gruppe oder eine Website zu erstellen, und vergewissern Sie sich, dass die Bezeichnung nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4eed5-160">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="4eed5-161">Wenn die Vertraulichkeitsbezeichnung nicht angezeigt wird, können Sie sie jetzt bedenkenlos ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="4eed5-161">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="4eed5-162">Wird die Bezeichnung weiterhin angezeigt, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="4eed5-162">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-office-365-groups"></a><span data-ttu-id="4eed5-163">Zuweisen von Vertraulichkeitsbezeichnungen zu Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="4eed5-163">Assign sensitivity labels to Office 365 groups</span></span>

<span data-ttu-id="4eed5-164">Jetzt können Sie die Vertraulichkeitsbezeichnungen auf Office 365-Gruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="4eed5-164">You're now ready to apply the sensitivity label or labels to Office 365 groups.</span></span> <span data-ttu-id="4eed5-165">Kehren Sie für weitere Anweisungen zur Azure AD-Dokumentation zurück:</span><span class="sxs-lookup"><span data-stu-id="4eed5-165">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="4eed5-166">Zuweisen einer Bezeichnung zu einer neuen Gruppe im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="4eed5-166">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="4eed5-167">Zuweisen einer Bezeichnung zu einer vorhandenen Gruppe im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="4eed5-167">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="4eed5-168">[Entfernen einer Bezeichnung von einer vorhandenen Gruppe im Azure-Portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="4eed5-168">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="4eed5-169">Anwenden einer Vertraulichkeitsbezeichnung auf ein neues Team</span><span class="sxs-lookup"><span data-stu-id="4eed5-169">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="4eed5-170">Benutzer können Vertraulichkeitsbezeichnungen auswählen, wenn sie neue Teams in Microsoft Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="4eed5-170">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="4eed5-171">Beim Auswählen der Vertraulichkeitsstufe werden die Datenschutzeinstellung bei Bedarf entsprechend geändert.</span><span class="sxs-lookup"><span data-stu-id="4eed5-171">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="4eed5-172">Abhängig von der für die Bezeichnung festgelegten Einstellung für den externen Benutzerzugriff können Benutzer Personen außerhalb der Organisation zum Team hinzufügen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="4eed5-172">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="4eed5-173">Weitere Informationen Vertraulichkeitsbezeichnungen für Teams</span><span class="sxs-lookup"><span data-stu-id="4eed5-173">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![Datenschutzeinstellung beim Erstellen eines neuen Teams](../media/privacy-setting-new-team.png)

<span data-ttu-id="4eed5-175">Nachdem Sie das Team erstellt haben, wird die Vertraulichkeitsbezeichnung in der oberen rechten Ecke aller Kanäle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4eed5-175">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![Die Vertraulichkeitsbezeichnung wird im Team angezeigt](../media/privacy-setting-teams.png)

<span data-ttu-id="4eed5-177">Der Dienst wendet auf die Office 365-Gruppe und die verbundene SharePoint-Teamwebsite automatisch die gleiche Vertraulichkeitsbezeichnung an.</span><span class="sxs-lookup"><span data-stu-id="4eed5-177">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="4eed5-178">Anwenden einer Vertraulichkeitsbezeichnung auf eine neue Gruppe in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="4eed5-178">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="4eed5-179">Wenn Sie in Outlook im Web eine neue Gruppe erstellen, können Sie die Option **Vertraulichkeit** für veröffentlichte Bezeichnungen auswählen oder ändern:</span><span class="sxs-lookup"><span data-stu-id="4eed5-179">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![Erstellen einer Gruppe und Auswählen einer Option unter "Vertraulichkeit"](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="4eed5-181">Anwenden einer Vertraulichkeitsbezeichnung auf eine neue Website</span><span class="sxs-lookup"><span data-stu-id="4eed5-181">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="4eed5-182">Administratoren und Endbenutzer können [beim Erstellen moderner Teamwebsites und Kommunikationswebsites](/sharepoint/create-site-collection) Vertraulichkeitsbezeichnungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="4eed5-182">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection).</span></span>

<span data-ttu-id="4eed5-183">Wenn Benutzer moderne Teamwebsites und Kommunikationswebsites erstellen, ist standardmäßig bereits eine Vertraulichkeitsbezeichnung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4eed5-183">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="4eed5-184">Benutzer können das Hilfesymbol auswählen, um weitere Informationen zu den Bezeichnungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4eed5-184">Users can select the help icon to learn more about the labels.</span></span>

![Erstellen einer Website und Auswählen einer Option unter "Vertraulichkeit"](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="4eed5-186">Wenn Benutzer zu der Website navigieren, werden der Name der Bezeichnung und die angewendeten Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4eed5-186">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Eine Website, auf die eine Vertraulichkeitsbezeichnung angewendet wurde](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="4eed5-188">Anzeigen von Vertraulichkeitsbezeichnungen im SharePoint Online Admin Center</span><span class="sxs-lookup"><span data-stu-id="4eed5-188">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="4eed5-189">Zum Anzeigen der angewendeten Vertraulichkeitsbezeichnungen verwenden Sie die Seite **Aktive Websites** im neuen SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="4eed5-189">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="4eed5-190">Möglicherweise müssen Sie zuerst die Spalte **Vertraulichkeit** hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="4eed5-190">You might need to first add the **Sensitivity** column:</span></span>

![Die Spalte "Vertraulichkeit" auf der Seite "Aktive Websites"](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="4eed5-192">[Weitere Informationen zum Verwalten von Websites im neuen SharePoint Admin Center](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="4eed5-192">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="4eed5-193">Ändern von Website- und Gruppeneinstellungen für eine Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="4eed5-193">Change site and group settings for a label</span></span>

<span data-ttu-id="4eed5-194">Wenn Sie eine Änderung an den Website- und Gruppeneinstellungen für eine Bezeichnung vornehmen, müssen Sie die folgenden PowerShell-Befehle ausführen, damit Ihre Teams, Websites und Gruppen die neuen Einstellungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4eed5-194">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="4eed5-195">Es wird empfohlen, die Website- und Gruppeneinstellungen für eine Bezeichnung nicht zu ändern, nachdem Sie die Bezeichnung auf mehrere Teams, Gruppen oder Websites angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="4eed5-195">As a best practice, don't the change site and group settings for a label after you've applied the label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="4eed5-196">Führen Sie die folgenden Befehle aus, um eine Verbindung mit PowerShell im Office 365 Security & Compliance Center herzustellen und die Liste der Vertraulichkeitsbezeichnungen und deren GUIDs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4eed5-196">Run the following commands to connect to Office 365 Security & Compliance Center PowerShell and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. <span data-ttu-id="4eed5-197">Notieren Sie sich die GUID für die Bezeichnung(en), die Sie geändert haben.</span><span class="sxs-lookup"><span data-stu-id="4eed5-197">Make a note of the GUID for the label or labels you have changed.</span></span>

3. <span data-ttu-id="4eed5-198">Stellen Sie jetzt eine Verbindung mit Exchange Online PowerShell her, und führen Sie das Cmdlet "Get-UnifiedGroup" aus. Geben Sie dabei die GUID der Bezeichnung anstelle der Beispiel-GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" an:</span><span class="sxs-lookup"><span data-stu-id="4eed5-198">Now connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. <span data-ttu-id="4eed5-199">Wenden Sie die Vertraulichkeitsbezeichnung für jede Gruppe unter Verwendung der Bezeichnungs-GUID anstelle der Beispiel-GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" erneut an:</span><span class="sxs-lookup"><span data-stu-id="4eed5-199">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="4eed5-200">Unterstützung der Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="4eed5-200">Support for the sensitivity labels</span></span>

<span data-ttu-id="4eed5-201">Sie können die Vertraulichkeitsbezeichnungen, die Sie für die Website- und Gruppeneinstellungen konfiguriert haben, mit den folgenden Apps und Diensten verwenden:</span><span class="sxs-lookup"><span data-stu-id="4eed5-201">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="4eed5-202">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4eed5-202">SharePoint Online</span></span>
- <span data-ttu-id="4eed5-203">Teams</span><span class="sxs-lookup"><span data-stu-id="4eed5-203">Teams</span></span>
- <span data-ttu-id="4eed5-204">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="4eed5-204">Outlook on the web</span></span>
- <span data-ttu-id="4eed5-205">SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="4eed5-205">SharePoint admin center</span></span>
- <span data-ttu-id="4eed5-206">Azure AD Admin Center</span><span class="sxs-lookup"><span data-stu-id="4eed5-206">Azure AD admin center</span></span>

<span data-ttu-id="4eed5-207">In folgenden anderen Apps und Diensten können Sie die Vertraulichkeitsbezeichnungen, die Sie für die Website- und Gruppeneinstellungen konfiguriert haben, derzeit nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="4eed5-207">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="4eed5-208">Outlook für Mac</span><span class="sxs-lookup"><span data-stu-id="4eed5-208">Outlook for the Mac</span></span>
- <span data-ttu-id="4eed5-209">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="4eed5-209">Outlook mobile</span></span>
- <span data-ttu-id="4eed5-210">Outlook Desktop für Windows</span><span class="sxs-lookup"><span data-stu-id="4eed5-210">Outlook desktop for Windows</span></span>
- <span data-ttu-id="4eed5-211">Forms</span><span class="sxs-lookup"><span data-stu-id="4eed5-211">Forms</span></span>
- <span data-ttu-id="4eed5-212">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4eed5-212">Dynamics 365</span></span>
- <span data-ttu-id="4eed5-213">Yammer</span><span class="sxs-lookup"><span data-stu-id="4eed5-213">Yammer</span></span>
- <span data-ttu-id="4eed5-214">Stream</span><span class="sxs-lookup"><span data-stu-id="4eed5-214">Stream</span></span>
- <span data-ttu-id="4eed5-215">Planner</span><span class="sxs-lookup"><span data-stu-id="4eed5-215">Planner</span></span>
- <span data-ttu-id="4eed5-216">Project</span><span class="sxs-lookup"><span data-stu-id="4eed5-216">Project</span></span>
- <span data-ttu-id="4eed5-217">PowerBI</span><span class="sxs-lookup"><span data-stu-id="4eed5-217">PowerBI</span></span>
- <span data-ttu-id="4eed5-218">Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="4eed5-218">Teams admin center</span></span>
- <span data-ttu-id="4eed5-219">Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="4eed5-219">Microsoft 365 admin center</span></span>
- <span data-ttu-id="4eed5-220">Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="4eed5-220">Exchange admin center</span></span>


## <a name="classic-azure-ad-site-classification"></a><span data-ttu-id="4eed5-221">Klassische Azure AD-Websiteklassifizierung</span><span class="sxs-lookup"><span data-stu-id="4eed5-221">Classic Azure AD site classification</span></span>

<span data-ttu-id="4eed5-222">Wenn Sie diese Vorschau aktivieren, unterstützt Office 365 die alten Klassifizierungen nicht mehr für neue Gruppen und SharePoint-Websites.</span><span class="sxs-lookup"><span data-stu-id="4eed5-222">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="4eed5-223">Bei vorhandenen Gruppen und Websites werden die alten Klassifizierungen jedoch weiterhin angezeigt, es sei denn, Sie konvertieren sie, um Vertraulichkeitsbezeichnungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4eed5-223">However, existing groups and sites still display the old classifications unless you convert them to use sensitivity labels.</span></span> <span data-ttu-id="4eed5-224">Alte Klassifizierungen schließen die Klassifizierung von "modernen" Websites ein, die Sie möglicherweise über Azure AD PowerShell oder die PnP Core-Bibliothek eingerichtet haben, in der Werte für die `ClassificationList`-Einstellung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4eed5-224">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="4eed5-225">Beispielsweise in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4eed5-225">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="4eed5-226">Weitere Informationen zur alten Klassifizierungsmethode finden Sie unter ["" ](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="4eed5-226">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="4eed5-227">Um Ihre alten Klassifizierungen in Vertraulichkeitsbezeichnungen umzuwandeln, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4eed5-227">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="4eed5-228">Verwenden vorhandener Bezeichnungen: Geben Sie die gewünschten Bezeichnungseinstellungen für Websites und Gruppen an, indem Sie bereits veröffentlichte Vertraulichkeitsbezeichnungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4eed5-228">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="4eed5-229">Erstellen neuer Bezeichnungen: Geben Sie die gewünschten Bezeichnungseinstellungen für Websites und Gruppen an, indem Sie neue Vertraulichkeitsbezeichnungen mit den gleichen Namen wie Ihre bestehenden Klassifizierungen erstellen und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4eed5-229">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="4eed5-230">Gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="4eed5-230">Then:</span></span> 

1. <span data-ttu-id="4eed5-231">Verwenden Sie PowerShell, um die Vertraulichkeitsbezeichnungen mithilfe von Namenszuordnung auf vorhandene Office 365-Gruppen und SharePoint-Websites anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="4eed5-231">Use PowerShell to apply the sensitivity labels to existing Office 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="4eed5-232">Entsprechende Anweisungen finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="4eed5-232">See the next section for instructions.</span></span>

2. <span data-ttu-id="4eed5-233">Entfernen Sie die alten Klassifizierungen der bestehenden Gruppen und Websites.</span><span class="sxs-lookup"><span data-stu-id="4eed5-233">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="4eed5-234">Sie können Benutzer zwar nicht daran hindern, neue Gruppen in Apps und Diensten, die noch keine Vertraulichkeitsbezeichnungen unterstützen, zu erstellen, aber Sie können wiederholt ein PowerShell-Skript ausführen, um nach neuen Gruppen zu suchen, die von Benutzern mit den alten Klassifizierungen erstellt wurden, und diese in Vertraulichkeitsbezeichnungen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="4eed5-234">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-office-365-groups-to-sensitivity-labels"></a><span data-ttu-id="4eed5-235">Verwenden von PowerShell, um Klassifizierungen für Office 365-Gruppen in Vertraulichkeitsbezeichnungen zu konvertieren</span><span class="sxs-lookup"><span data-stu-id="4eed5-235">Use PowerShell to convert classifications for Office 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="4eed5-236">Stellen Sie sicher, dass Sie die Version 16.0.19418.12000 oder höher der SharePoint Online-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="4eed5-236">Ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="4eed5-237">Wenn Sie bereits über die neueste Version verfügen, fahren Sie mit Schritt 4 fort.</span><span class="sxs-lookup"><span data-stu-id="4eed5-237">If you already have the latest version, skip to step 4.</span></span>

2. <span data-ttu-id="4eed5-238">Wenn Sie eine frühere Version der SharePoint-Online-Verwaltungsshell aus dem PowerShell-Katalog installiert haben, können Sie das Modul aktualisieren, indem Sie das folgende Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="4eed5-238">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>
    
    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

3. <span data-ttu-id="4eed5-239">Wenn Sie eine frühere Version der SharePoint Online-Verwaltungsshell installiert haben, wechseln Sie im Microsoft Download Center zu **Software hinzufügen oder entfernen**, und deinstallieren Sie die "SharePoint Online-Verwaltungsshell".</span><span class="sxs-lookup"><span data-stu-id="4eed5-239">If you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span> <span data-ttu-id="4eed5-240">Installieren Sie dann die neueste SharePoint-Online-Verwaltungsshell über das [Download Center](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="4eed5-240">Then, install the latest SharePoint Online Management Shell from the [Download Center](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="4eed5-241">Stellen Sie unter Verwendung eines Geschäfts-, Schul- oder Unikontos, das über globale Administrator- oder SharePoint-Administratorberechtigungen in Office 365 verfügt, eine Verbindung mit der SharePoint Online-Verwaltungsshell her.</span><span class="sxs-lookup"><span data-stu-id="4eed5-241">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="4eed5-242">Eine Anleitung dazu finden Sie unter [Erste Schritte mit der SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="4eed5-242">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

5. <span data-ttu-id="4eed5-243">Führen Sie die folgenden Befehle aus, um die Liste der Vertraulichkeitsbezeichnungen und deren GUIDs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4eed5-243">Run the following commands to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

6. <span data-ttu-id="4eed5-244">Notieren Sie sich die GUIDs für die Vertraulichkeitsbezeichnungen, die Sie auf Ihre Office 365-Gruppen anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4eed5-244">Make a note of the GUIDs for the sensitivity labels you want to apply to your Office 365 groups.</span></span>

7. <span data-ttu-id="4eed5-245">Verwenden Sie den folgenden Befehl als Beispiel, um die Liste der Gruppen abzurufen, die derzeit die Klassifizierung "Allgemein" aufweisen:</span><span class="sxs-lookup"><span data-stu-id="4eed5-245">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="4eed5-246">Fügen Sie für jede Gruppe die neue Vertraulichkeitsbezeichnungs-GUID hinzu.</span><span class="sxs-lookup"><span data-stu-id="4eed5-246">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="4eed5-247">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4eed5-247">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="4eed5-248">Überwachen von Vertraulichkeitsbezeichnungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="4eed5-248">Auditing sensitivity label activities</span></span>

<span data-ttu-id="4eed5-249">Wenn jemand ein Dokument auf eine Website hochlädt, die mit einer Vertraulichkeitsbezeichnung geschützt ist, und das Dokument eine Vertraulichkeitsbezeichnung mit [höherer Priorität](sensitivity-labels.md#label-priority-order-matters) als die auf die Website angewendete Vertraulichkeitsbezeichnung aufweist, wird diese Aktion nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="4eed5-249">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="4eed5-250">Angenommen, Sie haben die Bezeichnung **Allgemein** auf eine SharePoint-Website angewendet, und jemand lädt ein Dokument mit der Bezeichnung **Vertraulich** auf diese Site hoch.</span><span class="sxs-lookup"><span data-stu-id="4eed5-250">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="4eed5-251">Da eine Vertraulichkeitsbezeichnung mit einer höheren Priorität Inhalte kennzeichnet, die eine höhere Vertraulichkeitsstufe aufweisen, als Inhalte mit einer niedrigeren Priorität, könnte dies ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="4eed5-251">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="4eed5-252">Die Aktion wird zwar nicht blockiert, sie wird jedoch überwacht, sodass Sie Dokumente mit abweichender Bezeichnungspriorität identifizieren und bei Bedarf Maßnahmen ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="4eed5-252">Although the action isn't blocked, it is audited, so you can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="4eed5-253">Löschen oder verschieben Sie zum Beispiel das hochgeladene Dokument von der Website.</span><span class="sxs-lookup"><span data-stu-id="4eed5-253">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="4eed5-254">Es würde kein Sicherheitsrisiko darstellen, wenn die auf ein Dokument angewendete Vertraulichkeitsbezeichnung eine niedrigere Priorität aufweist als die auf die Website angewendete Vertraulichkeitsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="4eed5-254">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="4eed5-255">Angenommen, ein Dokument, das als **Allgemein** bezeichnet ist, wird auf eine Website hochgeladen, die mit **Vertraulich** bezeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="4eed5-255">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="4eed5-256">In diesem Szenario wird kein Überwachungsereignis erzeugt.</span><span class="sxs-lookup"><span data-stu-id="4eed5-256">In this scenario, an auditing event isn't generated.</span></span>

<span data-ttu-id="4eed5-257">Um das Überwachungsprotokoll nach diesem Ereignis zu durchsuchen, suchen Sie nach **Konflikt in Bezug auf die Vertraulichkeitsbezeichnung eines Dokuments** aus der Kategorie **Datei- und Seitenaktivitäten**.</span><span class="sxs-lookup"><span data-stu-id="4eed5-257">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="4eed5-258">Wenn jemand einer Website oder Gruppe eine Vertraulichkeitsbezeichnung hinzufügt oder eine Vertraulichkeitsbezeichnung von einer Website oder Gruppe entfernt, werden diese Aktivitäten ebenfalls überwacht.</span><span class="sxs-lookup"><span data-stu-id="4eed5-258">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited.</span></span> <span data-ttu-id="4eed5-259">Diese Ereignisse sind in der Kategorie [Vertraulichkeitsbezeichnungsaktivitäten](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) zu finden.</span><span class="sxs-lookup"><span data-stu-id="4eed5-259">These events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> 

<span data-ttu-id="4eed5-260">Anweisungen zum Durchsuchen des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="4eed5-260">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="4eed5-261">Problembehandlung bei der Bereitstellung von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="4eed5-261">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="4eed5-262">Sie haben Probleme mit Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites?</span><span class="sxs-lookup"><span data-stu-id="4eed5-262">Having problems with sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="4eed5-263">Überprüfen Sie die Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4eed5-263">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="4eed5-264">Bezeichnungen sind nach der Veröffentlichung nicht sichtbar</span><span class="sxs-lookup"><span data-stu-id="4eed5-264">Labels not visible after publishing</span></span>
<span data-ttu-id="4eed5-265">Wenn beim Erstellen eines Teams oder einer Office 365-Gruppe Probleme auftreten, nachdem Sie diese Einstellungen aktiviert oder die Beschreibung einer Vertraulichkeitsbezeichnung geändert haben, warten Sie nach dem Speichern der Bezeichnungsänderungen ein paar Stunden, und versuchen Sie dann erneut, das Team oder die Gruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4eed5-265">If you experience issues when you create a team or Office 365 group after you enable these settings or modify a sensitivity label's description, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="4eed5-266">Informationen hierzu finden Sie unter [Planen des Rollouts nach Erstellung oder Änderung einer Vertraulichkeitsbezeichnung](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="4eed5-266">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="4eed5-267">Wenn die neue Vertraulichkeitsbezeichnung in SharePoint Online weiterhin nicht angezeigt wird, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="4eed5-267">If you are still not able to see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="4eed5-268">Fehler beim Erstellen von Teams, Gruppen oder SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="4eed5-268">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="4eed5-269">Wenn während der öffentlichen Vorschau Erstellungsfehler auftreten, haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="4eed5-269">If you experience creation errors during the public preview, you have two options:</span></span>

- <span data-ttu-id="4eed5-270">Stellen Sie sicher, dass Vertraulichkeitsbezeichnungen für keinen Benutzer obligatorisch sind.</span><span class="sxs-lookup"><span data-stu-id="4eed5-270">Ensure that sensitivity labels are not mandatory for any user.</span></span>

- <span data-ttu-id="4eed5-271">Sie können Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites unter Verwendung der Anweisungen im Abschnitt [Aktivieren der Unterstützung von Vertraulichkeitsbezeichnungen in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell) deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4eed5-271">You can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="4eed5-272">Um die Vorschau zu deaktivieren, müssen Sie jedoch in Schritt 5 die Funktion mit `$setting["EnableMIPLabels"] = "False"` deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4eed5-272">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

