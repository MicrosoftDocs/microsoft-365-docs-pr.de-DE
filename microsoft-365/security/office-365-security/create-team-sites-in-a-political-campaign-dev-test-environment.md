---
title: Erstellen von Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne
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
ms.custom: ''
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Zusammenfassung: Informationen zum Erstellen von öffentlichen, privaten, vertraulichen und streng vertraulichen SharePoint Online-Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne.'
ms.openlocfilehash: d36b2c74cc7accadf5bbbde1b52f94c5e998ea8a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599492"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="57f7c-103">Erstellen von Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne</span><span class="sxs-lookup"><span data-stu-id="57f7c-103">Create team sites in a political campaign dev/test environment</span></span>

 <span data-ttu-id="57f7c-104">**Zusammenfassung:** Informationen zum Erstellen von öffentlichen, privaten, vertraulichen und streng vertraulichen SharePoint Online-Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne.</span><span class="sxs-lookup"><span data-stu-id="57f7c-104">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
  
<span data-ttu-id="57f7c-p101">Verwenden Sie die Schritte in diesem Artikel zum Erstellen einer Entwicklungs-/Testumgebung mit vier verschiedenen Typen von SharePoint Online-Teamwebsites für die Lösung [Microsoft-Sicherheitsanleitungen für politische Kampagnen, gemeinnützige Organisationen und andere agile Organisationen ](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). Diese Websites werden im Thema 10 **SharePoint und OneDrive for Business** detailliert erläutert.</span><span class="sxs-lookup"><span data-stu-id="57f7c-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>
  
## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="57f7c-107">Phase 1: Erstellen der Entwicklungs-/Testumgebung für eine politische Kampagne</span><span class="sxs-lookup"><span data-stu-id="57f7c-107">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="57f7c-108">Befolgen Sie zunächst die Anweisungen unter [Konfigurieren von Gruppen und Benutzern für eine politische Kampagne in einer Entwicklungs-/Testumgebung](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md), um Ihre Abonnements, Benutzer und Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="57f7c-108">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>
  
## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="57f7c-109">Phase 2: Erstellen von Office 365-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="57f7c-109">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="57f7c-110">In dieser Phase erstellen Sie die Bezeichnungen für die verschiedenen Sicherheitsstufen für Dokumentordner für SharePoint Online-Teamwebsites.</span><span class="sxs-lookup"><span data-stu-id="57f7c-110">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>
  
