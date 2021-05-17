---
title: Zusammenarbeit mit Gästen an einem Dokument
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: In diesem Artikel erfahren Sie, wie Sie mit Gästen an einem Dokument in SharePoint und OneDrive.
ms.openlocfilehash: 9158ec7692ef90eb2e270242472fceb10d0e60b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920228"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="ed8f5-103">Zusammenarbeit mit Gästen an einem Dokument</span><span class="sxs-lookup"><span data-stu-id="ed8f5-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="ed8f5-104">Wenn Sie mit Personen außerhalb Ihrer Organisation an Dokumenten in SharePoint oder OneDrive zusammenarbeiten müssen, können Sie ihnen einen Freigabelink zum Dokument senden.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="ed8f5-105">In diesem Artikel werden die erforderlichen Konfigurationsschritte Microsoft 365, um Freigabelinks für SharePoint und OneDrive anforderungen Ihrer Organisation einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="ed8f5-106">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="ed8f5-106">Video demonstration</span></span>

<span data-ttu-id="ed8f5-107">Dieses Video zeigt die in diesem Dokument beschriebenen Konfigurationsschritte.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="ed8f5-108">Einstellungen für die externe Zusammenarbeit in Azure</span><span class="sxs-lookup"><span data-stu-id="ed8f5-108">Azure external collaboration settings</span></span>

