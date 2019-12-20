---
title: Verwenden von Office 365 erweiterten eDiscovery-Dienstprogrammen
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Erfahren Sie mehr über die Dienstprogramme in Office 365 Advanced eDiscovery, einschließlich Fallprotokoll, klare Daten, Prozessfehler, Änderung der Relevanz und Transparenz Analyse.  '
ms.openlocfilehash: fd7ed1afe4b9204665e58b393c79bbb47b7598e3
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802330"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a><span data-ttu-id="26fbc-103">Verwenden von Office 365 erweiterten eDiscovery-Dienstprogrammen</span><span class="sxs-lookup"><span data-stu-id="26fbc-103">Use Office 365 Advanced eDiscovery utilities</span></span>

> [!NOTE]
> <span data-ttu-id="26fbc-p101">Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="26fbc-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="26fbc-106">Die Dienstprogramme, die in Advanced eDiscovery angezeigt und verfügbar sind, hängen von Kontext und Benutzerrollen ab.</span><span class="sxs-lookup"><span data-stu-id="26fbc-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="26fbc-107">Fallprotokoll</span><span class="sxs-lookup"><span data-stu-id="26fbc-107">Case log</span></span>

<span data-ttu-id="26fbc-108">Das Fallprotokoll enthält eine ausführliche Liste der Anwendungs Verarbeitungsaktivitäten, die für die Nachverfolgung, Problembehandlung und für die Behandlung von Fehlern und Warnungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="26fbc-108">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings.</span></span> <span data-ttu-id="26fbc-109">Das Protokoll kann auf dem Host oder Server lokal erstellt und gespeichert oder direkt an eine e-Mail-Adresse gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="26fbc-109">The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="26fbc-110">Die Protokolldatei kann auch auf den Clientcomputer heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="26fbc-110">The log file can also be downloaded to the client's computer.</span></span> <span data-ttu-id="26fbc-111">Die Client Download Option ist je nach Konfiguration und Benutzerrolle möglicherweise aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="26fbc-111">The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="26fbc-112">Klicken Sie in der Menüleiste auf das **Zahnrad** Symbol.</span><span class="sxs-lookup"><span data-stu-id="26fbc-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="26fbc-113">Wählen Sie auf der Registerkarte **Einstellungen und Dienstprogramme \> \*\* die Option \*\* \> Case Log Setup**aus.</span><span class="sxs-lookup"><span data-stu-id="26fbc-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="26fbc-114">Wählen Sie die **Protokollebene** wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="26fbc-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="26fbc-115">**Standard**: enthält die grundlegenden Protokolldaten.</span><span class="sxs-lookup"><span data-stu-id="26fbc-115">**Standard**: Includes the basic log data.</span></span> <span data-ttu-id="26fbc-116">Diese Option ist normalerweise für die Überwachung erforderlich und sollte verwendet werden, sofern nichts anderes empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="26fbc-116">This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="26fbc-117">**Minimal**: wird für sehr große Fälle verwendet und gibt nur die neuesten Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="26fbc-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="26fbc-118">Klicken Sie auf **Ausführungs Fallprotokoll**.</span><span class="sxs-lookup"><span data-stu-id="26fbc-118">Click **Run Case log**.</span></span> <span data-ttu-id="26fbc-119">Das Protokoll wird generiert, und path wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="26fbc-119">The log is generated and path is displayed.</span></span> <span data-ttu-id="26fbc-120">Die Informationen zum Vorgangsfortschritt für den aktuellen und letzten Vorgang werden im Aufgabenstatus Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="26fbc-120">The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="26fbc-121">Löschen von Daten</span><span class="sxs-lookup"><span data-stu-id="26fbc-121">Clear data</span></span>

