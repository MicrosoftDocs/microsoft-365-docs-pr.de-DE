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
description: Erfahren Sie, wie die Registerkarte entscheiden in Advanced eDiscovery Daten bereitstellt, mit denen Sie die richtige Größe des Überprüfungs Satzes von Fall Dateien ermitteln können.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769150"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a>Entscheidungen auf der Grundlage von Relevanz-Ergebnissen in Advanced eDiscovery
  
Im Modul "Relevanz" in Advanced eDiscovery enthält die Registerkarte "entscheiden" zusätzliche Informationen zum Anzeigen und Verwenden von Statistiken zur Entscheidungsunterstützung zur Bestimmung der Größe des Überprüfungs Satzes von Fall Dateien.
  
## <a name="using-the-decide-tab"></a>Verwenden der Registerkarte "entscheiden"

![Relevanz entscheiden](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Diese Registerkarte umfasst die folgenden Komponenten:
  
- **Problem**: von hier aus können Sie das Interesse aus der Liste auswählen.

- **Review-Rückruf Verhältnis**: Vergleiche der erweiterten eDiscovery-Überprüfung entsprechend den Relevanz-Bewertungen. Der Cutoff-Punkt im Diagramm stellt den Prozentsatz der zu überprüfenden Dateien dar, der einem Relevanz-Ergebnis zugeordnet ist. Dies wird in der Phase für die Relevanzprüfung und als Export Schwellenwert für das Culling verwendet. Der Standardgrenzwert für die Anzahl der zu überprüfenden Dateien liegt an dem Ort, an dem die Balance Zwischenrückruf und Genauigkeit optimal ist. Der tatsächliche Sperrpunkt sollte vom Benutzer abhängig von den Zielen und dem Kosten Kompromiss (% Review) und dem Risiko (% Rückruf) festgelegt werden. Mithilfe des Schiebereglers können Sie den abgrenzpunkt anpassen und die Auswirkung auf das Diagramm und die Parameter anzeigen, wenn Sie den Prozentsatz relevanter Dateien anpassen, die abgerufen werden sollen, und vor dem Validieren einer Entscheidung.

- **Parameter**: Review, Recall, Next relevant and Total Cost Parameters sind kumulierte berechnete Statistiken im Zusammenhang mit der Überprüfungsgruppe im Verhältnis zur Sammlung für den gesamten Fall. Definitionen für diese Parameter lauten wie folgt:

  - **Review**: Prozentsatz der zu überprüfenden Dateien basierend auf diesem Cutoff.

  - **Rückruf**: Prozentsatz relevanter Dateien im Überprüfungs Satz.

  - **Als nächstes relevant**: Kosten zum Überprüfen und Identifizieren einer anderen relevanten Datei, die sich derzeit nicht im Überprüfungs-Satzes befindet.

  - **Gesamtkosten**: Kosten für die Überprüfung dieses Prozentsatzes der Fall Dateien. Kosten Parametereinstellungen können vom Case Manager festgelegt werden.

  - **Verteilung nach Relevanz-Ergebnis**: Dateien in der dunkelgrauen Anzeige links liegen unterhalb der Cutoff-Punktzahl. Ein QuickInfo zeigt das Relevanz-Ergebnis und den zugehörigen Prozentsatz der Dateien im Überprüfungs Dateisatz im Verhältnis zu den Gesamtdateien an.

Im erweiterten **Detail** Bereich werden weitere Details angezeigt. Dateien in Sammlungs Abbildungen enthalten keine leeren oder nebligen Dateien. Familiendateien Abbildungen stellen Dateien dar, die nicht relevant geladen werden, aber dennoch als Teil der Familie gezählt werden.
