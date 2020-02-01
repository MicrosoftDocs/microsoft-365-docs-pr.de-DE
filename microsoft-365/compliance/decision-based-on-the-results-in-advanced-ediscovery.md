---
title: Entscheidung basierend auf den Ergebnissen in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
description: 'Erfahren Sie, wie die Registerkarte entscheiden in Office 365 Advanced eDiscovery Daten bereitstellt, mit denen Sie die richtige Größe des Überprüfungs Satzes von Fall Dateien ermitteln können. '
ms.openlocfilehash: e60aff12e20a4f8accfbcda958c2d087fd732e88
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595382"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a>Entscheidung basierend auf den Ergebnissen in Office 365 Advanced eDiscovery

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 In Advanced eDiscovery bietet die Registerkarte entscheiden zusätzliche Informationen zum Anzeigen und Verwenden von Statistiken zur Entscheidungsunterstützung zur Bestimmung der Größe des Überprüfungs Satzes von Fall Dateien. 
  
## <a name="using-the-decide-tab"></a>Verwenden der Registerkarte "entscheiden"

![Relevanz entscheiden](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Diese Registerkarte umfasst Folgendes:
  
- **Problem**: von hier aus können Sie das Interesse aus der Liste auswählen. 
    
- **Review-Rückruf Verhältnis**: Vergleich der erweiterten eDiscovery-Überprüfung entsprechend den Relevanz-Bewertungen. Der Cutoff-Punkt im Diagramm stellt den Prozentsatz der zu überprüfenden Dateien dar, der einem Relevanz-Ergebnis zugeordnet ist. Dies wird in der Phase für die Relevanzprüfung und als Export Schwellenwert für das Culling verwendet. Der Standardgrenzwert für die Anzahl der zu überprüfenden Dateien liegt an dem Ort, an dem die Balance Zwischenrückruf und Genauigkeit optimal ist. Der tatsächliche Sperrpunkt sollte vom Benutzer abhängig von den Zielen und dem Kosten Kompromiss (% Review) und dem Risiko (% Rückruf) festgelegt werden. Mithilfe des Schiebereglers können Sie den abgrenzpunkt anpassen und die Auswirkung auf das Diagramm und die Parameter anzeigen, wenn Sie den Prozentsatz relevanter Dateien anpassen, die abgerufen werden sollen, und vor dem Validieren einer Entscheidung.
    
- **Parameter**: Review, Recall, Next relevant and Total Cost Parameters sind kumulierte berechnete Statistiken im Zusammenhang mit der Überprüfungsgruppe im Verhältnis zur Sammlung für den gesamten Fall. Definitionen für diese Parameter lauten wie folgt:
    
    **Review**: Prozentsatz der zu überprüfenden Dateien basierend auf diesem Cutoff. 
    
    **Rückruf**: Prozentsatz relevanter Dateien im Überprüfungs Satz. 
    
    **Next relevant**: Kosten für die Überprüfung und Identifizierung einer zusätzlichen relevanten Datei, die derzeit nicht im Überprüfungs ist. 
    
    **Gesamtkosten**: Kosten für die Überprüfung dieses Prozentsatzes der Fall Dateien. Kosten Parametereinstellungen können vom Case Manager festgelegt werden.
    
- **Verteilung nach Relevanz-Ergebnis**: Dateien in der dunkelgrauen Anzeige links liegen unterhalb der Cutoff-Punktzahl. Ein QuickInfo zeigt das Relevanz-Ergebnis und den zugehörigen Prozentsatz der Dateien im Überprüfungs Dateisatz im Verhältnis zu den Gesamtdateien an.
    
Im erweiterten Detailbereich werden zusätzliche Details angezeigt. Dateien in Sammlungs Abbildungen enthalten keine leeren oder nebligen Dateien. Familiendateien Abbildungen stellen Dateien dar, die nicht relevant geladen werden, aber dennoch als Teil der Familie gezählt werden.
  
## <a name="see-also"></a>Siehe auch

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Grundlegendes zur Relevanz der Bewertung](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging und Bewertung](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Durchführen von Relevanz-Schulungen](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Analyse der nach Verfolgungs Relevanz](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Testen der Relevanz-Analyse](test-relevance-analysis-in-advanced-ediscovery.md)