1. <span data-ttu-id="57f7c-111">Falls erforderlich, melden Sie sich mit den Anmeldeinformationen des globalen Administratorkontos für Ihr Testabonnement beim Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="57f7c-111">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="57f7c-112">Hilfe finden Sie unter [Wo kann ich mich bei Office 365 anmelden?](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="57f7c-112">For help, see [Where to sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="57f7c-113">Klicken Sie auf der Registerkarte **Microsoft Office Home** auf die Kachel **Admin**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-113">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="57f7c-114">Klicken Sie auf der neuen Registerkarte **Microsoft 365 Admin Center** im Browser auf **Admin Center > Security &amp; Compliance**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-114">From the new **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="57f7c-115">Klicken Sie auf der neuen Registerkarte **Start - Security &amp; Compliance** im Browser auf **Klassifizierungen > Bezeichnungen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-115">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="57f7c-116">Klicken Sie im Bereich **Start > Bezeichnungen** auf **Bezeichnung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-116">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="57f7c-117">Geben Sie im Bereich **Name für Bezeichnung\*\*\*\*Intern** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-117">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="57f7c-118">Klicken Sie im Bereich **Bezeichnungseinstellungen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-118">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="57f7c-119">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnung erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-119">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="57f7c-120">Wiederholen Sie die Schritte 5 bis 8 für diese zusätzlichen Bezeichnungen:</span><span class="sxs-lookup"><span data-stu-id="57f7c-120">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="57f7c-121">Private</span><span class="sxs-lookup"><span data-stu-id="57f7c-121">Private</span></span>
    
  - <span data-ttu-id="57f7c-122">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="57f7c-122">Sensitive</span></span>
    
  - <span data-ttu-id="57f7c-123">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="57f7c-123">Highly Confidential</span></span>
    
10. <span data-ttu-id="57f7c-124">Klicken Sie im Bereich **Startseite > Bezeichnungen** auf **Bezeichnungen veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-124">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="57f7c-125">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Zu veröffentlichende Bezeichnungen wählen**</span><span class="sxs-lookup"><span data-stu-id="57f7c-125">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="57f7c-126">Klicken Sie im Bereich **Choose labels** (Bezeichnungen auswählen) auf **Hinzufügen**, wählen Sie alle vier Bezeichnungen aus.</span><span class="sxs-lookup"><span data-stu-id="57f7c-126">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="57f7c-127">Klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-127">Click **Done**.</span></span>
    
14. <span data-ttu-id="57f7c-128">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-128">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="57f7c-129">Klicken Sie im Bereich **Speicherorte auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-129">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="57f7c-130">Geben Sie im Bereich **Richtlinie benennen\*\*\*\*Kampagne** unter **Name** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-130">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="57f7c-131">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnungen veröffentlichen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-131">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="57f7c-132">Phase 3: Erstellen von SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="57f7c-132">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="57f7c-133">In dieser Phase werden SharePoint Online-Teamwebsites für Ihre politische Kampagne entsprechend den vier Typen von SharePoint Online-Teamwebsites erstellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="57f7c-133">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>
  
### <a name="campaign-wide-team-site"></a><span data-ttu-id="57f7c-134">Kampagnen-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="57f7c-134">Campaign wide team site</span></span>

<span data-ttu-id="57f7c-135">Führen Sie folgende Schritte aus, um eine öffentliche SharePoint Online-Basis-Teamwebsite zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="57f7c-135">To create a baseline public SharePoint Online team site, do the following:</span></span>
  
1. <span data-ttu-id="57f7c-136">Verwenden Sie, falls erforderlich, einen Browser auf Ihrem lokalen Computer, und melden Sie sich mit Ihrem globalen Administratorkonto beim Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) an.</span><span class="sxs-lookup"><span data-stu-id="57f7c-136">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="57f7c-137">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-137">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="57f7c-138">Klicken Sie in der neuen Registerkarte **SharePoint** in Ihrem Browser auf **+ Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-138">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="57f7c-139">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-139">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="57f7c-140">Geben Sie unter **Websitename** den Namen **Kampagne** ein. </span><span class="sxs-lookup"><span data-stu-id="57f7c-140">In **Site name**, type **Campaign wide**.</span></span> 
    
6. <span data-ttu-id="57f7c-141">Geben Sie unter **Beschreibung der Teamwebsite** den Text **SharePoint-Website für die gesamte Kampagne** ein.</span><span class="sxs-lookup"><span data-stu-id="57f7c-141">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>
    
7. <span data-ttu-id="57f7c-142">Wählen Sie unter **Datenschutzeinstellungen** die Option **Öffentlich - Alle Benutzer in der Organisation können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-142">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="57f7c-143">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-143">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="57f7c-144">Konfigurieren Sie anschließend den Ordner „Dokumente“ der Kampagnen-Teamwebsite für die Bezeichnung „Intern“.</span><span class="sxs-lookup"><span data-stu-id="57f7c-144">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>
  
1. <span data-ttu-id="57f7c-145">Klicken Sie auf der Registerkarte **Kampagne – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-145">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="57f7c-146">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-146">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="57f7c-147">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-147">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="57f7c-148">Wählen Sie unter **Einstellungen –Bezeichnung anwenden** die Option **Intern**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-148">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>
    
### <a name="campaign-project-1-team-site"></a><span data-ttu-id="57f7c-149">Teamwebsite für Kampagnenprojekt 1</span><span class="sxs-lookup"><span data-stu-id="57f7c-149">Campaign project 1 team site</span></span>

<span data-ttu-id="57f7c-150">Führen Sie die folgenden Schritte durch, um eine private SharePoint Online-Basis-Teamwebsite für ein Projekt innerhalb der Kampagne zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="57f7c-150">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>
  
1. <span data-ttu-id="57f7c-151">Verwenden Sie, falls erforderlich, einen Browser auf Ihrem lokalen Computer, und melden Sie sich mit Ihrem globalen Administratorkonto beim Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) an.</span><span class="sxs-lookup"><span data-stu-id="57f7c-151">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="57f7c-152">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-152">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="57f7c-153">Klicken Sie in der neuen Registerkarte **SharePoint** in Ihrem Browser auf **+ Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-153">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="57f7c-154">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-154">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="57f7c-155">Geben Sie unter **Websitename** den Namen **Kampagnenprojekt 1** ein. </span><span class="sxs-lookup"><span data-stu-id="57f7c-155">In **Site name**, type **Campaign project 1**.</span></span> 
    
6. <span data-ttu-id="57f7c-156">Geben Sie unter **Beschreibung der Teamwebsite** den Text **SharePoint-Website für das Kampagnenprojekt 1** ein.</span><span class="sxs-lookup"><span data-stu-id="57f7c-156">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>
    
7. <span data-ttu-id="57f7c-157">Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-157">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="57f7c-158">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-158">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="57f7c-159">Konfigurieren Sie anschließend den Ordner „Dokumente“ der Teamwebsite für Kampagnenprojekt 1 für die Bezeichnung „Privat“.</span><span class="sxs-lookup"><span data-stu-id="57f7c-159">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>
  
