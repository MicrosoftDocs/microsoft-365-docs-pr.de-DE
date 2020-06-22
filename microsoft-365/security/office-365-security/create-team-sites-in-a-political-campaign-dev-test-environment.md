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
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Zusammenfassung: Informationen zum Erstellen von öffentlichen, privaten, vertraulichen und streng vertraulichen SharePoint Online-Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne.'
ms.openlocfilehash: d22ada823877d4c0996be942c379e12929242eaf
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755236"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="d868f-103">Erstellen von Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne</span><span class="sxs-lookup"><span data-stu-id="d868f-103">Create team sites in a political campaign dev/test environment</span></span>

 <span data-ttu-id="d868f-104">**Zusammenfassung:** Informationen zum Erstellen von öffentlichen, privaten, vertraulichen und streng vertraulichen SharePoint Online-Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne.</span><span class="sxs-lookup"><span data-stu-id="d868f-104">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
  
<span data-ttu-id="d868f-105">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span><span class="sxs-lookup"><span data-stu-id="d868f-105">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span> <span data-ttu-id="d868f-106">These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="d868f-106">These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>
  
## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="d868f-107">Phase 1: Erstellen der Entwicklungs-/Testumgebung für eine politische Kampagne</span><span class="sxs-lookup"><span data-stu-id="d868f-107">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="d868f-108">Befolgen Sie zunächst die Anweisungen unter [Konfigurieren von Gruppen und Benutzern für eine politische Kampagne in einer Entwicklungs-/Testumgebung](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md), um Ihre Abonnements, Benutzer und Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d868f-108">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>
  
## <a name="phase-2-create-labels"></a><span data-ttu-id="d868f-109">Phase 2: Erstellen von Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="d868f-109">Phase 2: Create labels</span></span>

<span data-ttu-id="d868f-110">In dieser Phase erstellen Sie die Bezeichnungen für die verschiedenen Sicherheitsstufen für Dokumentordner für SharePoint Online-Teamwebsites.</span><span class="sxs-lookup"><span data-stu-id="d868f-110">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>
  
1. <span data-ttu-id="d868f-111">Falls erforderlich, melden Sie sich mit den Anmeldeinformationen des globalen Administratorkontos für Ihr Testabonnement beim Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="d868f-111">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="d868f-112">Hilfe finden Sie unter [Where to sign in to Microsoft 365 (Wo kann ich mich bei Microsoft 365 anmelden?)](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="d868f-112">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="d868f-113">Klicken Sie auf der Registerkarte **Microsoft Office Home** auf die Kachel **Admin**.</span><span class="sxs-lookup"><span data-stu-id="d868f-113">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="d868f-114">Klicken Sie auf der neuen Registerkarte **Microsoft 365 Admin Center** im Browser auf **Admin Center > Security &amp; Compliance**.</span><span class="sxs-lookup"><span data-stu-id="d868f-114">From the new **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="d868f-115">Klicken Sie auf der neuen Registerkarte **Start - Security &amp; Compliance** im Browser auf **Klassifizierungen > Bezeichnungen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-115">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="d868f-116">Klicken Sie im Bereich **Start > Bezeichnungen** auf **Bezeichnung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-116">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="d868f-117">Geben Sie im Bereich **Name für Bezeichnung\*\*\*\*Intern** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-117">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="d868f-118">Klicken Sie im Bereich **Bezeichnungseinstellungen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-118">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="d868f-119">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnung erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-119">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="d868f-120">Wiederholen Sie die Schritte 5 bis 8 für diese zusätzlichen Bezeichnungen:</span><span class="sxs-lookup"><span data-stu-id="d868f-120">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="d868f-121">Private</span><span class="sxs-lookup"><span data-stu-id="d868f-121">Private</span></span>
    
  - <span data-ttu-id="d868f-122">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="d868f-122">Sensitive</span></span>
    
  - <span data-ttu-id="d868f-123">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="d868f-123">Highly Confidential</span></span>
    
10. <span data-ttu-id="d868f-124">Klicken Sie im Bereich **Startseite > Bezeichnungen** auf **Bezeichnungen veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-124">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="d868f-125">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Zu veröffentlichende Bezeichnungen wählen**</span><span class="sxs-lookup"><span data-stu-id="d868f-125">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="d868f-126">Klicken Sie im Bereich **Choose labels** (Bezeichnungen auswählen) auf **Hinzufügen**, wählen Sie alle vier Bezeichnungen aus.</span><span class="sxs-lookup"><span data-stu-id="d868f-126">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="d868f-127">Klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="d868f-127">Click **Done**.</span></span>
    
14. <span data-ttu-id="d868f-128">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-128">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="d868f-129">Klicken Sie im Bereich **Speicherorte auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-129">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="d868f-130">Geben Sie im Bereich **Richtlinie benennen\*\*\*\*Kampagne** unter **Name** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-130">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="d868f-131">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnungen veröffentlichen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-131">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="d868f-132">Phase 3: Erstellen von SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="d868f-132">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="d868f-133">In dieser Phase werden SharePoint Online-Teamwebsites für Ihre politische Kampagne entsprechend den vier Typen von SharePoint Online-Teamwebsites erstellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d868f-133">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>
  
### <a name="campaign-wide-team-site"></a><span data-ttu-id="d868f-134">Kampagnen-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="d868f-134">Campaign wide team site</span></span>

<span data-ttu-id="d868f-135">Führen Sie folgende Schritte aus, um eine öffentliche SharePoint Online-Basis-Teamwebsite zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d868f-135">To create a baseline public SharePoint Online team site, do the following:</span></span>
  
1. <span data-ttu-id="d868f-136">Verwenden Sie, falls erforderlich, einen Browser auf Ihrem lokalen Computer, und melden Sie sich mit Ihrem globalen Administratorkonto beim Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) an.</span><span class="sxs-lookup"><span data-stu-id="d868f-136">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="d868f-137">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d868f-137">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="d868f-138">Klicken Sie in der neuen Registerkarte **SharePoint** in Ihrem Browser auf **+ Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-138">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="d868f-139">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="d868f-139">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="d868f-140">Geben Sie unter **Websitename** den Namen **Kampagne** ein. </span><span class="sxs-lookup"><span data-stu-id="d868f-140">In **Site name**, type **Campaign wide**.</span></span> 
    
