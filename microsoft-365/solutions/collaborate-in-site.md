---
title: Zusammenarbeit mit Gästen in einer Website
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
description: Hier finden Sie Informationen zu den Microsoft 365-Konfigurationsschritten, die zum Einrichten einer SharePoint-Website für die Zusammenarbeit mit Gästen erforderlich sind.
ms.openlocfilehash: 6862fe715fe2f19b968b773bc6df6c70c207a44f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663524"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="7742e-103">Zusammenarbeit mit Gästen in einer Website</span><span class="sxs-lookup"><span data-stu-id="7742e-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="7742e-104">Wenn Sie mit Gästen in Dokumenten, Daten und Listen zusammenarbeiten müssen, können Sie eine SharePoint-Website verwenden.</span><span class="sxs-lookup"><span data-stu-id="7742e-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="7742e-105">Moderne SharePoint-Websites sind mit Microsoft 365-Gruppen verbunden und können die Website Mitgliedschaft verwalten und zusätzliche Tools für die Zusammenarbeit bereitstellen, beispielsweise ein freigegebenes Postfach und einen Kalender.</span><span class="sxs-lookup"><span data-stu-id="7742e-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="7742e-106">In diesem Artikel werden die Microsoft 365-Konfigurationsschritte durchlaufen, die erforderlich sind, um eine SharePoint-Website für die Zusammenarbeit mit Gästen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="7742e-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="7742e-107">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="7742e-107">Video demonstration</span></span>

<span data-ttu-id="7742e-108">Dieses Video zeigt die in diesem Dokument beschriebenen Konfigurationsschritte.</span><span class="sxs-lookup"><span data-stu-id="7742e-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="7742e-109">Einstellungen für Azure-externe Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="7742e-109">Azure external collaboration settings</span></span>

