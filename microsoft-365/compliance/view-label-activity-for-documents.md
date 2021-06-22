---
title: Anzeigen der Bezeichnungsaktivität für Dokumente
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 5/9/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie den Bezeichnungsaktivitätsexplorer im Microsoft 365 Security & Compliance Center verwenden, um die Bezeichnungsaktivitäten zu durchsuchen und anzuzeigen.
ms.openlocfilehash: e21bb867044b2a6644b125aad9983ce3518f70ee
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053337"
---
# <a name="view-label-activity-for-documents"></a><span data-ttu-id="c508a-103">Anzeigen der Bezeichnungsaktivität für Dokumente</span><span class="sxs-lookup"><span data-stu-id="c508a-103">View label activity for documents</span></span>

<span data-ttu-id="c508a-p101">Nachdem Sie Ihre Bezeichnungen erstellt haben, sollten Sie überprüfen, ob sie auf Inhalte wie gewünscht angewendet werden. Mit dem Bezeichnungsaktivitäten-Explorer im Security &amp; Compliance Center können Sie Bezeichnungsaktivitäten für alle Inhalte in SharePoint und OneDrive for Business während der letzten 30 Tage schnell durchsuchen und anzeigen. Dies sind Echtzeitdaten, die Ihnen eine verständliche Ansicht der Vorgänge in Ihrem Mandanten bieten.</span><span class="sxs-lookup"><span data-stu-id="c508a-p101">After you create your labels, you'll want to verify that they're being applied to content as you intended. With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days. This is real-time data that gives you a clear view into what's happening in your tenant.</span></span>
  
<span data-ttu-id="c508a-107">Mit dem Bezeichnungsaktivitäten-Explorer können Sie beispielsweise folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="c508a-107">For example, with the Label Activity Explorer, you can:</span></span>
  
- <span data-ttu-id="c508a-108">Anzeigen, wie oft die einzelnen Bezeichnungen an jedem Tag (bis zu 30 Tage) angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="c508a-108">View how many times each label was applied on each day (up to 30 days).</span></span>
    
- <span data-ttu-id="c508a-109">Anzeigen, wer welche Datei genau an welchem Datum mit einer Bezeichnung versehen hat, zusammen mit einem Link zu der Website, auf der sich die Datei befindet.</span><span class="sxs-lookup"><span data-stu-id="c508a-109">See who labeled exactly which file on which date, along with a link to the site where that file resides.</span></span>
    
- <span data-ttu-id="c508a-110">Anzeigen, für welche Dateien Bezeichnungen geändert oder entfernt wurden, wie die alten und neuen Bezeichnungen lauten und wer die Änderung vorgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="c508a-110">View which files had labels changed or removed, what the old and new labels are, and who made the change.</span></span>
    
- <span data-ttu-id="c508a-p102">Filtern der Daten, um alle Bezeichnungsaktivitäten für bestimmte Bezeichnungen, Dateien oder Benutzer anzuzeigen. Sie können die Bezeichnungsaktivität auch nach Speicherort (SharePoint oder OneDrive for Business) filtern und danach, ob die Bezeichnung manuell oder automatisch angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c508a-p102">Filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
    
- <span data-ttu-id="c508a-p103">Anzeigen der Bezeichnungsaktivitäten für Ordner sowie einzelne Dokumente. In Kürze wird die Möglichkeit verfügbar sein, anzuzeigen, wie viele Dateien in diesem Ordner durch das Anwenden einer Bezeichnung auf den Ordner eine Bezeichnung erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="c508a-p103">View label activity for folders as well as individual documents. Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span></span>
    
<span data-ttu-id="c508a-115">Den Bezeichnungsaktivitäten-Explorer finden Sie im Security &amp;Compliance Center > **Informationskontrolle** > **Bezeichnungsaktivitäten-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="c508a-115">You can find the Label Activity Explorer in the Security &amp; Compliance Center > **Information governance** > **Label activity explorer**.</span></span>
  
<span data-ttu-id="c508a-116">Beachten Sie, dass für den Bezeichnungsaktivitäten-Explorer ein Office 365 Enterprise E5-Abonnement erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c508a-116">Note that the Label Activity Explorer requires an Office 365 Enterprise E5 subscription.</span></span>
  