1. <span data-ttu-id="57f7c-160">Klicken Sie auf der Registerkarte **Kampagnenprojekt 1 – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-160">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="57f7c-161">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-161">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="57f7c-162">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-162">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="57f7c-163">Wählen Sie unter **Einstellungen – Bezeichnung anwenden** die Option **Privat**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-163">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>
    
### <a name="campaign-marketing-team-site"></a><span data-ttu-id="57f7c-164">Kampagnenmarketing-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="57f7c-164">Campaign marketing team site</span></span>

<span data-ttu-id="57f7c-165">Führen Sie die folgenden Schritte durch, um eine isolierte, vertrauliche SharePoint-Teamwebsite für Kampagnenmarketingressourcen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="57f7c-165">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>
  
1. <span data-ttu-id="57f7c-166">Melden Sie sich über einen Browser auf Ihrem lokalen Computer mit Ihrem globalen Administratorkonto beim Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) an.</span><span class="sxs-lookup"><span data-stu-id="57f7c-166">Using a browser on your local computer, sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="57f7c-167">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-167">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="57f7c-168">Klicken Sie in der neuen Registerkarte **SharePoint** in Ihrem Browser auf **+ Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-168">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="57f7c-169">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-169">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="57f7c-170">Geben Sie unter **Name der Teamwebsite** den Namen **Kampagnenmarketing** ein.</span><span class="sxs-lookup"><span data-stu-id="57f7c-170">In **Team site name**, type **Campaign marketing**.</span></span>
    
6. <span data-ttu-id="57f7c-171">Geben Sie unter **Beschreibung der Teamwebsite** den Text **SharePoint-Website für Kampagnenmarketing (vertraulich)** ein.</span><span class="sxs-lookup"><span data-stu-id="57f7c-171">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>
    
7.  <span data-ttu-id="57f7c-172">Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-172">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="57f7c-173">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-173">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="57f7c-174">Klicken Sie auf der neuen Registerkarte **Kampagnenmarketing** in Ihrem Browser auf der Symbolleiste auf das Symbol „Einstellungen“, und klicken Sie dann auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-174">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="57f7c-175">Klicken Sie im Bereich **Websiteberechtigungen** auf **Erweiterte Berechtigungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="57f7c-176">Klicken Sie auf der neuen Registerkarte **Berechtigungen** in Ihrem Browser auf **Einstellungen für Zugriffsrechteanforderungen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-176">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="57f7c-177">Deaktivieren Sie im Dialogfeld **Einstellungen für Zugriffsrechteanforderungen** die Kontrollkästchen **Mitgliedern das Freigeben der Website sowie einzelner Dateien und Ordner erlauben** und **Mitgliedern das Einladen von anderen zur Websitemitglieder-Gruppe erlauben**, geben Sie **ITAdmin1@**<your organization name> **.onmicrosoft.com** unter **Alle Zugriffsanforderungen an die folgende E-Mail-Adresse senden:**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-177">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**<your organization name> **.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>
    
13. <span data-ttu-id="57f7c-178">Klicken Sie in der Liste auf **Kampagnenmarketingmitglieder**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-178">Click **Campaign marketing Members** in the list.</span></span>
    
14. <span data-ttu-id="57f7c-179">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-179">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="57f7c-180">Geben Sie im Dialogfeld **Freigeben** **Senior-Mitarbeiter und strategische Mitarbeiter** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-180">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="57f7c-181">Wiederholen Sie die Schritte 14 und 15 für die Gruppe **Analytiker** und das Benutzerkonto **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-181">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>
    
17. <span data-ttu-id="57f7c-182">Klicken Sie auf die Schaltfläche „Zurück“ in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="57f7c-182">Click the back button on your browser.</span></span>
    
18. <span data-ttu-id="57f7c-183">Klicken Sie in der Liste auf **Kampagnenmarketingbesitzer**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-183">Click **Campaign marketing Owners** in the list.</span></span>
    
19. <span data-ttu-id="57f7c-184">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-184">On the **People and Groups** page, click **New**.</span></span>
    
20. <span data-ttu-id="57f7c-185">Geben Sie im Dialogfeld **Freigeben** **IT-Mitarbeiter** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-185">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
21. <span data-ttu-id="57f7c-186">Klicken Sie auf die Schaltfläche „Zurück“ in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="57f7c-186">Click the back button on your browser.</span></span>
    
22. <span data-ttu-id="57f7c-187">Schließen Sie die Registerkarte **Benutzer und Gruppen** in Ihrem Browser, klicken Sie auf die Registerkarte **Kampagnenmarketing – Startseite** in Ihrem Browser, und schließen Sie dann den Bereich **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-187">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="57f7c-188">Nachfolgend finden Sie die Ergebnisse der Konfiguration von Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="57f7c-188">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="57f7c-189">Die SharePoint-Gruppe **Kampagnenmarketingmitglieder** enthält nur die Gruppen **Senior-Mitarbeiter und strategische Mitarbeiter** (mit den Candidate-, ChiefOfStaff- und die Strategic1-Benutzerkonten), **Kampagnenmarketing** (mit dem globalen Administratorkonto), **Analytiker** (mit dem DataScientist1-Benutzerkonto), und das **Regular1**-Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="57f7c-189">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>
    
