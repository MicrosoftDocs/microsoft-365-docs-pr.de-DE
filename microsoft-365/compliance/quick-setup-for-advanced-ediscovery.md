---
title: Schnelleinrichtung für Office 365 Advanced eDiscovery
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
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: 'Informationen zum Zugriff auf Office 365 Advanced eDiscovery im Office 365 Security &amp; Compliance Center und Erläuterung des üblichen Workflows für die Verwendung von Advanced eDiscovery.  '
ms.openlocfilehash: 6df2d68639f2be9f6ba38ea7211654058bc73035
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597672"
---
# <a name="quick-setup-for-office-365-advanced-ediscovery"></a><span data-ttu-id="91068-103">Schnelleinrichtung für Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="91068-103">Quick setup for Office 365 Advanced eDiscovery</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91068-104">Da wir weiterhin in neuere Versionen von Advanced eDiscovery investieren, kündigen wir die Deaktivierung von Office 365 Advanced eDiscovery (auch bekannt als *Advanced eDiscovery v1.0*).</span><span class="sxs-lookup"><span data-stu-id="91068-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Office 365 Advanced eDiscovery (also known as *Advanced eDiscovery v1.0*).</span></span> <span data-ttu-id="91068-105">Wenn Sie noch mit Advanced eDiscovery v1.0 arbeiten, wechseln Sie so bald wie möglich zu [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (auch bekannt als *Advanced eDiscovery-Lösung in Microsoft 365*).</span><span class="sxs-lookup"><span data-stu-id="91068-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="91068-106">Advanced eDiscovery 2.0 enthält ähnliche Funktionen wie Advanced eDiscovery v1.0, bietet aber auch viele neue Funktionen wie z. B. Verwahrerverwaltung, Kommunikationsverwaltung und Prüfungssätze.</span><span class="sxs-lookup"><span data-stu-id="91068-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="91068-107">Um mehr über die Deaktivierung von Advanced eDiscovery v1.0 zu erfahren, siehe [Deaktivierung von veralteten eDiscovery-Tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). </span><span class="sxs-lookup"><span data-stu-id="91068-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 

<span data-ttu-id="91068-108">In diesem Setup-Abschnitt werden einem Microsoft 365 Security &amp; Compliance Center eDiscovery-Manager die ersten Schritte mit Advanced eDiscovery gezeigt.</span><span class="sxs-lookup"><span data-stu-id="91068-108">This setup section shows an Microsoft 365 Security &amp; Compliance Center eDiscovery manager how to get started with Advanced eDiscovery.</span></span> <span data-ttu-id="91068-109">Es wird davon ausgegangen, dass in beiden Bereichen Grundkenntnisse vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="91068-109">A working knowledge of both is assumed.</span></span>
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a><span data-ttu-id="91068-110">Aufrufen eines Falls in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="91068-110">Accessing a case in Advanced eDiscovery</span></span>