6. <span data-ttu-id="d868f-141">Geben Sie unter **Beschreibung der Teamwebsite** den Text **SharePoint-Website für die gesamte Kampagne** ein.</span><span class="sxs-lookup"><span data-stu-id="d868f-141">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>
    
7. <span data-ttu-id="d868f-142">Wählen Sie unter **Datenschutzeinstellungen** die Option **Öffentlich - Alle Benutzer in der Organisation können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-142">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d868f-143">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-143">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="d868f-144">Konfigurieren Sie anschließend den Ordner „Dokumente“ der Kampagnen-Teamwebsite für die Bezeichnung „Intern“.</span><span class="sxs-lookup"><span data-stu-id="d868f-144">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>
  
1. <span data-ttu-id="d868f-145">Klicken Sie auf der Registerkarte **Kampagne – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="d868f-145">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="d868f-146">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-146">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="d868f-147">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="d868f-147">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="d868f-148">Wählen Sie unter **Einstellungen –Bezeichnung anwenden** die Option **Intern**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d868f-148">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>
    
### <a name="campaign-project-1-team-site"></a><span data-ttu-id="d868f-149">Teamwebsite für Kampagnenprojekt 1</span><span class="sxs-lookup"><span data-stu-id="d868f-149">Campaign project 1 team site</span></span>

<span data-ttu-id="d868f-150">Führen Sie die folgenden Schritte durch, um eine private SharePoint Online-Basis-Teamwebsite für ein Projekt innerhalb der Kampagne zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d868f-150">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>
  
1. <span data-ttu-id="d868f-151">Verwenden Sie, falls erforderlich, einen Browser auf Ihrem lokalen Computer, und melden Sie sich mit Ihrem globalen Administratorkonto beim Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) an.</span><span class="sxs-lookup"><span data-stu-id="d868f-151">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="d868f-152">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d868f-152">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="d868f-153">Klicken Sie in der neuen Registerkarte **SharePoint** in Ihrem Browser auf **+ Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-153">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="d868f-154">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="d868f-154">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="d868f-155">Geben Sie unter **Websitename** den Namen **Kampagnenprojekt 1** ein. </span><span class="sxs-lookup"><span data-stu-id="d868f-155">In **Site name**, type **Campaign project 1**.</span></span> 
    
6. <span data-ttu-id="d868f-156">Geben Sie unter **Beschreibung der Teamwebsite** den Text **SharePoint-Website für das Kampagnenprojekt 1** ein.</span><span class="sxs-lookup"><span data-stu-id="d868f-156">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>
    
7. <span data-ttu-id="d868f-157">Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-157">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d868f-158">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-158">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="d868f-159">Konfigurieren Sie anschließend den Ordner „Dokumente“ der Teamwebsite für Kampagnenprojekt 1 für die Bezeichnung „Privat“.</span><span class="sxs-lookup"><span data-stu-id="d868f-159">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>
  
1. <span data-ttu-id="d868f-160">Klicken Sie auf der Registerkarte **Kampagnenprojekt 1 – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="d868f-160">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="d868f-161">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-161">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="d868f-162">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="d868f-162">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="d868f-163">Wählen Sie unter **Einstellungen – Bezeichnung anwenden** die Option **Privat**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d868f-163">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>
    
