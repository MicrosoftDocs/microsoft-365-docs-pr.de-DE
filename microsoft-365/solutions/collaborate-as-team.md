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
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Erfahren Sie mehr über die Microsoft 365-Konfigurationsschritte, die zum Einrichten eines Teams für die Zusammenarbeit an Aufgaben, Unterhaltungen und Dokumentationen mit Gästen in Teams erforderlich sind.
ms.openlocfilehash: 34b7d5d47d7fb0c9196beda70184fa6510b6cc33
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780544"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="87d50-103">Zusammenarbeit mit Gästen in einem Team</span><span class="sxs-lookup"><span data-stu-id="87d50-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="87d50-104">Wenn Sie mit Gästen über Dokumente, Aufgaben und Unterhaltungen hinweg zusammenarbeiten müssen, empfehlen wir die Verwendung von Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="87d50-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="87d50-105">Teams bietet alle in Office und SharePoint verfügbaren Features für die Zusammenarbeit mit dauerhaftem Chat und einem anpassbaren und erweiterbaren Satz von Tools für die Zusammenarbeit in einer einheitlichen Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="87d50-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="87d50-106">In diesem Artikel werden die schritte zur Microsoft 365-Konfiguration erläutert, die zum Einrichten eines Teams für die Zusammenarbeit mit Gästen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="87d50-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="87d50-107">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="87d50-107">Video demonstration</span></span>

<span data-ttu-id="87d50-108">In diesem Video werden die in diesem Dokument beschriebenen Konfigurationsschritte gezeigt.</span><span class="sxs-lookup"><span data-stu-id="87d50-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="87d50-109">Einstellungen für die externe Zusammenarbeit in Azure</span><span class="sxs-lookup"><span data-stu-id="87d50-109">Azure External collaboration settings</span></span>

