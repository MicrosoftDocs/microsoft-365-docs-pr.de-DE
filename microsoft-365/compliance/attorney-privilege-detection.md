---
title: Einrichten der Erkennung von Anwalts Mandanten-Berechtigungen in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Verwenden Sie das Erkennungs Modell für Anwalts Client-Berechtigungen, um die Computer Lern basierte Erkennung von privilegierten Inhalten zu verwenden, wenn Inhalte in einem erweiterten eDiscovery-Fall überprüft werden.
ms.openlocfilehash: e8e64fac2994b515bf6bc582673fa7e47d427d02
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528390"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="99d82-103">Einrichten der Erkennung von Anwalts Mandanten-Berechtigungen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="99d82-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="99d82-104">Ein wichtiger und kostspieliger Aspekt der Überprüfungsphase eines eDiscovery-Prozesses besteht darin, Dokumente für privilegierte Inhalte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="99d82-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="99d82-105">Advanced eDiscovery bietet eine maschinelle Lern basierte Erkennung von privilegierten Inhalten, um diesen Prozess effizienter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="99d82-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="99d82-106">Dieses Feature wird als *Anwalts Client-Berechtigungs Erkennung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="99d82-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="99d82-107">Wie funktioniert das?</span><span class="sxs-lookup"><span data-stu-id="99d82-107">How does it work?</span></span>

<span data-ttu-id="99d82-108">Wenn die Erkennung der Anwalts-Client-Rechte aktiviert ist, werden alle Dokumente in einem Überprüfungs Satzes vom Anwalt-Client-Berechtigungs Erkennungs Modell verarbeitet, wenn Sie [die Daten](analyzing-data-in-review-set.md) im Überprüfungspaket analysieren.</span><span class="sxs-lookup"><span data-stu-id="99d82-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="99d82-109">Das Modell sucht zwei Dinge:</span><span class="sxs-lookup"><span data-stu-id="99d82-109">The model looks for two things:</span></span>

