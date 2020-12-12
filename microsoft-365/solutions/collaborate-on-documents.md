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
description: In diesem Artikel erfahren Sie, wie Sie mit Gästen in einem Dokument in SharePoint und OneDrive zusammenarbeiten.
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663511"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="effb9-103">Zusammenarbeit mit Gästen an einem Dokument</span><span class="sxs-lookup"><span data-stu-id="effb9-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="effb9-104">Wenn Sie mit Personen außerhalb Ihrer Organisation in Dokumenten in SharePoint oder OneDrive zusammenarbeiten müssen, können Sie Ihnen einen Freigabe Link an das Dokument senden.</span><span class="sxs-lookup"><span data-stu-id="effb9-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="effb9-105">In diesem Artikel werden die Microsoft 365-Konfigurationsschritte durchlaufen, die erforderlich sind, um Freigabe-Links für SharePoint und OneDrive für die Anforderungen Ihrer Organisation einzurichten.</span><span class="sxs-lookup"><span data-stu-id="effb9-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="effb9-106">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="effb9-106">Video demonstration</span></span>

<span data-ttu-id="effb9-107">Dieses Video zeigt die in diesem Dokument beschriebenen Konfigurationsschritte.</span><span class="sxs-lookup"><span data-stu-id="effb9-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="effb9-108">Einstellungen für Azure-externe Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="effb9-108">Azure external collaboration settings</span></span>

