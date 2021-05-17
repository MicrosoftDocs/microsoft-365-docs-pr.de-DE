---
title: Einrichten der Erkennung von Anwalts-Client-Rechten in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Verwenden Sie das Erkennungsmodell für Anwalts-Client-Rechte, um die computergestützte Erkennung privilegierter Inhalte bei der Überprüfung von Inhalten in einem Advanced eDiscovery verwenden.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358041"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="bb9a2-103">Einrichten der Erkennung von Anwalts-Client-Rechten in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bb9a2-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="bb9a2-104">Ein wichtiger und kostspieliger Aspekt der Überprüfungsphase eines eDiscovery-Prozesses ist die Überprüfung von Dokumenten auf privilegierte Inhalte.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="bb9a2-105">Advanced eDiscovery ermöglicht die maschinelle Lernerkennung privilegierter Inhalte, um diesen Prozess effizienter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="bb9a2-106">Dieses Feature wird als *Erkennung von Anwalts-Client-Rechten bezeichnet.*</span><span class="sxs-lookup"><span data-stu-id="bb9a2-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="bb9a2-107">Wie funktioniert das?</span><span class="sxs-lookup"><span data-stu-id="bb9a2-107">How does it work?</span></span>

<span data-ttu-id="bb9a2-108">Wenn die Erkennung von Anwalts-Client-Berechtigungen aktiviert ist, werden alle Dokumente in einem Überprüfungssatz vom Erkennungsmodell der Anwalts-Client-Rechte verarbeitet, wenn Sie die Daten [im](analyzing-data-in-review-set.md) Überprüfungssatz analysieren.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="bb9a2-109">Das Modell sucht nach zwei Dingen:</span><span class="sxs-lookup"><span data-stu-id="bb9a2-109">The model looks for two things:</span></span>

