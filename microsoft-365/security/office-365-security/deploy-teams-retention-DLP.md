---
title: Schützen von Dateien in Teams mit Aufbewahrungsbezeichnungen und Schutz vor Datenverlust (DLP)
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Zusammenfassung: Wenden Sie Richtlinien von Aufbewahrungsbezeichnungen und der Verhinderung von Datenverlust (DLP) für Dateien in Teams mit unterschiedlichen Ebenen des Informationsschutzes an.'
ms.openlocfilehash: 94d8a02d0ea88fa8a05cd6a2c95a2db866d72fad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083399"
---
# <a name="protect-files-in-teams-with-retention-labels-and-dlp"></a><span data-ttu-id="83111-103">Schützen von Dateien in Teams mit Aufbewahrungsbezeichnungen und Schutz vor Datenverlust (DLP)</span><span class="sxs-lookup"><span data-stu-id="83111-103">Protect files in teams with retention labels and DLP</span></span>

 
<span data-ttu-id="83111-104">Verwenden Sie die Schritte in diesem Artikel, um Richtlinien für Aufbewahrungsbezeichnungen und der Verhinderung von Datenverlust (DLP) für grundlegende, vertrauliche und streng vertrauliche Teams und deren zugrunde liegende SharePoint-Websites zu entwerfen und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="83111-104">Use the steps in this article to design and deploy retention labels and data loss prevention (DLP) policies for baseline, sensitive, and highly confidential teams and their underlying SharePoint sites.</span></span> <span data-ttu-id="83111-105">Weitere Informationen zu diesen drei Schutzebenen finden Sie unter [Sichern von Dateien in Microsoft Teams](secure-files-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="83111-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="83111-106">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="83111-106">How this works</span></span>

1. <span data-ttu-id="83111-107">Erstellen Sie die gewünschten Aufbewahrungsbezeichnungen, und veröffentlichen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="83111-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="83111-108">Es kann bis zu 12 Stunden dauern, bis diese veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="83111-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="83111-109">Bearbeiten Sie für die gewünschten zugrunde liegenden SharePoint-Websites die Einstellungen für die Dokumentbibliothek, um die gewünschten Aufbewahrungsbezeichnungen auf Elemente in der Bibliothek anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="83111-109">For the desired underlying SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="83111-110">Erstellen Sie DLP-Richtlinien, um Aktionen basierend auf den Aufbewahrungsbezeichnungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="83111-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="83111-111">Wenn Benutzer ein Dokument zu der zugrunde liegenden SharePoint-Websitebibliothek hinzufügen, erhält das Dokument standardmäßig die zugewiesene Aufbewahrungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="83111-111">When users add a document to the underlying SharePoint site library for the team, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="83111-112">Benutzer können das die Bezeichnung bei Bedarf ändern.</span><span class="sxs-lookup"><span data-stu-id="83111-112">Users can change the label, if needed.</span></span> <span data-ttu-id="83111-113">Wenn ein Benutzer ein Dokument außerhalb der Organisation freigibt, prüft DLP, ob eine Bezeichnung zugewiesen ist und ergreift entsprechende Maßnahmen, wenn eine DLP-Richtlinie der Bezeichnung entspricht.</span><span class="sxs-lookup"><span data-stu-id="83111-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="83111-114">DLP sucht auch nach weiteren Richtlinienübereinstimmungen, z. B. das Schützen von Dateien mit Kreditkartennummern, wenn dieser Typ von Richtlinie konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="83111-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="83111-115">Aufbewahrungsbezeichnungen für Ihre zugrunde liegenden SharePoint Online-Websites</span><span class="sxs-lookup"><span data-stu-id="83111-115">Retention labels for your underlying SharePoint sites</span></span>

<span data-ttu-id="83111-116">Es gibt drei Phasen beim Erstellen und anschließenden Zuweisen von Aufbewahrungbezeichnungen zu zugrunde liegenden SharePoint Online-Teamwebsites.</span><span class="sxs-lookup"><span data-stu-id="83111-116">There are three phases to creating and then assigning retention labels to underlying SharePoint sites.</span></span>
  
### <a name="step-1-determine-the-retention-label-names"></a><span data-ttu-id="83111-117">Schritt 1: Bestimmen der Namen der Aufbewahrungsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="83111-117">Step 1: Determine the retention label names</span></span>

<span data-ttu-id="83111-118">In dieser Phase bestimmen Sie die Namen Ihrer Aufbewahrungsbezeichnungen für die vier Ebenen des Informationsschutzes, der auf zugrunde liegende SharePoint Online-Teamwebsites angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="83111-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to underlying SharePoint sites.</span></span> <span data-ttu-id="83111-119">Die folgende Tabelle listet die empfohlenen Namen für jede Ebene auf.</span><span class="sxs-lookup"><span data-stu-id="83111-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="83111-120">**Schutzebene von zugrunde liegenden SharePoint-Websites**</span><span class="sxs-lookup"><span data-stu-id="83111-120">**underlying SharePoint sites protection level**</span></span>|<span data-ttu-id="83111-121">**Bezeichnungsname**</span><span class="sxs-lookup"><span data-stu-id="83111-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="83111-122">Grundlegend-Öffentlich</span><span class="sxs-lookup"><span data-stu-id="83111-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="83111-123">Intern Öffentlich</span><span class="sxs-lookup"><span data-stu-id="83111-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="83111-124">Grundlegend-Privat</span><span class="sxs-lookup"><span data-stu-id="83111-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="83111-125">Private</span><span class="sxs-lookup"><span data-stu-id="83111-125">Private</span></span>  <br/> |
|<span data-ttu-id="83111-126">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="83111-126">Sensitive</span></span>  <br/> |<span data-ttu-id="83111-127">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="83111-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="83111-128">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="83111-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="83111-129">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="83111-129">Highly Confidential</span></span>  <br/> |
   
### <a name="step-2-create-the-retention-labels"></a><span data-ttu-id="83111-130">Schritt 2: Erstellen der Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="83111-130">Step 2: Create the retention labels</span></span>

<span data-ttu-id="83111-131">In dieser Phase erstellen und veröffentlichen Sie Ihre bestimmten Bezeichnungen für die unterschiedlichen Ebenen des Informationsschutzes.</span><span class="sxs-lookup"><span data-stu-id="83111-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="83111-132">Melden Sie sich mit einem Konto beim [Microsoft 365 Compliance-Portal](https://compliance.microsoft.com) an, das über die Rolle „Sicherheitsadministrator“ oder „Unternehmensadministrator“ verfügt.</span><span class="sxs-lookup"><span data-stu-id="83111-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="83111-133">Klicken Sie auf der Registerkarte \*\*Start – Microsoft 365 Compliance \*\* im Browser auf **Klassifizierungen > Bezeichnungen**.</span><span class="sxs-lookup"><span data-stu-id="83111-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="83111-134">Klicken Sie auf **Aufbewahrungsbezeichnung > Erstellen einer Bezeichnung**.</span><span class="sxs-lookup"><span data-stu-id="83111-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="83111-135">Geben Sie im Bereich zum **Benennen der Bezeichnung** den Namen für die Bezeichnung und eine Beschreibung für Administratoren und Benutzer ein, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="83111-136">Tragen Sie im Bereich **Dateiplanbeschreibungen** die erforderlichen Informationen ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="83111-137">Legen Sie im Bereich **Bezeichnungseigenschaften**, falls erforderlich, **Aufbewahrung** auf **Ein**, und konfigurieren Sie die Aufbewahrungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="83111-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="83111-138">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="83111-139">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Beschriftung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="83111-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="83111-140">Für die zusätzlichen Beschriftungen klicken Sie auf **Beschriftung erstellen**, und wiederholen Sie dann bei Bedarf die Schritte 3 bis 7 in diesem Verfahren.</span><span class="sxs-lookup"><span data-stu-id="83111-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 in this procedure as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="83111-141">Veröffentlichen neuer Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="83111-141">Publish your new labels</span></span>

<span data-ttu-id="83111-142">Führen Sie dann diese Schritte aus, um die neuen Aufbewahrungsbezeichnungen zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="83111-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="83111-143">Klicken Sie im Bereich **Bezeichnungen** auf die Registerkarte **Aufbewahrungsbezeichnungen**, und klicken Sie dann auf **Bezeichnungen veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="83111-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="83111-144">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Zu veröffentlichende Bezeichnungen wählen**.</span><span class="sxs-lookup"><span data-stu-id="83111-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="83111-145">Klicken Sie im Bereich **Bezeichnungen auswählen** auf **Hinzufügen**, wählen Sie alle vier Bezeichnungen aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="83111-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="83111-146">Klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="83111-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="83111-147">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="83111-148">Klicken Sie im Bereich **Speicherorte auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="83111-149">Geben Sie im Bereich zum **Benennen der Richtlinie** einen Namen für den Bezeichnungssatz unter **Name** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="83111-150">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnungen veröffentlichen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="83111-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="step-3-apply-the-retention-labels-to-your-underlying-sharepoint-sites"></a><span data-ttu-id="83111-151">Schritt 3: Anwenden der Aufbewahrungsbezeichnungen auf Ihre zugrunde liegenden SharePoint Online-Websites</span><span class="sxs-lookup"><span data-stu-id="83111-151">Step 3: Apply the retention labels to your underlying SharePoint sites</span></span>

<span data-ttu-id="83111-152">Verwenden Sie die Schritte, um die Aufbewahrungsbezeichnungen auf die Dokumentordner Ihrer zugrunde liegenden SharePoint Online-Websites anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="83111-152">Use these steps to apply the retention labels to the documents folders of your underlying SharePoint sites.</span></span>
  
1.  <span data-ttu-id="83111-153">Klicken Sie im Team auf **Dateien**, und klicken Sie dann auf **In SharePoint** öffnen.</span><span class="sxs-lookup"><span data-stu-id="83111-153">From the team, click **Files**, and then click **Open in SharePoint**.</span></span>

2. <span data-ttu-id="83111-154">Klicken Sie auf der Registerkarte für die SharePoint-Website Ihres Browsers auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="83111-154">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
3. <span data-ttu-id="83111-155">Klicken Sie auf das Symbol „Einstellungen“, und klicken Sie dann auf **Bibliothekseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="83111-155">Click the settings icon, and then click **Library settings**.</span></span>
    
4. <span data-ttu-id="83111-156">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="83111-156">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
5. <span data-ttu-id="83111-157">Wählen Sie unter **Einstellungen – Bezeichnung anwenden** die entsprechende Aufbewahrungsbezeichnung, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="83111-157">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
6. <span data-ttu-id="83111-158">Schließen Sie die Registerkarte für die SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="83111-158">Close the tab for the SharePoint site.</span></span>
    
7. <span data-ttu-id="83111-159">Wiederholen Sie die Schritte 1 bis 6, um Ihren zusätzlichen zugrunde liegenden SharePoint-Websites Aufbewahrungsbezeichnungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="83111-159">Repeat steps 1-6 to assign retention labels to your additional underlying SharePoint sites.</span></span>
    
<span data-ttu-id="83111-160">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="83111-160">Here is your resulting configuration.</span></span>
  
![Aufbewahrungsbezeichnungen für die vier Arten von zugrunde liegenden SharePoint-Teamwebsites.](../../media/retention-labels.png)
  
## <a name="dlp-policies-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="83111-162">DLP-Richtlinien für Ihre zugrunde liegenden SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="83111-162">DLP policies for your underlying SharePoint sites</span></span>

<span data-ttu-id="83111-163">Gehen Sie wie folgt vor, um eine DLP-Richtlinie zu konfigurieren, die Benutzer benachrichtigt, wenn sie ein Dokument auf einer zugrunde liegenden SharePoint-Website mit Benutzern außerhalb der Organisation teilen.</span><span class="sxs-lookup"><span data-stu-id="83111-163">Use these steps to configure a DLP policy that notifies users when they share a document on an underlying SharePoint site outside the organization.</span></span>

1. <span data-ttu-id="83111-164">Melden Sie sich mit einem Konto beim [Microsoft 365 Compliance-Portal](https://compliance.microsoft.com/) an, das über die Rolle „Sicherheitsadministrator“ oder „Unternehmensadministrator“ verfügt.</span><span class="sxs-lookup"><span data-stu-id="83111-164">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="83111-165">Klicken Sie auf der Registerkarte **Microsoft 365 Compliance** in Ihrem Browser auf **Richtlinien > Verhinderung von Datenverlust**.</span><span class="sxs-lookup"><span data-stu-id="83111-165">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="83111-166">Klicken Sie im Bereich **Verhinderung von Datenverlust** auf **Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="83111-166">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="83111-167">Klicken Sie im Bereich **Mit einer Vorlage beginnen oder eine benutzerdefinierte Richtlinie erstellen** auf **Benutzerdefiniert**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-167">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="83111-168">Geben Sie im Bereich **Benennen Sie Ihre Richtlinie** unter **Name** den Namen der DLP-Richtlinie für die Vertraulichkeitsebene ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-168">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="83111-169">Klicken Sie im Bereich **Speicherorte auswählen** auf **Bestimmte Speicherorte auswählen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-169">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="83111-170">Deaktivieren Sie in der Liste der Speicherorte **Exchange-E-Mail**, **OneDrive-Konten** und **Teams-Chat- und Kanalnachrichten**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-170">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="83111-171">Klicken Sie im Bereich **Anpassen des zu schützenden Inhaltstyps** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="83111-171">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="83111-172">In der **wählen Sie die Typen der Inhalte zum Schutz** Bereich, klicken Sie auf **hinzufügen** im Dropdown-Listenfeld, und klicken Sie dann auf **Aufbewahrungsbezeichnungen**.</span><span class="sxs-lookup"><span data-stu-id="83111-172">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="83111-173">Klicken Sie im Bereich **Aufbewahrungsbezeichnungen** auf **Hinzufügen**, wählen Sie die Bezeichnung **Vertraulich** aus, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="83111-173">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="83111-174">Klicken Sie im Bereich **Typen des zu schützenden Inhalts auswählen** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="83111-174">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="83111-175">Klicken Sie im Bereich **Anpassen des zu schützenden Inhaltstyps** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-175">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="83111-176">Klicken Sie im Bereich **Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?** auf **Richtlinientipptext anpassen**.</span><span class="sxs-lookup"><span data-stu-id="83111-176">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="83111-177">Klicken Sie im Bereich **Customize policy tips and email notifications** (Anpassen der Richtlinientipps und der E-Mail-Benachrichtigungen) auf **Customize the policy tip text** (Den Tipptext der Richtlinie als nächstes anpassen).</span><span class="sxs-lookup"><span data-stu-id="83111-177">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="83111-178">Geben Sie im Textfeld einen der folgenden Tipps ein:</span><span class="sxs-lookup"><span data-stu-id="83111-178">In the text box, type or paste in one of the following tips:</span></span>
    
  - <span data-ttu-id="83111-p106">Wenn Sie eine Datei für einen Benutzer außerhalb der Organisation freigeben möchten, laden Sie die Datei herunter, und öffnen Sie sie. Klicken Sie auf „Datei“ > „Dokument schützen“ > „Mit Kennwort verschlüsseln“, und geben Sie dann ein sicheres Kennwort ein. Senden Sie das Kennwort in einer separaten E-Mail oder auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="83111-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="83111-p107">Streng vertrauliche Dateien werden durch Verschlüsselung geschützt. Nur externe Benutzer, die Berechtigungen für diese Dateien von Ihrer IT-Abteilung erhalten haben, können diese lesen.</span><span class="sxs-lookup"><span data-stu-id="83111-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="83111-184">Sie können auch einen eigenen Tipp in Bezug auf die Richtlinie eingeben oder einfügen, der den Benutzern erläutert, wie sie Dateien außerhalb der Organisation freigeben.</span><span class="sxs-lookup"><span data-stu-id="83111-184">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="83111-185">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="83111-185">Click **OK**.</span></span>
    
17. <span data-ttu-id="83111-186">Klicken Sie im Bereich **Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-186">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="83111-187">Klicken Sie im Bereich **Möchten Sie die Richtlinie aktivieren oder zunächst testen?** auf **Ja, Richtlinie aktivieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-187">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="83111-188">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="83111-188">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="83111-189">Hier sehen Sie die sich ergebende Konfiguration für vertrauliche Teams.</span><span class="sxs-lookup"><span data-stu-id="83111-189">Here is your resulting configuration for sensitive teams.</span></span>
  
![DLP-Richtlinie für vertrauliche Teams, die die Aufbewahrungsbezeichnung „Vertraulich“ verwenden](../../media/retention-labels-sensitive-dlp.png)
  
<span data-ttu-id="83111-191">Gehen Sie wie folgt vor, um eine DLP-Richtlinie zu konfigurieren, die Benutzer blockiert, wenn sie ein Dokument auf einer zugrunde liegenden SharePoint-Website mit Benutzern außerhalb der Organisation teilen.</span><span class="sxs-lookup"><span data-stu-id="83111-191">Next, use these steps to configure a DLP policy that blocks users when they share a document on an underlying SharePoint site outside the organization.</span></span>
  
1. <span data-ttu-id="83111-192">Klicken Sie auf der Registerkarte **Microsoft 365 Compliance** in Ihrem Browser auf **Richtlinien > Verhinderung von Datenverlust**.</span><span class="sxs-lookup"><span data-stu-id="83111-192">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="83111-193">Klicken Sie im Bereich **Verhinderung von Datenverlust** auf **Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="83111-193">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="83111-194">Klicken Sie im Bereich **Mit einer Vorlage beginnen oder eine benutzerdefinierte Richtlinie erstellen** auf **Benutzerdefiniert**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-194">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="83111-195">Geben Sie im Bereich **Benennen Sie Ihre Richtlinie** unter **Name** den Namen der DLP-Richtlinie für die streng vertrauliche Ebene ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-195">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="83111-196">Klicken Sie im Bereich **Speicherorte auswählen** auf **Bestimmte Speicherorte auswählen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-196">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="83111-197">Deaktivieren Sie in der Liste der Speicherorte **Exchange-E-Mail**, **OneDrive-Konten** und **Teams-Chat- und Kanalnachrichten**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-197">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="83111-198">Klicken Sie im Bereich **Typen von vertraulichen Informationen anpassen, die geschützt werden sollen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="83111-198">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="83111-199">In der **wählen Sie die Typen der Inhalte zum Schutz** Bereich, klicken Sie auf **hinzufügen** im Dropdown-Listenfeld, und klicken Sie dann auf **Aufbewahrungsbezeichnungen**.</span><span class="sxs-lookup"><span data-stu-id="83111-199">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="83111-200">Klicken Sie im Bereich **Aufbewahrungsbezeichnungen** auf **Hinzufügen**, wählen Sie die Bezeichnung **Streng vertraulich** aus, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="83111-200">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="83111-201">Klicken Sie im Bereich **Typen des zu schützenden Inhalts auswählen** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="83111-201">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="83111-202">Klicken Sie im Bereich **Customize the types of sensitive info you want to protect** (Anpassen der Typen an vertraulichen Informationen, die Sie schützen möchten) auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-202">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="83111-203">Klicken Sie im Bereich **What do you want to do if we detect sensitive info?** (Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?) auf **Customize the tip and email** (Den Tipp und die E-Mail anpassen).</span><span class="sxs-lookup"><span data-stu-id="83111-203">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="83111-204">Klicken Sie im Bereich **Customize policy tips and email notifications** (Anpassen der Richtlinientipps und der E-Mail-Benachrichtigungen) auf **Customize the policy tip text** (Den Tipptext der Richtlinie als nächstes anpassen).</span><span class="sxs-lookup"><span data-stu-id="83111-204">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="83111-205">Geben Sie Folgendes in das Textfeld ein, oder fügen Sie es ein:</span><span class="sxs-lookup"><span data-stu-id="83111-205">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="83111-p108">Wenn Sie eine Datei für einen Benutzer außerhalb der Organisation freigeben möchten, laden Sie die Datei herunter, und öffnen Sie sie. Klicken Sie auf „Datei“ > „Dokument schützen“ > „Mit Kennwort verschlüsseln“, und geben Sie dann ein sicheres Kennwort ein. Senden Sie das Kennwort in einer separaten E-Mail oder auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="83111-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="83111-209">Sie können auch einen eigenen Tipp in Bezug auf die Richtlinie eingeben oder einfügen, der den Benutzern erläutert, wie sie Dateien außerhalb der Organisation freigeben.</span><span class="sxs-lookup"><span data-stu-id="83111-209">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="83111-210">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="83111-210">Click **OK**.</span></span>
    
17. <span data-ttu-id="83111-211">Klicken Sie im Bereich **Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?** unter **Erkennen, wenn eine bestimmte Menge personenbezogener Informationen auf einmal freigegeben wird** auf **Zugriff einschränken oder Inhalt verschlüsseln** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-211">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="83111-212">Klicken Sie im Bereich **Möchten Sie die Richtlinie aktivieren oder zunächst testen?** auf **Ja, Richtlinie aktivieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83111-212">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="83111-213">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="83111-213">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="83111-214">Hier sehen Sie die sich ergebende Konfiguration für streng vertrauliche Teams an.</span><span class="sxs-lookup"><span data-stu-id="83111-214">Here is your resulting configuration for high confidentiality team.</span></span>
  
![DLP-Richtlinie für ein streng vertrauliches Team mit der Aufbewahrungsbezeichnung „Streng vertraulich“](../../media/retention-labels-highly-confidential-dlp.png)
  
## <a name="next-step"></a><span data-ttu-id="83111-216">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="83111-216">Next step</span></span>

[<span data-ttu-id="83111-217">Schützen von Dateien in Teams mit Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="83111-217">Protect files in teams with sensitivity labels</span></span>](deploy-teams-sensitivity-labels.md)
    
## <a name="see-also"></a><span data-ttu-id="83111-218">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83111-218">See Also</span></span>

[<span data-ttu-id="83111-219">Sichern von Dateien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="83111-219">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="83111-220">Cloudakzeptanz und Hybridlösungen</span><span class="sxs-lookup"><span data-stu-id="83111-220">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


