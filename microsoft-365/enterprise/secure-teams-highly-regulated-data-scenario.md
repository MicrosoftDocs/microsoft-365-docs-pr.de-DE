---
title: Teams für streng regulierte Daten
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erstellen Sie ein sicheres Team zum Speichern Ihrer wertvollsten und vertraulichen Dateien.
ms.openlocfilehash: 5117d310ccd877a7377e6e538e7fba13daaad4ef
ms.sourcegitcommit: 80dc9ceb14e3eb3ae61b0fc2c8c3d73d564a7ef9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "37617263"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="95065-103">Teams für streng regulierte Daten</span><span class="sxs-lookup"><span data-stu-id="95065-103">Microsoft Teams for highly regulated data</span></span>

<span data-ttu-id="95065-104">Dieser Artikel enthält Empfehlungen und beschreibt die Schritte zum Konfigurieren eines privaten Teams in Microsoft Teams, das den Zugriff auf Teams-Features, z. B. Chats, Besprechungen und Dateien, auf die Mitglieder und Besitzer der Office 365-Gruppe für dieses Team beschränkt.</span><span class="sxs-lookup"><span data-stu-id="95065-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="95065-105">Neben dem privaten Zugriff, der auf der Office 365-Gruppe basiert, wird in diesem Artikel beschrieben, wie die zugrunde liegende private SharePoint-Teamwebsite, auf die Sie über den Abschnitt **Dateien** eines Teamkanals zugreifen können, für die zusätzliche Sicherheit konfiguriert wird, die für die Speicherung von streng regulierten Daten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="95065-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="95065-106">Auf dieser SharePoint-Teamwebsite können Sie Dateien, Seiten, einen freigegebenen Kalender, Aufgaben, ein Notizbuch und Listen speichern und gemeinsam bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="95065-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

<span data-ttu-id="95065-107">Die Elemente der Konfiguration für ein Team für streng regulierte Daten sind:</span><span class="sxs-lookup"><span data-stu-id="95065-107">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="95065-108">Ein privates Team mit einer entsprechenden Office 365-Gruppe, die über Benutzerkonten für Besitzer und Mitglieder verfügt.</span><span class="sxs-lookup"><span data-stu-id="95065-108">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="95065-109">Zusätzliche Sicherheit auf der zugrunde liegenden SharePoint-Website für das Team, die verhindert,</span><span class="sxs-lookup"><span data-stu-id="95065-109">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="95065-110">Dass Mitglieder der Website anderen Personen Zugriff gewähren.</span><span class="sxs-lookup"><span data-stu-id="95065-110">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="95065-111">Dass Nicht-Mitglieder der Website Zugriff auf die Website anfordern.</span><span class="sxs-lookup"><span data-stu-id="95065-111">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="95065-112">Eine Office 365-Aufbewahrungsbezeichnung für die zugrunde liegende SharePoint-Website, die automatisch auf neue Dateien auf der Website angewendet wird, als Standardmethode zum Definieren von Aufbewahrungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="95065-112">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="95065-113">Eine DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust), die anhand der Aufbewahrungsbezeichnung Benutzer daran hindert, Dateien für Empfänger außerhalb der Organisation freizugeben oder an diese zu senden.</span><span class="sxs-lookup"><span data-stu-id="95065-113">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="95065-114">Eine Office 365-Vertraulichkeitsbezeichnung oder eine Unterbezeichnung einer streng regulierten Bezeichnung, für die Verschlüsselung aktiviert ist und die über Co-Autor-Berechtigungen für die Office 365-Gruppe des Teams verfügt.</span><span class="sxs-lookup"><span data-stu-id="95065-114">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="95065-115">Benutzer wenden die Bezeichnung oder Unterbezeichnung über die Menüleistenoption "Vertraulichkeit" in Word, Excel und PowerPoint auf Dateien an, die im Abschnitt **Dateien** des Teams gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="95065-115">Users apply the label or sublabel to files stored in **Files** section of the team from the Sensitivity menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="95065-116">Hier sehen Sie die resultierende Konfiguration mit einer Vertraulichkeitsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="95065-116">Here is the resulting configuration with a sensitivity label.</span></span>

![Konfiguration des Szenarios eines sicheren Teams](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)
 
## <a name="configuration"></a><span data-ttu-id="95065-118">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="95065-118">Configuration</span></span>

