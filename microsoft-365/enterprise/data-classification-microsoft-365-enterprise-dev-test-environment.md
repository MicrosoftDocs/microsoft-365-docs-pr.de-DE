---
title: Datenklassifizierung für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Umgebungs Anleitung, um Office 365 Aufbewahrungs Bezeichnungen für Dokumente in Ihrer Microsoft 365 Enterprise-Testumgebung zu erstellen und zu verwenden.
ms.openlocfilehash: e0186bcfc786356b34aff45b1b1e67f54dd40001
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672661"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d7068-103">Datenklassifizierung für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d7068-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d7068-104">*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 Enterprise-als auch für Office 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="d7068-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="d7068-105">Mit den Anweisungen in diesem Artikel Konfigurieren Sie die Datenklassifizierung mithilfe Office 365 Aufbewahrungs Bezeichnungen in Ihrer Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="d7068-105">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="d7068-107">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d7068-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d7068-108">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d7068-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d7068-109">Wenn Sie nur Office 365 Aufbewahrungs Bezeichnungen auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d7068-109">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d7068-110">Wenn Sie Office 365 Aufbewahrungs Bezeichnungen in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d7068-110">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d7068-111">Für das Testen Office 365 Aufbewahrungs Bezeichnungen ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="d7068-111">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d7068-112">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="d7068-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="d7068-113">Phase 2: Erstellen von Office 365-Aufbewahrungs Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="d7068-113">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="d7068-114">In dieser Phase erstellen Sie die Aufbewahrungs Bezeichnungen für die unterschiedlichen Aufbewahrungs Ebenen für SharePoint Online Dokumentordner.</span><span class="sxs-lookup"><span data-stu-id="d7068-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="d7068-115">Melden Sie sich beim [Microsoft 365 Compliance-Portal](https://compliance.microsoft.com) mit Ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="d7068-115">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="d7068-116">Klicken Sie auf der Registerkarte \*\*Start – Microsoft 365 Compliance \*\* im Browser auf **Klassifizierungen > Bezeichnungen**.</span><span class="sxs-lookup"><span data-stu-id="d7068-116">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="d7068-117">Klicken Sie auf **Aufbewahrungsbezeichnung > Erstellen einer Bezeichnung**.</span><span class="sxs-lookup"><span data-stu-id="d7068-117">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="d7068-118">Geben Sie im Bereich **Name für Bezeichnung\*\*\*\*Intern Öffentlich** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d7068-118">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="d7068-119">Klicken Sie im Bereich **Dateiplanbeschreibungen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d7068-119">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="d7068-120">Legen Sie im Bereich **Bezeichnungseigenschaften**, falls erforderlich, **Aufbewahrung** auf **Ein** fest, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d7068-120">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="d7068-121">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Beschriftung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d7068-121">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="d7068-122">Wiederholen Sie die Schritte 3 bis 7 für die zusätzlichen Bezeichnungen mit diesen Namen:</span><span class="sxs-lookup"><span data-stu-id="d7068-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="d7068-123">Private</span><span class="sxs-lookup"><span data-stu-id="d7068-123">Private</span></span>
    
  - <span data-ttu-id="d7068-124">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="d7068-124">Sensitive</span></span>
    
  - <span data-ttu-id="d7068-125">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="d7068-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="d7068-126">Klicken Sie im Bereich **Startseite > Bezeichnungen** auf **Bezeichnungen veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="d7068-126">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="d7068-127">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Zu veröffentlichende Bezeichnungen wählen**</span><span class="sxs-lookup"><span data-stu-id="d7068-127">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="d7068-128">Klicken Sie im Bereich **Choose labels** (Bezeichnungen auswählen) auf **Hinzufügen**, wählen Sie alle vier Bezeichnungen aus.</span><span class="sxs-lookup"><span data-stu-id="d7068-128">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="d7068-129">Klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="d7068-129">Click **Done**.</span></span>
    
13. <span data-ttu-id="d7068-130">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d7068-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="d7068-131">Klicken Sie im Bereich **Speicherorte auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d7068-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="d7068-132">Geben Sie im Bereich **Richtlinie benennen** **Beispielorganisation** unter **Name** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d7068-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="d7068-133">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnungen veröffentlichen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d7068-133">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
 
