---
title: Zusammenarbeit mit Gästen in einem Team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- M365solutions
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Hier finden Sie Informationen zu den Microsoft 365-Konfigurationsschritten, die zum Einrichten eines Teams für die Zusammenarbeit mit Gästen in Teams erforderlich sind.
ms.openlocfilehash: dabcfa53e9ccf4b3ea136b5ab522619fe81ae738
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160027"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="ee2e3-103">Zusammenarbeit mit Gästen in einem Team</span><span class="sxs-lookup"><span data-stu-id="ee2e3-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="ee2e3-104">Wenn Sie mit Gästen in Dokumenten, Aufgaben und Unterhaltungen zusammenarbeiten müssen, empfehlen wir die Verwendung von Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="ee2e3-105">Microsoft Teams bietet alle in Office und SharePoint verfügbaren Features für die Zusammenarbeit mit beständigem Chat sowie eine anpassbare und erweiterbare Gruppe von Tools für die Zusammenarbeit in einer einheitlichen Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="ee2e3-106">In diesem Artikel werden die Microsoft 365-Konfigurationsschritte durchlaufen, die erforderlich sind, um ein Team für die Zusammenarbeit mit Gästen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="ee2e3-107">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="ee2e3-107">Video demonstration</span></span>

<span data-ttu-id="ee2e3-108">Dieses Video zeigt die in diesem Dokument beschriebenen Konfigurationsschritte.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="ee2e3-109">Azure Organizational Relationships-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="ee2e3-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="ee2e3-110">Die Freigabe in Microsoft 365 wird auf der höchsten Ebene durch die Einstellungen für organisatorische Beziehungen in Azure Active Directory gesteuert.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-110">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="ee2e3-111">Wenn die Gast Freigabe in Azure AD deaktiviert oder eingeschränkt ist, werden alle Freigabeeinstellungen, die Sie in Microsoft 365 konfigurieren, außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="ee2e3-112">Überprüfen Sie die Einstellungen für Organisationsbeziehungen, um sicherzustellen, dass die Freigabe für Gäste nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot der Seite mit den Einstellungen für die Azure Active Directory-Organisationsbeziehungen](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="ee2e3-114">So legen Sie Einstellungen für die Organisationsbeziehung fest</span><span class="sxs-lookup"><span data-stu-id="ee2e3-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="ee2e3-115">Melden Sie sich bei Microsoft Azure [https://portal.azure.com](https://portal.azure.com)an an.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="ee2e3-116">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="ee2e3-117">Klicken Sie im Bereich **Übersicht** auf **Organisationsbeziehungen**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="ee2e3-118">Klicken Sie im Bereich **Organisationsbeziehungen** auf **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="ee2e3-119">Stellen Sie sicher, dass **Administratoren und Benutzer in der Rolle "Gast einladender" eingeladen** werden und **Mitglieder einladen können** , beide auf " **Ja**" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="ee2e3-120">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="ee2e3-121">Beachten Sie die Einstellungen im Abschnitt Einschränkungen für die **Zusammenarbeit** .</span><span class="sxs-lookup"><span data-stu-id="ee2e3-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="ee2e3-122">Stellen Sie sicher, dass die Domänen der Gäste, mit denen Sie zusammenarbeiten möchten, nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="ee2e3-123">Einstellungen für den Gastzugriff in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee2e3-123">Teams guest access settings</span></span>

<span data-ttu-id="ee2e3-124">Teams verfügt über einen Master ein/aus-Schalter für Gastzugriff und eine Vielzahl von Einstellungen zur Verfügung, um zu steuern, was Gäste in einem Team tun können.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-124">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="ee2e3-125">Der Hauptschalter, der den **Gastzugriff in Microsoft Teams zulässt** , muss für den Gastzugriff für die Arbeit in Microsoft Teams **eingeschaltet** sein.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-125">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="ee2e3-126">Stellen Sie sicher, dass der Gastzugriff in Microsoft Teams aktiviert ist, und nehmen Sie entsprechend Ihren geschäftlichen Anforderungen eine Anpassung an die Gast Einstellungen vor.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-126">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="ee2e3-127">Beachten Sie, dass sich diese Einstellungen auf alle Teams auswirken.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-127">Keep in mind that these settings affect all teams.</span></span>

![Screenshot der Teams-Umschaltfläche für den Gastzugriff](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="ee2e3-129">So legen Sie die Gastzugriffseinstellungen für Teams fest</span><span class="sxs-lookup"><span data-stu-id="ee2e3-129">To set Teams guest access settings</span></span>

1. <span data-ttu-id="ee2e3-130">Melden Sie sich beim Microsoft 365 Admin Center an auf [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="ee2e3-130">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="ee2e3-131">Klicken Sie in der linken Navigationsleiste auf **Alle anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-131">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="ee2e3-132">Klicken Sie unter **Admin Centers** auf **Teams**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-132">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="ee2e3-133">Erweitern Sie im Teams Admin Center **Organisationsweite Einstellungen** in der linken Navigationsleiste und klicken Sie auf **Gastzugriff**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-133">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="ee2e3-134">Stellen Sie sicher, dass **Gastzugriff in Teams zulassen** auf **Ein** ist.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-134">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="ee2e3-135">Nehmen Sie alle gewünschten Änderungen an den zusätzlichen Gasteinstellungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-135">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ee2e3-136">Es könnte bis zu vierundzwanzig Stunden dauern, bis die Gasteinstellung für Teams aktiv wird, nachdem sie eingeschaltet wurde.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-136">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="ee2e3-137">Microsoft 365 Gruppen-Gast Einstellungen</span><span class="sxs-lookup"><span data-stu-id="ee2e3-137">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="ee2e3-138">Microsoft Teams verwendet Microsoft 365-Gruppen für die Teammitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-138">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="ee2e3-139">Die Gast Einstellungen für Microsoft 365-Gruppen müssen aktiviert sein, damit Gastzugriff in Teams funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-139">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Screenshot der Gasteinstellungen für Microsoft 365-Gruppen im Microsoft 365 Admin Center](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="ee2e3-141">So legen Sie die Gast Einstellungen für Microsoft 365-Gruppen fest</span><span class="sxs-lookup"><span data-stu-id="ee2e3-141">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="ee2e3-142">Erweitern Sie im Microsoft 365 Admin Center in der linken Navigationsleiste **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-142">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="ee2e3-143">Klicken Sie auf **Dienste &-Add-ins**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-143">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="ee2e3-144">Klicken Sie in der Liste auf **Microsoft 365-Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-144">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="ee2e3-145">Stellen Sie sicher, dass die Gruppen **Mitglieder außerhalb Ihrer Organisation Zugriff auf Gruppeninhalte** haben und Gruppen **Besitzer Personen außerhalb Ihrer Organisation hinzufügen zulassen** Kontrollkästchen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-145">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="ee2e3-146">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-146">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="ee2e3-147">SharePoint-Freigabeeinstellungen auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="ee2e3-147">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="ee2e3-148">Microsoft Teams-Inhalte wie Dateien, Ordner und Listen werden in SharePoint gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-148">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="ee2e3-149">Damit Gäste auf diese Elemente in Microsoft Teams zugreifen können, müssen die SharePoint-Freigabeeinstellungen auf Organisationsebene für die Freigabe für Gäste zulässig sein.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-149">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="ee2e3-150">Mit den Einstellungen auf Organisationsebene wird festgelegt, welche Einstellungen für einzelne Websites verfügbar sind, einschließlich der Websites, die Microsoft Teams zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-150">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="ee2e3-151">Websiteeinstellungen dürfen nicht so restriktiv wie die Einstellungen auf Organisationsebene sein.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-151">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="ee2e3-152">Wenn Sie die Datei-und Ordnerfreigabe für nicht authentifizierte Personen zulassen möchten, wählen Sie **jeden**aus.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-152">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="ee2e3-153">Wenn Sie sicherstellen möchten, dass sich alle Gäste authentifizieren müssen, wählen Sie **neue und vorhandene Gäste**aus.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-153">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="ee2e3-154">Wählen Sie die frei zügigste Einstellung aus, die von einer beliebigen Website in Ihrer Organisation benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-154">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="ee2e3-156">So legen Sie Freigabeeinstellungen für SharePoint-Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="ee2e3-156">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="ee2e3-157">Klicken Sie im Microsoft 365 Admin Center in der linken Navigationsleiste unter **Admin Centers**auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-157">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="ee2e3-158">Klicken Sie im SharePoint Admin Center links in der Navigation auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-158">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="ee2e3-159">Stellen Sie sicher, dass die externe Freigabe für SharePoint auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-159">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="ee2e3-160">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-160">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="ee2e3-161">Standard Link Einstellungen für SharePoint-Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="ee2e3-161">SharePoint organization level default link settings</span></span>

<span data-ttu-id="ee2e3-162">Die Standardeinstellungen für Datei-und Ordnerverknüpfung legen fest, welche Link Option dem Benutzer standardmäßig angezeigt wird, wenn er eine Datei oder einen Ordner freigegeben hat.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-162">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="ee2e3-163">Benutzer können den Verknüpfungstyp vor der Freigabe bei Bedarf in eine der anderen Optionen ändern.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-163">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="ee2e3-164">Beachten Sie, dass sich diese Einstellung auf alle Teams und SharePoint-Websites in Ihrer Organisation auswirkt.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-164">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="ee2e3-165">Wählen Sie den Linktyp aus, der standardmäßig ausgewählt ist, wenn Benutzer Dateien und Ordner freigeben:</span><span class="sxs-lookup"><span data-stu-id="ee2e3-165">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="ee2e3-166">**Jeder, der über den Link verfügt** – wählen Sie diese Option aus, wenn Sie eine Vielzahl von nicht authentifizierten Freigaben von Dateien und Ordnern erwarten.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-166">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="ee2e3-167">Wenn Sie *alle* Links zulassen möchten, jedoch über versehentliche nicht authentifizierte Freigaben besorgt sind, sollten Sie eine der anderen Optionen als Standard verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-167">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="ee2e3-168">Dieser Linktyp ist nur verfügbar, wenn Sie die Freigabe von **Benutzern** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-168">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="ee2e3-169">**Nur Personen in Ihrer Organisation** – wählen Sie diese Option aus, wenn Sie davon ausgehen, dass die meisten Datei-und Ordner Freigaben für Personen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-169">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="ee2e3-170">**Bestimmte Personen** – diese Option wird empfohlen, wenn Sie eine Vielzahl von Datei-und Ordner Freigaben für Gäste erwarten.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-170">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="ee2e3-171">Diese Art von Link funktioniert mit Gästen und erfordert die Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-171">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot der Freigabeeinstellungen auf Organisationsebene für Dateien und Ordner in SharePoint und OneDrive](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="ee2e3-173">So legen Sie die Standard Link Einstellungen für die SharePoint-Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="ee2e3-173">To set the SharePoint organization level default link settings</span></span>

1. <span data-ttu-id="ee2e3-174">Navigieren Sie im SharePoint Admin Center zur Seite Freigabe.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-174">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="ee2e3-175">Wählen Sie unter **Datei-und Ordner Links**den standardmäßigen Freigabe Link aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-175">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="ee2e3-176">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-176">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="ee2e3-177">Team erstellen</span><span class="sxs-lookup"><span data-stu-id="ee2e3-177">Create a team</span></span>

<span data-ttu-id="ee2e3-178">Der nächste Schritt besteht darin, das Team zu erstellen, das Sie für die Zusammenarbeit mit Gästen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-178">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="ee2e3-179">So erstellen Sie ein Team</span><span class="sxs-lookup"><span data-stu-id="ee2e3-179">To create a team</span></span>
1. <span data-ttu-id="ee2e3-180">Klicken Sie in Microsoft Teams auf der Registerkarte **Teams** unten im linken Bereich auf **beitreten oder ein Team erstellen** .</span><span class="sxs-lookup"><span data-stu-id="ee2e3-180">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="ee2e3-181">Klicken Sie auf **Team erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-181">Click **Create a team**.</span></span>
3. <span data-ttu-id="ee2e3-182">Klicken Sie auf **ein Team von Grund auf neu erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-182">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="ee2e3-183">Wählen Sie **private** oder **Public**aus.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-183">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="ee2e3-184">Geben Sie einen Namen und eine Beschreibung für das Team ein, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-184">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="ee2e3-185">Klicken Sie auf **überspringen**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-185">Click **Skip**.</span></span>

<span data-ttu-id="ee2e3-186">Wir laden Benutzer später ein.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-186">We'll invite users later.</span></span> <span data-ttu-id="ee2e3-187">Als nächstes ist es wichtig, die Freigabeeinstellungen auf Websiteebene für die SharePoint-Website zu überprüfen, die dem Team zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-187">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="ee2e3-188">Freigabeeinstellungen für SharePoint-Websiteebene</span><span class="sxs-lookup"><span data-stu-id="ee2e3-188">SharePoint site level sharing settings</span></span>

<span data-ttu-id="ee2e3-189">Überprüfen Sie die Freigabeeinstellungen auf Standortebene, um sicherzustellen, dass die gewünschten Zugriffstypen für dieses Team zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-189">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="ee2e3-190">Wenn Sie beispielsweise die Einstellungen auf Organisationsebene auf " **jeder**" festlegen, aber alle Gäste sich für dieses Team authentifizieren möchten, stellen Sie sicher, dass die Freigabeeinstellungen auf Standortebene auf " **neu" und "vorhandene Gäste**" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-190">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="ee2e3-192">So legen Sie Freigabeeinstellungen auf Websiteebene fest</span><span class="sxs-lookup"><span data-stu-id="ee2e3-192">To set site-level sharing settings</span></span>
1. <span data-ttu-id="ee2e3-193">Erweitern Sie im SharePoint Admin Center links in der Navigation **Sites** und klicken Sie auf **Aktive Sites**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-193">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="ee2e3-194">Wählen Sie die Site des soeben erstellten Teams aus.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-194">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="ee2e3-195">Klicken Sie im Menüband auf **Freigabe**. </span><span class="sxs-lookup"><span data-stu-id="ee2e3-195">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="ee2e3-196">Stellen Sie sicher, dass die Freigabe auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-196">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="ee2e3-197">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-197">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="ee2e3-198">Benutzer einladen</span><span class="sxs-lookup"><span data-stu-id="ee2e3-198">Invite users</span></span>

<span data-ttu-id="ee2e3-199">Die Einstellungen für die Gast Freigabe sind nun konfiguriert, sodass Sie mit dem Hinzufügen interner Benutzer und Gäste zu Ihrem Team beginnen können.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-199">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="ee2e3-200">So laden Sie interne Benutzer zu einem Team ein</span><span class="sxs-lookup"><span data-stu-id="ee2e3-200">To invite internal users to a team</span></span>
1. <span data-ttu-id="ee2e3-201">Klicken Sie im Team auf **Weitere Optionen** (**\*\***), und klicken Sie dann auf **Mitglied hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-201">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="ee2e3-202">Geben Sie den Namen der Person ein, die Sie einladen möchten.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-202">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="ee2e3-203">Klicken Sie auf **Hinzufügen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-203">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="ee2e3-204">So laden Sie Gäste zu einem Team ein</span><span class="sxs-lookup"><span data-stu-id="ee2e3-204">To invite guests to a team</span></span>
1. <span data-ttu-id="ee2e3-205">Klicken Sie im Team auf **Weitere Optionen** (**\*\***), und klicken Sie dann auf **Mitglied hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-205">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="ee2e3-206">Geben Sie die e-Mail-Adresse des Gasts ein, den Sie einladen möchten.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-206">Type the email address of the guest who you want to invite.</span></span>
3. <span data-ttu-id="ee2e3-207">Klicken Sie auf **Gäste Informationen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-207">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="ee2e3-208">Geben Sie den vollständigen Namen des Gasts ein, und klicken Sie auf das Häkchen.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-208">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="ee2e3-209">Klicken Sie auf **Hinzufügen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ee2e3-209">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee2e3-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee2e3-210">See Also</span></span>

[<span data-ttu-id="ee2e3-211">Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="ee2e3-211">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="ee2e3-212">Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste</span><span class="sxs-lookup"><span data-stu-id="ee2e3-212">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="ee2e3-213">Erstellen einer sicheren Gastfreigabeumgebung</span><span class="sxs-lookup"><span data-stu-id="ee2e3-213">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="ee2e3-214">Erstellen eines B2B-Extranets mit verwalteten Gästen</span><span class="sxs-lookup"><span data-stu-id="ee2e3-214">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)