### <a name="campaign-marketing-team-site"></a><span data-ttu-id="d868f-164">Kampagnenmarketing-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="d868f-164">Campaign marketing team site</span></span>

<span data-ttu-id="d868f-165">Führen Sie die folgenden Schritte durch, um eine isolierte, vertrauliche SharePoint-Teamwebsite für Kampagnenmarketingressourcen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d868f-165">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>
  
1. <span data-ttu-id="d868f-166">Melden Sie sich über einen Browser auf Ihrem lokalen Computer mit Ihrem globalen Administratorkonto beim Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) an.</span><span class="sxs-lookup"><span data-stu-id="d868f-166">Using a browser on your local computer, sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="d868f-167">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d868f-167">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="d868f-168">Klicken Sie in der neuen Registerkarte **SharePoint** in Ihrem Browser auf **+ Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-168">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="d868f-169">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="d868f-169">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="d868f-170">Geben Sie unter **Name der Teamwebsite** den Namen **Kampagnenmarketing** ein.</span><span class="sxs-lookup"><span data-stu-id="d868f-170">In **Team site name**, type **Campaign marketing**.</span></span>
    
6. <span data-ttu-id="d868f-171">Geben Sie unter **Beschreibung der Teamwebsite** den Text **SharePoint-Website für Kampagnenmarketing (vertraulich)** ein.</span><span class="sxs-lookup"><span data-stu-id="d868f-171">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>
    
7.  <span data-ttu-id="d868f-172">Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-172">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d868f-173">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-173">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="d868f-174">Klicken Sie auf der neuen Registerkarte **Kampagnenmarketing** in Ihrem Browser auf der Symbolleiste auf das Symbol „Einstellungen“, und klicken Sie dann auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-174">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="d868f-175">Klicken Sie im Bereich **Websiteberechtigungen** auf **Erweiterte Berechtigungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="d868f-176">Klicken Sie auf der neuen Registerkarte **Berechtigungen** in Ihrem Browser auf **Einstellungen für Zugriffsrechteanforderungen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-176">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="d868f-177">Deaktivieren Sie im Dialogfeld **Einstellungen für Zugriffsrechteanforderungen** die Kontrollkästchen **Mitgliedern das Freigeben der Website sowie einzelner Dateien und Ordner erlauben** und **Mitgliedern das Einladen von anderen zur Websitemitglieder-Gruppe erlauben**, geben Sie **ITAdmin1@**<your organization name> **.onmicrosoft.com** unter **Alle Zugriffsanforderungen an die folgende E-Mail-Adresse senden:**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d868f-177">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**<your organization name> **.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>
    
13. <span data-ttu-id="d868f-178">Klicken Sie in der Liste auf **Kampagnenmarketingmitglieder**.</span><span class="sxs-lookup"><span data-stu-id="d868f-178">Click **Campaign marketing Members** in the list.</span></span>
    
14. <span data-ttu-id="d868f-179">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="d868f-179">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="d868f-180">Geben Sie im Dialogfeld **Freigeben** **Senior-Mitarbeiter und strategische Mitarbeiter** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="d868f-180">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="d868f-181">Wiederholen Sie die Schritte 14 und 15 für die Gruppe **Analytiker** und das Benutzerkonto **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="d868f-181">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>
    
17. <span data-ttu-id="d868f-182">Klicken Sie auf die Schaltfläche „Zurück“ in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="d868f-182">Click the back button on your browser.</span></span>
    
18. <span data-ttu-id="d868f-183">Klicken Sie in der Liste auf **Kampagnenmarketingbesitzer**.</span><span class="sxs-lookup"><span data-stu-id="d868f-183">Click **Campaign marketing Owners** in the list.</span></span>
    
19. <span data-ttu-id="d868f-184">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="d868f-184">On the **People and Groups** page, click **New**.</span></span>
    
20. <span data-ttu-id="d868f-185">Geben Sie im Dialogfeld **Freigeben** **IT-Mitarbeiter** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="d868f-185">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
21. <span data-ttu-id="d868f-186">Klicken Sie auf die Schaltfläche „Zurück“ in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="d868f-186">Click the back button on your browser.</span></span>
    
22. <span data-ttu-id="d868f-187">Schließen Sie die Registerkarte **Benutzer und Gruppen** in Ihrem Browser, klicken Sie auf die Registerkarte **Kampagnenmarketing – Startseite** in Ihrem Browser, und schließen Sie dann den Bereich **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-187">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="d868f-188">Nachfolgend finden Sie die Ergebnisse der Konfiguration von Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="d868f-188">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="d868f-189">Die SharePoint-Gruppe **Kampagnenmarketingmitglieder** enthält nur die Gruppen **Senior-Mitarbeiter und strategische Mitarbeiter** (mit den Candidate-, ChiefOfStaff- und die Strategic1-Benutzerkonten), **Kampagnenmarketing** (mit dem globalen Administratorkonto), **Analytiker** (mit dem DataScientist1-Benutzerkonto), und das **Regular1**-Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="d868f-189">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>
    