<span data-ttu-id="26fbc-122">Wenn das Löschen oder erneute Initialisieren von Falldaten erforderlich ist, muss die Datenbankinstanz initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="26fbc-122">If it is necessary to delete or reinitialize case data, the database instance must be initialized.</span></span> <span data-ttu-id="26fbc-123">Mit dem Dienstprogramm "Daten löschen" werden alle angegebenen Einträge aus der falldatenbank, den Textdateien, dem Fallordner und den akkumulierten Ergebnissen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="26fbc-123">The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results.</span></span> <span data-ttu-id="26fbc-124">Die Funktion kann nur von einem Administrator ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="26fbc-124">The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="26fbc-125">Diese Aktion ist nicht umkehrbar und löscht alle vom Experten durchgeführten Relevanz-Tagging und-Analysen.</span><span class="sxs-lookup"><span data-stu-id="26fbc-125">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert.</span></span> <span data-ttu-id="26fbc-126">Speichern Sie bei Bedarf eine Sicherung der Daten.</span><span class="sxs-lookup"><span data-stu-id="26fbc-126">Save a backup of data, if necessary.</span></span> <span data-ttu-id="26fbc-127">Verwenden Sie diese Option mit größter Sorgfalt.</span><span class="sxs-lookup"><span data-stu-id="26fbc-127">Use this option with extreme care.</span></span> <span data-ttu-id="26fbc-128">Das Löschen von gekennzeichneten und bewerteten Dateien kann sich auf die Relevanz der Ergebnisse auswirken.</span><span class="sxs-lookup"><span data-stu-id="26fbc-128">Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="26fbc-129">Klicken Sie in der Menüleiste auf das **Zahnrad** Symbol.</span><span class="sxs-lookup"><span data-stu-id="26fbc-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="26fbc-130">Wählen Sie auf der Registerkarte **Einstellungen und Dienstprogramme \> \*\* die Option \*\* \> Daten Einrichtung löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="26fbc-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="26fbc-131">Wählen Sie eine Option aus, damit die Informationen initialisiert werden:</span><span class="sxs-lookup"><span data-stu-id="26fbc-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="26fbc-132">**Relevanz**: Löscht alle relevanten arbeiten, einschließlich der Definition von Lasten und der Zuordnung von zu Lasten gemachten Dateien.</span><span class="sxs-lookup"><span data-stu-id="26fbc-132">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads.</span></span> <span data-ttu-id="26fbc-133">Alle Beispiele und Markierungen werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="26fbc-133">It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="26fbc-134">**Nahe Duplikate und e-Mail-Threads**: Löscht alle Analyseinformationen von nahe Duplikaten und e-Mail-Threads.</span><span class="sxs-lookup"><span data-stu-id="26fbc-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="26fbc-135">**Designs**: löscht Designs-bezogene Daten.</span><span class="sxs-lookup"><span data-stu-id="26fbc-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="26fbc-136">**Export Historie**: Löscht Verlaufsinformationen von Export Batches.</span><span class="sxs-lookup"><span data-stu-id="26fbc-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="26fbc-137">Klicken Sie auf **Daten löschen**.</span><span class="sxs-lookup"><span data-stu-id="26fbc-137">Click **Clear data**.</span></span> <span data-ttu-id="26fbc-138">Die Case-Daten werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="26fbc-138">The case data is cleared.</span></span> <span data-ttu-id="26fbc-139">Die Informationen zum Vorgangsfortschritt für den aktuellen und letzten Vorgang werden im **Aufgabenstatus** Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="26fbc-139">The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="26fbc-140">Relevanz ändern</span><span class="sxs-lookup"><span data-stu-id="26fbc-140">Modify Relevance</span></span>

<span data-ttu-id="26fbc-141">In diesem Abschnitt wird beschrieben, wie ein Relevanz-Beispiel übersprungen oder zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="26fbc-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="26fbc-142">Klicken Sie in der Menüleiste auf das **Zahnrad** Symbol.</span><span class="sxs-lookup"><span data-stu-id="26fbc-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="26fbc-143">Wählen Sie auf der Registerkarte \*\*Einstellungen und Dienstprogramme \> \*\* die Option **Relevanz ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="26fbc-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="26fbc-144">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="26fbc-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="26fbc-145">**Aktuelles Beispiel überspringen-für aktuellen Benutzer**: Dadurch werden alle nicht markierten Dateien im Open Case-Beispiel des Benutzers, der das Dienstprogramm ausführt, als **Skip**markiert.</span><span class="sxs-lookup"><span data-stu-id="26fbc-145">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility.</span></span> <span data-ttu-id="26fbc-146">Für Dateien, die als **Skip**markiert sind, wird die Relevanz-Verarbeitung nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="26fbc-146">Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="26fbc-147">**Aktuelles Beispiel überspringen – alle geöffneten Beispiele**: Dadurch werden alle nicht markierten Dateien in allen geöffneten Beispielen für alle Benutzer als **Skip**markiert.</span><span class="sxs-lookup"><span data-stu-id="26fbc-147">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users.</span></span> <span data-ttu-id="26fbc-148">Diese Option wird nicht empfohlen, wenn Benutzer derzeit Beispiele kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="26fbc-148">This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="26fbc-149">**Rollback für das letzte Beispiel**: das letzte abgeschlossene Schulungs Beispiel für Relevanz wird rückgängig gemacht, unabhängig davon, ob es vor oder nach dem Prozess "Calculate" liegt.</span><span class="sxs-lookup"><span data-stu-id="26fbc-149">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process.</span></span> <span data-ttu-id="26fbc-150">Rollback eines catch-up-Beispiels ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="26fbc-150">Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="26fbc-151">Klicken **Sie auf Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="26fbc-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="26fbc-152">Transparenz Analyse</span><span class="sxs-lookup"><span data-stu-id="26fbc-152">Transparency analysis</span></span>

