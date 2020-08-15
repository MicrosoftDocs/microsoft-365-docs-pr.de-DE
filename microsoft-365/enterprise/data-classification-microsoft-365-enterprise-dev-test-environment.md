---
title: Datenklassifizierung für Ihre Microsoft 365 für Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Umgebungs Anleitung, um Aufbewahrungs Bezeichnungen für Dokumente in Ihrer Microsoft 365 for Enterprise-Testumgebung zu erstellen und zu verwenden.
ms.openlocfilehash: 171fcb74b09a1f2e5c80f23e010640dce55660bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686406"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="02834-103">Datenklassifizierung für Ihre Microsoft 365 für Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="02834-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="02834-104">*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="02834-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="02834-105">Mit den Anweisungen in diesem Artikel Konfigurieren Sie die Datenklassifizierung mithilfe von Aufbewahrungs Bezeichnungen in Ihrer Microsoft 365 for Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="02834-105">With the instructions in this article, you configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="02834-107">Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="02834-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="02834-108">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="02834-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="02834-109">Wenn Sie Aufbewahrungs Bezeichnungen nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="02834-109">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="02834-110">Wenn Sie Aufbewahrungs Bezeichnungen in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="02834-110">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="02834-111">Das Testen von Aufbewahrungs Bezeichnungen erfordert keine simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="02834-111">Testing retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="02834-112">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="02834-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="02834-113">Phase 2: Erstellen von Aufbewahrungs Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="02834-113">Phase 2: Create retention labels</span></span>

<span data-ttu-id="02834-114">In dieser Phase erstellen Sie die Aufbewahrungs Bezeichnungen für die unterschiedlichen Aufbewahrungs Ebenen für SharePoint Online Dokumentordner.</span><span class="sxs-lookup"><span data-stu-id="02834-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="02834-115">Melden Sie sich beim [Microsoft 365-Sicherheitscenter](https://security.microsoft.com/homepage) mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="02834-115">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
    
2. <span data-ttu-id="02834-116">Klicken Sie auf der Registerkarte " **Start-Microsoft 365 Security** " Ihres Browsers auf **Klassifizierung > Aufbewahrungs Bezeichnungen**.</span><span class="sxs-lookup"><span data-stu-id="02834-116">From the **Home - Microsoft 365 security** tab of your browser, click **Classification > Retention labels**.</span></span>
    
3. <span data-ttu-id="02834-117">Klicken Sie auf **Bezeichnung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="02834-117">Click **Create a label**.</span></span>
    
4. <span data-ttu-id="02834-118">Geben Sie im Bereich **Name Ihrer** Bezeichnung den Namen **internal Public** in **Name Your Label**ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="02834-118">In the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="02834-119">Klicken Sie im Bereich **Datei Plan Deskriptoren** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="02834-119">In the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="02834-120">Legen Sie im Bereich **Bezeichnungs Einstellungen** bei Bedarf **Retention** die Beibehaltung **auf ein**fest, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="02834-120">In the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="02834-121">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="02834-121">In the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="02834-122">Wiederholen Sie die Schritte 3 bis 7 für die zusätzlichen Bezeichnungen mit diesen Namen:</span><span class="sxs-lookup"><span data-stu-id="02834-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="02834-123">Private</span><span class="sxs-lookup"><span data-stu-id="02834-123">Private</span></span>
    
  - <span data-ttu-id="02834-124">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="02834-124">Sensitive</span></span>
    
  - <span data-ttu-id="02834-125">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="02834-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="02834-126">Klicken Sie im Bereich **Aufbewahrungs Bezeichnungen** auf **Bezeichnungen veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="02834-126">In the **Retention labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="02834-127">Klicken Sie im Bereich **zu veröffentlichende Bezeichnungen auswählen** auf **Bezeichnungen zur Veröffentlichung auswählen**.</span><span class="sxs-lookup"><span data-stu-id="02834-127">In the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="02834-128">Klicken Sie im Bereich **Beschriftungen auswählen** auf **Hinzufügen** , und wählen Sie alle vier Bezeichnungen aus.</span><span class="sxs-lookup"><span data-stu-id="02834-128">In the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="02834-129">Klicken Sie auf **Hinzufügen** und dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="02834-129">Click **Add**, and then click **Done**.</span></span>
    
13. <span data-ttu-id="02834-130">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="02834-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="02834-131">Klicken Sie im Bereich **Speicherorte auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="02834-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="02834-132">Geben Sie im Bereich **Richtlinie benennen** **Beispielorganisation** unter **Name** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="02834-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="02834-133">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnungen veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="02834-133">On the **Review your settings** pane, click **Publish labels**.</span></span>
 