<span data-ttu-id="87d50-110">Die Freigabe in Microsoft 365 wird auf der höchsten Ebene durch die Einstellungen für die externe Zusammenarbeit in [Azure Active Directory bestimmt.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)</span><span class="sxs-lookup"><span data-stu-id="87d50-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="87d50-111">Wenn die Gastfreigabe in Azure AD deaktiviert oder eingeschränkt ist, setzt diese Einstellung alle Freigabeeinstellungen außer Kraft, die Sie in Microsoft 365 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="87d50-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="87d50-112">Überprüfen Sie die Einstellungen für die externe B2B-Zusammenarbeit, um sicherzustellen, dass die Freigabe für Gäste nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="87d50-112">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot der Seite mit den Einstellungen für die Azure Active Directory-Organisationsbeziehungen](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="87d50-114">So legen Sie Einstellungen für die externe Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="87d50-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="87d50-115">Melden Sie sich bei Azure Active Directory unter [https://aad.portal.azure.com](https://aad.portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="87d50-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="87d50-116">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="87d50-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="87d50-117">Klicken **Sie auf "Externe Identitäten".**</span><span class="sxs-lookup"><span data-stu-id="87d50-117">Click **External identities**.</span></span>
4. <span data-ttu-id="87d50-118">Klicken Sie **auf dem Bildschirm "Erste** Schritte" im linken Navigationsbereich auf Einstellungen für **die externe Zusammenarbeit.**</span><span class="sxs-lookup"><span data-stu-id="87d50-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="87d50-119">Stellen Sie **sicher, dass** Administratoren und Benutzer in der Rolle "Gast-Inviter" einladen können und dass Mitglieder, die einladen **können,** beide auf **"Ja" festgelegt sind.**</span><span class="sxs-lookup"><span data-stu-id="87d50-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="87d50-120">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="87d50-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="87d50-121">Beachten Sie die Einstellungen im Abschnitt **"Einschränkungen für die Zusammenarbeit".**</span><span class="sxs-lookup"><span data-stu-id="87d50-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="87d50-122">Stellen Sie sicher, dass die Domänen der Gäste, mit der Sie zusammenarbeiten möchten, nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="87d50-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="87d50-123">Wenn Sie mit Gästen aus mehreren Organisationen arbeiten, sollten Sie deren Zugriff auf Verzeichnisdaten einschränken.</span><span class="sxs-lookup"><span data-stu-id="87d50-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="87d50-124">Dadurch wird verhindert, dass sie sehen, wer sonst ein Gast im Verzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="87d50-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="87d50-125">Wählen Sie dazu unter Einschränkungen für  den Gastbenutzerzugriff die Option "Gastbenutzer haben eingeschränkten Zugriff auf Eigenschaften und Mitgliedschaft in Verzeichnisobjekteinstellungen" aus, oder der Gastbenutzerzugriff ist auf Eigenschaften und Mitgliedschaften ihrer eigenen **Verzeichnisobjekte beschränkt.**</span><span class="sxs-lookup"><span data-stu-id="87d50-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="87d50-126">Gastzugriffseinstellungen für Teams</span><span class="sxs-lookup"><span data-stu-id="87d50-126">Teams guest access settings</span></span>

<span data-ttu-id="87d50-127">Teams verfügt über einen Master-Ein-/Aus-Schalter für den Gastzugriff und eine Vielzahl von Einstellungen, die steuern, was Gäste in einem Team tun können.</span><span class="sxs-lookup"><span data-stu-id="87d50-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="87d50-128">Der Master-Switch" **"Gastzugriff in Teams** zulassen" muss **"On"** sein, damit der Gastzugriff in Teams funktioniert.</span><span class="sxs-lookup"><span data-stu-id="87d50-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="87d50-129">Stellen Sie sicher, dass der Gastzugriff in Teams aktiviert ist, und nehmen Sie jede Anpassung der Gasteinstellungen basierend auf Ihren Geschäftsanforderungen vor.</span><span class="sxs-lookup"><span data-stu-id="87d50-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="87d50-130">Beachten Sie, dass sich diese Einstellungen auf alle Teams auswirken.</span><span class="sxs-lookup"><span data-stu-id="87d50-130">Keep in mind that these settings affect all teams.</span></span>

![Screenshot der Teams-Umschaltfläche für den Gastzugriff](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="87d50-132">So legen Sie die Gastzugriffseinstellungen für Teams fest</span><span class="sxs-lookup"><span data-stu-id="87d50-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="87d50-133">Melden Sie sich beim Microsoft 365 Admin Center an auf [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="87d50-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="87d50-134">Klicken Sie im linken Navigationsbereich auf **"Alle anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="87d50-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="87d50-135">Klicken Sie unter **Admin Centers** auf **Teams**.</span><span class="sxs-lookup"><span data-stu-id="87d50-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="87d50-136">Erweitern Sie im Teams Admin Center im linken Navigationsbereich **organisationsweite** Einstellungen, und klicken Sie auf **Gastzugriff.**</span><span class="sxs-lookup"><span data-stu-id="87d50-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="87d50-137">Stellen Sie sicher, dass **Gastzugriff in Teams zulassen** auf **Ein** ist.</span><span class="sxs-lookup"><span data-stu-id="87d50-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="87d50-138">Nehmen Sie alle gewünschten Änderungen an den zusätzlichen Gasteinstellungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="87d50-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="87d50-139">Sobald der Gastzugriff für Teams aktiviert ist, können Sie optional den Gastzugriff auf einzelne Teams und die zugehörigen SharePoint-Websites mithilfe von Vertraulichkeitsbezeichnungen steuern.</span><span class="sxs-lookup"><span data-stu-id="87d50-139">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="87d50-140">Weitere Informationen finden Sie unter [Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="87d50-140">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="87d50-141">Es kann bis zu 24 Stunden dauern, bis die Gasteinstellungen von Teams aktiviert werden, nachdem Sie sie aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="87d50-141">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="87d50-142">Gasteinstellungen für Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="87d50-142">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="87d50-143">Teams verwendet Microsoft 365-Gruppen für die Teammitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="87d50-143">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="87d50-144">Die Gasteinstellungen für Microsoft 365-Gruppen müssen aktiviert sein, damit der Gastzugriff in Teams funktioniert.</span><span class="sxs-lookup"><span data-stu-id="87d50-144">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Screenshot der Gasteinstellungen für Microsoft 365-Gruppen im Microsoft 365 Admin Center](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="87d50-146">So legen Sie Die Gasteinstellungen für Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="87d50-146">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="87d50-147">Erweitern Sie im Microsoft 365 Admin Center im linken Navigationsbereich die **Einstellungen.**</span><span class="sxs-lookup"><span data-stu-id="87d50-147">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="87d50-148">Klicken Sie **auf Organisationseinstellungen.**</span><span class="sxs-lookup"><span data-stu-id="87d50-148">Click **Org settings**.</span></span>
3. <span data-ttu-id="87d50-149">Klicken Sie in der Liste auf **Microsoft 365-Gruppen.**</span><span class="sxs-lookup"><span data-stu-id="87d50-149">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="87d50-150">Stellen Sie sicher, dass die Kontrollkästchen "Gruppenbesitzern das Hinzufügen von Personen außerhalb Ihrer Organisation zu **Microsoft 365-Gruppen** als Gäste gestatten" und "Gastgruppenmitglieder zugriff auf Gruppeninhalte gestatten" aktiviert sind. </span><span class="sxs-lookup"><span data-stu-id="87d50-150">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="87d50-151">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **"Änderungen speichern".**</span><span class="sxs-lookup"><span data-stu-id="87d50-151">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="87d50-152">Freigabeeinstellungen auf SharePoint-Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="87d50-152">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="87d50-153">Teams-Inhalte wie Dateien, Ordner und Listen werden alle in SharePoint gespeichert.</span><span class="sxs-lookup"><span data-stu-id="87d50-153">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="87d50-154">Damit Gäste Zugriff auf diese Elemente in Teams haben, müssen die Freigabeeinstellungen auf Der Organisationsebene von SharePoint die Freigabe für Gäste zulassen.</span><span class="sxs-lookup"><span data-stu-id="87d50-154">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="87d50-155">Die Einstellungen auf Organisationsebene bestimmen, welche Einstellungen für einzelne Websites verfügbar sind, einschließlich websites, die Teams zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="87d50-155">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="87d50-156">Websiteeinstellungen dürfen nicht weniger als die Einstellungen auf Organisationsebene sein.</span><span class="sxs-lookup"><span data-stu-id="87d50-156">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="87d50-157">Wenn Sie die Datei- und Ordnerfreigabe für nicht authentifizierte Personen zulassen möchten, wählen Sie **"Jeder" aus.**</span><span class="sxs-lookup"><span data-stu-id="87d50-157">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="87d50-158">Wenn Sie sicherstellen möchten, dass alle Gäste authentifiziert werden müssen, wählen **Sie "Neu" und "Vorhandene Gäste" aus.**</span><span class="sxs-lookup"><span data-stu-id="87d50-158">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="87d50-159">Wählen Sie die einstellung mit den meisten Anforderungen aus, die von jeder Website in Ihrer Organisation benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="87d50-159">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="87d50-161">So legen Sie Freigabeeinstellungen auf Organisationsebene für SharePoint</span><span class="sxs-lookup"><span data-stu-id="87d50-161">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="87d50-162">Klicken Sie im Microsoft 365 Admin Center im linken Navigationsbereich unter **Admin Center** auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="87d50-162">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="87d50-163">Erweitern Sie im SharePoint Admin Center im  linken Navigationsbereich "Richtlinien", und klicken Sie dann auf **"Freigeben".**</span><span class="sxs-lookup"><span data-stu-id="87d50-163">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="87d50-164">Stellen Sie sicher, dass die externe Freigabe für SharePoint auf **"Jeder"** **oder "Neu" und "Vorhandene Gäste" festgelegt ist.**</span><span class="sxs-lookup"><span data-stu-id="87d50-164">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="87d50-165">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="87d50-165">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="87d50-166">Standardlinkeinstellungen auf Organisationsebene in SharePoint</span><span class="sxs-lookup"><span data-stu-id="87d50-166">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="87d50-167">Die Standardeinstellungen für Datei- und Ordnerverknüpfungen bestimmen die Linkoption, die Benutzern standardmäßig angezeigt wird, wenn sie eine Datei oder einen Ordner freigeben.</span><span class="sxs-lookup"><span data-stu-id="87d50-167">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="87d50-168">Benutzer können den Linktyp bei Bedarf vor der Freigabe in eine der anderen Optionen ändern.</span><span class="sxs-lookup"><span data-stu-id="87d50-168">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="87d50-169">Beachten Sie, dass sich diese Einstellung auf alle Teams und SharePoint-Websites in Ihrer Organisation auswirkt.</span><span class="sxs-lookup"><span data-stu-id="87d50-169">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="87d50-170">Wählen Sie einen der folgenden Linktypen aus, der standardmäßig ausgewählt wird, wenn Benutzer Dateien und Ordner freigeben:</span><span class="sxs-lookup"><span data-stu-id="87d50-170">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="87d50-171">**Jeder mit dem Link** – Wählen Sie diese Option aus, wenn Sie erwarten, dass eine große Menge nicht authentifizierter Freigaben von Dateien und Ordnern möglich ist.</span><span class="sxs-lookup"><span data-stu-id="87d50-171">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="87d50-172">Wenn Sie "Jeder"-Links  zulassen möchten, aber bedenken, dass die Freigabe versehentlich nicht authentifiziert wird, sollten Sie eine der anderen Optionen als Standard verwenden.</span><span class="sxs-lookup"><span data-stu-id="87d50-172">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="87d50-173">Dieser Linktyp ist nur verfügbar, wenn Sie die Freigabe für **"Jeder"** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="87d50-173">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="87d50-174">**Nur Personen in Ihrer Organisation** – Wählen Sie diese Option aus, wenn Sie erwarten, dass die meisten Datei- und Ordnerfreigaben für Personen innerhalb Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="87d50-174">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="87d50-175">**Bestimmte Personen** – Erwägen Sie diese Option, wenn Sie eine große Menge datei- und Ordnerfreigaben für Gäste erwarten.</span><span class="sxs-lookup"><span data-stu-id="87d50-175">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="87d50-176">Diese Art von Link funktioniert mit Gästen und erfordert, dass sie sich authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="87d50-176">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot der Freigabeeinstellungen auf Organisationsebene für Dateien und Ordner in SharePoint und OneDrive](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="87d50-178">So legen Sie die Standardlinkeinstellungen auf Organisationsebene für SharePoint</span><span class="sxs-lookup"><span data-stu-id="87d50-178">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="87d50-179">Navigieren Sie im SharePoint Admin Center zur Seite "Freigabe".</span><span class="sxs-lookup"><span data-stu-id="87d50-179">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="87d50-180">Wählen **Sie unter Datei- und Ordnerlinks** den Standardfreigabelink aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="87d50-180">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="87d50-181">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="87d50-181">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="87d50-182">Ein Team erstellen</span><span class="sxs-lookup"><span data-stu-id="87d50-182">Create a team</span></span>

<span data-ttu-id="87d50-183">Der nächste Schritt besteht im Erstellen des Teams, das Sie für die Zusammenarbeit mit Gästen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="87d50-183">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="87d50-184">So erstellen Sie ein Team</span><span class="sxs-lookup"><span data-stu-id="87d50-184">To create a team</span></span>
1. <span data-ttu-id="87d50-185">Klicken Sie in Teams auf  der Registerkarte **"Teams"** unten im linken Bereich auf "Teilnehmen", oder erstellen Sie ein Team.</span><span class="sxs-lookup"><span data-stu-id="87d50-185">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="87d50-186">Klicken **Sie auf "Team erstellen".**</span><span class="sxs-lookup"><span data-stu-id="87d50-186">Click **Create a team**.</span></span>
3. <span data-ttu-id="87d50-187">Klicken **Sie auf "Team von Grund auf neu erstellen".**</span><span class="sxs-lookup"><span data-stu-id="87d50-187">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="87d50-188">Wählen **Sie "Privat"** oder **"Öffentlich" aus.**</span><span class="sxs-lookup"><span data-stu-id="87d50-188">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="87d50-189">Geben Sie einen Namen und eine Beschreibung für das Team ein, und klicken Sie dann auf **"Erstellen".**</span><span class="sxs-lookup"><span data-stu-id="87d50-189">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="87d50-190">Klicken Sie **auf "Überspringen".**</span><span class="sxs-lookup"><span data-stu-id="87d50-190">Click **Skip**.</span></span>

<span data-ttu-id="87d50-191">Wir laden die Benutzer später ein.</span><span class="sxs-lookup"><span data-stu-id="87d50-191">We'll invite users later.</span></span> <span data-ttu-id="87d50-192">Als Nächstes ist es wichtig, die Freigabeeinstellungen auf Websiteebene für die dem Team zugeordnete SharePoint-Website zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="87d50-192">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="87d50-193">Freigabeeinstellungen auf Websiteebene in SharePoint</span><span class="sxs-lookup"><span data-stu-id="87d50-193">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="87d50-194">Überprüfen Sie die Freigabeeinstellungen auf Websiteebene, um sicherzustellen, dass sie die Art des Zugriffs zulassen, den Sie für dieses Team wünschen.</span><span class="sxs-lookup"><span data-stu-id="87d50-194">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="87d50-195">Wenn Sie beispielsweise die Einstellungen auf Organisationsebene auf **"Jeder"** festlegen, aber alle Gäste für dieses Team authentifizieren sollen, stellen Sie sicher, dass die Freigabeeinstellungen auf Websiteebene auf **"Neu"** und "Vorhandene Gäste" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="87d50-195">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="87d50-197">So legen Sie Freigabeeinstellungen auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="87d50-197">To set site-level sharing settings</span></span>
1. <span data-ttu-id="87d50-198">Erweitern Sie im SharePoint Admin Center im linken Navigationsbereich **"Websites",** und klicken Sie auf **"Aktive Websites".**</span><span class="sxs-lookup"><span data-stu-id="87d50-198">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="87d50-199">Wählen Sie die Site des soeben erstellten Teams aus.</span><span class="sxs-lookup"><span data-stu-id="87d50-199">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="87d50-200">Klicken Sie auf ... und wählen Sie **"Freigabe"** aus.</span><span class="sxs-lookup"><span data-stu-id="87d50-200">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="87d50-201">Stellen Sie sicher, dass die Freigabe auf **"Jeder"** oder **"Neu" und "Vorhandene Gäste" festgelegt ist.**</span><span class="sxs-lookup"><span data-stu-id="87d50-201">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="87d50-202">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="87d50-202">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="87d50-203">Benutzer einladen</span><span class="sxs-lookup"><span data-stu-id="87d50-203">Invite users</span></span>

<span data-ttu-id="87d50-204">Die Einstellungen für die Gastfreigabe sind jetzt konfiguriert, sodass Sie mit dem Hinzufügen interner Benutzer und Gäste zu Ihrem Team beginnen können.</span><span class="sxs-lookup"><span data-stu-id="87d50-204">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="87d50-205">So laden Sie interne Benutzer zu einem Team ein</span><span class="sxs-lookup"><span data-stu-id="87d50-205">To invite internal users to a team</span></span>
1. <span data-ttu-id="87d50-206">Klicken Sie im Team auf **"Weitere Optionen"** ( ), und klicken Sie dann auf **\*\*\*** **"Mitglied hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="87d50-206">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="87d50-207">Geben Sie den Namen der Person ein, die Sie einladen möchten.</span><span class="sxs-lookup"><span data-stu-id="87d50-207">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="87d50-208">Klicken Sie auf **Hinzufügen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="87d50-208">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="87d50-209">So laden Sie Gäste zu einem Team ein</span><span class="sxs-lookup"><span data-stu-id="87d50-209">To invite guests to a team</span></span>
1. <span data-ttu-id="87d50-210">Klicken Sie im Team auf **"Weitere Optionen"** ( ), und klicken Sie dann auf **\*\*\*** **"Mitglied hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="87d50-210">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="87d50-211">Geben Sie die E-Mail-Adresse des Gasts ein, den Sie einladen möchten.</span><span class="sxs-lookup"><span data-stu-id="87d50-211">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="87d50-212">Klicken **Sie auf Gastinformationen bearbeiten.**</span><span class="sxs-lookup"><span data-stu-id="87d50-212">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="87d50-213">Geben Sie den vollständigen Namen des Gasts ein, und klicken Sie auf das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="87d50-213">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="87d50-214">Klicken Sie auf **Hinzufügen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="87d50-214">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="87d50-215">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87d50-215">See also</span></span>

[<span data-ttu-id="87d50-216">Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="87d50-216">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="87d50-217">Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste</span><span class="sxs-lookup"><span data-stu-id="87d50-217">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="87d50-218">Erstellen einer sicheren Gastfreigabeumgebung</span><span class="sxs-lookup"><span data-stu-id="87d50-218">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="87d50-219">Erstellen eines B2B-Extranets mit verwalteten Gästen</span><span class="sxs-lookup"><span data-stu-id="87d50-219">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="87d50-220">SharePoint- und #A0 in Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="87d50-220">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="87d50-221">Freigabeoptionen sind bei der Freigabe aus SharePoint oder OneDrive ausgegraut</span><span class="sxs-lookup"><span data-stu-id="87d50-221">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