<span data-ttu-id="26fbc-153">Das Dienstprogramm zur Transparenz Analyse ermöglicht eine detaillierte Ansicht der Dateien und ihres zugewiesenen Relevanz-Ergebnisses.</span><span class="sxs-lookup"><span data-stu-id="26fbc-153">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score.</span></span> <span data-ttu-id="26fbc-154">Der Bericht kann als Plausibilitätsüberprüfung verwendet werden oder um die Relevanz einer Datei zu vergleichen, die von einem menschlichen Prüfer im Vergleich zur von Advanced eDiscovery zugewiesenen Relevanz definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="26fbc-154">The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="26fbc-155">Zusätzlich zu den Relevanz-Werten berechnet und weist Advanced eDiscovery Stich Wort Gewichte zu, die den Keyword-Kontext Beachtung finden.</span><span class="sxs-lookup"><span data-stu-id="26fbc-155">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context.</span></span> <span data-ttu-id="26fbc-156">Das gleiche Wort in einer Datei kann je nach Kontext und Ort unterschiedliche Gewichtungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="26fbc-156">The same word in a file can be assigned different weights, depending on context and location.</span></span> <span data-ttu-id="26fbc-157">Jedes Keyword wird mit einer zunehmenden Skala von Farbintensitäten markiert, die von gelb bis dunkel Orange und unterschiedliche Grauschattierungen reichen.</span><span class="sxs-lookup"><span data-stu-id="26fbc-157">Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray.</span></span> <span data-ttu-id="26fbc-158">Die Farbcodierung wird verwendet, um den relativen positiven oder negativen Beitrag des Wortes zur Relevanz-Bewertung visuell anzugeben.</span><span class="sxs-lookup"><span data-stu-id="26fbc-158">Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="26fbc-159">In einem Szenario mit mehreren Problemfällen kann für jedes Problem ein Bericht über die Transparenz Analyse generiert werden.</span><span class="sxs-lookup"><span data-stu-id="26fbc-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="26fbc-160">Klicken Sie in der Menüleiste auf das **Zahnrad** Symbol.</span><span class="sxs-lookup"><span data-stu-id="26fbc-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="26fbc-161">Wählen Sie auf der Registerkarte **Einstellungen und Dienstprogramme \> \*\* die Option \*\* \> Transparenz Analyse einrichten**aus.</span><span class="sxs-lookup"><span data-stu-id="26fbc-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="26fbc-162">Geben Sie in \* \* Datei-ID \* \* die Datei-ID der zu verarbeitenden Datei ein.</span><span class="sxs-lookup"><span data-stu-id="26fbc-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="26fbc-163">Wählen Sie in der Liste **Problem** das relevante Problem aus.</span><span class="sxs-lookup"><span data-stu-id="26fbc-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="26fbc-164">Klicken Sie auf **Transparenz Analyse**.</span><span class="sxs-lookup"><span data-stu-id="26fbc-164">Click **Transparency analysis**.</span></span> <span data-ttu-id="26fbc-165">Nach Abschluss des Berichts wird der Bericht über die Transparenz der Datei angezeigt, der zeigt, wie die markierten Schlüsselwortfarben mit dem Gesamtergebnis der Relevanz korrelieren.</span><span class="sxs-lookup"><span data-stu-id="26fbc-165">Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="26fbc-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26fbc-166">See also</span></span>

[<span data-ttu-id="26fbc-167">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="26fbc-167">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="26fbc-168">Definieren von Fall-und Mandanten Einstellungen</span><span class="sxs-lookup"><span data-stu-id="26fbc-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

