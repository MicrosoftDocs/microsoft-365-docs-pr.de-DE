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
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487732"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="f825c-103">Datenklassifizierung für Ihre Microsoft 365 für Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="f825c-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="f825c-104">*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="f825c-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="f825c-105">In diesem Artikel wird beschrieben, wie Sie die Datenklassifizierung mithilfe von Aufbewahrungs Bezeichnungen in Ihrer Microsoft 365 for Enterprise-Testumgebung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f825c-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="f825c-106">Das Klassifizieren von Daten in Ihrer Testumgebung umfasst drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="f825c-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="f825c-107">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="f825c-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="f825c-108">Phase 2: Erstellen von Aufbewahrungs Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="f825c-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="f825c-109">Phase 3: Anwenden von Aufbewahrungs Bezeichnungen auf Dokumente</span><span class="sxs-lookup"><span data-stu-id="f825c-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="f825c-111">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="f825c-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="f825c-112">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="f825c-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="f825c-113">Wenn Sie Aufbewahrungs Bezeichnungen nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f825c-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f825c-114">Wenn Sie Aufbewahrungs Bezeichnungen in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f825c-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f825c-115">Das Testen von Aufbewahrungs Bezeichnungen erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="f825c-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="f825c-116">Er wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="f825c-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="f825c-117">Phase 2: Erstellen von Aufbewahrungs Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="f825c-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="f825c-118">Erstellen Sie in dieser Phase die Aufbewahrungs Bezeichnungen für die unterschiedlichen Aufbewahrungs Ebenen für SharePoint Online Dokumentordner:</span><span class="sxs-lookup"><span data-stu-id="f825c-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="f825c-119">Melden Sie sich beim [Microsoft 365-Sicherheitscenter](https://security.microsoft.com/homepage) mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="f825c-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="f825c-120">Wählen Sie auf der Registerkarte **Home-Microsoft 365 Security** in Ihrem Browser **Klassifizierungs**  >  **Aufbewahrungs Bezeichnungen**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="f825c-121">Wählen Sie **Bezeichnung erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="f825c-122">Geben Sie im Bereich **Name Ihres Bezeichnungs** Felds **internal Public** in **Name Your Label**ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="f825c-123">Wählen Sie im Bereich **Datei Plan Deskriptoren** die Option **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="f825c-124">Legen Sie im Bereich **Bezeichnungs Einstellungen** bei Bedarf die Option **Aufbewahrung** auf **ein**fest, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="f825c-125">Wählen Sie im Bereich **Einstellungen überprüfen** **die Option Bezeichnung erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="f825c-126">Wiederholen Sie die Schritte 3 bis 7 für die zusätzlichen Bezeichnungen mit diesen Namen:</span><span class="sxs-lookup"><span data-stu-id="f825c-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="f825c-127">Private</span><span class="sxs-lookup"><span data-stu-id="f825c-127">Private</span></span>
  - <span data-ttu-id="f825c-128">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="f825c-128">Sensitive</span></span>
  - <span data-ttu-id="f825c-129">Streng vertraulich</span><span class="sxs-lookup"><span data-stu-id="f825c-129">Highly Confidential</span></span>
