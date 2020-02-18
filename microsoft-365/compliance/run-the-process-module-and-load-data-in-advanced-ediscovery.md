---
title: Ausführen des Prozess Moduls und Laden von Daten in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'Erfahren Sie, wie Sie mit dem &amp; Office 365 Security Compliance Center auf Office 365 Advanced eDiscovery zugreifen und das Prozessmodul für einen Fall ausführen.  '
ms.openlocfilehash: 13b665c377022997ef4e60bc883993a86d8b9f75
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081522"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a><span data-ttu-id="35e61-103">Ausführen des Prozess Moduls und Laden von Daten in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="35e61-103">Run the Process module and load data in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="35e61-p101">Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="35e61-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="35e61-106">In diesem Abschnitt wird die Funktionalität des Advanced eDiscovery Process-Moduls beschrieben.</span><span class="sxs-lookup"><span data-stu-id="35e61-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="35e61-107">Zusätzlich zu Dateidaten können Metadaten wie Dateityp, Erweiterung, Ort oder Pfad, Erstellungsdatum und-Uhrzeit, Autor, Depotbank und Betreff in Advanced eDiscovery geladen und für jeden Fall gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="35e61-107">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case.</span></span> <span data-ttu-id="35e61-108">Einige Metadaten werden von Advanced eDiscovery berechnet, beispielsweise, wenn systemeigene Dateien geladen werden.</span><span class="sxs-lookup"><span data-stu-id="35e61-108">Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="35e61-109">Advanced eDiscovery stellt Systemmetadaten-Werte bereit, beispielsweise nahe doppelte Gruppierungen oder Relevanz-Bewertungen.</span><span class="sxs-lookup"><span data-stu-id="35e61-109">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores.</span></span> <span data-ttu-id="35e61-110">Andere Metadaten, wie beispielsweise Datei Anmerkungen, können vom Administrator hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="35e61-110">Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="35e61-111">Ausgeführter Prozess</span><span class="sxs-lookup"><span data-stu-id="35e61-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="35e61-112">Batch Nummern werden während des Prozesses einer Datei zugewiesen, um die Nachverfolgung von Dateien zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="35e61-112">Batch numbers are assigned to a file during Process to allow the tracking of files.</span></span> <span data-ttu-id="35e61-113">Die Batchnummer ermöglicht auch das Identifizieren von Prozess Batches für die Wiederaufbereitung von Optionen.</span><span class="sxs-lookup"><span data-stu-id="35e61-113">The batch number also enables identification of Process batches for reprocessing options.</span></span> <span data-ttu-id="35e61-114">Für die Filterung nach Batchnummer und Sitzungen stehen zusätzliche Filter zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="35e61-114">Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="35e61-115">Führen Sie die folgenden Schritte aus, um den Prozess auszuführen.</span><span class="sxs-lookup"><span data-stu-id="35e61-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="35e61-116">[Öffnen Sie das Office 365 &amp; Security Compliance Center](go-to-the-securitycompliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="35e61-116">[Open the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="35e61-117">Wechseln Sie **zu &amp; Search Investigation** \> **eDiscovery** , und klicken Sie dann auf **Gehe zu Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="35e61-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="35e61-118">Wählen Sie in Advanced eDiscovery den entsprechenden Fall auf der Seite angezeigte **Anfragen** aus, und klicken Sie auf **Gehe zu Groß-/Kleinschreibung**.</span><span class="sxs-lookup"><span data-stu-id="35e61-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="35e61-119">Wählen Sie in **Prepare** \> **Process** \> **Setup**einen Container aus der Liste der verfügbaren Container aus.</span><span class="sxs-lookup"><span data-stu-id="35e61-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![Klicken Sie auf Prozess, um dem Fall die Suchergebnisse hinzuzufügen.](../media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="35e61-121">Klicken Sie auf **Erweiterte Einstellungen...** , wenn Sie den Container als Seed-Dateien oder als Dateien mit vordefinierten Tags hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="35e61-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="35e61-122">Verwenden Sie Seed-Dateien, um das Training für Probleme mit niedrigem Umfang zu beschleunigen (normalerweise 2% oder weniger).</span><span class="sxs-lookup"><span data-stu-id="35e61-122">Use seed files to accelerate training for issues with low richness (usually 2%, or less).</span></span> <span data-ttu-id="35e61-123">Für Seed-Dateien wird empfohlen, dass Sie eine Vielzahl von eindeutig relevanten Dateien auswählen und über 20-50-Seeds pro Problem verarbeiten (zu viele seeddateien können die Relevanz der Ergebnisse verzerren).</span><span class="sxs-lookup"><span data-stu-id="35e61-123">For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results).</span></span> <span data-ttu-id="35e61-124">Seed-Dateien sollten von derselben Person überprüft werden, die das Problem trainiert.</span><span class="sxs-lookup"><span data-stu-id="35e61-124">Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="35e61-125">Verwenden Sie Pre-Tagged-Dateien, um die Relevanz-Schulung zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="35e61-125">Use pre-tagged files to automate Relevance training.</span></span> <span data-ttu-id="35e61-126">Sie sollten mindestens 1.500-Dateien markieren und den Anteil relevanter für unrelevante Dateien auf die gleiche Weise wie in der zur Relevanz hinzugefügten Sammlung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="35e61-126">You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance.</span></span> <span data-ttu-id="35e61-127">Diese Dateien sollten manuell markiert werden, und Sie sollten in der Qualität von Tagging sicher sein.</span><span class="sxs-lookup"><span data-stu-id="35e61-127">These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![Screenshot der Seite "Erweiterte Einstellungen" für die Verarbeitung von Batchdateien](../media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="35e61-129">Im Abschnitt **Seed** :</span><span class="sxs-lookup"><span data-stu-id="35e61-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="35e61-130">Wählen Sie **als Seed-Dateien markieren** aus, um den Container als seeddateien zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="35e61-130">Choose **Mark as seed files** to mark the container as seed files.</span></span> <span data-ttu-id="35e61-131">Sie müssen auch auswählen, um Sie pro Problem aus der Dropdownliste **für Probleme** zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="35e61-131">You also need choose to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="35e61-132">Wählen Sie aus der Dropdownliste **Tag** entweder **relevant** oder **nicht relevant** aus.</span><span class="sxs-lookup"><span data-stu-id="35e61-132">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="35e61-133">Nachdem Sie Dateien als **Seed**festgelegt haben, können Sie Sie nicht als **vormarkiert**markieren.</span><span class="sxs-lookup"><span data-stu-id="35e61-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="35e61-134">Im Abschnitt " **Pre-Tagged files** ":</span><span class="sxs-lookup"><span data-stu-id="35e61-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="35e61-135">Wählen Sie **als vordefinierte Dateien markieren** aus, um den Container als vormarkierte Dateien zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="35e61-135">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files.</span></span> <span data-ttu-id="35e61-136">Sie müssen Sie auch pro Problem aus der Dropdownliste " **für Problem** " zuweisen.</span><span class="sxs-lookup"><span data-stu-id="35e61-136">You also need to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="35e61-137">Wählen Sie aus der Dropdownliste **Tag** entweder **relevant** oder **nicht relevant** aus.</span><span class="sxs-lookup"><span data-stu-id="35e61-137">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="35e61-138">Nachdem Sie Dateien als **vordefinierte Tags**festgelegt haben, können Sie Sie nicht als **Seed**markieren.</span><span class="sxs-lookup"><span data-stu-id="35e61-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="35e61-139">Im Abschnitt **e-Mail-Tagging** .</span><span class="sxs-lookup"><span data-stu-id="35e61-139">In the **Email tagging** section.</span></span> <span data-ttu-id="35e61-140">Legen Sie fest, welcher Teil einer verarbeiteten e-Mail als Seed oder Pre-Tagged markiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="35e61-140">set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="35e61-141">Klicken Sie zunächst auf **verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="35e61-141">To begin, click **Process**.</span></span> <span data-ttu-id="35e61-142">Nach Abschluss werden die Prozessergebnisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="35e61-142">When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="35e61-143">Optional Wenn Sie einer bestimmten Depotbank Datenquellen zuweisen müssen, können Sie Verwalter Namen in **Verwalter** \> **Verwalten** und \> Zuweisungen **in Verwalter zuweisen hinzu** fügen und **Bearbeiten.**</span><span class="sxs-lookup"><span data-stu-id="35e61-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="35e61-144">Wenn Sie den Fall hinzufügen, können Sie den Vorgang erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="35e61-144">If you add to the case, then you can process again.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="35e61-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35e61-145">See also</span></span>

[<span data-ttu-id="35e61-146">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="35e61-146">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="35e61-147">Anzeigen der Ergebnisse des Prozess Moduls</span><span class="sxs-lookup"><span data-stu-id="35e61-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