<span data-ttu-id="ed8f5-109">Die Freigabe in Microsoft 365 wird auf der höchsten Ebene von den [Einstellungen für B2B externe Zusammenarbeit in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations) geregelt.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="ed8f5-110">Wenn die Gastfreigabe in Azure AD deaktiviert oder eingeschränkt ist, überschreibt diese Einstellung alle Freigabeeinstellungen, die Sie in azure Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="ed8f5-111">Überprüfen Sie die B2B-Einstellungen für die externe Zusammenarbeit, um sicherzustellen, dass die Freigabe für Gäste nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot der Seite mit den Einstellungen für die Azure Active Directory-Organisationsbeziehungen](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="ed8f5-113">Festlegen der Einstellungen für die Azure Externe Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="ed8f5-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="ed8f5-114">Bei Azure Active Directory an [https://aad.portal.azure.com](https://aad.portal.azure.com) anmelden.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="ed8f5-115">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="ed8f5-116">Klicken Sie auf **Externe Identitäten**.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-116">Click **External identities**.</span></span>
4. <span data-ttu-id="ed8f5-117">Klicken Sie auf dem Bildschirm **Erste Schritte** im linken Navigationsbereich auf **Einstellungen für die externe Zusammenarbeit**.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="ed8f5-118">Stellen Sie sicher, dass sowie **Administratoren und Benutzer mit der Rolle "Einladender" können einladen** als auch **Mitglieder können einladen** beide auf **Ja** festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="ed8f5-119">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="ed8f5-120">Beachten Sie die Einstellungen im Bereich **Einschränkungen für die Zusammenarbeit**.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="ed8f5-121">Stellen Sie sicher, dass die Domänen der Gäste, mit denen Sie zusammenarbeiten möchten, nicht blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="ed8f5-122">Wenn Sie mit Gästen aus mehreren Organisationen arbeiten, könnten Sie möglicherweise Interesse daran haben, ihren Zugriff auf Verzeichnisdaten einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="ed8f5-123">Dies wird es ihnen verhindern zu sehen, wer sonst noch Gast im Verzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="ed8f5-124">Wählen Sie dazu unter **Einschränkungen des Gastzugriffs** die Einstellung **Gastbenutzer haben eingeschränkten Zugriff auf Eigenschaften und die Mitgliedschaft bei den Einstellungen der Verzeichnisobjekte** oder **Zugriff der Gastbenutzer ist auf Eigenschaften und die Mitgliedschaft bei ihren eigenen Verzeichnisobjekten eingeschränkt**.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="ed8f5-125">SharePoint freigabeeinstellungen auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="ed8f5-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="ed8f5-126">Damit Personen außerhalb Ihrer Organisation Zugriff auf ein Dokument in SharePoint oder OneDrive haben, müssen die SharePoint- und OneDrive-Freigabeeinstellungen auf Organisationsebene die Freigabe für Personen außerhalb Ihrer Organisation zulassen.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="ed8f5-127">Die Einstellungen auf Organisationsebene für SharePoint bestimmen die Einstellungen, die für einzelne Websites SharePoint werden.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="ed8f5-128">Websiteeinstellungen können nicht passiver sein als die Einstellungen auf Organisationsebene.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="ed8f5-129">Die Einstellung auf Organisationsebene für OneDrive bestimmt die Freigabeebene, die in den Benutzerbibliotheken OneDrive wird.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="ed8f5-130">Wenn SharePoint und OneDrive nicht authentifizierte Datei- und Ordnerfreigabe zulassen möchten, wählen Sie **Jeder aus.**</span><span class="sxs-lookup"><span data-stu-id="ed8f5-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="ed8f5-131">Wenn Sie sicherstellen möchten, dass Personen außerhalb Ihrer Organisation authentifiziert werden müssen, wählen Sie **Neu und vorhandene Gäste aus.**</span><span class="sxs-lookup"><span data-stu-id="ed8f5-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="ed8f5-132">*Jeder* Links ist die einfachste Möglichkeit zum Teilen: Personen außerhalb Ihrer Organisation können den Link ohne Authentifizierung öffnen und können ihn an andere personen übergeben.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="ed8f5-133">Wählen SharePoint sie die lässigste Einstellung aus, die von jeder Website in Ihrer Organisation benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="ed8f5-135">So legt man SharePoint-Freigabeeinstellungen auf Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="ed8f5-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="ed8f5-136">Klicken Sie im Microsoft 365 Admin Center im linken Navigationsbereich unter **Admin Center** auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="ed8f5-137">Klicken Sie SharePoint Admin Center im linken Navigationsbereich unter **Richtlinien** auf **Freigeben.**</span><span class="sxs-lookup"><span data-stu-id="ed8f5-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="ed8f5-138">Stellen Sie sicher, dass die externe Freigabe für SharePoint oder OneDrive auf **Jeder** oder **Neue und vorhandene Gäste festgelegt ist.**</span><span class="sxs-lookup"><span data-stu-id="ed8f5-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="ed8f5-139">(Beachten Sie, dass OneDrive einstellung nicht zulässiger als die Einstellung SharePoint sein kann.)</span><span class="sxs-lookup"><span data-stu-id="ed8f5-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="ed8f5-140">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="ed8f5-141">SharePoint-Standardlinkeinstellungen auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="ed8f5-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="ed8f5-142">Die Standardeinstellungen für die Datei- und -ordnerverknüpfung bestimmen die Verknüpfungsoption, die Benutzern standardmäßig angezeigt wird, wenn sie eine Datei oder einen Ordner freigeben.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="ed8f5-143">Benutzer können, wenn sie so möchten, die Verknüpfungsart vor der Freigabe in eine der anderen Optionen ändern.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="ed8f5-144">Beachten Sie, dass sich diese Einstellung SharePoint Websites in Ihrer Organisation sowie auf OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="ed8f5-145">Wählen Sie einen Link aus einem der folgenden Typen aus, der dann standardmäßig ausgewählt wird, wenn Benutzer Dateien und Ordner freigeben:</span><span class="sxs-lookup"><span data-stu-id="ed8f5-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="ed8f5-146">**Jeder mit dem Link** – Wählen Sie diese Option aus, wenn Sie mit einer großen Anzahl nicht authentifizierter Dateien und Ordnerfreigaben rechnen.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="ed8f5-147">Wenn Sie *Jeder*-Links erlauben wollen, aber zufällige nicht authentifizierte Freigaben befürchten, erwägen Sie eine der anderen Optionen als Standard.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="ed8f5-148">Diese Verknüpfungsart ist nur verfügbar, wenn Sie die Freigabe auf **Jeder** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="ed8f5-149">**Nur Personen in Ihrer Organisation** – Wählen Sie diese Option, wenn Sie erwarten, dass die meisten Freigaben von Dateien und Ordnern zwischen Personen innerhalb Ihrer Organisation stattfinden werden.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="ed8f5-150">**Bestimmte Personen** – erwägen Sie diese Option, wenn Sie erwarten, dass Sie viele Dateien und Ordner an Gäste freigeben werden.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="ed8f5-151">Dieser Typ von Link arbeitet mit Gästen und erfordert deren Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot der Freigabeeinstellungen auf Organisationsebene für Dateien und Ordner in SharePoint und OneDrive](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="ed8f5-153">So legen Sie SharePoint und OneDrive standardverknüpfungseinstellungen auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="ed8f5-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="ed8f5-154">Navigieren Sie zur Seite „Freigabe“ im SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="ed8f5-155">Wählen Sie unter **Datei- und Ordnerlinks** den Link zur Standardfreigabe, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="ed8f5-156">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="ed8f5-157">Wenn Sie die Berechtigung für den Freigabelink festlegen möchten, wählen Sie unter Wählen Sie die Berechtigung aus, die standardmäßig für **Freigabelinks ausgewählt ist.**</span><span class="sxs-lookup"><span data-stu-id="ed8f5-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="ed8f5-158">Wählen **Sie Ansicht** aus, wenn nicht authentifizierte Benutzer keine Änderungen an den Dateien und Ordnern vornehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="ed8f5-159">Wählen **Sie Bearbeiten** aus, wenn nicht authentifizierte Benutzer Änderungen an den Dateien und Ordnern vornehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="ed8f5-160">Beachten Sie, dass die oben genannten beiden Voraboptionen nicht nur für Gäste/externe Benutzer, sondern auch für interne Benutzer angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="ed8f5-161">Die von Ihnen festgelegte Berechtigungsoption wird durch Selbstverwaltung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="ed8f5-162">So legen Sie Berechtigungen für Links fest, die die Freigabe für alle Personen zulassen</span><span class="sxs-lookup"><span data-stu-id="ed8f5-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="ed8f5-163">Geben Sie **unter Diese Links die folgenden Berechtigungen ein:** Unterbereich,</span><span class="sxs-lookup"><span data-stu-id="ed8f5-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="ed8f5-164">In der **Dropdownliste** Dateien</span><span class="sxs-lookup"><span data-stu-id="ed8f5-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="ed8f5-165">Wählen **Sie Ansicht und Bearbeiten** aus, wenn nicht authentifizierte Benutzer Änderungen an den Dateien vornehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="ed8f5-166">Wählen **Sie Ansicht** aus, wenn nicht authentifizierte Benutzer keine Änderungen an den Dateien vornehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="ed8f5-167">In **der Dropdownliste** Ordner</span><span class="sxs-lookup"><span data-stu-id="ed8f5-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="ed8f5-168">Wählen **Sie Anzeigen, Bearbeiten und Hochladen aus,** wenn Nicht authentifizierte Benutzer Änderungen an den Ordnern vornehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="ed8f5-169">Wählen **Sie Ansicht** aus, wenn nicht authentifizierte Benutzer keine Änderungen an den Ordnern vornehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="ed8f5-170">SharePoint-Freigabeeinstellungen auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="ed8f5-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="ed8f5-171">Wenn Sie Dateien und Ordner freigeben, die sich an einer SharePoint befinden, müssen Sie auch die Freigabeeinstellungen auf Websiteebene für diese Website überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="ed8f5-173">So legt man Freigabeeinstellungen auf Websiteebene fest</span><span class="sxs-lookup"><span data-stu-id="ed8f5-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="ed8f5-174">Erweitern Sie im SharePoint Admin Center links im Navigationsbereich **Websites** und klicken Sie auf **Aktive Websites**.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="ed8f5-175">Wählen Sie die Website aus, auf der Sie Dateien und Ordner für Gäste freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="ed8f5-176">Scrollen Sie rechts über die Zeile (in der die ausgewählte Website vorhanden ist), und klicken Sie in der Spalte Externe **Freigabe auf eine beliebige** Stelle.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="ed8f5-177">Klicken Sie auf der angezeigten Seite auf **die Registerkarte** Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="ed8f5-178">Klicken Sie **im Bereich Externe** Freigabe auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="ed8f5-179">Vergewissern Sie sich, dass die Freigabe auf **Jeder** oder **Neue und vorhandene Gäste** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="ed8f5-180">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="ed8f5-181">Benutzer einladen</span><span class="sxs-lookup"><span data-stu-id="ed8f5-181">Invite users</span></span>

<span data-ttu-id="ed8f5-182">Die Einstellungen für die Gastfreigabe sind jetzt konfiguriert. Benutzer können nun Dateien und Ordner für Personen außerhalb Ihrer Organisation freigeben.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="ed8f5-183">Weitere [Informationen finden OneDrive Dateien](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) und Ordner freigeben und SharePoint [oder](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) Ordner freigeben.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed8f5-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed8f5-184">See also</span></span>

[<span data-ttu-id="ed8f5-185">Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="ed8f5-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="ed8f5-186">Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste</span><span class="sxs-lookup"><span data-stu-id="ed8f5-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="ed8f5-187">SharePoint- und OneDrive-Integration in Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="ed8f5-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)