- <span data-ttu-id="d868f-190">Die SharePoint-Gruppe **Kampagnenmarketing – Besitzer** enthält nur die Gruppe **IT-Mitarbeiter** (nur mit den ITAdmin1- und ITAdmin2-Benutzerkonten).</span><span class="sxs-lookup"><span data-stu-id="d868f-190">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="d868f-191">Die SharePoint-Gruppe **Kampagnenmarketing – Besucher** enthält keine Gruppen oder Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="d868f-191">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="d868f-192">Mitglieder können keine Berechtigungen auf Websiteebene ändern (dies kann nur von Mitgliedern der Gruppe **Kampagnenmarketing – Besitzer** ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="d868f-192">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>
    
- <span data-ttu-id="d868f-193">Andere Benutzerkonten können nicht auf die Website oder die zugehörigen Ressourcen zugreifen, Sie können jedoch Zugriff auf die Website anfordern. Dabei wird eine E-Mail an das Postfach des ITAdmin1-Benutzerkontos gesendet.</span><span class="sxs-lookup"><span data-stu-id="d868f-193">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>
    
<span data-ttu-id="d868f-194">Konfigurieren Sie anschließend den Ordner „Dokumente“ der Kampagnenmarketing-Teamwebsite für die Bezeichnung „Vertraulich“.</span><span class="sxs-lookup"><span data-stu-id="d868f-194">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="d868f-195">Klicken Sie auf der Registerkarte **Kampagnenmarketing – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="d868f-195">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="d868f-196">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-196">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="d868f-197">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="d868f-197">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="d868f-198">Wählen Sie unter **Einstellungen – Bezeichnung anwenden** die Option **Vertraulich**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d868f-198">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>
    
<span data-ttu-id="d868f-199">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization.</span><span class="sxs-lookup"><span data-stu-id="d868f-199">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization.</span></span> <span data-ttu-id="d868f-200">This DLP policy will apply to resources in the Campaign marketing site.</span><span class="sxs-lookup"><span data-stu-id="d868f-200">This DLP policy will apply to resources in the Campaign marketing site.</span></span>
  
1. <span data-ttu-id="d868f-201">Klicken Sie auf der Registerkarte **Microsoft Office-Homepage** im Browser auf die Kachel **Security &amp; Compliance**.</span><span class="sxs-lookup"><span data-stu-id="d868f-201">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="d868f-202">Klicken Sie auf der Registerkarte **Security &amp; Compliance** in Ihrem Browser auf **Verhinderung von Datenverlust > Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="d868f-202">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="d868f-203">Klicken Sie im Bereich **Verhinderung von Datenverlust** auf **+ Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-203">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="d868f-204">Klicken Sie im Bereich **Mit einer Vorlage beginnen oder eine benutzerdefinierte Richtlinie erstellen** auf **Benutzerdefiniert**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-204">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="d868f-205">Geben Sie im Bereich **Ihre Richtlinie benennen** den Namen **Bezeichnung „Vertraulich" - SharePoint Online-Teamwebsites** bei **Name** ein, und klicken Sie dann auf **Weiter**</span><span class="sxs-lookup"><span data-stu-id="d868f-205">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="d868f-206">Klicken Sie im Bereich **Speicherorte auswählen** auf **Bestimmte Speicherorte auswählen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-206">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="d868f-207">Deaktivieren Sie in der Liste der Speicherorte **Exchange-E-Mail** und **OneDrive-Konten**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-207">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d868f-208">Klicken Sie im Bereich **Typen von vertraulichen Informationen anpassen, die geschützt werden sollen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d868f-208">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="d868f-209">In der **wählen Sie die Typen der Inhalte zum Schutz** Bereich, klicken Sie auf **hinzufügen** im Dropdown-Listenfeld, und klicken Sie dann auf **Etiketten**.</span><span class="sxs-lookup"><span data-stu-id="d868f-209">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="d868f-210">Klicken Sie im Bereich **Bezeichnungen** auf **+ Hinzufügen**, wählen Sie die Bezeichnung **Vertraulich** aus, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="d868f-210">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="d868f-211">Klicken Sie im Bereich **Typen des zu schützenden Inhalts auswählen** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d868f-211">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="d868f-212">Klicken Sie im Bereich **Customize the types of sensitive info you want to protect** (Anpassen der Typen an vertraulichen Informationen, die Sie schützen möchten) auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-212">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="d868f-213">Klicken Sie im Bereich **What do you want to do if we detect sensitive info?** (Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?) auf **Customize the tip and email** (Den Tipp und die E-Mail anpassen).</span><span class="sxs-lookup"><span data-stu-id="d868f-213">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="d868f-214">Klicken Sie im Bereich **Customize policy tips and email notifications** (Anpassen der Richtlinientipps und der E-Mail-Benachrichtigungen) auf **Customize the policy tip text** (Den Tipptext der Richtlinie als nächstes anpassen).</span><span class="sxs-lookup"><span data-stu-id="d868f-214">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="d868f-215">Geben Sie Folgendes in das Textfeld ein, oder fügen Sie es ein:</span><span class="sxs-lookup"><span data-stu-id="d868f-215">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="d868f-216">To share with a user outside the organization, download the file and then open it.</span><span class="sxs-lookup"><span data-stu-id="d868f-216">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="d868f-217">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span><span class="sxs-lookup"><span data-stu-id="d868f-217">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="d868f-218">Send the password in a separate email or other means of communication.</span><span class="sxs-lookup"><span data-stu-id="d868f-218">Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="d868f-219">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d868f-219">Click **OK**.</span></span>
    
17. <span data-ttu-id="d868f-220">Deaktivieren Sie im Fenster **Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?** das Kontrollkästchen **Freigeben blockieren und Zugriff auf freigegebene Inhalte einschränken**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-220">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>
    
18. <span data-ttu-id="d868f-221">Klicken Sie im Bereich **Möchten Sie die Richtlinie aktivieren oder zunächst testen?** auf **Ja, Richtlinie aktivieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-221">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="d868f-222">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-222">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
### <a name="campaign-strategy-team-site"></a><span data-ttu-id="d868f-223">Teamwebsite für Kampagnenstrategie</span><span class="sxs-lookup"><span data-stu-id="d868f-223">Campaign strategy team site</span></span>

<span data-ttu-id="d868f-224">Führen Sie die folgenden Schritte durch, um eine isolierte, streng vertrauliche SharePoint Online-Teamwebsite für Kampagnenstrategieressourcen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d868f-224">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>
  
1. <span data-ttu-id="d868f-225">Verwenden Sie, falls erforderlich, einen Browser auf Ihrem lokalen Computer, und melden Sie sich mit Ihrem globalen Administratorkonto beim Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) an.</span><span class="sxs-lookup"><span data-stu-id="d868f-225">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="d868f-226">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d868f-226">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="d868f-227">Klicken Sie in der neuen Registerkarte **SharePoint** in Ihrem Browser auf **+ Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-227">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="d868f-228">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="d868f-228">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="d868f-229">Geben Sie unter **Name der Teamwebsite** den Namen **Kampagnenstrategie** ein.</span><span class="sxs-lookup"><span data-stu-id="d868f-229">In **Team site name**, type **Campaign strategy**.</span></span>
    
