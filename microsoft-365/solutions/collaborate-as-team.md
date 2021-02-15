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
ms.openlocfilehash: 66c5692dd8cd233d8b3639f8ce0755ce51b60c0a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233074"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="f8955-103">Zusammenarbeit mit Gästen in einem Team</span><span class="sxs-lookup"><span data-stu-id="f8955-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="f8955-104">Wenn Sie mit Gästen über Dokumente, Aufgaben und Unterhaltungen hinweg zusammenarbeiten müssen, empfehlen wir die Verwendung von Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f8955-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="f8955-105">Teams bietet alle in Office und SharePoint verfügbaren Features für die Zusammenarbeit mit dauerhaftem Chat und einem anpassbaren und erweiterbaren Satz von Tools für die Zusammenarbeit in einer einheitlichen Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="f8955-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="f8955-106">In diesem Artikel werden die schritte zur Microsoft 365-Konfiguration erläutert, die zum Einrichten eines Teams für die Zusammenarbeit mit Gästen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f8955-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="f8955-107">Nachdem Sie den Gastzugriff konfiguriert haben, können Sie Gäste zu Teams einladen, indem Sie die Schritte in "Hinzufügen von Gästen zu [einem Team in Teams" ausführen.](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f)</span><span class="sxs-lookup"><span data-stu-id="f8955-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="f8955-108">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="f8955-108">Video demonstration</span></span>

<span data-ttu-id="f8955-109">In diesem Video werden die in diesem Dokument beschriebenen Konfigurationsschritte gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8955-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="f8955-110">Einstellungen für die externe Zusammenarbeit in Azure</span><span class="sxs-lookup"><span data-stu-id="f8955-110">Azure External collaboration settings</span></span>

<span data-ttu-id="f8955-111">Die Freigabe in Microsoft 365 wird auf der höchsten Ebene durch die Einstellungen für die externe Zusammenarbeit in [Azure Active Directory bestimmt.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)</span><span class="sxs-lookup"><span data-stu-id="f8955-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="f8955-112">Wenn die Gastfreigabe in Azure AD deaktiviert oder eingeschränkt ist, setzt diese Einstellung alle Freigabeeinstellungen außer Kraft, die Sie in Microsoft 365 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f8955-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="f8955-113">Überprüfen Sie die Einstellungen für die externe B2B-Zusammenarbeit, um sicherzustellen, dass die Freigabe für Gäste nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="f8955-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot der Seite mit den Einstellungen für die Azure Active Directory-Organisationsbeziehungen](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="f8955-115">So legen Sie Einstellungen für die externe Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="f8955-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="f8955-116">Melden Sie sich bei Azure Active Directory unter [https://aad.portal.azure.com](https://aad.portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="f8955-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="f8955-117">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f8955-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="f8955-118">Klicken **Sie auf "Externe Identitäten".**</span><span class="sxs-lookup"><span data-stu-id="f8955-118">Click **External identities**.</span></span>
4. <span data-ttu-id="f8955-119">Klicken Sie **auf dem Bildschirm "Erste** Schritte" im linken Navigationsbereich auf Einstellungen für **die externe Zusammenarbeit.**</span><span class="sxs-lookup"><span data-stu-id="f8955-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="f8955-120">Stellen Sie **sicher, dass** Administratoren und Benutzer in der Rolle "Gast-Inviter" einladen können und dass Mitglieder, die einladen **können,** beide auf **"Ja" festgelegt sind.**</span><span class="sxs-lookup"><span data-stu-id="f8955-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="f8955-121">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f8955-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="f8955-122">Beachten Sie die Einstellungen im Abschnitt **"Einschränkungen für die Zusammenarbeit".**</span><span class="sxs-lookup"><span data-stu-id="f8955-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="f8955-123">Stellen Sie sicher, dass die Domänen der Gäste, mit der Sie zusammenarbeiten möchten, nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="f8955-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="f8955-124">Wenn Sie mit Gästen aus mehreren Organisationen arbeiten, sollten Sie deren Zugriff auf Verzeichnisdaten einschränken.</span><span class="sxs-lookup"><span data-stu-id="f8955-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="f8955-125">Dadurch wird verhindert, dass sie sehen, wer sonst ein Gast im Verzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="f8955-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="f8955-126">Wählen Sie dazu unter "Gastbenutzerzugriffseinschränkungen" die Option "Gastbenutzer haben eingeschränkten Zugriff auf Eigenschaften und Mitgliedschaft in Verzeichnisobjekteinstellungen" aus, oder der Gastbenutzerzugriff ist auf Eigenschaften und Mitgliedschaften ihrer eigenen **Verzeichnisobjekte beschränkt.** </span><span class="sxs-lookup"><span data-stu-id="f8955-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="f8955-127">Gastzugriffseinstellungen für Teams</span><span class="sxs-lookup"><span data-stu-id="f8955-127">Teams guest access settings</span></span>

<span data-ttu-id="f8955-128">Teams verfügt über einen Master-Ein-/Aus-Schalter für den Gastzugriff und eine Vielzahl von Einstellungen, die steuern, was Gäste in einem Team tun können.</span><span class="sxs-lookup"><span data-stu-id="f8955-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="f8955-129">Der Master-Switch" **"Gastzugriff in Teams** zulassen" muss **"On"** sein, damit der Gastzugriff in Teams funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f8955-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="f8955-130">Stellen Sie sicher, dass der Gastzugriff in Teams aktiviert ist, und nehmen Sie eine Anpassung der Gasteinstellungen basierend auf Ihren Geschäftsanforderungen vor.</span><span class="sxs-lookup"><span data-stu-id="f8955-130">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="f8955-131">Beachten Sie, dass sich diese Einstellungen auf alle Teams auswirken.</span><span class="sxs-lookup"><span data-stu-id="f8955-131">Keep in mind that these settings affect all teams.</span></span>

![Screenshot der Teams-Umschaltfläche für den Gastzugriff](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="f8955-133">So legen Sie die Gastzugriffseinstellungen für Teams fest</span><span class="sxs-lookup"><span data-stu-id="f8955-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="f8955-134">Melden Sie sich beim Microsoft 365 Admin Center an auf [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f8955-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="f8955-135">Klicken Sie im linken Navigationsbereich auf **"Alle anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="f8955-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="f8955-136">Klicken Sie unter **Admin Centers** auf **Teams**.</span><span class="sxs-lookup"><span data-stu-id="f8955-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="f8955-137">Erweitern Sie im Teams Admin Center im linken Navigationsbereich **organisationsweite** Einstellungen, und klicken Sie auf **Gastzugriff.**</span><span class="sxs-lookup"><span data-stu-id="f8955-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="f8955-138">Stellen Sie sicher, dass **Gastzugriff in Teams zulassen** auf **Ein** ist.</span><span class="sxs-lookup"><span data-stu-id="f8955-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="f8955-139">Nehmen Sie alle gewünschten Änderungen an den zusätzlichen Gasteinstellungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f8955-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="f8955-140">Sobald der Gastzugriff für Teams aktiviert ist, können Sie optional den Gastzugriff auf einzelne Teams und die zugehörigen SharePoint-Websites mithilfe von Vertraulichkeitsbezeichnungen steuern.</span><span class="sxs-lookup"><span data-stu-id="f8955-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="f8955-141">Weitere Informationen finden Sie unter [Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="f8955-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="f8955-142">Es kann bis zu 24 Stunden dauern, bis die Gasteinstellungen von Teams aktiviert werden, nachdem Sie sie aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="f8955-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="f8955-143">Gasteinstellungen für Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="f8955-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="f8955-144">Teams verwendet Microsoft 365-Gruppen für die Teammitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="f8955-144">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="f8955-145">Die Gasteinstellungen für Microsoft 365-Gruppen müssen aktiviert sein, damit der Gastzugriff in Teams funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f8955-145">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Screenshot der Gasteinstellungen für Microsoft 365-Gruppen im Microsoft 365 Admin Center](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="f8955-147">So legen Sie Die Gasteinstellungen für Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="f8955-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="f8955-148">Erweitern Sie im Microsoft 365 Admin Center im linken Navigationsbereich die **Einstellungen.**</span><span class="sxs-lookup"><span data-stu-id="f8955-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="f8955-149">Klicken Sie **auf Organisationseinstellungen.**</span><span class="sxs-lookup"><span data-stu-id="f8955-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="f8955-150">Klicken Sie in der Liste auf **Microsoft 365-Gruppen.**</span><span class="sxs-lookup"><span data-stu-id="f8955-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="f8955-151">Stellen Sie sicher, dass die Kontrollkästchen "Gruppenbesitzern das Hinzufügen von Personen außerhalb Ihrer Organisation zu **Microsoft 365-Gruppen** als Gäste gestatten" und "Gastgruppenmitglieder zugriff auf Gruppeninhalte gestatten" aktiviert sind. </span><span class="sxs-lookup"><span data-stu-id="f8955-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="f8955-152">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **"Änderungen speichern".**</span><span class="sxs-lookup"><span data-stu-id="f8955-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="f8955-153">Freigabeeinstellungen auf SharePoint-Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="f8955-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="f8955-154">Teams-Inhalte wie Dateien, Ordner und Listen werden alle in SharePoint gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f8955-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="f8955-155">Damit Gäste Zugriff auf diese Elemente in Teams haben, müssen die Freigabeeinstellungen auf Der Organisationsebene von SharePoint die Freigabe für Gäste zulassen.</span><span class="sxs-lookup"><span data-stu-id="f8955-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="f8955-156">Die Einstellungen auf Organisationsebene bestimmen, welche Einstellungen für einzelne Websites verfügbar sind, einschließlich websites, die Teams zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f8955-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="f8955-157">Websiteeinstellungen können nicht weniger als die Einstellungen auf Organisationsebene sein.</span><span class="sxs-lookup"><span data-stu-id="f8955-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="f8955-158">Wenn Sie die Datei- und Ordnerfreigabe für nicht authentifizierte Personen zulassen möchten, wählen Sie **"Jeder" aus.**</span><span class="sxs-lookup"><span data-stu-id="f8955-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="f8955-159">Wenn Sie sicherstellen möchten, dass alle Gäste authentifiziert werden müssen, wählen **Sie "Neu" und "Vorhandene Gäste" aus.**</span><span class="sxs-lookup"><span data-stu-id="f8955-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="f8955-160">Wählen Sie die einstellung mit den meisten Anforderungen aus, die von jeder Website in Ihrer Organisation benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="f8955-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="f8955-162">So legen Sie Freigabeeinstellungen auf Organisationsebene für SharePoint</span><span class="sxs-lookup"><span data-stu-id="f8955-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="f8955-163">Klicken Sie im Microsoft 365 Admin Center im linken Navigationsbereich unter **Admin Center** auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f8955-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="f8955-164">Erweitern Sie im SharePoint Admin Center im  linken Navigationsbereich "Richtlinien", und klicken Sie dann auf **"Freigabe".**</span><span class="sxs-lookup"><span data-stu-id="f8955-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="f8955-165">Stellen Sie sicher, dass die externe Freigabe für SharePoint auf **"Jeder"** **oder "Neu" und "Vorhandene Gäste" festgelegt ist.**</span><span class="sxs-lookup"><span data-stu-id="f8955-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="f8955-166">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f8955-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="f8955-167">Standardlinkeinstellungen auf Organisationsebene in SharePoint</span><span class="sxs-lookup"><span data-stu-id="f8955-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="f8955-168">Die Standardeinstellungen für Datei- und Ordnerverknüpfungen bestimmen die Linkoption, die Benutzern standardmäßig angezeigt wird, wenn sie eine Datei oder einen Ordner freigeben.</span><span class="sxs-lookup"><span data-stu-id="f8955-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="f8955-169">Benutzer können den Linktyp bei Bedarf vor der Freigabe in eine der anderen Optionen ändern.</span><span class="sxs-lookup"><span data-stu-id="f8955-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="f8955-170">Beachten Sie, dass sich diese Einstellung auf alle Teams und SharePoint-Websites in Ihrer Organisation auswirkt.</span><span class="sxs-lookup"><span data-stu-id="f8955-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="f8955-171">Wählen Sie einen der folgenden Linktypen aus, der standardmäßig ausgewählt wird, wenn Benutzer Dateien und Ordner freigeben:</span><span class="sxs-lookup"><span data-stu-id="f8955-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="f8955-172">**Jeder mit dem Link** – Wählen Sie diese Option aus, wenn Sie erwarten, dass eine große Menge nicht authentifizierter Freigaben von Dateien und Ordnern möglich ist.</span><span class="sxs-lookup"><span data-stu-id="f8955-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="f8955-173">Wenn Sie "Jeder"-Links  zulassen möchten, aber bedenken, dass die Freigabe versehentlich nicht authentifiziert wird, sollten Sie eine der anderen Optionen als Standard verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8955-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="f8955-174">Dieser Linktyp ist nur verfügbar, wenn Sie die Freigabe für **"Jeder"** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="f8955-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="f8955-175">**Nur Personen in Ihrer Organisation** – Wählen Sie diese Option aus, wenn Sie erwarten, dass die meisten Datei- und Ordnerfreigaben für Personen innerhalb Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f8955-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="f8955-176">**Bestimmte Personen** – Erwägen Sie diese Option, wenn Sie eine große Menge datei- und Ordnerfreigaben für Gäste erwarten.</span><span class="sxs-lookup"><span data-stu-id="f8955-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="f8955-177">Diese Art von Link funktioniert mit Gästen und erfordert, dass sie sich authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="f8955-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot der Freigabeeinstellungen auf Organisationsebene für Dateien und Ordner in SharePoint und OneDrive](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="f8955-179">So legen Sie die Standardlinkeinstellungen auf Organisationsebene für SharePoint</span><span class="sxs-lookup"><span data-stu-id="f8955-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="f8955-180">Navigieren Sie im SharePoint Admin Center zur Seite "Freigabe".</span><span class="sxs-lookup"><span data-stu-id="f8955-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="f8955-181">Wählen **Sie unter Datei- und Ordnerlinks** den Standardfreigabelink aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f8955-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="f8955-182">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f8955-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="f8955-183">Ein Team erstellen</span><span class="sxs-lookup"><span data-stu-id="f8955-183">Create a team</span></span>

<span data-ttu-id="f8955-184">Der nächste Schritt besteht im Erstellen des Teams, das Sie für die Zusammenarbeit mit Gästen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f8955-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="f8955-185">So erstellen Sie ein Team</span><span class="sxs-lookup"><span data-stu-id="f8955-185">To create a team</span></span>
1. <span data-ttu-id="f8955-186">Klicken Sie in Teams auf  der Registerkarte **"Teams"** unten im linken Bereich auf "Teilnehmen", oder erstellen Sie ein Team.</span><span class="sxs-lookup"><span data-stu-id="f8955-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="f8955-187">Klicken **Sie auf "Team erstellen".**</span><span class="sxs-lookup"><span data-stu-id="f8955-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="f8955-188">Klicken **Sie auf "Team von Grund auf neu erstellen".**</span><span class="sxs-lookup"><span data-stu-id="f8955-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="f8955-189">Wählen **Sie "Privat"** oder **"Öffentlich" aus.**</span><span class="sxs-lookup"><span data-stu-id="f8955-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="f8955-190">Geben Sie einen Namen und eine Beschreibung für das Team ein, und klicken Sie dann auf **"Erstellen".**</span><span class="sxs-lookup"><span data-stu-id="f8955-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="f8955-191">Klicken Sie **auf "Überspringen".**</span><span class="sxs-lookup"><span data-stu-id="f8955-191">Click **Skip**.</span></span>

<span data-ttu-id="f8955-192">Wir laden die Benutzer später ein.</span><span class="sxs-lookup"><span data-stu-id="f8955-192">We'll invite users later.</span></span> <span data-ttu-id="f8955-193">Als Nächstes ist es wichtig, die Freigabeeinstellungen auf Websiteebene für die dem Team zugeordnete SharePoint-Website zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f8955-193">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="f8955-194">Freigabeeinstellungen auf Websiteebene in SharePoint</span><span class="sxs-lookup"><span data-stu-id="f8955-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="f8955-195">Überprüfen Sie die Freigabeeinstellungen auf Websiteebene, um sicherzustellen, dass sie die Art des Zugriffs zulassen, den Sie für dieses Team wünschen.</span><span class="sxs-lookup"><span data-stu-id="f8955-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="f8955-196">Wenn Sie beispielsweise die Einstellungen auf Organisationsebene auf **"Jeder"** festlegen, aber alle Gäste für dieses Team authentifizieren sollen, stellen Sie sicher, dass die Freigabeeinstellungen auf Websiteebene auf **"Neu"** und "Vorhandene Gäste" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f8955-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="f8955-198">So legen Sie Freigabeeinstellungen auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="f8955-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="f8955-199">Erweitern Sie im SharePoint Admin Center im linken Navigationsbereich **"Websites",** und klicken Sie auf **"Aktive Websites".**</span><span class="sxs-lookup"><span data-stu-id="f8955-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="f8955-200">Wählen Sie die Site des soeben erstellten Teams aus.</span><span class="sxs-lookup"><span data-stu-id="f8955-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="f8955-201">Klicken Sie auf ... und wählen Sie **"Freigabe"** aus.</span><span class="sxs-lookup"><span data-stu-id="f8955-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="f8955-202">Stellen Sie sicher, dass die Freigabe auf **"Jeder"** oder **"Neu" und "Vorhandene Gäste" festgelegt ist.**</span><span class="sxs-lookup"><span data-stu-id="f8955-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="f8955-203">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f8955-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="f8955-204">Benutzer einladen</span><span class="sxs-lookup"><span data-stu-id="f8955-204">Invite users</span></span>

<span data-ttu-id="f8955-205">Die Einstellungen für die Gastfreigabe sind jetzt konfiguriert, sodass Sie mit dem Hinzufügen interner Benutzer und Gäste zu Ihrem Team beginnen können.</span><span class="sxs-lookup"><span data-stu-id="f8955-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="f8955-206">So laden Sie interne Benutzer zu einem Team ein</span><span class="sxs-lookup"><span data-stu-id="f8955-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="f8955-207">Klicken Sie im Team auf **"Weitere Optionen"** ( ), und klicken Sie dann auf **\*\*\*** **"Mitglied hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="f8955-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="f8955-208">Geben Sie den Namen der Person ein, die Sie einladen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8955-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="f8955-209">Klicken Sie auf **Hinzufügen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="f8955-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="f8955-210">So laden Sie Gäste zu einem Team ein</span><span class="sxs-lookup"><span data-stu-id="f8955-210">To invite guests to a team</span></span>
1. <span data-ttu-id="f8955-211">Klicken Sie im Team auf **"Weitere Optionen"** ( ), und klicken Sie dann auf **\*\*\*** **"Mitglied hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="f8955-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="f8955-212">Geben Sie die E-Mail-Adresse des Gasts ein, den Sie einladen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8955-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="f8955-213">Klicken **Sie auf Gastinformationen bearbeiten.**</span><span class="sxs-lookup"><span data-stu-id="f8955-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="f8955-214">Geben Sie den vollständigen Namen des Gasts ein, und klicken Sie auf das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="f8955-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="f8955-215">Klicken Sie auf **Hinzufügen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="f8955-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8955-216">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8955-216">See also</span></span>

[<span data-ttu-id="f8955-217">Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="f8955-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="f8955-218">Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste</span><span class="sxs-lookup"><span data-stu-id="f8955-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="f8955-219">Erstellen einer sicheren Gastfreigabeumgebung</span><span class="sxs-lookup"><span data-stu-id="f8955-219">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="f8955-220">Erstellen eines B2B-Extranets mit verwalteten Gästen</span><span class="sxs-lookup"><span data-stu-id="f8955-220">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="f8955-221">SharePoint- und OneDrive-Integration in Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="f8955-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="f8955-222">Freigabeoptionen sind bei der Freigabe aus SharePoint oder OneDrive ausgegraut</span><span class="sxs-lookup"><span data-stu-id="f8955-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
