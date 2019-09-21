---
title: Einrichten der Erkennung von Anwalts Mandanten-Berechtigungen in Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: Verwenden Sie das Erkennungs Modell "Attorney-Client-Berechtigung", um die Lern basierte Erkennung privilegierter Inhalte zu verwenden, wenn Sie Inhalte in einem erweiterten eDiscovery-Fall überprüfen.
ms.openlocfilehash: 943b788dfea62433f0f6c1dca3b6b105cf92bae8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081081"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="7ef59-103">Einrichten der Erkennung von Anwalts Mandanten-Berechtigungen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7ef59-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="7ef59-104">Ein wichtiger und kostspieliger Aspekt der Überprüfungsphase eines eDiscovery-Prozesses besteht darin, Dokumente für privilegierte Inhalte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7ef59-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="7ef59-105">Advanced eDiscovery bietet eine maschinelle Lern basierte Erkennung von privilegierten Inhalten, um diesen Prozess effizienter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="7ef59-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="7ef59-106">Dieses Feature wird als *Anwalts Client-Berechtigungs Erkennung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7ef59-106">This feature is called *attorney-client privilege detection*.</span></span>

> [!NOTE]
> <span data-ttu-id="7ef59-107">Sie müssen sich für das Erkennungs Modell für Anwalts-und Client Rechte entscheiden, bevor Sie es verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7ef59-107">You must opt in to the attorney-client privilege detection model before you can use it.</span></span> <span data-ttu-id="7ef59-108">Anweisungen finden Sie in [Schritt 1](#step-1-opt-in-to-attorney-client-privilege-detection) .</span><span class="sxs-lookup"><span data-stu-id="7ef59-108">See [Step 1](#step-1-opt-in-to-attorney-client-privilege-detection) for instructions.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="7ef59-109">Wie funktioniert dies?</span><span class="sxs-lookup"><span data-stu-id="7ef59-109">How does it work?</span></span>

<span data-ttu-id="7ef59-110">Wenn die Erkennung der Anwalts-Client-Rechte aktiviert ist, werden alle Dokumente in einem Überprüfungs Satzes vom Anwalt-Client-Berechtigungs Erkennungs Modell verarbeitet, wenn Sie [die Daten](analyzing-data-in-review-set.md) im Überprüfungspaket analysieren.</span><span class="sxs-lookup"><span data-stu-id="7ef59-110">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="7ef59-111">Das Modell sucht zwei Dinge:</span><span class="sxs-lookup"><span data-stu-id="7ef59-111">The model looks for two things:</span></span>

- <span data-ttu-id="7ef59-112">Privilegierte Inhalte – das Modell verwendet Maschinelles Lernen, um die Wahrscheinlichkeit zu ermitteln, dass das Dokumentinhalte enthält, die in der Natur legal sind.</span><span class="sxs-lookup"><span data-stu-id="7ef59-112">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="7ef59-113">Teilnehmer – im Rahmen der Einrichtung der Anwalts-Client-Berechtigungs Erkennung müssen Sie eine Liste der Anwälte für Ihre Organisation übermitteln.</span><span class="sxs-lookup"><span data-stu-id="7ef59-113">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="7ef59-114">Das Modell vergleicht dann die Teilnehmer des Dokuments mit der anwaltsliste, um festzustellen, ob ein Dokument mindestens einen Anwalts Teilnehmer hat.</span><span class="sxs-lookup"><span data-stu-id="7ef59-114">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="7ef59-115">Das Modell erzeugt für jedes Dokument die folgenden drei Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="7ef59-115">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="7ef59-116">**AttorneyClientPrivilegeScore** – die Wahrscheinlichkeit, dass das Dokument in der Natur legal ist; die Werte für die Partitur liegen zwischen **0** und **1**.</span><span class="sxs-lookup"><span data-stu-id="7ef59-116">**AttorneyClientPrivilegeScore** – The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="7ef59-117">**HasAttorney** – diese Eigenschaft wird auf **true** festgelegt, wenn einer der Dokument Teilnehmer in der anwaltsliste aufgeführt ist; Andernfalls ist der Wert **false**.</span><span class="sxs-lookup"><span data-stu-id="7ef59-117">**HasAttorney** – This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="7ef59-118">Der Wert ist auch auf " **false** " festgelegt, wenn Ihre Organisation keine anwaltsliste hochgeladen hat.</span><span class="sxs-lookup"><span data-stu-id="7ef59-118">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="7ef59-119">**Isprivilege** – diese Eigenschaft wird auf **true** festgelegt, wenn der Wert für **AttorneyClientPrivilegeScore** oberhalb des Schwellenwerts liegt *oder* wenn das Dokument über einen Anwalts Teilnehmer verfügt; Andernfalls wird der Wert auf **false**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7ef59-119">**IsPrivilege** – This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="7ef59-120">Diese Eigenschaften (und die entsprechenden Werte) werden den Datei Metadaten der Dokumente in einem Überprüfungs Satzes hinzugefügt, wie im folgenden Screenshot dargestellt:</span><span class="sxs-lookup"><span data-stu-id="7ef59-120">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![In Datei Metadaten angezeigte Anwalts-Client-Berechtigungs Eigenschaften](media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="7ef59-122">Diese drei Eigenschaften können auch innerhalb eines Überprüfungs Satzes durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="7ef59-122">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="7ef59-123">Weitere Informationen finden Sie unter [Abfragen der Daten in einem Überprüfungs Satzes](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="7ef59-123">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="7ef59-124">Einrichten des Erkennungs Modells für Anwalts Client-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7ef59-124">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="7ef59-125">Um das Erkennungs Modell für das Attorney-Client-Privileg zu aktivieren, muss Ihre Organisation sich anmelden und dann eine anwaltsliste hochladen.</span><span class="sxs-lookup"><span data-stu-id="7ef59-125">To enable the attorney-client privilege detection model, your organization has to opt-in and then upload an attorney list.</span></span>

