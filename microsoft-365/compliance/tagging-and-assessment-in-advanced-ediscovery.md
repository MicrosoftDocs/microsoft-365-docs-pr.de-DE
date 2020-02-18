---
title: Tagging und Bewertung in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: 'Lesen Sie die Schritte zum Durchführen von Assessment-Schulungen, einschließlich Tagging-Dateien, und Überprüfen der Bewertungsergebnisse in Office 365 Advanced eDiscovery. '
ms.openlocfilehash: 93780d42cd42ced692a81f5cfd739bcd8713c2c2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081037"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a>Tagging und Bewertung in Office 365 Advanced eDiscovery

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In diesem Abschnitt wird das Verfahren für das Modul "Advanced eDiscovery Relevancy Assessment" beschrieben. 
  
## <a name="performing-assessment-training-and-analysis"></a>Durchführen von Schulungs-und Analyse Tests

1. Klicken Sie auf der Registerkarte ** \> Relevanz Track** auf **Bewertung** , um die Fall Bewertung zu starten. 
    
    In diesem Verfahren wird beispielsweise ein Beispiel für einen assessmentsatz von 500-Dateien erstellt, und die Registerkarte " **Tag** " wird angezeigt, die den Markierungsbereich, den angezeigten Dateiinhalt und andere Kennzeichnungs Optionen enthält. 
    
    ![Registerkarte "Relevanz-Tag" für Bewertung](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. Überprüfen Sie jede Datei im Beispiel, bestimmen Sie die Relevanz der Datei für die einzelnen Fall Probleme, und markieren Sie die Datei mit den Schaltflächen Relevanz (R), nicht relevant (Nr) und überspringen im Bereich **Tagging Panel** . 
    
    > [!NOTE]
    >  Die Bewertung erfordert 500 getaggte Dateien. Wenn Dateien "übersprungen" werden, erhalten Sie weitere Dateien, die Tags hinzugefügt werden. 
  
3. Klicken Sie nach dem Markieren aller Dateien im Beispiel auf **berechnen**. 
    
    Die Bewertung Current Error Margin and Reichhaltigkeit werden berechnet und auf der Registerkarte **Relevanz Track** mit erweiterten Details pro Problem angezeigt, wie unten dargestellt. Weitere Details zu diesem Dialogfeld werden im späteren Abschnitt "Überprüfen der Ergebnisse der Bewertung" beschrieben. 
    
    ![Relevanz Track-Assessment](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > Standardmäßig wird empfohlen, mit dem standardmäßigen nächsten Schritt fortzufahren, wenn der Indikator für die Status Bewertung des Problems abgeschlossen wurde, was bedeutet, dass das Bewertungs Beispiel überprüft und ausreichende relevante Dateien markiert wurden. > andernfalls können Sie, wenn Sie die Ergebnisse der Registerkarte **Track** anzeigen und den Fehlerbereich und den nächsten Schritt steuern möchten, auf neben **Nächster Schritt** **ändern** klicken, **Bewertung fortsetzen**auswählen und dann auf **OK**klicken. 
  
1. Klicken Sie rechts neben dem Kontrollkästchen **Bewertung** auf **ändern** , um die Bewertungsparameter pro Problem anzuzeigen und anzugeben. Es wird ein Dialogfeld **Bewertungsebene** für jedes Problem angezeigt, wie im folgenden Beispiel dargestellt: 
    
    ![Fall Problem bei Bewertungsebene](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    Die folgenden Parameter für das Problem werden berechnet und im Dialogfeld " **Bewertungsstufe** " angezeigt: 
    
    **Ziel Fehlermarge für Rückruf Schätzungen**: basierend auf diesem Wert wird die geschätzte Anzahl zusätzlicher Dateien berechnet, die für die Überprüfung erforderlich sind. Der für Rückruf verwendete Rand ist größer als 75% und mit einem Konfidenzniveau von 95%. 
    
    **Erforderliche zusätzliche Testdateien**: gibt an, wie viele weitere Dateien erforderlich sind, wenn die Anforderungen des aktuellen Fehler Rands nicht erfüllt wurden. 
    
2. So passen Sie den aktuellen Fehler Rand an und sehen den Effekt unterschiedlicher Fehler Ränder (pro Problem):
    
1. Wählen Sie in der Liste **Problem auswählen** ein Problem aus. 
    
2. Geben Sie unter **Ziel Fehlermarge für Rückruf Schätzungen**einen neuen Wert ein.
    
3. Klicken Sie auf **Werte aktualisieren** , um die Auswirkungen der Anpassungen anzuzeigen. 
    
3. Klicken Sie im Dialogfeld **Bewertungsebene** auf **erweitert** , um die folgenden zusätzlichen Parameter und Details anzuzeigen: 
    
    ![Fallbeispiel für Bewertungsebene erweiterte Ansicht](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    **Geschätzter Reichtum**: Geschätzter Umfang gemäß den aktuellen Bewertungsergebnissen
    
    **Für angenommene Rückruf**: Standardmäßig gilt die Ziel Fehlermarge für Rückrufe über 75%. Klicken Sie auf **Bearbeiten** , wenn Sie diesen Parameter ändern und die Fehlergrenze für einen anderen Bereich von Rückruf Werten steuern möchten. 
    
    **Konfidenz Stufe**: Standardmäßig beträgt der empfohlene Fehler Rand für das Vertrauen 95%. Klicken Sie auf **Bearbeiten** , wenn Sie diesen Parameter ändern möchten. 
    
    **Rand des erwarteten**Umfangs des Umfangs: bei den aktualisierten Werten ist dies der erwartete Fehlerbereich des Reichtums, nachdem alle zusätzlichen Bewertungsdateien überprüft wurden.
    
    **Zusätzliche Bewertungsdateien erforderlich**: bei den aktualisierten Werten ist die Anzahl der zusätzlichen Bewertungsdateien, die überprüft werden müssen, um das Ziel zu erreichen.
    
    **Erforderliche Gesamt Wertungs Dateien**: bei den aktualisierten Werten werden Gesamt Bewertungsdateien für die Überprüfung benötigt.
    
    **Erwartete Anzahl relevanter Dateien in der Bewertung**: bei den aktualisierten Werten wird die erwartete Anzahl relevanter Dateien in der gesamten Bewertung nach der Überprüfung aller zusätzlichen Bewertungsdateien berücksichtigt.
    
4. Klicken Sie auf **Werte neu berechnen**, wenn Parameter geändert werden. Wenn Sie fertig sind, wenn ein Problem vorliegt, klicken Sie auf **OK** , um die Änderungen zu speichern (oder als **nächstes** , wenn mehrere Probleme zu überprüfen oder zu ändern sind, und klicken Sie dann auf **Fertig stellen**). 
    
    Wenn es mehrere Probleme gibt, wird, nachdem alle Probleme überprüft oder angepasst wurden, ein Dialogfeld " **Bewertungsstufe: Zusammenfassung** " angezeigt, wie im folgenden Beispiel dargestellt. 
    
    ![Zusammenfassung der Bewertungsebene](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    Nach erfolgreichem Abschluss der Bewertung fahren Sie mit dem nächsten Schritt in Relevanz Training fort.
    
## <a name="reviewing-assessment-results"></a>Überprüfen der Bewertungsergebnisse

Nachdem ein Bewertungs Beispiel markiert wurde, werden die Bewertungsergebnisse berechnet und auf der Registerkarte Relevanz Track angezeigt.
  
Die folgenden Ergebnisse werden in der erweiterten Spuranzeige angezeigt: 
  
- Bewertung der aktuellen Fehlermarge für Rückruf Schätzungen
    
- Geschätzte Reichhaltigkeit
    
- Erforderliche zusätzliche Bewertungsdateien (zur Überarbeitung)
    
Der Rand der Bewertung des aktuellen Fehlers ist die von Advanced eDiscovery Empfohlene Fehlermarge. Die Nummer, die für die erforderlichen "zusätzlichen Beurteilungs Dateien" angezeigt wird, entspricht dieser Empfehlung.
  
Die Statusanzeige des Assessments zeigt den Grad des Abschlusses der Bewertung bei der aktuellen Fehlermarge an. Wenn die Bewertung fortgeschritten ist, wird der Benutzer ein anderes Bewertungs Beispiel markieren.
  
Wenn die Statusanzeige Assessment als abgeschlossen angezeigt wird, bedeutet dies, dass die Bewertungs Beispiel Überprüfung abgeschlossen wurde und ausreichende relevante Dateien markiert wurden. 
  
Die erweiterte Spuranzeige zeigt den empfohlenen nächsten Schritt, die Bewertungsstatistiken und den Zugriff auf detaillierte Ergebnisse.
  
Wenn die Reichweite sehr gering ist, ist die Anzahl der zusätzlichen assessmentdateien, die für eine minimale Anzahl relevanter Dateien zur Erstellung nützlicher Statistiken benötigt werden, sehr hoch. Advanced eDiscovery empfiehlt dann die Weiterbildung. Der Statusindikator für die Bewertung wird schattiert angezeigt, und es werden keine Statistiken verfügbar sein. 
  
In Ermangelung einer statistisch basierten Stabilisierung werden Ergebnisse mit einer niedrigeren Genauigkeitsstufe und Zuverlässigkeitsstufe erzielt. Diese Ergebnisse können jedoch zum Auffinden relevanter Dateien verwendet werden, wenn Sie den Prozentsatz relevanter gefundener Dateien nicht kennen müssen. In ähnlicher Weise kann dieser Status verwendet werden, um Probleme mit niedrigem Umfang auszubilden, wobei Relevanz Scores den Zugriff auf Dateien beschleunigen kann, die für ein bestimmtes Problem relevant sind.
  
> [!TIP]
> Auf der **Register \> Karte relevanzstatus** , erweiterte Ausgabe Anzeige, stehen die folgenden Anzeigeoptionen zur Verfügung: > den empfohlenen nächsten Schritt wie den **nächsten Schritt: die Kennzeichnung** kann umgangen werden (pro Problem), indem Sie rechts auf die Schaltfläche **ändern** klicken und dann im **nächsten Schritt**einen anderen Schritt auswählen. Wenn der Statusindikator für die Bewertung nicht abgeschlossen ist, wird die nächste empfohlene Option verwendet, um weitere Bewertungsdateien zu markieren und die Genauigkeit der Statistik zu verbessern. > Sie können den Fehler Rand ändern und seine Auswirkung bewerten, indem Sie auf **ändern**klicken und im **Dialogfeld Bewertungsebene**den **Ziel Fehler Rand für Rückruf Schätzungen**ändern und auf **Werte aktualisieren**klicken. Außerdem können Sie in diesem Dialogfeld Erweiterte Optionen anzeigen, indem Sie auf **erweitert**klicken. > Sie können zusätzliche Statistiken zur Bewertungsebene und deren Auswirkungen anzeigen, indem Sie auf **Ansicht**klicken. Im Dialogfeld Detail Ergebnisse werden Statistiken pro Problem angezeigt, wenn mindestens 500 getaggte Bewertungsdateien vorhanden sind und mindestens 18 Dateien als relevant für das Problem gekennzeichnet sind. 
  
## <a name="see-also"></a>Siehe auch

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Grundlegendes zur Relevanz der Bewertung](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging und Relevanz Training](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Analyse der nach Verfolgungs Relevanz](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Entscheidung basierend auf den Ergebnissen](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testen der Relevanz-Analyse](test-relevance-analysis-in-advanced-ediscovery.md)

