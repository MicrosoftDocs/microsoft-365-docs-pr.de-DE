---
title: Klassifizierung von Daten für Ihr Unternehmen der Microsoft 365 test Environment.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Lab Guide erstellen und Verwenden von Office 365 Etiketten auf Dokumente in Ihrer testumgebung Microsoft 365 Enterprise.
ms.openlocfilehash: 656c1d0128a7b834ada04b674a60c03a731aa431
ms.sourcegitcommit: 42e4d280b562304335efc93787c89992504c5823
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26538642"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a8180-103">Klassifizierung von Daten für Ihr Unternehmen der Microsoft 365 test Environment.</span><span class="sxs-lookup"><span data-stu-id="a8180-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a8180-104">Mit den Anweisungen in diesem Artikel konfigurieren Sie mithilfe von Office 365 Bezeichnungen in Ihrer unternehmensumgebung Microsoft 365 Test Datenklassifikation.</span><span class="sxs-lookup"><span data-stu-id="a8180-104">With the instructions in this article, you configure data classification using Office 365 labels in your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="a8180-106">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a8180-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a8180-107">Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8180-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a8180-108">Wenn Sie Office 365 Beschriftungen auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="a8180-108">If you just want to configure Office 365 labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a8180-109">Wenn Sie Office 365 Bezeichnungen in einer simulierten Enterprise konfigurieren möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a8180-109">If you want to configure Office 365 labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a8180-p101">Testen Office 365 Etiketten erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit Sie automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="a8180-p101">Testing Office 365 labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="a8180-112">Phase 2: Erstellen von Office 365-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="a8180-112">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="a8180-113">In dieser Phase erstellen Sie die Beschriftungen für unterschiedlichen Sicherheitsebenen für SharePoint Online Dokumente Ordner.</span><span class="sxs-lookup"><span data-stu-id="a8180-113">In this phase, you create the labels for the different levels of security for SharePoint Online documents folders.</span></span>
  
