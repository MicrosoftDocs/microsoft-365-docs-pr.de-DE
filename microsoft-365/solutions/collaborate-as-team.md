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
localization_priority: Priority
f1.keywords: NOCSH
description: Erfahren Sie mehr über die Konfigurationsschritte in Microsoft 365, die notwendig sind, um ein Team für die Zusammenarbeit mit Gästen in Teams bei Aufgaben, Unterhaltungen und Dokumentationen einzurichten.
ms.openlocfilehash: 986f9c1f343c8ccc3d76557291938d170923c89b
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712318"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="bc133-103">Zusammenarbeit mit Gästen in einem Team</span><span class="sxs-lookup"><span data-stu-id="bc133-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="bc133-104">Wenn Sie über Dokumente, Aufgaben und Unterhaltungen hinweg mit Gästen zusammenarbeiten möchten, empfehlen wir Ihnen Microsoft Teams zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bc133-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="bc133-105">Teams bietet aale in SharePoint und Office verfügbaren Features für die Zusammenarbeit mit beständigem Chat und einer anpassbaren und erweiterbaren Auswahl an Tools für die Zusammenarbeit in einer vereinheitlichten Benutzererfahrung.</span><span class="sxs-lookup"><span data-stu-id="bc133-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="bc133-106">In diesem Artikel werden die einzelnen Konfigurationsschritte von Microsoft 365 behandelt, die erforderlich sind, um ein Team für die Zusammenarbeit mit Gästen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="bc133-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="bc133-107">Sobald Sie den Gastzugriff konfiguriert haben, können Sie Gäste zu Teams einladen, indem Sie den Schritten in [Gästen in ein Team in Teams einladen](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f) folgen.</span><span class="sxs-lookup"><span data-stu-id="bc133-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="bc133-108">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="bc133-108">Video demonstration</span></span>

<span data-ttu-id="bc133-109">Dieses Video zeigt die in diesem Dokument beschriebenen Konfigurationsschritte.</span><span class="sxs-lookup"><span data-stu-id="bc133-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="bc133-110">Einstellungen für die Azure Externe Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="bc133-110">Azure External collaboration settings</span></span>