6. <span data-ttu-id="d868f-230">Geben Sie unter **Beschreibung der Teamwebsite** den Text **SharePoint-Website für Kampagnenstrategie (streng vertraulich)** ein.</span><span class="sxs-lookup"><span data-stu-id="d868f-230">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>
    
7.  <span data-ttu-id="d868f-231">Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-231">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d868f-232">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-232">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="d868f-233">Klicken Sie auf der neuen Registerkarte **Kampagnenstrategie** in Ihrem Browser auf der Symbolleiste auf das Symbol „Einstellungen“, und klicken Sie dann auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-233">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="d868f-234">Klicken Sie im Bereich **Websiteberechtigungen** auf **Erweiterte Berechtigungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-234">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="d868f-235">Klicken Sie auf der neuen Registerkarte **Berechtigungen** in Ihrem Browser auf **Einstellungen für Zugriffsrechteanforderungen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-235">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="d868f-236">Deaktivieren Sie im Dialogfeld **Einstellungen für Zugriffsrechteanforderungen** die Optionen **Mitgliedern das Freigeben der Website sowie einzelner Dateien und Ordner erlauben** und **Mitgliedern das Einladen von anderen zur Websitemitglieder-Gruppe erlauben** (sodass alle drei Kontrollkästchen deaktiviert sind), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d868f-236">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
13. <span data-ttu-id="d868f-237">Klicken Sie in der Liste auf **Kampagnenstrategiemitglieder**.</span><span class="sxs-lookup"><span data-stu-id="d868f-237">Click **Campaign strategy Members** in the list.</span></span>
    
14. <span data-ttu-id="d868f-238">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="d868f-238">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="d868f-239">Geben Sie im Dialogfeld **Freigeben** **Senior-Mitarbeiter und strategische Mitarbeiter** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="d868f-239">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="d868f-240">Klicken Sie in der Liste auf **Kampagnenstrategiebesitzer**.</span><span class="sxs-lookup"><span data-stu-id="d868f-240">Click **Campaign strategy Owners** in the list.</span></span>
    
17. <span data-ttu-id="d868f-241">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="d868f-241">On the **People and Groups** page, click **New**.</span></span>
    