![Bezeichnungsaktivitäten-Explorer](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a><span data-ttu-id="c508a-118">Anzeigen von Bezeichnungsaktivitäten für Dateien oder Ordner</span><span class="sxs-lookup"><span data-stu-id="c508a-118">View label activities for files or folders</span></span>

<span data-ttu-id="c508a-p104">Am oberen Rand des Bezeichnungsaktivitäten-Explorers können Sie auswählen, ob Aktivitäten für Dateien oder Ordner angezeigt werden sollen. Beachten Sie, dass Ordneraktivitäten nur den Ordner selbst betreffen, nicht die Dateien innerhalb des Ordners.</span><span class="sxs-lookup"><span data-stu-id="c508a-p104">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders. Note that folder activity includes only the folder itself, not the files inside the folder.</span></span>
  
<span data-ttu-id="c508a-p105">Sie möchten möglicherweise Bezeichnungsaktivitäten für Ordner anzeigen, da beim Anwenden einer Bezeichnung auf einen Ordner alle Dateien in diesem Ordner ebenfalls diese Bezeichnung erhalten (mit Ausnahme von Dateien, auf die bereits eine Bezeichnung explizit angewendet wurde). Daher kann das Anwenden einer Bezeichnung auf einen Ordner sich auf eine beträchtliche Anzahl von Dateien auswirken. Weitere Informationen finden Sie unter [Anwenden einer Standardaufbewahrungsbezeichnung auf den gesamten Inhalt einer SharePoint-Bibliothek, eines Ordners oder einer Dokumentenmappe](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="c508a-p105">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them). Therefore, labeling folders might affect a significant number of files. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
  
![Dropdownmenü, in dem die Bezeichnungsaktivitäten für Dateien und Ordner angezeigt werden](../media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a><span data-ttu-id="c508a-125">Bezeichnungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="c508a-125">Label activities</span></span>

 <span data-ttu-id="c508a-p106">**Bezeichnungsaktivitäten** umfassen alle Bezeichnungsaktionen: **Hinzufügen**, **Entfernen** oder **Ändern** einer Bezeichnung. Sie können diese Ansicht verwenden, um einen umfassenden Überblick darüber zu erhalten, auf wie viele Dateien die einzelnen Bezeichnungen pro Tag angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="c508a-p106">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label. You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span></span> 
  
### <a name="label-changes"></a><span data-ttu-id="c508a-128">Bezeichnungsänderungen</span><span class="sxs-lookup"><span data-stu-id="c508a-128">Label changes</span></span>

 <span data-ttu-id="c508a-p107">**Bezeichnungsänderungen** umfassen die folgenden potenziell riskanten Aktionen: **Entfernen** oder **Ändern** einer Bezeichnung. Sie können diese Ansicht verwenden, um diese riskanten Aktionen sowie den Benutzer, der sie ausgeführt hat, auf einen Blick zu sehen. In der Aktivitätsliste unterhalb des Diagramms können Sie eine Datei auswählen, und dann im Detailbereich auf der rechten Seite auf einen Link zu dieser Datei klicken.</span><span class="sxs-lookup"><span data-stu-id="c508a-p107">**Label changes** includes the potentially risky actions of **removing** or **changing** a label. You can use this view to quickly see such risky actions and the user who performed them. In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span></span> 
  
![Detailbereich für Bezeichnungsaktivität](../media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a><span data-ttu-id="c508a-133">Filtern von Bezeichnungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="c508a-133">Filter label activity</span></span>

<span data-ttu-id="c508a-p108">Sie können die Daten mühelos filtern, um alle Bezeichnungsaktivitäten für bestimmte Bezeichnungen, Dateien oder Benutzer anzuzeigen. Sie können Bezeichnungsaktivitäten auch nach Speicherort (SharePoint oder OneDrive for Business) filtern und danach, ob die Bezeichnung manuell oder automatisch angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c508a-p108">You can quickly filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
  
![Filter für Bezeichnungsaktivitäten](../media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  