- <span data-ttu-id="57f7c-190">Die SharePoint-Gruppe **Kampagnenmarketing – Besitzer** enthält nur die Gruppe **IT-Mitarbeiter** (nur mit den ITAdmin1- und ITAdmin2-Benutzerkonten).</span><span class="sxs-lookup"><span data-stu-id="57f7c-190">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="57f7c-191">Die SharePoint-Gruppe **Kampagnenmarketing – Besucher** enthält keine Gruppen oder Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="57f7c-191">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="57f7c-192">Mitglieder können keine Berechtigungen auf Websiteebene ändern (dies kann nur von Mitgliedern der Gruppe **Kampagnenmarketing – Besitzer** ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="57f7c-192">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>
    
- <span data-ttu-id="57f7c-193">Andere Benutzerkonten können nicht auf die Website oder die zugehörigen Ressourcen zugreifen, Sie können jedoch Zugriff auf die Website anfordern. Dabei wird eine E-Mail an das Postfach des ITAdmin1-Benutzerkontos gesendet.</span><span class="sxs-lookup"><span data-stu-id="57f7c-193">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>
    
<span data-ttu-id="57f7c-194">Konfigurieren Sie anschließend den Ordner „Dokumente“ der Kampagnenmarketing-Teamwebsite für die Bezeichnung „Vertraulich“.</span><span class="sxs-lookup"><span data-stu-id="57f7c-194">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="57f7c-195">Klicken Sie auf der Registerkarte **Kampagnenmarketing – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-195">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="57f7c-196">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-196">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="57f7c-197">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-197">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="57f7c-198">Wählen Sie unter **Einstellungen – Bezeichnung anwenden** die Option **Vertraulich**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-198">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>
    
<span data-ttu-id="57f7c-p103">Konfigurieren Sie als Nächstes eine Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP), die Benutzer benachrichtigt, wenn sie ein Dokument auf einer SharePoint Online-Teamwebsite mit der Bezeichnung „Vertraulich“ außerhalb der Organisation freigeben. Diese DLP-Richtlinie gilt für Ressourcen auf der Kampagnenmarketingwebsite.</span><span class="sxs-lookup"><span data-stu-id="57f7c-p103">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>
  
1. <span data-ttu-id="57f7c-201">Klicken Sie auf der Registerkarte **Microsoft Office-Homepage** im Browser auf die Kachel **Security &amp; Compliance**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-201">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="57f7c-202">Klicken Sie auf der Registerkarte **Security &amp; Compliance** in Ihrem Browser auf **Verhinderung von Datenverlust > Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-202">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="57f7c-203">Klicken Sie im Bereich **Verhinderung von Datenverlust** auf **+ Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-203">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="57f7c-204">Klicken Sie im Bereich **Mit einer Vorlage beginnen oder eine benutzerdefinierte Richtlinie erstellen** auf **Benutzerdefiniert**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-204">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="57f7c-205">Geben Sie im Bereich **Ihre Richtlinie benennen** den Namen **Bezeichnung „Vertraulich" - SharePoint Online-Teamwebsites** bei **Name** ein, und klicken Sie dann auf **Weiter**</span><span class="sxs-lookup"><span data-stu-id="57f7c-205">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="57f7c-206">Klicken Sie im Bereich **Speicherorte auswählen** auf **Bestimmte Speicherorte auswählen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-206">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="57f7c-207">Deaktivieren Sie in der Liste der Speicherorte **Exchange-E-Mail** und **OneDrive-Konten**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-207">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="57f7c-208">Klicken Sie im Bereich **Typen von vertraulichen Informationen anpassen, die geschützt werden sollen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-208">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="57f7c-209">In der **wählen Sie die Typen der Inhalte zum Schutz** Bereich, klicken Sie auf **hinzufügen** im Dropdown-Listenfeld, und klicken Sie dann auf **Etiketten**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-209">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="57f7c-210">Klicken Sie im Bereich **Bezeichnungen** auf **+ Hinzufügen**, wählen Sie die Bezeichnung **Vertraulich** aus, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-210">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="57f7c-211">Klicken Sie im Bereich **Typen des zu schützenden Inhalts auswählen** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-211">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="57f7c-212">Klicken Sie im Bereich **Customize the types of sensitive info you want to protect** (Anpassen der Typen an vertraulichen Informationen, die Sie schützen möchten) auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-212">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="57f7c-213">Klicken Sie im Bereich **What do you want to do if we detect sensitive info?** (Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?) auf **Customize the tip and email** (Den Tipp und die E-Mail anpassen).</span><span class="sxs-lookup"><span data-stu-id="57f7c-213">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="57f7c-214">Klicken Sie im Bereich **Customize policy tips and email notifications** (Anpassen der Richtlinientipps und der E-Mail-Benachrichtigungen) auf **Customize the policy tip text** (Den Tipptext der Richtlinie als nächstes anpassen).</span><span class="sxs-lookup"><span data-stu-id="57f7c-214">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="57f7c-215">Geben Sie Folgendes in das Textfeld ein, oder fügen Sie es ein:</span><span class="sxs-lookup"><span data-stu-id="57f7c-215">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="57f7c-p104">Wenn Sie eine Datei für einen Benutzer außerhalb der Organisation freigeben möchten, laden Sie die Datei herunter, und öffnen Sie sie. Klicken Sie auf „Datei“ > „Dokument schützen“ > „Mit Kennwort verschlüsseln“, und geben Sie dann ein sicheres Kennwort ein. Senden Sie das Kennwort in einer separaten E-Mail oder auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="57f7c-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="57f7c-219">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-219">Click **OK**.</span></span>
    