- <span data-ttu-id="99d82-110">Privilegierte Inhalte – das Modell verwendet Maschinelles Lernen, um die Wahrscheinlichkeit zu ermitteln, dass das Dokumentinhalte enthält, die in der Natur legal sind.</span><span class="sxs-lookup"><span data-stu-id="99d82-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="99d82-111">Teilnehmer – im Rahmen der Einrichtung der Anwalts-Client-Berechtigungs Erkennung müssen Sie eine Liste der Anwälte für Ihre Organisation übermitteln.</span><span class="sxs-lookup"><span data-stu-id="99d82-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="99d82-112">Das Modell vergleicht dann die Teilnehmer des Dokuments mit der anwaltsliste, um festzustellen, ob ein Dokument mindestens einen Anwalts Teilnehmer hat.</span><span class="sxs-lookup"><span data-stu-id="99d82-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="99d82-113">Das Modell erzeugt für jedes Dokument die folgenden drei Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="99d82-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="99d82-114">**AttorneyClientPrivilegeScore:** Die Wahrscheinlichkeit, dass das Dokument in der Natur legal ist; die Werte für die Partitur liegen zwischen **0** und **1**.</span><span class="sxs-lookup"><span data-stu-id="99d82-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="99d82-115">**HasAttorney:** Diese Eigenschaft wird auf **true** festgelegt, wenn einer der Dokument Teilnehmer in der anwaltsliste aufgeführt ist; Andernfalls ist der Wert **false**.</span><span class="sxs-lookup"><span data-stu-id="99d82-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="99d82-116">Der Wert ist auch auf " **false** " festgelegt, wenn Ihre Organisation keine anwaltsliste hochgeladen hat.</span><span class="sxs-lookup"><span data-stu-id="99d82-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="99d82-117">**Isprivilege:** Diese Eigenschaft wird auf **true** festgelegt, wenn der Wert für **AttorneyClientPrivilegeScore** oberhalb des Schwellenwerts liegt *oder* wenn das Dokument über einen Anwalts Teilnehmer verfügt; Andernfalls wird der Wert auf **false**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="99d82-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="99d82-118">Diese Eigenschaften (und die entsprechenden Werte) werden den Datei Metadaten der Dokumente in einem Überprüfungs Satzes hinzugefügt, wie im folgenden Screenshot dargestellt:</span><span class="sxs-lookup"><span data-stu-id="99d82-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![In Datei Metadaten angezeigte Anwalts-Client-Berechtigungs Eigenschaften](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="99d82-120">Diese drei Eigenschaften können auch innerhalb eines Überprüfungs Satzes durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="99d82-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="99d82-121">Weitere Informationen finden Sie unter [Abfragen der Daten in einem Überprüfungs Satzes](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="99d82-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="99d82-122">Einrichten des Erkennungs Modells für Anwalts Client-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="99d82-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="99d82-123">Um das Erkennungs Modell für das Attorney-Client-Privileg zu aktivieren, muss Ihre Organisation es aktivieren und dann eine anwaltsliste hochladen.</span><span class="sxs-lookup"><span data-stu-id="99d82-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="99d82-124">Schritt 1: Aktivieren der Erkennung der Anwalts Client-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="99d82-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="99d82-125">Eine Person, die ein eDiscovery-Administrator in Ihrer Organisation ist (ein Mitglied der Untergruppe eDiscovery Administrator in der Rollengruppe eDiscovery-Manager), muss das Modell in ihren erweiterten eDiscovery-Fällen verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="99d82-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="99d82-126">Wechseln Sie im Security & Compliance Center zu **eDiscovery > Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="99d82-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="99d82-127">Klicken Sie auf der Seite für die **Erweiterte eDiscovery** -Homepage auf der Kachel **Einstellungen** auf **globale Analyse Einstellungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="99d82-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   ![Wählen Sie "experimentelle Features konfigurieren" aus.](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="99d82-129">Wählen Sie auf der Registerkarte **Analytics-Einstellungen** die Option **Attorney-Client-Berechtigungen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="99d82-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="99d82-130">Verwenden Sie auf der Seite " **Attorney-Client-Privilege-** Flyout" die Umschaltfläche, um das Feature zu aktivieren, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="99d82-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="99d82-131">Schritt 2: Hochladen einer Liste von Anwälten (optional)</span><span class="sxs-lookup"><span data-stu-id="99d82-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="99d82-132">Um das Erkennungs Modell "Attorney-Client-Berechtigung" vollständig zu nutzen und die Ergebnisse des " **hat Attorney** " oder der **potenziell privilegierten** Erkennung zu verwenden, die zuvor beschrieben wurde, wird empfohlen, eine Liste mit e-Mail-Adressen für die Anwälte und das juristische Personal hochzuladen, die für Ihre Organisation arbeiten.</span><span class="sxs-lookup"><span data-stu-id="99d82-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="99d82-133">So laden Sie eine anwaltsliste für das Erkennungs Modell "Attorney-Client-Berechtigung" hoch:</span><span class="sxs-lookup"><span data-stu-id="99d82-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="99d82-134">Erstellen Sie eine CSV-Datei (ohne Kopfzeile), und fügen Sie die e-Mail-Adresse für jede entsprechende Person in einer separaten Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="99d82-134">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="99d82-135">Speichern Sie diese Datei auf Ihrem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="99d82-135">Save this file to your local computer.</span></span>

2. <span data-ttu-id="99d82-136">Wählen Sie auf der Website für die **Erweiterte eDiscovery** -Startseite in der Kachel **Einstellungen** die Option **experimentelle Features konfigurieren**aus, und wählen Sie dann **Attorney-Client-Berechtigungseinstellung verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="99d82-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="99d82-137">Die Seite " **Attorney-Client-Privilege** " wird angezeigt, und die Option " **Anwalt-Client-Berechtigung erkennen** " ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="99d82-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Flyout-Seite "Attorney-Client-Privilegien"](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="99d82-139">Wählen Sie **Durchsuchen** aus, und suchen Sie die CSV-Datei, die Sie in Schritt 1 erstellt haben, und wählen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="99d82-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="99d82-140">Wählen Sie **Speichern** aus, um die anwaltsliste hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="99d82-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="99d82-141">Verwenden des Erkennungs Modells für Anwalts Client-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="99d82-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="99d82-142">Führen Sie die Schritte in diesem Abschnitt aus, um die Erkennung von Anwalts Mandanten-Berechtigungen für Dokumente in einem Überprüfungs Sätze zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="99d82-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="99d82-143">Schritt 1: Erstellen einer smarttaggruppe mit dem Anwalt-Client-Berechtigungs Erkennungs Modell</span><span class="sxs-lookup"><span data-stu-id="99d82-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="99d82-144">Eine der wichtigsten Methoden zum Anzeigen der Ergebnisse der Erkennung von Anwalts Client-Berechtigungen in Ihrem Überprüfungsprozess ist die Verwendung einer smarttaggruppe.</span><span class="sxs-lookup"><span data-stu-id="99d82-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="99d82-145">Eine smarttaggruppe gibt die Ergebnisse der Anwalts-Client-Berechtigungs Erkennung an und zeigt die Ergebnisse Inline neben den Tags in einer smarttaggruppe an.</span><span class="sxs-lookup"><span data-stu-id="99d82-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="99d82-146">Auf diese Weise können Sie während der Dokumentüberprüfung schnell potenziell privilegierte Dokumente identifizieren.</span><span class="sxs-lookup"><span data-stu-id="99d82-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="99d82-147">Darüber hinaus können Sie die Tags in der smarttaggruppe auch verwenden, um Dokumente als privilegiertes oder als nicht privilegiertes Tag zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="99d82-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="99d82-148">Weitere Informationen zu Smarttags finden Sie unter [Einrichten von Smart Tags in Advanced eDiscovery](smart-tags.md).</span><span class="sxs-lookup"><span data-stu-id="99d82-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="99d82-149">Wählen Sie in der Überprüfungsgruppe, die die Dokumente enthält, die Sie in Schritt 1 analysiert haben, die Option **Review-Gruppe verwalten** aus, und wählen Sie dann **Tags verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="99d82-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="99d82-150">Wählen Sie unter **Tags**die Dropdown Seite neben **Gruppe hinzufügen** aus, und wählen Sie dann **smarttaggruppe hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="99d82-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![Wählen Sie "smarttaggruppe hinzufügen" aus.](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="99d82-152">Wählen Sie auf der Seite **Modell für Smarttag auswählen** die Option neben **Anwalt-Client-Privileg** **auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="99d82-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="99d82-153">Es wird eine Transpondergruppe namens " **Attorney-Client Privilege** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="99d82-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="99d82-154">Sie enthält zwei untergeordnete Tags mit dem Namen " **positiv** " und " **negativ**", die den möglichen Ergebnissen entsprechen, die das Modell erzeugt.</span><span class="sxs-lookup"><span data-stu-id="99d82-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Smarttaggruppe "Attorney-Client Privilege"](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="99d82-156">Benennen Sie die Tag-Gruppe und die Tags entsprechend ihrer Überprüfung um.</span><span class="sxs-lookup"><span data-stu-id="99d82-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="99d82-157">Sie können beispielsweise " **positiv** " in " **privilegierte** " und " **negativ** " in " **nicht privilegierte**" umbenennen.</span><span class="sxs-lookup"><span data-stu-id="99d82-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="99d82-158">Schritt 2: Analysieren eines Überprüfungs Satzes</span><span class="sxs-lookup"><span data-stu-id="99d82-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="99d82-159">Wenn Sie die Dokumente in einem Überprüfungs Satzes analysieren, wird auch das Clientzugriffs Berechtigungs-Erkennungs Modell ausgeführt und die entsprechenden Eigenschaften (beschrieben in [How is it work?](#how-does-it-work) wird jedem Dokument in der Überprüfungsgruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="99d82-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="99d82-160">Weitere Informationen zum Analysieren von Daten in Überprüfungs Sätzen finden Sie unter [Analysieren von Daten in einer Überprüfungsgruppe in Advanced eDiscovery](analyzing-data-in-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="99d82-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="99d82-161">Schritt 3: Verwenden der smarttaggruppe zur Überprüfung von privilegierten Inhalten</span><span class="sxs-lookup"><span data-stu-id="99d82-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="99d82-162">Nach der Analyse des Überprüfungs Satzes und der Einrichtung von Smarttags besteht der nächste Schritt darin, die Dokumente zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="99d82-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="99d82-163">Wenn das Modell festgestellt hat, dass das Dokument möglicherweise privilegiert ist, zeigt das entsprechende Smarttag im **taggingbereich** die folgenden Ergebnisse an, die von der Berechtigung "Anwalt-Client-Erkennung" erzeugt werden:</span><span class="sxs-lookup"><span data-stu-id="99d82-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="99d82-164">Wenn das Dokumentinhalt enthält, der möglicherweise zulässig ist, wird der **rechtliche Inhalt** der Bezeichnung neben dem entsprechenden Smarttag angezeigt (in diesem Fall das standardmäßige **positive** Tag).</span><span class="sxs-lookup"><span data-stu-id="99d82-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="99d82-165">Wenn das Dokument über einen Teilnehmer verfügt, der in der anwaltsliste Ihrer Organisation gefunden wird, wird der Bezeichnungs **Anwalt** neben dem entsprechenden Smarttag angezeigt (in diesem Fall ist dies auch das standardmäßige **positive** Tag).</span><span class="sxs-lookup"><span data-stu-id="99d82-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="99d82-166">Wenn das Dokumentinhalte enthält, die möglicherweise legal sind *und* ein Teilnehmer in der anwaltsliste gefunden wird, werden sowohl die **rechtlichen Inhalte** als auch rechts **Anwalts** Bezeichnungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="99d82-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="99d82-167">Wenn das Modell feststellt, dass ein Dokument keine Inhalte enthält, die in der Natur legal sind oder keinen Teilnehmer aus der anwaltsliste enthalten, wird im taggingbereich keine Bezeichnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="99d82-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="99d82-168">Die folgenden Screenshots zeigen beispielsweise zwei Dokumente.</span><span class="sxs-lookup"><span data-stu-id="99d82-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="99d82-169">Der erste enthält Inhalte, die in der Natur legal sind und einen Teilnehmer in der Liste der Rechtsanwälte gefunden haben.</span><span class="sxs-lookup"><span data-stu-id="99d82-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="99d82-170">Der zweite enthält weder und daher keine Beschriftungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="99d82-170">The second contains neither and therefore doesn't display any labels.</span></span>

![Dokument mit Rechtsanwalt und rechtlichen Inhalts Bezeichnungen](../media/AeDTaggingPanelLegalContentAttorney.png)

![Dokument ohne Beschriftungen](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="99d82-173">Nachdem Sie ein Dokument überprüft haben, um festzustellen, ob es privilegierte Inhalte enthält, können Sie das Dokument mit dem entsprechenden Tag versehen.</span><span class="sxs-lookup"><span data-stu-id="99d82-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