18. <span data-ttu-id="d868f-242">Geben Sie im Dialogfeld **Freigeben** **IT-Mitarbeiter** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="d868f-242">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
19. <span data-ttu-id="d868f-243">Klicken Sie auf die Schaltfläche „Zurück“ in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="d868f-243">Click the back button on your browser.</span></span>
    
20. <span data-ttu-id="d868f-244">Schließen Sie die Registerkarte **Benutzer und Gruppen** in Ihrem Browser, klicken Sie auf die Registerkarte **Kampagnenstrategie – Startseite** in Ihrem Browser, und schließen Sie dann den Bereich **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-244">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="d868f-245">Nachfolgend finden Sie die Ergebnisse der Konfiguration von Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="d868f-245">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="d868f-246">Die SharePoint-Gruppe **Kampagnenstrategiemitglieder** enthält nur die Gruppen **Senior-Mitarbeiter und strategische Mitarbeiter** (mit den Candidate-, ChiefOfStaff- und die Strategic1-Benutzerkonten) und **Kampagnenstrategie** (nur mit dem globalen Administratorkonto).
</span><span class="sxs-lookup"><span data-stu-id="d868f-246">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="d868f-247">Die SharePoint-Gruppe **Kampagnenstrategie – Besitzer** enthält nur die Gruppe **IT-Mitarbeiter** (nur mit den ITAdmin1- und ITAdmin2-Benutzerkonten).</span><span class="sxs-lookup"><span data-stu-id="d868f-247">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="d868f-248">Die SharePoint-Gruppe **Kampagnenstrategie – Besucher** enthält keine Gruppen oder Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="d868f-248">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="d868f-249">Mitglieder können keine Berechtigungen auf Websiteebene ändern (dies kann nur von Mitgliedern der Gruppe **Kampagnenstrategie – Besitzer** ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="d868f-249">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>
    
- <span data-ttu-id="d868f-250">Other user accounts cannot access the site or its resources or request access to the site.</span><span class="sxs-lookup"><span data-stu-id="d868f-250">Other user accounts cannot access the site or its resources or request access to the site.</span></span> <span data-ttu-id="d868f-251">Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span><span class="sxs-lookup"><span data-stu-id="d868f-251">Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>
    
<span data-ttu-id="d868f-252">Konfigurieren Sie anschließend den Ordner „Dokumente“ der Kampagnenstrategie-Teamwebsite für die Bezeichnung „Streng vertraulich“.</span><span class="sxs-lookup"><span data-stu-id="d868f-252">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>
  
1. <span data-ttu-id="d868f-253">Klicken Sie auf der Registerkarte **Kampagnenstrategie – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="d868f-253">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="d868f-254">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-254">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="d868f-255">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="d868f-255">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="d868f-256">Wählen Sie unter **Einstellungen – Bezeichnung anwenden** die Option **Streng vertraulich**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d868f-256">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>
    
<span data-ttu-id="d868f-257">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization.</span><span class="sxs-lookup"><span data-stu-id="d868f-257">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization.</span></span> <span data-ttu-id="d868f-258">This DLP policy will apply to resources in the Campaign strategy site.</span><span class="sxs-lookup"><span data-stu-id="d868f-258">This DLP policy will apply to resources in the Campaign strategy site.</span></span>
  
1. <span data-ttu-id="d868f-259">Falls erforderlich, verwenden Sie einen Browser auf Ihrem lokalen Computer und melden Sie sich mit einem Konto beim Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) an, das über die Rolle „Sicherheitsadministrator“ oder „Unternehmensadministrator“ verfügt.</span><span class="sxs-lookup"><span data-stu-id="d868f-259">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="d868f-260">Klicken Sie auf der Registerkarte **Microsoft Office-Homepage** im Browser auf die Kachel **Security &amp; Compliance**.</span><span class="sxs-lookup"><span data-stu-id="d868f-260">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
3. <span data-ttu-id="d868f-261">Klicken Sie auf der Registerkarte **Security &amp; Compliance** in Ihrem Browser auf **Verhinderung von Datenverlust > Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="d868f-261">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
4. <span data-ttu-id="d868f-262">Klicken Sie im Bereich **Verhinderung von Datenverlust** auf **+ Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-262">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
5. <span data-ttu-id="d868f-263">Klicken Sie im Bereich **Mit einer Vorlage beginnen oder eine benutzerdefinierte Richtlinie erstellen** auf **Benutzerdefiniert**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-263">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="d868f-264">Geben Sie im Bereich **Ihre Richtlinie benennen** den Namen **Bezeichnung „Streng vertraulich" - SharePoint Online-Teamwebsites** bei **Name** ein, und klicken Sie dann auf **Weiter**</span><span class="sxs-lookup"><span data-stu-id="d868f-264">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="d868f-265">Klicken Sie im Bereich **Speicherorte auswählen** auf **Bestimmte Speicherorte auswählen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-265">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d868f-266">Deaktivieren Sie in der Liste der Speicherorte **Exchange-E-Mail** und **OneDrive-Konten**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-266">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
9. <span data-ttu-id="d868f-267">Klicken Sie im Bereich **Typen von vertraulichen Informationen anpassen, die geschützt werden sollen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d868f-267">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
10. <span data-ttu-id="d868f-268">In der **wählen Sie die Typen der Inhalte zum Schutz** Bereich, klicken Sie auf **hinzufügen** im Dropdown-Listenfeld, und klicken Sie dann auf **Etiketten**.</span><span class="sxs-lookup"><span data-stu-id="d868f-268">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
11. <span data-ttu-id="d868f-269">Klicken Sie im Bereich **Bezeichnungen** auf **+ Hinzufügen**, wählen Sie die Bezeichnung **Streng vertraulich** aus, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="d868f-269">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
12. <span data-ttu-id="d868f-270">Klicken Sie im Bereich **Typen des zu schützenden Inhalts auswählen** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d868f-270">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
13. <span data-ttu-id="d868f-271">Klicken Sie im Bereich **Customize the types of sensitive info you want to protect** (Anpassen der Typen an vertraulichen Informationen, die Sie schützen möchten) auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-271">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="d868f-272">Klicken Sie im Bereich **What do you want to do if we detect sensitive info?** (Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?) auf **Customize the tip and email** (Den Tipp und die E-Mail anpassen).</span><span class="sxs-lookup"><span data-stu-id="d868f-272">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
15. <span data-ttu-id="d868f-273">Klicken Sie im Bereich **Customize policy tips and email notifications** (Anpassen der Richtlinientipps und der E-Mail-Benachrichtigungen) auf **Customize the policy tip text** (Den Tipptext der Richtlinie als nächstes anpassen).</span><span class="sxs-lookup"><span data-stu-id="d868f-273">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
16. <span data-ttu-id="d868f-274">Geben Sie Folgendes in das Textfeld ein, oder fügen Sie es ein:</span><span class="sxs-lookup"><span data-stu-id="d868f-274">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="d868f-275">To share with a user outside the organization, download the file and then open it.</span><span class="sxs-lookup"><span data-stu-id="d868f-275">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="d868f-276">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span><span class="sxs-lookup"><span data-stu-id="d868f-276">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="d868f-277">Send the password in a separate email or other means of communication.</span><span class="sxs-lookup"><span data-stu-id="d868f-277">Send the password in a separate email or other means of communication.</span></span>
    