17. <span data-ttu-id="57f7c-220">Deaktivieren Sie im Fenster **Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?** das Kontrollkästchen **Freigeben blockieren und Zugriff auf freigegebene Inhalte einschränken**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-220">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>
    
18. <span data-ttu-id="57f7c-221">Klicken Sie im Bereich **Möchten Sie die Richtlinie aktivieren oder zunächst testen?** auf **Ja, Richtlinie aktivieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-221">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="57f7c-222">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-222">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
### <a name="campaign-strategy-team-site"></a><span data-ttu-id="57f7c-223">Teamwebsite für Kampagnenstrategie</span><span class="sxs-lookup"><span data-stu-id="57f7c-223">Campaign strategy team site</span></span>

<span data-ttu-id="57f7c-224">Führen Sie die folgenden Schritte durch, um eine isolierte, streng vertrauliche SharePoint Online-Teamwebsite für Kampagnenstrategieressourcen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="57f7c-224">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>
  
1. <span data-ttu-id="57f7c-225">Verwenden Sie, falls erforderlich, einen Browser auf Ihrem lokalen Computer, und melden Sie sich mit Ihrem globalen Administratorkonto beim Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) an.</span><span class="sxs-lookup"><span data-stu-id="57f7c-225">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="57f7c-226">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-226">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="57f7c-227">Klicken Sie in der neuen Registerkarte **SharePoint** in Ihrem Browser auf **+ Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-227">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="57f7c-228">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-228">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="57f7c-229">Geben Sie unter **Name der Teamwebsite** den Namen **Kampagnenstrategie** ein.</span><span class="sxs-lookup"><span data-stu-id="57f7c-229">In **Team site name**, type **Campaign strategy**.</span></span>
    
6. <span data-ttu-id="57f7c-230">Geben Sie unter **Beschreibung der Teamwebsite** den Text **SharePoint-Website für Kampagnenstrategie (streng vertraulich)** ein.</span><span class="sxs-lookup"><span data-stu-id="57f7c-230">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>
    
7.  <span data-ttu-id="57f7c-231">Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-231">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="57f7c-232">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-232">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="57f7c-233">Klicken Sie auf der neuen Registerkarte **Kampagnenstrategie** in Ihrem Browser auf der Symbolleiste auf das Symbol „Einstellungen“, und klicken Sie dann auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-233">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="57f7c-234">Klicken Sie im Bereich **Websiteberechtigungen** auf **Erweiterte Berechtigungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-234">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="57f7c-235">Klicken Sie auf der neuen Registerkarte **Berechtigungen** in Ihrem Browser auf **Einstellungen für Zugriffsrechteanforderungen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-235">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="57f7c-236">Deaktivieren Sie im Dialogfeld **Einstellungen für Zugriffsrechteanforderungen** die Optionen **Mitgliedern das Freigeben der Website sowie einzelner Dateien und Ordner erlauben** und **Mitgliedern das Einladen von anderen zur Websitemitglieder-Gruppe erlauben** (sodass alle drei Kontrollkästchen deaktiviert sind), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-236">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
13. <span data-ttu-id="57f7c-237">Klicken Sie in der Liste auf **Kampagnenstrategiemitglieder**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-237">Click **Campaign strategy Members** in the list.</span></span>
    
14. <span data-ttu-id="57f7c-238">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-238">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="57f7c-239">Geben Sie im Dialogfeld **Freigeben** **Senior-Mitarbeiter und strategische Mitarbeiter** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-239">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="57f7c-240">Klicken Sie in der Liste auf **Kampagnenstrategiebesitzer**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-240">Click **Campaign strategy Owners** in the list.</span></span>
    