### <a name="step-1-opt-in-to-attorney-client-privilege-detection"></a><span data-ttu-id="7ef59-126">Schritt 1: Anmelden bei der Erkennung von Anwalts-und Client rechten</span><span class="sxs-lookup"><span data-stu-id="7ef59-126">Step 1: Opt-in to attorney-client privilege detection</span></span>

<span data-ttu-id="7ef59-127">Wie bereits erwähnt, befindet sich das Erkennungs Modell für das Anwalts Client-Recht in der Vorschau.</span><span class="sxs-lookup"><span data-stu-id="7ef59-127">As previously stated, the attorney-client privilege detection model is in Preview.</span></span> <span data-ttu-id="7ef59-128">Daher muss sich eine Person in Ihrem Unternehmen eDiscovery Administrator (ein Mitglied der Untergruppe eDiscovery Administrator in der Rollengruppe eDiscovery-Manager) anmelden, um das Modell in ihren erweiterten eDiscovery-Fällen zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="7ef59-128">Therefore a person in your organization eDiscovery Administrator (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must opt in to make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="7ef59-129">Wechseln Sie im Security #a0 Compliance Center zu **eDiscovery #a1 Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="7ef59-129">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="7ef59-130">Klicken Sie auf der Seite für die **Erweiterte eDiscovery** -Homepage auf der Kachel **Einstellungen** auf **experimentelle Features konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="7ef59-130">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure experimental features**.</span></span>

   ![Klicken Sie auf "experimentelle Features konfigurieren".](media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="7ef59-132">Klicken Sie auf der Registerkarte **experimentelle Features** auf **Attorney-Client-Berechtigungseinstellung verwalten**.</span><span class="sxs-lookup"><span data-stu-id="7ef59-132">On the **Experimental features** tab, click **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="7ef59-133">Klicken Sie auf der Seite " **Attorney-Client-Privilege-** Flyout" auf die Umschaltfläche, um das Feature zu aktivieren, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7ef59-133">On the **Attorney-client privilege** flyout page, click the toggle to turn on the feature and then click **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="7ef59-134">Schritt 2: Hochladen einer Liste von Anwälten (optional)</span><span class="sxs-lookup"><span data-stu-id="7ef59-134">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="7ef59-135">Um das Erkennungs Modell "Attorney-Client-Berechtigung" vollständig zu nutzen und die Ergebnisse des " **hat Attorney** " oder der **potenziell privilegierten** Erkennung zu verwenden, die zuvor beschrieben wurde, empfehlen wir Ihnen, eine Liste mit e-Mail-Adressen für folgendes hochzuladen: Juristen und juristische Personen, die für Ihre Organisation arbeiten.</span><span class="sxs-lookup"><span data-stu-id="7ef59-135">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="7ef59-136">So laden Sie eine anwaltsliste für das Erkennungs Modell "Attorney-Client-Berechtigung" hoch:</span><span class="sxs-lookup"><span data-stu-id="7ef59-136">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="7ef59-137">Erstellen Sie eine CSV-Datei (ohne Kopfzeile), und fügen Sie die e-Mail-Adresse für jede entsprechende Person in einer separaten Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="7ef59-137">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="7ef59-138">Speichern Sie diese Datei auf Ihrem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="7ef59-138">Save this file to your local computer.</span></span>

2. <span data-ttu-id="7ef59-139">Klicken Sie auf der Seite für die **Erweiterte eDiscovery** -Homepage auf der Kachel **Einstellungen** auf **experimentelle Features konfigurieren**, und klicken Sie dann auf **Anwalts-Client-Berechtigungseinstellung verwalten**.</span><span class="sxs-lookup"><span data-stu-id="7ef59-139">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure experimental features**, and then click **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="7ef59-140">Die Seite " **Attorney-Client-Privilege** " wird angezeigt, und die Option " **Anwalt-Client-Berechtigung erkennen** " ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7ef59-140">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Flyout-Seite "Attorney-Client-Privilegien"](media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="7ef59-142">Klicken Sie auf **Durchsuchen** , und suchen Sie dann nach der CSV-Datei, die Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7ef59-142">Click **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="7ef59-143">Klicken Sie auf **Speichern** , um die anwaltsliste hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="7ef59-143">Click **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="7ef59-144">Verwenden des Erkennungs Modells für Anwalts Client-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7ef59-144">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="7ef59-145">Führen Sie die Schritte in diesem Abschnitt aus, um die Erkennung von Anwalts Mandanten-Berechtigungen für Dokumente in einem Überprüfungs Sätze zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ef59-145">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="7ef59-146">Schritt 1: Erstellen einer smarttaggruppe mit dem Anwalt-Client-Berechtigungs Erkennungs Modell</span><span class="sxs-lookup"><span data-stu-id="7ef59-146">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="7ef59-147">Eine der wichtigsten Methoden zum Anzeigen der Ergebnisse der Erkennung von Anwalts Client-Berechtigungen in Ihrem Überprüfungsprozess ist die Verwendung einer smarttaggruppe.</span><span class="sxs-lookup"><span data-stu-id="7ef59-147">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="7ef59-148">Eine smarttaggruppe gibt die Ergebnisse der Anwalts-Client-Berechtigungs Erkennung an und zeigt die Ergebnisse Inline neben den Tags in einer smarttaggruppe an.</span><span class="sxs-lookup"><span data-stu-id="7ef59-148">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="7ef59-149">Auf diese Weise können Sie während der Dokumentüberprüfung schnell potenziell privilegierte Dokumente identifizieren.</span><span class="sxs-lookup"><span data-stu-id="7ef59-149">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="7ef59-150">Darüber hinaus können Sie die Tags in der smarttaggruppe auch verwenden, um Dokumente als privilegiertes oder als nicht privilegiertes Tag zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="7ef59-150">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="7ef59-151">Weitere Informationen zu Smarttags finden Sie unter [Einrichten von Smart Tags in Advanced eDiscovery](smart-tags.md).</span><span class="sxs-lookup"><span data-stu-id="7ef59-151">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="7ef59-152">Klicken Sie in der Überprüfungsgruppe mit den Dokumenten, die Sie in Schritt 1 analysiert haben, auf **Überarbeitungs Gruppe verwalten** , und klicken Sie dann auf **Tags verwalten**.</span><span class="sxs-lookup"><span data-stu-id="7ef59-152">In the review set that contains the documents that you analyzed in Step 1, click **Manage review set** and then click **Manage tags**.</span></span>
 
2. <span data-ttu-id="7ef59-153">Klicken Sie unter **Tags**auf die Dropdown Seite neben **Gruppe hinzufügen** , und klicken Sie dann auf **smarttaggruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7ef59-153">Under **Tags**, click the pull-down next to **Add group** and then click **Add smart tag group**.</span></span>

   ![Klicken Sie auf Smart Tag-Gruppe hinzufügen.](media/AeDCreateSmartTag.png)

3. <span data-ttu-id="7ef59-155">Klicken Sie auf der Seite **Modell für Smarttag auswählen** auf neben **Anwalts Mandanten-Privileg** **auswählen** .</span><span class="sxs-lookup"><span data-stu-id="7ef59-155">On the **Choose a model for your smart tag** page, click **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="7ef59-156">Es wird eine Transpondergruppe namens " **Attorney-Client Privilege** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ef59-156">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="7ef59-157">Sie enthält zwei untergeordnete Tags mit dem Namen " **positiv** " und " **negativ**", die den möglichen Ergebnissen entsprechen, die das Modell erzeugt.</span><span class="sxs-lookup"><span data-stu-id="7ef59-157">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Smarttaggruppe "Attorney-Client Privilege"](media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="7ef59-159">Benennen Sie die Tag-Gruppe und die Tags entsprechend ihrer Überprüfung um.</span><span class="sxs-lookup"><span data-stu-id="7ef59-159">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="7ef59-160">Sie können beispielsweise " **positiv** " in " **privilegierte** " und " **negativ** " in " **nicht privilegierte**" umbenennen.</span><span class="sxs-lookup"><span data-stu-id="7ef59-160">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="7ef59-161">Schritt 2: Analysieren eines Überprüfungs Satzes</span><span class="sxs-lookup"><span data-stu-id="7ef59-161">Step 2: Analyze a review set</span></span>

<span data-ttu-id="7ef59-162">Wenn Sie die Dokumente in einem Überprüfungs Satzes analysieren, wird auch das Clientzugriffs Berechtigungs-Erkennungs Modell ausgeführt und die entsprechenden Eigenschaften (beschrieben in[How is it work?](#how-does-it-work) wird jedem Dokument in der Überprüfungsgruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7ef59-162">When you analyze the documents in a review set, the attorney-client privilege detection model will also be run and the corresponding properties (described in[How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="7ef59-163">Weitere Informationen zum Analysieren von Daten in Überprüfungs Sätzen finden Sie unter [Analysieren von Daten in einer Überprüfungsgruppe in Advanced eDiscovery](analyzing-data-in-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="7ef59-163">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="7ef59-164">Schritt 3: Verwenden der smarttaggruppe zur Überprüfung von privilegierten Inhalten</span><span class="sxs-lookup"><span data-stu-id="7ef59-164">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="7ef59-165">Nach der Analyse des Überprüfungs Satzes und der Einrichtung von Smarttags besteht der nächste Schritt darin, die Dokumente zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7ef59-165">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="7ef59-166">Wenn das Modell festgestellt hat, dass das Dokument möglicherweise privilegiert ist, zeigt das entsprechende Smarttag im **taggingbereich** die folgenden Ergebnisse an, die von der Berechtigung "Anwalt-Client-Erkennung" erzeugt werden:</span><span class="sxs-lookup"><span data-stu-id="7ef59-166">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="7ef59-167">Wenn das Dokumentinhalt enthält, der möglicherweise zulässig ist, wird der **rechtliche Inhalt** der Bezeichnung neben dem entsprechenden Smarttag angezeigt (in diesem Fall das standardmäßige **positive** Tag).</span><span class="sxs-lookup"><span data-stu-id="7ef59-167">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="7ef59-168">Wenn das Dokument über einen Teilnehmer verfügt, der in der anwaltsliste Ihrer Organisation gefunden wird, wird der Bezeichnungs **Anwalt** neben dem entsprechenden Smarttag angezeigt (in diesem Fall ist dies auch das standardmäßige **positive** Tag).</span><span class="sxs-lookup"><span data-stu-id="7ef59-168">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="7ef59-169">Wenn das Dokumentinhalte enthält, die möglicherweise legal sind *und* ein Teilnehmer in der anwaltsliste gefunden wird, werden sowohl die **rechtlichen Inhalte** als auch rechts **Anwalts** Bezeichnungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ef59-169">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="7ef59-170">Wenn das Modell feststellt, dass ein Dokument keine Inhalte enthält, die in der Natur legal sind oder keinen Teilnehmer aus der anwaltsliste enthalten, wird im taggingbereich keine Bezeichnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ef59-170">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="7ef59-171">Die folgenden Screenshots zeigen beispielsweise zwei Dokumente; der erste enthält Inhalte, die in der Natur legal sind und einen Teilnehmer in der Liste der Rechtsanwälte gefunden haben. der zweite enthält weder und daher keine Beschriftungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ef59-171">For example, the following screenshots show two documents; the first one contains content that is legal in nature and has a participant found in the list of attorneys; the second contains neither and therefore doesn't display any labels.</span></span>

![Dokument mit Rechtsanwalt und rechtlichen Inhalts Bezeichnungen](media/AeDTaggingPanelLegalContentAttorney.png)

![Dokument ohne Beschriftungen](media/AeDTaggingPanelNegative.png)

<span data-ttu-id="7ef59-174">Nachdem Sie ein Dokument überprüft haben, um festzustellen, ob es privilegierte Inhalte enthält, können Sie das Dokument mit dem entsprechenden Tag versehen.</span><span class="sxs-lookup"><span data-stu-id="7ef59-174">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>