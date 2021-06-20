---
title: Erstellen von Teamwebsites – Entwicklungsumgebung für eine politische Kampagne
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Zusammenfassung: Informationen zum Erstellen von öffentlichen, privaten, vertraulichen und streng vertraulichen SharePoint Online-Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fcba6e2f3939115d6dfbaae80d322246bdeadee9
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029897"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="ff64f-103">Erstellen von Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne</span><span class="sxs-lookup"><span data-stu-id="ff64f-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ff64f-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="ff64f-104">**Applies to**</span></span>

- [<span data-ttu-id="ff64f-105">Microsoft Defender für Office 365 – Plan 2</span><span class="sxs-lookup"><span data-stu-id="ff64f-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="ff64f-106">**Zusammenfassung:** Informationen zum Erstellen von öffentlichen, privaten, vertraulichen und streng vertraulichen SharePoint Online-Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne.</span><span class="sxs-lookup"><span data-stu-id="ff64f-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span>

<span data-ttu-id="ff64f-p101">Verwenden Sie die Schritte in diesem Artikel zum Erstellen einer Entwicklungs-/Testumgebung mit vier verschiedenen Typen von SharePoint Online-Teamwebsites für die Lösung [Microsoft-Sicherheitsanleitungen für politische Kampagnen, gemeinnützige Organisationen und andere agile Organisationen](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). Diese Websites werden im Thema 10 **SharePoint und OneDrive for Business** detailliert erläutert.</span><span class="sxs-lookup"><span data-stu-id="ff64f-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="ff64f-109">Phase 1: Erstellen der Entwicklungs-/Testumgebung für eine politische Kampagne</span><span class="sxs-lookup"><span data-stu-id="ff64f-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="ff64f-110">Befolgen Sie zunächst die Anweisungen unter [Konfigurieren von Gruppen und Benutzern für eine politische Kampagne in einer Entwicklungs-/Testumgebung](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md), um Ihre Abonnements, Benutzer und Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff64f-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="ff64f-111">Phase 2: Erstellen von Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="ff64f-111">Phase 2: Create labels</span></span>

<span data-ttu-id="ff64f-112">In dieser Phase erstellen Sie die Bezeichnungen für die verschiedenen Sicherheitsstufen für Dokumentordner für SharePoint Online-Teamwebsites.</span><span class="sxs-lookup"><span data-stu-id="ff64f-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="ff64f-p102">Melden Sie sich bei Bedarf beim Microsoft 365 Admin Center (<https://admin.microsoft.com>) mit den Anmeldeinformationen des globalen Administratorkontos Ihres Testabonnements an. Hilfe finden Sie unter [Wo Sie sich bei Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)anmelden können.</span><span class="sxs-lookup"><span data-stu-id="ff64f-p102">If needed, sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) with the credentials of the global administrator account of your trial subscription. For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="ff64f-115">Klicken Sie auf der **Startseite**, auf der Sie beginnen, auf **Alle anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-115">From the **Home** page where you start, click **Show all**.</span></span> <span data-ttu-id="ff64f-116">Klicken Sie im **Admin Center** angezeigten Abschnitt auf **Compliance**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-116">In the **Admin centers** section that appears, click **Compliance**.</span></span>

3. <span data-ttu-id="ff64f-117">Wechseln Sie im Microsoft 365 Compliance Center auf der **Startseite** zum **Lösungen** Abschnitt \> **Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-117">From the **Home** page of the Microsoft 365 compliance center, go to the **Solutions** section \> **Information protection**.</span></span> <span data-ttu-id="ff64f-118">Um direkt zur Seite **Information Protection** zu wechseln, verwenden Sie <https://compliance.microsoft.com//informationprotection>.</span><span class="sxs-lookup"><span data-stu-id="ff64f-118">To go directly to the **Information protection** page, use <https://compliance.microsoft.com//informationprotection>.</span></span>

4. <span data-ttu-id="ff64f-119">Überprüfen Sie auf der Seite **Information Protection**, ob das **Bezeichnungs**-Tag ausgewählt ist, und klicken Sie dann auf das ![Symbol "Bezeichnung erstellen",](../../media/m365-cc-sc-create-icon.png) **Bezeichnung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-119">On the **Information protection** page, verify that the **Label** tag is selected, and then click  ![Create a label icon](../../media/m365-cc-sc-create-icon.png) **Create a label**.</span></span>

5. <span data-ttu-id="ff64f-120">Der Assistent **Neue Vertraulichkeitsbezeichnung** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ff64f-120">The **New sensitivity label** wizard opens.</span></span> <span data-ttu-id="ff64f-121">Geben Sie im Schritt **Name & Description** die folgenden Werte ein:</span><span class="sxs-lookup"><span data-stu-id="ff64f-121">On the **Name & description** step, enter the following values:</span></span>
   - <span data-ttu-id="ff64f-122">**Name**: Geben Sie **interne** ein.</span><span class="sxs-lookup"><span data-stu-id="ff64f-122">**Name**: Type **Internal**.</span></span>
   - <span data-ttu-id="ff64f-123">**Anzeigename**</span><span class="sxs-lookup"><span data-stu-id="ff64f-123">**Display name**</span></span>
   - <span data-ttu-id="ff64f-124">**Beschreibung für Benutzer**</span><span class="sxs-lookup"><span data-stu-id="ff64f-124">**Description for users**</span></span>

   <span data-ttu-id="ff64f-125">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-125">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="ff64f-126">Klicken Sie im Bereich **Bezeichnungseinstellungen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-126">On the **Label settings** pane, click **Next**.</span></span>

7. <span data-ttu-id="ff64f-127">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnung erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-127">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

8. <span data-ttu-id="ff64f-128">Wiederholen Sie die Schritte 5 bis 8 für diese zusätzlichen Bezeichnungen:</span><span class="sxs-lookup"><span data-stu-id="ff64f-128">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="ff64f-129">Private</span><span class="sxs-lookup"><span data-stu-id="ff64f-129">Private</span></span>
   - <span data-ttu-id="ff64f-130">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="ff64f-130">Sensitive</span></span>
   - <span data-ttu-id="ff64f-131">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="ff64f-131">Highly Confidential</span></span>

9. <span data-ttu-id="ff64f-132">Klicken Sie im Bereich **Startseite > Bezeichnungen** auf **Bezeichnungen veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-132">From the **Home > Labels** pane, click **Publish labels**.</span></span>

10. <span data-ttu-id="ff64f-133">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Zu veröffentlichende Bezeichnungen wählen**</span><span class="sxs-lookup"><span data-stu-id="ff64f-133">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

11. <span data-ttu-id="ff64f-134">Klicken Sie im Bereich **Choose labels** (Bezeichnungen auswählen) auf **Hinzufügen**, wählen Sie alle vier Bezeichnungen aus.</span><span class="sxs-lookup"><span data-stu-id="ff64f-134">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

12. <span data-ttu-id="ff64f-135">Klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-135">Click **Done**.</span></span>

13. <span data-ttu-id="ff64f-136">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-136">On the **Choose labels to publish** pane, click **Next**.</span></span>

14. <span data-ttu-id="ff64f-137">Klicken Sie im Bereich **Speicherorte auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-137">On the **Choose locations** pane, click **Next**.</span></span>

15. <span data-ttu-id="ff64f-138">Geben Sie im Bereich **Richtlinie benennen\*\*\*\*Kampagne** unter **Name** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-138">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

16. <span data-ttu-id="ff64f-139">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnungen veröffentlichen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-139">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="ff64f-140">Phase 3: Erstellen von SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="ff64f-140">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="ff64f-141">In dieser Phase werden SharePoint Online-Teamwebsites für Ihre politische Kampagne entsprechend den vier Typen von SharePoint Online-Teamwebsites erstellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ff64f-141">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="ff64f-142">Kampagnen-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="ff64f-142">Campaign wide team site</span></span>

<span data-ttu-id="ff64f-143">Führen Sie folgende Schritte aus, um eine öffentliche SharePoint Online-Basis-Teamwebsite zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="ff64f-143">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="ff64f-144">Verwenden Sie, falls erforderlich, einen Browser auf Ihrem lokalen Computer, und melden Sie sich mit Ihrem globalen Administratorkonto beim Admin Center (<https://admin.microsoft.com>) an.</span><span class="sxs-lookup"><span data-stu-id="ff64f-144">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="ff64f-145">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-145">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="ff64f-146">Klicken Sie in der neuen Registerkarte **SharePoint** in Ihrem Browser auf **+ Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-146">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="ff64f-147">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-147">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="ff64f-148">Geben Sie unter **Websitename** den Namen **Kampagne** ein. </span><span class="sxs-lookup"><span data-stu-id="ff64f-148">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="ff64f-149">Geben Sie unter **Beschreibung der Teamwebsite** den Text **SharePoint-Website für die gesamte Kampagne** ein.</span><span class="sxs-lookup"><span data-stu-id="ff64f-149">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="ff64f-150">Wählen Sie unter **Datenschutzeinstellungen** die Option **Öffentlich - Alle Benutzer in der Organisation können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-150">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="ff64f-151">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-151">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="ff64f-152">Konfigurieren Sie anschließend den Ordner „Dokumente“ der Kampagnen-Teamwebsite für die Bezeichnung „Intern“.</span><span class="sxs-lookup"><span data-stu-id="ff64f-152">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="ff64f-153">Klicken Sie auf der Registerkarte **Kampagne – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-153">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="ff64f-154">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-154">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="ff64f-155">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-155">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="ff64f-156">Wählen Sie unter **Einstellungen –Bezeichnung anwenden** die Option **Intern**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-156">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="ff64f-157">Teamwebsite für Kampagnenprojekt 1</span><span class="sxs-lookup"><span data-stu-id="ff64f-157">Campaign project 1 team site</span></span>

<span data-ttu-id="ff64f-158">Führen Sie die folgenden Schritte durch, um eine private SharePoint Online-Basis-Teamwebsite für ein Projekt innerhalb der Kampagne zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="ff64f-158">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="ff64f-159">Verwenden Sie, falls erforderlich, einen Browser auf Ihrem lokalen Computer, und melden Sie sich mit Ihrem globalen Administratorkonto beim Admin Center (<https://admin.microsoft.com>) an.</span><span class="sxs-lookup"><span data-stu-id="ff64f-159">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="ff64f-160">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-160">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="ff64f-161">Klicken Sie in der neuen Registerkarte **SharePoint** in Ihrem Browser auf **+ Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-161">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="ff64f-162">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-162">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="ff64f-163">Geben Sie unter **Websitename** den Namen **Kampagnenprojekt 1** ein. </span><span class="sxs-lookup"><span data-stu-id="ff64f-163">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="ff64f-164">Geben Sie unter **Beschreibung der Teamwebsite** den Text **SharePoint-Website für das Kampagnenprojekt 1** ein.</span><span class="sxs-lookup"><span data-stu-id="ff64f-164">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="ff64f-165">Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-165">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="ff64f-166">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-166">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="ff64f-167">Konfigurieren Sie anschließend den Ordner „Dokumente“ der Teamwebsite für Kampagnenprojekt 1 für die Bezeichnung „Privat“.</span><span class="sxs-lookup"><span data-stu-id="ff64f-167">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="ff64f-168">Klicken Sie auf der Registerkarte **Kampagnenprojekt 1 – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-168">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="ff64f-169">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-169">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="ff64f-170">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-170">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="ff64f-171">Wählen Sie unter **Einstellungen – Bezeichnung anwenden** die Option **Privat**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-171">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="ff64f-172">Kampagnenmarketing-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="ff64f-172">Campaign marketing team site</span></span>

<span data-ttu-id="ff64f-173">Führen Sie die folgenden Schritte durch, um eine isolierte, vertrauliche SharePoint-Teamwebsite für Kampagnenmarketingressourcen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="ff64f-173">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="ff64f-174">Melden Sie sich auf Ihrem lokalen Computer über einen Browser mit Ihrem globalen Administratorkonto beim Admin Center (<https://admin.microsoft.com>) an.</span><span class="sxs-lookup"><span data-stu-id="ff64f-174">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="ff64f-175">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-175">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="ff64f-176">Klicken Sie in der neuen Registerkarte **SharePoint** in Ihrem Browser auf **+ Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-176">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="ff64f-177">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-177">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="ff64f-178">Geben Sie unter **Name der Teamwebsite** den Namen **Kampagnenmarketing** ein.</span><span class="sxs-lookup"><span data-stu-id="ff64f-178">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="ff64f-179">Geben Sie unter **Beschreibung der Teamwebsite** den Text **SharePoint-Website für Kampagnenmarketing (vertraulich)** ein.</span><span class="sxs-lookup"><span data-stu-id="ff64f-179">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="ff64f-180">Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-180">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="ff64f-181">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-181">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="ff64f-182">Klicken Sie auf der neuen Registerkarte **Kampagnenmarketing** in Ihrem Browser auf der Symbolleiste auf das Symbol „Einstellungen“, und klicken Sie dann auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-182">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="ff64f-183">Klicken Sie im Bereich **Websiteberechtigungen** auf **Erweiterte Berechtigungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-183">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="ff64f-184">Klicken Sie auf der neuen Registerkarte **Berechtigungen** in Ihrem Browser auf **Einstellungen für Zugriffsrechteanforderungen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-184">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="ff64f-185">Deaktivieren Sie im Dialogfeld **Einstellungen für Zugriffsrechteanforderungen** die Kontrollkästchen **Mitgliedern das Freigeben der Website sowie einzelner Dateien und Ordner erlauben** und **Mitgliedern das Einladen von anderen zur Websitemitglieder-Gruppe erlauben**, geben Sie in **Alle Zugriffsanforderungen senden** den Text **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-185">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="ff64f-186">Klicken Sie in der Liste auf **Kampagnenmarketingmitglieder**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-186">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="ff64f-187">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-187">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="ff64f-188">Geben Sie im Dialogfeld **Freigeben** **Senior-Mitarbeiter und strategische Mitarbeiter** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-188">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="ff64f-189">Wiederholen Sie die Schritte 14 und 15 für die Gruppe **Analytiker** und das Benutzerkonto **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-189">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="ff64f-190">Klicken Sie auf die Schaltfläche „Zurück“ in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="ff64f-190">Click the back button on your browser.</span></span>

18. <span data-ttu-id="ff64f-191">Klicken Sie in der Liste auf **Kampagnenmarketingbesitzer**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-191">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="ff64f-192">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-192">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="ff64f-193">Geben Sie im Dialogfeld **Freigeben** **IT-Mitarbeiter** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-193">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="ff64f-194">Klicken Sie auf die Schaltfläche „Zurück“ in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="ff64f-194">Click the back button on your browser.</span></span>

22. <span data-ttu-id="ff64f-195">Schließen Sie die Registerkarte **Benutzer und Gruppen** in Ihrem Browser, klicken Sie auf die Registerkarte **Kampagnenmarketing – Startseite** in Ihrem Browser, und schließen Sie dann den Bereich **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-195">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="ff64f-196">Nachfolgend finden Sie die Ergebnisse der Konfiguration von Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="ff64f-196">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="ff64f-197">Die SharePoint-Gruppe **Kampagnenmarketingmitglieder** enthält nur die Gruppen **Senior-Mitarbeiter und strategische Mitarbeiter** (mit den Candidate-, ChiefOfStaff- und die Strategic1-Benutzerkonten), **Kampagnenmarketing** (mit dem globalen Administratorkonto), **Analytiker** (mit dem DataScientist1-Benutzerkonto), und das **Regular1**-Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="ff64f-197">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="ff64f-198">Die SharePoint-Gruppe **Kampagnenmarketing – Besitzer** enthält nur die Gruppe **IT-Mitarbeiter** (nur mit den ITAdmin1- und ITAdmin2-Benutzerkonten).</span><span class="sxs-lookup"><span data-stu-id="ff64f-198">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="ff64f-199">Die SharePoint-Gruppe **Kampagnenmarketing – Besucher** enthält keine Gruppen oder Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="ff64f-199">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="ff64f-200">Mitglieder können keine Berechtigungen auf Websiteebene ändern (dies kann nur von Mitgliedern der Gruppe **Kampagnenmarketing – Besitzer** ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="ff64f-200">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="ff64f-201">Andere Benutzerkonten können nicht auf die Website oder die zugehörigen Ressourcen zugreifen, Sie können jedoch Zugriff auf die Website anfordern. Dabei wird eine E-Mail an das Postfach des ITAdmin1-Benutzerkontos gesendet.</span><span class="sxs-lookup"><span data-stu-id="ff64f-201">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="ff64f-202">Konfigurieren Sie anschließend den Ordner „Dokumente“ der Kampagnenmarketing-Teamwebsite für die Bezeichnung „Vertraulich“.</span><span class="sxs-lookup"><span data-stu-id="ff64f-202">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="ff64f-203">Klicken Sie auf der Registerkarte **Kampagnenmarketing – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-203">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="ff64f-204">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-204">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="ff64f-205">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-205">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="ff64f-206">Wählen Sie unter **Einstellungen – Bezeichnung anwenden** die Option **Vertraulich**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-206">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="ff64f-p106">Konfigurieren Sie als Nächstes eine Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP), die Benutzer benachrichtigt, wenn sie ein Dokument auf einer SharePoint Online-Teamwebsite mit der Bezeichnung „Vertraulich“ außerhalb der Organisation freigeben. Diese DLP-Richtlinie gilt für Ressourcen auf der Kampagnenmarketingwebsite.</span><span class="sxs-lookup"><span data-stu-id="ff64f-p106">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="ff64f-209">Klicken Sie in der Registerkarte **Microsoft Office Home** des Browsers auf die Kachel **Security & Compliance**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-209">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="ff64f-210">Klicken Sie auf der neuen Registerkarte **Security & Compliance** in Ihrem Browser auf **Verhinderung von Datenverlust > Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-210">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="ff64f-211">Klicken Sie im Bereich **Verhinderung von Datenverlust** auf **+ Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-211">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="ff64f-212">Klicken Sie im Bereich **Mit einer Vorlage beginnen oder eine benutzerdefinierte Richtlinie erstellen** auf **Benutzerdefiniert**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-212">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="ff64f-213">Geben Sie im Bereich **Ihre Richtlinie benennen** den Namen **Bezeichnung „Vertraulich" - SharePoint Online-Teamwebsites** bei **Name** ein, und klicken Sie dann auf **Weiter**</span><span class="sxs-lookup"><span data-stu-id="ff64f-213">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="ff64f-214">Klicken Sie im Bereich **Speicherorte auswählen** auf **Bestimmte Speicherorte auswählen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-214">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="ff64f-215">Deaktivieren Sie in der Liste der Speicherorte **Exchange-E-Mail** und **OneDrive-Konten**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-215">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="ff64f-216">Klicken Sie im Bereich **Typen von vertraulichen Informationen anpassen, die geschützt werden sollen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-216">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="ff64f-217">In der **wählen Sie die Typen der Inhalte zum Schutz** Bereich, klicken Sie auf **hinzufügen** im Dropdown-Listenfeld, und klicken Sie dann auf **Etiketten**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-217">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="ff64f-218">Klicken Sie im Bereich **Bezeichnungen** auf **+ Hinzufügen**, wählen Sie die Bezeichnung **Vertraulich** aus, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-218">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="ff64f-219">Klicken Sie im Bereich **Typen des zu schützenden Inhalts auswählen** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-219">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="ff64f-220">Klicken Sie im Bereich **Customize the types of sensitive info you want to protect** (Anpassen der Typen an vertraulichen Informationen, die Sie schützen möchten) auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-220">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="ff64f-221">Klicken Sie im Bereich **What do you want to do if we detect sensitive info?** (Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?) auf **Customize the tip and email** (Den Tipp und die E-Mail anpassen).</span><span class="sxs-lookup"><span data-stu-id="ff64f-221">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="ff64f-222">Klicken Sie im Bereich **Customize policy tips and email notifications** (Anpassen der Richtlinientipps und der E-Mail-Benachrichtigungen) auf **Customize the policy tip text** (Den Tipptext der Richtlinie als nächstes anpassen).</span><span class="sxs-lookup"><span data-stu-id="ff64f-222">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="ff64f-223">Geben Sie Folgendes in das Textfeld ein, oder fügen Sie es ein:</span><span class="sxs-lookup"><span data-stu-id="ff64f-223">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="ff64f-p107">Wenn Sie eine Datei für einen Benutzer außerhalb der Organisation freigeben möchten, laden Sie die Datei herunter, und öffnen Sie sie. Klicken Sie auf „Datei“ > „Dokument schützen“ > „Mit Kennwort verschlüsseln“, und geben Sie dann ein sicheres Kennwort ein. Senden Sie das Kennwort in einer separaten E-Mail oder auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="ff64f-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="ff64f-227">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-227">Click **OK**.</span></span>

17. <span data-ttu-id="ff64f-228">Deaktivieren Sie im Fenster **Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?** das Kontrollkästchen **Freigeben blockieren und Zugriff auf freigegebene Inhalte einschränken**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-228">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="ff64f-229">Klicken Sie im Bereich **Möchten Sie die Richtlinie aktivieren oder zunächst testen?** auf **Ja, Richtlinie aktivieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-229">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="ff64f-230">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-230">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="ff64f-231">Teamwebsite für Kampagnenstrategie</span><span class="sxs-lookup"><span data-stu-id="ff64f-231">Campaign strategy team site</span></span>

<span data-ttu-id="ff64f-232">Führen Sie die folgenden Schritte durch, um eine isolierte, streng vertrauliche SharePoint Online-Teamwebsite für Kampagnenstrategieressourcen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="ff64f-232">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="ff64f-233">Verwenden Sie, falls erforderlich, einen Browser auf Ihrem lokalen Computer, und melden Sie sich mit Ihrem globalen Administratorkonto beim Admin Center (<https://admin.microsoft.com>) an.</span><span class="sxs-lookup"><span data-stu-id="ff64f-233">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="ff64f-234">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-234">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="ff64f-235">Klicken Sie in der neuen Registerkarte **SharePoint** in Ihrem Browser auf **+ Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-235">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="ff64f-236">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-236">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="ff64f-237">Geben Sie unter **Name der Teamwebsite** den Namen **Kampagnenstrategie** ein.</span><span class="sxs-lookup"><span data-stu-id="ff64f-237">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="ff64f-238">Geben Sie unter **Beschreibung der Teamwebsite** den Text **SharePoint-Website für Kampagnenstrategie (streng vertraulich)** ein.</span><span class="sxs-lookup"><span data-stu-id="ff64f-238">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="ff64f-239">Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-239">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="ff64f-240">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-240">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="ff64f-241">Klicken Sie auf der neuen Registerkarte **Kampagnenstrategie** in Ihrem Browser auf der Symbolleiste auf das Symbol „Einstellungen“, und klicken Sie dann auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-241">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="ff64f-242">Klicken Sie im Bereich **Websiteberechtigungen** auf **Erweiterte Berechtigungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-242">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="ff64f-243">Klicken Sie auf der neuen Registerkarte **Berechtigungen** in Ihrem Browser auf **Einstellungen für Zugriffsrechteanforderungen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-243">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="ff64f-244">Deaktivieren Sie im Dialogfeld **Einstellungen für Zugriffsrechteanforderungen** die Optionen **Mitgliedern das Freigeben der Website sowie einzelner Dateien und Ordner erlauben** und **Mitgliedern das Einladen von anderen zur Websitemitglieder-Gruppe erlauben** (sodass alle drei Kontrollkästchen deaktiviert sind), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-244">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="ff64f-245">Klicken Sie in der Liste auf **Kampagnenstrategiemitglieder**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-245">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="ff64f-246">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-246">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="ff64f-247">Geben Sie im Dialogfeld **Freigeben** **Senior-Mitarbeiter und strategische Mitarbeiter** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-247">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="ff64f-248">Klicken Sie in der Liste auf **Kampagnenstrategiebesitzer**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-248">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="ff64f-249">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-249">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="ff64f-250">Geben Sie im Dialogfeld **Freigeben** **IT-Mitarbeiter** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-250">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="ff64f-251">Klicken Sie auf die Schaltfläche „Zurück“ in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="ff64f-251">Click the back button on your browser.</span></span>

20. <span data-ttu-id="ff64f-252">Schließen Sie die Registerkarte **Benutzer und Gruppen** in Ihrem Browser, klicken Sie auf die Registerkarte **Kampagnenstrategie – Startseite** in Ihrem Browser, und schließen Sie dann den Bereich **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-252">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="ff64f-253">Nachfolgend finden Sie die Ergebnisse der Konfiguration von Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="ff64f-253">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="ff64f-254">Die SharePoint-Gruppe **Kampagnenstrategiemitglieder** enthält nur die Gruppen **Senior-Mitarbeiter und strategische Mitarbeiter** (mit den Candidate-, ChiefOfStaff- und die Strategic1-Benutzerkonten) und **Kampagnenstrategie** (nur mit dem globalen Administratorkonto).
</span><span class="sxs-lookup"><span data-stu-id="ff64f-254">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="ff64f-255">Die SharePoint-Gruppe **Kampagnenstrategie – Besitzer** enthält nur die Gruppe **IT-Mitarbeiter** (nur mit den ITAdmin1- und ITAdmin2-Benutzerkonten).</span><span class="sxs-lookup"><span data-stu-id="ff64f-255">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="ff64f-256">Die SharePoint-Gruppe **Kampagnenstrategie – Besucher** enthält keine Gruppen oder Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="ff64f-256">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="ff64f-257">Mitglieder können keine Berechtigungen auf Websiteebene ändern (dies kann nur von Mitgliedern der Gruppe **Kampagnenstrategie – Besitzer** ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="ff64f-257">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="ff64f-p108">Andere Benutzerkonten können nicht auf die Website oder ihre Ressourcen zugreifen oder Zugriff auf die Website anfordern. Zusätzliche Berechtigungen für die Website müssen vom globalen Administrator oder von einem Mitglied der Gruppe **Kampagnenstrategie – Besitzer** gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="ff64f-p108">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="ff64f-260">Konfigurieren Sie anschließend den Ordner „Dokumente“ der Kampagnenstrategie-Teamwebsite für die Bezeichnung „Streng vertraulich“.</span><span class="sxs-lookup"><span data-stu-id="ff64f-260">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="ff64f-261">Klicken Sie auf der Registerkarte **Kampagnenstrategie – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-261">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="ff64f-262">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-262">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="ff64f-263">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-263">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="ff64f-264">Wählen Sie unter **Einstellungen – Bezeichnung anwenden** die Option **Streng vertraulich**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-264">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="ff64f-p109">Konfigurieren Sie als Nächstes eine DLP-Richtlinie, die Benutzer blockiert, wenn sie ein Dokument auf einer SharePoint Online-Teamwebsite mit der Bezeichnung „Streng vertraulich“ außerhalb der Organisation freigeben. Diese DLP-Richtlinie gilt für Ressourcen auf der Kampagnenstrategiewebsite.</span><span class="sxs-lookup"><span data-stu-id="ff64f-p109">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="ff64f-267">Falls erforderlich, verwenden Sie einen Browser auf Ihrem lokalen Computer und melden Sie sich mit einem Konto beim Admin Center (<https://admin.microsoft.com>) an, das über die Rolle „Sicherheitsadministrator“ oder „Unternehmensadministrator“ verfügt.</span><span class="sxs-lookup"><span data-stu-id="ff64f-267">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="ff64f-268">Klicken Sie in der Registerkarte **Microsoft Office Home** des Browsers auf die Kachel **Security & Compliance**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-268">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="ff64f-269">Klicken Sie auf der neuen Registerkarte **Security & Compliance** in Ihrem Browser auf **Verhinderung von Datenverlust > Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-269">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="ff64f-270">Klicken Sie im Bereich **Verhinderung von Datenverlust** auf **+ Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-270">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="ff64f-271">Klicken Sie im Bereich **Mit einer Vorlage beginnen oder eine benutzerdefinierte Richtlinie erstellen** auf **Benutzerdefiniert**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-271">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="ff64f-272">Geben Sie im Bereich **Ihre Richtlinie benennen** den Namen **Bezeichnung „Streng vertraulich" - SharePoint Online-Teamwebsites** bei **Name** ein, und klicken Sie dann auf **Weiter**</span><span class="sxs-lookup"><span data-stu-id="ff64f-272">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="ff64f-273">Klicken Sie im Bereich **Speicherorte auswählen** auf **Bestimmte Speicherorte auswählen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-273">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="ff64f-274">Deaktivieren Sie in der Liste der Speicherorte **Exchange-E-Mail** und **OneDrive-Konten**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-274">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="ff64f-275">Klicken Sie im Bereich **Typen von vertraulichen Informationen anpassen, die geschützt werden sollen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-275">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="ff64f-276">In der **wählen Sie die Typen der Inhalte zum Schutz** Bereich, klicken Sie auf **hinzufügen** im Dropdown-Listenfeld, und klicken Sie dann auf **Etiketten**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-276">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="ff64f-277">Klicken Sie im Bereich **Bezeichnungen** auf **+ Hinzufügen**, wählen Sie die Bezeichnung **Streng vertraulich** aus, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-277">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="ff64f-278">Klicken Sie im Bereich **Typen des zu schützenden Inhalts auswählen** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-278">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="ff64f-279">Klicken Sie im Bereich **Customize the types of sensitive info you want to protect** (Anpassen der Typen an vertraulichen Informationen, die Sie schützen möchten) auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-279">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="ff64f-280">Klicken Sie im Bereich **What do you want to do if we detect sensitive info?** (Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?) auf **Customize the tip and email** (Den Tipp und die E-Mail anpassen).</span><span class="sxs-lookup"><span data-stu-id="ff64f-280">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="ff64f-281">Klicken Sie im Bereich **Customize policy tips and email notifications** (Anpassen der Richtlinientipps und der E-Mail-Benachrichtigungen) auf **Customize the policy tip text** (Den Tipptext der Richtlinie als nächstes anpassen).</span><span class="sxs-lookup"><span data-stu-id="ff64f-281">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="ff64f-282">Geben Sie Folgendes in das Textfeld ein, oder fügen Sie es ein:</span><span class="sxs-lookup"><span data-stu-id="ff64f-282">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="ff64f-p110">Wenn Sie eine Datei für einen Benutzer außerhalb der Organisation freigeben möchten, laden Sie die Datei herunter, und öffnen Sie sie. Klicken Sie auf „Datei“ > „Dokument schützen“ > „Mit Kennwort verschlüsseln“, und geben Sie dann ein sicheres Kennwort ein. Senden Sie das Kennwort in einer separaten E-Mail oder auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="ff64f-p110">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="ff64f-286">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-286">Click **OK**.</span></span>

18. <span data-ttu-id="ff64f-287">Wählen Sie im Bereich **Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?** die Option **Begründung für Außerkraftsetzung erforderlich**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-287">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="ff64f-288">Klicken Sie im Bereich **Möchten Sie die Richtlinie aktivieren oder zunächst testen?** auf **Ja, Richtlinie aktivieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-288">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="ff64f-289">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-289">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="ff64f-290">Befolgen Sie die Anweisungen unter [Aktivieren von Azure RMS mit dem Microsoft 365 Admin Center](/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="ff64f-290">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="ff64f-291">Konfigurieren Sie als Nächstes Azure Information Protection mit einer neuen bereichsbezogenen Richtlinie und einer untergeordneten Bezeichnung für Schutz und Berechtigungen, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ff64f-291">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="ff64f-p111">Melden Sie sich mit einem Konto im Admin Center an, das über die Rolle „Sicherheitsadministrator" oder Unternehmensadministrator" verfügt. Hilfe finden Sie unter [Wo kann ich mich bei Office 365 anmelden](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="ff64f-p111">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role. For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="ff64f-294">Wechseln Sie auf einer separaten Registerkarte im Browser zum Azure-Portal (<https://portal.azure.com>).</span><span class="sxs-lookup"><span data-stu-id="ff64f-294">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="ff64f-295">Geben Sie im Suchfeld die **Information** ein, klicken Sie dann auf **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-295">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="ff64f-296">Klicken Sie auf **Etiketten**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-296">Click **Labels**.</span></span>

5. <span data-ttu-id="ff64f-297">Klicken Sie mit der rechten Maustaste auf die Bezeichnung **Streng vertraulich**, und klicken Sie dann auf **Unterbezeichnung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-297">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="ff64f-298">Geben Sie unter **Name** **Kampagnenstrategie** und unter **Beschreibung** **Bezeichnung für Dokumente in der Teamwebsite für Kampagnenstrategie** ein.</span><span class="sxs-lookup"><span data-stu-id="ff64f-298">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="ff64f-299">Klicken Sie unter **Berechtigungen für Dokumente und E-Mails mit dieser Bezeichnung festlegen** auf **Schützen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-299">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="ff64f-300">Klicken Sie im Abschnitt **Schutz** auf **Azure (Cloudschlüssel)**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-300">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="ff64f-301">Klicken Sie im Blatt **Schützen** unter **Schutzeinstellungen** auf **+ Berechtigungen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-301">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="ff64f-302">Klicken Sie auf dem Blatt **Berechtigungen hinzufügen** unter **Benutzer und Gruppen angeben** auf **+ Verzeichnis durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-302">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="ff64f-303">Wählen Sie im Bereich **AAD-Benutzer und -Gruppen** die Option **Senior-Mitarbeiter und strategische Mitarbeiter**, und klicken Sie dann auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-303">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="ff64f-304">Klicken Sie unter **Aus voreingestellten Berechtigungen wählen oder Benutzerdefiniert festlegen** auf **Benutzerdefiniert**, und aktivieren Sie dann die Kontrollkästchen **Rechte anzeigen**, **Inhalt bearbeiten**, **Speichern**, **Antworten** und **Allen antworten**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-304">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="ff64f-305">Klicken Sie zweimal auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-305">Click **OK** twice.</span></span>

14. <span data-ttu-id="ff64f-306">Klicken Sie auf dem Blatt **Untergeordnete Bezeichnung** auf **Speichern** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-306">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="ff64f-307">Klicken Sie auf dem Blatt **Azure Information Protection** auf **Richtlinien > + Neue Richtlinie hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-307">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="ff64f-308">Geben Sie unter **Name** **Kampagnenstrategie** und unter **Beschreibung** **Dokumente in der Teamwebsite für Kampagnenstrategie** ein.</span><span class="sxs-lookup"><span data-stu-id="ff64f-308">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="ff64f-309">Klicken Sie auf **Wählen Sie aus, welche Benutzer oder Gruppen diese Richtlinie erhalten. > Benutzer/Gruppen** und wählen Sie dann **Senior-Mitarbeiter und strategische Mitarbeiter**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-309">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="ff64f-310">Klicken Sie auf **Auswählen\> OK**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-310">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="ff64f-p112">Klicken Sie auf **Bezeichnungen hinzufügen oder entfernen**. Klicken Sie im Bereich **Richtlinie: Bezeichnungen hinzufügen oder entfernen** auf **Kampagnenstrategie** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-p112">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="ff64f-313">Klicken Sie auf **Speichern** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff64f-313">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="ff64f-314">Sie können jetzt mit dem Erstellen von Dokumenten in diesen vier Websites beginnen und den Zugriff mit verschiedenen Benutzerkonten testen.</span><span class="sxs-lookup"><span data-stu-id="ff64f-314">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="ff64f-315">Um ein Dokument mit Azure Information Protection und mit dieser neuen Bezeichnung zu schützen, müssen Sie [den Azure Information Protection-Client](/information-protection/rms-client/install-client-app) auf einem Testcomputer installieren, Office vom Admin Center installieren und sich dann aus Microsoft Word mit einem Konto in der Gruppe **Senior-Mitarbeiter und strategische Mitarbeiter** Ihres Testabonnements anmelden.</span><span class="sxs-lookup"><span data-stu-id="ff64f-315">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff64f-316">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff64f-316">See Also</span></span>

[<span data-ttu-id="ff64f-317">Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützigen Organisationen und andere agile Organisationen</span><span class="sxs-lookup"><span data-stu-id="ff64f-317">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="ff64f-318">Konfigurieren von Gruppen und Benutzern für eine politische Kampagne in einer Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="ff64f-318">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="ff64f-319">Testumgebungsanleitungen (TLGs) zur Cloudakzeptanz</span><span class="sxs-lookup"><span data-stu-id="ff64f-319">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="ff64f-320">Microsoft 365-Lösungs- und Architekturcenter</span><span class="sxs-lookup"><span data-stu-id="ff64f-320">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)