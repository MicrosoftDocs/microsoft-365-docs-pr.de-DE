---
title: Zusammenarbeit mit Gästen in einem Team
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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Hier finden Sie Informationen zu den Microsoft 365-Konfigurationsschritten, die zum Einrichten eines Teams für die Zusammenarbeit mit Gästen in Teams erforderlich sind.
ms.openlocfilehash: 7a2259358d6976184d393980b2b7c0320c3bb171
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48409048"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="d2acb-103">Zusammenarbeit mit Gästen in einem Team</span><span class="sxs-lookup"><span data-stu-id="d2acb-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="d2acb-104">Wenn Sie mit Gästen in Dokumenten, Aufgaben und Unterhaltungen zusammenarbeiten müssen, empfehlen wir die Verwendung von Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d2acb-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="d2acb-105">Microsoft Teams bietet alle in Office und SharePoint verfügbaren Features für die Zusammenarbeit mit beständigem Chat sowie eine anpassbare und erweiterbare Gruppe von Tools für die Zusammenarbeit in einer einheitlichen Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="d2acb-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="d2acb-106">In diesem Artikel werden die Microsoft 365-Konfigurationsschritte durchlaufen, die erforderlich sind, um ein Team für die Zusammenarbeit mit Gästen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="d2acb-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="d2acb-107">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="d2acb-107">Video demonstration</span></span>