<span data-ttu-id="bc133-111">Die Freigabe in Microsoft 365 wird auf der höchsten Ebene von den [Einstellungen für B2B externe Zusammenarbeit in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations) geregelt.</span><span class="sxs-lookup"><span data-stu-id="bc133-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="bc133-112">Wenn die Gastfreigabe in Azure AD deaktiviert oder eingeschränkt ist, setzt diese Einstellung alle Freigabeeinstellungen, die Sie in Microsoft 365 konfiguriert haben, außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="bc133-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="bc133-113">Überprüfen Sie die Einstellungen für B2B externe Zusammenarbeit um sicherzustellen, dass die Freigabe für Gäste nicht blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="bc133-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot der Seite mit den Einstellungen für die Azure Active Directory-Organisationsbeziehungen](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="bc133-115">Festlegen der Einstellungen für die Azure Externe Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="bc133-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="bc133-116">Bei Azure Active Directory an [https://aad.portal.azure.com](https://aad.portal.azure.com) anmelden.</span><span class="sxs-lookup"><span data-stu-id="bc133-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="bc133-117">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="bc133-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="bc133-118">Klicken Sie auf **Externe Identitäten**.</span><span class="sxs-lookup"><span data-stu-id="bc133-118">Click **External identities**.</span></span>
4. <span data-ttu-id="bc133-119">Klicken Sie auf dem Bildschirm **Erste Schritte** im linken Navigationsbereich auf **Einstellungen für die externe Zusammenarbeit**.</span><span class="sxs-lookup"><span data-stu-id="bc133-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="bc133-120">Stellen Sie sicher, dass sowie **Administratoren und Benutzer mit der Rolle "Einladender" können einladen** als auch **Mitglieder können einladen** beide auf **Ja** festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="bc133-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="bc133-121">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bc133-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="bc133-122">Beachten Sie die Einstellungen im Bereich **Einschränkungen für die Zusammenarbeit**.</span><span class="sxs-lookup"><span data-stu-id="bc133-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="bc133-123">Stellen Sie sicher, dass die Domänen der Gäste, mit denen Sie zusammenarbeiten möchten, nicht blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="bc133-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="bc133-124">Wenn Sie mit Gästen aus mehreren Organisationen arbeiten, könnten Sie möglicherweise Interesse daran haben, ihren Zugriff auf Verzeichnisdaten einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="bc133-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="bc133-125">Dies wird es ihnen verhindern zu sehen, wer sonst noch Gast im Verzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="bc133-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="bc133-126">Wählen Sie dazu unter **Einschränkungen des Gastzugriffs** die Einstellung **Gastbenutzer haben eingeschränkten Zugriff auf Eigenschaften und die Mitgliedschaft bei den Einstellungen der Verzeichnisobjekte** oder **Zugriff der Gastbenutzer ist auf Eigenschaften und die Mitgliedschaft bei ihren eigenen Verzeichnisobjekten eingeschränkt**.</span><span class="sxs-lookup"><span data-stu-id="bc133-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="bc133-127">Gastzugriffseinstellungen für Teams</span><span class="sxs-lookup"><span data-stu-id="bc133-127">Teams guest access settings</span></span>

<span data-ttu-id="bc133-128">Teams verfügt über einen ein/aus-Master-Schalter für den Gastzugriff und eine Vielzahl an Einstellungen zur Kontrolle dessen, was Gäste in einem Team machen können und was nicht.</span><span class="sxs-lookup"><span data-stu-id="bc133-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="bc133-129">Der Master-Schalter, **Gastzugriff in Teams ermöglichen** muss auf **An** gestellt sein, damit Gastzugriff in Teams funktioniert.</span><span class="sxs-lookup"><span data-stu-id="bc133-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="bc133-130">Stellen Sie sicher, dass der Gastzugriff in Teams aktiviert ist und nehmen Sie Anpassungen an den Gasteinstellungen je nach Ihren geschäftlichen Anforderungen vor.</span><span class="sxs-lookup"><span data-stu-id="bc133-130">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="bc133-131">Bedenken Sie, dass sich diese Einstellungen auf alle Teams auswirken.</span><span class="sxs-lookup"><span data-stu-id="bc133-131">Keep in mind that these settings affect all teams.</span></span>

![Screenshot der Teams-Umschaltfläche für den Gastzugriff](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="bc133-133">So legen Sie die Gastzugriffseinstellungen für Teams fest</span><span class="sxs-lookup"><span data-stu-id="bc133-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="bc133-134">Melden Sie sich beim Microsoft 365 Admin Center an auf [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="bc133-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="bc133-135">Klicken Sie im linken Navigationsbereich auf **Alle anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="bc133-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="bc133-136">Klicken Sie unter **Admin Centers** auf **Teams**.</span><span class="sxs-lookup"><span data-stu-id="bc133-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="bc133-137">Erweitern Sie im Teams Admin Center **Organisationsweite Einstellungen** im linken Navigationsbereich und klicken Sie auf **Gastzugriff**.</span><span class="sxs-lookup"><span data-stu-id="bc133-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="bc133-138">Stellen Sie sicher, dass **Gastzugriff in Teams zulassen** auf **Ein** ist.</span><span class="sxs-lookup"><span data-stu-id="bc133-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="bc133-139">Nehmen Sie alle gewünschten Änderungen an den zusätzlichen Gasteinstellungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bc133-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="bc133-140">Sobald Sie den Teams-Gastzugriff aktiviert haben, können Sie den Gastzugriff zu einzelnen Teams und deren zugeordneten SharePoint-Websites optional mithilfe von Vertraulichkeitsbeschriftungen steuern.</span><span class="sxs-lookup"><span data-stu-id="bc133-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="bc133-141">Weitere Informationen finden Sie unter [Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="bc133-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="bc133-142">Nachdem die Gasteinstellung für Teams eingeschaltet wurde, kann es bis zu vierundzwanzig Stunden dauern, bis sie aktiv wird.</span><span class="sxs-lookup"><span data-stu-id="bc133-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="bc133-143">Gasteinstellungen für Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="bc133-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="bc133-144">Teams verwendet Microsoft 365-Gruppen für die Teammitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="bc133-144">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="bc133-145">Die Gasteinstellungen für Microsoft 365-Gruppen müssen aktiviert sein, damit der Gastzugriff in Teams funktionieren kann.</span><span class="sxs-lookup"><span data-stu-id="bc133-145">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Screenshot der Gasteinstellungen für Microsoft 365-Gruppen im Microsoft 365 Admin Center](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="bc133-147">So legt man Gasteinstellungen für Microsoft 365-Gruppen fest</span><span class="sxs-lookup"><span data-stu-id="bc133-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="bc133-148">Erweitern Sie **Einstellungen** im linken Navigationsbereich des Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="bc133-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="bc133-149">Klicken Sie auf **Organisationseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="bc133-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="bc133-150">Klicken Sie in der Liste auf **Microsoft 365-Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="bc133-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="bc133-151">Stellen Sie sicher, dass die Kontrollkästchen bei den Einstellungen **Gruppenbesitzer Personen außerhalb der Organisation zu Microsoft 365-Gruppen als Gäste hinzufügen lassen** und **Mitgliedern von Gästegruppen Zugriff auf Gruppeninhalte gewährleisten** beide aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="bc133-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="bc133-152">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="bc133-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="bc133-153">SharePoint-Freigabeeinstellungen auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="bc133-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="bc133-154">Teams-Inhalte wie Dateien, Ordner und Listen werden alle in SharePoint gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bc133-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="bc133-155">Damit Gäste in Teams Zugriff auf diese Elemente haben, müssen die SharePoint Freigabeeinstellungen auf Organisationsebene die Freigabe mit Gästen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bc133-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="bc133-156">Die Einstellungen auf Organisationsebene bestimmen, welche Einstellungen für einzelne Websites zur Verfügung stehen, einschließlich Websites, die zu Teams zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bc133-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="bc133-157">Websiteeinstellungen können nicht passiver sein als die Einstellungen auf Organisationsebene.</span><span class="sxs-lookup"><span data-stu-id="bc133-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="bc133-158">Wenn Sie die Freigabe von Dateien und Ordnern mit nicht authentifizierten Personen erlauben möchten, wählen Sie **Jeder** aus.</span><span class="sxs-lookup"><span data-stu-id="bc133-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="bc133-159">Wenn Sie sicherstellen möchten, dass sich alle Gäste authentifizieren müssen, wählen Sie **Neue und vorhandene Gäste** aus.</span><span class="sxs-lookup"><span data-stu-id="bc133-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="bc133-160">Wählen Sie die am wenigsten eingeschränkte Einstellung aus, die von jeder Website in Ihrer Organisation benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="bc133-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="bc133-162">So legt man SharePoint-Freigabeeinstellungen auf Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="bc133-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="bc133-163">Klicken Sie im Microsoft 365 Admin Center im linken Navigationsbereich unter **Admin Center** auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="bc133-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="bc133-164">Erweitern Sie im SharePoint Admin Center im linken Navigationsbereich **Richtlinien** und klicken Sie dann auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="bc133-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="bc133-165">Stellen Sie sicher, dass die Externe Freigabe für SharePoint auf **Jeder** oder **Neue und vorhandene Gäste** eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="bc133-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="bc133-166">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bc133-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="bc133-167">SharePoint-Standardlinkeinstellungen auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="bc133-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="bc133-168">Die Standardeinstellungen für die Datei- und -ordnerverknüpfung bestimmen die Verknüpfungsoption, die Benutzern standardmäßig angezeigt wird, wenn sie eine Datei oder einen Ordner freigeben.</span><span class="sxs-lookup"><span data-stu-id="bc133-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="bc133-169">Benutzer können, wenn sie so möchten, die Verknüpfungsart vor der Freigabe in eine der anderen Optionen ändern.</span><span class="sxs-lookup"><span data-stu-id="bc133-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="bc133-170">Bedenken Sie, dass sich diese Einstellung auf alle Teams und SharePoint-Websites in Ihrer Organisation auswirkt.</span><span class="sxs-lookup"><span data-stu-id="bc133-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="bc133-171">Wählen Sie eine der folgenden Verknüpfungsarten, die dann standardmäßig ausgewählt wird, wenn Benutzer Dateien und Ordner freigeben:</span><span class="sxs-lookup"><span data-stu-id="bc133-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="bc133-172">**Jeder mit diesem Link** – Wählen Sie diese Option aus, wenn Sie erwarten, dass Sie viele nicht authentifizierte Freigaben von Dateien und Ordnern durchführen werden.</span><span class="sxs-lookup"><span data-stu-id="bc133-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="bc133-173">Wenn Sie *Jeder*-Links erlauben wollen, aber zufällige nicht authentifizierte Freigaben befürchten, erwägen Sie eine der anderen Optionen als Standard.</span><span class="sxs-lookup"><span data-stu-id="bc133-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="bc133-174">Diese Verknüpfungsart ist nur verfügbar, wenn Sie die Freigabe auf **Jeder** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="bc133-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="bc133-175">**Nur Personen in Ihrer Organisation** – Wählen Sie diese Option, wenn Sie erwarten, dass die meisten Freigaben von Dateien und Ordnern zwischen Personen innerhalb Ihrer Organisation stattfinden werden.</span><span class="sxs-lookup"><span data-stu-id="bc133-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="bc133-176">**Bestimmte Personen** – erwägen Sie diese Option, wenn Sie erwarten, dass Sie viele Dateien und Ordner an Gäste freigeben werden.</span><span class="sxs-lookup"><span data-stu-id="bc133-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="bc133-177">Dieser Typ von Link arbeitet mit Gästen und erfordert deren Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="bc133-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot der Freigabeeinstellungen auf Organisationsebene für Dateien und Ordner in SharePoint und OneDrive](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="bc133-179">So legt man SharePoint-Standardlinkeinstellungen auf Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="bc133-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="bc133-180">Navigieren Sie zur Seite „Freigabe“ im SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="bc133-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="bc133-181">Wählen Sie unter **Datei- und Ordnerlinks** den Link zur Standardfreigabe, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="bc133-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="bc133-182">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bc133-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="bc133-183">Team erstellen</span><span class="sxs-lookup"><span data-stu-id="bc133-183">Create a team</span></span>

<span data-ttu-id="bc133-184">Der nächste Schritt ist das Erstellen des Teams, mit dem Sie vorhaben mit Gästen zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="bc133-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="bc133-185">So erstellt man eine klassische Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="bc133-185">To create a team</span></span>
1. <span data-ttu-id="bc133-186">Klicken Sie in Microsoft Teams auf der Registerkarte **Teams** auf der linken Seite unten auf **Einem Team beitreten oder ein Team erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bc133-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="bc133-187">Klicken Sie auf **Team erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bc133-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="bc133-188">Klicken Sie auf **Neuerstellen eines Teams**.</span><span class="sxs-lookup"><span data-stu-id="bc133-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="bc133-189">Wählen Sie **Privat** oder **Öffentlich** aus.</span><span class="sxs-lookup"><span data-stu-id="bc133-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="bc133-190">Geben Sie einen Namen und eine Beschreibung für das Team ein, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bc133-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="bc133-191">Klicken Sie auf **Überspringen**.</span><span class="sxs-lookup"><span data-stu-id="bc133-191">Click **Skip**.</span></span>

<span data-ttu-id="bc133-192">Wir werden Benutzer später einladen.</span><span class="sxs-lookup"><span data-stu-id="bc133-192">We'll invite users later.</span></span> <span data-ttu-id="bc133-193">Als nächstes ist es wichtig, dass Sie die Freigabeeinstellungen auf Websiteebene für die SharePoint-Website, die dem Team zugeordnet ist, überprüfen.</span><span class="sxs-lookup"><span data-stu-id="bc133-193">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="bc133-194">SharePoint-Freigabeeinstellungen auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="bc133-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="bc133-195">Überprüfen Sie die Freigabeeinstellungen auf Websiteebene, um sicherzustellen, dass sie die Zugriffsart zulassen, die Sie für dieses Team eingestellt haben möchten.</span><span class="sxs-lookup"><span data-stu-id="bc133-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="bc133-196">Wenn Sie z. B. die Einstellungen auf Organisationsebene auf **Jeder** festlegen, von allen Gästen jedoch wollen, dass sie sich für dieses Team authentifizieren, stellen Sie sicher, dass die Freigabeeinstellungen auf Websiteebene auf **Neue und vorhandene Gäste** festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="bc133-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="bc133-198">So legt man Freigabeeinstellungen auf Websiteebene fest</span><span class="sxs-lookup"><span data-stu-id="bc133-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="bc133-199">Erweitern Sie im SharePoint Admin Center links im Navigationsbereich **Websites** und klicken Sie auf **Aktive Websites**.</span><span class="sxs-lookup"><span data-stu-id="bc133-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="bc133-200">Wählen Sie die Site des soeben erstellten Teams aus.</span><span class="sxs-lookup"><span data-stu-id="bc133-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="bc133-201">Klicken Sie ... und wählen Sie **Freigabe** aus.</span><span class="sxs-lookup"><span data-stu-id="bc133-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="bc133-202">Vergewissern Sie sich, dass die Freigabe auf **Jeder** oder **Neue und vorhandene Gäste** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bc133-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="bc133-203">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bc133-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="bc133-204">Benutzer einladen</span><span class="sxs-lookup"><span data-stu-id="bc133-204">Invite users</span></span>

<span data-ttu-id="bc133-205">Einstellungen für die Gastfreigabe sind nun konfiguriert, Sie können also mit dem Hinzufügen von internen Benutzern und Gästen zu Ihrem Team anfangen.</span><span class="sxs-lookup"><span data-stu-id="bc133-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="bc133-206">So lädt man interne Benutzer in ein Team ein</span><span class="sxs-lookup"><span data-stu-id="bc133-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="bc133-207">Klicken Sie im Team auf **Weitere Optionen** (**\*\*\***) und dann auf **Mitglieder hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bc133-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="bc133-208">Geben Sie den Namen der Person ein, die Sie einladen möchten.</span><span class="sxs-lookup"><span data-stu-id="bc133-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="bc133-209">Klicken Sie auf **Hinzufügen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="bc133-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="bc133-210">Sie kann man Gäste zu einem Team hinzufügen</span><span class="sxs-lookup"><span data-stu-id="bc133-210">To invite guests to a team</span></span>
1. <span data-ttu-id="bc133-211">Klicken Sie im Team auf **Weitere Optionen** (**\*\*\***) und dann auf **Mitglieder hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bc133-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="bc133-212">Geben Sie die E-Mail-Adresse des Gasts ein, die Sie einladen möchten.</span><span class="sxs-lookup"><span data-stu-id="bc133-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="bc133-213">Klicken Sie auf **Bearbeiten von Gastbenutzerinformationen**.</span><span class="sxs-lookup"><span data-stu-id="bc133-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="bc133-214">Geben Sie den vollständigen Namen des Gasts ein und klicken Sie auf das Häkchen.</span><span class="sxs-lookup"><span data-stu-id="bc133-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="bc133-215">Klicken Sie auf **Hinzufügen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="bc133-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc133-216">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc133-216">See also</span></span>

[<span data-ttu-id="bc133-217">Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="bc133-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="bc133-218">Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste</span><span class="sxs-lookup"><span data-stu-id="bc133-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="bc133-219">Erstellen einer sicheren Gastfreigabeumgebung</span><span class="sxs-lookup"><span data-stu-id="bc133-219">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="bc133-220">Erstellen eines B2B-Extranets mit verwalteten Gästen</span><span class="sxs-lookup"><span data-stu-id="bc133-220">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="bc133-221">SharePoint- und OneDrive-Integration in Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="bc133-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="bc133-222">Freigabeoptionen werden abgeblendet, wenn von SharePoint oder OneDrive freigegeben wird</span><span class="sxs-lookup"><span data-stu-id="bc133-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
