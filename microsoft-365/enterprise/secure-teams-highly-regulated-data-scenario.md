---
title: Teams für streng regulierte Daten
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erstellen Sie ein sicheres Team zum Speichern Ihrer wertvollsten und vertraulichen Dateien.
ms.openlocfilehash: 95c0fc4177f2a16fc79dd0833809f4405e8cdda9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631393"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="34299-103">Teams für streng regulierte Daten</span><span class="sxs-lookup"><span data-stu-id="34299-103">Teams for highly regulated data</span></span>

<span data-ttu-id="34299-104">Dieser Artikel enthält Empfehlungen und beschreibt die Schritte zum Konfigurieren eines privaten Teams in Microsoft Teams, das den Zugriff auf Teams-Features, z. B. Chats, Besprechungen und Dateien, auf die Mitglieder und Besitzer der Microsoft 365-Gruppe für dieses Team beschränkt.</span><span class="sxs-lookup"><span data-stu-id="34299-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Microsoft 365 group for the team.</span></span> 

<span data-ttu-id="34299-105">Neben dem privaten Zugriff, der auf der Microsoft 365-Gruppe basiert, wird in diesem Artikel beschrieben, wie die zugrunde liegende private SharePoint-Teamwebsite, auf die Sie über den Abschnitt **Dateien** eines Teamkanals zugreifen können, für die zusätzliche Sicherheit konfiguriert wird, die für die Speicherung von streng regulierten Daten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="34299-105">Beyond the private access based on the Microsoft 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="34299-106">Auf dieser SharePoint-Teamwebsite können Sie Dateien, Seiten, einen freigegebenen Kalender, Aufgaben, ein Notizbuch und Listen speichern und gemeinsam bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="34299-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

>[!Note]
> <span data-ttu-id="34299-107">[Hier](teams-sharepoint-online-sites-highly-regulated-data.md) finden Sie ein ähnliches Szenario unter Verwendung von SharePoint.</span><span class="sxs-lookup"><span data-stu-id="34299-107">A similar scenario using SharePoint is [here](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
>

<span data-ttu-id="34299-108">Die Elemente der Konfiguration für ein Team für streng regulierte Daten sind:</span><span class="sxs-lookup"><span data-stu-id="34299-108">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="34299-109">Ein privates Team mit einer entsprechenden Microsoft 365-Gruppe, die über Benutzerkonten für Besitzer und Mitglieder verfügt.</span><span class="sxs-lookup"><span data-stu-id="34299-109">A private team with a corresponding Microsoft 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="34299-110">Zusätzliche Sicherheit auf der zugrunde liegenden SharePoint-Website für das Team, die verhindert,</span><span class="sxs-lookup"><span data-stu-id="34299-110">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="34299-111">Dass Mitglieder der Website anderen Personen Zugriff gewähren.</span><span class="sxs-lookup"><span data-stu-id="34299-111">Prevents members of the site from granting access to others.</span></span>
  - <span data-ttu-id="34299-112">Dass Nicht-Mitglieder der Website Zugriff auf die Website anfordern.</span><span class="sxs-lookup"><span data-stu-id="34299-112">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="34299-113">Eine Aufbewahrungsbezeichnung für die zugrunde liegende SharePoint-Website, die automatisch auf neue Dateien auf der Website angewendet wird, als Standardmethode zum Definieren von Aufbewahrungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="34299-113">A retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="34299-114">Eine DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust), die anhand der Aufbewahrungsbezeichnung Benutzer daran hindert, Dateien für Empfänger außerhalb der Organisation freizugeben oder an diese zu senden.</span><span class="sxs-lookup"><span data-stu-id="34299-114">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="34299-115">Eine Vertraulichkeitsbezeichnung oder eine Unterbezeichnung einer streng regulierten Bezeichnung, für die Verschlüsselung aktiviert ist und die über Co-Autor-Berechtigungen für die Microsoft 365-Gruppe des Teams verfügt.</span><span class="sxs-lookup"><span data-stu-id="34299-115">A sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Microsoft 365 group of the team.</span></span> <span data-ttu-id="34299-116">Benutzer wenden die Bezeichnung oder Unterbezeichnung über die Menüleistenoption **Vertraulichkeit** in Word, Excel und PowerPoint auf Dateien an, die im Abschnitt **Dateien** des Teams gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="34299-116">Users apply the label or sublabel to files stored in **Files** section of the team from the **Sensitivity** menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="34299-117">Hier sehen Sie die resultierende Konfiguration mit einer Vertraulichkeitsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="34299-117">Here is the resulting configuration with a sensitivity label.</span></span>

