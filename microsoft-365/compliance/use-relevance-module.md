---
title: Verwenden des Moduls "Relevanz" zum Analysieren von Daten in Evidence
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
description: ''
ms.openlocfilehash: cf69f76fd461c718bccb560f91bf31c2e30aea39
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601292"
---
# <a name="use-the-relevance-module-to-analyze-data-in-evidence"></a><span data-ttu-id="6f532-102">Verwenden des Moduls "Relevanz" zum Analysieren von Daten in Evidence</span><span class="sxs-lookup"><span data-stu-id="6f532-102">Use the Relevance module to analyze data in evidence</span></span>

<span data-ttu-id="6f532-103">In Data Investigations (Preview) enthält das Modul Relevanz die Relevanz Schulung und Überprüfung von Dateien im Zusammenhang mit einer Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="6f532-103">In Data Investigations (Preview), the Relevance module includes the Relevance training and review of files related to an investigation.</span></span> <span data-ttu-id="6f532-104">Der Relevanz-Workflow wird wie folgt dargestellt und beschrieben:</span><span class="sxs-lookup"><span data-stu-id="6f532-104">The Relevance workflow is shown and described as follows:</span></span>
  
![Relevanz-Workflow](media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="6f532-106">**Zyklen der Bewertung und Nachverfolgung**:</span><span class="sxs-lookup"><span data-stu-id="6f532-106">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="6f532-107">**Bewertung**: ermöglicht eine frühe Bewertung basierend auf einer zufälligen Stichprobe von Dateien und verwendet diese Bewertung, um Entscheidungen zu treffen, um die Leistung des vorhersagbaren Codierungsprozesses zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="6f532-107">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="6f532-108">**Track**: berechnen und Anzeigen von vorläufigen Ergebnissen der Bewertung bei gleichzeitiger Überwachung der statistischen Gültigkeit des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="6f532-108">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="6f532-109">**Trainingszyklen und Nachverfolgung**</span><span class="sxs-lookup"><span data-stu-id="6f532-109">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="6f532-110">**Tag**: Data Investigations (Preview) erlernt Relevanz-Kriterien für jedes Problem, basierend auf der iterativen Überprüfung und Markierung der einzelnen Dateien durch den Experten.</span><span class="sxs-lookup"><span data-stu-id="6f532-110">**Tag**: Data Investigations (Preview) learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="6f532-111">**Track**: berechnen und Anzeigen von Zwischenergebnissen der Relevanz-Schulung bei gleichzeitiger Überwachung der statistischen Gültigkeit des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="6f532-111">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="6f532-112">**Batch Berechnung**: die akkumulierten und gelernten Relevanz-Kriterien werden auf die gesamte Dateisammlung angewendet, und für jede Datei wird ein Relevanz-Score generiert.</span><span class="sxs-lookup"><span data-stu-id="6f532-112">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="6f532-113">**Entscheidung**: die Ergebnisse der Analyse, die auf den gesamten Fall angewendet werden, werden nach der Batch Berechnung angezeigt, und es werden Daten angezeigt, mit denen die Dokument Überprüfungs Entscheidungen getroffen werden.</span><span class="sxs-lookup"><span data-stu-id="6f532-113">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="6f532-114">**Test**: Ergebnisse können getestet werden, um die Gültigkeit und Effektivität der Verarbeitung von Daten Untersuchungen (Preview) zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6f532-114">**Test**: Results can be tested to verify the validity and effectiveness of the Data Investigations (Preview) processing.</span></span>

- <span data-ttu-id="6f532-115">**Suche**: Wenn Sie den Relevanz-Workflow abgeschlossen haben, können Sie die Ausgabe wie etwa das Quantil eines Dokuments für Ihr Problem verwenden, wenn Sie eine Abfrage innerhalb Ihres Arbeitssatzes ausführen.</span><span class="sxs-lookup"><span data-stu-id="6f532-115">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="6f532-116">Richtlinien für die Relevanz-Schulung und-Prüfung</span><span class="sxs-lookup"><span data-stu-id="6f532-116">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="6f532-117">Im folgenden finden Sie eine Übersicht über Richtlinien für die Relevanz-Schulung und-Überprüfung:</span><span class="sxs-lookup"><span data-stu-id="6f532-117">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="6f532-118">**Fehler und Inkonsistenzen**: Wenn Markierungsfehler während des Trainings vorgenommen werden, kehren Sie zu vorherigen Datei Beispielen zurück, um Sie zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="6f532-118">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="6f532-119">Wenn zu viele Fehler zu korrigieren sind oder eine neue Perspektive für den Fall oder das Problem vorliegt, sollten die Relevanz-Kriterien vom Administrator neu definiert werden, und die Relevanz-Schulung wurde neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="6f532-119">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="6f532-120">**Tagging und Schulung**:</span><span class="sxs-lookup"><span data-stu-id="6f532-120">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="6f532-121">Dateien sollten nur auf der Grundlage von Inhalt gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="6f532-121">Files should be tagged based on content only.</span></span> <span data-ttu-id="6f532-122">Metadaten wie Depot, Datum oder Dateipfad werden nicht als solche betrachtet.</span><span class="sxs-lookup"><span data-stu-id="6f532-122">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="6f532-123">Berücksichtigen Sie keine Datumsbereichs Angaben im Text beim Markieren von Dateien.</span><span class="sxs-lookup"><span data-stu-id="6f532-123">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="6f532-124">Berücksichtigen Sie beim Markieren von Dateien keine eingebetteten grafischen Bilder.</span><span class="sxs-lookup"><span data-stu-id="6f532-124">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="6f532-125">Auf Relevanz angewendeter Text ignorieren wird im angezeigten Dateiinhalt in der Textansicht relevant entfernt.</span><span class="sxs-lookup"><span data-stu-id="6f532-125">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="6f532-126">Wenn die Werte für Ignore Text nach dem bereits begonnenen Relevanz Training definiert wurden, wird der neue ignorierte Text auf Beispieldateien angewendet, die an dem Ort erstellt wurden, an dem er definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6f532-126">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="6f532-127">Das Feature Text ignorieren sollte vorsichtig verwendet werden, da die Leistung der Dateianalyse durch die Verwendung reduziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6f532-127">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="6f532-128">Verwenden Sie die Option " **Tagging überspringen** " nur, wenn dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6f532-128">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="6f532-129">Daten Untersuchungen (Vorschau) werden nicht basierend auf übersprungenen Dateien trainiert.</span><span class="sxs-lookup"><span data-stu-id="6f532-129">Data Investigations (Preview) does not train based on skipped files.</span></span> <span data-ttu-id="6f532-130">Wenn es schwierig ist, festzustellen, ob eine Datei relevant ist, ist es besser, nach Möglichkeit als relevant (n) oder nicht relevant (Nr) zu markieren, anstatt **Skip**auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6f532-130">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="6f532-131">Wenn Daten Untersuchungen (Preview) das Training auswerten, kann man dann sehen, wie gut diese Dateitypen verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="6f532-131">When Data Investigations (Preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="6f532-132">Selbst Dateien mit einer sehr kleinen Menge extrahierten Texts sollten im Training als R/Nr und nicht als "Skip" markiert werden, wenn möglich.</span><span class="sxs-lookup"><span data-stu-id="6f532-132">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="6f532-133">Tagging kann sich auf die Klassifizierung auswirken, solange die Datei lesbar ist und als R/Nr gekennzeichnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6f532-133">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="6f532-134">Die Dateisequenz Nummer in der Liste der angezeigten Beispieldateien auf der Registerkarte **Tag** ermöglicht es dem Benutzer, zur ursprünglichen angezeigten Reihenfolge der Dateien zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="6f532-134">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="6f532-135">Sie können zu einem beliebigen Beispiel zurückkehren und die Kennzeichnung der Bewertungs-und Schulungs Mappen-Dateien ändern.</span><span class="sxs-lookup"><span data-stu-id="6f532-135">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="6f532-136">Die Änderungen werden angewendet, wenn das nächste Beispiel erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6f532-136">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="6f532-137">Gescannte Excel-Dateien im PDF-Format sollten beim Markieren von Dateien identisch mit systemeigenen Excel-Dateien behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="6f532-137">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="6f532-138">Wenn Sie in Bezug auf die Relevanz der Kennzeichnung einer Datei Zweifel haben, wenden Sie sich an einen Experten.</span><span class="sxs-lookup"><span data-stu-id="6f532-138">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="6f532-139">Falsche Kennzeichnung während des Relevanz-Trainings kann zu einem späteren Zeitpunkt des Prozesses zu einem Zeitverlust führen und kann sich auch negativ auf die Qualität der Gesamtergebnisse auswirken.</span><span class="sxs-lookup"><span data-stu-id="6f532-139">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="6f532-140">Schlüsselwörter, die in Stichwortlisten definiert wurden, werden in Farben angezeigt, damit der Benutzer relevante Dateien beim Tagging identifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="6f532-140">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="6f532-141">**Batch Berechnung**: Dateien, die vom Experten als R/Nr markiert wurden, erhalten eine Punktzahl von 0 oder 100.</span><span class="sxs-lookup"><span data-stu-id="6f532-141">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="6f532-142">Dies gilt für Tagging, das vor der Batch Berechnung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6f532-142">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="6f532-143">Wenn der Experte das Problem nach der Batch Berechnung in den Leerlauf umgeschaltet und das Problem fortgesetzt hat, werden die neu markierten Ergebnisse nicht 100/0, sondern die ursprüngliche Punktzahl sein.</span><span class="sxs-lookup"><span data-stu-id="6f532-143">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="6f532-144">**Probleme und Samplingmodus**: Probleme werden normalerweise deaktiviert, wenn die Arbeit an Ihnen abgeschlossen ist (Relevanz-Training wird stabilisiert und Batch Berechnung wurde durchgeführt), wenn die Probleme abgebrochen werden oder wenn ein anderer Benutzer an den Problemen arbeitet.</span><span class="sxs-lookup"><span data-stu-id="6f532-144">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="6f532-145">Schritte zur Relevanz-Schulung</span><span class="sxs-lookup"><span data-stu-id="6f532-145">Steps in Relevance training</span></span>

<span data-ttu-id="6f532-146">Auf der Registerkarte \*\*relevanzstatus \> \*\* werden mit den folgenden nächsten Schritten Empfehlungen zur Vorgehensweise bei der Verarbeitung von Daten Untersuchungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6f532-146">In the **Relevance \> Track** tab, Data investigations provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="6f532-147">Die Auswirkungen werden im folgenden beschrieben, wenn jeder der folgenden Schritte im Relevanz-Schulungsprozess empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="6f532-147">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="6f532-148">Tagging/Continue Tagging: Dateiüberprüfung und Relevanz-Tagging, die von einem Experten für jede Datei und jedes Problem in einem Beispiel ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6f532-148">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="6f532-149">Implikation: ein vorhandenes Beispiel muss markiert werden.</span><span class="sxs-lookup"><span data-stu-id="6f532-149">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="6f532-150">Assessment/Continue Assessment: ermöglicht frühzeitiges Überprüfen der Fall Ausgabe Relevanz und eine vorläufige Ansicht der Relevanz der für den aktuellen Fall importierten Datei Auffüllung.</span><span class="sxs-lookup"><span data-stu-id="6f532-150">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="6f532-151">Implikation: Es ist eine weitere Bewertung erforderlich oder empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="6f532-151">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="6f532-152">Schulung/Fortsetzung der Schulung: Prozess, in dem Daten Untersuchungen von dem Experten erlernt werden, der die Dateibeispiele kennzeichnen kann, und die Fähigkeit erlangt, relevante Kriterien für jedes Problem im Kontext jedes Einzelfalls zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6f532-152">Training / Continue training: Process during which Data investigations learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="6f532-153">Implikation: das Problem erfordert mehr Schulung; Das nächste Beispiel sollte erstellt und markiert werden.</span><span class="sxs-lookup"><span data-stu-id="6f532-153">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="6f532-154">Batch Berechnung: relevanzprozess, bei dem Daten Untersuchungen das erworbene Wissen während der Schulungsphase erwerben und auf die gesamte Datei Auffüllung anwenden.</span><span class="sxs-lookup"><span data-stu-id="6f532-154">Batch calculation: Relevance process in which Data investigations takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="6f532-155">Alle Dateien in der entsprechenden Dateigruppe werden auf Relevanz ausgewertet und einem Relevanz-Score zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6f532-155">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="6f532-156">Implikation: das Problem wurde stabilisiert, und die Batch Berechnung kann ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6f532-156">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="6f532-157">Catch-up: Relevanz gibt an, wann ein Experte ein Beispiel für Dateien prüft und kennzeichnet, die aus einer zusätzlichen Datei Auslastung während eines Szenarios mit Rollen Lasten ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="6f532-157">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="6f532-158">Implikation: eine neue Last wurde hinzugefügt, und Nachholbedarf ist erforderlich, um die Arbeit fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="6f532-158">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="6f532-159">Tag Inkonsistenzen: Prozess identifiziert über einen Algorithmus für Daten Untersuchungen Inkonsistenzen im Datei Kennzeichnungs Prozess, die sich möglicherweise negativ auf die Analyse auswirken.</span><span class="sxs-lookup"><span data-stu-id="6f532-159">Tag inconsistencies: Process identifies, via an Data investigations algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="6f532-160">Implikation: das nächste Beispiel enthält Dateien, die in vorherigen Beispielen markiert wurden, und ihre Kennzeichnung muss erneut ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6f532-160">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="6f532-161">Update Klassifizierung: ermöglicht dem Benutzer das Anwenden von Markierungen oder Seeding Änderungen.</span><span class="sxs-lookup"><span data-stu-id="6f532-161">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="6f532-162">Implikation: das Tagging und das Seeding können geändert werden, ohne dass ein weiteres Relevanz-Beispiel manuell ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="6f532-162">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="6f532-163">In der Warteschleife: der Relevanz-Schulungsprozess ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6f532-163">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="6f532-164">Implikation: an dieser Position ist keine Relevanz-Schulung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6f532-164">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="6f532-165">Obwohl Daten Untersuchungen Sie durch den Prozess führen, mit empfohlenen nächsten Schritten in verschiedenen Phasen, können Sie auch zwischen Registerkarten und Seiten navigieren und Entscheidungen treffen, um Situationen zu beheben, die für den jeweiligen Fall, das Problem oder Dokument Überprüfungsprozess.</span><span class="sxs-lookup"><span data-stu-id="6f532-165">Although Data investigations guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="6f532-166">Es ist möglich, Daten Untersuchungen im nächsten Schritt zur Verarbeitung von Optionen zu akzeptieren oder außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="6f532-166">It is possible to accept or override Data investigations Next step processing choices.</span></span> <span data-ttu-id="6f532-167">Wenn Sie einen anderen Schritt als den empfohlenen nächsten Schritt durchführen möchten, klicken Sie auf den **nächsten Schritt** , der in der erweiterten Problemanzeige im Dialogfeld aufgeführt ist, klicken Sie neben dem nächsten Schritt auf die Schaltfläche **ändern** , und wählen Sie eine andere Option für nächsten Schritt aus.</span><span class="sxs-lookup"><span data-stu-id="6f532-167">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6f532-168">Einige Optionen bleiben nach dem entsperren möglicherweise deaktiviert, da Sie für die Verwendung zu diesem Zeitpunkt im Prozess nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="6f532-168">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="6f532-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f532-169">More information</span></span>

[<span data-ttu-id="6f532-170">Grundlegendes zur Relevanz der Bewertung</span><span class="sxs-lookup"><span data-stu-id="6f532-170">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6f532-171">Tagging und Bewertung</span><span class="sxs-lookup"><span data-stu-id="6f532-171">Tagging and assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6f532-172">Tagging und Relevanz Training</span><span class="sxs-lookup"><span data-stu-id="6f532-172">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6f532-173">Analyse der nach Verfolgungs Relevanz</span><span class="sxs-lookup"><span data-stu-id="6f532-173">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6f532-174">Entscheidung basierend auf den Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="6f532-174">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6f532-175">Testen der Relevanz-Analyse</span><span class="sxs-lookup"><span data-stu-id="6f532-175">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="6f532-176">Abfragen der Daten in Evidence</span><span class="sxs-lookup"><span data-stu-id="6f532-176">Query the data in evidence</span></span>](evidence-query.md)