<span data-ttu-id="02834-134">Beachten Sie, dass es einige Minuten dauern kann, bis die Aufbewahrungs Bezeichnungen veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="02834-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="02834-135">Phase 3: Anwenden von Aufbewahrungs Bezeichnungen auf Dokumente</span><span class="sxs-lookup"><span data-stu-id="02834-135">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="02834-136">In dieser Phase ermitteln Sie das Standardverhalten für die Aufbewahrungs Bezeichnung für Dateien im Ordner "Dokumente" einer SharePoint Online Website und ändern die Aufbewahrungs Bezeichnung eines Dokuments manuell.</span><span class="sxs-lookup"><span data-stu-id="02834-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="02834-137">Erstellen Sie zunächst eine SharePoint Online Teamwebsite auf sensibler Ebene:</span><span class="sxs-lookup"><span data-stu-id="02834-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="02834-138">Melden Sie sich mit einer privaten Instanz Ihres Browsers beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="02834-138">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
    
2. <span data-ttu-id="02834-139">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="02834-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="02834-140">Klicken Sie auf der neuen **SharePoint** -Registerkarte in Ihrem Browser auf **Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="02834-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="02834-141">Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.</span><span class="sxs-lookup"><span data-stu-id="02834-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="02834-142">Geben Sie unter **Name der Team Website den Namen** **SensitiveFiles**ein.</span><span class="sxs-lookup"><span data-stu-id="02834-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="02834-143">Geben Sie unter **Beschreibung der Team Website** **den Text SharePoint-Website für vertrauliche Dateien**ein.</span><span class="sxs-lookup"><span data-stu-id="02834-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="02834-144">Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="02834-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="02834-145">Klicken Sie im Bereich **Wen möchten Sie hinzufügen?** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="02834-145">In the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="02834-146">Konfigurieren Sie als nächstes den Ordner "Dokumente" der SensitiveFiles-Teamwebsite für die Bezeichnung für die vertrauliche Aufbewahrung.</span><span class="sxs-lookup"><span data-stu-id="02834-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="02834-147">Klicken Sie auf der Registerkarte **SensitiveFiles** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="02834-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="02834-148">Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="02834-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="02834-149">Klicken Sie unter **Berechtigungen und Verwaltung**auf **Bezeichnung auf Elemente in dieser Liste oder Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="02834-149">Under **Permissions and Management**, click **Apply label to items in this list or library**.</span></span> <span data-ttu-id="02834-150">Wenn diese Option nicht angezeigt wird, werden Ihre Aufbewahrungs Bezeichnungen noch nicht veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="02834-150">If this option does not appear, your retention labels are not yet published.</span></span> <span data-ttu-id="02834-151">Versuchen Sie diesen Schritt zu einem späteren Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="02834-151">Try this step at a later time.</span></span>
    
4. <span data-ttu-id="02834-152">Wählen Sie unter **Einstellungen – Bezeichnung anwenden**die Option **vertraulich** im Dropdownfeld aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="02834-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="02834-153">Erstellen Sie als nächstes ein neues Dokument auf der SensitiveFiles-Website, und ändern Sie dessen Aufbewahrungs Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="02834-153">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="02834-154">Klicken Sie im Ordner Dokumente auf **Neues > Word-Dokument**.</span><span class="sxs-lookup"><span data-stu-id="02834-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="02834-155">Geben Sie Text in das leere Dokument ein.</span><span class="sxs-lookup"><span data-stu-id="02834-155">Type some text in the blank document.</span></span> <span data-ttu-id="02834-156">Warten Sie, bis der Text gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="02834-156">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="02834-157">Klicken Sie in der Menüleiste auf **freigegebene Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="02834-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="02834-158">Klicken Sie auf die vertikalen Auslassungspunkte neben dem Namen der **Document.docx** Datei, und klicken Sie dann auf **Details**.</span><span class="sxs-lookup"><span data-stu-id="02834-158">Click the vertical ellipsis next to the **Document.docx** file name, and then click **Details**.</span></span>
    
5. <span data-ttu-id="02834-159">Beachten Sie im rechten Bereich im Abschnitt **Eigenschaften** unter **Aufbewahrungs Bezeichnung anwenden**, dass für das Dokument die Bezeichnung für die **vertrauliche** Aufbewahrung automatisch angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="02834-159">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
    
6. <span data-ttu-id="02834-160">Klicken Sie auf **Alle bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="02834-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="02834-161">Wählen Sie im Bereich **Document.docx** unter **Aufbewahrungs Bezeichnung anwenden**die Bezeichnung **streng vertraulich** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="02834-161">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="02834-162">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="02834-162">Next step</span></span>

<span data-ttu-id="02834-163">Untersuchen Sie zusätzliche Features und Funktionen für den [Informationsschutz](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="02834-163">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="02834-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02834-164">See also</span></span>

[<span data-ttu-id="02834-165">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="02834-165">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="02834-166">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="02834-166">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="02834-167">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="02834-167">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 
