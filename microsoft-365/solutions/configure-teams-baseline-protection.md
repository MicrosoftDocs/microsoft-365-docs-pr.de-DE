---
title: Konfigurieren von Teams mit grundlegendem Schutz
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
recommendations: false
description: Hier erfahren Sie, wie Sie Teams mit grundlegendem Schutz bereitstellen.
ms.openlocfilehash: bf95c26a9bf724aaddae8321022ecdfceae82d1a
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229059"
---
# <a name="configure-teams-with-baseline-protection"></a><span data-ttu-id="5f6a3-103">Konfigurieren von Teams mit grundlegendem Schutz</span><span class="sxs-lookup"><span data-stu-id="5f6a3-103">Configure teams with baseline protection</span></span>

<span data-ttu-id="5f6a3-104">In diesem Artikel wird erläutert, wie Teams mit eine grundlegenden Schutzebene bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-104">In this article, we look at how to deploy teams with a baseline level of protection.</span></span> <span data-ttu-id="5f6a3-105">Auf dieser Ebene können die Benutzer eine Vielzahl von Optionen für die Zusammenarbeit nutzen und gleichzeitig die Verwaltung von Berechtigungen verbessern sowie grundlegende Schutzmaßnahmen gegen versehentliche Freigabe bieten.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-105">This level allows users a wide range of options for collaboration while enhancing permissions management and providing basic protection against oversharing.</span></span> <span data-ttu-id="5f6a3-106">Empfohlene Schutzmaßnahmen für diese Stufe umfassen Richtlinien für den Identitäts- und Gerätezugriff sowie Schutz vor Schadsoftware.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-106">Recommended protections for this level include identity and device access policies and protection against malware.</span></span> <span data-ttu-id="5f6a3-107">Darüber hinaus können Sie bei Bedarf bedingte Zugriffsrichtlinien und Datenschutzbestimmungen anwenden.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-107">Additionally, you can apply conditional access policies and data loss protections as needed.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="5f6a3-108">Erste Schutzmaßnahmen</span><span class="sxs-lookup"><span data-stu-id="5f6a3-108">Initial protections</span></span>

<span data-ttu-id="5f6a3-109">Als Erstes wird empfohlen, grundlegende Identitäts- und Gerätezugriffsrichtlinien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-109">As a first step, we recommend that you configure basic identity and device-access policies.</span></span> <span data-ttu-id="5f6a3-110">Einzelheiten hierzu finden Sie unter [Richtlinienempfehlungen zum Schützen von Teams-Chats, -Gruppen und -Dateien](../security/office-365-security/teams-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5f6a3-110">See [Policy recommendations for securing Teams chats, groups, and files](../security/office-365-security/teams-access-policies.md) for details.</span></span>

<span data-ttu-id="5f6a3-111">Außerdem empfehlen wir, die grundlegenden Defender für Office 365-Features zum Schutz vor Schadsoftware in Dokumenten, Anlagen und Links zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-111">We also recommend turning on basic Defender for Office 365 features to guard against malware in documents, attachments, and links.</span></span> <span data-ttu-id="5f6a3-112">Wir empfehlen, jede der Optionen in der folgenden Tabelle zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-112">We recommend turning on each of the options in the following table.</span></span>

