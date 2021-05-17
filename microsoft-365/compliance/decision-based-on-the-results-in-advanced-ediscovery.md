---
title: Entscheidung basierend auf den Ergebnissen in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Erfahren Sie, wie die Registerkarte "Entscheiden" in Advanced eDiscovery Daten enthält, mit deren Hilfe Sie die richtige Größe der Falldateien für die Überprüfung ermitteln können.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769150"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a>Entscheidungen basierend auf Relevanzergebnissen in Advanced eDiscovery
  
Im Relevanzmodul in Advanced eDiscovery enthält die Registerkarte Entscheiden zusätzliche Informationen zum Anzeigen und Verwenden von Entscheidungsunterstützungsstatistiken zum Bestimmen der Größe des Überprüfungssatz von Falldateien.
  
## <a name="using-the-decide-tab"></a>Verwenden der Registerkarte Entscheiden

![Relevanz entscheiden](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Diese Registerkarte enthält die folgenden Komponenten:
  
- **Problem**: Hier können Sie das problem von Interesse aus der Liste auswählen.

- **Review-Recall-Verhältnis:** Vergleiche der Erweiterten eDiscovery-Überprüfung gemäß Relevanzbewertung. Der Cutoff-Punkt im Diagramm stellt den Prozentsatz der zu überprüfende Dateien dar, die einer Relevanzbewertung zugeordnet sind. Dies wird in der Relevanztestphase und als Exportschwellenwert für das Culling verwendet. Der Standardschnittpunkt für die Anzahl der zu überprüfenden Dateien ist an dem Punkt, an dem das Gleichgewicht zwischen Rückruf und Genauigkeit optimal ist. Der tatsächliche Stichpunkt sollte vom Benutzer abhängig von den Zielen und dem Kostenabschneiden (%review) und dem Risiko (%recall) bestimmt werden. Mit dem Schieberegler können Sie den Stichpunkt anpassen und die Auswirkungen auf das Diagramm und die Parameter anzeigen, wenn Sie den Prozentteil der abzurufenden relevanten Dateien anpassen und bevor Sie eine Entscheidung überprüfen.

- **Parameter**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics relation to the review set in relation to the collection for the entire case. Die Definitionen für diese Parameter sind wie folgt:

  - **Review**: Prozentsatz der Dateien, die basierend auf dieser Stichwahl überprüft werden.

  - **Rückruf**: Prozentsatz der relevanten Dateien im Überprüfungssatz.

  - **Next relevant:** Kosten für die Überprüfung und Identifizierung einer anderen relevanten Datei, die sich derzeit nicht im Überprüfungssatz befindet.

  - **Gesamtkosten**: Kosten für die Überprüfung dieses Prozentsatzes der Falldateien. Einstellungen für den Cost-Parameter können vom Case-Manager festgelegt werden.

  - **Verteilung nach Relevanzpunktzahl:** Dateien in der dunkelgrauen Anzeige auf der linken Seite liegen unterhalb der Cutoff-Bewertung. Eine QuickInfo zeigt die Relevanzbewertung und den zugehörigen Prozentsatz der Dateien in der Überprüfungsdatei im Verhältnis zu den Gesamtdateien an.

Im **erweiterten Detailbereich** werden weitere Details angezeigt. Dateien in Sammlungsfiguren enthalten keine leeren oder nebuischen Dateien. Abbildungen von Familiendateien stellen Dateien dar, die nicht in Relevanz geladen, aber dennoch als Teil der Familie gezählt werden.
