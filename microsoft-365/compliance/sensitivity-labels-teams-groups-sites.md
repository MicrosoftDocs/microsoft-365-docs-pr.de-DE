---
title: Verwenden Sie Vertraulichkeitsbezeichnungen mit Microsoft Teams, Microsoft 365-Gruppen und auf SharePoint-Websites
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
ms.openlocfilehash: b9168320b5764a3d7ed4e1570c32f0f35ccbc44d
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199625"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="be818-103">Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden</span><span class="sxs-lookup"><span data-stu-id="be818-103">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

><span data-ttu-id="be818-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="be818-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="be818-105">Zusätzlich zur Verwendung von [Vertraulichkeitsbezeichnungen](sensitivity-labels.md), um Dokumente und E-Mails zu klassifizieren und zu schützen, können Sie Vertraulichkeitsbezeichnungen auch verwenden, um Inhalte in den folgenden Containern zu schützen: Microsoft Teams-Websites, Microsoft 365-Gruppen ([vormals Office 365-Gruppen](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) und SharePoint-Websites.</span><span class="sxs-lookup"><span data-stu-id="be818-105">In addition to using [sensitivity labels](sensitivity-labels.md) to classify and protect documents and emails, you can also use sensitivity labels to protect content in the following containers: Microsoft Teams sites, Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), and SharePoint sites.</span></span> <span data-ttu-id="be818-106">Verwenden Sie für diese Klassifizierung und den Schutz auf Containerebene die folgenden Bezeichnungseinstellungen:</span><span class="sxs-lookup"><span data-stu-id="be818-106">For this container-level classification and protection, use the following label settings:</span></span>

- <span data-ttu-id="be818-107">Datenschutz (öffentlich oder privat) für mit einer Microsoft 365-Gruppe verbundene Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="be818-107">Privacy (public or private) of Microsoft 365 group-connected teams sites</span></span>
- <span data-ttu-id="be818-108">Zugriff externer Benutzer</span><span class="sxs-lookup"><span data-stu-id="be818-108">External users access</span></span>
- <span data-ttu-id="be818-109">Zugriff von nicht verwalteten Geräten aus</span><span class="sxs-lookup"><span data-stu-id="be818-109">Access from unmanaged devices</span></span> 

<span data-ttu-id="be818-110">Wenn Sie diese Vertraulichkeitsbezeichnung auf einen unterstützten Container anwenden, wendet die Bezeichnung die konfigurierten Optionen automatisch auf die verbundene Website oder Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="be818-110">When you apply this sensitivity label to a supported container, the label automatically applies the classification and protection settings to the connected site or group.</span></span>

<span data-ttu-id="be818-111">Der Inhalt dieser Container erbt jedoch nicht die Beschriftungen für die Klassifizierung und Einstellungen wie visuelle Markierungen oder Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="be818-111">Content in these containers however, do not inherit the labels for the classification and settings such as visual markings, or encryption.</span></span> <span data-ttu-id="be818-112">Aktivieren Sie[Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive](sensitivity-labels-sharepoint-onedrive-files.md), damit Benutzer Bezeichnungen auf ihre Dokumente in SharePoint- oder Teamwebsites anwenden können.</span><span class="sxs-lookup"><span data-stu-id="be818-112">So that users can label their documents in SharePoint sites or team sites, make sure you've [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

> [!NOTE]
> <span data-ttu-id="be818-113">Vertraulichkeitsbezeichnungen für Container werden von Office 365-Content Delivery Networks (CDNs) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be818-113">Sensitivity labels for containers aren't supported with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="be818-114">Vertraulichkeitsbezeichnungen für Microsoft Teams, Microsoft 365-Gruppen und auf SharePoint-Websites verwenden</span><span class="sxs-lookup"><span data-stu-id="be818-114">Using sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="be818-115">Bevor Sie Vertraulichkeitsbezeichnungen aktivieren und für die neuen Einstellungen konfigurieren, können Benutzer Vertraulichkeitsbezeichnungen in ihren Apps anzeigen und anwenden.</span><span class="sxs-lookup"><span data-stu-id="be818-115">Before you enable sensitivity labels for containers and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="be818-116">Beispielsweise aus Word:</span><span class="sxs-lookup"><span data-stu-id="be818-116">For example, from Word:</span></span>

![Eine in der Word-Desktop-App angezeigte Vertraulichkeitsbezeichnung](../media/sensitivity-label-word.png)

<span data-ttu-id="be818-118">Nachdem Sie Vertraulichkeitsbezeichnungen für Container aktiviert und konfiguriert haben, können Benutzer Vertraulichkeitsbezeichnungen außerdem für Microsoft Team-Websites, Microsoft 365-Gruppen und SharePoint-Websites anzeigen und anwenden.</span><span class="sxs-lookup"><span data-stu-id="be818-118">After you enable and configure sensitivity labels for containers, users can additionally see and apply sensitivity labels to Microsoft team sites, Microsoft 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="be818-119">Beispielsweise, wenn eine neue Teamwebsite in SharePoint erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="be818-119">For example, when you create a new team site from SharePoint:</span></span>