|<span data-ttu-id="5f6a3-113">Option</span><span class="sxs-lookup"><span data-stu-id="5f6a3-113">Option</span></span>|<span data-ttu-id="5f6a3-114">Informationen</span><span class="sxs-lookup"><span data-stu-id="5f6a3-114">Information</span></span>|
|:------|:-----------|
|<span data-ttu-id="5f6a3-115">Sichere Anlagen für SPO, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5f6a3-115">Safe Attachments for SPO, OneDrive and Teams</span></span>|[<span data-ttu-id="5f6a3-116">Sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="5f6a3-116">Safe Attachments</span></span>](../security/office-365-security/safe-attachments.md) <p> [<span data-ttu-id="5f6a3-117">Defender für Office 365 – SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5f6a3-117">Defender for Office 365 - SharePoint, OneDrive, and Microsoft Teams</span></span>](../security/office-365-security/mdo-for-spo-odb-and-teams.md)|
|<span data-ttu-id="5f6a3-118">Sichere Dokumente</span><span class="sxs-lookup"><span data-stu-id="5f6a3-118">Safe Documents</span></span>|[<span data-ttu-id="5f6a3-119">Sichere Dokumente in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="5f6a3-119">Safe Documents in Microsoft Defender for Office 365</span></span>](../security/office-365-security/safe-docs.md)|
|<span data-ttu-id="5f6a3-120">Sichere Links für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5f6a3-120">Safe Links for Teams</span></span>|[<span data-ttu-id="5f6a3-121">Office 365 Sichere Links in Teams</span><span class="sxs-lookup"><span data-stu-id="5f6a3-121">Office 365 Safe Links in Teams</span></span>](../security/office-365-security/safe-links.md) <p> [<span data-ttu-id="5f6a3-122">Sichere Links</span><span class="sxs-lookup"><span data-stu-id="5f6a3-122">Safe Links</span></span>](../security/office-365-security/safe-links.md)|

## <a name="teams-guest-sharing"></a><span data-ttu-id="5f6a3-123">Teams-Gastfreigabe</span><span class="sxs-lookup"><span data-stu-id="5f6a3-123">Teams guest sharing</span></span>

<span data-ttu-id="5f6a3-124">In jeder der Ebenen haben wir die Möglichkeit, die Freigabe für Personen außerhalb Ihrer Organisation zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-124">In each of the tiers, we have the option of sharing with people outside your organization.</span></span> <span data-ttu-id="5f6a3-125">Bei den vertraulichen und hochsensiblen Kategorien haben wir die Möglichkeit, die Gastfreigabe auf Teamebene durch Verwenden von Vertraulichkeitsbeschriftungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-125">For the sensitive and highly sensitive tiers, we will have the option to turn guest sharing off at the team level by using sensitivity labels.</span></span> <span data-ttu-id="5f6a3-126">Die Einstellung für die Gastfreigabe auf Organisationsebene muss aktiviert sein, damit die Gastfreigabe überhaupt in Teams funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-126">But the organization-level guest sharing setting must be turned on for guest sharing to work at all in Teams.</span></span>

