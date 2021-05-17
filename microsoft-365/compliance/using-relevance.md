---
title: Verwenden Des Relevanzmoduls zum Analysieren von Daten in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Erfahren Sie, wie das Relevanzmodul Daten in Nachweisen mit einer Beschreibung des Relevanzworkflows und der Schulungsschritte in Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286061"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a><span data-ttu-id="85325-103">Verwenden Des Relevanzmoduls zum Analysieren von Daten in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="85325-103">Use the Relevance module to analyze data in Advanced eDiscovery</span></span>

<span data-ttu-id="85325-104">In Advanced eDiscovery umfasst das Relevanzmodul die Relevanzschulung und die Überprüfung von Dateien im Zusammenhang mit einem Fall.</span><span class="sxs-lookup"><span data-stu-id="85325-104">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="85325-105">Um den Relevanzworkflow zu verwenden, wechseln Sie zu Überprüfungssatz in einem Überprüfungssatz verwalten, und klicken Sie auf Relevanz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="85325-105">In order to use the Relevance workflow, go to Manage review set within a review set and click on Show Relevance.</span></span> <span data-ttu-id="85325-106">Es gibt einige Schritte, die Sie ausführen müssen, bevor Sie den Workflow starten können:</span><span class="sxs-lookup"><span data-stu-id="85325-106">There are a couple of steps you need to complete before you can start the workflow:</span></span>

- <span data-ttu-id="85325-107">Prozess: Jeder dem Überprüfungssatz hinzugefügte Lastensatz wird hier als "Container" gezeigt.</span><span class="sxs-lookup"><span data-stu-id="85325-107">Process: each load set added to the review set will show up as a "container" here.</span></span> <span data-ttu-id="85325-108">Sie müssen diese Dokumente verarbeiten, bevor Sie sie dem Relevanzmodul hinzufügen können. Hier können Sie sie auch als Seed markieren oder für ein bestimmtes Problem vorab markieren.</span><span class="sxs-lookup"><span data-stu-id="85325-108">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>

- <span data-ttu-id="85325-109">Relevanz hinzufügen: Unter Relevanzlasten können Sie Dokumente hinzufügen, die zu Relevanz verarbeitet wurden, um sie für \> Schulungen verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="85325-109">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="85325-110">Der Relevanzworkflow wird wie folgt angezeigt und beschrieben:</span><span class="sxs-lookup"><span data-stu-id="85325-110">The Relevance workflow is shown and described as follows:</span></span>
  
