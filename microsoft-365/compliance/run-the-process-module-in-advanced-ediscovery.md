---
title: Ausführen des Prozess Moduls in Office 365 Advanced eDiscovery
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
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: 'Erfahren Sie mehr über die Richtlinien für die Vorbereitung von Fall Dateien Office 365 Daten für die Analyse mit Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 779f9ae4f93933063139b2d7d65deb2500b263e1
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597582"
---
# <a name="run-the-process-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="29cd6-103">Ausführen des Prozess Moduls in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="29cd6-103">Run the Process module in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="29cd6-104">Fall Dateien werden während des **Vorbereitungs** \> **Prozesses**in die erweiterte eDiscovery geladen.</span><span class="sxs-lookup"><span data-stu-id="29cd6-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="29cd6-p101">Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="29cd6-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="29cd6-107">Richtlinien: Vorbereiten von Daten für erweiterte eDiscovery</span><span class="sxs-lookup"><span data-stu-id="29cd6-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="29cd6-108">**Qualität**: identifizieren Sie eindeutig die für den Fall relevante Fall Datei Population.</span><span class="sxs-lookup"><span data-stu-id="29cd6-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="29cd6-109">**Lädt**: Laden Sie die Dateien an einen Speicherort, auf den Advanced eDiscovery zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="29cd6-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="29cd6-110">**Datei-ID**: ein eindeutiger Dateibezeichner in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="29cd6-110">**File ID**: A unique file identifier in Advanced eDiscovery.</span></span> <span data-ttu-id="29cd6-111">Wenn kein Dateibezeichner importiert wird, generiert Advanced eDiscovery automatisch die ID.</span><span class="sxs-lookup"><span data-stu-id="29cd6-111">If no file identifier is imported, Advanced eDiscovery automatically generates the ID.</span></span> <span data-ttu-id="29cd6-112">Wenn Sie die ID in einer nachfolgenden Prozesslast zuordnen und einen anderen Pfad zuordnen als bei der anfänglichen Prozesslast, ersetzt Advanced eDiscovery den Pfad (statt einen neuen Dateieintrag hinzuzufügen).</span><span class="sxs-lookup"><span data-stu-id="29cd6-112">If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry).</span></span> <span data-ttu-id="29cd6-113">Die ID kann als Referenz im Export Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29cd6-113">The ID can be used as a reference in the Export process.</span></span> <span data-ttu-id="29cd6-114">Der ID-Wert sollte nicht "-1" lauten.</span><span class="sxs-lookup"><span data-stu-id="29cd6-114">The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="29cd6-115">**MD5**: Diese Signatur wird verwendet, um zwischen Dateien zu unterscheiden (zwei Dateien werden nur dann als exakte Duplikate betrachtet, wenn Sie denselben MD5 haben).</span><span class="sxs-lookup"><span data-stu-id="29cd6-115">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5).</span></span> <span data-ttu-id="29cd6-116">Standardmäßig berechnet Advanced eDiscovery die MD5-Datei.</span><span class="sxs-lookup"><span data-stu-id="29cd6-116">By default, Advanced eDiscovery calculates the MD5 of files.</span></span> <span data-ttu-id="29cd6-117">Wenn es sich bei den geladenen Dateien um Textdateien handelt, wird empfohlen, den ursprünglichen MD5-Wert zu laden und zuzuordnen, anstatt ihn in Advanced eDiscovery zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="29cd6-117">When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="29cd6-118">**Dateityp und Name**:</span><span class="sxs-lookup"><span data-stu-id="29cd6-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="29cd6-119">Advanced eDiscovery kann Dateien verschiedener Formate verarbeiten und geladene systemeigene Dateien in ein Standardformat extrahieren, \*beispielsweise. TXT, HTML oder. XML.</span><span class="sxs-lookup"><span data-stu-id="29cd6-119">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML.</span></span> <span data-ttu-id="29cd6-120">Die Verarbeitung von Textdateien ist schneller als systemeigene Dateien.</span><span class="sxs-lookup"><span data-stu-id="29cd6-120">Processing of text files is faster than native files.</span></span> <span data-ttu-id="29cd6-121">Extrahierte Textdateien werden im Fallordner gespeichert.</span><span class="sxs-lookup"><span data-stu-id="29cd6-121">Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="29cd6-122">Laden Sie keine Dateien, die nicht extrahiert werden können, wie Systemdateien oder Grafik Bilder.</span><span class="sxs-lookup"><span data-stu-id="29cd6-122">Do not load files that cannot be extracted, such as system files or graphic images.</span></span> <span data-ttu-id="29cd6-123">Diese Dateien können die Verarbeitung verzögern.</span><span class="sxs-lookup"><span data-stu-id="29cd6-123">These files may delay processing.</span></span>
    
  - <span data-ttu-id="29cd6-124">Stellen Sie sicher, dass die Dateinamen signifikant benannt sind und die Pfade korrekt sind.</span><span class="sxs-lookup"><span data-stu-id="29cd6-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="29cd6-125">**Dateipfad**: Advanced eDiscovery kann Dateien mit Pfad Längen von bis zu 400 Zeichen laden.</span><span class="sxs-lookup"><span data-stu-id="29cd6-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="29cd6-126">**Textextraktion**: beim Extrahieren von Text aus systemeigenen Dateien, zusätzlich zum normalen Text, werden auch die folgenden extrahiert: verborgener Text (Excel und. doc), ausgeblendete Spalten (Excel), Nachverfolgen von Änderungen (doc), referentennotizen (PPT), eingebettete Objekte (beispielsweise Excel-Objekte in a. ppt).</span><span class="sxs-lookup"><span data-stu-id="29cd6-126">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt).</span></span> <span data-ttu-id="29cd6-127">Diese können im Text-Editor angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="29cd6-127">These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="29cd6-128">**Text ignorieren**: dieses optionale Feature wird nach dem Ausführen des Prozesses und vor der Analyse definiert.</span><span class="sxs-lookup"><span data-stu-id="29cd6-128">**Ignore Text**: This optional feature is defined after Process is run and before Analyze.</span></span> <span data-ttu-id="29cd6-129">Ignore Text sollte mit Vorsicht verwendet werden, da seine Verwendung die Leistung der Dateianalyse verringern kann.</span><span class="sxs-lookup"><span data-stu-id="29cd6-129">Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="29cd6-130">**Mehrsprachiger Text**: Advanced eDiscovery verarbeitet derzeit keine mehrsprachigen Namen für Tags, Verwalter und Probleme.</span><span class="sxs-lookup"><span data-stu-id="29cd6-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="29cd6-131">**Metadata**: bestimmen Sie, ob es Metadaten gibt, die Sie in der falldatenbank zur zukünftigen Referenz speichern möchten, beispielsweise den Datumsbereich, die Dateigröße, den Dateityp, den depotverwalter und den Betreff.</span><span class="sxs-lookup"><span data-stu-id="29cd6-131">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject.</span></span> <span data-ttu-id="29cd6-132">Metadaten können geladen werden, nachdem Dateien bereits geladen wurden, ohne dass das Inventar erneut ausgeführt oder der Aufwand für die erneute Verarbeitung hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="29cd6-132">Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="29cd6-133">Wenn die Dateien ursprünglich aus dem Pfad geladen wurden, ordnen Sie die Spalte path zu, wenn Sie später Metadaten importieren.</span><span class="sxs-lookup"><span data-stu-id="29cd6-133">If the files were originally loaded by path, map the path column when later importing metadata.</span></span> <span data-ttu-id="29cd6-134">Es ist möglich, auf die Datei anhand der ID zu referenzieren und einen anderen Pfad zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="29cd6-134">It is possible to refer to the file by ID and to map a different path.</span></span> <span data-ttu-id="29cd6-135">Dies ist ein nützliches Szenario, wenn sich die Dateipfade ändern.</span><span class="sxs-lookup"><span data-stu-id="29cd6-135">This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="29cd6-136">Wenn die Dateien ursprünglich von der Datei-ID geladen wurden, ordnen Sie die ID-Spalte beim Laden von Metadaten zu.</span><span class="sxs-lookup"><span data-stu-id="29cd6-136">If the files were originally loaded by File ID, map the ID column when loading metadata.</span></span> <span data-ttu-id="29cd6-137">Wenn Sie auf die Datei durch path (anstelle von ID) verweisen, wird das erneute Laden von Dateien mit einer anderen ID bewirkt.</span><span class="sxs-lookup"><span data-stu-id="29cd6-137">Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID.</span></span> <span data-ttu-id="29cd6-138">Mit Advanced eDiscovery werden Kopien der Dateien erstellt, anstatt Metadaten der vorhandenen Dateien zu laden.</span><span class="sxs-lookup"><span data-stu-id="29cd6-138">Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="29cd6-139">**Familien**: Es ist nicht möglich, eine Familie ohne das übergeordnete Element (Familienoberhaupt) zu laden.</span><span class="sxs-lookup"><span data-stu-id="29cd6-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="29cd6-140">**Dateigröße**: Es gibt keine Beschränkung der Größe von Dateien, die auf Advanced eDiscovery geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="29cd6-140">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery.</span></span> <span data-ttu-id="29cd6-141">Für die Analyse (Analyse, Relevanz usw.) beträgt der Grenzwert 5.242.880 Zeichen extrahierten Texts.</span><span class="sxs-lookup"><span data-stu-id="29cd6-141">For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text.</span></span> <span data-ttu-id="29cd6-142">Größere Dateien werden ignoriert (beispielsweise relevant: Dateien nehmen nicht am Relevanz-Schulungsprozess Teil und erhalten nach der Stapel Berechnung kein Relevanz-Ergebnis).</span><span class="sxs-lookup"><span data-stu-id="29cd6-142">Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="29cd6-143">**Datei Menge**: Es gibt keine empfohlene Grenze für die Anzahl der Dateien, die in einem einzigen Fall behandelt werden können.</span><span class="sxs-lookup"><span data-stu-id="29cd6-143">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case.</span></span> <span data-ttu-id="29cd6-144">Die Leistung hängt von den Ressourcen Ihres Systems ab.</span><span class="sxs-lookup"><span data-stu-id="29cd6-144">Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="29cd6-145">Filtern von Dateien</span><span class="sxs-lookup"><span data-stu-id="29cd6-145">Filtering files</span></span>