<span data-ttu-id="d2acb-108">Dieses Video zeigt die in diesem Dokument beschriebenen Konfigurationsschritte.</span><span class="sxs-lookup"><span data-stu-id="d2acb-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="d2acb-109">Azure Organizational Relationships-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="d2acb-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="d2acb-110">Die Freigabe in Microsoft 365 wird auf der höchsten Ebene durch die [Einstellungen für organisatorische Beziehungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)gesteuert.</span><span class="sxs-lookup"><span data-stu-id="d2acb-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="d2acb-111">Wenn die Gast Freigabe in Azure AD deaktiviert oder eingeschränkt ist, überschreibt diese Einstellung alle Freigabeeinstellungen, die Sie in Microsoft 365 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d2acb-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="d2acb-112">Überprüfen Sie die Einstellungen für Organisationsbeziehungen, um sicherzustellen, dass die Freigabe für Gäste nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="d2acb-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot der Seite mit den Einstellungen für die Azure Active Directory-Organisationsbeziehungen](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="d2acb-114">So legen Sie Einstellungen für die Organisationsbeziehung fest</span><span class="sxs-lookup"><span data-stu-id="d2acb-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="d2acb-115">Melden Sie sich bei Azure Active Directory unter an [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="d2acb-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="d2acb-116">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="d2acb-117">Klicken Sie auf **externe Identitäten**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-117">Click **External identities**.</span></span>
4. <span data-ttu-id="d2acb-118">Klicken Sie auf dem Bildschirm **Erste Schritte** im linken Navigationsbereich auf **Einstellungen für externe Zusammenarbeit**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="d2acb-119">Stellen Sie sicher, dass **Administratoren und Benutzer in der Rolle "Gast einladender" eingeladen** werden und **Mitglieder einladen können** , beide auf " **Ja**" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="d2acb-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="d2acb-120">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="d2acb-121">Beachten Sie die Einstellungen im Abschnitt Einschränkungen für die **Zusammenarbeit** .</span><span class="sxs-lookup"><span data-stu-id="d2acb-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="d2acb-122">Stellen Sie sicher, dass die Domänen der Gäste, mit denen Sie zusammenarbeiten möchten, nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="d2acb-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="d2acb-123">Wenn Sie mit Gästen aus mehreren Organisationen zusammenarbeiten, möchten Sie möglicherweise die Möglichkeit zum Zugriff auf Verzeichnisdaten einschränken.</span><span class="sxs-lookup"><span data-stu-id="d2acb-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="d2acb-124">Dadurch wird verhindert, dass Sie sehen, wer sonst ein Gast im Verzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="d2acb-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="d2acb-125">Wählen Sie dazu unter **Benutzerzugriffs Einschränkungen**für Gast die Option **Gastbenutzer haben begrenzten Zugriff auf Eigenschaften und Mitgliedschaft in Verzeichnisobjekt Einstellungen** oder **Gastbenutzer Zugriff ist auf Eigenschaften und Mitgliedschaften ihrer eigenen Verzeichnisobjekte beschränkt**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="d2acb-126">Einstellungen für den Gastzugriff in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d2acb-126">Teams guest access settings</span></span>

<span data-ttu-id="d2acb-127">Teams verfügt über einen Master ein/aus-Schalter für Gastzugriff und eine Vielzahl von Einstellungen zur Verfügung, um zu steuern, was Gäste in einem Team tun können.</span><span class="sxs-lookup"><span data-stu-id="d2acb-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="d2acb-128">Der Hauptschalter, der den **Gastzugriff in Microsoft Teams zulässt** , muss für den Gastzugriff für die Arbeit in Microsoft Teams **eingeschaltet** sein.</span><span class="sxs-lookup"><span data-stu-id="d2acb-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="d2acb-129">Stellen Sie sicher, dass der Gastzugriff in Microsoft Teams aktiviert ist, und nehmen Sie entsprechend Ihren geschäftlichen Anforderungen eine Anpassung an die Gast Einstellungen vor.</span><span class="sxs-lookup"><span data-stu-id="d2acb-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="d2acb-130">Beachten Sie, dass sich diese Einstellungen auf alle Teams auswirken.</span><span class="sxs-lookup"><span data-stu-id="d2acb-130">Keep in mind that these settings affect all teams.</span></span>

![Screenshot der Teams-Umschaltfläche für den Gastzugriff](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="d2acb-132">So legen Sie die Gastzugriffseinstellungen für Teams fest</span><span class="sxs-lookup"><span data-stu-id="d2acb-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="d2acb-133">Melden Sie sich beim Microsoft 365 Admin Center an auf [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d2acb-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="d2acb-134">Klicken Sie im linken Navigationsbereich auf **Alle anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="d2acb-135">Klicken Sie unter **Admin Centers** auf **Teams**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="d2acb-136">Erweitern Sie im Teamadministrator Center im linken Navigationsbereich die Option **organisationsweite Einstellungen** , und klicken Sie dann auf **Gastzugriff**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="d2acb-137">Stellen Sie sicher, dass **Gastzugriff in Teams zulassen** auf **Ein** ist.</span><span class="sxs-lookup"><span data-stu-id="d2acb-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="d2acb-138">Nehmen Sie alle gewünschten Änderungen an den zusätzlichen Gasteinstellungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d2acb-139">Es kann bis zu vierundzwanzig Stunden dauern, bis die Teams-Gast Einstellungen aktiviert werden, nachdem Sie sie aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="d2acb-139">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="d2acb-140">Microsoft 365 Gruppen-Gast Einstellungen</span><span class="sxs-lookup"><span data-stu-id="d2acb-140">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="d2acb-141">Microsoft Teams verwendet Microsoft 365-Gruppen für die Teammitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="d2acb-141">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="d2acb-142">Die Gast Einstellungen für Microsoft 365-Gruppen müssen aktiviert sein, damit Gastzugriff in Teams funktioniert.</span><span class="sxs-lookup"><span data-stu-id="d2acb-142">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Screenshot der Gasteinstellungen für Microsoft 365-Gruppen im Microsoft 365 Admin Center](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="d2acb-144">So legen Sie die Gast Einstellungen für Microsoft 365-Gruppen fest</span><span class="sxs-lookup"><span data-stu-id="d2acb-144">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="d2acb-145">Erweitern Sie im Microsoft 365 Admin Center im linken Navigationsbereich die Option **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-145">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="d2acb-146">Klicken Sie auf **org-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-146">Click **Org settings**.</span></span>
3. <span data-ttu-id="d2acb-147">Klicken Sie in der Liste auf **Microsoft 365-Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-147">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="d2acb-148">Stellen Sie sicher, dass die **Gruppenbesitzer zulassen Personen außerhalb Ihrer Organisation zu Microsoft 365-Gruppen hinzufügen** und die Kontrollkästchen Benutzer **Gruppenmitglieder können Zugriff auf Gruppeninhalte zulassen** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="d2acb-148">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="d2acb-149">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-149">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="d2acb-150">SharePoint-Freigabeeinstellungen auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="d2acb-150">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="d2acb-151">Microsoft Teams-Inhalte wie Dateien, Ordner und Listen werden in SharePoint gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d2acb-151">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="d2acb-152">Damit Gäste auf diese Elemente in Microsoft Teams zugreifen können, müssen die SharePoint-Freigabeeinstellungen auf Organisationsebene für die Freigabe für Gäste zulässig sein.</span><span class="sxs-lookup"><span data-stu-id="d2acb-152">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="d2acb-153">Mit den Einstellungen auf Organisationsebene wird festgelegt, welche Einstellungen für einzelne Websites verfügbar sind, einschließlich der Websites, die Microsoft Teams zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d2acb-153">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="d2acb-154">Websiteeinstellungen dürfen nicht so restriktiv wie die Einstellungen auf Organisationsebene sein.</span><span class="sxs-lookup"><span data-stu-id="d2acb-154">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="d2acb-155">Wenn Sie die Datei-und Ordnerfreigabe für nicht authentifizierte Personen zulassen möchten, wählen Sie **jeden**aus.</span><span class="sxs-lookup"><span data-stu-id="d2acb-155">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="d2acb-156">Wenn Sie sicherstellen möchten, dass sich alle Gäste authentifizieren müssen, wählen Sie **neue und vorhandene Gäste**aus.</span><span class="sxs-lookup"><span data-stu-id="d2acb-156">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="d2acb-157">Wählen Sie die frei zügigste Einstellung aus, die von einer beliebigen Website in Ihrer Organisation benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="d2acb-157">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="d2acb-159">So legen Sie Freigabeeinstellungen für SharePoint auf Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="d2acb-159">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="d2acb-160">Klicken Sie im Microsoft 365 Admin Center im linken Navigationsbereich unter **Admin Centers**auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-160">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="d2acb-161">Erweitern Sie im SharePoint Admin Center im linken Navigationsbereich **Richtlinien** , und klicken Sie dann auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-161">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="d2acb-162">Stellen Sie sicher, dass die externe Freigabe für SharePoint auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d2acb-162">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="d2acb-163">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-163">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="d2acb-164">Standard Link Einstellungen für SharePoint auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="d2acb-164">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="d2acb-165">Die Standardeinstellungen für Datei-und Ordnerverknüpfung bestimmen die Verknüpfungsoption, die Benutzern standardmäßig angezeigt wird, wenn Sie eine Datei oder einen Ordner freigeben.</span><span class="sxs-lookup"><span data-stu-id="d2acb-165">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="d2acb-166">Benutzer können den Verknüpfungstyp in eine der anderen Optionen vor der Freigabe ändern, falls gewünscht.</span><span class="sxs-lookup"><span data-stu-id="d2acb-166">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="d2acb-167">Beachten Sie, dass sich diese Einstellung auf alle Teams und SharePoint-Websites in Ihrer Organisation auswirkt.</span><span class="sxs-lookup"><span data-stu-id="d2acb-167">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="d2acb-168">Wählen Sie einen der folgenden Verknüpfungstypen aus, der standardmäßig ausgewählt wird, wenn Benutzer Dateien und Ordner freigeben:</span><span class="sxs-lookup"><span data-stu-id="d2acb-168">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="d2acb-169">**Jeder, der über den Link verfügt** – wählen Sie diese Option aus, wenn Sie eine Vielzahl von nicht authentifizierten Freigaben von Dateien und Ordnern erwarten.</span><span class="sxs-lookup"><span data-stu-id="d2acb-169">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="d2acb-170">Wenn Sie *alle* Links zulassen möchten, jedoch über versehentliche nicht authentifizierte Freigaben besorgt sind, sollten Sie eine der anderen Optionen als Standard verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2acb-170">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="d2acb-171">Dieser Linktyp ist nur verfügbar, wenn Sie die Freigabe von **Benutzern** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="d2acb-171">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="d2acb-172">**Nur Personen in Ihrer Organisation** – wählen Sie diese Option aus, wenn Sie davon ausgehen, dass die meisten Datei-und Ordner Freigaben für Personen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="d2acb-172">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="d2acb-173">**Bestimmte Personen** – diese Option wird empfohlen, wenn Sie eine Vielzahl von Datei-und Ordner Freigaben für Gäste erwarten.</span><span class="sxs-lookup"><span data-stu-id="d2acb-173">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="d2acb-174">Diese Art von Link funktioniert mit Gästen und erfordert die Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="d2acb-174">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot der Freigabeeinstellungen auf Organisationsebene für Dateien und Ordner in SharePoint und OneDrive](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="d2acb-176">So legen Sie die Standard Verknüpfungseinstellungen für SharePoint auf Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="d2acb-176">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="d2acb-177">Navigieren Sie im SharePoint Admin Center zur Seite Freigabe.</span><span class="sxs-lookup"><span data-stu-id="d2acb-177">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="d2acb-178">Wählen Sie unter **Datei-und Ordner Links**den standardmäßigen Freigabe Link aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d2acb-178">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="d2acb-179">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-179">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="d2acb-180">Team erstellen</span><span class="sxs-lookup"><span data-stu-id="d2acb-180">Create a team</span></span>

<span data-ttu-id="d2acb-181">Der nächste Schritt besteht darin, das Team zu erstellen, das Sie für die Zusammenarbeit mit Gästen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d2acb-181">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="d2acb-182">So erstellen Sie ein Team</span><span class="sxs-lookup"><span data-stu-id="d2acb-182">To create a team</span></span>
1. <span data-ttu-id="d2acb-183">Klicken Sie in Microsoft Teams auf der Registerkarte **Teams** unten im linken Bereich auf **beitreten oder ein Team erstellen** .</span><span class="sxs-lookup"><span data-stu-id="d2acb-183">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="d2acb-184">Klicken Sie auf **Team erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-184">Click **Create a team**.</span></span>
3. <span data-ttu-id="d2acb-185">Klicken Sie auf **ein Team von Grund auf neu erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-185">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="d2acb-186">Wählen Sie **private** oder **Public**aus.</span><span class="sxs-lookup"><span data-stu-id="d2acb-186">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="d2acb-187">Geben Sie einen Namen und eine Beschreibung für das Team ein, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-187">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="d2acb-188">Klicken Sie auf **überspringen**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-188">Click **Skip**.</span></span>

<span data-ttu-id="d2acb-189">Wir laden Benutzer später ein.</span><span class="sxs-lookup"><span data-stu-id="d2acb-189">We'll invite users later.</span></span> <span data-ttu-id="d2acb-190">Als nächstes ist es wichtig, die Freigabeeinstellungen auf Websiteebene für die SharePoint-Website zu überprüfen, die dem Team zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d2acb-190">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="d2acb-191">SharePoint-Freigabeeinstellungen auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="d2acb-191">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="d2acb-192">Überprüfen Sie die Freigabeeinstellungen auf Standortebene, um sicherzustellen, dass die gewünschten Zugriffstypen für dieses Team zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="d2acb-192">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="d2acb-193">Wenn Sie beispielsweise die Einstellungen auf Organisationsebene auf " **jeder**" festlegen, aber alle Gäste sich für dieses Team authentifizieren möchten, stellen Sie sicher, dass die Freigabeeinstellungen auf Standortebene auf " **neu" und "vorhandene Gäste**" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="d2acb-193">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="d2acb-195">So legen Sie Freigabeeinstellungen auf Websiteebene fest</span><span class="sxs-lookup"><span data-stu-id="d2acb-195">To set site-level sharing settings</span></span>
1. <span data-ttu-id="d2acb-196">Erweitern Sie im SharePoint Admin Center im linken Navigationsbereich den Knoten **Websites** , und klicken Sie dann auf **aktive Standorte**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-196">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="d2acb-197">Wählen Sie die Site des soeben erstellten Teams aus.</span><span class="sxs-lookup"><span data-stu-id="d2acb-197">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="d2acb-198">Klicken Sie auf... und wählen Sie **Freigabe**aus.</span><span class="sxs-lookup"><span data-stu-id="d2acb-198">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="d2acb-199">Stellen Sie sicher, dass die Freigabe auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d2acb-199">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="d2acb-200">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-200">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="d2acb-201">Benutzer einladen</span><span class="sxs-lookup"><span data-stu-id="d2acb-201">Invite users</span></span>

<span data-ttu-id="d2acb-202">Die Einstellungen für die Gast Freigabe sind nun konfiguriert, sodass Sie mit dem Hinzufügen interner Benutzer und Gäste zu Ihrem Team beginnen können.</span><span class="sxs-lookup"><span data-stu-id="d2acb-202">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="d2acb-203">So laden Sie interne Benutzer zu einem Team ein</span><span class="sxs-lookup"><span data-stu-id="d2acb-203">To invite internal users to a team</span></span>
1. <span data-ttu-id="d2acb-204">Klicken Sie im Team auf **Weitere Optionen** ( **\*\*\*** ), und klicken Sie dann auf **Mitglied hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-204">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="d2acb-205">Geben Sie den Namen der Person ein, die Sie einladen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2acb-205">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="d2acb-206">Klicken Sie auf **Hinzufügen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-206">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="d2acb-207">So laden Sie Gäste zu einem Team ein</span><span class="sxs-lookup"><span data-stu-id="d2acb-207">To invite guests to a team</span></span>
1. <span data-ttu-id="d2acb-208">Klicken Sie im Team auf **Weitere Optionen** ( **\*\*\*** ), und klicken Sie dann auf **Mitglied hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-208">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="d2acb-209">Geben Sie die e-Mail-Adresse des Gasts ein, den Sie einladen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2acb-209">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="d2acb-210">Klicken Sie auf **Gäste Informationen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-210">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="d2acb-211">Geben Sie den vollständigen Namen des Gasts ein, und klicken Sie auf das Häkchen.</span><span class="sxs-lookup"><span data-stu-id="d2acb-211">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="d2acb-212">Klicken Sie auf **Hinzufügen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d2acb-212">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2acb-213">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2acb-213">See also</span></span>

[<span data-ttu-id="d2acb-214">Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="d2acb-214">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="d2acb-215">Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste</span><span class="sxs-lookup"><span data-stu-id="d2acb-215">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="d2acb-216">Erstellen einer sicheren Gastfreigabeumgebung</span><span class="sxs-lookup"><span data-stu-id="d2acb-216">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="d2acb-217">Erstellen eines B2B-Extranets mit verwalteten Gästen</span><span class="sxs-lookup"><span data-stu-id="d2acb-217">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="d2acb-218">SharePoint-und OneDrive-Integration mit Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="d2acb-218">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