- <span data-ttu-id="bb9a2-110">Privilegierter Inhalt – Das Modell verwendet maschinelles Lernen, um die Wahrscheinlichkeit zu bestimmen, dass das Dokument Inhalte enthält, die legaler Natur sind.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="bb9a2-111">Teilnehmer – Im Rahmen der Einrichtung der Anwalts-Client-Berechtigungserkennung müssen Sie eine Liste der Anwälte für Ihre Organisation einreichen.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="bb9a2-112">Das Modell vergleicht dann die Teilnehmer des Dokuments mit der Liste der Rechtsanwälte, um festzustellen, ob mindestens ein Teilnehmer des Dokuments ein Rechtsanwalt ist.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="bb9a2-113">Das Modell erzeugt die folgenden drei Eigenschaften für jedes Dokument:</span><span class="sxs-lookup"><span data-stu-id="bb9a2-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="bb9a2-114">**AttorneyClientPrivilegeScore:** Die Wahrscheinlichkeit, dass das Dokument rechtlicher Natur ist; Die Werte für die Bewertung liegen zwischen **0** und **1**.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="bb9a2-115">**HasAttorney:** Diese Eigenschaft ist auf **true festgelegt,** wenn einer der Dokumentteilnehmer in der Anwaltsliste aufgeführt ist. Andernfalls ist der Wert **false**.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="bb9a2-116">Der Wert wird auch auf **false** festgelegt, wenn Ihre Organisation keine Anwaltsliste hochgeladen hat.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="bb9a2-117">**IsPrivilege:** Diese Eigenschaft wird auf **true** festgelegt, wenn der Wert für  **AttorneyClientPrivilegeScore** über dem Schwellenwert liegt oder wenn das Dokument über einen Anwaltsteilnehmer verfügt. andernfalls wird der Wert auf **false festgelegt.**</span><span class="sxs-lookup"><span data-stu-id="bb9a2-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="bb9a2-118">Diese Eigenschaften (und ihre entsprechenden Werte) werden den Dateimetadaten der Dokumente in einem Überprüfungssatz hinzugefügt, wie im folgenden Screenshot gezeigt:</span><span class="sxs-lookup"><span data-stu-id="bb9a2-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![Eigenschaften von Anwalts-Client-Berechtigungen, die in Dateimetadaten angezeigt werden](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="bb9a2-120">Diese drei Eigenschaften können auch in einem Überprüfungssatz durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="bb9a2-121">Weitere Informationen finden Sie unter [Query the data in a review set](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="bb9a2-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="bb9a2-122">Einrichten des Erkennungsmodells für Anwalts-Client-Rechte</span><span class="sxs-lookup"><span data-stu-id="bb9a2-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="bb9a2-123">Um das Erkennungsmodell für Anwalts-Client-Rechte zu aktivieren, muss Ihre Organisation es aktivieren und dann eine Anwaltsliste hochladen.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="bb9a2-124">Schritt 1: Aktivieren der Erkennung von Anwalts-Client-Rechten</span><span class="sxs-lookup"><span data-stu-id="bb9a2-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="bb9a2-125">Eine Person, die ein eDiscovery-Administrator in Ihrer Organisation ist (Mitglied der eDiscovery-Administrator-Untergruppe in der Rollengruppe eDiscovery-Manager), muss das Modell in Ihren Advanced eDiscovery verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="bb9a2-126">Wechseln Sie im Security & Compliance Center zu **eDiscovery > Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="bb9a2-127">Klicken Sie **Advanced eDiscovery** Startseite in der Kachel **Einstellungen** auf **Globale Analyseeinstellungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   ![Wählen Sie "Experimentelle Features konfigurieren" aus.](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="bb9a2-129">Wählen Sie **auf der Registerkarte** Analyseeinstellungen die Option **Anwalts-Client-Rechte verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="bb9a2-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="bb9a2-130">Klicken Sie auf der Flyoutseite **Anwaltsgeheimnisse** auf die Umschaltfläche, um das Feature zu aktivieren, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="bb9a2-131">Schritt 2: Hochladen einer Liste von Anwälten (optional)</span><span class="sxs-lookup"><span data-stu-id="bb9a2-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="bb9a2-132">Um das Erkennungsmodell der Anwalts-Client-Rechte voll  zu nutzen  und die Ergebnisse der zuvor beschriebenen Erkennung von Anwalts- oder Potenziell privilegierten Rechten zu nutzen, empfehlen wir, eine Liste der E-Mail-Adressen für die Anwälte und Rechtsmitarbeiter hochzuladen, die für Ihre Organisation arbeiten.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="bb9a2-133">So laden Sie eine Anwaltsliste hoch, die vom Erkennungsmodell für Anwalts-Client-Rechte verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="bb9a2-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="bb9a2-134">Erstellen Sie eine CSV-Datei (ohne Kopfzeile), und fügen Sie die E-Mail-Adresse jeder relevanten Person in einer separaten Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-134">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="bb9a2-135">Speichern Sie die Datei auf Ihrem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-135">Save this file to your local computer.</span></span>

2. <span data-ttu-id="bb9a2-136">Wählen Sie **Advanced eDiscovery** Startseite auf der Kachel **Einstellungen** Konfigurieren experimenteller Features **aus,** und wählen Sie dann Die Einstellung **Anwalts-Client-Rechte verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="bb9a2-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="bb9a2-137">Die **Seite Anwalt-Client-Rechte** wird angezeigt, und die **Option Anwalt-Client-Berechtigungserkennung** ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Flyoutseite für Anwalts-Clientrechte](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="bb9a2-139">Wählen **Sie Durchsuchen** aus, und suchen Sie dann die .csv, die Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="bb9a2-140">Wählen **Sie Speichern** aus, um die Anwaltsliste hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="bb9a2-141">Verwenden des Anwalts-Client-Berechtigungserkennungsmodells</span><span class="sxs-lookup"><span data-stu-id="bb9a2-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="bb9a2-142">Führen Sie die Schritte in diesem Abschnitt aus, um die Erkennung von Anwalts-Client-Rechten für Dokumente in einem Überprüfungssatz zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="bb9a2-143">Schritt 1: Erstellen einer Smarttaggruppe mit Einem Anwalt-Client-Berechtigungserkennungsmodell</span><span class="sxs-lookup"><span data-stu-id="bb9a2-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="bb9a2-144">Eine der wichtigsten Methoden zum Anzeigen der Ergebnisse der Erkennung von Anwaltsgeheimnissen in Ihrem Überprüfungsprozess ist die Verwendung einer Smarttaggruppe.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="bb9a2-145">Eine Smarttaggruppe zeigt die Ergebnisse der Erkennung von Anwaltsgeheimnissen an und listet die Ergebnisse in der Zeile neben den Kategorien in einer Smarttaggruppe auf.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="bb9a2-146">Auf diese Weise können Sie potenziell privilegierte Dokumente während der Dokumentüberprüfung schnell identifizieren.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="bb9a2-147">Darüber hinaus können Sie auch die Tags der Smarttaggruppe verwenden, um Dokumente als privilegiert oder nicht privilegiert zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="bb9a2-148">Weitere Informationen zu Smarttags finden Sie unter [Einrichten von Smarttags in Advanced eDiscovery](smart-tags.md).</span><span class="sxs-lookup"><span data-stu-id="bb9a2-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="bb9a2-149">Wählen Sie im Überprüfungssatz, der die dokumente enthält, die Sie in Schritt 1 analysiert haben, **Die** Option Überprüfungssatz verwalten aus, und wählen Sie **dann Tags verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="bb9a2-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="bb9a2-150">Wählen **Sie unter Tags** den Pull-Down neben Gruppe **hinzufügen** aus, und wählen Sie **dann Smarttaggruppe hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="bb9a2-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![Wählen Sie "Smarttaggruppe hinzufügen" aus.](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="bb9a2-152">Wählen Sie **auf der Seite Modell für Ihr Smarttag** auswählen **neben** **Anwalts-Client-Berechtigung auswählen aus.**</span><span class="sxs-lookup"><span data-stu-id="bb9a2-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="bb9a2-153">Eine Taggruppe mit dem **Namen Anwalt-Client-Berechtigung** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="bb9a2-154">Sie enthält zwei untergeordnete Tags mit dem Namen **Positive** und **Negative,** die den möglichen Ergebnissen des Modells entsprechen.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Smarttaggruppe "Anwalts-Client-Rechte"](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="bb9a2-156">Benennen Sie die Taggruppe und die Tags entsprechend Ihrer Überprüfung um.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="bb9a2-157">Sie können z. B. **Positive** in **Privileged und** **Negative in** Not **privileged umbenennen.**</span><span class="sxs-lookup"><span data-stu-id="bb9a2-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="bb9a2-158">Schritt 2: Analysieren eines Überprüfungssatz</span><span class="sxs-lookup"><span data-stu-id="bb9a2-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="bb9a2-159">Wenn Sie die Dokumente in einem Überprüfungssatz analysieren, wird auch das Erkennungsmodell für Anwalts-Client-Berechtigungen ausgeführt, und die entsprechenden Eigenschaften (siehe Wie funktioniert [das?](#how-does-it-work) wird jedem Dokument im Überprüfungssatz hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="bb9a2-160">Weitere Informationen zum Analysieren von Daten im Überprüfungssatz finden Sie unter Analysieren von Daten [in einem Überprüfungssatz in Advanced eDiscovery](analyzing-data-in-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="bb9a2-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="bb9a2-161">Schritt 3: Verwenden der Smarttaggruppe zur Überprüfung privilegierter Inhalte</span><span class="sxs-lookup"><span data-stu-id="bb9a2-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="bb9a2-162">Nach der Analyse des Überprüfungssets und dem Einrichten von Smarttags besteht der nächste Schritt in der Überprüfung der Dokumente.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="bb9a2-163">Wenn das Modell festgestellt hat, dass das Dokument potenziell privilegiert ist, zeigt das entsprechende Smarttag im **Tagging-Panel** die folgenden Ergebnisse an, die durch die Erkennung von Anwalts-Client-Berechtigungen erzeugt werden:</span><span class="sxs-lookup"><span data-stu-id="bb9a2-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="bb9a2-164">Wenn das Dokument Inhalte enthält, die möglicherweise rechtlicher Natur sind, wird die Bezeichnung **Rechtlicher** Inhalt neben dem entsprechenden Smarttag angezeigt (in diesem Fall das standardmäßige **Positive** Tag).</span><span class="sxs-lookup"><span data-stu-id="bb9a2-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="bb9a2-165">Wenn das Dokument über einen Teilnehmer verfügt, der in der Anwaltsliste Ihrer Organisation gefunden wird, wird die Bezeichnung **Anwalt** neben dem entsprechenden Smarttag angezeigt (das in diesem Fall auch das standardmäßige **Positive** Tag ist).</span><span class="sxs-lookup"><span data-stu-id="bb9a2-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="bb9a2-166">Wenn das Dokument Inhalte enthält,  die möglicherweise rechtlicher Natur sind und ein Teilnehmer in der Anwaltsliste gefunden wurde, werden sowohl die Bezeichnungen **"Rechtlicher Inhalt"** als auch **"Anwalt"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="bb9a2-167">Wenn das Modell feststellt, dass ein Dokument keine Inhalte enthält, die rechtlicher Natur sind oder keinen Teilnehmer aus der Anwaltsliste enthalten, wird keine Bezeichnung im Markierungspanel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="bb9a2-168">Die folgenden Screenshots zeigen beispielsweise zwei Dokumente.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="bb9a2-169">Der erste enthält Inhalte, die rechtlicher Natur sind und einen Teilnehmer in der Liste der Anwälte finden.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="bb9a2-170">Die zweite enthält keine bezeichnungen und zeigt daher keine Bezeichnungen an.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-170">The second contains neither and therefore doesn't display any labels.</span></span>

![Dokument mit Anwalts- und Rechtsinhaltsbezeichnungen](../media/AeDTaggingPanelLegalContentAttorney.png)

![Dokument ohne Bezeichnungen](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="bb9a2-173">Nachdem Sie ein Dokument überprüft haben, um zu sehen, ob es privilegierten Inhalt enthält, können Sie das Dokument mit dem entsprechenden Tag kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="bb9a2-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