![Screenshot der Teams-Umschaltfläche für den Gastzugriff](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="5f6a3-128">So legen Sie die Gastzugriffseinstellungen für Teams fest</span><span class="sxs-lookup"><span data-stu-id="5f6a3-128">To set Teams guest access settings</span></span>

1. <span data-ttu-id="5f6a3-129">Melden Sie sich beim Microsoft 365 Admin Center an auf [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5f6a3-129">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="5f6a3-130">Klicken Sie in der linken Navigationsleiste auf **Alle anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-130">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="5f6a3-131">Klicken Sie unter **Admin Centers** auf **Teams**.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-131">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="5f6a3-132">Erweitern Sie im Teams Admin Center **Organisationsweite Einstellungen** in der linken Navigationsleiste und klicken Sie auf **Gastzugriff**.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-132">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="5f6a3-133">Stellen Sie sicher, dass **Gastzugriff in Teams zulassen** auf **Ein** ist.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-133">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="5f6a3-134">Nehmen Sie alle gewünschten Änderungen an den zusätzlichen Gasteinstellungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-134">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="5f6a3-135">Es könnte bis zu vierundzwanzig Stunden dauern, bis die Gasteinstellung für Teams aktiv wird, nachdem sie eingeschaltet wurde.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-135">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

<span data-ttu-id="5f6a3-136">Die Gastfreigabe ist für Office 365-Gruppen und Microsoft Office SharePoint Online standardmäßig aktiviert. Wenn Sie jedoch zuvor eine der Einstellungen für die Gastfreigabe für Ihre Organisation geändert haben, empfiehlt es sich, [Zusammenarbeit mit Gästen in einem Team](./collaborate-as-team.md) zu prüfen, um sicherzustellen, dass die Gastfreigabe in Teams zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-136">Guest sharing is turned on by default for Office 365 groups and SharePoint, however if you have previously changed any of the guest sharing settings for your organization, we recommend that you review [Collaborate with guests in a team](./collaborate-as-team.md) to ensure that guest sharing will be available in Teams.</span></span>

## <a name="site-and-file-sharing"></a><span data-ttu-id="5f6a3-137">Website- und Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="5f6a3-137">Site and file sharing</span></span>

<span data-ttu-id="5f6a3-138">Um das Risiko zu verringern, dass Dateien oder Ordner versehentlich für Personen außerhalb Ihrer Organisation freigegeben werden, sollten Sie den standardmäßigen Freigabelink für Microsoft Office SharePoint Online auf *Nur Personen in Ihrer Organisation* setzen.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-138">To reduce the risk of accidentally sharing files or folders with people outside your organization, we recommend changing the default sharing link for SharePoint to *Only people in your organization*.</span></span> <span data-ttu-id="5f6a3-139">(Wenn Benutzer externe Freigaben vornehmen müssen und die Gastfreigabe aktiviert ist, können Sie den Linktyp beim Freigeben weiterhin ändern.)</span><span class="sxs-lookup"><span data-stu-id="5f6a3-139">(If users need to share externally, and you have enabled guest sharing, they can still change the link type when they share.)</span></span>

<span data-ttu-id="5f6a3-140">So ändern Sie den standardmäßigen Freigabelink</span><span class="sxs-lookup"><span data-stu-id="5f6a3-140">To change the default sharing link</span></span>
1. <span data-ttu-id="5f6a3-141">Öffnen Sie das [SharePoint Admin Center](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="5f6a3-141">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="5f6a3-142">Klicken Sie unter **Richtlinien** auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-142">Under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="5f6a3-143">Wählen Sie unter **Datei- und Ordnerlinks** die Option **Nur Personen in Ihrer Organisation** aus.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-143">Under **File and folder links**, select **Only people in your organization**.</span></span>
4. <span data-ttu-id="5f6a3-144">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-144">Click **Save**.</span></span>

<span data-ttu-id="5f6a3-145">Für eine optimale Benutzererfahrung empfiehlt es sich außerdem, [SharePoint- und OneDrive-Integration in Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-145">For the best guest sharing experience, we also recommend that you enable [SharePoint and OneDrive integration with Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="5f6a3-146">Ein Team erstellen</span><span class="sxs-lookup"><span data-stu-id="5f6a3-146">Create a team</span></span>

<span data-ttu-id="5f6a3-147">Eine zusätzliche Konfiguration für die grundlegende Schutzebene erfolgt auf der SharePoint-Website, die einem Team zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-147">Additional configuration for the baseline level of protection is done in the SharePoint site associated with a team.</span></span> <span data-ttu-id="5f6a3-148">[Erstellen Sie ein öffentliches oder privates Team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b), bevor Sie mit dem nächsten Abschnitt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-148">[Create a public or private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) before proceeding to the next section.</span></span>

## <a name="site-sharing-settings"></a><span data-ttu-id="5f6a3-149">Freigabeeinstellungen für Websites</span><span class="sxs-lookup"><span data-stu-id="5f6a3-149">Site sharing settings</span></span>

<span data-ttu-id="5f6a3-150">Standardmäßig können Mitglieder einer SharePoint-Website andere Benutzer zur Website einladen.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-150">By default, members of a SharePoint site can invite others to the site.</span></span> <span data-ttu-id="5f6a3-151">Wenn eine Website zu einem Team gehört, werden Teammitglieder als Websitemitglieder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-151">When a site is part of a team, team members are included as site members.</span></span> <span data-ttu-id="5f6a3-152">Personen, die direkt zur Website hinzugefügt wurden, haben jedoch keinen Zugriff auf den Rest des Teams.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-152">However, people added directly to the site don't have access to the rest of the team.</span></span> <span data-ttu-id="5f6a3-153">Aus diesem Grund empfiehlt es sich, Berechtigungen ausschließlich über das Team zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-153">For this reason, we recommend managing permissions exclusively through the team.</span></span>

<span data-ttu-id="5f6a3-154">Um die Berechtigungsverwaltung zu unterstützen, empfiehlt es sich, die zugeordnete Website so zu konfigurieren, dass sie nur Besitzern das Freigeben der Website selbst gestattet.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-154">To help with permissions management, we recommend configuring the associated site to only allow owners to share the site by itself.</span></span> <span data-ttu-id="5f6a3-155">Auf diese Weise wird die Verwaltung von Berechtigungen vereinfacht und der Zugriff von Personen ohne Wissen des Teambesitzers verhindert.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-155">This simplifies permissions management and helps prevent access by people without a team owner's knowledge.</span></span> <span data-ttu-id="5f6a3-156">Führen Sie diese Vorgehensweise für jedes Team aus, das einen grundlegenden Schutz erfordert.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-156">Do this for each team that requires baseline protection.</span></span>

<span data-ttu-id="5f6a3-157">So aktualisieren Sie die Freigabeeinstellungen der Website</span><span class="sxs-lookup"><span data-stu-id="5f6a3-157">To update the site sharing settings</span></span>
1. <span data-ttu-id="5f6a3-158">Klicken Sie auf der Symbolleiste des Teams auf **Dateien**.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-158">In the tool bar for the team, click **Files**.</span></span>
2. <span data-ttu-id="5f6a3-159">Klicken Sie auf **In SharePoint öffnen**.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-159">Click **Open in SharePoint**.</span></span>
3. <span data-ttu-id="5f6a3-160">Klicken Sie in der Symbolleiste der SharePoint-Website auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-160">In the tool bar of the SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
4. <span data-ttu-id="5f6a3-161">Klicken Sie im Bereich **Websiteberechtigungen** unter **Websitefreigabe** auf **Ändern, wie Mitglieder teilen können**.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-161">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
5. <span data-ttu-id="5f6a3-162">Wählen Sie unter **Freigabeberechtigungen** die Option **Websitebesitzer und -mitglieder sowie Personen mit Bearbeitungsberechtigungen können Dateien und Ordner freigeben, aber nur Websitebesitzer können die Website freigeben**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-162">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="5f6a3-163">Zusätzliche Schutzfunktionen</span><span class="sxs-lookup"><span data-stu-id="5f6a3-163">Additional protections</span></span>

<span data-ttu-id="5f6a3-164">Microsoft 365 bietet zusätzliche Methoden zum Schützen Ihrer Inhalte.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-164">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="5f6a3-165">Prüfen Sie, ob die folgenden Optionen zur Verbesserung der Sicherheit in Ihrer Organisation beitragen würden.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-165">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="5f6a3-166">Lassen Sie Gäste den [Nutzungsbedingungen](/azure/active-directory/conditional-access/terms-of-use) zustimmen.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-166">Have guests agree to a [terms of use](/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="5f6a3-167">Konfigurieren Sie eine [Richtlinie für Sitzungstimeout](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) für Gastbenutzer.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-167">Configure a [session timeout policy](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="5f6a3-168">Erstellen Sie [Typen vertraulicher Informationen](../compliance/sensitive-information-type-learn-about.md) und verwenden Sie [Schutz vor Datenverlust](../compliance/dlp-learn-about-dlp.md) zum Festlegen von Richtlinien für den Zugriff auf vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="5f6a3-168">Create [sensitive information types](../compliance/sensitive-information-type-learn-about.md) and use [data loss protection](../compliance/dlp-learn-about-dlp.md) to set policies around accessing sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f6a3-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f6a3-169">See Also</span></span>

[<span data-ttu-id="5f6a3-170">Verwalten von Besprechungsrichtlinien in Teams</span><span class="sxs-lookup"><span data-stu-id="5f6a3-170">Manage meeting policies in Teams</span></span>](/microsoftteams/meeting-policies-in-teams)

[<span data-ttu-id="5f6a3-171">Erste Schritte mit dem Insider-Risikomanagement</span><span class="sxs-lookup"><span data-stu-id="5f6a3-171">Get started with insider risk management</span></span>](../compliance/insider-risk-management-configure.md)