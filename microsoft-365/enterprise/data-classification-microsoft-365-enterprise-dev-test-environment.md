---
title: Klassifizierung von Daten für Ihr Unternehmen der Microsoft 365 test Environment.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Lab Guide erstellen und Verwenden von Office 365 Etiketten auf Dokumente in Ihrer testumgebung Microsoft 365 Enterprise.
ms.openlocfilehash: 33ac1fa8e26c0037882e6c240cc04ec19e6a6a7b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868173"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="767c2-103">Klassifizierung von Daten für Ihr Unternehmen der Microsoft 365 test Environment.</span><span class="sxs-lookup"><span data-stu-id="767c2-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="767c2-104">Mit den Anweisungen in diesem Artikel konfigurieren Sie mithilfe von Office 365 Aufbewahrung Bezeichnungen in Ihrer unternehmensumgebung Microsoft 365 Test Datenklassifikation.</span><span class="sxs-lookup"><span data-stu-id="767c2-104">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="767c2-106">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="767c2-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="767c2-107">Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="767c2-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="767c2-108">Wenn Sie Office 365 Beschriftungen auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="767c2-108">If you just want to configure Office 365 labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="767c2-109">Wenn Sie Office 365 Bezeichnungen in einer simulierten Enterprise konfigurieren möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="767c2-109">If you want to configure Office 365 labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="767c2-p101">Testen Office 365 Etiketten erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit Sie automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="767c2-p101">Testing Office 365 labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="767c2-112">Phase 2: Erstellen von Office 365-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="767c2-112">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="767c2-113">In dieser Phase erstellen Sie die Beschriftungen für die verschiedenen Berechtigungsstufen Aufbewahrung für SharePoint Online Dokumente Ordner.</span><span class="sxs-lookup"><span data-stu-id="767c2-113">In this phase, you create the labels for the different levels of retention for SharePoint Online documents folders.</span></span>
  