17. <span data-ttu-id="57f7c-241">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-241">On the **People and Groups** page, click **New**.</span></span>
    
18. <span data-ttu-id="57f7c-242">Geben Sie im Dialogfeld **Freigeben** **IT-Mitarbeiter** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-242">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
19. <span data-ttu-id="57f7c-243">Klicken Sie auf die Schaltfläche „Zurück“ in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="57f7c-243">Click the back button on your browser.</span></span>
    
20. <span data-ttu-id="57f7c-244">Schließen Sie die Registerkarte **Benutzer und Gruppen** in Ihrem Browser, klicken Sie auf die Registerkarte **Kampagnenstrategie – Startseite** in Ihrem Browser, und schließen Sie dann den Bereich **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-244">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="57f7c-245">Nachfolgend finden Sie die Ergebnisse der Konfiguration von Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="57f7c-245">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="57f7c-246">Die SharePoint-Gruppe **Kampagnenstrategiemitglieder** enthält nur die Gruppen **Senior-Mitarbeiter und strategische Mitarbeiter** (mit den Candidate-, ChiefOfStaff- und die Strategic1-Benutzerkonten) und **Kampagnenstrategie** (nur mit dem globalen Administratorkonto).
</span><span class="sxs-lookup"><span data-stu-id="57f7c-246">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="57f7c-247">Die SharePoint-Gruppe **Kampagnenstrategie – Besitzer** enthält nur die Gruppe **IT-Mitarbeiter** (nur mit den ITAdmin1- und ITAdmin2-Benutzerkonten).</span><span class="sxs-lookup"><span data-stu-id="57f7c-247">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="57f7c-248">Die SharePoint-Gruppe **Kampagnenstrategie – Besucher** enthält keine Gruppen oder Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="57f7c-248">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="57f7c-249">Mitglieder können keine Berechtigungen auf Websiteebene ändern (dies kann nur von Mitgliedern der Gruppe **Kampagnenstrategie – Besitzer** ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="57f7c-249">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>
    
- <span data-ttu-id="57f7c-p105">Andere Benutzerkonten können nicht auf die Website oder ihre Ressourcen zugreifen oder Zugriff auf die Website anfordern. Zusätzliche Berechtigungen für die Website müssen vom globalen Administrator oder von einem Mitglied der Gruppe **Kampagnenstrategie – Besitzer** gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="57f7c-p105">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>
    
<span data-ttu-id="57f7c-252">Konfigurieren Sie anschließend den Ordner „Dokumente“ der Kampagnenstrategie-Teamwebsite für die Bezeichnung „Streng vertraulich“.</span><span class="sxs-lookup"><span data-stu-id="57f7c-252">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>
  
1. <span data-ttu-id="57f7c-253">Klicken Sie auf der Registerkarte **Kampagnenstrategie – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-253">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="57f7c-254">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-254">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="57f7c-255">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-255">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="57f7c-256">Wählen Sie unter **Einstellungen – Bezeichnung anwenden** die Option **Streng vertraulich**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-256">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>
    
<span data-ttu-id="57f7c-p106">Konfigurieren Sie als Nächstes eine DLP-Richtlinie, die Benutzer blockiert, wenn sie ein Dokument auf einer SharePoint Online-Teamwebsite mit der Bezeichnung „Streng vertraulich“ außerhalb der Organisation freigeben. Diese DLP-Richtlinie gilt für Ressourcen auf der Kampagnenstrategiewebsite.</span><span class="sxs-lookup"><span data-stu-id="57f7c-p106">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>
  
1. <span data-ttu-id="57f7c-259">Falls erforderlich, verwenden Sie einen Browser auf Ihrem lokalen Computer und melden Sie sich mit einem Konto beim Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) an, das über die Rolle „Sicherheitsadministrator“ oder „Unternehmensadministrator“ verfügt.</span><span class="sxs-lookup"><span data-stu-id="57f7c-259">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="57f7c-260">Klicken Sie auf der Registerkarte **Microsoft Office-Homepage** im Browser auf die Kachel **Security &amp; Compliance**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-260">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
3. <span data-ttu-id="57f7c-261">Klicken Sie auf der Registerkarte **Security &amp; Compliance** in Ihrem Browser auf **Verhinderung von Datenverlust > Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-261">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
4. <span data-ttu-id="57f7c-262">Klicken Sie im Bereich **Verhinderung von Datenverlust** auf **+ Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-262">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
5. <span data-ttu-id="57f7c-263">Klicken Sie im Bereich **Mit einer Vorlage beginnen oder eine benutzerdefinierte Richtlinie erstellen** auf **Benutzerdefiniert**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-263">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="57f7c-264">Geben Sie im Bereich **Ihre Richtlinie benennen** den Namen **Bezeichnung „Streng vertraulich" - SharePoint Online-Teamwebsites** bei **Name** ein, und klicken Sie dann auf **Weiter**</span><span class="sxs-lookup"><span data-stu-id="57f7c-264">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="57f7c-265">Klicken Sie im Bereich **Speicherorte auswählen** auf **Bestimmte Speicherorte auswählen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-265">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="57f7c-266">Deaktivieren Sie in der Liste der Speicherorte **Exchange-E-Mail** und **OneDrive-Konten**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-266">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
9. <span data-ttu-id="57f7c-267">Klicken Sie im Bereich **Typen von vertraulichen Informationen anpassen, die geschützt werden sollen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-267">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
10. <span data-ttu-id="57f7c-268">In der **wählen Sie die Typen der Inhalte zum Schutz** Bereich, klicken Sie auf **hinzufügen** im Dropdown-Listenfeld, und klicken Sie dann auf **Etiketten**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-268">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
11. <span data-ttu-id="57f7c-269">Klicken Sie im Bereich **Bezeichnungen** auf **+ Hinzufügen**, wählen Sie die Bezeichnung **Streng vertraulich** aus, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-269">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
12. <span data-ttu-id="57f7c-270">Klicken Sie im Bereich **Typen des zu schützenden Inhalts auswählen** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-270">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
13. <span data-ttu-id="57f7c-271">Klicken Sie im Bereich **Customize the types of sensitive info you want to protect** (Anpassen der Typen an vertraulichen Informationen, die Sie schützen möchten) auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-271">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="57f7c-272">Klicken Sie im Bereich **What do you want to do if we detect sensitive info?** (Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?) auf **Customize the tip and email** (Den Tipp und die E-Mail anpassen).</span><span class="sxs-lookup"><span data-stu-id="57f7c-272">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
15. <span data-ttu-id="57f7c-273">Klicken Sie im Bereich **Customize policy tips and email notifications** (Anpassen der Richtlinientipps und der E-Mail-Benachrichtigungen) auf **Customize the policy tip text** (Den Tipptext der Richtlinie als nächstes anpassen).</span><span class="sxs-lookup"><span data-stu-id="57f7c-273">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
16. <span data-ttu-id="57f7c-274">Geben Sie Folgendes in das Textfeld ein, oder fügen Sie es ein:</span><span class="sxs-lookup"><span data-stu-id="57f7c-274">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="57f7c-p107">Wenn Sie eine Datei für einen Benutzer außerhalb der Organisation freigeben möchten, laden Sie die Datei herunter, und öffnen Sie sie. Klicken Sie auf „Datei“ > „Dokument schützen“ > „Mit Kennwort verschlüsseln“, und geben Sie dann ein sicheres Kennwort ein. Senden Sie das Kennwort in einer separaten E-Mail oder auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="57f7c-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
17. <span data-ttu-id="57f7c-278">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-278">Click **OK**.</span></span>
    