1. <span data-ttu-id="a8180-p102">Falls erforderlich, verwenden Sie eine private Instanz des Internetbrowsers, und melden Sie sich das Office-Portal mit Ihrer globalen Administratorkonto an. Hilfe finden Sie unter [Where zur Anmeldung bei Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="a8180-p102">If needed, use a private instance of your Internet browser and sign in to the Office portal with your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="a8180-116">Klicken Sie auf der Registerkarte **Microsoft Office Home** auf die Kachel **Admin**.</span><span class="sxs-lookup"><span data-stu-id="a8180-116">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="a8180-117">Klicken Sie auf der neuen Registerkarte **Office Admin Center** im Browser auf **Admin Center > Security &amp; Compliance**.</span><span class="sxs-lookup"><span data-stu-id="a8180-117">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="a8180-118">Klicken Sie auf der neuen Registerkarte **Start - Security &amp; Compliance** im Browser auf **Klassifizierungen > Bezeichnungen**.</span><span class="sxs-lookup"><span data-stu-id="a8180-118">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="a8180-119">Klicken Sie im Bereich **Start > Bezeichnungen** auf **Bezeichnung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a8180-119">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="a8180-120">Geben Sie im Bereich **Name für Bezeichnung** **Intern Öffentlich** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8180-120">On the **Name your label** pane, type **Internal Public**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="a8180-121">Klicken Sie im Bereich **Bezeichnungseinstellungen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8180-121">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="a8180-122">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnung erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="a8180-122">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="a8180-123">Wiederholen Sie die Schritte 5 bis 8 für diese zusätzlichen Bezeichnungen:</span><span class="sxs-lookup"><span data-stu-id="a8180-123">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="a8180-124">Private</span><span class="sxs-lookup"><span data-stu-id="a8180-124">Private</span></span>
    
  - <span data-ttu-id="a8180-125">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="a8180-125">Sensitive</span></span>
    
  - <span data-ttu-id="a8180-126">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="a8180-126">Highly Confidential</span></span>
    
10. <span data-ttu-id="a8180-127">Klicken Sie im Bereich **Startseite > Bezeichnungen** auf **Bezeichnungen veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="a8180-127">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="a8180-128">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Zu veröffentlichende Bezeichnungen wählen**</span><span class="sxs-lookup"><span data-stu-id="a8180-128">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="a8180-129">Klicken Sie im Bereich **Choose labels** (Bezeichnungen auswählen) auf **Hinzufügen**, wählen Sie alle vier Bezeichnungen aus.</span><span class="sxs-lookup"><span data-stu-id="a8180-129">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="a8180-130">Klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="a8180-130">Click **Done**.</span></span>
    
14. <span data-ttu-id="a8180-131">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8180-131">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="a8180-132">Klicken Sie im Bereich **Speicherorte auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8180-132">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="a8180-133">Geben Sie im Bereich **Richtlinie benennen** **Beispielorganisation** unter **Name** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8180-133">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="a8180-134">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnungen veröffentlichen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="a8180-134">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

<span data-ttu-id="a8180-135">Beachten Sie, dass es ein paar Minuten für die Beschriftungen zu veröffentlichenden dauern kann.</span><span class="sxs-lookup"><span data-stu-id="a8180-135">Note that it might take a few minutes for the labels to be published.</span></span>

## <a name="phase-3-apply-office-365-labels-to-documents"></a><span data-ttu-id="a8180-136">Phase 3: Office 365 Etiketten auf Dokumente anwenden</span><span class="sxs-lookup"><span data-stu-id="a8180-136">Phase 3: Apply Office 365 labels to documents</span></span>

<span data-ttu-id="a8180-137">In dieser Phase ermitteln das Standardverhalten für die Beschriftung für Dateien im Ordner "Dokumente" einer SharePoint Online-Website und Manuelles Ändern der Beschriftung eines Dokuments.</span><span class="sxs-lookup"><span data-stu-id="a8180-137">In this phase, you discover the default label behavior for files in the Documents folder of a SharePoint Online site and manually change the label of a document.</span></span>

<span data-ttu-id="a8180-138">Erstellen Sie zunächst eine Sensitive-Ebene SharePoint Online-Teamwebsite:</span><span class="sxs-lookup"><span data-stu-id="a8180-138">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="a8180-p103">Melden Sie sich mit einem Browser auf dem lokalen Computer an, in das Office-Portal mit Ihrem Konto globaler Administrator. Hilfe finden Sie unter [Where zur Anmeldung bei Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="a8180-p103">Using a browser on your local computer, sign in to the Office portal using your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="a8180-141">Klicken Sie in der Liste von Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a8180-141">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="a8180-142">Klicken Sie auf der neuen Registerkarte **SharePoint** in Ihrem Browser auf **Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a8180-142">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="a8180-143">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="a8180-143">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="a8180-144">Geben Sie in das Feld **Teamname Website** **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="a8180-144">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="a8180-145">Geben Sie im Feld **websitebeschreibung Team** **SharePoint-Website für vertrauliche Dateien**.</span><span class="sxs-lookup"><span data-stu-id="a8180-145">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="a8180-146">Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8180-146">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="a8180-147">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a8180-147">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="a8180-148">Konfigurieren Sie anschließend den Dokumentenordner der Teamwebsite SensitiveFiles für die Bezeichnung vertrauliche.</span><span class="sxs-lookup"><span data-stu-id="a8180-148">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="a8180-149">Klicken Sie auf der Registerkarte **SensitiveFiles** Ihres Browsers auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="a8180-149">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="a8180-150">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="a8180-150">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="a8180-151">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="a8180-151">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="a8180-152">**Bezeichnung Einstellungen anwenden**wählen Sie im Dropdown- **vertrauliche** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a8180-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="a8180-153">Im nächsten Schritt erstellen Sie ein neues Dokument auf der Website SensitiveFiles, und ändern Sie dessen Beschriftung.</span><span class="sxs-lookup"><span data-stu-id="a8180-153">Next, create a new document in the SensitiveFiles site and change its label.</span></span>
    
1. <span data-ttu-id="a8180-154">Klicken Sie im Dokumentenordner auf **Neu > Word-Dokument**.</span><span class="sxs-lookup"><span data-stu-id="a8180-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="a8180-p104">Geben Sie Text in das leere Dokument. Warten Sie auf den Text gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a8180-p104">Type some text in the blank document. Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="a8180-157">Klicken Sie in der Menüleiste auf **Freigegebene Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="a8180-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="a8180-158">Klicken Sie auf das Word-Symbol neben dem Dateinamen **Document.docx** .</span><span class="sxs-lookup"><span data-stu-id="a8180-158">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="a8180-159">Beachten Sie im rechten Bereich, in den Abschnitt **Eigenschaften** unter **Übernehmen Label**, dass das Dokument die Bezeichnung des **vertrauliche** automatisch angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a8180-159">In the right-hand pane, in the **Properties** section, under **Apply label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="a8180-160">Klicken Sie auf **alle zu bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a8180-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="a8180-161">Wählen Sie im Bereich **Document.docx** unter **Übernehmen Beschriftung**die **Streng vertraulich** Beschriftung, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a8180-161">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="a8180-162">Finden Sie im Schritt [Configure Klassifizierung für Ihre Umgebung](data-classification-microsoft-365-enterprise-dev-test-environment.md) in der Phase **Information Protection** Informationen und Links zu Office 365 Bezeichnungen in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="a8180-162">See the [Configure classification for your environment](data-classification-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to Office 365 labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="a8180-163">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="a8180-163">Next step</span></span>

<span data-ttu-id="a8180-164">Hier finden Sie zusätzliche [Informationen Protection](m365-enterprise-test-lab-guides.md#information-protection) Features und Funktionen in Ihrer testumgebung.</span><span class="sxs-lookup"><span data-stu-id="a8180-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8180-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8180-165">See also</span></span>

[<span data-ttu-id="a8180-166">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8180-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a8180-167">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8180-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a8180-168">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8180-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 