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
ms.openlocfilehash: bb97beaacf6a433e4fc5c38a897327d1e359ffb1
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613514"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="f84d1-103">Zusammenarbeit mit Gästen an einem Dokument</span><span class="sxs-lookup"><span data-stu-id="f84d1-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="f84d1-104">Wenn Sie mit Personen außerhalb Ihrer Organisation in Dokumenten in SharePoint oder OneDrive zusammenarbeiten müssen, können Sie Ihnen einen Freigabe Link an das Dokument senden.</span><span class="sxs-lookup"><span data-stu-id="f84d1-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="f84d1-105">In diesem Artikel werden die Microsoft 365-Konfigurationsschritte durchlaufen, die erforderlich sind, um Freigabe-Links für SharePoint und OneDrive für die Anforderungen Ihrer Organisation einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f84d1-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="f84d1-106">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="f84d1-106">Video demonstration</span></span>

<span data-ttu-id="f84d1-107">Dieses Video zeigt die in diesem Dokument beschriebenen Konfigurationsschritte.</span><span class="sxs-lookup"><span data-stu-id="f84d1-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="f84d1-108">Azure Organizational Relationships-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="f84d1-108">Azure organizational relationships settings</span></span>

<span data-ttu-id="f84d1-109">Die Freigabe in Microsoft 365 wird auf der höchsten Ebene durch die [Einstellungen für organisatorische Beziehungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)gesteuert.</span><span class="sxs-lookup"><span data-stu-id="f84d1-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="f84d1-110">Wenn die Gast Freigabe in Azure AD deaktiviert oder eingeschränkt ist, überschreibt diese Einstellung alle Freigabeeinstellungen, die Sie in Microsoft 365 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f84d1-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="f84d1-111">Überprüfen Sie die Einstellungen für Organisationsbeziehungen, um sicherzustellen, dass die Freigabe für Gäste nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="f84d1-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot der Seite mit den Einstellungen für die Azure Active Directory-Organisationsbeziehungen](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="f84d1-113">So legen Sie Einstellungen für die Organisationsbeziehung fest</span><span class="sxs-lookup"><span data-stu-id="f84d1-113">To set organizational relationship settings</span></span>

<span data-ttu-id="f84d1-114">So legen Sie Einstellungen für die externe Zusammenarbeit fest</span><span class="sxs-lookup"><span data-stu-id="f84d1-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="f84d1-115">Melden Sie sich bei Azure Active Directory unter an [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="f84d1-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="f84d1-116">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f84d1-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="f84d1-117">Klicken Sie auf **externe Identitäten**.</span><span class="sxs-lookup"><span data-stu-id="f84d1-117">Click **External identities**.</span></span>
4. <span data-ttu-id="f84d1-118">Klicken Sie auf dem Bildschirm **Erste Schritte** im linken Navigationsbereich auf **Einstellungen für externe Zusammenarbeit**.</span><span class="sxs-lookup"><span data-stu-id="f84d1-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="f84d1-119">Stellen Sie sicher, dass **Administratoren und Benutzer in der Rolle "Gast einladender" eingeladen** werden und **Mitglieder einladen können** , beide auf " **Ja**" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f84d1-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="f84d1-120">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f84d1-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="f84d1-121">Beachten Sie die Einstellungen im Abschnitt Einschränkungen für die **Zusammenarbeit** .</span><span class="sxs-lookup"><span data-stu-id="f84d1-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="f84d1-122">Stellen Sie sicher, dass die Domänen der Gäste, mit denen Sie zusammenarbeiten möchten, nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="f84d1-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="f84d1-123">Wenn Sie mit Gästen aus mehreren Organisationen zusammenarbeiten, möchten Sie möglicherweise die Möglichkeit zum Zugriff auf Verzeichnisdaten einschränken.</span><span class="sxs-lookup"><span data-stu-id="f84d1-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="f84d1-124">Dadurch wird verhindert, dass Sie sehen, wer sonst ein Gast im Verzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="f84d1-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="f84d1-125">Wählen Sie dazu unter **Benutzerzugriffs Einschränkungen** für Gast die Option **Gastbenutzer haben begrenzten Zugriff auf Eigenschaften und Mitgliedschaft in Verzeichnisobjekt Einstellungen** oder **Gastbenutzer Zugriff ist auf Eigenschaften und Mitgliedschaften ihrer eigenen Verzeichnisobjekte beschränkt**.</span><span class="sxs-lookup"><span data-stu-id="f84d1-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="f84d1-126">SharePoint-Freigabeeinstellungen auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="f84d1-126">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="f84d1-127">Damit Personen außerhalb Ihrer Organisation Zugriff auf ein Dokument in SharePoint oder OneDrive haben, müssen die Freigabeeinstellungen für SharePoint und OneDrive auf Organisationsebene die Freigabe für Personen außerhalb Ihrer Organisation zulassen.</span><span class="sxs-lookup"><span data-stu-id="f84d1-127">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="f84d1-128">Die Einstellungen auf Organisationsebene für SharePoint bestimmen die Einstellungen, die für einzelne SharePoint-Websites verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f84d1-128">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="f84d1-129">Websiteeinstellungen dürfen nicht so restriktiv wie die Einstellungen auf Organisationsebene sein.</span><span class="sxs-lookup"><span data-stu-id="f84d1-129">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="f84d1-130">Die Einstellung auf Organisationsebene für OneDrive bestimmt die Freigabeebene, die in den OneDrive-Bibliotheken der Benutzer verfügbar sein wird.</span><span class="sxs-lookup"><span data-stu-id="f84d1-130">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="f84d1-131">Wenn Sie für SharePoint und OneDrive die nicht authentifizierte Datei-und Ordnerfreigabe zulassen möchten, wählen Sie **jeden** aus.</span><span class="sxs-lookup"><span data-stu-id="f84d1-131">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="f84d1-132">Wenn Sie sicherstellen möchten, dass sich Personen außerhalb Ihrer Organisation authentifizieren müssen, wählen Sie **neue und vorhandene Gäste** aus.</span><span class="sxs-lookup"><span data-stu-id="f84d1-132">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="f84d1-133">*Jeder* Links ist die einfachste Möglichkeit zur Freigabe: Personen außerhalb Ihrer Organisation können die Verknüpfung ohne Authentifizierung öffnen und können Sie an andere weitergeben.</span><span class="sxs-lookup"><span data-stu-id="f84d1-133">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="f84d1-134">Wählen Sie für SharePoint die frei zügigste Einstellung aus, die von einer beliebigen Website in Ihrer Organisation benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="f84d1-134">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="f84d1-136">So legen Sie Freigabeeinstellungen für SharePoint auf Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="f84d1-136">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="f84d1-137">Klicken Sie im Microsoft 365 Admin Center im linken Navigationsbereich unter **Admin Centers** auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f84d1-137">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="f84d1-138">Klicken Sie im SharePoint Admin Center im linken Navigationsbereich unter **Richtlinien** auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="f84d1-138">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="f84d1-139">Stellen Sie sicher, dass die externe Freigabe für SharePoint oder OneDrive auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f84d1-139">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="f84d1-140">(Beachten Sie, dass die OneDrive-Einstellung nicht restriktiver als die SharePoint-Einstellung sein kann.)</span><span class="sxs-lookup"><span data-stu-id="f84d1-140">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="f84d1-141">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f84d1-141">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="f84d1-142">Standard Link Einstellungen für SharePoint auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="f84d1-142">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="f84d1-143">Die Standardeinstellungen für Datei-und Ordnerverknüpfung bestimmen die Verknüpfungsoption, die Benutzern standardmäßig angezeigt wird, wenn Sie eine Datei oder einen Ordner freigeben.</span><span class="sxs-lookup"><span data-stu-id="f84d1-143">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="f84d1-144">Benutzer können den Verknüpfungstyp in eine der anderen Optionen vor der Freigabe ändern, falls gewünscht.</span><span class="sxs-lookup"><span data-stu-id="f84d1-144">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="f84d1-145">Beachten Sie, dass sich diese Einstellung auf SharePoint-Websites in Ihrer Organisation sowie auf OneDrive auswirkt.</span><span class="sxs-lookup"><span data-stu-id="f84d1-145">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="f84d1-146">Wählen Sie einen Link von einem der folgenden Typen aus, der dann standardmäßig ausgewählt wird, wenn Benutzer Dateien und Ordner freigeben:</span><span class="sxs-lookup"><span data-stu-id="f84d1-146">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="f84d1-147">**Jeder, der über den Link verfügt** – wählen Sie diese Option aus, wenn Sie eine Vielzahl von nicht authentifizierten Datei-und Ordner Freigaben erwarten.</span><span class="sxs-lookup"><span data-stu-id="f84d1-147">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="f84d1-148">Wenn Sie *alle* Links zulassen möchten, jedoch über versehentliche nicht authentifizierte Freigaben besorgt sind, sollten Sie eine der anderen Optionen als Standard verwenden.</span><span class="sxs-lookup"><span data-stu-id="f84d1-148">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="f84d1-149">Dieser Linktyp ist nur verfügbar, wenn Sie die Freigabe von **Benutzern** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="f84d1-149">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="f84d1-150">**Nur Personen in Ihrer Organisation** – wählen Sie diese Option aus, wenn Sie davon ausgehen, dass die meisten Datei-und Ordner Freigaben für Personen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="f84d1-150">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="f84d1-151">**Bestimmte Personen** – diese Option wird empfohlen, wenn Sie eine Vielzahl von Datei-und Ordner Freigaben für Gäste erwarten.</span><span class="sxs-lookup"><span data-stu-id="f84d1-151">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="f84d1-152">Diese Art von Link funktioniert mit Gästen und erfordert die Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f84d1-152">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot der Freigabeeinstellungen auf Organisationsebene für Dateien und Ordner in SharePoint und OneDrive](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="f84d1-154">So legen Sie die Standard Link Einstellungen für SharePoint und OneDrive auf Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="f84d1-154">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="f84d1-155">Navigieren Sie im SharePoint Admin Center zur Seite Freigabe.</span><span class="sxs-lookup"><span data-stu-id="f84d1-155">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="f84d1-156">Wählen Sie unter **Datei-und Ordner Links** den standardmäßigen Freigabe Link aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f84d1-156">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="f84d1-157">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f84d1-157">If you made changes, click **Save**.</span></span>

<span data-ttu-id="f84d1-158">Klicken Sie zum Festlegen der Berechtigung für den Freigabe Link unter **Wählen Sie die Berechtigung aus, die standardmäßig für Freigabelinks ausgewählt ist.**</span><span class="sxs-lookup"><span data-stu-id="f84d1-158">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="f84d1-159">Wählen Sie **Ansicht** aus, wenn Sie nicht möchten, dass nicht authentifizierte Benutzer Änderungen an den Dateien und Ordnern vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f84d1-159">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="f84d1-160">Wählen Sie **Bearbeiten** aus, wenn Sie zulassen möchten, dass nicht authentifizierte Benutzer Änderungen an den Dateien und Ordnern vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f84d1-160">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="f84d1-161">Beachten Sie, dass die beiden obigen premission-Optionen nicht nur für Gäste/externe Benutzer, sondern auch für interne Benutzer angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f84d1-161">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="f84d1-162">Die von Ihnen gewählte Berechtigungsoption wird durch selbst Diskretion bestimmt.</span><span class="sxs-lookup"><span data-stu-id="f84d1-162">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="f84d1-163">So legen Sie Berechtigungen für Links fest, die die Freigabe für beliebige Personen zulassen</span><span class="sxs-lookup"><span data-stu-id="f84d1-163">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="f84d1-164">Unter den **folgenden Links können diese Berechtigungen erteilt werden:** Unterbereich,</span><span class="sxs-lookup"><span data-stu-id="f84d1-164">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="f84d1-165">In der Dropdownliste **Dateien**</span><span class="sxs-lookup"><span data-stu-id="f84d1-165">From the **Files** drop-down list,</span></span> 
        1. <span data-ttu-id="f84d1-166">Wählen Sie **anzeigen und bearbeiten** aus, wenn Sie zulassen möchten, dass nicht authentifizierte Benutzer Änderungen an den Dateien vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="f84d1-166">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        2. <span data-ttu-id="f84d1-167">Wählen Sie **Ansicht** aus, wenn Sie nicht möchten, dass nicht authentifizierte Benutzer Änderungen an den Dateien vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f84d1-167">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="f84d1-168">In der Dropdownliste **Ordner**</span><span class="sxs-lookup"><span data-stu-id="f84d1-168">From the **Folders** drop-down list,</span></span>
        1. <span data-ttu-id="f84d1-169">Wählen Sie **anzeigen, bearbeiten und hochladen** aus, wenn Sie zulassen möchten, dass nicht authentifizierte Benutzer Änderungen an den Ordnern vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="f84d1-169">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        2. <span data-ttu-id="f84d1-170">Wählen Sie **Ansicht** aus, wenn Sie nicht möchten, dass nicht authentifizierte Benutzer Änderungen an den Ordnern vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f84d1-170">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="f84d1-171">SharePoint-Freigabeeinstellungen auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="f84d1-171">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="f84d1-172">Wenn Sie Dateien und Ordner in einer SharePoint-Website freigeben, müssen Sie auch die Freigabeeinstellungen auf Websiteebene für diese Website überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f84d1-172">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="f84d1-174">So legen Sie Freigabeeinstellungen auf Websiteebene fest</span><span class="sxs-lookup"><span data-stu-id="f84d1-174">To set site-level sharing settings</span></span>

1. <span data-ttu-id="f84d1-175">Erweitern Sie im SharePoint Admin Center im linken Navigationsbereich den Knoten **Websites** , und klicken Sie dann auf **aktive Standorte**.</span><span class="sxs-lookup"><span data-stu-id="f84d1-175">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="f84d1-176">Wählen Sie die Website aus, für die Sie Dateien und Ordner für Gäste freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="f84d1-176">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="f84d1-177">Scrollen Sie nach rechts in der Zeile (in der die ausgewählte Website vorhanden ist), und klicken Sie auf eine beliebige Stelle in der Spalte **externe Freigabe** .</span><span class="sxs-lookup"><span data-stu-id="f84d1-177">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="f84d1-178">Klicken Sie auf der Seite, die sich öffnet, auf Registerkarte **Richtlinien** .</span><span class="sxs-lookup"><span data-stu-id="f84d1-178">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="f84d1-179">Klicken Sie im Bereich **externe Freigabe** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f84d1-179">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="f84d1-180">Stellen Sie sicher, dass die Freigabe auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f84d1-180">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="f84d1-181">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f84d1-181">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="f84d1-182">Benutzer einladen</span><span class="sxs-lookup"><span data-stu-id="f84d1-182">Invite users</span></span>

<span data-ttu-id="f84d1-183">Einstellungen für die Gast Freigabe sind jetzt konfiguriert; Damit können Benutzer nun Dateien und Ordner für Personen außerhalb Ihrer Organisation freigeben.</span><span class="sxs-lookup"><span data-stu-id="f84d1-183">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="f84d1-184">Weitere Informationen finden Sie unter [Freigeben von OneDrive-Dateien und-Ordnern](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) und Freigeben von [SharePoint-Dateien oder-Ordnern](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .</span><span class="sxs-lookup"><span data-stu-id="f84d1-184">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="f84d1-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f84d1-185">See also</span></span>

[<span data-ttu-id="f84d1-186">Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="f84d1-186">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="f84d1-187">Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste</span><span class="sxs-lookup"><span data-stu-id="f84d1-187">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="f84d1-188">SharePoint-und OneDrive-Integration mit Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="f84d1-188">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