<span data-ttu-id="d7068-134">Beachten Sie, dass es einige Minuten dauern kann, bis die Aufbewahrungs Bezeichnungen veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="d7068-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="d7068-135">Phase 3: anwenden Office 365 Aufbewahrungs Bezeichnungen auf Dokumente</span><span class="sxs-lookup"><span data-stu-id="d7068-135">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="d7068-136">In dieser Phase ermitteln Sie das Standardverhalten für die Aufbewahrungs Bezeichnung für Dateien im Ordner "Dokumente" einer SharePoint Online Website und ändern die Aufbewahrungs Bezeichnung eines Dokuments manuell.</span><span class="sxs-lookup"><span data-stu-id="d7068-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="d7068-137">Erstellen Sie zunächst eine SharePoint Online Teamwebsite auf sensibler Ebene:</span><span class="sxs-lookup"><span data-stu-id="d7068-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="d7068-138">Verwenden Sie einen Browser auf dem lokalen Computer, und melden Sie sich im [Office 365-Portal](https://portal.office.com) mit Ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="d7068-138">Using a browser on your local computer, sign in to the [Office 365 portal](https://portal.office.com) using your global administrator account.</span></span>
    
2. <span data-ttu-id="d7068-139">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d7068-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="d7068-140">Klicken Sie auf der neuen **SharePoint** -Registerkarte in Ihrem Browser auf **Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d7068-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="d7068-141">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="d7068-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="d7068-142">Geben Sie unter **Name der Team Website den Namen** **SensitiveFiles**ein.</span><span class="sxs-lookup"><span data-stu-id="d7068-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="d7068-143">Geben Sie unter **Beschreibung der Team Website** **den Text SharePoint-Website für vertrauliche Dateien**ein.</span><span class="sxs-lookup"><span data-stu-id="d7068-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="d7068-144">Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d7068-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d7068-145">Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d7068-145">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="d7068-146">Konfigurieren Sie als nächstes den Ordner "Dokumente" der SensitiveFiles-Teamwebsite für die Bezeichnung für die vertrauliche Aufbewahrung.</span><span class="sxs-lookup"><span data-stu-id="d7068-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="d7068-147">Klicken Sie auf der Registerkarte **SensitiveFiles** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="d7068-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="d7068-148">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d7068-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="d7068-149">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="d7068-149">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="d7068-150">Wählen Sie unter **Einstellungen – Bezeichnung anwenden**die Option **vertraulich** im Dropdownfeld aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d7068-150">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="d7068-151">Erstellen Sie als nächstes ein neues Dokument auf der SensitiveFiles-Website, und ändern Sie dessen Aufbewahrungs Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="d7068-151">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="d7068-152">Klicken Sie im Ordner Dokumente auf **Neues #a0 Word-Dokument**.</span><span class="sxs-lookup"><span data-stu-id="d7068-152">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="d7068-153">Geben Sie Text in das leere Dokument ein.</span><span class="sxs-lookup"><span data-stu-id="d7068-153">Type some text in the blank document.</span></span> <span data-ttu-id="d7068-154">Warten Sie, bis der Text gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="d7068-154">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="d7068-155">Klicken Sie in der Menüleiste auf **freigegebene Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="d7068-155">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="d7068-156">Klicken Sie auf das Word-Symbol neben dem Dateinamen **Document. docx** .</span><span class="sxs-lookup"><span data-stu-id="d7068-156">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="d7068-157">Beachten Sie im rechten Bereich im Abschnitt **Eigenschaften** unter **Aufbewahrungs Bezeichnung anwenden**, dass das **vertrauliche** Etikett automatisch auf das Dokument angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d7068-157">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="d7068-158">Klicken Sie auf **alle bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d7068-158">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="d7068-159">Wählen Sie im Bereich **Document. docx** unter **Bezeichnung anwenden**die Bezeichnung **streng vertraulich** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d7068-159">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="d7068-160">Informationen und Links zur Bereitstellung Office 365 Aufbewahrungs Bezeichnungen in der Produktionsumgebung finden Sie im Schritt [Konfigurieren der Klassifizierung für Ihre Umgebung](infoprotect-configure-classification.md) in der **Information Protection** -Phase.</span><span class="sxs-lookup"><span data-stu-id="d7068-160">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="d7068-161">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d7068-161">Next step</span></span>

<span data-ttu-id="d7068-162">Untersuchen Sie zusätzliche Features und Funktionen für den [Informationsschutz](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="d7068-162">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7068-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7068-163">See also</span></span>

[<span data-ttu-id="d7068-164">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d7068-164">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d7068-165">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d7068-165">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d7068-166">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d7068-166">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 