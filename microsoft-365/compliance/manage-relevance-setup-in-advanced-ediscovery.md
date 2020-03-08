---
title: Verwalten der Einrichtung von Relevanz in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
description: Lesen Sie die Empfehlungen zum Einrichten des Relevanztrainings in Office 365 Advanced eDiscovery, um Dateien nach ihrer Relevanz zu beurteilen und Analyseergebnisse zu generieren.
ms.openlocfilehash: 49c7614eb1fec4e61fb374fb637093fd6e860619
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557885"
---
# <a name="manage-relevance-setup-in-advanced-ediscovery-classic"></a><span data-ttu-id="d08d2-103">Verwalten der Einrichtung von Relevanz in Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="d08d2-103">Manage Relevance setup in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="d08d2-p101">Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="d08d2-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="d08d2-p102">Bei der Relevanztechnologie von Advanced eDiscovery wird eine Software unter Anleitung von Experten zum Bewerten von Dateien nach ihrer Relevanz eingesetzt. Das Relevanzmodul in Advanced eDiscovery kann für eine frühzeitige Falleinschätzung, zum Sortieren und zur Überprüfung von Dateibeispielen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d08d2-p102">Advanced eDiscovery Relevance technology employs expert-guided software for scoring files by their relevance. Advanced eDiscovery Relevance can be used for Early Case Assessment (ECA), culling, and file sample review.</span></span> 
  
 <span data-ttu-id="d08d2-p103">Advanced eDiscovery umfasst die Komponenten für das Relevanztraining und das Markieren von Dateien, die für einen Fall relevant sind. Advanced eDiscovery lernt anhand der trainierten Beispiele relevanter und nicht relevanter Dateien, um Relevanzbewertungen für jede Datei bereitzustellen, und generiert Analyseergebnisse, die während und nach dem Dateiüberprüfungsprozess verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d08d2-p103">Advanced eDiscovery includes components for the Relevance training and tagging of files relevant to a case. Advanced eDiscovery learns from the trained samples of Relevant and Not Relevant files to provide Relevance scores for each file, and generates analytical results that can be used during and after the file review process.</span></span> 
  
## <a name="guidelines-for-setting-up-relevance-training"></a><span data-ttu-id="d08d2-110">Richtlinien zum Einrichten des Relevanztrainings</span><span class="sxs-lookup"><span data-stu-id="d08d2-110">Guidelines for setting up Relevance training</span></span>

 <span data-ttu-id="d08d2-p104">Wählen Sie in Advanced eDiscovery im Fenster **Fälle** einen Fall aus, und klicken Sie auf **Zum Fall wechseln**. Klicken Sie auf **Relevanz** \> **Einrichten von Relevanz**. Befolgen Sie die folgenden empfohlenen Richtlinien zum Einrichten von Relevanz.</span><span class="sxs-lookup"><span data-stu-id="d08d2-p104">In Advance eDiscovery, in the **Cases** window, select a case and click **Go to case**. Click **Relevance** \> **Relevanace setup**. Follow these recommended guidelines to setup Relevance.</span></span> 
  
- <span data-ttu-id="d08d2-114">**Markieren**: Die Effektivität des iterativen Relevanztrainingsprozesses ist von der Fähigkeit des Experten abhängig, die Dateibeispiele präzise und konsistent zu markieren.</span><span class="sxs-lookup"><span data-stu-id="d08d2-114">**Tagging**: The effectiveness of the iterative Relevance training process is dependent on the ability of the expert to tag the file samples with precision and consistency.</span></span>
    
- <span data-ttu-id="d08d2-115">**Fallprobleme**:</span><span class="sxs-lookup"><span data-stu-id="d08d2-115">**Case issues**:</span></span> 
    
  - <span data-ttu-id="d08d2-p105">Verwenden Sie im gesamten Relevanztrainingsprozess für jedes Problem denselben Experten. Das gleichzeitige Markieren desselben Problems durch mehrere Experten ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="d08d2-p105">For each issue, use the same expert throughout the entire Relevance training process. Simultaneous tagging of the same issue by multiple experts is not permitted.</span></span>
    
  - <span data-ttu-id="d08d2-118">Ermitteln Sie, ob jede Gruppe von Dateien nur für ein bestimmtes Problem relevant ist.</span><span class="sxs-lookup"><span data-stu-id="d08d2-118">Determine if each group of files is pertinent only to a specific issue.</span></span> 
    
  - <span data-ttu-id="d08d2-p106">Wenn ein Problem zu allgemein definiert ist, werden in Advanced eDiscovery möglicherweise zu viele Dateien gefunden, die eigentlich nicht relevant sind. Wenn ein Problem zu eng definiert ist, dauert der Relevanztrainingsprozess möglicherweise länger.</span><span class="sxs-lookup"><span data-stu-id="d08d2-p106">If an issue is defined too generally, Advanced eDiscovery may yield too many files that are actually not relevant. If an issue is defined too narrowly, the Relevance training process may take more time.</span></span> 
    
  - <span data-ttu-id="d08d2-121">Bei jedem Zyklus des Relevanztrainings befasst sich Advanced eDiscovery mit einem einzigen aktiven Problem, und es werden Zwischenergebnisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d08d2-121">During each Relevance training cycle, Advanced eDiscovery focuses on a single active issue and interim sample results are displayed accordingly.</span></span>
    
  - <span data-ttu-id="d08d2-p107">In einem Szenario mit mehreren Problemen können mithilfe des Samplingmodus die Probleme ausgewählt werden, die in die Verarbeitung aufgenommen werden sollen. Probleme, die als „deaktiviert“ definiert sind, werden erst verarbeitet, wenn ihr Samplingmodus geändert wird. Ein Problem kann nur für einen Experten „im Leerlauf“ oder „aktiviert“ sein.</span><span class="sxs-lookup"><span data-stu-id="d08d2-p107">In a multiple-issue scenario, the Sampling mode enables the selection of issues to be included in processing. Issues defined as "off" are not handled until their Sampling mode is changed. An issue can be "idle" or "on" for only one expert.</span></span>
    
  -  <span data-ttu-id="d08d2-p108">Advanced eDiscovery kann zum Generieren von Kandidatberechtigungsdateien verwendet werden. Richten Sie ein separates Problem für Berechtigungen ein. Wenn möglich, trainieren und sortieren Sie erst im Hinblick auf Relevanz. Trainieren Sie dann im Hinblick auf die Berechtigung nur für den sortierten Satz (laden Sie den sortierten Satz als separaten Fall erneut).</span><span class="sxs-lookup"><span data-stu-id="d08d2-p108">Advanced eDiscovery can be used to generate candidate privilege files. Set up a separate issue for privilege. If possible, train and cull for relevance first, and then train for privilege on the culled set only (reload the culled set as a separate case).</span></span> 
    
  - <span data-ttu-id="d08d2-p109">Die Batchberechnung kann nur ausgeführt werden, wenn keine offenen Beispiele vorhanden sind (beim Klicken auf „Batchberechnung“ wird eine Liste von Benutzern mit offenen Beispielen angezeigt). Um Beispiele von anderen Benutzern zu schließen (dies sollte nur durchgeführt werden, wenn diese Benutzer diese Beispiele nicht markieren), kann ein Administrator das Dienstprogramm „Relevanz ändern“ mit der Option des Beispiels für alle Benutzer verwenden.</span><span class="sxs-lookup"><span data-stu-id="d08d2-p109">Batch calculation can be performed only when there are no open samples (when clicking Batch Calculation, there will be a list displayed of users with open samples). To "close" samples of other users (this should be performed only if these users are not tagging these samples), an Administrator can use the "Modify relevance" utility with the "All users sample" option.</span></span>
    