17. <span data-ttu-id="d868f-278">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d868f-278">Click **OK**.</span></span>
    
18. <span data-ttu-id="d868f-279">Wählen Sie im Bereich **Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?** die Option **Begründung für Außerkraftsetzung erforderlich**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-279">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="d868f-280">Klicken Sie im Bereich **Möchten Sie die Richtlinie aktivieren oder zunächst testen?** auf **Ja, Richtlinie aktivieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-280">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
20. <span data-ttu-id="d868f-281">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-281">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="d868f-282">Befolgen Sie die Anweisungen unter [Aktivieren von Azure RMS mit dem Microsoft 365 Admin Center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="d868f-282">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>
  
<span data-ttu-id="d868f-283">Konfigurieren Sie als Nächstes Azure Information Protection mit einer neuen bereichsbezogenen Richtlinie und einer untergeordneten Bezeichnung für Schutz und Berechtigungen, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="d868f-283">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>
  
1. <span data-ttu-id="d868f-284">Melden Sie sich beim Admin Center mit einem Konto an, das über die Rolle „Sicherheitsadministrator" oder Unternehmensadministrator" verfügt.</span><span class="sxs-lookup"><span data-stu-id="d868f-284">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="d868f-285">Hilfe finden Sie unter [Where to sign in to Office 365 (Wo kann ich mich bei Office 365 anmelden?)](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="d868f-285">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="d868f-286">Wechseln Sie auf einer separaten Registerkarte im Browser zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="d868f-286">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
4. <span data-ttu-id="d868f-287">Geben Sie im Suchfeld die **Information** ein, klicken Sie dann auf **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="d868f-287">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="d868f-288">Klicken Sie auf **Etiketten**.</span><span class="sxs-lookup"><span data-stu-id="d868f-288">Click **Labels**.</span></span>
    
6. <span data-ttu-id="d868f-289">Klicken Sie mit der rechten Maustaste auf die Bezeichnung **Streng vertraulich**, und klicken Sie dann auf **Unterbezeichnung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-289">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="d868f-290">Geben Sie unter **Name** **Kampagnenstrategie** und unter **Beschreibung** **Bezeichnung für Dokumente in der Teamwebsite für Kampagnenstrategie** ein.</span><span class="sxs-lookup"><span data-stu-id="d868f-290">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>
    
8. <span data-ttu-id="d868f-291">Klicken Sie unter **Berechtigungen für Dokumente und E-Mails mit dieser Bezeichnung festlegen** auf **Schützen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-291">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="d868f-292">Klicken Sie im Abschnitt **Schutz** auf **Azure (Cloudschlüssel)**.</span><span class="sxs-lookup"><span data-stu-id="d868f-292">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="d868f-293">Klicken Sie im Blatt **Schützen** unter **Schutzeinstellungen** auf **+ Berechtigungen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-293">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>
    
11. <span data-ttu-id="d868f-294">Klicken Sie auf dem Blatt **Berechtigungen hinzufügen** unter **Benutzer und Gruppen angeben** auf **+ Verzeichnis durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-294">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>
    
12. <span data-ttu-id="d868f-295">Wählen Sie im Bereich **AAD-Benutzer und -Gruppen** die Option **Senior-Mitarbeiter und strategische Mitarbeiter**, und klicken Sie dann auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-295">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>
    
13. <span data-ttu-id="d868f-296">Klicken Sie unter **Aus voreingestellten Berechtigungen wählen oder Benutzerdefiniert festlegen** auf **Benutzerdefiniert**, und aktivieren Sie dann die Kontrollkästchen **Rechte anzeigen**, **Inhalt bearbeiten**, \*\* Speichern\*\*, **Antworten** und **Allen antworten**.</span><span class="sxs-lookup"><span data-stu-id="d868f-296">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="d868f-297">Klicken Sie zweimal auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d868f-297">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="d868f-298">Klicken Sie auf dem Blatt **Untergeordnete Bezeichnung** auf **Speichern** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d868f-298">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="d868f-299">Klicken Sie auf dem Blatt **Azure Information Protection** auf **Richtlinien > + Neue Richtlinie hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d868f-299">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="d868f-300">Geben Sie unter **Name** **Kampagnenstrategie** und unter **Beschreibung** **Dokumente in der Teamwebsite für Kampagnenstrategie** ein.</span><span class="sxs-lookup"><span data-stu-id="d868f-300">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>
    
18. <span data-ttu-id="d868f-301">Klicken Sie auf **Wählen Sie aus, welche Benutzer oder Gruppen diese Richtlinie erhalten. > Benutzer/Gruppen** und wählen Sie dann **Senior-Mitarbeiter und strategische Mitarbeiter**.</span><span class="sxs-lookup"><span data-stu-id="d868f-301">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>
    
19. <span data-ttu-id="d868f-302">Klicken Sie auf **Auswählen > OK**.</span><span class="sxs-lookup"><span data-stu-id="d868f-302">Click **Select > OK**.</span></span>

20. <span data-ttu-id="d868f-303">Click **Add or remove labels**.</span><span class="sxs-lookup"><span data-stu-id="d868f-303">Click **Add or remove labels**.</span></span> <span data-ttu-id="d868f-304">In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span><span class="sxs-lookup"><span data-stu-id="d868f-304">In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>   

21. <span data-ttu-id="d868f-305">Klicken Sie auf **Speichern** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d868f-305">Click **Save**, and then click **OK**.</span></span>
  
<span data-ttu-id="d868f-306">Sie können jetzt mit dem Erstellen von Dokumenten in diesen vier Websites beginnen und den Zugriff mit verschiedenen Benutzerkonten testen.</span><span class="sxs-lookup"><span data-stu-id="d868f-306">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span> 
  
<span data-ttu-id="d868f-307">Um ein Dokument mit Azure Information Protection und mit dieser neuen Bezeichnung zu schützen, müssen Sie [den Azure Information Protection-Client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) auf einem Testcomputer installieren, Office vom Admin Center installieren und sich dann aus Microsoft Word mit einem Konto in der Gruppe **Senior-Mitarbeiter und strategische Mitarbeiter** Ihres Testabonnements anmelden.</span><span class="sxs-lookup"><span data-stu-id="d868f-307">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d868f-308">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d868f-308">See Also</span></span>

[<span data-ttu-id="d868f-309">Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützigen Organisationen und andere agile Organisationen</span><span class="sxs-lookup"><span data-stu-id="d868f-309">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="d868f-310">Konfigurieren von Gruppen und Benutzern für eine politische Kampagne in einer Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d868f-310">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)
  
[<span data-ttu-id="d868f-311">Testumgebungsanleitungen (TLGs) zur Cloudakzeptanz</span><span class="sxs-lookup"><span data-stu-id="d868f-311">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="d868f-312">Cloudakzeptanz und Hybridlösungen</span><span class="sxs-lookup"><span data-stu-id="d868f-312">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