<span data-ttu-id="7742e-110">Die Freigabe in Microsoft 365 wird auf der höchsten Ebene durch die [Einstellungen für die B2B-externe Zusammenarbeit in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)gesteuert.</span><span class="sxs-lookup"><span data-stu-id="7742e-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="7742e-111">Wenn die Gast Freigabe in Azure AD deaktiviert oder eingeschränkt ist, überschreibt diese Einstellung alle Freigabeeinstellungen, die Sie in Microsoft 365 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7742e-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="7742e-112">Überprüfen Sie die Einstellungen für die externe Zusammenarbeit in B2B, um sicherzustellen, dass die Freigabe für Gäste nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="7742e-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot von Azure Active Directory Seite "Einstellungen für externe Zusammenarbeit"](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="7742e-114">So legen Sie Einstellungen für die externe Zusammenarbeit fest</span><span class="sxs-lookup"><span data-stu-id="7742e-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="7742e-115">Melden Sie sich bei Azure Active Directory unter an [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="7742e-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="7742e-116">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7742e-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="7742e-117">Klicken Sie auf **externe Identitäten**.</span><span class="sxs-lookup"><span data-stu-id="7742e-117">Click **External identities**.</span></span>
4. <span data-ttu-id="7742e-118">Klicken Sie auf dem Bildschirm **Erste Schritte** im linken Navigationsbereich auf **Einstellungen für externe Zusammenarbeit**.</span><span class="sxs-lookup"><span data-stu-id="7742e-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="7742e-119">Stellen Sie sicher, dass **Administratoren und Benutzer in der Rolle "Gast einladender" eingeladen** werden und **Mitglieder einladen können** , beide auf " **Ja**" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="7742e-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="7742e-120">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7742e-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="7742e-121">Beachten Sie die Einstellungen im Abschnitt Einschränkungen für die **Zusammenarbeit** .</span><span class="sxs-lookup"><span data-stu-id="7742e-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="7742e-122">Stellen Sie sicher, dass die Domänen der Gäste, mit denen Sie zusammenarbeiten möchten, nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="7742e-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="7742e-123">Wenn Sie mit Gästen aus mehreren Organisationen zusammenarbeiten, möchten Sie möglicherweise die Möglichkeit zum Zugriff auf Verzeichnisdaten einschränken.</span><span class="sxs-lookup"><span data-stu-id="7742e-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="7742e-124">Dadurch wird verhindert, dass Sie sehen, wer sonst ein Gast im Verzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="7742e-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="7742e-125">Wählen Sie dazu unter **Benutzerzugriffs Einschränkungen** für Gast die Option **Gastbenutzer haben begrenzten Zugriff auf Eigenschaften und Mitgliedschaft in Verzeichnisobjekt Einstellungen** oder **Gastbenutzer Zugriff ist auf Eigenschaften und Mitgliedschaften ihrer eigenen Verzeichnisobjekte beschränkt**.</span><span class="sxs-lookup"><span data-stu-id="7742e-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="7742e-126">Microsoft 365 Gruppen-Gast Einstellungen</span><span class="sxs-lookup"><span data-stu-id="7742e-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="7742e-127">Moderne SharePoint-Websites verwenden Microsoft 365-Gruppen, um den Website Zugriff zu steuern.</span><span class="sxs-lookup"><span data-stu-id="7742e-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="7742e-128">Die Gast Einstellungen für Microsoft 365-Gruppen müssen aktiviert sein, damit der Gastzugriff auf SharePoint-Websites funktioniert.</span><span class="sxs-lookup"><span data-stu-id="7742e-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Screenshot der Gasteinstellungen für Microsoft 365-Gruppen im Microsoft 365 Admin Center](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="7742e-130">So legen Sie die Gast Einstellungen für Microsoft 365-Gruppen fest</span><span class="sxs-lookup"><span data-stu-id="7742e-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="7742e-131">Erweitern Sie im Microsoft 365 Admin Center im linken Navigationsbereich die Option **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="7742e-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="7742e-132">Klicken Sie auf **org-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="7742e-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="7742e-133">Klicken Sie in der Liste auf **Microsoft 365-Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="7742e-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="7742e-134">Stellen Sie sicher, dass die **Gruppenbesitzer zulassen Personen außerhalb Ihrer Organisation zu Microsoft 365-Gruppen hinzufügen** und die Kontrollkästchen Benutzer **Gruppenmitglieder können Zugriff auf Gruppeninhalte zulassen** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="7742e-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="7742e-135">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="7742e-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="7742e-136">SharePoint-Freigabeeinstellungen auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="7742e-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="7742e-137">Damit Gästezugriff auf SharePoint-Websites haben, müssen die SharePoint-Freigabeeinstellungen auf Organisationsebene für die Freigabe für Gäste zulässig sein.</span><span class="sxs-lookup"><span data-stu-id="7742e-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="7742e-138">Die Einstellungen auf Organisationsebene bestimmen die Einstellungen, die für einzelne Websites verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7742e-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="7742e-139">Websiteeinstellungen dürfen nicht so restriktiv wie die Einstellungen auf Organisationsebene sein.</span><span class="sxs-lookup"><span data-stu-id="7742e-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="7742e-140">Wenn Sie die Freigabe nicht authentifizierter Dateien und Ordner zulassen möchten, wählen Sie **jeden** aus.</span><span class="sxs-lookup"><span data-stu-id="7742e-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="7742e-141">Wenn Sie sicherstellen möchten, dass sich alle Personen außerhalb Ihrer Organisation authentifizieren müssen, wählen Sie **neue und vorhandene Gäste** aus.</span><span class="sxs-lookup"><span data-stu-id="7742e-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="7742e-142">Wählen Sie die frei zügigste Einstellung aus, die von einer beliebigen Website in Ihrer Organisation benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="7742e-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="7742e-144">So legen Sie Freigabeeinstellungen für SharePoint auf Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="7742e-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="7742e-145">Klicken Sie im Microsoft 365 Admin Center im linken Navigationsbereich unter **Admin Centers** auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7742e-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="7742e-146">Klicken Sie im SharePoint Admin Center im linken Navigationsbereich unter **Richtlinien** auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="7742e-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="7742e-147">Stellen Sie sicher, dass die externe Freigabe für SharePoint auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7742e-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="7742e-148">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7742e-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="7742e-149">Erstellen einer Website</span><span class="sxs-lookup"><span data-stu-id="7742e-149">Create a site</span></span>

<span data-ttu-id="7742e-150">Im nächsten Schritt erstellen Sie die Website, die Sie für die Zusammenarbeit mit Gästen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7742e-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="7742e-151">So erstellen Sie eine Website</span><span class="sxs-lookup"><span data-stu-id="7742e-151">To create a site</span></span>
1. <span data-ttu-id="7742e-152">Klicken Sie im SharePoint Admin Center unter **Websites** auf **Aktive Websites**.</span><span class="sxs-lookup"><span data-stu-id="7742e-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="7742e-153">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7742e-153">Click **Create**.</span></span>
3. <span data-ttu-id="7742e-154">Klicken Sie auf **Team Website**.</span><span class="sxs-lookup"><span data-stu-id="7742e-154">Click **Team site**.</span></span>
4. <span data-ttu-id="7742e-155">Geben Sie einen Websitenamen ein, und geben Sie einen Namen für den Gruppenbesitzer (Websitebesitzer) ein.</span><span class="sxs-lookup"><span data-stu-id="7742e-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="7742e-156">Wählen Sie unter **Erweiterte Einstellungen** aus, ob diese Website öffentlich oder privat sein soll.</span><span class="sxs-lookup"><span data-stu-id="7742e-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="7742e-157">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7742e-157">Click **Next**.</span></span>
7. <span data-ttu-id="7742e-158">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="7742e-158">Click **Finish**.</span></span>

<span data-ttu-id="7742e-159">Wir laden Benutzer später ein.</span><span class="sxs-lookup"><span data-stu-id="7742e-159">We'll invite users later.</span></span> <span data-ttu-id="7742e-160">Als nächstes ist es wichtig, die Freigabeeinstellungen auf Standortebene für diese Website zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7742e-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="7742e-161">SharePoint-Freigabeeinstellungen auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="7742e-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="7742e-162">Überprüfen Sie die Freigabeeinstellungen auf Standortebene, um sicherzustellen, dass die gewünschten Zugriffstypen für diese Website zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="7742e-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="7742e-163">Wenn Sie beispielsweise die Einstellungen auf Organisationsebene auf " **jeder**" festlegen, aber alle Gäste für diese Website authentifizieren möchten, stellen Sie sicher, dass die Freigabeeinstellungen auf Standortebene auf " **neu" und "vorhandene Gäste**" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="7742e-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="7742e-164">Beachten Sie, dass die Website nicht für nicht authentifizierte Personen freigegeben werden kann (**jede** Einstellung), sondern einzelne Dateien und Ordner können.</span><span class="sxs-lookup"><span data-stu-id="7742e-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="7742e-165">Sie können auch [Sensitivitäts Bezeichnungen verwenden, um externe Freigabeeinstellungen für SharePoint-Websites zu steuern](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="7742e-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="7742e-167">So legen Sie Freigabeeinstellungen auf Websiteebene fest</span><span class="sxs-lookup"><span data-stu-id="7742e-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="7742e-168">Erweitern Sie im SharePoint Admin Center links in der Navigation **Sites** und klicken Sie auf **Aktive Sites**.</span><span class="sxs-lookup"><span data-stu-id="7742e-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="7742e-169">Wählen Sie die Website aus, die Sie freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="7742e-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="7742e-170">Klicken Sie auf..., und klicken Sie auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="7742e-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="7742e-171">Stellen Sie sicher, dass die Freigabe auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7742e-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="7742e-172">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7742e-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="7742e-173">Benutzer einladen</span><span class="sxs-lookup"><span data-stu-id="7742e-173">Invite users</span></span>

<span data-ttu-id="7742e-174">Die Einstellungen für die Gast Freigabe sind nun konfiguriert, sodass Sie mit dem Hinzufügen interner Benutzer und Gäste zu Ihrer Website beginnen können.</span><span class="sxs-lookup"><span data-stu-id="7742e-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="7742e-175">Der Website Zugriff wird über die zugehörige Microsoft 365-Gruppe gesteuert, sodass Benutzer dort hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7742e-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="7742e-176">So laden Sie interne Benutzer zu einer Gruppe ein</span><span class="sxs-lookup"><span data-stu-id="7742e-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="7742e-177">Navigieren Sie zu der Website, auf der Sie Benutzer hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="7742e-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="7742e-178">Klicken Sie in der oberen rechten Ecke auf **Mitglieder** -Link, der die Mitgliederanzahl kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="7742e-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="7742e-179">Klicken Sie auf **Mitglieder hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7742e-179">Click **Add members**.</span></span>
4. <span data-ttu-id="7742e-180">Geben Sie die Namen oder e-Mail-Adressen der Benutzer ein, die Sie zur Website einladen möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7742e-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="7742e-181">Gäste können nicht von der Website hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7742e-181">Guests can't be added from the site.</span></span> <span data-ttu-id="7742e-182">Sie müssen Sie mit Outlook im Internet hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7742e-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="7742e-183">Klicken Sie daher als Voraussetzung für das Hinzufügen und einladen von Gästen zu einer Gruppe auf die URL der Website in der Spalte **URL**  , um zur Website spezifischen Seite zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="7742e-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="7742e-184">Klicken Sie auf dieser Seite auf das **App-Startprogramm** Symbol, und wählen Sie **Outlook** aus.</span><span class="sxs-lookup"><span data-stu-id="7742e-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="7742e-185">Auf diesem Bildschirm können Sie Gäste in eine Gruppe einladen, die nachfolgend beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="7742e-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="7742e-186">So laden Sie Gäste zu einer Gruppe ein</span><span class="sxs-lookup"><span data-stu-id="7742e-186">To invite guests to a group</span></span>
1. <span data-ttu-id="7742e-187">Klicken Sie unter **Gruppen** auf die Gruppe, für die Sie Gäste einladen möchten.</span><span class="sxs-lookup"><span data-stu-id="7742e-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="7742e-188">Öffnen Sie die Gruppe Visitenkarte, klicken Sie auf **Mitglieder** Link in der oberen rechten Ecke (der Link, der die Mitgliederanzahl kennzeichnet).</span><span class="sxs-lookup"><span data-stu-id="7742e-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="7742e-189">Klicken Sie auf **Mitglieder hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7742e-189">click **Add members**.</span></span>
4. <span data-ttu-id="7742e-190">Geben Sie die e-Mail-Adressen der Gäste ein, die Sie einladen möchten, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7742e-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="7742e-191">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="7742e-191">Click **Close**.</span></span>
<span data-ttu-id="7742e-192">Beachten Sie, dass Sie nur auf **Schließen** klicken müssen, wenn Sie nicht der Besitzer der Gruppe sind und daher nicht berechtigt sind, den Gast der Gruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7742e-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="7742e-193">In diesen Fällen wird die Anforderung zum Hinzufügen des Gasts in der Gruppe zur Genehmigung an den Gruppenbesitzer übergeben.</span><span class="sxs-lookup"><span data-stu-id="7742e-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="7742e-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7742e-194">See also</span></span>

[<span data-ttu-id="7742e-195">Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="7742e-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="7742e-196">Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste</span><span class="sxs-lookup"><span data-stu-id="7742e-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="7742e-197">Erstellen einer sicheren Gastfreigabeumgebung</span><span class="sxs-lookup"><span data-stu-id="7742e-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="7742e-198">Erstellen eines B2B-Extranets mit verwalteten Gästen</span><span class="sxs-lookup"><span data-stu-id="7742e-198">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="7742e-199">SharePoint-und OneDrive-Integration mit Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="7742e-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
