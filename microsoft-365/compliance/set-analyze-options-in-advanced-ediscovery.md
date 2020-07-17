---
title: Festlegen von Analyseoptionen in Advanced eDiscovery
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: Lesen Sie die Schritte zum Einrichten von Optionen für den Analyseprozess in Advanced eDiscovery, einschließlich nahe gestellter Duplikate, e-Mail-Threads und Designs.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d622e06cdfe9a46f470be46d1a5b9df98347cc0a
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936882"
---
# <a name="set-analyze-options-in-advanced-ediscovery-classic"></a><span data-ttu-id="22827-103">Festlegen von Analyseoptionen in Advanced eDiscovery (klassisch)</span><span class="sxs-lookup"><span data-stu-id="22827-103">Set Analyze options in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="22827-p101">Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="22827-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="22827-106">Legen Sie in Advanced eDiscovery die Analyseoptionen vor der Ausführung von ANALYZE fest.</span><span class="sxs-lookup"><span data-stu-id="22827-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="22827-107">Festlegen von Analyseoptionen</span><span class="sxs-lookup"><span data-stu-id="22827-107">Set Analyze options</span></span>

<span data-ttu-id="22827-108">Öffnen Sie **Prepare \> analyze** \> **Setup**.</span><span class="sxs-lookup"><span data-stu-id="22827-108">Open **Prepare \> Analyze** \> **Setup**.</span></span> <span data-ttu-id="22827-109">Das folgende Fenster wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22827-109">The following window is displayed.</span></span>
  