1. <span data-ttu-id="f825c-130">Wählen Sie im Bereich **Aufbewahrungs Bezeichnungen** die Option **Bezeichnungen veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="f825c-131">Wählen Sie im Bereich **zu veröffentlichende Bezeichnungen** auswählen die Option **zu veröffentlichende Bezeichnungen**auswählen aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="f825c-132">Wählen Sie im Bereich **Beschriftungen** auswählen die Option **Hinzufügen** aus, und wählen Sie alle vier Bezeichnungen aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="f825c-133">Wählen Sie **Hinzufügen**aus, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="f825c-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="f825c-134">Wählen Sie im Bereich **zu veröffentlichende Bezeichnungen auswählen** die Option **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="f825c-135">Wählen Sie im Bereich **Speicherorte** auswählen die Option **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="f825c-136">Geben Sie im Bereich **Name Ihrer Richtlinie** unter **Name**die **Beispielorganisation** ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="f825c-137">Wählen Sie im Bereich **Einstellungen überprüfen** die Option **Bezeichnungen veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="f825c-138">Es kann einige Minuten dauern, bis die Aufbewahrungs Bezeichnungen veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="f825c-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="f825c-139">Phase 3: Anwenden von Aufbewahrungs Bezeichnungen auf Dokumente</span><span class="sxs-lookup"><span data-stu-id="f825c-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="f825c-140">In dieser Phase ermitteln Sie das Standardverhalten für die Aufbewahrungs Bezeichnung für Dateien im Ordner "Dokumente" einer SharePoint Online Website und ändern die Aufbewahrungs Bezeichnung eines Dokuments manuell.</span><span class="sxs-lookup"><span data-stu-id="f825c-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="f825c-141">Erstellen Sie zunächst eine SharePoint Online Teamwebsite auf sensibler Ebene:</span><span class="sxs-lookup"><span data-stu-id="f825c-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="f825c-142">Melden Sie sich mit einer privaten Instanz Ihres Browsers beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="f825c-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="f825c-143">Wählen Sie in der Kachel Liste die Option **SharePoint**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="f825c-144">Wählen Sie auf der neuen **SharePoint** -Registerkarte in Ihrem Browser **Website erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="f825c-145">Wählen Sie auf der Seite **Website erstellen** die Option **Teamwebsite** aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="f825c-146">Geben Sie im Feld **Name der Team Website den Namen** **SensitiveFiles**ein.</span><span class="sxs-lookup"><span data-stu-id="f825c-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="f825c-147">Geben Sie im Feld **Beschreibung der Team Website** die Option **SharePoint-Website für vertrauliche Dateien**ein.</span><span class="sxs-lookup"><span data-stu-id="f825c-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="f825c-148">Wählen Sie unter **Datenschutzeinstellungen** **die Option Privat nur Mitglieder können auf diese Website zugreifen**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="f825c-149">Wählen Sie im Bereich **Wen möchten Sie hinzufügen?** die Option **Fertig stellen**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="f825c-150">Konfigurieren Sie als nächstes den Ordner "Dokumente" der SensitiveFiles-Teamwebsite für die Bezeichnung für die vertrauliche Aufbewahrung.</span><span class="sxs-lookup"><span data-stu-id="f825c-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="f825c-151">Wählen Sie auf der Registerkarte **SensitiveFiles** Ihres Browsers die Option **Dokumente**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="f825c-152">Wählen Sie das Symbol **Einstellungen** aus, und wählen Sie dann **Bibliothekseinstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="f825c-153">Wählen Sie unter **Berechtigungen und Verwaltung** **die Option Bezeichnung auf Elemente in dieser Liste oder Bibliothek anwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="f825c-154">Wenn diese Option nicht angezeigt wird, werden Ihre Aufbewahrungs Bezeichnungen noch nicht veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="f825c-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="f825c-155">Versuchen Sie diesen Schritt zu einem späteren Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="f825c-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="f825c-156">Wählen Sie unter **Einstellungen – Bezeichnung anwenden**die Option **vertraulich** im Dropdownfeld aus, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="f825c-157">Erstellen Sie als nächstes ein neues Dokument auf der SensitiveFiles-Website, und ändern Sie dessen Aufbewahrungs Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="f825c-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="f825c-158">Wählen Sie im Ordner Dokumente die Option **Neues**  >  **Word-Dokument**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="f825c-159">Geben Sie einen Text in das leere Dokument ein.</span><span class="sxs-lookup"><span data-stu-id="f825c-159">Enter some text in the blank document.</span></span> <span data-ttu-id="f825c-160">Warten Sie, bis der Text gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f825c-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="f825c-161">Wählen Sie in der Menüleiste **freigegebene Dokumente**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="f825c-162">Wählen Sie neben dem Namen der **Document.docx** Datei die vertikalen Auslassungspunkte aus, und wählen Sie dann **Details**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="f825c-163">Beachten Sie im rechten Bereich im Abschnitt **Eigenschaften** unter **Aufbewahrungs Bezeichnung anwenden**, dass für das Dokument die Aufbewahrungs Bezeichnung für **vertrauliche** Dokumente automatisch angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f825c-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="f825c-164">Klicken Sie auf **Alle bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f825c-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="f825c-165">Wählen Sie im Bereich **Document.docx** unter **Aufbewahrungs Bezeichnung anwenden**die Bezeichnung **streng vertraulich** aus, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="f825c-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="f825c-166">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f825c-166">Next step</span></span>

<span data-ttu-id="f825c-167">Untersuchen Sie zusätzliche Features und Funktionen für den [Informationsschutz](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="f825c-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f825c-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f825c-168">See also</span></span>

[<span data-ttu-id="f825c-169">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f825c-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f825c-170">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f825c-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f825c-171">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="f825c-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