<span data-ttu-id="91068-p103">Sie rufen Advanced eDiscovery über das Security &amp; Compliance Center auf. Sie müssen ein Mitglied eines eDiscovery-Falls im Security &amp; Compliance Center sein, um den Fall in Advanced eDiscovery aufzurufen. Anweisungen zum Zuweisen von eDiscovery-Fallrechten und Hinzufügen von Benutzern zu einem eDiscovery-Fall finden Sie unter [Verwalten von eDiscovery-Fällen in Office 365](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="91068-p103">You access Advanced eDiscovery from the Security &amp; Compliance Center. You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery. For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span></span> 
  
<span data-ttu-id="91068-114">So navigieren Sie zu einem Fall in Advanced eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="91068-114">To go to a case in Advanced eDiscovery:</span></span> 
  
1. <span data-ttu-id="91068-115">[Wechseln Sie zum Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="91068-115">[Go to the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="91068-116">Klicken Sie im Security &amp; Compliance Center auf **Suche &amp; Untersuchung** \> **eDiscovery**, um die Liste der Fälle in Ihrem Unternehmen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="91068-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
3. <span data-ttu-id="91068-117">Klicken Sie auf der Seite **eDiscovery** auf **Öffnen** neben dem Fall, zu dem Sie in Advanced eDiscovery wechseln möchten.</span><span class="sxs-lookup"><span data-stu-id="91068-117">On the **eDiscovery** page, click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span> 
    
4. <span data-ttu-id="91068-118">Klicken Sie auf der Seite **Start** für den Fall auf **Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="91068-118">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span>
    
    <span data-ttu-id="91068-p104">Die Statusanzeige für die Verbindung zu Advanced eDiscovery wird angezeigt\*\*\*\*. Wenn Sie verbunden sind, wird der Fall in Advanced eDiscovery geöffnet.</span><span class="sxs-lookup"><span data-stu-id="91068-p104">The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected, the case is opened in Advanced eDiscovery.</span></span> 
    
## <a name="workflow"></a><span data-ttu-id="91068-121">Workflow</span><span class="sxs-lookup"><span data-stu-id="91068-121">Workflow</span></span>

<span data-ttu-id="91068-122">Das folgende Diagramm zeigt den allgemeinen Workflow für die Verwaltung und Verwendung von eDiscovery-Fällen im Security &amp; Compliance Center und in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="91068-122">The following diagram illustrates the common workflow for managing and using eDiscovery cases in the Security &amp; Compliance Center and Advanced eDiscovery.</span></span> 
  
![Diagramm zeigt den Workflow „Erweiterte eDiscovery in Office 365“, der aus den vier Phasen des Einrichtens, einschließlich Benutzern und Fällen, des Identifizierens der Falldaten, des Exportierens und des Verarbeitens und dann aus den Phasen der Analyse und des Exports auf den lokalen Computer besteht.](media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
<span data-ttu-id="91068-p105">Dieser Setup-Abschnitt beschreibt die ersten vier Schritte im Workflow. Eine Beschreibung der anderen Schritte im Workflow finden Sie im Folgenden.</span><span class="sxs-lookup"><span data-stu-id="91068-p105">This setup section describes the first four steps in the workflow. For a description of the other steps in the workflow, see the following.</span></span>
  
## <a name="analyze"></a><span data-ttu-id="91068-126">Analysieren</span><span class="sxs-lookup"><span data-stu-id="91068-126">Analyze</span></span>

<span data-ttu-id="91068-p106">[Analysieren von Falldaten](analyze-case-data-with-advanced-ediscovery.md) Identifiziert und ordnet die Dateien nach verschiedenen Parametern, ermöglicht die Verwendung von Designs und zeigt die Ergebnisse an. Die Analysefunktion kann vom Benutzer angepasst werden, um verbesserte Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="91068-p106">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results. Analyze functionality can be customized by the user in order to achieve enhanced results.</span></span> 
  
## <a name="relevance-setup-and-relevance"></a><span data-ttu-id="91068-129">Relevanzeinrichtung und Relevanz</span><span class="sxs-lookup"><span data-stu-id="91068-129">Relevance Setup and Relevance</span></span>

<span data-ttu-id="91068-p107">[Relevanzeinrichtung](manage-relevance-setup-in-advanced-ediscovery.md) und [Verwenden des Relevanzmoduls](use-relevance-in-advanced-ediscovery.md) Ermöglicht die Bewertung und Relevanztraining basierend auf einer Stichprobe von Dateien und verwendet diese, um Entscheidungen auf den Predictive Coding-Prozess anzuwenden. Berechnet und zeigt Zwischenergebnisse während der Überwachung der statistischen Gültigkeit des Prozesses an. Zeigt die Ergebnisse zur Erleichterung von Prüfentscheidungen an.</span><span class="sxs-lookup"><span data-stu-id="91068-p107">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process. Calculates and displays interim results while monitoring statistical validity of the process. Displays the results to facilitate in making review decisions.</span></span> 
  
## <a name="export"></a><span data-ttu-id="91068-133">Exportieren</span><span class="sxs-lookup"><span data-stu-id="91068-133">Export</span></span>

<span data-ttu-id="91068-134">[Exportieren von Falldaten](export-case-data-in-advanced-ediscovery.md) Ermöglicht das Exportieren von Advanced eDiscovery-Inhalten und -Ergebnissen zur externen Prüfung.</span><span class="sxs-lookup"><span data-stu-id="91068-134">[Exporting case data](export-case-data-in-advanced-ediscovery.md) Enables the exporting of Advanced eDiscovery content and results for external review.</span></span> 
  
## <a name="report"></a><span data-ttu-id="91068-135">Bericht</span><span class="sxs-lookup"><span data-stu-id="91068-135">Report</span></span>

<span data-ttu-id="91068-136">[Ausführen von Berichten](run-reports-in-advanced-ediscovery.md) Ermöglicht die Erstellung ausgewählter Berichte zur Advanced eDiscovery-Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="91068-136">[Running reports](run-reports-in-advanced-ediscovery.md) Enables the generation of selected reports related to Advanced eDiscovery processing.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="91068-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91068-137">See also</span></span>

[<span data-ttu-id="91068-138">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="91068-138">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="91068-139">Einrichten von Benutzern und Fällen</span><span class="sxs-lookup"><span data-stu-id="91068-139">Setting up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="91068-140">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="91068-140">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)