<span data-ttu-id="95065-119">Die End-to-End-Konfiguration eines sicheren Teams umfasst folgende Schritte:</span><span class="sxs-lookup"><span data-stu-id="95065-119">The end-to-end configuration of a secure team consists of these steps:</span></span>

1. <span data-ttu-id="95065-120">Konfigurieren des Identitäts- und Gerätezugriffs.</span><span class="sxs-lookup"><span data-stu-id="95065-120">Configure identity and device access.</span></span>
2. <span data-ttu-id="95065-121">Erstellen eines privaten Teams.</span><span class="sxs-lookup"><span data-stu-id="95065-121">Create a team</span></span>
3. <span data-ttu-id="95065-122">Konfigurieren der zugrunde liegenden SharePoint-Website für zusätzliche Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="95065-122">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="95065-123">Erstellen Sie einer Aufbewahrungsbezeichnung und einer DLP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="95065-123">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="95065-124">Erstellen der Bezeichnung oder einer Unterbezeichnung der streng regulierten Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="95065-124">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="95065-125">Schritt 1: Konfigurieren des Identitäts- und Gerätezugriffs</span><span class="sxs-lookup"><span data-stu-id="95065-125">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="95065-126">Um den Zugriff auf das Team und dessen zugrunde liegende SharePoint-Website zu schützen, stellen Sie sicher, dass Sie [Identitäts- und Gerätezugriffsrichtlinien](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) und die [empfohlenen SharePoint Online-Zugriffsrichtlinien](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies) konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="95065-126">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the [recommended SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="95065-127">Schritt 2: Erstellen eines privaten Teams</span><span class="sxs-lookup"><span data-stu-id="95065-127">Step 2: Create a private team</span></span>

<span data-ttu-id="95065-128">Folgen Sie [diesen Anweisungen](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b), um ein privates Team zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="95065-128">Follow [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private SharePoint team site.</span></span>

<span data-ttu-id="95065-129">Wenn Sie ein privates Team erstellen, gelten die folgenden Standardberechtigungen:</span><span class="sxs-lookup"><span data-stu-id="95065-129">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="95065-130">Die Office 365-Gruppe für das Team (die Teamgruppe) verfügt über Gruppenbesitzer und Gruppenmitglieder.</span><span class="sxs-lookup"><span data-stu-id="95065-130">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="95065-131">Für die zugrunde liegende SharePoint-Website für das Team (die Teamwebsite):</span><span class="sxs-lookup"><span data-stu-id="95065-131">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="95065-132">Die Websitesammlungsadministratoren werden für die Teamgruppenbesitzer konfiguriert</span><span class="sxs-lookup"><span data-stu-id="95065-132">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="95065-133">Für die Teamwebsite:</span><span class="sxs-lookup"><span data-stu-id="95065-133">For the Team Site:</span></span> 
    - <span data-ttu-id="95065-134">Die SharePoint-Gruppe der Teamwebsitebesitzer – mit der Berechtigungsstufe "Vollzugriff" – wird auf die Teamgruppenbesitzer festgelegt.</span><span class="sxs-lookup"><span data-stu-id="95065-134">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="95065-135">Die SharePoint-Gruppe der Teamwebsitemitglieder – mit der Berechtigungsstufe "Bearbeiten" – wird auf die Teamgruppenmitglieder festgelegt.</span><span class="sxs-lookup"><span data-stu-id="95065-135">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="95065-136">Die SharePoint-Gruppe "Teamwebsitebesucher" – mit der Berechtigungsstufe "Lesen" – enthält keine Gruppen oder Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="95065-136">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="95065-137">Die folgenden Standardberechtigungen gelten für die Teamwebsite.</span><span class="sxs-lookup"><span data-stu-id="95065-137">Here are the default permissions for the Team Site.</span></span>

![Die Standardberechtigungen der Teamwebsite](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="95065-139">Wenn Sie die SharePoint-Gruppe "\<Teamname > Besitzer" für die Berechtigungsstufe "Bearbeiten" anzeigen, wird "\<Teamname > Besitzer" nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="95065-139">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="95065-140">Die resultierenden Berechtigungen ermöglichen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="95065-140">The resulting permissions allow:</span></span>

- <span data-ttu-id="95065-141">Teamgruppenbesitzer können die Website verwalten und haben Vollzugriff auf die Websiteinhalte.</span><span class="sxs-lookup"><span data-stu-id="95065-141">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="95065-142">Teamgruppenmitglieder können Dateien auf der Website erstellen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="95065-142">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="95065-143">Die Verwaltung von Berechtigungen entspricht der Verwaltung von Teammitgliedern und -besitzern.</span><span class="sxs-lookup"><span data-stu-id="95065-143">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="95065-144">Nachfolgend sehen Sie die daraus resultierende Konfiguration bis zu diesem Punkt.</span><span class="sxs-lookup"><span data-stu-id="95065-144">Here’s the resulting configuration so far.</span></span>

![Schritt 2 der Konfiguration des Szenarios eines sicheren Teams](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="95065-146">Schritt 3: Konfigurieren der zugrunde liegenden SharePoint-Website für zusätzliche Sicherheit</span><span class="sxs-lookup"><span data-stu-id="95065-146">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="95065-147">Konfigurieren Sie diese Berechtigungseinstellungen auf der Teamwebsite.</span><span class="sxs-lookup"><span data-stu-id="95065-147">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="95065-148">Klicken Sie in der Symbolleiste auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="95065-148">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="95065-149">Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.</span><span class="sxs-lookup"><span data-stu-id="95065-149">In the **Site permissions** pane,, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="95065-150">Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus.</span><span class="sxs-lookup"><span data-stu-id="95065-150">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="95065-151">Deaktivieren Sie **Zugriffsanforderungen zulassen**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="95065-151">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="95065-152">Bei diesen Einstellungen ist die Möglichkeit, dass Teamgruppenmitglieder die Teamwebsite mit anderen Mitgliedern oder Nichtmitgliedern teilen, um den Zugriff auf die Teamwebsite anzufordern, deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="95065-152">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

<span data-ttu-id="95065-153">Nachfolgend sehen Sie die daraus resultierende Konfiguration bis zu diesem Punkt.</span><span class="sxs-lookup"><span data-stu-id="95065-153">Here’s the resulting configuration so far.</span></span>

![Schritt 3 der Konfiguration des Szenarios eines sicheren Teams](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="95065-155">Schritt 4: Erstellen Sie einer Aufbewahrungsbezeichnung und einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="95065-155">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="95065-156">Verwenden Sie [diese Anleitungen](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) für folgende Aktionen:</span><span class="sxs-lookup"><span data-stu-id="95065-156">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="95065-157">Erstellen und Veröffentlichen einer Aufbewahrungsbezeichnung für stark regulierte Daten (sofern erforderlich).</span><span class="sxs-lookup"><span data-stu-id="95065-157">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="95065-158">Konfigurieren der Teamwebsite für die in Schritt 1 erstellte Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="95065-158">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="95065-159">Erstellen einer DLP-Richtlinie für stark regulierte Daten, die die in Schritt 2 erstellte Aufbewahrungsbezeichnung verwendet und Benutzer am Senden von Dateien an Ziele außerhalb der Organisation hindert.</span><span class="sxs-lookup"><span data-stu-id="95065-159">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span> <span data-ttu-id="95065-160">Sie können die Richtlinie auch basierend auf [DLP Richtlinienvorlagen](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates) für zusätzliche Anforderungen konfigurieren, z. B. für Vorschriften aus dem Gesundheitswesen oder der Finanzbranche.</span><span class="sxs-lookup"><span data-stu-id="95065-160">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="95065-161">Nachfolgend sehen Sie die daraus resultierende Konfiguration bis zu diesem Punkt.</span><span class="sxs-lookup"><span data-stu-id="95065-161">Here’s the resulting configuration so far.</span></span>

![Schritt 4 der Konfiguration des Szenarios eines sicheren Teams](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a><span data-ttu-id="95065-163">Schritt 5: Erstellen der Bezeichnung oder einer Unterbezeichnung der streng regulierten Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="95065-163">Step 5: Create the label or a sublabel of the highly regulated label</span></span>

<span data-ttu-id="95065-164">Im Gegensatz zu einer Vertraulichkeitsbezeichnung für streng regulierte Daten, die von jedem auf eine beliebige Datei angewendet werden kann, benötigt ein sicheres Team eine eigene Bezeichnung oder Unterbezeichnung, damit für Dateien, denen diese Bezeichnung oder Unterbezeichnung zugeordnet ist, Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="95065-164">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="95065-165">Die Dateien werden verschlüsselt, und die Verschlüsselung ist an die Dateien gebunden.</span><span class="sxs-lookup"><span data-stu-id="95065-165">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="95065-166">Die Dateien enthalten benutzerdefinierte Berechtigungen, sodass sie nur von Mitgliedern der Teamgruppe geöffnet werden können.</span><span class="sxs-lookup"><span data-stu-id="95065-166">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="95065-167">Um diese zusätzliche Sicherheitsstufe für die auf der Teamwebsite gespeicherten Dateien zu erreichen, müssen Sie eine neue Vertraulichkeitsbezeichnung konfigurieren, bei der es sich entweder um eine eigene Bezeichnung oder um eine Unterbezeichnung der allgemeinen Bezeichnung für stark regulierten Dateien handelt.</span><span class="sxs-lookup"><span data-stu-id="95065-167">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="95065-168">Diese wird nur für Teamgruppenmitglieder in der Liste der Bezeichnungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="95065-168">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="95065-169">Verwenden Sie eine Vertraulichkeitsbezeichnung, wenn Sie nur eine kleine Anzahl von Bezeichnungen für die globale Nutzung und für einzelne private Teams benötigen.</span><span class="sxs-lookup"><span data-stu-id="95065-169">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="95065-170">Verwenden Sie eine Vertraulichkeitsunterbezeichnung, wenn Sie über eine große Anzahl von Bezeichnungen verfügen oder Bezeichnungen für private Teams unter der streng regulierten Bezeichnung organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="95065-170">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams the under the highly regulated label.</span></span>

<span data-ttu-id="95065-171">[Verwenden Sie diese Anweisungen ](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) zum Konfigurieren einer separaten Bezeichnung oder einer Unterbezeichnung mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="95065-171">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="95065-172">Der Name der Bezeichnung enthält den Namen des Teams.</span><span class="sxs-lookup"><span data-stu-id="95065-172">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="95065-173">Die Verschlüsselung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="95065-173">Encryption is enabled.</span></span>
- <span data-ttu-id="95065-174">Die Teamgruppe verfügt über Berechtigungen für die gemeinsame Dokumenterstellung.</span><span class="sxs-lookup"><span data-stu-id="95065-174">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="95065-175">Hier sehen Sie die resultierende Konfiguration mit der neuen Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="95065-175">Here’s the resulting configuration with the new label.</span></span>

![Schritt 5 der Konfiguration des Szenarios eines sicheren Teams](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="95065-177">Hier sehen Sie die Beziehung zwischen der Vertraulichkeitsbezeichnung und der Teamgruppe.</span><span class="sxs-lookup"><span data-stu-id="95065-177">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![Beziehung zwischen der Teamgruppe und den Bezeichnungsberechtigungen](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="95065-179">Wenn Sie die Vertraulichkeitsbezeichnung oder eine Unterbezeichnung für benutzerdefinierte Berechtigungen oder mit einem Ablaufdatum konfigurieren, können Sie die Datei nicht aus Microsoft Teams oder SharePoint Online öffnen.</span><span class="sxs-lookup"><span data-stu-id="95065-179">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint Online.</span></span> <span data-ttu-id="95065-180">Sie müssen eine Office-App verwenden.</span><span class="sxs-lookup"><span data-stu-id="95065-180">You must use an Office app.</span></span>
>

## <a name="using-the-team-and-a-sensitivity-label"></a><span data-ttu-id="95065-181">Verwenden des Teams und einer Vertraulichkeitsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="95065-181">Using the team and a sensitivity label</span></span>

<span data-ttu-id="95065-182">Mitglieder der Teamgruppe können auf das Team und alle zugehörigen Ressourcen zugreifen, b. B. Chats, Besprechungen und andere Apps.</span><span class="sxs-lookup"><span data-stu-id="95065-182">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="95065-183">Wenn Sie mit Dateien aus dem Abschnitt **Dateien** eines Kanals arbeiten, müssen die Mitglieder der Teamgruppe den für das sichere Team erstellten Dateien die Vertraulichkeitsbezeichnung oder eine Unterbezeichnung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="95065-183">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="95065-184">Es folgt ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="95065-184">Here’s an example.</span></span>

![Beispiel für eine Bezeichnung, die auf eine Datei in einem sicheren Team angewendet wurde](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="95065-186">Wird die Bezeichnung auf eine Datei angewendet, ist diese abgesichert.</span><span class="sxs-lookup"><span data-stu-id="95065-186">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="95065-187">Mitglieder der Teamgruppe können sie in Teams öffnen und in Echtzeit zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="95065-187">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="95065-188">Sie wird verschlüsselt und umfasst die für die Teamgruppenmitglieder festgelegten Co-Autor-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="95065-188">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="95065-189">Wenn die Datei die Website verlässt und an einen böswilligen Benutzer weitergeleitet wird, lässt sich die Datei nur öffnen, und ihr Inhalt kann nur angezeigt werden, wenn die Anmeldeinformationen eines Benutzerkontos angegeben werden, das Mitglied der Teamgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="95065-189">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="95065-190">Sie können sehen, welchen Dateien eine Bezeichnung zugeordnet ist, indem Sie einen Ordner in SharePoint Online anzeigen und über die Option **Spalten ein-/ausblenden** > **Spalte hinzufügen** die Spalte **Vertraulichkeit** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="95065-190">You can see which files have a label assigned by viewing a folder in SharePoint Online and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

## <a name="custom-permissions"></a><span data-ttu-id="95065-191">Benutzerdefinierte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="95065-191">Custom permissions</span></span>

<span data-ttu-id="95065-192">Sie können auch benutzerdefinierte SharePoint-Websiteberechtigungen für die Teamwebsite und, falls erforderlich, die entsprechende Vertraulichkeitsbezeichnung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="95065-192">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="95065-193">Es folgen zwei Beispiele.</span><span class="sxs-lookup"><span data-stu-id="95065-193">Here are two examples.</span></span>

### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="95065-194">Beispiel 1: Delegieren der SharePoint-Websiteverwaltung</span><span class="sxs-lookup"><span data-stu-id="95065-194">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="95065-195">Wenn der Teambesitzer keine SharePoint-Verwaltungsoberfläche hat oder die Verwaltung der Teamwebsite delegieren möchte, könnte er das Benutzerkonto eines SharePoint-Administrators zur Liste der Teambesitzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="95065-195">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="95065-196">Aber dann hat der SharePoint-Administrator Vollzugriff auf das Team und alle zugehörigen Ressourcen und wäre in der Lage, eine Datei mit angewendeter Vertraulichkeitsbezeichnung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="95065-196">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="95065-197">Um diese Zuweisung von zu vielen Berechtigungen zu verhindern, fügen Sie das Benutzerkonto des SharePoint-Administrators der SharePoint-Gruppe "Teamwebsitebesitzer" in den erweiterten Berechtigungseinstellungen der Website hinzu.</span><span class="sxs-lookup"><span data-stu-id="95065-197">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="95065-198">Der SharePoint-Administrator kann die Website verwalten, aber ist nicht in der Lage, auf das Team und seine Ressourcen zuzugreifen oder die Dateien mit zugewiesenen Vertraulichkeitsbezeichnungen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="95065-198">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="95065-199">Beispiel 2: Zulassen des schreibgeschützten Zugriffs auf Dateien mit Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="95065-199">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="95065-200">Wenn einige Mitarbeiter den Inhalt von Dateien mit Bezeichnungen in der Teamwebsite nur anzeigen müssen, fügen Sie die einzelnen Benutzerkonten zur</span><span class="sxs-lookup"><span data-stu-id="95065-200">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="95065-201">SharePoint-Gruppe "\<Teamname > Besucher" hinzu, die standardmäßig über die Berechtigungsstufe "Lesen" verfügt.</span><span class="sxs-lookup"><span data-stu-id="95065-201">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="95065-202">Die Vertraulichkeitsbezeichnung mit Leseberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="95065-202">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="95065-203">Hier sehen Sie die resultierenden Berechtigungen für die Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="95065-203">Here are the resulting permissions on the label.</span></span>

![Beispiel für benutzerdefinierte Berechtigungen zum Anzeigen von Dateien mit Bezeichnungen](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="95065-205">Die Websitebesucher können direkt auf die Teamwebsite zugreifen und die Inhalte von Dateien anzeigen, auf die die Unterbezeichnung angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="95065-205">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="95065-206">Da Sie aber keine Mitglieder der Teamgruppe sind, können sie nicht auf das Team oder die zugehörigen Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="95065-206">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="95065-207">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95065-207">See also</span></span>

[<span data-ttu-id="95065-208">SharePoint-Websites für streng regulierte Daten</span><span class="sxs-lookup"><span data-stu-id="95065-208">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="95065-209">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="95065-209">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