![Festlegen von Analyseoptionen](../media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="22827-111">**Nahe Duplikate und e-Mail-Threads** Aktivieren Sie dieses Kontrollkästchen, wenn Sie die Analyse ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="22827-111">**Near-duplicates and email threads** Check this box if you want to run the analysis.</span></span> <span data-ttu-id="22827-112">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="22827-112">It is selected by default.</span></span> 
  
 <span data-ttu-id="22827-113">**Dokument Ähnlichkeit** Geben Sie den Schwellenwert für nahe Dubletten ein, oder übernehmen Sie den Standardwert von 65%.</span><span class="sxs-lookup"><span data-stu-id="22827-113">**Document similarity** Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="22827-114">**Designs** Aktivieren Sie dieses Kontrollkästchen, um alle Dateien zu verarbeiten und Ihnen Designs zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="22827-114">**Themes**Check this box to process all files and assign themes to them.</span></span> <span data-ttu-id="22827-115">Dieses Kontrollkästchen ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="22827-115">By default, this check box is not selected.</span></span> <span data-ttu-id="22827-116">Geben Sie die folgenden Optionen ein, wenn Sie die Design Verarbeitung durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="22827-116">Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="22827-117">**Maximale Anzahl von Designs** Geben Sie einen Wert für die Anzahl der zu erstellende Designs ein, oder wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="22827-117">**Max number of themes**Enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="22827-118">Der Standardwert ist 200.</span><span class="sxs-lookup"><span data-stu-id="22827-118">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="22827-119">Die Erhöhung der Anzahl von Designs wirkt sich sowohl auf die Leistung als auch auf die Möglichkeit eines Designs für die Verallgemeinerung aus.</span><span class="sxs-lookup"><span data-stu-id="22827-119">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="22827-120">Je höher die Anzahl der Designs ist, desto präziser sind Sie.</span><span class="sxs-lookup"><span data-stu-id="22827-120">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="22827-121">Wenn beispielsweise eine Gruppe von 50 Designs ein Design wie "Basketball, Sporen, Clippers, Lakers" enthält; 300 Designs können separate Designs enthalten: "spores", "Clippers", "Lakers".</span><span class="sxs-lookup"><span data-stu-id="22827-121">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="22827-122">Wenn Sie kein Bewusstsein für das Thema "Basketball" und verwenden Sie diese Funktion für ECA, sehen das Thema "Basketball" könnte nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="22827-122">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="22827-123">Wenn die Verarbeitung jedoch zu viele Designs hatte, werden Sie möglicherweise nie das Wort "Basketball" sehen und wissen möglicherweise nicht, dass Spurs und Clippers gute Basketball Themen sind, anstatt Elemente, die auf Stiefeln laufen und für Haare verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="22827-123">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="22827-124">**Vorgeschlagene Designs** Sie können Design Wörter vorschlagen, um die Verarbeitung von Designs zu steuern.</span><span class="sxs-lookup"><span data-stu-id="22827-124">**Suggested themes** You can suggest theme words to control Themes processing.</span></span> <span data-ttu-id="22827-125">Advanced eDiscovery konzentriert sich auf diese vorgeschlagenen Wörter und versucht, ein oder mehrere relevante Designs basierend auf den Einstellungen für "maximale Anzahl von Designs" zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="22827-125">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="22827-126">Wenn beispielsweise das vorgeschlagene Wort "Computer" lautet und Sie "2" als "maximale Anzahl von Designs" angegeben haben, versucht Advanced eDiscovery, zwei Designs zu generieren, die sich auf das Wort "Computer" beziehen.</span><span class="sxs-lookup"><span data-stu-id="22827-126">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="22827-127">Die beiden Themen können beispielsweise "Computer Software" und "Computer Hardware" lauten.</span><span class="sxs-lookup"><span data-stu-id="22827-127">The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![Hinzufügen eines vorgeschlagenen Designs](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="22827-129">Wenn Sie vorgeschlagene Designs anzeigen, hinzufügen oder bearbeiten möchten, klicken Sie auf **ändern**.</span><span class="sxs-lookup"><span data-stu-id="22827-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="22827-130">Klicken Sie im Bereich **vorgeschlagene Designs** **auf das** Symbol Add Icon hinzufügen, ![ ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) um ein Design hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="22827-130">In the **Suggested themes** panel, click the **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme.</span></span> <span data-ttu-id="22827-131">Fügen Sie im Bereich **vorgeschlagenes Design hinzufügen** die Wörter hinzu, getrennt durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="22827-131">In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="22827-132">Wählen Sie unter **Anzahl der Designs**einen Wert aus, um die Anzahl der Designs zu ermitteln, die Advanced eDiscovery für diese Wörter zu generieren versucht (Standard ist 1 Design).</span><span class="sxs-lookup"><span data-stu-id="22827-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="22827-133">Klicken Sie auf **Speichern** , und schließen Sie dann den Dialog.</span><span class="sxs-lookup"><span data-stu-id="22827-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="22827-134">Die Gesamtzahl der Designs umfasst vorgeschlagene Designs.</span><span class="sxs-lookup"><span data-stu-id="22827-134">The total number of themes includes Suggested Themes.</span></span> <span data-ttu-id="22827-135">Die insgesamt vorgeschlagenen Designs dürfen die Gesamtdesigns nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="22827-135">The total Suggested Themes cannot exceed the total themes.</span></span> <span data-ttu-id="22827-136">Wenn es viele vorgeschlagene Themen im Verhältnis zu den Gesamtdesigns gibt, werden nur einige "neuartige" Designs vom System erkannt, da die meisten Designs für vorgeschlagene Designs bestimmt sind.</span><span class="sxs-lookup"><span data-stu-id="22827-136">If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="22827-137">**Modus "** Wählen Sie in der Dropdownliste die Option **Designs** aus:</span><span class="sxs-lookup"><span data-stu-id="22827-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="22827-138">**Modell erstellen und anwenden**: berechnet Designs anhand von Modellen aus einem Segment der Dateien und verteilt dann Dateien unter diesen.</span><span class="sxs-lookup"><span data-stu-id="22827-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="22827-139">**Modell erstellen**: berechnet ein Design Modell aus einem Segment der Dateien.</span><span class="sxs-lookup"><span data-stu-id="22827-139">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="22827-140">Das Anwenden von Dateien wird separat zu einem anderen Zeitpunkt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="22827-140">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="22827-141">**Modell anwenden**: diese Option wird nur angezeigt, wenn ein Modell zuvor erstellt wurde und noch nicht angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="22827-141">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="22827-142">Dadurch werden die Dateien basierend auf den Designs aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="22827-142">This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="22827-143">Sie können auch [Text ignorieren festlegen](set-ignore-text-in-advanced-ediscovery.md) und [Erweiterte Einstellungen](set-analyze-advanced-settings-in-advanced-ediscovery.md) für ANALYZE festlegen.</span><span class="sxs-lookup"><span data-stu-id="22827-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="22827-144">Nachdem Sie diese Optionen festgelegt haben, klicken Sie auf **Analyse** ausführen.</span><span class="sxs-lookup"><span data-stu-id="22827-144">After you've set these options, click **Analyze** to run.</span></span> <span data-ttu-id="22827-145">[Anzeigen von Analyseergebnissen](view-analyze-results-in-advanced-ediscovery.md) werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22827-145">[View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="22827-146">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="22827-146">Related topics</span></span>

[<span data-ttu-id="22827-147">Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="22827-147">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="22827-148">Grundlegendes zur Dokument Ähnlichkeit</span><span class="sxs-lookup"><span data-stu-id="22827-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="22827-149">Text ignorieren festlegen</span><span class="sxs-lookup"><span data-stu-id="22827-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="22827-150">Erweiterte Einstellungen für ANALYZE festlegen</span><span class="sxs-lookup"><span data-stu-id="22827-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="22827-151">Anzeigen von Analyseergebnissen</span><span class="sxs-lookup"><span data-stu-id="22827-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