1. <span data-ttu-id="767c2-p102">Falls erforderlich, verwenden Sie eine private Instanz des Internetbrowsers, und melden Sie sich das Office-Portal mit Ihrer globalen Administratorkonto an. Hilfe finden Sie unter [Where zur Anmeldung bei Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="767c2-p102">If needed, use a private instance of your Internet browser and sign in to the Office portal with your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="767c2-116">Klicken Sie auf der Registerkarte **Microsoft Office Home** auf die Kachel **Admin**.</span><span class="sxs-lookup"><span data-stu-id="767c2-116">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="767c2-117">Klicken Sie auf der neuen Registerkarte **Office Admin Center** im Browser auf **Admin Center > Security &amp; Compliance**.</span><span class="sxs-lookup"><span data-stu-id="767c2-117">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="767c2-p103">Von der neuen **Home - Sicherheit &amp; Compliance** Registerkarte des Browsers, klicken Sie auf **Klassifikationen > Etiketten**. Aus der **Home > Etiketten** Bereich, klicken Sie auf der Registerkarte **Archivierung** .</span><span class="sxs-lookup"><span data-stu-id="767c2-p103">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**. From the **Home > Labels** pane, click the **Retention** tab.</span></span>
    
5. <span data-ttu-id="767c2-120">Klicken Sie auf **eine Beschriftung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="767c2-120">Click **Create a label**.</span></span>
    
6. <span data-ttu-id="767c2-121">Geben Sie im Bereich **Name für Bezeichnung** **Intern Öffentlich** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="767c2-121">On the **Name your label** pane, type **Internal Public**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="767c2-122">Klicken Sie im Bereich **Bezeichnungseinstellungen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="767c2-122">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="767c2-123">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnung erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="767c2-123">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="767c2-124">Wiederholen Sie die Schritte 5 bis 8 für diese zusätzlichen Bezeichnungen:</span><span class="sxs-lookup"><span data-stu-id="767c2-124">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="767c2-125">Private</span><span class="sxs-lookup"><span data-stu-id="767c2-125">Private</span></span>
    
  - <span data-ttu-id="767c2-126">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="767c2-126">Sensitive</span></span>
    
  - <span data-ttu-id="767c2-127">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="767c2-127">Highly Confidential</span></span>
    
10. <span data-ttu-id="767c2-128">Klicken Sie im Bereich **Startseite > Bezeichnungen** auf **Bezeichnungen veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="767c2-128">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="767c2-129">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Zu veröffentlichende Bezeichnungen wählen**</span><span class="sxs-lookup"><span data-stu-id="767c2-129">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="767c2-130">Klicken Sie im Bereich **Choose labels** (Bezeichnungen auswählen) auf **Hinzufügen**, wählen Sie alle vier Bezeichnungen aus.</span><span class="sxs-lookup"><span data-stu-id="767c2-130">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="767c2-131">Klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="767c2-131">Click **Done**.</span></span>
    
14. <span data-ttu-id="767c2-132">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="767c2-132">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="767c2-133">Klicken Sie im Bereich **Speicherorte auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="767c2-133">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="767c2-134">Geben Sie im Bereich **Richtlinie benennen** **Beispielorganisation** unter **Name** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="767c2-134">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="767c2-135">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnungen veröffentlichen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="767c2-135">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

<span data-ttu-id="767c2-136">Beachten Sie, dass es ein paar Minuten für die Beschriftungen zu veröffentlichenden dauern kann.</span><span class="sxs-lookup"><span data-stu-id="767c2-136">Note that it might take a few minutes for the labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="767c2-137">Phase 3: Office 365 Aufbewahrung Etiketten auf Dokumente anwenden</span><span class="sxs-lookup"><span data-stu-id="767c2-137">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="767c2-138">In dieser Phase ermitteln das Standardverhalten für die Beschriftung für Dateien im Ordner "Dokumente" einer SharePoint Online-Website und Manuelles Ändern der Beschriftung eines Dokuments.</span><span class="sxs-lookup"><span data-stu-id="767c2-138">In this phase, you discover the default label behavior for files in the Documents folder of a SharePoint Online site and manually change the label of a document.</span></span>

<span data-ttu-id="767c2-139">Erstellen Sie zunächst eine Sensitive-Ebene SharePoint Online-Teamwebsite:</span><span class="sxs-lookup"><span data-stu-id="767c2-139">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="767c2-p104">Melden Sie sich mit einem Browser auf dem lokalen Computer an, in das Office-Portal mit Ihrem Konto globaler Administrator. Hilfe finden Sie unter [Where zur Anmeldung bei Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="767c2-p104">Using a browser on your local computer, sign in to the Office portal using your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="767c2-142">Klicken Sie in der Liste von Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="767c2-142">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="767c2-143">Klicken Sie auf der neuen Registerkarte **SharePoint** in Ihrem Browser auf **Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="767c2-143">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="767c2-144">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="767c2-144">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="767c2-145">Geben Sie in das Feld **Teamname Website** **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="767c2-145">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="767c2-146">Geben Sie im Feld **websitebeschreibung Team** **SharePoint-Website für vertrauliche Dateien**.</span><span class="sxs-lookup"><span data-stu-id="767c2-146">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="767c2-147">Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="767c2-147">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="767c2-148">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="767c2-148">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="767c2-149">Konfigurieren Sie anschließend den Dokumentenordner der Teamwebsite SensitiveFiles für die Bezeichnung vertrauliche.</span><span class="sxs-lookup"><span data-stu-id="767c2-149">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="767c2-150">Klicken Sie auf der Registerkarte **SensitiveFiles** Ihres Browsers auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="767c2-150">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="767c2-151">Klicken Sie auf das Symbol „Einstellungen“, und klicken Sie dann auf **Bibliothekseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="767c2-151">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="767c2-152">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="767c2-152">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="767c2-153">**Bezeichnung Einstellungen anwenden**wählen Sie im Dropdown- **vertrauliche** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="767c2-153">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="767c2-154">Im nächsten Schritt erstellen Sie ein neues Dokument auf der Website SensitiveFiles, und ändern Sie dessen Beschriftung.</span><span class="sxs-lookup"><span data-stu-id="767c2-154">Next, create a new document in the SensitiveFiles site and change its label.</span></span>
    
1. <span data-ttu-id="767c2-155">Klicken Sie im Dokumentenordner auf **Neu > Word-Dokument**.</span><span class="sxs-lookup"><span data-stu-id="767c2-155">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="767c2-p105">Geben Sie Text in das leere Dokument. Warten Sie auf den Text gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="767c2-p105">Type some text in the blank document. Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="767c2-158">Klicken Sie in der Menüleiste auf **Freigegebene Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="767c2-158">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="767c2-159">Klicken Sie auf das Word-Symbol neben dem Dateinamen **Document.docx** .</span><span class="sxs-lookup"><span data-stu-id="767c2-159">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="767c2-160">Beachten Sie im rechten Bereich, in den Abschnitt **Eigenschaften** unter **Übernehmen Aufbewahrung Label**, dass das Dokument die Bezeichnung des **vertrauliche** automatisch angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="767c2-160">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="767c2-161">Klicken Sie auf **alle zu bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="767c2-161">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="767c2-162">Wählen Sie im Bereich **Document.docx** unter **Übernehmen Beschriftung**die **Streng vertraulich** Beschriftung, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="767c2-162">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="767c2-163">Finden Sie im Schritt [Configure Klassifizierung für Ihre Umgebung](infoprotect-configure-classification.md) in der Phase **Information Protection** Informationen und Links zu Office 365 Aufbewahrung Bezeichnungen in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="767c2-163">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="767c2-164">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="767c2-164">Next step</span></span>

<span data-ttu-id="767c2-165">Hier finden Sie zusätzliche [Informationen Protection](m365-enterprise-test-lab-guides.md#information-protection) Features und Funktionen in Ihrer testumgebung.</span><span class="sxs-lookup"><span data-stu-id="767c2-165">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="767c2-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="767c2-166">See also</span></span>

[<span data-ttu-id="767c2-167">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="767c2-167">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="767c2-168">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="767c2-168">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="767c2-169">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="767c2-169">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 