- <span data-ttu-id="d08d2-p110">**Metadaten**: Advanced eDiscovery konzentriert sich auf Inhalte. Es werden keine Metadaten als Teil der Relevanzkriterien berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="d08d2-p110">**Metadata**: Advanced eDiscovery focuses on content. It does not consider metadata as part of the relevance criteria.</span></span> 
    
- <span data-ttu-id="d08d2-132">**Relevanzgrad**: Wenn der Relevanzgrad für ein Problem nach der Bewertung unter 3 % liegt, sollte das Seeding des Relevanztrainings mit bekannten relevanten und nicht relevanten Dateien ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d08d2-132">**Richness**: If the Richness for an issue is less than 3% after Assessment, consider seeding the Relevance training with known Relevant and Not Relevant files.</span></span>
    
- <span data-ttu-id="d08d2-p111">**Dateigröße**: Große Dateien (über 5.242.880 Zeichen extrahierter Text) werden im Relevanztool ignoriert. Die Dateien sind nicht am Relevanztrainingsprozess beteiligt und erhalten nach der Batchberechnung keine Relevanzbewertung. Dateien über 5 MB können in dem Bewertungssatz aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="d08d2-p111">**File size**: Large files (over 5,242,880 characters of extracted text) are ignored in Relevance. The files do not participate in the Relevance training process and do not receive a Relevance score after Batch Calculation. Files over 5MB can be included in the Assessment set.</span></span>
    
## <a name="setting-up-case-issues"></a><span data-ttu-id="d08d2-136">Einrichten von Fallproblemen</span><span class="sxs-lookup"><span data-stu-id="d08d2-136">Setting up case issues</span></span>

<span data-ttu-id="d08d2-137">Die in diesem Abschnitt beschriebenen Parameter sind in Advanced eDiscovery unter **Relevanz** \> **Einrichten von Relevanz** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d08d2-137">The parameters described in this section are available in the Advanced eDiscovery **Relevance** \> **Relevance setup**.</span></span> 
  
- <span data-ttu-id="d08d2-138">Probleme müssen einem Benutzer zugewiesen werden, der die Dateien trainiert.</span><span class="sxs-lookup"><span data-stu-id="d08d2-138">Issues must be assigned to a user who will train the files.</span></span>
    
- <span data-ttu-id="d08d2-139">Importierte Dateien müssen dann der verarbeiteten Last hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d08d2-139">Imported files must then be added to the load being processed.</span></span>
    
- <span data-ttu-id="d08d2-140">Definieren und organisieren Sie Probleme sorgfältig, da sich dies auf die Ergebnisse des Relevanztrainings auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="d08d2-140">Define and organize issues carefully, as this can impact the Relevance training results.</span></span>
    
<span data-ttu-id="d08d2-141">Nachdem die Parameter festgelegt wurden, kann der Prüfer/Experte mit dem Training der Dateien auf der Registerkarte **Relevanz** beginnen.</span><span class="sxs-lookup"><span data-stu-id="d08d2-141">After parameters are set, the reviewer / expert can start training the files in the **Relevance** tab.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d08d2-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d08d2-142">See also</span></span>

[<span data-ttu-id="d08d2-143">Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="d08d2-143">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="d08d2-144">Definieren von Problemen und Zuweisen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="d08d2-144">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="d08d2-145">Einrichten von Lasten zum Hinzufügen importierter Dateien</span><span class="sxs-lookup"><span data-stu-id="d08d2-145">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)
  
[<span data-ttu-id="d08d2-146">Definieren hervorgehobener Schlüsselwörter und erweiterte Optionen</span><span class="sxs-lookup"><span data-stu-id="d08d2-146">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