18. <span data-ttu-id="57f7c-279">Wählen Sie im Bereich **Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?** die Option **Begründung für Außerkraftsetzung erforderlich**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-279">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="57f7c-280">Klicken Sie im Bereich **Möchten Sie die Richtlinie aktivieren oder zunächst testen?** auf **Ja, Richtlinie aktivieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-280">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
20. <span data-ttu-id="57f7c-281">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-281">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="57f7c-282">Befolgen Sie die Anweisungen unter [Aktivieren von Azure RMS mit dem Microsoft 365 Admin Center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="57f7c-282">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>
  
<span data-ttu-id="57f7c-283">Konfigurieren Sie als Nächstes Azure Information Protection mit einer neuen bereichsbezogenen Richtlinie und einer untergeordneten Bezeichnung für Schutz und Berechtigungen, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="57f7c-283">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>
  
1. <span data-ttu-id="57f7c-284">Melden Sie sich beim Admin Center mit einem Konto an, das über die Rolle „Sicherheitsadministrator" oder Unternehmensadministrator" verfügt.</span><span class="sxs-lookup"><span data-stu-id="57f7c-284">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="57f7c-285">Hilfe finden Sie unter [Where to sign in to Office 365 (Wo kann ich mich bei Office 365 anmelden?)](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="57f7c-285">For help, see [Where to sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="57f7c-286">Wechseln Sie auf einer separaten Registerkarte im Browser zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="57f7c-286">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
4. <span data-ttu-id="57f7c-287">Geben Sie im Suchfeld die **Information** ein, klicken Sie dann auf **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-287">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="57f7c-288">Klicken Sie auf **Etiketten**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-288">Click **Labels**.</span></span>
    
6. <span data-ttu-id="57f7c-289">Klicken Sie mit der rechten Maustaste auf die Bezeichnung **Streng vertraulich**, und klicken Sie dann auf **Unterbezeichnung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-289">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="57f7c-290">Geben Sie unter **Name** **Kampagnenstrategie** und unter **Beschreibung** **Bezeichnung für Dokumente in der Teamwebsite für Kampagnenstrategie** ein.</span><span class="sxs-lookup"><span data-stu-id="57f7c-290">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>
    
8. <span data-ttu-id="57f7c-291">Klicken Sie unter **Berechtigungen für Dokumente und E-Mails mit dieser Bezeichnung festlegen** auf **Schützen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-291">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="57f7c-292">Klicken Sie im Abschnitt **Schutz** auf **Azure (Cloudschlüssel)**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-292">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="57f7c-293">Klicken Sie im Blatt **Schützen** unter **Schutzeinstellungen** auf **+ Berechtigungen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-293">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>
    
11. <span data-ttu-id="57f7c-294">Klicken Sie auf dem Blatt **Berechtigungen hinzufügen** unter **Benutzer und Gruppen angeben** auf **+ Verzeichnis durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-294">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>
    
12. <span data-ttu-id="57f7c-295">Wählen Sie im Bereich **AAD-Benutzer und -Gruppen** die Option **Senior-Mitarbeiter und strategische Mitarbeiter**, und klicken Sie dann auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-295">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>
    
13. <span data-ttu-id="57f7c-296">Klicken Sie unter **Aus voreingestellten Berechtigungen wählen oder Benutzerdefiniert festlegen** auf **Benutzerdefiniert**, und aktivieren Sie dann die Kontrollkästchen **Rechte anzeigen**, **Inhalt bearbeiten**, \*\* Speichern\*\*, **Antworten** und **Allen antworten**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-296">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="57f7c-297">Klicken Sie zweimal auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-297">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="57f7c-298">Klicken Sie auf dem Blatt **Untergeordnete Bezeichnung** auf **Speichern** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-298">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="57f7c-299">Klicken Sie auf dem Blatt **Azure Information Protection** auf **Richtlinien > + Neue Richtlinie hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-299">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="57f7c-300">Geben Sie unter **Name** **Kampagnenstrategie** und unter **Beschreibung** **Dokumente in der Teamwebsite für Kampagnenstrategie** ein.</span><span class="sxs-lookup"><span data-stu-id="57f7c-300">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>
    
18. <span data-ttu-id="57f7c-301">Klicken Sie auf **Wählen Sie aus, welche Benutzer oder Gruppen diese Richtlinie erhalten. > Benutzer/Gruppen** und wählen Sie dann **Senior-Mitarbeiter und strategische Mitarbeiter**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-301">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>
    
19. <span data-ttu-id="57f7c-302">Klicken Sie auf **Auswählen > OK**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-302">Click **Select > OK**.</span></span>

20. <span data-ttu-id="57f7c-p109">Klicken Sie auf **Bezeichnungen hinzufügen oder entfernen**. Klicken Sie im Bereich **Richtlinie: Bezeichnungen hinzufügen oder entfernen** auf **Kampagnenstrategie** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-p109">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>   

21. <span data-ttu-id="57f7c-305">Klicken Sie auf **Speichern** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-305">Click **Save**, and then click **OK**.</span></span>
  
<span data-ttu-id="57f7c-306">Sie können jetzt mit dem Erstellen von Dokumenten in diesen vier Websites beginnen und den Zugriff mit verschiedenen Benutzerkonten testen.</span><span class="sxs-lookup"><span data-stu-id="57f7c-306">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span> 
  
<span data-ttu-id="57f7c-307">Um ein Dokument mit Azure Information Protection und mit dieser neuen Bezeichnung zu schützen, müssen Sie [den Azure Information Protection-Client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) auf einem Testcomputer installieren, Office vom Admin Center installieren und sich dann aus Microsoft Word mit einem Konto in der Gruppe **Senior-Mitarbeiter und strategische Mitarbeiter** Ihres Testabonnements anmelden.</span><span class="sxs-lookup"><span data-stu-id="57f7c-307">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="57f7c-308">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57f7c-308">See Also</span></span>

[<span data-ttu-id="57f7c-309">Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützigen Organisationen und andere agile Organisationen</span><span class="sxs-lookup"><span data-stu-id="57f7c-309">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="57f7c-310">Konfigurieren von Gruppen und Benutzern für eine politische Kampagne in einer Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="57f7c-310">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)
  
[<span data-ttu-id="57f7c-311">Testumgebungsanleitungen (TLGs) zur Cloudakzeptanz</span><span class="sxs-lookup"><span data-stu-id="57f7c-311">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="57f7c-312">Cloudakzeptanz und Hybridlösungen</span><span class="sxs-lookup"><span data-stu-id="57f7c-312">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