![Eine Vertraulichkeitsbezeichnung beim Erstellen einer Teamwebsite in SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a><span data-ttu-id="be818-121">Aktivieren von Vertraulichkeitsbezeichnungen für Container und Synchronisieren von Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="be818-121">How to enable sensitivity labels for containers and synchronize labels</span></span>

1. <span data-ttu-id="be818-122">Weil dieses Feature die Azure AD-Funktionen nutzt, führen Sie zum Aktivieren der Vertraulichkeitsbezeichnungen die Anleitungen in der Azure AD-Dokumentation aus: [Zuweisen von Vertraulichkeitsbezeichnungen zu Microsoft 365-Gruppen in Azure Active Directory (Vorschau)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="be818-122">Because this feature uses Azure AD functionality, follow the instructions from the Azure AD documentation to enable sensitivity label support: [Assign sensitivity labels to Microsoft 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="be818-123">Sie müssen jetzt Ihre Vertraulichkeitsbezeichnungen mit Azure AD synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="be818-123">You now need to synchronize your sensitivity labels to Azure AD.</span></span> <span data-ttu-id="be818-124">Stellen Sie [zunächst eine Verbindung mit Office 365 Security & Compliance Center PowerShell her](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="be818-124">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="be818-125">Melden Sie sich beispielsweise bei einer PowerShell-Sitzung, die Sie als Administrator ausführen, mit einem globalen Administratorkonto an:</span><span class="sxs-lookup"><span data-stu-id="be818-125">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

3. <span data-ttu-id="be818-126">Führen Sie dann den folgenden Befehl aus, damit Ihre Vertraulichkeitsbezeichnungen mit Microsoft 365-Gruppen verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="be818-126">Then run the following command to ensure your sensitivity labels can be used with Microsoft 365 groups:</span></span>
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings"></a><span data-ttu-id="be818-127">Website- und Gruppeneinstellungen konfigurieren</span><span class="sxs-lookup"><span data-stu-id="be818-127">How to configure site and group settings</span></span>

<span data-ttu-id="be818-128">Sie können jetzt Vertraulichkeitsbezeichnungen erstellen oder bearbeiten, die für Websites und Gruppen verfügbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="be818-128">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="be818-129">Durch Aktivieren der Vertraulichkeitsbezeichnungen für Container wird eine neue Seite im Assistenten für Vertraulichkeitsbezeichnungen verfügbar: **Website- und Gruppeneinstellungen**</span><span class="sxs-lookup"><span data-stu-id="be818-129">Enabling sensitivity labels for containers makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="be818-130">Wenn Sie Hilfe beim Erstellen oder Bearbeiten einer Vertraulichkeitsbezeichnung benötigen, lesen Sie die Anweisungen unter [Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="be818-130">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="be818-131">Auf dieser neuen Seite **Website- und Gruppeneinstellungen** können Sie die Einstellungen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="be818-131">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="be818-132">**Datenschutz für mit einer Office 365-Gruppe verbundene Teamwebsites**: Behalten Sie den Standardwert **Öffentlich bei – jeder in der Organisation kann auf die Site zugreifen**, wenn Sie möchten, dass jeder in Ihrer Organisation auf die Teamwebsite oder Gruppe zugreifen kann, auf der diese Bezeichnung angebracht ist.</span><span class="sxs-lookup"><span data-stu-id="be818-132">**Privacy of Office 365 group-connected teams sites**: Keep the default of **Public - anyone in the organization can access the site** if you want anyone in your organization to access the team site or group where this label is applied.</span></span>
    
    <span data-ttu-id="be818-133">Wählen Sie **Privat** aus, wenn Sie möchten, dass der Zugriff nur auf genehmigte Mitglieder in Ihrer Organisation beschränkt wird.</span><span class="sxs-lookup"><span data-stu-id="be818-133">Select **Private** if you want access to be restricted to only approved members in your organization.</span></span>
    
    <span data-ttu-id="be818-134">Wählen Sie **Keine – lassen Sie den Benutzer wählen, wer auf die Website zugreifen kann**, wenn Sie diese Standardeinstellung beibehalten, wenn Sie den Inhalt im Container mit Vertraulichkeitsbezeichnungen schützen möchten, die Benutzer aber trotzdem selbst Datenschutzeinstellungen konfigurieren können sollen.</span><span class="sxs-lookup"><span data-stu-id="be818-134">Select **None - let user chose who can access the site** when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
    
    <span data-ttu-id="be818-135">Die Einstellungen von **Öffentlich** oder **Privat** setzen und sperren die Datenschutzeinstellung, wenn Sie diese Bezeichnung auf den Container aufbringen.</span><span class="sxs-lookup"><span data-stu-id="be818-135">The settings of **Public** or **Private** set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="be818-136">Die von Ihnen gewählte Einstellung ersetzt alle vorherigen Datenschutzeinstellungen, die für das Team oder die Gruppe konfiguriert wurden, und sperrt den Datenschutzwert, so dass er nur geändert werden kann, wenn zuvor die Vertraulichkeitsbezeichnung vom Container entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="be818-136">Your chosen setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="be818-137">Nachdem Sie die Vertraulichkeitsbezeichnung entfernt haben, bleibt die Datenschutzeinstellung der Bezeichnung erhalten, aber Benutzer können sie jetzt wieder ändern.</span><span class="sxs-lookup"><span data-stu-id="be818-137">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>

- <span data-ttu-id="be818-138">**Zugriff für externe Benutzer**: Steuern Sie, ob der Gruppenbesitzer [Gäste zur Gruppe hinzufügen](/office365/admin/create-groups/manage-guest-access-in-groups) kann.</span><span class="sxs-lookup"><span data-stu-id="be818-138">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="be818-139">**Nicht verwaltete Geräte**: Erlauben Sie für [nicht verwaltete Geräte](/sharepoint/control-access-from-unmanaged-devices) vollen Zugriff oder nur Webzugriff, bzw. blockieren Sie den Zugriff vollständig.</span><span class="sxs-lookup"><span data-stu-id="be818-139">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> <span data-ttu-id="be818-140">Wenn Sie diese Einstellung auf Mandantenebene oder für einen bestimmten Standort konfiguriert haben, wird sie nur angewendet, wenn sie restriktiver ist.</span><span class="sxs-lookup"><span data-stu-id="be818-140">If you have configured this setting at the tenant level or for a specific site, the setting you specify here will be applied only if it's more restrictive.</span></span>

![Die Registerkarte "Website- und Gruppeneinstellungen"](../media/edit-sensitivity-label-site-group2.png)

> [!IMPORTANT]
> <span data-ttu-id="be818-142">Wenn Sie eine Bezeichnung auf ein Team, eine Gruppe oder eine Website anwenden, werden nur diese Website- und Gruppeneinstellungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="be818-142">Only these site and group settings take effect when you apply the label to a team, group, or site.</span></span> <span data-ttu-id="be818-143">Andere Bezeichnungseinstellungen (z. B. Verschlüsselung und Inhaltskennzeichnung) werden nicht auf die Inhalte innerhalb des Teams, der Gruppen oder der Website angewendet.</span><span class="sxs-lookup"><span data-stu-id="be818-143">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="be818-144">Schrittweises Rollout für Mandanten: Wenn Benutzer Teams, Gruppen und Websites erstellen, stehen nur Bezeichnungen mit den Website- und Gruppeneinstellungen zur Auswahl.</span><span class="sxs-lookup"><span data-stu-id="be818-144">Gradually rolling out to tenants: Only labels with the site and group settings will be available to select when users create teams, groups, and sites.</span></span> <span data-ttu-id="be818-145">Wenn Sie derzeit eine Bezeichnung auf einen Container anwenden können, die Website- und Gruppeneinstellungen für die Bezeichnung jedoch nicht aktiviert sind, wird nur der Name der Bezeichnung auf den Container angewendet.</span><span class="sxs-lookup"><span data-stu-id="be818-145">If you can currently apply a label to a container when the label doesn't have the site and group settings enabled, only the label name is applied to the container.</span></span>

<span data-ttu-id="be818-146">Wenn Ihre Vertraulichkeitskennzeichnung noch nicht veröffentlicht wurde, veröffentlichen Sie diese jetzt, indem Sie sie[einer Richtlinie für Vertraulichkeitskennzeichnungen hinzufügen](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="be818-146">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="be818-147">Diejenigen Benutzer, denen eine Richtlinie zur Vertraulichkeitskennzeichnung zugeordnet ist, die diese Kennzeichnung beinhaltet, können diese für Websites und Gruppen auswählen.</span><span class="sxs-lookup"><span data-stu-id="be818-147">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

<span data-ttu-id="be818-148">Aus der Bezeichnungsrichtlinie gilt nur die Richtlinieneinstellung **Diese Bezeichnung standardmäßig auf Dokumente und E-Mail anwenden**, wenn Sie die Bezeichnung auf Container anwenden.</span><span class="sxs-lookup"><span data-stu-id="be818-148">From the label policy, only the policy setting **Apply this label by default to documents and email** is applicable when you apply this label to containers.</span></span> <span data-ttu-id="be818-149">Es werden keine anderen Richtlinieneinstellungen angewendet, beispielsweise obligatorische Bezeichnungen, das Anfordern von Benutzerbegründungen sowie ein Link zur benutzerdefinierten Hilfeseite.</span><span class="sxs-lookup"><span data-stu-id="be818-149">Other policy settings are not applied, which include mandatory labeling, requiring user justification, and a link to the custom help page.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="be818-150">Verwaltung von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="be818-150">Sensitivity label management</span></span>

<span data-ttu-id="be818-151">Verwenden Sie die folgende Anleitung zum Erstellen, Ändern oder Löschen von Vertraulichkeitsbezeichnungen, die für Websites und Gruppen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="be818-151">Use the following guidance for when you create, modify, or delete sensitivity labels that are configured for sites and groups.</span></span>

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="be818-152">Erstellen und Veröffentlichen von Bezeichnungen, die für Websites und Gruppen konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="be818-152">Creating and publishing labels that are configured for sites and groups</span></span>

<span data-ttu-id="be818-153">Wenn eine neue Vertraulichkeitsbezeichnung erstellt und veröffentlicht wird, ist es innerhalb einer Stunde für Benutzer in Teams, Gruppen und Websites sichtbar.</span><span class="sxs-lookup"><span data-stu-id="be818-153">When a new sensitivity label is created and published, it's visible for users in teams, groups, and sites within one hour.</span></span> <span data-ttu-id="be818-154">Wenn Sie jedoch eine vorhandene Bezeichnung ändern, kann es bis zu 24 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="be818-154">However, if you modify an existing label, allow up to 24 hours.</span></span> <span data-ttu-id="be818-155">Verwenden Sie die nachstehenden Anweisungen, um eine Bezeichnung für Ihre Benutzer zu veröffentlichen, wenn diese Bezeichnung für Website-und Gruppeneinstellungen konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="be818-155">Use the following guidance to publish a label for your users when that label is configured for site and group settings:</span></span>

1. <span data-ttu-id="be818-156">Nachdem Sie die Vertraulichkeitsbezeichnung erstellt und konfiguriert haben, fügen Sie diese Bezeichnung zu einer Bezeichnungsrichtlinie hinzu, die nur für einige Testbenutzer gilt.</span><span class="sxs-lookup"><span data-stu-id="be818-156">After you create and configure the sensitivity label, add this label to a label policy that applies to just a few test users.</span></span>

2. <span data-ttu-id="be818-157">Warten Sie, bis die Änderung repliziert wurde:</span><span class="sxs-lookup"><span data-stu-id="be818-157">Wait for the change to replicate:</span></span>
    - <span data-ttu-id="be818-158">Neue Bezeichnung: Warten Sie eine Stunde.</span><span class="sxs-lookup"><span data-stu-id="be818-158">New label: Wait for one hour.</span></span>
    - <span data-ttu-id="be818-159">Vorhandene Bezeichnung: Warten Sie 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="be818-159">Existing label: Wait for 24 hours.</span></span>

3. <span data-ttu-id="be818-160">Verwenden Sie nach Ablauf dieser Zeit ein Testbenutzerkonto, um ein Team, eine Microsoft 365-Gruppe oder eine SharePoint-Website mit der Bezeichnung zu erstellen, die Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="be818-160">After this wait period, use one of the test user accounts to create a team, Microsoft 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="be818-161">Wenn während des Erstellungsvorgangs keine Fehler auftreten, wissen Sie, dass Sie die Bezeichnung für alle Benutzer in Ihrem Mandanten veröffentlichen können.</span><span class="sxs-lookup"><span data-stu-id="be818-161">If there are no errors during this creation operation, you know it's safe to publish the label to all users in your tenant.</span></span>

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="be818-162">Veröffentlichte Bezeichnungen ändern, die für Websites und Gruppen konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="be818-162">Modifying published labels that are configured for sites and groups</span></span>

<span data-ttu-id="be818-163">Es wird empfohlen, die Website- und Gruppeneinstellungen für eine Vertraulichkeitsbezeichnung nicht zu ändern, nachdem sie auf Teams, Gruppen oder Websites angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="be818-163">As a best practice, don't change the site and group settings for a sensitivity label after the label has been applied to teams, groups, or sites.</span></span> <span data-ttu-id="be818-164">Denken Sie in diesem Fall daran, 24 Stunden zu warten, bis die Änderungen in alle Container mit der Bezeichnung übernommen wurden.</span><span class="sxs-lookup"><span data-stu-id="be818-164">If you do, remember to wait for 24 hours for the changes to replicate to all containers that have the label applied.</span></span> 

<span data-ttu-id="be818-165">Wenn Ihre Änderungen die Einstellung**Zugriff für externe Benutzer** einschließen, gilt außerdem:</span><span class="sxs-lookup"><span data-stu-id="be818-165">In addition, if your changes include the **External users access** setting:</span></span>

- <span data-ttu-id="be818-166">Die neue Einstellung gilt für neue Benutzer, jedoch nicht für bestehende Benutzer.</span><span class="sxs-lookup"><span data-stu-id="be818-166">The new setting applies to new users but not to existing users.</span></span> <span data-ttu-id="be818-167">Wenn diese Einstellung beispielsweise zuvor ausgewählt war und Gastbenutzer auf die Website zugegriffen haben, können diese Gastbenutzer weiterhin auf die Website zugreifen, nachdem diese Einstellung in der Konfigurieren der Bezeichnungen deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="be818-167">For example, if this setting was previously selected and as a result, guest users accessed the site, these guest users can still access the site after this setting is cleared in the label configuration.</span></span>

- <span data-ttu-id="be818-168">Die Datenschutzeinstellungen für die Gruppeneigenschaften "hiddenMembership" und "roleEnabled" werden nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="be818-168">The privacy settings for the group properties hiddenMembership and roleEnabled aren't updated.</span></span>


### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="be818-169">Veröffentlichte Bezeichnungen löschen, die für Websites und Gruppen konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="be818-169">Deleting published labels that are configured for sites and groups</span></span>

<span data-ttu-id="be818-170">Wenn Sie eine Vertraulichkeitsbezeichnung löschen, deren Website- und Gruppeneinstellungen aktiviert sind, und diese Bezeichnung in einer oder mehreren Bezeichnungsrichtlinien enthalten ist, kann dies zu Erstellungsfehlern für neue Teams, Gruppen und Websites führen.</span><span class="sxs-lookup"><span data-stu-id="be818-170">If you delete a sensitivity label that has the site and group settings enabled, and that label is included in one or more label policies, this action can result in creation failures for new teams, groups, and sites.</span></span> <span data-ttu-id="be818-171">Folgen Sie dieser Anleitung, um dieses Problem zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="be818-171">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="be818-172">Entfernen Sie die Vertraulichkeitsbezeichnung aus allen Bezeichnungsrichtlinien, in denen die Bezeichnung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="be818-172">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="be818-173">Warten Sie eine Stunde.</span><span class="sxs-lookup"><span data-stu-id="be818-173">Wait for one hour.</span></span>

3. <span data-ttu-id="be818-174">Versuchen Sie nach dieser Wartezeit ein Team, eine Gruppe oder eine Website zu erstellen. Überprüfen Sie, dass die Bezeichnung nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="be818-174">After this wait period, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="be818-175">Wenn die Vertraulichkeitsbezeichnung nicht angezeigt wird, kann sie jetzt bedenkenlos geändert oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="be818-175">If the sensitivity label isn't visible, you can now safely delete the label.</span></span>

## <a name="how-to-apply-sensitivity-labels-to-containers"></a><span data-ttu-id="be818-176">Anwenden von Vertraulichkeitsbezeichnungen auf Container</span><span class="sxs-lookup"><span data-stu-id="be818-176">How to apply sensitivity labels to containers</span></span>

<span data-ttu-id="be818-177">Jetzt können Sie die Vertraulichkeitsbezeichnung(en) auf folgende Container anwenden:</span><span class="sxs-lookup"><span data-stu-id="be818-177">You're now ready to apply the sensitivity label or labels to the following containers:</span></span>

- [<span data-ttu-id="be818-178">Microsoft 365-Gruppe in Azure AD</span><span class="sxs-lookup"><span data-stu-id="be818-178">Microsoft 365 group in Azure AD</span></span>](#apply-sensitivity-labels-to-microsoft-365-groups)
- [<span data-ttu-id="be818-179">Microsoft-Teams-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="be818-179">Microsoft Teams team site</span></span>](#apply-a-sensitivity-label-to-a-new-team)
- [<span data-ttu-id="be818-180">Microsoft 365 Gruppe in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="be818-180">Microsoft 365 group in Outlook on the web</span></span>](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [<span data-ttu-id="be818-181">SharePoint-Website</span><span class="sxs-lookup"><span data-stu-id="be818-181">SharePoint site</span></span>](#apply-a-sensitivity-label-to-a-new-site)

<span data-ttu-id="be818-182">Sie können PowerShell verwenden, wenn Sie eine [Vertraulichkeitsbezeichnung auf mehrere Websites anwenden möchten](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).</span><span class="sxs-lookup"><span data-stu-id="be818-182">You can use PowerShell if you need to [apply a sensitivity label to multiple sites](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).</span></span>

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a><span data-ttu-id="be818-183">Anwenden von Vertraulichkeitsbezeichnungen auf Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="be818-183">Apply sensitivity labels to Microsoft 365 groups</span></span>

<span data-ttu-id="be818-184">Jetzt können Sie die Vertraulichkeitsbezeichnung(en) auf Microsoft 365-Gruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="be818-184">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups.</span></span> <span data-ttu-id="be818-185">Kehren Sie für weitere Anweisungen zur Azure AD-Dokumentation zurück:</span><span class="sxs-lookup"><span data-stu-id="be818-185">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="be818-186">Zuweisen einer Bezeichnung zu einer neuen Gruppe im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="be818-186">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="be818-187">Zuweisen einer Bezeichnung zu einer vorhandenen Gruppe im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="be818-187">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="be818-188">[Entfernen einer Bezeichnung von einer vorhandenen Gruppe im Azure-Portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="be818-188">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="be818-189">Anwenden einer Vertraulichkeitsbezeichnung auf ein neues Team</span><span class="sxs-lookup"><span data-stu-id="be818-189">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="be818-190">Benutzer können Vertraulichkeitsbezeichnungen auswählen, wenn sie neue Teams in Microsoft Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="be818-190">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="be818-191">Wenn sie die Bezeichnung aus der Dropdownliste **Vertraulichkeit** auswählen, kann sich die Datenschutzeinstellung entsprechend der Bezeichnungskonfiguration ändern.</span><span class="sxs-lookup"><span data-stu-id="be818-191">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="be818-192">Abhängig von der für die Bezeichnung festgelegten Einstellung für den externen Benutzerzugriff können Benutzer Personen außerhalb der Organisation zum Team hinzufügen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="be818-192">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="be818-193">Weitere Informationen Vertraulichkeitsbezeichnungen für Teams</span><span class="sxs-lookup"><span data-stu-id="be818-193">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![Datenschutzeinstellung beim Erstellen eines neuen Teams](../media/privacy-setting-new-team.png)

<span data-ttu-id="be818-195">Nachdem Sie das Team erstellt haben, wird die Vertraulichkeitsbezeichnung in der oberen rechten Ecke aller Kanäle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be818-195">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![Die Vertraulichkeitsbezeichnung wird im Team angezeigt](../media/privacy-setting-teams.png)

<span data-ttu-id="be818-197">Der Dienst wendet auf die Microsoft 365-Gruppe und die verbundene SharePoint-Teamwebsite automatisch dieselbe Vertraulichkeitsbezeichnung an.</span><span class="sxs-lookup"><span data-stu-id="be818-197">The service automatically applies the same sensitivity label to the Microsoft 365 group and the connected SharePoint team site.</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="be818-198">Anwenden einer Vertraulichkeitsbezeichnung auf eine neue Gruppe in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="be818-198">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="be818-199">Wenn Sie in Outlook im Web eine neue Gruppe erstellen, können Sie die Option **Vertraulichkeit** für veröffentlichte Bezeichnungen auswählen oder ändern:</span><span class="sxs-lookup"><span data-stu-id="be818-199">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![Erstellen einer Gruppe und Auswählen einer Option unter "Vertraulichkeit"](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="be818-201">Anwenden einer Vertraulichkeitsbezeichnung auf eine neue Website</span><span class="sxs-lookup"><span data-stu-id="be818-201">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="be818-202">Administratoren und Endbenutzer können [beim Erstellen moderner Teamwebsites und Kommunikationswebsites](/sharepoint/create-site-collection) Vertraulichkeitsbezeichnungen auswählen, und **Erweiterte Einstellungen** erweitern:</span><span class="sxs-lookup"><span data-stu-id="be818-202">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![Erstellen einer Website und Auswählen einer Option unter "Vertraulichkeit"](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="be818-204">In der Dropdownliste werden die Bezeichnungsnamen für die Auswahl angezeigt, und das Hilfesymbol zeigt alle Bezeichnungsnamen mit entsprechender QuickInfo an, was Benutzern dabei helfen kann, die richtige Bezeichnung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="be818-204">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="be818-205">Wenn die Bezeichnung angewendet wurde und Benutzer zur Website navigieren, werden der Name der Bezeichnung und die angewendeten Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be818-205">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="be818-206">So wurde dieser Website beispielsweise die Bezeichnung **Vertraulich** zugewiesen und die Datenschutzeinstellung auf **Privat** festgelegt:</span><span class="sxs-lookup"><span data-stu-id="be818-206">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![Eine Website, auf die eine Vertraulichkeitsbezeichnung angewendet wurde](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a><span data-ttu-id="be818-208">Verwenden von PowerShell, um eine Vertraulichkeitsbezeichnung auf mehrere Websites anzuwenden</span><span class="sxs-lookup"><span data-stu-id="be818-208">Use PowerShell to apply a sensitivity label to multiple sites</span></span>

<span data-ttu-id="be818-209">Sie können die [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps) und [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps)Cmdlet mit dem Parameter*Vertraulichkeitsbezeichnung* aus der aktuellen SharePoint Online-Verwaltungsshell verwenden, um eine Vertraulichkeitsbezeichnung auf mehrere Websites anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="be818-209">You can use the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps) and [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet with the *SensitivityLabel* parameter from the current SharePoint Online Management Shell to apply a sensitivity label to many sites.</span></span> <span data-ttu-id="be818-210">Die Websites können eine beliebige SharePoint-Websitesammlung oder eine OneDrive-Website sein.</span><span class="sxs-lookup"><span data-stu-id="be818-210">The sites can be any SharePoint site collection, or a OneDrive site.</span></span>

<span data-ttu-id="be818-211">Stellen Sie sicher, dass Sie über die Version 16.0.19418.12000 oder höher der SharePoint Online-Verwaltungsshell verfügen.</span><span class="sxs-lookup"><span data-stu-id="be818-211">Make sure you have version 16.0.19418.12000 or later of the SharePoint Online Management Shell.</span></span>

1. <span data-ttu-id="be818-212">Öffnen Sie eine PowerShell-Sitzung mit der Option **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="be818-212">Open a PowerShell session with the **Run as Administrator** option.</span></span>

2. <span data-ttu-id="be818-213">Wenn Sie die GUID ihrer Bezeichnung nicht kennen: Stellen Sie eine Verbindung zur[Office 365 Security & Compliance Center-PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) her, und rufen Sie die Liste der Vertraulichkeitsbezeichnungen und deren GUIDs ab.</span><span class="sxs-lookup"><span data-stu-id="be818-213">If you don't know your label GUID: [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="be818-214">Stellen Sie nun [eine Verbindung mit Exchange Online PowerShell her,](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) und bewahren Sie die GUID der Bezeichnung als Variable auf.</span><span class="sxs-lookup"><span data-stu-id="be818-214">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) and store your label GUID as a variable.</span></span> <span data-ttu-id="be818-215">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="be818-215">For example:</span></span> 
    
    ```powershell
    $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
    ```

4. <span data-ttu-id="be818-216">Erstellen Sie eine neue Variable, die mehrere Websites identifiziert, die eine bestimmte Zeichenfolge in ihrer URL gemeinsam haben.</span><span class="sxs-lookup"><span data-stu-id="be818-216">Create a new variable that identifies multiple sites that have an identifying string in common in their URL.</span></span> <span data-ttu-id="be818-217">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="be818-217">For example:</span></span>
    
    ```powershell
    $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents" 
    ```

5. <span data-ttu-id="be818-218">Führen Sie den folgenden Befehl aus, um die Bezeichnung auf diese Websites anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="be818-218">Run the following command to apply the label to these sites.</span></span> <span data-ttu-id="be818-219">Anhand unserer Beispiele:</span><span class="sxs-lookup"><span data-stu-id="be818-219">Using our examples:</span></span>
    
    ```powershell
    $sites | ForEach-Object {Set-SpoTenant $_.url -SensitivityLabel $Id}
    ```

<span data-ttu-id="be818-220">Wenn Sie unterschiedliche Bezeichnungen auf unterschiedliche Websites anwenden möchten, wiederholen Sie den folgenden Befehl für jede Website: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span><span class="sxs-lookup"><span data-stu-id="be818-220">To apply different labels to different sites, repeat the following command for each site: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span></span>

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="be818-221">Vertraulichkeitsbezeichnungen im SharePoint Admin Center aufrufen und verwalten</span><span class="sxs-lookup"><span data-stu-id="be818-221">View and manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="be818-222">Zum Anzeigen der angewendeten Vertraulichkeitsbezeichnungen verwenden Sie die Seite **Aktive Websites** im neuen SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="be818-222">To view, sort, and search the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="be818-223">Möglicherweise müssen Sie zuerst die Spalte **Vertraulichkeit** hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="be818-223">You might need to first add the **Sensitivity** column:</span></span>

![Die Spalte "Vertraulichkeit" auf der Seite "Aktive Websites"](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="be818-225">Weitere Informationen zum Verwalten von Websites auf der Seite „Aktive Websites“ sowie zum Hinzufügen einer Spalte finden Sie unter [Verwalten von Websites im neuen SharePoint Admin Center](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="be818-225">For more information about managing sites from the Active sites page, including how to add a column, see [Manage sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

<span data-ttu-id="be818-226">Auf dieser Seite können Sie auch eine Bezeichnung ändern und anwenden:</span><span class="sxs-lookup"><span data-stu-id="be818-226">You can also change and apply a label from this page:</span></span>

1. <span data-ttu-id="be818-227">Wählen Sie den Websitenamen aus, um den Detailbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="be818-227">Select the site name to open the details pane.</span></span>

2. <span data-ttu-id="be818-228">Wählen Sie die Registerkarte **Richtlinien** aus, und wählen Sie dann **Bearbeiten** für die Einstellung **Vertraulichkeit** aus.</span><span class="sxs-lookup"><span data-stu-id="be818-228">Select the **Policies** tab, and then select **Edit** for the **Sensitivity** setting.</span></span>

3. <span data-ttu-id="be818-229">Wählen Sie im Bereich **Vertraulichkeitseinstellung bearbeiten** die Vertraulichkeitsbezeichnung aus, die Sie auf die Website anwenden möchten, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="be818-229">From the **Edit sensitivity setting** pane, select the sensitivity label you want to apply to the site, and then select **Save**.</span></span>

## <a name="support-for-sensitivity-labels"></a><span data-ttu-id="be818-230">Support für Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="be818-230">Support for sensitivity labels</span></span>

<span data-ttu-id="be818-231">Die folgenden Apps und Dienste unterstützen Vertraulichkeitsbezeichnungen, die für Websites und Gruppeneinstellungen konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="be818-231">The following apps and services support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="be818-232">Admin Center:</span><span class="sxs-lookup"><span data-stu-id="be818-232">Admin centers:</span></span>
    - <span data-ttu-id="be818-233">SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="be818-233">SharePoint admin center</span></span>
    - <span data-ttu-id="be818-234">Azure Active Directory-Portal</span><span class="sxs-lookup"><span data-stu-id="be818-234">Azure Active Directory portal</span></span>
    - <span data-ttu-id="be818-235">Microsoft 365 Compliance Center, Microsoft 365 Security Center, Office 365 Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="be818-235">Microsoft 365 compliance center, Microsoft 365 security center, Office 365 Security & Compliance Center</span></span>

- <span data-ttu-id="be818-236">Benutzer-Apps und -Dienste:</span><span class="sxs-lookup"><span data-stu-id="be818-236">User apps and services:</span></span>
    - <span data-ttu-id="be818-237">SharePoint</span><span class="sxs-lookup"><span data-stu-id="be818-237">SharePoint</span></span>
    - <span data-ttu-id="be818-238">Teams</span><span class="sxs-lookup"><span data-stu-id="be818-238">Teams</span></span>
    - <span data-ttu-id="be818-239">Outlook im Web und für Windows, MacOS, iOS und Android</span><span class="sxs-lookup"><span data-stu-id="be818-239">Outlook on the web and for Windows, MacOS, iOS, and Android</span></span>
    - <span data-ttu-id="be818-240">Formulare</span><span class="sxs-lookup"><span data-stu-id="be818-240">Forms</span></span>
    - <span data-ttu-id="be818-241">Stream</span><span class="sxs-lookup"><span data-stu-id="be818-241">Stream</span></span>

<span data-ttu-id="be818-242">Die folgenden Apps und Dienste unterstützen derzeit keine Vertraulichkeitsbezeichnungen, die für Websites und Gruppeneinstellungen konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="be818-242">The following apps and services don't currently support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="be818-243">Admin Center:</span><span class="sxs-lookup"><span data-stu-id="be818-243">Admin centers:</span></span>
    - <span data-ttu-id="be818-244">Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="be818-244">Microsoft 365 admin center</span></span>
    - <span data-ttu-id="be818-245">Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="be818-245">Teams admin center</span></span>
    - <span data-ttu-id="be818-246">Exchange Admin-Center</span><span class="sxs-lookup"><span data-stu-id="be818-246">Exchange admin center</span></span>

- <span data-ttu-id="be818-247">Benutzer-Apps und -Dienste:</span><span class="sxs-lookup"><span data-stu-id="be818-247">User apps and services:</span></span>
    - <span data-ttu-id="be818-248">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="be818-248">Dynamics 365</span></span>
    - <span data-ttu-id="be818-249">Yammer</span><span class="sxs-lookup"><span data-stu-id="be818-249">Yammer</span></span>
    - <span data-ttu-id="be818-250">Planner</span><span class="sxs-lookup"><span data-stu-id="be818-250">Planner</span></span>
    - <span data-ttu-id="be818-251">Project</span><span class="sxs-lookup"><span data-stu-id="be818-251">Project</span></span>
    - <span data-ttu-id="be818-252">PowerBI</span><span class="sxs-lookup"><span data-stu-id="be818-252">PowerBI</span></span>

## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="be818-253">Klassische Azure AD-Gruppenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="be818-253">Classic Azure AD group classification</span></span>

<span data-ttu-id="be818-254">Microsoft 365 unterstützt die alten Klassifizierungen für neue Microsoft 365-Gruppen und SharePoint-Websites nicht mehr, wenn Sie Vertraulichkeitsbezeichnungen für Container aktivieren.</span><span class="sxs-lookup"><span data-stu-id="be818-254">Microsoft 365 no longer supports the old classifications for new Microsoft 365 groups and SharePoint sites after you enable sensitivity labels for containers.</span></span> <span data-ttu-id="be818-255">Bestehende Gruppen und Websites, die Vertraulichkeitsbezeichnungen unterstützen, zeigen weiterhin die alten Klassifizierungswerte an, es sei denn, Sie konvertieren sie zur Verwendung von Vertraulichkeitsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="be818-255">However, existing groups and sites that support sensitivity labels still display the old classification values until you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="be818-256">Ein Beispiel dafür, wie Sie die alte Gruppenklassifizierung für Microsoft Office SharePoint Online verwendet haben könnten, finden Sie unter [Klassifizierung "moderner" Microsoft Office SharePoint Online-Websites](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="be818-256">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="be818-257">Diese Klassifizierungen wurden konfiguriert, indem Azure AD PowerShell oder die PnP-Kernbibliothek verwendet und Werte für die Einstellung `ClassificationList` festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="be818-257">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting.</span></span> <span data-ttu-id="be818-258">Wenn in Ihrem Mandanten Klassifizierungswerte definiert sind, werden sie angezeigt, wenn Sie den folgenden Befehl aus dem [AzureADPreview PowerShell-Modul](https://www.powershellgallery.com/packages/AzureADPreview) ausführen:</span><span class="sxs-lookup"><span data-stu-id="be818-258">If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="be818-259">Um Ihre alten Klassifizierungen in Vertraulichkeitsbezeichnungen umzuwandeln, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="be818-259">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="be818-260">Verwenden vorhandener Bezeichnungen: Geben Sie die gewünschten Bezeichnungseinstellungen für Websites und Gruppen an, indem Sie bereits veröffentlichte Vertraulichkeitsbezeichnungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="be818-260">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="be818-261">Erstellen neuer Bezeichnungen: Geben Sie die gewünschten Bezeichnungseinstellungen für Websites und Gruppen an, indem Sie neue Vertraulichkeitsbezeichnungen mit den gleichen Namen wie Ihre bestehenden Klassifizierungen erstellen und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="be818-261">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="be818-262">Gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="be818-262">Then:</span></span> 

1. <span data-ttu-id="be818-263">Verwenden Sie PowerShell, um die Vertraulichkeitsbezeichnungen mithilfe von Namenszuordnung auf vorhandene Microsoft 365-Gruppen und SharePoint-Websites anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="be818-263">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="be818-264">Entsprechende Anweisungen finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="be818-264">See the next section for instructions.</span></span>

2. <span data-ttu-id="be818-265">Entfernen Sie die alten Klassifizierungen der bestehenden Gruppen und Websites.</span><span class="sxs-lookup"><span data-stu-id="be818-265">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="be818-266">Sie können Benutzer zwar nicht daran hindern, neue Gruppen in Apps und Diensten, die noch keine Vertraulichkeitsbezeichnungen unterstützen, zu erstellen, aber Sie können wiederholt ein PowerShell-Skript ausführen, um nach neuen Gruppen zu suchen, die von Benutzern mit den alten Klassifizierungen erstellt wurden, und diese in Vertraulichkeitsbezeichnungen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="be818-266">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

<span data-ttu-id="be818-267">Informationen zum Verwalten der Koexistenz von Vertraulichkeitsbezeichnungen und Azure AD-Klassifizierungen für Websites und Gruppen finden Sie unter [Azure Active Directory Klassifizierung und Vertraulichkeitsbezeichnungen für Microsoft 365-Gruppen](migrate-aad-classification-sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="be818-267">To help you manage the coexistence of sensitivity labels and Azure AD classifications for sites and groups, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](migrate-aad-classification-sensitivity-labels.md).</span></span>

#### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a><span data-ttu-id="be818-268">Verwenden von PowerShell, um Klassifizierungen für Microsoft 365-Gruppen in Vertraulichkeitsbezeichnungen zu konvertieren</span><span class="sxs-lookup"><span data-stu-id="be818-268">Use PowerShell to convert classifications for Microsoft 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="be818-269">Stellen Sie [zunächst eine Verbindung mit Office 365 Security & Compliance Center PowerShell her](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="be818-269">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="be818-270">Melden Sie sich beispielsweise bei einer PowerShell-Sitzung, die Sie als Administrator ausführen, mit einem globalen Administratorkonto an:</span><span class="sxs-lookup"><span data-stu-id="be818-270">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="be818-271">Führen Sie das Cmdlet [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) aus, um die Liste der Vertraulichkeitsbezeichnungen und deren GUIDs abzurufen:</span><span class="sxs-lookup"><span data-stu-id="be818-271">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) cmdlet:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="be818-272">Notieren Sie sich die GUIDs für die Vertraulichkeitsbezeichnungen, die Sie auf Ihre Microsoft 365-Gruppen anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="be818-272">Make a note of the GUIDs for the sensitivity labels you want to apply to your Microsoft 365 groups.</span></span>

4. <span data-ttu-id="be818-273">[Stellen Sie jetzt eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="be818-273">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
    <span data-ttu-id="be818-274">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="be818-274">For example:</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```

5. <span data-ttu-id="be818-275">Verwenden Sie den folgenden Befehl als Beispiel, um die Liste der Gruppen abzurufen, die derzeit die Klassifizierung "Allgemein" aufweisen:</span><span class="sxs-lookup"><span data-stu-id="be818-275">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="be818-276">Fügen Sie für jede Gruppe die neue Vertraulichkeitsbezeichnungs-GUID hinzu.</span><span class="sxs-lookup"><span data-stu-id="be818-276">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="be818-277">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="be818-277">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="be818-278">Wiederholen Sie die Schritte 5 und 6 für die restlichen Gruppenklassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="be818-278">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="be818-279">Überwachen von Vertraulichkeitsbezeichnungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="be818-279">Auditing sensitivity label activities</span></span>

<span data-ttu-id="be818-280">Wenn jemand ein Dokument auf eine Website hochlädt, die mit einer Vertraulichkeitsbezeichnung geschützt ist, und das Dokument eine Vertraulichkeitsbezeichnung mit [höherer Priorität](sensitivity-labels.md#label-priority-order-matters) als die auf die Website angewendete Vertraulichkeitsbezeichnung aufweist, wird diese Aktion nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="be818-280">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="be818-281">Angenommen, Sie haben die Bezeichnung **Allgemein** auf eine SharePoint-Website angewendet, und jemand lädt ein Dokument mit der Bezeichnung **Vertraulich** auf diese Site hoch.</span><span class="sxs-lookup"><span data-stu-id="be818-281">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="be818-282">Da eine Vertraulichkeitsbezeichnung mit einer höheren Priorität Inhalte kennzeichnet, die eine höhere Vertraulichkeitsstufe aufweisen, als Inhalte mit einer niedrigeren Priorität, könnte dies ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="be818-282">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="be818-283">Obwohl die Aktion nicht blockiert ist, wird sie überwacht und generiert automatisch eine E-Mail-Nachricht an die Person, die das Dokument hochgeladen hat und den Websiteadministrator.</span><span class="sxs-lookup"><span data-stu-id="be818-283">Although the action isn't blocked, it is audited and automatically generates an email to the person who uploaded the document and the site administrator.</span></span> <span data-ttu-id="be818-284">Als Resultat können der Benutzer und der Administrator Dokumente mit abweichender Bezeichnungspriorität identifizieren und bei Bedarf Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="be818-284">As a result, both the user and administrators can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="be818-285">Löschen oder verschieben Sie zum Beispiel das hochgeladene Dokument von der Website.</span><span class="sxs-lookup"><span data-stu-id="be818-285">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="be818-286">Es würde kein Sicherheitsrisiko darstellen, wenn die auf ein Dokument angewendete Vertraulichkeitsbezeichnung eine niedrigere Priorität aufweist als die auf die Website angewendete Vertraulichkeitsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="be818-286">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="be818-287">Angenommen, ein Dokument, das als **Allgemein** bezeichnet ist, wird auf eine Website hochgeladen, die mit **Vertraulich** bezeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="be818-287">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="be818-288">In diesem Szenario wird kein Überwachungsereignis und keine E-Mail erzeugt.</span><span class="sxs-lookup"><span data-stu-id="be818-288">In this scenario, an auditing event and email aren't generated.</span></span>

<span data-ttu-id="be818-289">Um das Überwachungsprotokoll nach diesem Ereignis zu durchsuchen, suchen Sie nach **Konflikt in Bezug auf die Vertraulichkeitsbezeichnung eines Dokuments** aus der Kategorie **Datei- und Seitenaktivitäten**.</span><span class="sxs-lookup"><span data-stu-id="be818-289">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="be818-290">Die automatisch generierte E-Mail-Nachricht enthält den Betreff **Inkompatible Vertraulichkeitskennzeichnung erkannt** und in der E-Mail-Nachricht wird der Konflikt der Kennzeichnung mit einem Link zum hochgeladenen Dokument und der Website erläutert.</span><span class="sxs-lookup"><span data-stu-id="be818-290">The automatically generated email has the subject **Incompatible sensitivity label detected** and the email message explains the labeling mismatch with a link to the uploaded document and site.</span></span> <span data-ttu-id="be818-291">Sie enthält außerdem einen Link zur Dokumentation, in der erläutert wird, wie Benutzer die Vertraulichkeitskennzeichnung ändern können.</span><span class="sxs-lookup"><span data-stu-id="be818-291">It also contains a documentation link that explains how users can change the sensitivity label.</span></span> <span data-ttu-id="be818-292">Derzeit können diese automatisierten E-Mails nicht deaktiviert oder angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="be818-292">Currently, these automated emails cannot be disabled or customized.</span></span>

<span data-ttu-id="be818-293">Wenn jemand einer Website oder Gruppe eine Vertraulichkeitsbezeichnung hinzufügt oder eine Vertraulichkeitsbezeichnung von einer Website oder Gruppe entfernt, werden diese Aktivitäten ebenfalls überwacht, jedoch wird nicht automatisch eine E-Mail erzeugt.</span><span class="sxs-lookup"><span data-stu-id="be818-293">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited but without automatically generating an email.</span></span> 

<span data-ttu-id="be818-294">All diese Überwachungsereignisse sind in der Kategorie [Vertraulichkeitsbezeichnungsaktivitäten](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) zu finden.</span><span class="sxs-lookup"><span data-stu-id="be818-294">All these auditing events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> <span data-ttu-id="be818-295">Anweisungen zum Durchsuchen des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="be818-295">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="how-to-disable-sensitivity-labels-for-containers"></a><span data-ttu-id="be818-296">Deaktivieren von Vertraulichkeitsbezeichnungen für Container</span><span class="sxs-lookup"><span data-stu-id="be818-296">How to disable sensitivity labels for containers</span></span>

<span data-ttu-id="be818-297">Sie können Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites unter Verwendung der Anweisungen im Abschnitt [Aktivieren der Unterstützung von Vertraulichkeitsbezeichnungen in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell) deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="be818-297">You can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="be818-298">Wenn Sie das Feature jedoch deaktivieren möchten, geben Sie in Schritt 5 `$setting["EnableMIPLabels"] = "False"`an.</span><span class="sxs-lookup"><span data-stu-id="be818-298">However, to disable the feature, in step 5, specify `$setting["EnableMIPLabels"] = "False"`.</span></span>

<span data-ttu-id="be818-299">Diese Aktion blendet zusätzlich die Seite **Websites und Gruppeneinstellungen** beim Erstellen oder Bearbeiten von Vertraulichkeitsbezeichnungen aus und setzt zurück, welche Eigenschaft Container für ihre Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="be818-299">In addition to hiding the **Sites and group settings** page when you create or edit sensitivity labels, this action reverts which property the containers use for their configuration.</span></span> <span data-ttu-id="be818-300">Wenn Sie Vertraulichkeitsbezeichnungen für Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites aktivieren, wird die Eigenschaft, die aus **Klassifizierung** (für [Azure AD-Gruppen Klassifizierung](#classic-azure-ad-group-classification)) verwendet wird, auf **Vertraulichkeit**umgestellt.</span><span class="sxs-lookup"><span data-stu-id="be818-300">Enabling sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites switches the property used from **Classification** (used for [Azure AD group classification](#classic-azure-ad-group-classification)) to **Sensitivity**.</span></span> <span data-ttu-id="be818-301">Wenn Sie Vertraulichkeitsbezeichnungen für Container deaktivieren, ignorieren Container die Eigenschaft „Vertraulichkeit“ und verwenden wieder die Eigenschaft „Klassifizierung“.</span><span class="sxs-lookup"><span data-stu-id="be818-301">When you disable sensitivity labels for containers, the containers ignore the Sensitivity property and use the Classification property again.</span></span>

<span data-ttu-id="be818-302">Das bedeutet, dass alle Bezeichnungseinstellungen von Websites und Gruppen, die zuvor auf Container angewendet wurden, nicht erzwungen werden und Container die Bezeichnungen nicht mehr anzeigen.</span><span class="sxs-lookup"><span data-stu-id="be818-302">This means that any label settings from sites and groups previously applied to containers won't be enforced, and containers no longer display the labels.</span></span>

<span data-ttu-id="be818-303">Wenn diesen Containern Azure AD-Klassifizierungswerte zugewiesen wurden, werden die Container wieder auf die Verwendung der Klassifizierungen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="be818-303">If these containers have Azure AD classification values applied to them, the containers revert to using the classifications again.</span></span> <span data-ttu-id="be818-304">Beachten Sie, dass alle neuen Websites oder Gruppen, die nach der Aktivierung des Features erstellt wurden, keine Bezeichnung oder Klassifizierung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="be818-304">Be aware that any new sites or groups that were created after enabling the feature won't display a label or have a classification.</span></span> <span data-ttu-id="be818-305">Für diese Container und alle neuen Container können Sie jetzt Klassifizierungswerte anwenden.</span><span class="sxs-lookup"><span data-stu-id="be818-305">For these containers, and any new containers, you can now apply classification values.</span></span> <span data-ttu-id="be818-306">Weitere Informationen finden Sie unter [SharePoint "moderne" Website-Klassifizierung](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) und [Erstellen von Klassifizierungen für Office-Gruppen in Ihrer Organisation](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).</span><span class="sxs-lookup"><span data-stu-id="be818-306">For more information, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) and [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="be818-307">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="be818-307">Additional resources</span></span>

<span data-ttu-id="be818-308">Sehen Sie sich das aufgezeichnete Webinar und die beantworteten Fragen zum Thema [Verwenden von Vertraulichkeitsbezeichnungen in Microsoft Teams, O365-Gruppen und SharePoint-Websites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380) an.</span><span class="sxs-lookup"><span data-stu-id="be818-308">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

<span data-ttu-id="be818-309">Dieses Webinar wurde aufgezeichnet, als das Feature sich noch in der Vorschau befindet, sodass Sie möglicherweise auf der Benutzeroberfläche einige Diskrepanzen bemerken.</span><span class="sxs-lookup"><span data-stu-id="be818-309">This webinar was recorded when the feature was still in preview, so you might notice some discrepancies in the UI.</span></span> <span data-ttu-id="be818-310">Die Informationen zu diesem Feature sind jedoch weiterhin korrekt und alle neuen Funktionen sind auf dieser Seite dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="be818-310">However, the information for this feature is still accurate, with any new capabilities documented on this page.</span></span>
