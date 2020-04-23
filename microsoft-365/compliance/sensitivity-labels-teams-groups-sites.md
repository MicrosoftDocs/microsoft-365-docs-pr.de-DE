---
title: Verwenden von Vertraulichkeitsbezeichnungen für Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites (öffentliche Vorschau)
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
description: Verwenden Sie Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in SharePoint- und Microsoft Teams-Websites sowie in Microsoft 365-Gruppen.
ms.openlocfilehash: b9ca945ac90ab27d3bc25f1022070eff4737bc10
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631302"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="c06cc-103">Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites (öffentliche Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c06cc-103">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites (public preview)</span></span>

><span data-ttu-id="c06cc-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="c06cc-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="c06cc-105">Wenn Sie im [Microsoft 365 Compliance Center](https://protection.office.com/) Vertraulichkeitsbezeichnungen erstellen, können Sie sie jetzt auf die folgenden Container anwenden: Microsoft Teams-Websites, Microsoft 365-Gruppen und SharePoint-Websites.</span><span class="sxs-lookup"><span data-stu-id="c06cc-105">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams sites, Microsoft 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="c06cc-106">Verwenden Sie die folgenden Bezeichnungseinstellungen zum Schutz von Inhalt in diesen Containern:</span><span class="sxs-lookup"><span data-stu-id="c06cc-106">Use the following label settings to help protect the content in those containers:</span></span>

- <span data-ttu-id="c06cc-107">Datenschutz (öffentlich oder privat) für mit einer Microsoft 365-Gruppe verbundene Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="c06cc-107">Privacy (public or private) of Microsoft 365 group-connected teams sites</span></span>
- <span data-ttu-id="c06cc-108">Zugriff externer Benutzer</span><span class="sxs-lookup"><span data-stu-id="c06cc-108">External users access</span></span>
- <span data-ttu-id="c06cc-109">Zugriff von nicht verwalteten Geräten aus</span><span class="sxs-lookup"><span data-stu-id="c06cc-109">Access from unmanaged devices</span></span> 

<span data-ttu-id="c06cc-110">Wenn Sie diese Bezeichnung auf einen unterstützten Container anwenden, wendet die Bezeichnung die konfigurierten Optionen automatisch auf die verbundene Website oder Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="c06cc-110">When you apply this label to a supported container, the label automatically applies the configured options to the connected site or group.</span></span> 

<span data-ttu-id="c06cc-111">Der Inhalt in diesen Containern erbt die Bezeichnung jedoch nicht für Einstellungen wie Bezeichnungsnamen, visuelle Markierungen oder Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="c06cc-111">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="c06cc-112">[Aktivieren Sie von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive](sensitivity-labels-sharepoint-onedrive-files.md), damit Benutzer Bezeichnungen auf ihre Dokumente in SharePoint- oder Teamwebsites anwenden können.</span><span class="sxs-lookup"><span data-stu-id="c06cc-112">So that users can label their documents in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="c06cc-113">Informationen zur öffentlichen Vorschau für Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="c06cc-113">About the public preview for Microsoft Teams, Microsoft 365 Groups, and SharePoint sites</span></span>

<span data-ttu-id="c06cc-114">Vertraulichkeitsbezeichnungen für Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites werden schrittweise für Mandanten bereitgestellt und können sich vor der endgültigen Version ändern.</span><span class="sxs-lookup"><span data-stu-id="c06cc-114">Sensitivity labels for Microsoft Teams, Microsoft 365 Groups, and SharePoint sites are in gradual rollout to tenants and might change before final release.</span></span> <span data-ttu-id="c06cc-115">Diese öffentliche Vorschau kann nicht mit Office 365-Netzwerken für die Inhaltsübermittlung (Content Delivery Network, CDN) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c06cc-115">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="c06cc-116">Bevor Sie diese Vorschau aktivieren und Vertraulichkeitsbezeichnungen für die neuen Einstellungen konfigurieren, können die Benutzer Vertraulichkeitsbezeichnungen in ihren Apps anzeigen und anwenden.</span><span class="sxs-lookup"><span data-stu-id="c06cc-116">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="c06cc-117">Beispielsweise aus Word:</span><span class="sxs-lookup"><span data-stu-id="c06cc-117">For example, from Word:</span></span>

![Eine in der Word-Desktop-App angezeigte Vertraulichkeitsbezeichnung](../media/sensitivity-label-word.png)

<span data-ttu-id="c06cc-119">Nachdem Sie diese Vorschau aktiviert und konfiguriert haben, können Benutzer Vertraulichkeitsbezeichnungen außerdem für Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites anzeigen und anwenden.</span><span class="sxs-lookup"><span data-stu-id="c06cc-119">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Microsoft 365 Groups, and SharePoint sites.</span></span> <span data-ttu-id="c06cc-120">Beispielsweise, wenn eine neue Teamwebsite in SharePoint erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="c06cc-120">For example, when you create a new team site from SharePoint:</span></span>

![Eine Vertraulichkeitsbezeichnung beim Erstellen einer Teamwebsite in SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="c06cc-122">Aktivieren dieser Vorschau und Synchronisieren von Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="c06cc-122">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="c06cc-123">Weil dieses Feature die Azure AD-Funktionen nutzt, führen Sie zum Aktivieren der Vorschau die Anleitungen in der Azure AD-Dokumentation aus: [Zuweisen von Vertraulichkeitsbezeichnungen zu Microsoft 365-Gruppen in Azure Active Directory (Vorschau)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="c06cc-123">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Microsoft 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="c06cc-124">[Stellen Sie jetzt eine Verbindung mit Office 365 Security & Compliance Center PowerShell her](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c06cc-124">Now [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="c06cc-125">Melden Sie sich beispielsweise bei einer PowerShell-Sitzung, die Sie als Administrator ausführen, mit einem globalen Administratorkonto an:</span><span class="sxs-lookup"><span data-stu-id="c06cc-125">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

3. <span data-ttu-id="c06cc-126">Führen Sie den folgenden Befehl aus, um Ihre Vertraulichkeitsbezeichnungen mit Azure AD zu synchronisieren, damit sie mit Microsoft 365-Gruppen verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="c06cc-126">Run the following command to synchronize your sensitivity labels to Azure AD, so that they can be used with Microsoft 365 Groups:</span></span>
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="c06cc-127">Konfigurieren von Website- und Gruppeneinstellungen beim Erstellen oder Bearbeiten von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="c06cc-127">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="c06cc-128">Sie können jetzt Vertraulichkeitsbezeichnungen erstellen oder bearbeiten, die für Websites und Gruppen verfügbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="c06cc-128">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="c06cc-129">Durch Aktivieren der Vorschau wird eine neue Seite im Assistenten für Vertraulichkeitsbezeichnungen verfügbar: **Website- und Gruppeneinstellungen**</span><span class="sxs-lookup"><span data-stu-id="c06cc-129">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="c06cc-130">Wenn Sie Hilfe beim Erstellen oder Bearbeiten einer Vertraulichkeitsbezeichnung benötigen, lesen Sie die Anweisungen unter [Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="c06cc-130">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="c06cc-131">Auf dieser neuen Seite **Website- und Gruppeneinstellungen** können Sie die Einstellungen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="c06cc-131">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="c06cc-132">**Datenschutz für mit Microsoft 365-Gruppen verbundene Teams-Websites**: Derzeit erfolgt das Rollout der Standardeinstellung **Keine. Benutzer kann wählen, wer auf die Website zugreifen kann** an die Mandanten.</span><span class="sxs-lookup"><span data-stu-id="c06cc-132">**Privacy of Microsoft 365 group-connected teams sites**: The default setting of **None - let user chose who can access the site** is currently rolling out to tenants.</span></span> <span data-ttu-id="c06cc-133">Behalten Sie diese Standardeinstellung bei, wenn Sie den Inhalt im Container mit Vertraulichkeitsbezeichnungen schützen möchten, die Benutzer aber trotzdem selbst Datenschutzeinstellungen konfigurieren können sollen.</span><span class="sxs-lookup"><span data-stu-id="c06cc-133">Keep this default setting when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
    
    <span data-ttu-id="c06cc-134">Wählen Sie **Öffentlich** oder**Privat** aus, um die Datenschutzeinstellung festzulegen und zu sperren, wenn Sie diese Bezeichnung auf den Container anwenden.</span><span class="sxs-lookup"><span data-stu-id="c06cc-134">Select **Public** or**Private** to set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="c06cc-135">Wählen Sie **Öffentlich** aus, wenn Sie möchten, dass jeder in Ihrer Organisation auf die Teamwebsite oder Gruppe, auf die diese Bezeichnung angewendet wird, zugreifen kann, und **Privat**, wenn Sie den Zugriff auf genehmigte Mitglieder in Ihrer Organisation beschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="c06cc-135">Choose **Public** if you want anyone in your organization to access the team site or group where this label is applied, or **Private** if you want access to be restricted to only approved members in your organization.</span></span> 
    
    <span data-ttu-id="c06cc-136">Die Einstellung **Öffentlich** oder **Privat** ersetzt alle für das Team oder die Gruppe möglicherweise früher konfigurierten Datenschutzeinstellungen und sperrt den Datenschutzwert, sodass er nur geändert werden kann, wenn zuvor die Vertraulichkeitsbezeichnung vom Container entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="c06cc-136">The **Public** or **Private** setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="c06cc-137">Nachdem Sie die Vertraulichkeitsbezeichnung entfernt haben, bleibt die Datenschutzeinstellung der Bezeichnung erhalten, aber Benutzer können sie jetzt wieder ändern.</span><span class="sxs-lookup"><span data-stu-id="c06cc-137">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>

- <span data-ttu-id="c06cc-138">**Zugriff für externe Benutzer**: Steuern Sie, ob der Gruppenbesitzer [Gäste zur Gruppe hinzufügen](/office365/admin/create-groups/manage-guest-access-in-groups) kann.</span><span class="sxs-lookup"><span data-stu-id="c06cc-138">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="c06cc-139">**Nicht verwaltete Geräte**: Erlauben Sie für [nicht verwaltete Geräte](/sharepoint/control-access-from-unmanaged-devices) vollen Zugriff oder nur Webzugriff, bzw. blockieren Sie den Zugriff vollständig.</span><span class="sxs-lookup"><span data-stu-id="c06cc-139">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> 

![Die Registerkarte "Website- und Gruppeneinstellungen"](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="c06cc-141">Wenn Sie eine Bezeichnung auf ein Team, eine Gruppe oder eine Website anwenden, werden nur diese Website- und Gruppeneinstellungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="c06cc-141">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="c06cc-142">Andere Bezeichnungseinstellungen (z. B. Verschlüsselung und Inhaltskennzeichnung) werden nicht auf die Inhalte innerhalb des Teams, der Gruppen oder der Website angewendet.</span><span class="sxs-lookup"><span data-stu-id="c06cc-142">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="c06cc-143">Schrittweises Rollout für Mandanten: Wenn Benutzer Teams, Gruppen und Websites erstellen, stehen nur Bezeichnungen mit den Website- und Gruppeneinstellungen zur Auswahl.</span><span class="sxs-lookup"><span data-stu-id="c06cc-143">Gradually rolling out to tenants: Only labels with the site and group settings will be available to select when users create teams, groups, and sites.</span></span> <span data-ttu-id="c06cc-144">Wenn Sie derzeit eine Bezeichnung auf einen Container anwenden können, die Website- und Gruppeneinstellungen für die Bezeichnung jedoch nicht aktiviert sind, wird nur der Name der Bezeichnung auf den Container angewendet.</span><span class="sxs-lookup"><span data-stu-id="c06cc-144">If you can currently apply a label to a container when the label doesn't have the site and group settings enabled, only the label name is applied to the container.</span></span>

<span data-ttu-id="c06cc-145">Wenn Ihre Vertraulichkeitskennzeichnung noch nicht veröffentlicht wurde, veröffentlichen Sie diese jetzt, indem Sie sie[einer Richtlinie für Vertraulichkeitskennzeichnungen hinzufügen](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="c06cc-145">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="c06cc-146">Diejenigen Benutzer, denen eine Richtlinie zur Vertraulichkeitskennzeichnung zugeordnet ist, die diese Kennzeichnung beinhaltet, können diese für Websites und Gruppen auswählen.</span><span class="sxs-lookup"><span data-stu-id="c06cc-146">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

<span data-ttu-id="c06cc-147">Aus der Bezeichnungsrichtlinie gilt nur die Richtlinieneinstellung **Diese Bezeichnung standardmäßig auf Dokumente und E-Mail anwenden**, wenn Sie die Bezeichnung auf Container anwenden.</span><span class="sxs-lookup"><span data-stu-id="c06cc-147">From the label policy, only the policy setting **Apply this label by default to documents and email** is applicable when you apply this label to containers.</span></span> <span data-ttu-id="c06cc-148">Es werden keine anderen Richtlinieneinstellungen angewendet, beispielsweise obligatorische Bezeichnungen, das Anfordern von Benutzerbegründungen sowie ein Link zur benutzerdefinierten Hilfeseite.</span><span class="sxs-lookup"><span data-stu-id="c06cc-148">Other policy settings are not applied, which include mandatory labeling, requiring user justification, and a link to the custom help page.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="c06cc-149">Verwaltung von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="c06cc-149">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="c06cc-150">Das Erstellen, Ändern und Löschen von Vertraulichkeitsbezeichnungen, die Sie für Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden, erfordert eine sorgfältige Abstimmung mit der Veröffentlichung von Bezeichnungsrichtlinien für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c06cc-150">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Microsoft 365 Groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="c06cc-151">Vermeiden Sie Erstellungsfehler für Websites und Gruppen, die sich auf alle Benutzer auswirken, indem Sie die nachstehenden Anweisungen beachten.</span><span class="sxs-lookup"><span data-stu-id="c06cc-151">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="c06cc-152">**Erstellen und Veröffentlichen von Bezeichnungen:**</span><span class="sxs-lookup"><span data-stu-id="c06cc-152">**Creating and publishing labels:**</span></span>

<span data-ttu-id="c06cc-153">Nach der Erstellung und Veröffentlichung einer Vertraulichkeitsbezeichnung kann es bis zu 24 Stunden dauern, bis die Bezeichnung für Benutzer in Teams, Gruppen und Websites sichtbar wird.</span><span class="sxs-lookup"><span data-stu-id="c06cc-153">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="c06cc-154">Führen Sie die folgenden Schritte aus, um eine Bezeichnung für alle Benutzer im Mandanten zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="c06cc-154">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="c06cc-155">Erstellen Sie die Vertraulichkeitsbezeichnung, und veröffentlichen Sie sie nur für einige Benutzerkonten im Mandanten.</span><span class="sxs-lookup"><span data-stu-id="c06cc-155">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="c06cc-156">Warten Sie 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="c06cc-156">Wait for 24 hours.</span></span>

3. <span data-ttu-id="c06cc-157">Nach Ablauf dieser 24 Stunden erstellen Sie mit einem der in Schritt 1 angegebenen Benutzerkonten ein Team, eine Microsoft 365-Gruppe oder eine SharePoint-Website mit der in Schritt 1 erstellten Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="c06cc-157">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Microsoft 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="c06cc-158">Wenn während des Erstellungsvorgangs für Schritt 3 keine Fehler auftreten, veröffentlichen Sie die Bezeichnung für alle Benutzer in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="c06cc-158">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="c06cc-159">Wenn Fehler auftreten, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="c06cc-159">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="c06cc-160">**Ändern und Löschen von veröffentlichten Bezeichnungen:**</span><span class="sxs-lookup"><span data-stu-id="c06cc-160">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="c06cc-161">Wenn Sie eine Vertraulichkeitsbezeichnung, deren Website- und Gruppeneinstellungen aktiviert sind, ändern oder löschen, und diese Bezeichnung in einer oder mehreren Bezeichnungsrichtlinien enthalten ist, kann dies zu Erstellungsfehlern für alle Teams, Gruppen und Websites führen.</span><span class="sxs-lookup"><span data-stu-id="c06cc-161">If you modify or delete a sensitivity label with the site and group settings enabled, and that label is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="c06cc-162">Folgen Sie dieser Anleitung, um dieses Problem zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="c06cc-162">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="c06cc-163">Entfernen Sie die Vertraulichkeitsbezeichnung aus allen Bezeichnungsrichtlinien, in denen die Bezeichnung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c06cc-163">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="c06cc-164">Warten Sie 48 Stunden.</span><span class="sxs-lookup"><span data-stu-id="c06cc-164">Wait for 48 hours.</span></span>

3. <span data-ttu-id="c06cc-165">Versuchen Sie nach 48 Stunden, ein Team, eine Gruppe oder eine Website zu erstellen, und vergewissern Sie sich, dass die Bezeichnung nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c06cc-165">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="c06cc-166">Wenn die Vertraulichkeitsbezeichnung nicht angezeigt wird, können Sie sie jetzt bedenkenlos ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="c06cc-166">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="c06cc-167">Wird die Bezeichnung weiterhin angezeigt, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="c06cc-167">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-microsoft-365-groups"></a><span data-ttu-id="c06cc-168">Zuweisen von Vertraulichkeitsbezeichnungen zu Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="c06cc-168">Assign sensitivity labels to Microsoft 365 Groups</span></span>

<span data-ttu-id="c06cc-169">Jetzt können Sie die Vertraulichkeitsbezeichnung(en) auf Microsoft 365-Gruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="c06cc-169">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups.</span></span> <span data-ttu-id="c06cc-170">Kehren Sie für weitere Anweisungen zur Azure AD-Dokumentation zurück:</span><span class="sxs-lookup"><span data-stu-id="c06cc-170">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="c06cc-171">Zuweisen einer Bezeichnung zu einer neuen Gruppe im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="c06cc-171">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="c06cc-172">Zuweisen einer Bezeichnung zu einer vorhandenen Gruppe im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="c06cc-172">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="c06cc-173">[Entfernen einer Bezeichnung von einer vorhandenen Gruppe im Azure-Portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c06cc-173">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="c06cc-174">Anwenden einer Vertraulichkeitsbezeichnung auf ein neues Team</span><span class="sxs-lookup"><span data-stu-id="c06cc-174">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="c06cc-175">Benutzer können Vertraulichkeitsbezeichnungen auswählen, wenn sie neue Teams in Microsoft Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="c06cc-175">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="c06cc-176">Wenn sie die Bezeichnung aus der Dropdownliste **Vertraulichkeit** auswählen, kann sich die Datenschutzeinstellung entsprechend der Bezeichnungskonfiguration ändern.</span><span class="sxs-lookup"><span data-stu-id="c06cc-176">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="c06cc-177">Abhängig von der für die Bezeichnung festgelegten Einstellung für den externen Benutzerzugriff können Benutzer Personen außerhalb der Organisation zum Team hinzufügen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="c06cc-177">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="c06cc-178">Weitere Informationen Vertraulichkeitsbezeichnungen für Teams</span><span class="sxs-lookup"><span data-stu-id="c06cc-178">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![Datenschutzeinstellung beim Erstellen eines neuen Teams](../media/privacy-setting-new-team.png)

<span data-ttu-id="c06cc-180">Nachdem Sie das Team erstellt haben, wird die Vertraulichkeitsbezeichnung in der oberen rechten Ecke aller Kanäle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c06cc-180">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![Die Vertraulichkeitsbezeichnung wird im Team angezeigt](../media/privacy-setting-teams.png)

<span data-ttu-id="c06cc-182">Der Dienst wendet auf die Microsoft 365-Gruppe und die verbundene SharePoint-Teamwebsite automatisch dieselbe Vertraulichkeitsbezeichnung an.</span><span class="sxs-lookup"><span data-stu-id="c06cc-182">The service automatically applies the same sensitivity label to the Microsoft 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="c06cc-183">Anwenden einer Vertraulichkeitsbezeichnung auf eine neue Gruppe in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="c06cc-183">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="c06cc-184">Wenn Sie in Outlook im Web eine neue Gruppe erstellen, können Sie die Option **Vertraulichkeit** für veröffentlichte Bezeichnungen auswählen oder ändern:</span><span class="sxs-lookup"><span data-stu-id="c06cc-184">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![Erstellen einer Gruppe und Auswählen einer Option unter "Vertraulichkeit"](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="c06cc-186">Anwenden einer Vertraulichkeitsbezeichnung auf eine neue Website</span><span class="sxs-lookup"><span data-stu-id="c06cc-186">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="c06cc-187">Administratoren und Endbenutzer können [beim Erstellen moderner Teamwebsites und Kommunikationswebsites](/sharepoint/create-site-collection) Vertraulichkeitsbezeichnungen auswählen, und **Erweiterte Einstellungen** erweitern:</span><span class="sxs-lookup"><span data-stu-id="c06cc-187">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![Erstellen einer Website und Auswählen einer Option unter "Vertraulichkeit"](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="c06cc-189">In der Dropdownliste werden die Bezeichnungsnamen für die Auswahl angezeigt, und das Hilfesymbol zeigt alle Bezeichnungsnamen mit entsprechender QuickInfo an, was Benutzern dabei helfen kann, die richtige Bezeichnung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c06cc-189">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="c06cc-190">Wenn die Bezeichnung angewendet wurde und Benutzer zur Website navigieren, werden der Name der Bezeichnung und die angewendeten Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c06cc-190">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="c06cc-191">So wurde dieser Website beispielsweise die Bezeichnung **Vertraulich** zugewiesen und die Datenschutzeinstellung auf **Privat** festgelegt:</span><span class="sxs-lookup"><span data-stu-id="c06cc-191">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![Eine Website, auf die eine Vertraulichkeitsbezeichnung angewendet wurde](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="c06cc-193">Anzeigen von Vertraulichkeitsbezeichnungen im SharePoint Online Admin Center</span><span class="sxs-lookup"><span data-stu-id="c06cc-193">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="c06cc-194">Zum Anzeigen der angewendeten Vertraulichkeitsbezeichnungen verwenden Sie die Seite **Aktive Websites** im neuen SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="c06cc-194">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="c06cc-195">Möglicherweise müssen Sie zuerst die Spalte **Vertraulichkeit** hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="c06cc-195">You might need to first add the **Sensitivity** column:</span></span>

![Die Spalte "Vertraulichkeit" auf der Seite "Aktive Websites"](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="c06cc-197">[Weitere Informationen zum Verwalten von Websites im neuen SharePoint Admin Center](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="c06cc-197">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="c06cc-198">Ändern von Website- und Gruppeneinstellungen für eine Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="c06cc-198">Change site and group settings for a label</span></span>

<span data-ttu-id="c06cc-199">Wenn Sie eine Änderung an den Website- und Gruppeneinstellungen für eine Bezeichnung vornehmen, müssen Sie die folgenden PowerShell-Befehle ausführen, damit Ihre Teams, Websites und Gruppen die neuen Einstellungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c06cc-199">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="c06cc-200">Es wird empfohlen, die Website- und Gruppeneinstellungen für eine Bezeichnung nicht zu ändern, nachdem Sie die Vertraulichkeitsbezeichnung auf mehrere Teams, Gruppen oder Websites angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="c06cc-200">As a best practice, don't the change site and group settings for a label after you've applied the sensitivity label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="c06cc-201">Stellen Sie [zunächst eine Verbindung mit Office 365 Security & Compliance Center PowerShell her](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c06cc-201">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="c06cc-202">Melden Sie sich beispielsweise bei einer PowerShell-Sitzung, die Sie als Administrator ausführen, mit einem globalen Administratorkonto an:</span><span class="sxs-lookup"><span data-stu-id="c06cc-202">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="c06cc-203">Führen Sie das Cmdlet [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) aus, um die Liste der Vertraulichkeitsbezeichnungen und deren GUIDs abzurufen:</span><span class="sxs-lookup"><span data-stu-id="c06cc-203">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) cmdlet:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="c06cc-204">Notieren Sie sich die GUID für die Bezeichnung(en), die Sie geändert haben.</span><span class="sxs-lookup"><span data-stu-id="c06cc-204">Make a note of the GUID for the label or labels you have changed.</span></span>

4. <span data-ttu-id="c06cc-205">[Stellen Sie jetzt eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="c06cc-205">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
    <span data-ttu-id="c06cc-206">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c06cc-206">For example:</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```
    
5. <span data-ttu-id="c06cc-207">Führen Sie das Cmdlet [Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) aus. Geben Sie dabei die GUID der Bezeichnung anstelle der Beispiel-GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" an:</span><span class="sxs-lookup"><span data-stu-id="c06cc-207">Run the [Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

6. <span data-ttu-id="c06cc-208">Wenden Sie die Vertraulichkeitsbezeichnung für jede Gruppe unter Verwendung der Bezeichnungs-GUID anstelle der Beispiel-GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" erneut an:</span><span class="sxs-lookup"><span data-stu-id="c06cc-208">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="c06cc-209">Unterstützung der Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="c06cc-209">Support for the sensitivity labels</span></span>

<span data-ttu-id="c06cc-210">Sie können die Vertraulichkeitsbezeichnungen, die Sie für die Website- und Gruppeneinstellungen konfiguriert haben, mit den folgenden Apps und Diensten verwenden:</span><span class="sxs-lookup"><span data-stu-id="c06cc-210">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="c06cc-211">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c06cc-211">SharePoint Online</span></span>
- <span data-ttu-id="c06cc-212">Teams</span><span class="sxs-lookup"><span data-stu-id="c06cc-212">Teams</span></span>
- <span data-ttu-id="c06cc-213">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="c06cc-213">Outlook on the web</span></span>
- <span data-ttu-id="c06cc-214">SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="c06cc-214">SharePoint admin center</span></span>
- <span data-ttu-id="c06cc-215">Azure AD Admin Center</span><span class="sxs-lookup"><span data-stu-id="c06cc-215">Azure AD admin center</span></span>

<span data-ttu-id="c06cc-216">In folgenden anderen Apps und Diensten können Sie die Vertraulichkeitsbezeichnungen, die Sie für die Website- und Gruppeneinstellungen konfiguriert haben, derzeit nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="c06cc-216">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="c06cc-217">Outlook für Mac</span><span class="sxs-lookup"><span data-stu-id="c06cc-217">Outlook for the Mac</span></span>
- <span data-ttu-id="c06cc-218">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="c06cc-218">Outlook mobile</span></span>
- <span data-ttu-id="c06cc-219">Outlook Desktop für Windows</span><span class="sxs-lookup"><span data-stu-id="c06cc-219">Outlook desktop for Windows</span></span>
- <span data-ttu-id="c06cc-220">Forms</span><span class="sxs-lookup"><span data-stu-id="c06cc-220">Forms</span></span>
- <span data-ttu-id="c06cc-221">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c06cc-221">Dynamics 365</span></span>
- <span data-ttu-id="c06cc-222">Yammer</span><span class="sxs-lookup"><span data-stu-id="c06cc-222">Yammer</span></span>
- <span data-ttu-id="c06cc-223">Stream</span><span class="sxs-lookup"><span data-stu-id="c06cc-223">Stream</span></span>
- <span data-ttu-id="c06cc-224">Planner</span><span class="sxs-lookup"><span data-stu-id="c06cc-224">Planner</span></span>
- <span data-ttu-id="c06cc-225">Project</span><span class="sxs-lookup"><span data-stu-id="c06cc-225">Project</span></span>
- <span data-ttu-id="c06cc-226">PowerBI</span><span class="sxs-lookup"><span data-stu-id="c06cc-226">PowerBI</span></span>
- <span data-ttu-id="c06cc-227">Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="c06cc-227">Teams admin center</span></span>
- <span data-ttu-id="c06cc-228">Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="c06cc-228">Microsoft 365 admin center</span></span>
- <span data-ttu-id="c06cc-229">Exchange Admin-Center</span><span class="sxs-lookup"><span data-stu-id="c06cc-229">Exchange admin center</span></span>


## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="c06cc-230">Klassische Azure AD-Gruppenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="c06cc-230">Classic Azure AD group classification</span></span>

<span data-ttu-id="c06cc-231">Wenn Sie diese Vorschau aktivieren, unterstützt Microsoft 365 die alten Klassifikationen für neue Office 365-Gruppen und SharePoint Online-Websites nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="c06cc-231">Microsoft 365 no longer supports the old classifications for new Office 365 groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="c06cc-232">Bestehende Gruppen und Sites zeigen jedoch weiterhin die alten Klassifizierungswerte an, es sei denn, Sie konvertieren sie zur Verwendung von Vertraulichkeitsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="c06cc-232">However, existing groups and sites still display the old classification values unless you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="c06cc-233">Ein Beispiel dafür, wie Sie die alte Gruppenklassifizierung für Microsoft Office SharePoint Online verwendet haben könnten, finden Sie unter [Klassifizierung "moderner" Microsoft Office SharePoint Online-Websites](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="c06cc-233">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="c06cc-234">Diese Klassifizierungen wurden konfiguriert, indem Azure AD PowerShell oder die PnP-Kernbibliothek verwendet und Werte für die Einstellung `ClassificationList` festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="c06cc-234">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting.</span></span> <span data-ttu-id="c06cc-235">Wenn in Ihrem Mandanten Klassifizierungswerte definiert sind, werden sie angezeigt, wenn Sie den folgenden Befehl aus dem [AzureADPreview PowerShell-Modul](https://www.powershellgallery.com/packages/AzureADPreview) ausführen:</span><span class="sxs-lookup"><span data-stu-id="c06cc-235">If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="c06cc-236">Um Ihre alten Klassifizierungen in Vertraulichkeitsbezeichnungen umzuwandeln, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c06cc-236">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="c06cc-237">Verwenden vorhandener Bezeichnungen: Geben Sie die gewünschten Bezeichnungseinstellungen für Websites und Gruppen an, indem Sie bereits veröffentlichte Vertraulichkeitsbezeichnungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c06cc-237">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="c06cc-238">Erstellen neuer Bezeichnungen: Geben Sie die gewünschten Bezeichnungseinstellungen für Websites und Gruppen an, indem Sie neue Vertraulichkeitsbezeichnungen mit den gleichen Namen wie Ihre bestehenden Klassifizierungen erstellen und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="c06cc-238">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="c06cc-239">Gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="c06cc-239">Then:</span></span> 

1. <span data-ttu-id="c06cc-240">Verwenden Sie PowerShell, um die Vertraulichkeitsbezeichnungen mithilfe von Namenszuordnung auf vorhandene Microsoft 365-Gruppen und SharePoint-Websites anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="c06cc-240">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="c06cc-241">Entsprechende Anweisungen finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c06cc-241">See the next section for instructions.</span></span>

2. <span data-ttu-id="c06cc-242">Entfernen Sie die alten Klassifizierungen der bestehenden Gruppen und Websites.</span><span class="sxs-lookup"><span data-stu-id="c06cc-242">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="c06cc-243">Sie können Benutzer zwar nicht daran hindern, neue Gruppen in Apps und Diensten, die noch keine Vertraulichkeitsbezeichnungen unterstützen, zu erstellen, aber Sie können wiederholt ein PowerShell-Skript ausführen, um nach neuen Gruppen zu suchen, die von Benutzern mit den alten Klassifizierungen erstellt wurden, und diese in Vertraulichkeitsbezeichnungen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="c06cc-243">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a><span data-ttu-id="c06cc-244">Verwenden von PowerShell, um Klassifizierungen für Microsoft 365-Gruppen in Vertraulichkeitsbezeichnungen zu konvertieren</span><span class="sxs-lookup"><span data-stu-id="c06cc-244">Use PowerShell to convert classifications for Microsoft 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="c06cc-245">Stellen Sie [zunächst eine Verbindung mit Office 365 Security & Compliance Center PowerShell her](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c06cc-245">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="c06cc-246">Melden Sie sich beispielsweise bei einer PowerShell-Sitzung, die Sie als Administrator ausführen, mit einem globalen Administratorkonto an:</span><span class="sxs-lookup"><span data-stu-id="c06cc-246">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="c06cc-247">Führen Sie das Cmdlet [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) aus, um die Liste der Vertraulichkeitsbezeichnungen und deren GUIDs abzurufen:</span><span class="sxs-lookup"><span data-stu-id="c06cc-247">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) cmdlet:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="c06cc-248">Notieren Sie sich die GUIDs für die Vertraulichkeitsbezeichnungen, die Sie auf Ihre Office 365-Gruppen anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c06cc-248">Make a note of the GUIDs for the sensitivity labels you want to apply to your Office 365 groups.</span></span>

4. <span data-ttu-id="c06cc-249">[Stellen Sie jetzt eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="c06cc-249">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
    <span data-ttu-id="c06cc-250">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c06cc-250">For example:</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```

6. <span data-ttu-id="c06cc-251">Notieren Sie sich die GUIDs für die Vertraulichkeitsbezeichnungen, die Sie auf Ihre Microsoft 365-Gruppen anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c06cc-251">Make a note of the GUIDs for the sensitivity labels you want to apply to your Microsoft 365 groups.</span></span>

7. <span data-ttu-id="c06cc-252">Verwenden Sie den folgenden Befehl als Beispiel, um die Liste der Gruppen abzurufen, die derzeit die Klassifizierung "Allgemein" aufweisen:</span><span class="sxs-lookup"><span data-stu-id="c06cc-252">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="c06cc-253">Fügen Sie für jede Gruppe die neue Vertraulichkeitsbezeichnungs-GUID hinzu.</span><span class="sxs-lookup"><span data-stu-id="c06cc-253">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="c06cc-254">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c06cc-254">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="c06cc-255">Wiederholen Sie die Schritte 5 und 6 für die restlichen Gruppenklassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="c06cc-255">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="c06cc-256">Überwachen von Vertraulichkeitsbezeichnungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="c06cc-256">Auditing sensitivity label activities</span></span>

<span data-ttu-id="c06cc-257">Wenn jemand ein Dokument auf eine Website hochlädt, die mit einer Vertraulichkeitsbezeichnung geschützt ist, und das Dokument eine Vertraulichkeitsbezeichnung mit [höherer Priorität](sensitivity-labels.md#label-priority-order-matters) als die auf die Website angewendete Vertraulichkeitsbezeichnung aufweist, wird diese Aktion nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="c06cc-257">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="c06cc-258">Angenommen, Sie haben die Bezeichnung **Allgemein** auf eine SharePoint-Website angewendet, und jemand lädt ein Dokument mit der Bezeichnung **Vertraulich** auf diese Site hoch.</span><span class="sxs-lookup"><span data-stu-id="c06cc-258">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="c06cc-259">Da eine Vertraulichkeitsbezeichnung mit einer höheren Priorität Inhalte kennzeichnet, die eine höhere Vertraulichkeitsstufe aufweisen, als Inhalte mit einer niedrigeren Priorität, könnte dies ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="c06cc-259">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="c06cc-260">Die Aktion wird zwar nicht blockiert, sie wird jedoch überwacht, sodass Sie Dokumente mit abweichender Bezeichnungspriorität identifizieren und bei Bedarf Maßnahmen ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="c06cc-260">Although the action isn't blocked, it is audited, so you can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="c06cc-261">Löschen oder verschieben Sie zum Beispiel das hochgeladene Dokument von der Website.</span><span class="sxs-lookup"><span data-stu-id="c06cc-261">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="c06cc-262">Es würde kein Sicherheitsrisiko darstellen, wenn die auf ein Dokument angewendete Vertraulichkeitsbezeichnung eine niedrigere Priorität aufweist als die auf die Website angewendete Vertraulichkeitsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="c06cc-262">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="c06cc-263">Angenommen, ein Dokument, das als **Allgemein** bezeichnet ist, wird auf eine Website hochgeladen, die mit **Vertraulich** bezeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="c06cc-263">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="c06cc-264">In diesem Szenario wird kein Überwachungsereignis erzeugt.</span><span class="sxs-lookup"><span data-stu-id="c06cc-264">In this scenario, an auditing event isn't generated.</span></span>

<span data-ttu-id="c06cc-265">Um das Überwachungsprotokoll nach diesem Ereignis zu durchsuchen, suchen Sie nach **Konflikt in Bezug auf die Vertraulichkeitsbezeichnung eines Dokuments** aus der Kategorie **Datei- und Seitenaktivitäten**.</span><span class="sxs-lookup"><span data-stu-id="c06cc-265">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="c06cc-266">Wenn jemand einer Website oder Gruppe eine Vertraulichkeitsbezeichnung hinzufügt oder eine Vertraulichkeitsbezeichnung von einer Website oder Gruppe entfernt, werden diese Aktivitäten ebenfalls überwacht.</span><span class="sxs-lookup"><span data-stu-id="c06cc-266">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited.</span></span> <span data-ttu-id="c06cc-267">Diese Ereignisse sind in der Kategorie [Vertraulichkeitsbezeichnungsaktivitäten](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) zu finden.</span><span class="sxs-lookup"><span data-stu-id="c06cc-267">These events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> 

<span data-ttu-id="c06cc-268">Anweisungen zum Durchsuchen des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="c06cc-268">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="c06cc-269">Problembehandlung bei der Bereitstellung von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="c06cc-269">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="c06cc-270">Sie haben Probleme mit Vertraulichkeitsbezeichnungen für Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites?</span><span class="sxs-lookup"><span data-stu-id="c06cc-270">Having problems with sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="c06cc-271">Überprüfen Sie die Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c06cc-271">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="c06cc-272">Bezeichnungen sind nach der Veröffentlichung nicht sichtbar</span><span class="sxs-lookup"><span data-stu-id="c06cc-272">Labels not visible after publishing</span></span>
<span data-ttu-id="c06cc-273">Wenn beim Erstellen einer Website oder einer Microsoft 365-Gruppe Probleme auftreten, nachdem Sie diese Einstellungen aktiviert oder aber den Namen oder die QuickInfo einer Vertraulichkeitsbezeichnung geändert haben, warten Sie nach dem Speichern der Bezeichnungsänderungen ein paar Stunden, und versuchen Sie dann, das Team oder die Gruppe erneut zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c06cc-273">If you experience issues when you create a site or Microsoft 365 group after you enable these settings or modify a sensitivity label's name or tooltip, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="c06cc-274">Informationen hierzu finden Sie unter [Planen des Rollouts nach Erstellung oder Änderung einer Vertraulichkeitsbezeichnung](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="c06cc-274">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="c06cc-275">Wenn die neue Vertraulichkeitsbezeichnung in SharePoint Online weiterhin nicht angezeigt wird, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="c06cc-275">If you still can't see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="c06cc-276">Fehler beim Erstellen von Teams, Gruppen oder SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="c06cc-276">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="c06cc-277">Wenn während der öffentlichen Vorschau Erstellungsfehler auftreten, können Sie Vertraulichkeitsbezeichnungen für Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites unter Verwendung der Anweisungen im Abschnitt [Aktivieren der Unterstützung von Vertraulichkeitsbezeichnungen in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell) deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c06cc-277">If you experience creation errors during the public preview, you can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="c06cc-278">Um die Vorschau zu deaktivieren, müssen Sie jedoch in Schritt 5 die Funktion mit `$setting["EnableMIPLabels"] = "False"` deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c06cc-278">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c06cc-279">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c06cc-279">Additional resources</span></span>

<span data-ttu-id="c06cc-280">Sehen Sie sich das aufgezeichnete Webinar und die beantworteten Fragen zum Thema [Verwenden von Vertraulichkeitsbezeichnungen in Microsoft Teams, O365-Gruppen und SharePoint-Websites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380) an.</span><span class="sxs-lookup"><span data-stu-id="c06cc-280">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