![Konfiguration des Szenarios eines sicheren Teams](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="34299-119">Sehen Sie sich dieses kurze Video an, um eine kurze Übersicht zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="34299-119">For a quick overview, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a> <span data-ttu-id="34299-120">Eine einseitige Zusammenfassung dieses Szenarios finden Sie auf dem [Poster für Teams für streng regulierte Daten](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf).</span><span class="sxs-lookup"><span data-stu-id="34299-120">For a 1-page summary of this scenario, see the [Teams for highly regulated data poster](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="34299-121">[![Poster für Teams für streng regulierte Daten](../media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="34299-121">[![Teams for highly regulated data poster](../media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="34299-122">Sie können dieses Poster auch im [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)- oder [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/Teams-Highly-Regulated-Data-Poster.pptx)-Format herunterladen und in den Formaten "Brief", "Legal" oder "Tabloid" (27,94 x 43,18 cm) ausdrucken.</span><span class="sxs-lookup"><span data-stu-id="34299-122">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/Teams-Highly-Regulated-Data-Poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>

## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a><span data-ttu-id="34299-123">Phase 1: Konfigurieren eines Teams für stark regulierte Daten</span><span class="sxs-lookup"><span data-stu-id="34299-123">Phase 1: Configure a team for highly regulated data</span></span>

<span data-ttu-id="34299-124">Die End-to-End-Konfiguration umfasst folgende Schritte:</span><span class="sxs-lookup"><span data-stu-id="34299-124">The end-to-end configuration consists of these steps:</span></span>

1. <span data-ttu-id="34299-125">Konfigurieren des Identitäts- und Gerätezugriffs.</span><span class="sxs-lookup"><span data-stu-id="34299-125">Configure identity and device access.</span></span>
2. <span data-ttu-id="34299-126">Erstellen eines privaten Teams.</span><span class="sxs-lookup"><span data-stu-id="34299-126">Create a private team.</span></span>
3. <span data-ttu-id="34299-127">Konfigurieren der zugrunde liegenden SharePoint-Website für zusätzliche Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="34299-127">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="34299-128">Erstellen Sie einer Aufbewahrungsbezeichnung und einer DLP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="34299-128">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="34299-129">Erstellen der Bezeichnung oder einer Unterbezeichnung der streng regulierten Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="34299-129">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="34299-130">Schritt 1: Konfigurieren des Identitäts- und Gerätezugriffs</span><span class="sxs-lookup"><span data-stu-id="34299-130">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="34299-131">Um den Zugriff auf das Team und dessen zugrunde liegende SharePoint-Website zu schützen, stellen Sie sicher, dass Sie [Identitäts- und Gerätezugriffsrichtlinien](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) und die [empfohlenen SharePoint Online-Zugriffsrichtlinien](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies) konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="34299-131">To protect access to the team and its underlying SharePoint site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the recommended [SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="34299-132">Schritt 2: Erstellen eines privaten Teams</span><span class="sxs-lookup"><span data-stu-id="34299-132">Step 2: Create a private team</span></span>

<span data-ttu-id="34299-133">Folgen Sie [diesen Anweisungen](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b), um ein privates Team zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="34299-133">Use [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private team.</span></span>

<span data-ttu-id="34299-134">Wenn Sie ein privates Team erstellen, gelten die folgenden Standardberechtigungen:</span><span class="sxs-lookup"><span data-stu-id="34299-134">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="34299-135">Die Microsoft 365-Gruppe für das Team (die Teamgruppe) verfügt über Gruppenbesitzer und Gruppenmitglieder.</span><span class="sxs-lookup"><span data-stu-id="34299-135">The Microsoft 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="34299-136">Für die zugrunde liegende SharePoint-Website für das Team (die Teamwebsite):</span><span class="sxs-lookup"><span data-stu-id="34299-136">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="34299-137">Die Websitesammlungsadministratoren werden für die Teamgruppenbesitzer konfiguriert</span><span class="sxs-lookup"><span data-stu-id="34299-137">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="34299-138">Für die Teamwebsite:</span><span class="sxs-lookup"><span data-stu-id="34299-138">For the Team Site:</span></span> 
    - <span data-ttu-id="34299-139">Die SharePoint-Gruppe der Teamwebsitebesitzer – mit der Berechtigungsstufe "Vollzugriff" – wird auf die Teamgruppenbesitzer festgelegt.</span><span class="sxs-lookup"><span data-stu-id="34299-139">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="34299-140">Die SharePoint-Gruppe der Teamwebsitemitglieder – mit der Berechtigungsstufe "Bearbeiten" – wird auf die Teamgruppenmitglieder festgelegt.</span><span class="sxs-lookup"><span data-stu-id="34299-140">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="34299-141">Die SharePoint-Gruppe "Teamwebsitebesucher" – mit der Berechtigungsstufe "Lesen" – enthält keine Gruppen oder Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="34299-141">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="34299-142">Die folgenden Standardberechtigungen gelten für die Teamwebsite.</span><span class="sxs-lookup"><span data-stu-id="34299-142">Here are the default permissions for the Team Site.</span></span>

![Die Standardberechtigungen der Teamwebsite](../media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="34299-144">Wenn Sie die SharePoint-Gruppe "\<Teamname > Besitzer" für die Berechtigungsstufe "Bearbeiten" anzeigen, wird "\<Teamname > Besitzer" nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="34299-144">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="34299-145">Die resultierenden Berechtigungen ermöglichen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="34299-145">The resulting permissions allow:</span></span>

- <span data-ttu-id="34299-146">Teamgruppenbesitzer können die Website verwalten und haben Vollzugriff auf die Websiteinhalte.</span><span class="sxs-lookup"><span data-stu-id="34299-146">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="34299-147">Teamgruppenmitglieder können Dateien auf der Website erstellen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="34299-147">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="34299-148">Die Verwaltung von Berechtigungen entspricht der Verwaltung von Teammitgliedern und -besitzern.</span><span class="sxs-lookup"><span data-stu-id="34299-148">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="34299-149">Nachfolgend sehen Sie die daraus resultierende Konfiguration bis zu diesem Punkt.</span><span class="sxs-lookup"><span data-stu-id="34299-149">Here’s the resulting configuration so far.</span></span>

![Schritt 2 der Konfiguration des Szenarios eines sicheren Teams](../media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="34299-151">Schritt 3: Konfigurieren der zugrunde liegenden SharePoint-Website für zusätzliche Sicherheit</span><span class="sxs-lookup"><span data-stu-id="34299-151">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="34299-152">Konfigurieren Sie diese Berechtigungseinstellungen auf der Teamwebsite.</span><span class="sxs-lookup"><span data-stu-id="34299-152">From the Team Site, configure these permission settings.</span></span>

1. <span data-ttu-id="34299-153">Klicken Sie in der Symbolleiste auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="34299-153">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="34299-154">Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.</span><span class="sxs-lookup"><span data-stu-id="34299-154">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="34299-155">Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus.</span><span class="sxs-lookup"><span data-stu-id="34299-155">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="34299-156">Deaktivieren Sie **Zugriffsanforderungen zulassen**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="34299-156">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="34299-157">Bei diesen Einstellungen ist die Möglichkeit, dass Teamgruppenmitglieder die Teamwebsite mit anderen Mitgliedern oder Nichtmitgliedern teilen, um den Zugriff auf die Teamwebsite anzufordern, deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="34299-157">With these settings, the ability for Team Group members to share the Team Site with other members or for non-members to request access to the Team Site is disabled.</span></span>

<span data-ttu-id="34299-158">Nachfolgend sehen Sie die daraus resultierende Konfiguration bis zu diesem Punkt.</span><span class="sxs-lookup"><span data-stu-id="34299-158">Here’s the resulting configuration so far.</span></span>

![Schritt 3 der Konfiguration des Szenarios eines sicheren Teams](../media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="34299-160">Schritt 4: Erstellen Sie einer Aufbewahrungsbezeichnung und einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="34299-160">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="34299-161">Verwenden Sie [diese Anleitungen](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp) für folgende Aktionen:</span><span class="sxs-lookup"><span data-stu-id="34299-161">Use [these instructions](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp) to:</span></span>

1. <span data-ttu-id="34299-162">Erstellen und Veröffentlichen einer Aufbewahrungsbezeichnung für stark regulierte Daten (sofern erforderlich).</span><span class="sxs-lookup"><span data-stu-id="34299-162">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="34299-163">Konfigurieren der Teamwebsite für die in Schritt 1 erstellte Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="34299-163">Configure the Team Site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="34299-164">Erstellen einer DLP-Richtlinie für stark regulierte Daten, die die in Schritt 2 erstellte Aufbewahrungsbezeichnung verwendet und Benutzer am Senden von Dateien an Ziele außerhalb der Organisation hindert.</span><span class="sxs-lookup"><span data-stu-id="34299-164">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization.</span></span> <span data-ttu-id="34299-165">Sie können die Richtlinie auch basierend auf [DLP Richtlinienvorlagen](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates) für zusätzliche Anforderungen konfigurieren, z. B. für Vorschriften aus dem Gesundheitswesen oder der Finanzbranche.</span><span class="sxs-lookup"><span data-stu-id="34299-165">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="34299-166">Nachfolgend sehen Sie die daraus resultierende Konfiguration bis zu diesem Punkt.</span><span class="sxs-lookup"><span data-stu-id="34299-166">Here’s the resulting configuration so far.</span></span>

![Schritt 4 der Konfiguration des Szenarios eines sicheren Teams](../media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-a-sensitivity-label-or-a-sublabel-of-the-highly-regulated-sensitivity-label"></a><span data-ttu-id="34299-168">Schritt 5: Erstellen einer Vertraulichkeitsbezeichnung oder einer Unterbezeichnung der streng regulierten Vertraulichkeitsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="34299-168">Step 5: Create a sensitivity label or a sublabel of the highly regulated sensitivity label</span></span>

<span data-ttu-id="34299-169">Im Gegensatz zu einer Vertraulichkeitsbezeichnung für streng regulierte Daten, die von jedem auf eine beliebige Datei angewendet werden kann, benötigt ein sicheres Team eine eigene Bezeichnung oder Unterbezeichnung, damit für Dateien, denen diese Bezeichnung oder Unterbezeichnung zugeordnet ist, Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="34299-169">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="34299-170">Die Dateien werden verschlüsselt, und die Verschlüsselung ist an die Dateien gebunden.</span><span class="sxs-lookup"><span data-stu-id="34299-170">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="34299-171">Die Dateien enthalten benutzerdefinierte Berechtigungen, sodass sie nur von Mitgliedern der Teamgruppe geöffnet werden können.</span><span class="sxs-lookup"><span data-stu-id="34299-171">Contain custom permissions so that only members of the Team Group can open it.</span></span>

<span data-ttu-id="34299-172">Um diese zusätzliche Sicherheitsstufe für die auf der Teamwebsite gespeicherten Dateien zu erreichen, müssen Sie eine neue Vertraulichkeitsbezeichnung konfigurieren, bei der es sich entweder um eine eigene Bezeichnung oder um eine Unterbezeichnung der allgemeinen Bezeichnung für stark regulierten Dateien handelt.</span><span class="sxs-lookup"><span data-stu-id="34299-172">To accomplish this additional level of security for files stored in the Team Site, you must configure a new sensitivity label that is either its own label a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="34299-173">Diese wird nur für Teamgruppenmitglieder in der Liste der Bezeichnungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="34299-173">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="34299-174">Verwenden Sie eine Vertraulichkeitsbezeichnung, wenn Sie nur eine kleine Anzahl von Bezeichnungen für die globale Nutzung und für einzelne private Teams benötigen.</span><span class="sxs-lookup"><span data-stu-id="34299-174">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="34299-175">Verwenden Sie eine Vertraulichkeitsunterbezeichnung, wenn Sie über eine große Anzahl von Bezeichnungen verfügen oder Bezeichnungen für private Teams unter der streng regulierten Bezeichnung organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="34299-175">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams under the highly regulated label.</span></span>

<span data-ttu-id="34299-176">[Verwenden Sie diese Anweisungen ](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) zum Konfigurieren einer separaten Bezeichnung oder einer Unterbezeichnung mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="34299-176">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="34299-177">Der Name der Bezeichnung enthält den Namen des Teams.</span><span class="sxs-lookup"><span data-stu-id="34299-177">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="34299-178">Die Verschlüsselung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="34299-178">Encryption is enabled</span></span>
- <span data-ttu-id="34299-179">Die Teamgruppe verfügt über Berechtigungen für die gemeinsame Dokumenterstellung.</span><span class="sxs-lookup"><span data-stu-id="34299-179">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="34299-180">Hier sehen Sie die resultierende Konfiguration mit der neuen Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="34299-180">Here’s the resulting configuration with the new label.</span></span>

![Schritt 5 der Konfiguration des Szenarios eines sicheren Teams](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="34299-182">Hier sehen Sie die Beziehung zwischen der Vertraulichkeitsbezeichnung und der Teamgruppe.</span><span class="sxs-lookup"><span data-stu-id="34299-182">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![Beziehung zwischen der Teamgruppe und den Bezeichnungsberechtigungen](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="34299-184">Wenn Sie die Vertraulichkeitsbezeichnung oder eine Unterbezeichnung für benutzerdefinierte Berechtigungen oder mit einem Ablaufdatum konfigurieren, können Sie die Datei nicht aus Microsoft Teams oder SharePoint öffnen.</span><span class="sxs-lookup"><span data-stu-id="34299-184">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint.</span></span> <span data-ttu-id="34299-185">Sie müssen eine Office-App verwenden.</span><span class="sxs-lookup"><span data-stu-id="34299-185">You must use an Office app.</span></span>
>

### <a name="custom-permissions"></a><span data-ttu-id="34299-186">Benutzerdefinierte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="34299-186">Custom permissions</span></span>

<span data-ttu-id="34299-187">Sie können auch benutzerdefinierte SharePoint-Websiteberechtigungen für die Teamwebsite und, falls erforderlich, die entsprechende Vertraulichkeitsbezeichnung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="34299-187">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="34299-188">Es folgen zwei Beispiele.</span><span class="sxs-lookup"><span data-stu-id="34299-188">Here are two examples.</span></span>

#### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="34299-189">Beispiel 1: Delegieren der SharePoint-Websiteverwaltung</span><span class="sxs-lookup"><span data-stu-id="34299-189">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="34299-190">Wenn der Teambesitzer keine SharePoint-Verwaltungsoberfläche hat oder die Verwaltung der Teamwebsite delegieren möchte, könnte er das Benutzerkonto eines SharePoint-Administrators zur Liste der Teambesitzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="34299-190">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="34299-191">Aber dann hat der SharePoint-Administrator Vollzugriff auf das Team und alle zugehörigen Ressourcen und wäre in der Lage, eine Datei mit angewendeter Vertraulichkeitsbezeichnung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34299-191">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="34299-192">Um diese Zuweisung von zu vielen Berechtigungen zu verhindern, fügen Sie das Benutzerkonto des SharePoint-Administrators der SharePoint-Gruppe "Teamwebsitebesitzer" in den erweiterten Berechtigungseinstellungen der Website hinzu.</span><span class="sxs-lookup"><span data-stu-id="34299-192">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="34299-193">Der SharePoint-Administrator kann die Website verwalten, aber ist nicht in der Lage, auf das Team und seine Ressourcen zuzugreifen oder die Dateien mit zugewiesenen Vertraulichkeitsbezeichnungen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34299-193">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="34299-194">Beispiel 2: Zulassen des schreibgeschützten Zugriffs auf Dateien mit Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="34299-194">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="34299-195">Wenn einige Mitarbeiter den Inhalt von Dateien mit Bezeichnungen in der Teamwebsite nur anzeigen müssen, fügen Sie die einzelnen Benutzerkonten zur</span><span class="sxs-lookup"><span data-stu-id="34299-195">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="34299-196">SharePoint-Gruppe "\<Teamname > Besucher" hinzu, die standardmäßig über die Berechtigungsstufe "Lesen" verfügt.</span><span class="sxs-lookup"><span data-stu-id="34299-196">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="34299-197">Die Vertraulichkeitsbezeichnung mit Leseberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="34299-197">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="34299-198">Hier sehen Sie die resultierenden Berechtigungen für die Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="34299-198">Here are the resulting permissions on the label.</span></span>

![Beispiel für benutzerdefinierte Berechtigungen zum Anzeigen von Dateien mit Bezeichnungen](../media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="34299-200">Die Websitebesucher können direkt auf die Teamwebsite zugreifen und die Inhalte von Dateien anzeigen, auf die die Unterbezeichnung angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="34299-200">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="34299-201">Da Sie aber keine Mitglieder der Teamgruppe sind, können sie nicht auf das Team oder die zugehörigen Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="34299-201">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>


## <a name="phase-2-drive-user-adoption-for-team-members"></a><span data-ttu-id="34299-202">Phase 2: Fördern der Benutzerakzeptanz für Teammitglieder</span><span class="sxs-lookup"><span data-stu-id="34299-202">Phase 2: Drive user adoption for team members</span></span>

<span data-ttu-id="34299-203">Wenn das Team aktiv ist, ist es an der Zeit, die Benutzerakzeptanz dieses Teams und dessen zusätzlicher Sicherheit für Teammitglieder zu fördern.</span><span class="sxs-lookup"><span data-stu-id="34299-203">With the team in place, it’s time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="34299-204">Schritt 1: Schulen der Benutzer</span><span class="sxs-lookup"><span data-stu-id="34299-204">Step 1: Train your users</span></span>

<span data-ttu-id="34299-205">Mitglieder der Teamgruppe können auf das Team und alle zugehörigen Ressourcen zugreifen, b. B. Chats, Besprechungen und andere Apps.</span><span class="sxs-lookup"><span data-stu-id="34299-205">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="34299-206">Wenn Sie mit Dateien aus dem Abschnitt **Dateien** eines Kanals arbeiten, müssen die Mitglieder der Teamgruppe den für das sichere Team erstellten Dateien die Vertraulichkeitsbezeichnung oder eine Unterbezeichnung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="34299-206">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="34299-207">Es folgt ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="34299-207">Here’s an example.</span></span>

![Beispiel für eine Bezeichnung, die auf eine Datei in einem sicheren Team angewendet wurde](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="34299-209">Wird die Bezeichnung auf eine Datei angewendet, ist diese abgesichert.</span><span class="sxs-lookup"><span data-stu-id="34299-209">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="34299-210">Mitglieder der Teamgruppe können sie in Teams öffnen und in Echtzeit zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="34299-210">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="34299-211">Sie wird verschlüsselt und umfasst die für die Teamgruppenmitglieder festgelegten Co-Autor-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="34299-211">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="34299-212">Wenn die Datei die Website verlässt und an einen böswilligen Benutzer weitergeleitet wird, lässt sich die Datei nur öffnen, und ihr Inhalt kann nur angezeigt werden, wenn die Anmeldeinformationen eines Benutzerkontos angegeben werden, das Mitglied der Teamgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="34299-212">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="34299-213">Schulen Sie Ihre Teammitglieder:</span><span class="sxs-lookup"><span data-stu-id="34299-213">Train your team members:</span></span>

- <span data-ttu-id="34299-214">Vermitteln Sie ihnen, wie wichtig es ist, das neue Team für Chats, Besprechungen, Dateien und andere Ressourcen der Teamwebsite zu nutzen und welche Auswirkungen ein Verlust streng regulierter Daten hat, z. B. rechtliche Konsequenzen, Bußgelder, Ransomware oder Verlust des Wettbewerbsvorteils.</span><span class="sxs-lookup"><span data-stu-id="34299-214">On the importance of using the new team for chats, meetings, files, and the other resources of the Team Site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="34299-215">So greifen Sie auf das Team zu.</span><span class="sxs-lookup"><span data-stu-id="34299-215">How to access the team.</span></span>
- <span data-ttu-id="34299-216">Erklären Sie, wie neue Dateien auf der Website erstellt und neue, lokal gespeicherte Dateien hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="34299-216">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="34299-217">Veranschaulichen Sie, wie durch die DLP-Richtlinie verhindert wird, dass Dateien extern freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="34299-217">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="34299-218">So beschriften Sie Dateien mit der Bezeichnung oder Unterbezeichnung des Teams.</span><span class="sxs-lookup"><span data-stu-id="34299-218">How to label files with the custom label or sublabel for the team.</span></span>
- <span data-ttu-id="34299-219">Veranschaulichen Sie, wie die Bezeichnung oder Unterbezeichnung Dateien schützt, auch wenn sie die Website verlassen.</span><span class="sxs-lookup"><span data-stu-id="34299-219">How the label or sublabel protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="34299-220">Diese Schulung sollte praktische Übungen umfassen, damit die Teammitglieder diese Funktionen und deren Ergebnisse ausprobieren können.</span><span class="sxs-lookup"><span data-stu-id="34299-220">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="34299-221">Schritt 2: Durchführen regelmäßiger Verwendungsprüfungen und Behandeln des Feedbacks der Teammitglieder.</span><span class="sxs-lookup"><span data-stu-id="34299-221">Step 2: Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="34299-222">In den Wochen nach der Schulung:</span><span class="sxs-lookup"><span data-stu-id="34299-222">In the weeks after training:</span></span>

- <span data-ttu-id="34299-223">Reagieren Sie umgehend auf Feedback von Teammitgliedern und optimieren Sie die Richtlinien und Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="34299-223">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="34299-224">Analysieren Sie die Verwendung der Website und vergleichen Sie sie mit den Erwartungen.</span><span class="sxs-lookup"><span data-stu-id="34299-224">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="34299-225">Sicherstellen, dass streng regulierte Dateien korrekt mit der eigens erstellten Vertraulichkeitsbezeichnung oder -unterbezeichnung gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="34299-225">Verify that highly regulated files have been properly labeled with the custom sensitivity label or sublabel.</span></span>

  <span data-ttu-id="34299-226">Sie können sehen, welchen Dateien eine Bezeichnung zugeordnet ist, indem Sie einen Ordner in SharePoint anzeigen und über die Option **Spalten ein-/ausblenden** > **Spalte hinzufügen** die Spalte **Vertraulichkeit** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="34299-226">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="34299-227">Ihre Benutzer bei Bedarf erneut schulen.</span><span class="sxs-lookup"><span data-stu-id="34299-227">Retrain your users as needed.</span></span>

## <a name="demonstrate-this-in-a-test-environment"></a><span data-ttu-id="34299-228">Dies in einer Testumgebung demonstrieren</span><span class="sxs-lookup"><span data-stu-id="34299-228">Demonstrate this in a test environment</span></span>

<span data-ttu-id="34299-229">Wenn Sie eine eigene Testumgebung zum Testen von Teams für sensible und streng vertrauliche Dateien erstellen möchten, lesen Sie [diese Anweisungen](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-team-for-files-in-a-dev-test-environment).</span><span class="sxs-lookup"><span data-stu-id="34299-229">To build out your own test environment to test teams for sensitive and highly confidential files, see [these instructions](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-team-for-files-in-a-dev-test-environment).</span></span> 

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)

## <a name="how-the-contoso-corporation-used-a-secure-team-for-a-top-secret-project"></a><span data-ttu-id="34299-231">Verwendung eines sicheren Teams für ein streng geheimes Projekt in der Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="34299-231">How the Contoso Corporation used a secure team for a top-secret project</span></span>

<span data-ttu-id="34299-232">Die Contoso Corporation ist ein fiktiver, aber repräsentativer globaler Mischkonzern.</span><span class="sxs-lookup"><span data-stu-id="34299-232">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="34299-233">Erfahren Sie, wie Contoso die Einführung eines [sicheren Teams](contoso-team-for-top-secret-project.md) für ein streng geheimes Projekt zur Entwicklung und Markteinführung einer neuen Reihe von Produkten und Dienstleistungen konfiguriert und vorangetrieben hat.</span><span class="sxs-lookup"><span data-stu-id="34299-233">See how Contoso configured and drove the adoption of a [secure team](contoso-team-for-top-secret-project.md) for a top secret project to develop and bring to market a new set of products and services.</span></span> 

## <a name="see-also"></a><span data-ttu-id="34299-234">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34299-234">See also</span></span>

[<span data-ttu-id="34299-235">SharePoint-Websites für streng regulierte Daten</span><span class="sxs-lookup"><span data-stu-id="34299-235">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="34299-236">Microsoft 365 Enterprise-Arbeitslasten und -Szenarien</span><span class="sxs-lookup"><span data-stu-id="34299-236">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="34299-237">[Microsoft 365-Produktivitätsbibliothek](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="34299-237">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="34299-238">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="34299-238">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