![Relevanzworkflow](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="85325-112">**Bewertungs- und Nachverfolgungszyklen:**</span><span class="sxs-lookup"><span data-stu-id="85325-112">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="85325-113">**Bewertung**: Ermöglicht eine frühzeitige Bewertung basierend auf einer zufälligen Stichprobe von Dateien und verwendet diese Bewertung, um Entscheidungen anzuwenden, um die Leistung des Vorhersagecodierungsprozesses zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="85325-113">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="85325-114">**Track**: Berechnen und Anzeigen von Zwischenergebnissen der Bewertung während der Überwachung der statistischen Gültigkeit des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="85325-114">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="85325-115">**Zyklen von Schulungen und Nachverfolgung**</span><span class="sxs-lookup"><span data-stu-id="85325-115">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="85325-116">**Tag**: Advanced eDiscovery die relevanzspezifischen Kriterien für jedes Problem basierend auf der iterativen Überprüfung und Kennzeichnung einzelner Dateien durch den Experten.</span><span class="sxs-lookup"><span data-stu-id="85325-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="85325-117">**Track**: Berechnen und Anzeigen von Zwischenergebnissen der Relevanzschulung während der Überwachung der statistischen Gültigkeit des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="85325-117">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="85325-118">**Batchberechnung:** Die kumulierten und gelernten Relevanzkriterien werden auf die gesamte Dateisammlung angewendet, und für jede Datei wird eine Relevanzpunktzahl generiert.</span><span class="sxs-lookup"><span data-stu-id="85325-118">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="85325-119">**Entscheidung**: Die Ergebnisse der Analyse, die auf den gesamten Fall angewendet wurde, werden nach der Batchberechnung angezeigt, und Daten, die zum Treffen von Entscheidungen zur Dokumentüberprüfung verwendet werden, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85325-119">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="85325-120">**Test:** Die Ergebnisse können getestet werden, um die Gültigkeit und Effektivität der Advanced eDiscovery zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="85325-120">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>

- <span data-ttu-id="85325-121">**Suche**: Sobald der Relevanzworkflow abgeschlossen ist, können Sie die Ausgabe wie z. B. das Lesen von Perzentil eines Dokuments für Ihr Problem verwenden, wenn Sie eine Abfrage in Ihrem Überprüfungssatz ausführen.</span><span class="sxs-lookup"><span data-stu-id="85325-121">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your review set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="85325-122">Richtlinien für Relevanzschulungen und -überprüfungen</span><span class="sxs-lookup"><span data-stu-id="85325-122">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="85325-123">Im Folgenden finden Sie eine Übersicht über Richtlinien für Relevanzschulungen und -überprüfungen:</span><span class="sxs-lookup"><span data-stu-id="85325-123">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="85325-124">**Fehler und Inkonsistenzen:** Wenn während der Schulung Taggingfehler auftreten, kehren Sie zu vorherigen Dateibeispielen zurück, um sie zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="85325-124">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="85325-125">Wenn zu viele Fehler zu korrigieren sind oder eine neue Perspektive für den Fall oder das Problem vor liegt, sollten die Relevanzkriterien vom Administrator neu definiert und die Relevanzschulung neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="85325-125">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="85325-126">**Tagging und Schulungen**:</span><span class="sxs-lookup"><span data-stu-id="85325-126">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="85325-127">Dateien sollten nur basierend auf Inhalten markiert werden.</span><span class="sxs-lookup"><span data-stu-id="85325-127">Files should be tagged based on content only.</span></span> <span data-ttu-id="85325-128">Berücksichtigen Sie keine Metadaten, z. B. Custodian, Datum oder Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="85325-128">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="85325-129">Berücksichtigen Sie beim Markieren von Dateien keine Datumsbereichsangaben im Text.</span><span class="sxs-lookup"><span data-stu-id="85325-129">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="85325-130">Berücksichtigen Sie beim Markieren von Dateien keine eingebetteten grafischen Bilder.</span><span class="sxs-lookup"><span data-stu-id="85325-130">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="85325-131">Auf Relevanz angewendeter Text ignorieren wird im angezeigten Dateiinhalt in der Textansicht in Relevanz entfernt.</span><span class="sxs-lookup"><span data-stu-id="85325-131">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="85325-132">Wenn die Werte für Text ignorieren definiert wurden, nachdem die Relevanzschulung bereits gestartet wurde, wird der neue ignorierte Text auf Beispieldateien angewendet, die an dem Punkt erstellt wurden, an dem er definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="85325-132">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="85325-133">Das Feature Text ignorieren sollte vorsichtig verwendet werden, da seine Verwendung die Leistung der Dateianalyse beeinträchtigen kann.</span><span class="sxs-lookup"><span data-stu-id="85325-133">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="85325-134">Verwenden Sie **die Option Tagging** überspringen nur bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="85325-134">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="85325-135">Advanced eDiscovery wird nicht basierend auf übersprungenen Dateien trainiert.</span><span class="sxs-lookup"><span data-stu-id="85325-135">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="85325-136">Wenn es schwierig ist, festzustellen, ob eine Datei relevant ist, ist es bei der Bewertung besser, wenn möglich als Relevant (R) oder Nicht relevant (NR) zu kennzeichnen, anstatt Skip zu **wählen.**</span><span class="sxs-lookup"><span data-stu-id="85325-136">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="85325-137">Wenn Advanced eDiscovery Die Schulung ausgewertet wird, wird dann deutlich, wie gut diese Dateitypen verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="85325-137">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="85325-138">Selbst Dateien mit einer sehr geringen Menge extrahierten Textes sollten in Schulungen als R/NR gekennzeichnet werden, und nicht nach Möglichkeit als "Überspringen".</span><span class="sxs-lookup"><span data-stu-id="85325-138">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="85325-139">Tagging kann sich auf den Klassifizierungstyp auswirken, solange die Datei lesbar ist und als R/NR gekennzeichnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="85325-139">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="85325-140">Die Dateisequenznummer in der Liste der angezeigten Beispieldateien auf der Registerkarte **Tag** ermöglicht es dem Benutzer, zur ursprünglich angezeigten Reihenfolge der Dateien zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="85325-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="85325-141">Sie können zu einem beliebigen Beispiel wechseln und die Markierung der Bewertungs- und Schulungssetdateien ändern.</span><span class="sxs-lookup"><span data-stu-id="85325-141">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="85325-142">Die Änderungen werden beim Erstellen des nächsten Beispiels angewendet.</span><span class="sxs-lookup"><span data-stu-id="85325-142">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="85325-143">Gescannte Excel dateien im PDF-Format sollten beim Markieren von Dateien wie systemeigene Excel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="85325-143">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="85325-144">Wenn Sie zweifeln hinsichtlich der Relevanztagging einer Datei, wenden Sie sich an einen Experten.</span><span class="sxs-lookup"><span data-stu-id="85325-144">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="85325-145">Falsche Markierungen während des Relevanztrainings können zu einem späteren Zeitpunkt im Prozess zu Zeit verloren gehen und sich auch negativ auf die Qualität der Gesamtergebnisse auswirken.</span><span class="sxs-lookup"><span data-stu-id="85325-145">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="85325-146">Schlüsselwörter, die in Stichwortlisten definiert wurden, werden in Farben angezeigt, um dem Benutzer zu helfen, relevante Dateien beim Markieren zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="85325-146">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="85325-147">**Batchberechnung:** Dateien, die vom Experten als R/NR gekennzeichnet wurden, erhalten eine Bewertung von 0 oder 100.</span><span class="sxs-lookup"><span data-stu-id="85325-147">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="85325-148">Dies gilt für Markierungen, die vor der Batchberechnung vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="85325-148">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="85325-149">Wenn der Experte das Problem nach der Batchberechnung in Leerlauf umgestellt hat und dieses Problem weiterhin taggiert, sind die neu markierten Ergebnisse nicht 100/0, sondern die ursprüngliche Bewertung.</span><span class="sxs-lookup"><span data-stu-id="85325-149">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="85325-150">**Probleme und Samplingmodus:** Probleme werden in der Regel deaktiviert, wenn die Arbeit an ihnen abgeschlossen ist (Relevanzschulungen werden stabilisiert und Batchberechnungen durchgeführt), wenn die Probleme abgebrochen werden oder wenn ein anderer Benutzer an den Problemen arbeitet.</span><span class="sxs-lookup"><span data-stu-id="85325-150">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="85325-151">Schritte in Relevanzschulungen</span><span class="sxs-lookup"><span data-stu-id="85325-151">Steps in Relevance training</span></span>

<span data-ttu-id="85325-152">Auf der **Registerkarte \> Relevanzspur** enthält Advanced eDiscovery Empfehlungen zum Fortfahren in der Verarbeitung mit den folgenden nächsten Schritten.</span><span class="sxs-lookup"><span data-stu-id="85325-152">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="85325-153">Die Auswirkungen werden unten beschrieben, wenn jeder der folgenden Schritte im Relevanzschulungsprozess empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="85325-153">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="85325-154">Tagging/Continue-Tagging: Dateiüberprüfung und Relevanztagging, die von einem Experten für jede Datei und jedes Problem innerhalb eines Beispiels durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="85325-154">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="85325-155">Implikationen: Ein vorhandenes Beispiel muss markiert werden.</span><span class="sxs-lookup"><span data-stu-id="85325-155">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="85325-156">Bewertung/Fortsetzung der Bewertung: Ermöglicht eine frühzeitige Überprüfung der Relevanz des Fallproblems und eine vorläufige Ansicht der Relevanz der für den aktuellen Fall importierten Dateigesamtheit.</span><span class="sxs-lookup"><span data-stu-id="85325-156">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="85325-157">Implikationen: Es ist eine weitere Bewertung erforderlich oder empfohlen.</span><span class="sxs-lookup"><span data-stu-id="85325-157">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="85325-158">Schulung/Weiterbildung: Prozess, bei dem Advanced eDiscovery von dem Experten lernt, der die Dateibeispiele tagt und die Möglichkeit erhält, Relevanzkriterien zu identifizieren, die für jedes Problem im Kontext jedes Falls relevant sind.</span><span class="sxs-lookup"><span data-stu-id="85325-158">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="85325-159">Implikationen: Das Problem benötigt mehr Schulungen; das nächste Beispiel sollte erstellt und markiert werden.</span><span class="sxs-lookup"><span data-stu-id="85325-159">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="85325-160">Batchberechnung: Relevanzprozess, bei dem Advanced eDiscovery das während der Schulung erworbene Wissen aufnimmt und auf die gesamte Dateigesamtheit angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="85325-160">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="85325-161">Alle Dateien in der relevanten Dateigruppe werden auf Relevanz geprüft und einer Relevanznote zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="85325-161">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="85325-162">Implikationen: Das Problem hat sich stabilisiert, und die Batchberechnung kann durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="85325-162">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="85325-163">Nachholbedarf: Relevanz gibt an, wann ein Experte ein Beispiel von Dateien überprüft und tagt, die während eines Rolling Loads-Szenarios aus einer zusätzlichen Dateilast ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="85325-163">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="85325-164">Implikationen: Es wurde eine neue Last hinzugefügt, und die Nachholzeit ist erforderlich, um weiter zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="85325-164">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="85325-165">Inkonsistenzen des Tags: Der Prozess identifiziert über einen Advanced eDiscovery-Algorithmus Inkonsistenzen im Dateitaggingprozess, die sich negativ auf die Analyse auswirken können.</span><span class="sxs-lookup"><span data-stu-id="85325-165">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="85325-166">Implikationen: Das nächste Beispiel enthält Dateien, die in vorherigen Beispielen markiert wurden, und deren Markierung muss rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="85325-166">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="85325-167">Updateklassifikator: Ermöglicht dem Benutzer das Anwenden von Tagging- oder Seedingänderungen.</span><span class="sxs-lookup"><span data-stu-id="85325-167">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="85325-168">Implikationen: Markierungs- und Seedingänderungen können angewendet werden, ohne ein weiteres Relevanzbeispiel manuell ausführen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="85325-168">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="85325-169">In Warteschleife: Der Relevanzschulungsprozess ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="85325-169">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="85325-170">Implikationen: Derzeit ist keine Relevanzschulung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="85325-170">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="85325-171">Obwohl Advanced eDiscovery Sie durch den Prozess führt, können Sie mit empfohlenen Nächsten Schritten in unterschiedlichen Phasen auch zwischen Registerkarten und Seiten navigieren und Entscheidungen treffen, um Situationen zu beheben, die für Ihren individuellen Fall-, Problem- oder Dokumentüberprüfungsprozess relevant sein können.</span><span class="sxs-lookup"><span data-stu-id="85325-171">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="85325-172">Es ist möglich, die Auswahlmöglichkeiten für die Advanced eDiscovery nächsten Schritt zu akzeptieren oder außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="85325-172">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="85325-173">Wenn Sie einen anderen Schritt als den empfohlenen  Nächsten Schritt ausführen möchten, klicken Sie  im Dialogfeld auf den nächsten Schritt, der in der erweiterten Problemanzeige aufgeführt ist, klicken Sie auf die Schaltfläche Ändern neben dem nächsten Schritt, und wählen Sie eine weitere Option Nächsten Schritt aus.</span><span class="sxs-lookup"><span data-stu-id="85325-173">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="85325-174">Einige Optionen bleiben nach dem Entsperren möglicherweise deaktiviert, da sie zu diesem Zeitpunkt im Prozess nicht zur Verwendung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="85325-174">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="85325-175">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85325-175">More information</span></span>

[<span data-ttu-id="85325-176">Grundlegendes zur Bewertung in Relevanz</span><span class="sxs-lookup"><span data-stu-id="85325-176">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="85325-177">Tagging und Bewertung</span><span class="sxs-lookup"><span data-stu-id="85325-177">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="85325-178">Tagging- und Relevanzschulungen</span><span class="sxs-lookup"><span data-stu-id="85325-178">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="85325-179">Verfolgen der Relevanzanalyse</span><span class="sxs-lookup"><span data-stu-id="85325-179">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="85325-180">Entscheidung basierend auf den Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="85325-180">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="85325-181">Testen der Relevanzanalyse</span><span class="sxs-lookup"><span data-stu-id="85325-181">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="85325-182">Abfragen der Daten in einem Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="85325-182">Query the data in a review set</span></span>](review-set-search.md)