<span data-ttu-id="29cd6-146">Eine benutzerdefinierte Bezeichnung kann mit einer Reihe von Dateien verknüpft werden, um Sie von Prozessen oder anderen Aufgaben auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="29cd6-146">A user-defined label can be associated with a set of files to exclude them from Process or other tasks.</span></span> <span data-ttu-id="29cd6-147">Jeder Prozess Sitzung ist eine Batch-ID zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="29cd6-147">Each Process session is associated with a batch ID.</span></span> <span data-ttu-id="29cd6-148">Obwohl die Batch-ID für den Experten in Relevanz nicht sichtbar ist, kann dies mithilfe eines Such Dienstprogramms erfolgen, indem ein Filter für den aktuellen Batch hinzugefügt und alle entsprechenden Dateien mit einer benutzerdefinierten Bezeichnung versehen werden.</span><span class="sxs-lookup"><span data-stu-id="29cd6-148">Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="29cd6-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29cd6-149">See also</span></span>

[<span data-ttu-id="29cd6-150">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="29cd6-150">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="29cd6-151">Ausführung des Prozess Moduls und Laden von Daten</span><span class="sxs-lookup"><span data-stu-id="29cd6-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="29cd6-152">Anzeigen der Ergebnisse des Prozess Moduls</span><span class="sxs-lookup"><span data-stu-id="29cd6-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

