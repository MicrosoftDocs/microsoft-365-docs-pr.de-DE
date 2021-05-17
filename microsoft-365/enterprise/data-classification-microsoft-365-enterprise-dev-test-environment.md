---
title: Datenklassifizierung für Microsoft 365 für Die Unternehmenstestumgebung
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
description: Verwenden Sie dieses Testumgebungshandbuch zum Erstellen und Verwenden von Aufbewahrungsbezeichnungen für Dokumente in Microsoft 365 Unternehmenstestumgebung.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919188"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="722a4-103">Datenklassifizierung für Microsoft 365 für Die Unternehmenstestumgebung</span><span class="sxs-lookup"><span data-stu-id="722a4-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="722a4-104">*Diese Testumgebungsanleitung kann sowohl für Microsoft 365 als auch für Office 365 Enterprise verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="722a4-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="722a4-105">In diesem Artikel wird beschrieben, wie Sie die Datenklassifizierung mithilfe von Aufbewahrungsbezeichnungen in Microsoft 365 Unternehmenstestumgebung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="722a4-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="722a4-106">Das Klassifizieren von Daten in Ihrer Testumgebung umfasst drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="722a4-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="722a4-107">Phase 1: Build out your Microsoft 365 for Enterprise test environment</span><span class="sxs-lookup"><span data-stu-id="722a4-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="722a4-108">Phase 2: Erstellen von Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="722a4-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="722a4-109">Phase 3: Anwenden von Aufbewahrungsbezeichnungen auf Dokumente</span><span class="sxs-lookup"><span data-stu-id="722a4-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="722a4-111">Eine visuelle Karte zu allen Artikeln im Stapel Microsoft 365 test lab guide für unternehmen finden Sie unter [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="722a4-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="722a4-112">Phase 1: Build out your Microsoft 365 for Enterprise test environment</span><span class="sxs-lookup"><span data-stu-id="722a4-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="722a4-113">Wenn Sie Aufbewahrungsbezeichnungen nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="722a4-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="722a4-114">Wenn Sie Aufbewahrungsbezeichnungen in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="722a4-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="722a4-115">Das Testen von Aufbewahrungsbezeichnungen erfordert keine simulierte Unternehmenstestumgebung, die ein simuliertes Intranet umfasst, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory Domain Services (AD DS)-Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="722a4-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="722a4-116">Es wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="722a4-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="722a4-117">Phase 2: Erstellen von Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="722a4-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="722a4-118">Erstellen Sie in dieser Phase die Aufbewahrungsbezeichnungen für die verschiedenen Aufbewahrungsebenen für SharePoint Onlinedokumentordner:</span><span class="sxs-lookup"><span data-stu-id="722a4-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="722a4-119">Melden Sie sich beim [Microsoft 365 Security Center](https://security.microsoft.com/homepage) mit Ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="722a4-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="722a4-120">Wählen Sie auf der **Registerkarte Microsoft 365 Ihres** Browsers die Option Klassifizierungsaufbewahrungsbezeichnungen   >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="722a4-121">Wählen Sie **Bezeichnung erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="722a4-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="722a4-122">Geben Sie **im Bereich** Bezeichnung benennen die Option **Internes Öffentliches** unter **Bezeichnung** benennen ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="722a4-123">Wählen Sie **im Bereich Dateiplandeskriptoren** die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="722a4-124">Legen Sie **im Bereich** Bezeichnungseinstellungen bei Bedarf **aufbewahrung** auf **Ein** und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="722a4-125">Wählen Sie **im Bereich Einstellungen überprüfen** die Option Bezeichnung erstellen **aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="722a4-126">Wiederholen Sie die Schritte 3 bis 7 für die zusätzlichen Bezeichnungen mit diesen Namen:</span><span class="sxs-lookup"><span data-stu-id="722a4-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="722a4-127">Private</span><span class="sxs-lookup"><span data-stu-id="722a4-127">Private</span></span>
  - <span data-ttu-id="722a4-128">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="722a4-128">Sensitive</span></span>
  - <span data-ttu-id="722a4-129">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="722a4-129">Highly Confidential</span></span>
1. <span data-ttu-id="722a4-130">Wählen Sie **im Bereich Aufbewahrungsbezeichnungen** die Option **Bezeichnungen veröffentlichen aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="722a4-131">Wählen Sie **im Bereich Zu veröffentlichende Bezeichnungen** auswählen die Option **Zu veröffentlichende Bezeichnungen auswählen aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="722a4-132">Wählen Sie **im Bereich Bezeichnungen** auswählen die Option **Hinzufügen** aus, und wählen Sie alle vier Bezeichnungen aus.</span><span class="sxs-lookup"><span data-stu-id="722a4-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="722a4-133">Wählen **Sie Hinzufügen** aus, und wählen Sie dann Fertig **aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="722a4-134">Wählen Sie **im Bereich Zu veröffentlichende Bezeichnungen** auswählen die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="722a4-135">Wählen Sie **im Bereich** Speicherorte auswählen die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="722a4-136">Geben Sie im Bereich Name **Ihrer Richtlinie** **beispielorganisation** in **Name** ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="722a4-137">Wählen Sie **im Bereich Einstellungen überprüfen** die Option **Bezeichnungen veröffentlichen aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="722a4-138">Es kann einige Minuten dauern, bis die Aufbewahrungsbezeichnungen veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="722a4-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="722a4-139">Phase 3: Anwenden von Aufbewahrungsbezeichnungen auf Dokumente</span><span class="sxs-lookup"><span data-stu-id="722a4-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="722a4-140">In dieser Phase ermitteln Sie das standardaufbewahrungsbezeichnungsverhalten für Dateien im Ordner Dokumente einer SharePoint Online-Website und ändern manuell die Aufbewahrungsbezeichnung eines Dokuments.</span><span class="sxs-lookup"><span data-stu-id="722a4-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="722a4-141">Erstellen Sie zunächst eine Website auf vertraulicher SharePoint Online-Teamwebsite:</span><span class="sxs-lookup"><span data-stu-id="722a4-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="722a4-142">Melden Sie sich mit einer privaten Instanz Ihres Browsers beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="722a4-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="722a4-143">Wählen Sie in der Liste der Kacheln **die Option SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="722a4-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="722a4-144">Wählen Sie auf **der registerkarte SharePoint** in Ihrem Browser Website erstellen **aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="722a4-145">Wählen Sie auf der Seite **Website erstellen** die Option **Teamwebsite** aus.</span><span class="sxs-lookup"><span data-stu-id="722a4-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="722a4-146">Geben Sie **im Feld Teamwebsitename** **sensitiveFiles ein.**</span><span class="sxs-lookup"><span data-stu-id="722a4-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="722a4-147">Geben Sie **im Feld Teamwebsitebeschreibung** SharePoint für vertrauliche **Dateien ein.**</span><span class="sxs-lookup"><span data-stu-id="722a4-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="722a4-148">Wählen **Sie unter** Datenschutzeinstellungen die Option Privat aus – nur Mitglieder können auf diese Website **zugreifen,** und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="722a4-149">Wählen Sie **im Wer, die Sie hinzufügen möchten?** die Option **Fertig stellen aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="722a4-150">Konfigurieren Sie als Nächstes den Ordner Dokumente der SensitiveFiles-Teamwebsite für die Bezeichnung "Vertrauliche Aufbewahrung".</span><span class="sxs-lookup"><span data-stu-id="722a4-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="722a4-151">Wählen Sie auf der **Registerkarte SensitiveFiles** Ihres Browsers Dokumente **aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="722a4-152">Wählen Sie **Einstellungen** Symbol aus, und wählen Sie dann **Bibliothekseinstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="722a4-153">Wählen **Sie unter Berechtigungen und Verwaltung** die Option Bezeichnung auf Elemente in dieser Liste oder Bibliothek anwenden **aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="722a4-154">Wenn diese Option nicht angezeigt wird, werden Ihre Aufbewahrungsbezeichnungen noch nicht veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="722a4-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="722a4-155">Versuchen Sie diesen Schritt zu einem späteren Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="722a4-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="722a4-156">Wählen **Einstellungen Im Dropdownfeld unter Bezeichnung** anwenden die Option **Vertraulich** aus, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="722a4-157">Erstellen Sie als Nächstes ein neues Dokument auf der SensitiveFiles-Website, und ändern Sie die Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="722a4-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="722a4-158">Wählen Sie im Ordner Dokumente die Option **Neues**  >  **Word-Dokument aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="722a4-159">Geben Sie text in das leere Dokument ein.</span><span class="sxs-lookup"><span data-stu-id="722a4-159">Enter some text in the blank document.</span></span> <span data-ttu-id="722a4-160">Warten Sie, bis der Text gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="722a4-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="722a4-161">Wählen Sie auf der Menüleiste **freigegebene Dokumente aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="722a4-162">Wählen Sie neben **Document.docx** Dateinamen die vertikalen Auslassungspunkte aus, und wählen Sie dann **Details aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="722a4-163">Beachten Sie im rechten Bereich im Abschnitt **Eigenschaften** unter **Aufbewahrungsbezeichnung** anwenden, dass für das Dokument automatisch die Aufbewahrungsbezeichnung **Vertraulich** angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="722a4-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="722a4-164">Klicken Sie auf **Alle bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="722a4-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="722a4-165">Wählen Sie **imDocument.docx** unter **Aufbewahrungsbezeichnung** anwenden die Bezeichnung **Streng vertraulich** aus, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="722a4-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="722a4-166">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="722a4-166">Next step</span></span>

<span data-ttu-id="722a4-167">Erkunden Sie [zusätzliche Features und](m365-enterprise-test-lab-guides.md#information-protection) Funktionen zum Schutz von Informationen in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="722a4-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="722a4-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="722a4-168">See also</span></span>

[<span data-ttu-id="722a4-169">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="722a4-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="722a4-170">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="722a4-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="722a4-171">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="722a4-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)