<span data-ttu-id="effb9-109">Die Freigabe in Microsoft 365 wird auf der höchsten Ebene durch die [Einstellungen für die B2B-externe Zusammenarbeit in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)gesteuert.</span><span class="sxs-lookup"><span data-stu-id="effb9-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="effb9-110">Wenn die Gast Freigabe in Azure AD deaktiviert oder eingeschränkt ist, überschreibt diese Einstellung alle Freigabeeinstellungen, die Sie in Microsoft 365 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="effb9-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="effb9-111">Überprüfen Sie die Einstellungen für die externe Zusammenarbeit in B2B, um sicherzustellen, dass die Freigabe für Gäste nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="effb9-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot der Seite mit den Einstellungen für die Azure Active Directory-Organisationsbeziehungen](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="effb9-113">So legen Sie Einstellungen für die externe Zusammenarbeit fest</span><span class="sxs-lookup"><span data-stu-id="effb9-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="effb9-114">Melden Sie sich bei Azure Active Directory unter an [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="effb9-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="effb9-115">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="effb9-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="effb9-116">Klicken Sie auf **externe Identitäten**.</span><span class="sxs-lookup"><span data-stu-id="effb9-116">Click **External identities**.</span></span>
4. <span data-ttu-id="effb9-117">Klicken Sie auf dem Bildschirm **Erste Schritte** im linken Navigationsbereich auf **Einstellungen für externe Zusammenarbeit**.</span><span class="sxs-lookup"><span data-stu-id="effb9-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="effb9-118">Stellen Sie sicher, dass **Administratoren und Benutzer in der Rolle "Gast einladender" eingeladen** werden und **Mitglieder einladen können** , beide auf " **Ja**" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="effb9-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="effb9-119">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="effb9-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="effb9-120">Beachten Sie die Einstellungen im Abschnitt Einschränkungen für die **Zusammenarbeit** .</span><span class="sxs-lookup"><span data-stu-id="effb9-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="effb9-121">Stellen Sie sicher, dass die Domänen der Gäste, mit denen Sie zusammenarbeiten möchten, nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="effb9-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="effb9-122">Wenn Sie mit Gästen aus mehreren Organisationen zusammenarbeiten, möchten Sie möglicherweise die Möglichkeit zum Zugriff auf Verzeichnisdaten einschränken.</span><span class="sxs-lookup"><span data-stu-id="effb9-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="effb9-123">Dadurch wird verhindert, dass Sie sehen, wer sonst ein Gast im Verzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="effb9-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="effb9-124">Wählen Sie dazu unter **Benutzerzugriffs Einschränkungen** für Gast die Option **Gastbenutzer haben begrenzten Zugriff auf Eigenschaften und Mitgliedschaft in Verzeichnisobjekt Einstellungen** oder **Gastbenutzer Zugriff ist auf Eigenschaften und Mitgliedschaften ihrer eigenen Verzeichnisobjekte beschränkt**.</span><span class="sxs-lookup"><span data-stu-id="effb9-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="effb9-125">SharePoint-Freigabeeinstellungen auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="effb9-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="effb9-126">Damit Personen außerhalb Ihrer Organisation Zugriff auf ein Dokument in SharePoint oder OneDrive haben, müssen die Freigabeeinstellungen für SharePoint und OneDrive auf Organisationsebene die Freigabe für Personen außerhalb Ihrer Organisation zulassen.</span><span class="sxs-lookup"><span data-stu-id="effb9-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="effb9-127">Die Einstellungen auf Organisationsebene für SharePoint bestimmen die Einstellungen, die für einzelne SharePoint-Websites verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="effb9-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="effb9-128">Websiteeinstellungen dürfen nicht so restriktiv wie die Einstellungen auf Organisationsebene sein.</span><span class="sxs-lookup"><span data-stu-id="effb9-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="effb9-129">Die Einstellung auf Organisationsebene für OneDrive bestimmt die Freigabeebene, die in den OneDrive-Bibliotheken der Benutzer verfügbar sein wird.</span><span class="sxs-lookup"><span data-stu-id="effb9-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="effb9-130">Wenn Sie für SharePoint und OneDrive die nicht authentifizierte Datei-und Ordnerfreigabe zulassen möchten, wählen Sie **jeden** aus.</span><span class="sxs-lookup"><span data-stu-id="effb9-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="effb9-131">Wenn Sie sicherstellen möchten, dass sich Personen außerhalb Ihrer Organisation authentifizieren müssen, wählen Sie **neue und vorhandene Gäste** aus.</span><span class="sxs-lookup"><span data-stu-id="effb9-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="effb9-132">*Jeder* Links ist die einfachste Möglichkeit zur Freigabe: Personen außerhalb Ihrer Organisation können die Verknüpfung ohne Authentifizierung öffnen und können Sie an andere weitergeben.</span><span class="sxs-lookup"><span data-stu-id="effb9-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="effb9-133">Wählen Sie für SharePoint die frei zügigste Einstellung aus, die von einer beliebigen Website in Ihrer Organisation benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="effb9-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="effb9-135">So legen Sie Freigabeeinstellungen für SharePoint auf Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="effb9-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="effb9-136">Klicken Sie im Microsoft 365 Admin Center im linken Navigationsbereich unter **Admin Centers** auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="effb9-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="effb9-137">Klicken Sie im SharePoint Admin Center im linken Navigationsbereich unter **Richtlinien** auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="effb9-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="effb9-138">Stellen Sie sicher, dass die externe Freigabe für SharePoint oder OneDrive auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="effb9-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="effb9-139">(Beachten Sie, dass die OneDrive-Einstellung nicht restriktiver als die SharePoint-Einstellung sein kann.)</span><span class="sxs-lookup"><span data-stu-id="effb9-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="effb9-140">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="effb9-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="effb9-141">Standard Link Einstellungen für SharePoint auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="effb9-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="effb9-142">Die Standardeinstellungen für Datei-und Ordnerverknüpfung bestimmen die Verknüpfungsoption, die Benutzern standardmäßig angezeigt wird, wenn Sie eine Datei oder einen Ordner freigeben.</span><span class="sxs-lookup"><span data-stu-id="effb9-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="effb9-143">Benutzer können den Verknüpfungstyp in eine der anderen Optionen vor der Freigabe ändern, falls gewünscht.</span><span class="sxs-lookup"><span data-stu-id="effb9-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="effb9-144">Beachten Sie, dass sich diese Einstellung auf SharePoint-Websites in Ihrer Organisation sowie auf OneDrive auswirkt.</span><span class="sxs-lookup"><span data-stu-id="effb9-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="effb9-145">Wählen Sie einen Link von einem der folgenden Typen aus, der dann standardmäßig ausgewählt wird, wenn Benutzer Dateien und Ordner freigeben:</span><span class="sxs-lookup"><span data-stu-id="effb9-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="effb9-146">**Jeder, der über den Link verfügt** – wählen Sie diese Option aus, wenn Sie eine Vielzahl von nicht authentifizierten Datei-und Ordner Freigaben erwarten.</span><span class="sxs-lookup"><span data-stu-id="effb9-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="effb9-147">Wenn Sie *alle* Links zulassen möchten, jedoch über versehentliche nicht authentifizierte Freigaben besorgt sind, sollten Sie eine der anderen Optionen als Standard verwenden.</span><span class="sxs-lookup"><span data-stu-id="effb9-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="effb9-148">Dieser Linktyp ist nur verfügbar, wenn Sie die Freigabe von **Benutzern** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="effb9-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="effb9-149">**Nur Personen in Ihrer Organisation** – wählen Sie diese Option aus, wenn Sie davon ausgehen, dass die meisten Datei-und Ordner Freigaben für Personen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="effb9-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="effb9-150">**Bestimmte Personen** – diese Option wird empfohlen, wenn Sie eine Vielzahl von Datei-und Ordner Freigaben für Gäste erwarten.</span><span class="sxs-lookup"><span data-stu-id="effb9-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="effb9-151">Diese Art von Link funktioniert mit Gästen und erfordert die Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="effb9-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot der Freigabeeinstellungen auf Organisationsebene für Dateien und Ordner in SharePoint und OneDrive](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="effb9-153">So legen Sie die Standard Link Einstellungen für SharePoint und OneDrive auf Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="effb9-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="effb9-154">Navigieren Sie im SharePoint Admin Center zur Seite Freigabe.</span><span class="sxs-lookup"><span data-stu-id="effb9-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="effb9-155">Wählen Sie unter **Datei-und Ordner Links** den standardmäßigen Freigabe Link aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="effb9-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="effb9-156">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="effb9-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="effb9-157">Klicken Sie zum Festlegen der Berechtigung für den Freigabe Link unter **Wählen Sie die Berechtigung aus, die standardmäßig für Freigabelinks ausgewählt ist.**</span><span class="sxs-lookup"><span data-stu-id="effb9-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="effb9-158">Wählen Sie **Ansicht** aus, wenn Sie nicht möchten, dass nicht authentifizierte Benutzer Änderungen an den Dateien und Ordnern vornehmen.</span><span class="sxs-lookup"><span data-stu-id="effb9-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="effb9-159">Wählen Sie **Bearbeiten** aus, wenn Sie zulassen möchten, dass nicht authentifizierte Benutzer Änderungen an den Dateien und Ordnern vornehmen.</span><span class="sxs-lookup"><span data-stu-id="effb9-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="effb9-160">Beachten Sie, dass die beiden obigen premission-Optionen nicht nur für Gäste/externe Benutzer, sondern auch für interne Benutzer angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="effb9-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="effb9-161">Die von Ihnen gewählte Berechtigungsoption wird durch selbst Diskretion bestimmt.</span><span class="sxs-lookup"><span data-stu-id="effb9-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="effb9-162">So legen Sie Berechtigungen für Links fest, die die Freigabe für beliebige Personen zulassen</span><span class="sxs-lookup"><span data-stu-id="effb9-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="effb9-163">Unter den **folgenden Links können diese Berechtigungen erteilt werden:** Unterbereich,</span><span class="sxs-lookup"><span data-stu-id="effb9-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="effb9-164">In der Dropdownliste **Dateien**</span><span class="sxs-lookup"><span data-stu-id="effb9-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="effb9-165">Wählen Sie **anzeigen und bearbeiten** aus, wenn Sie zulassen möchten, dass nicht authentifizierte Benutzer Änderungen an den Dateien vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="effb9-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="effb9-166">Wählen Sie **Ansicht** aus, wenn Sie nicht möchten, dass nicht authentifizierte Benutzer Änderungen an den Dateien vornehmen.</span><span class="sxs-lookup"><span data-stu-id="effb9-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="effb9-167">In der Dropdownliste **Ordner**</span><span class="sxs-lookup"><span data-stu-id="effb9-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="effb9-168">Wählen Sie **anzeigen, bearbeiten und hochladen** aus, wenn Sie zulassen möchten, dass nicht authentifizierte Benutzer Änderungen an den Ordnern vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="effb9-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="effb9-169">Wählen Sie **Ansicht** aus, wenn Sie nicht möchten, dass nicht authentifizierte Benutzer Änderungen an den Ordnern vornehmen.</span><span class="sxs-lookup"><span data-stu-id="effb9-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="effb9-170">SharePoint-Freigabeeinstellungen auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="effb9-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="effb9-171">Wenn Sie Dateien und Ordner in einer SharePoint-Website freigeben, müssen Sie auch die Freigabeeinstellungen auf Websiteebene für diese Website überprüfen.</span><span class="sxs-lookup"><span data-stu-id="effb9-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="effb9-173">So legen Sie Freigabeeinstellungen auf Websiteebene fest</span><span class="sxs-lookup"><span data-stu-id="effb9-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="effb9-174">Erweitern Sie im SharePoint Admin Center im linken Navigationsbereich den Knoten **Websites** , und klicken Sie dann auf **aktive Standorte**.</span><span class="sxs-lookup"><span data-stu-id="effb9-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="effb9-175">Wählen Sie die Website aus, für die Sie Dateien und Ordner für Gäste freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="effb9-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="effb9-176">Scrollen Sie nach rechts in der Zeile (in der die ausgewählte Website vorhanden ist), und klicken Sie auf eine beliebige Stelle in der Spalte **externe Freigabe** .</span><span class="sxs-lookup"><span data-stu-id="effb9-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="effb9-177">Klicken Sie auf der Seite, die sich öffnet, auf Registerkarte **Richtlinien** .</span><span class="sxs-lookup"><span data-stu-id="effb9-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="effb9-178">Klicken Sie im Bereich **externe Freigabe** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="effb9-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="effb9-179">Stellen Sie sicher, dass die Freigabe auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="effb9-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="effb9-180">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="effb9-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="effb9-181">Benutzer einladen</span><span class="sxs-lookup"><span data-stu-id="effb9-181">Invite users</span></span>

<span data-ttu-id="effb9-182">Einstellungen für die Gast Freigabe sind jetzt konfiguriert; Damit können Benutzer nun Dateien und Ordner für Personen außerhalb Ihrer Organisation freigeben.</span><span class="sxs-lookup"><span data-stu-id="effb9-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="effb9-183">Weitere Informationen finden Sie unter [Freigeben von OneDrive-Dateien und-Ordnern](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) und Freigeben von [SharePoint-Dateien oder-Ordnern](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .</span><span class="sxs-lookup"><span data-stu-id="effb9-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="effb9-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="effb9-184">See also</span></span>

[<span data-ttu-id="effb9-185">Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="effb9-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="effb9-186">Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste</span><span class="sxs-lookup"><span data-stu-id="effb9-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="effb9-187">SharePoint-und OneDrive-Integration mit Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="effb9-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
