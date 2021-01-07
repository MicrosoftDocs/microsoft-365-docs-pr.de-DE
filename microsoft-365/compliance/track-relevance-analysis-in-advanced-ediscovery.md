---
title: Nachverfolgen der Relevanz-Analyse in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Hier erfahren Sie, wie Sie den Status und die Ergebnisse von Relevanz-Schulungen für Fall Probleme in Advanced eDiscovery anzeigen und interpretieren.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769180"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a>Nachverfolgen der Relevanz-Analyse in Advanced eDiscovery
  
In Advanced eDiscovery wird auf der Registerkarte Relevanz Track die berechnete Gültigkeit der Relevanz-Schulung angezeigt, die auf der Registerkarte "Tag" ausgeführt wird, und es wird der nächste Schritt angegeben, der in Relevanz für den iterativen Schulungsprozess erfolgen soll. 
  
## <a name="tracking-relevance-training-status"></a>Schulungsstatus für Tracking Relevanz

1. Zeigen Sie die folgenden Details in Relevanz Track für die Fall Probleme an, wie im folgenden Beispiel des Dialogfelds **Problem Name** gezeigt.

   - **Bewertung**: dieser Fortschrittsindikator zeigt an, in welchem Ausmaß die an diesem Punkt durchgeführte Relevanz-Schulung Das Bewertungs Ziel im Hinblick auf die Fehlergrenze erreicht hat. Die Reichhaltigkeit der Relevanz-Schulungsergebnisse wird ebenfalls angezeigt.

   - **Schulung**: Diese farbcodierte Statusanzeige und QuickInfo gibt die Stabilität der Relevanz-Trainingsergebnisse und eine numerische Skala an, die die Anzahl der für jedes Problem geschilderten Relevanz-Schulungsbeispiele anzeigt. Der Experte überwacht den Fortschritt des iterativen Relevanz-Schulungsprozesses. 
  
   - **Stapel Berechnung**: Diese Statusanzeige enthält Informationen zum Abschluss der Batch Berechnung.
  
   - **Nächster Schritt**: zeigt die Empfehlung für den nächsten Schritt an, der ausgeführt werden soll. 
  
    In dem Beispiel wird eine erfolgreich abgeschlossene Bewertung für ein Problem angezeigt, die durch den abgeschlossenen Farbverlaufs Indikator und das Häkchen gekennzeichnet ist. Tagging ist im Gange, aber der Fall wird weiterhin als instabil betrachtet (Stabilitäts Status wird auch in einem QuickInfo-Tool angezeigt). Die Empfehlung für den nächsten Schritt lautet "Training". 
  
    ![Relevanz Track Training Schritt 1](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    In der erweiterten Ansicht werden zusätzliche Informationen und Optionen angezeigt. Der angezeigte aktuelle Fehler Rand ist der Fehler Rand des Rückrufs im aktuellen Bewertungsstatus, da die vorhandenen (bereits markierten) Bewertungsdateien vorhanden sind.
  
    > [!NOTE]
    >  Die Bewertungsphase kann umgangen werden, indem das Kontrollkästchen **Bewertung** pro Problem und dann für "alle Probleme" deaktiviert wird. Daraus ergibt sich jedoch keine Statistik für dieses Problem. > das Deaktivieren des Kontrollkästchens **Bewertung** kann nur ausgeführt werden, bevor eine Bewertung durchgeführt wird. Wenn in einem Fall mehrere Probleme vorhanden sind, wird die Bewertung nur umgangen, wenn das Kontrollkästchen für jedes Problem deaktiviert ist. 
  
    Wenn die Bewertung nicht mit dem ersten Beispiel Dateisatz abgeschlossen ist, kann die Bewertung der nächste Schritt sein, um weitere Dateien zu markieren.
  
    In **Relevanz** \> **Track** zeigen die trainingsfortschrittsanzeige und die QuickInfo die geschätzte Anzahl zusätzlicher Beispiele an, die für die Stabilität erforderlich sind. Diese Schätzung enthält eine Richtlinie für die erforderliche zusätzliche Schulung.
  
    ![Relevanz Track Training](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. Wenn Sie die Markierung abgeschlossen haben und die Schulung fortsetzen möchten, klicken Sie auf **Training**. Ein weiterer Beispielsatz von Dateien wird aus dem geladenen Datei Satz für zusätzliche Schulungen generiert. Anschließend kehren Sie zur Registerkarte Tag zurück, um weitere Dateien zu markieren und zu Schulen.

### <a name="reaching-stable-training-levels"></a>Erreichen stabiler Schulungsstufen

Nachdem die Bewertungsdateien ein stabiles Schulungsniveau erreicht haben, ist Advanced eDiscovery für die Batch Berechnung verfügbar.
  
> [!NOTE]
> Normalerweise ist nach drei stabilen Schulungs Beispielen der nächste Schritt "Batch Berechnung". Es kann Ausnahmen geben, beispielsweise, wenn Änderungen am Tagging von Dateien aus früheren Beispielen oder beim Hinzufügen von Seed-Dateien vorgenommen wurden. 
  
### <a name="performing-batch-calculation"></a>Durchführen der Batch Berechnung

Die Batch Berechnung wird als nächster Schritt nach erfolgreichem Abschluss des Trainings ausgeführt (wenn ein stabiler Trainingsstatus durch die Statusanzeige angezeigt wird, ein Häkchen und ein stabiler Status in der QuickInfo). Bei der Batch Berechnung wird das während der Relevanz-Schulung erworbene Wissen auf die gesamte Datei Auffüllung angewendet, um die Relevanz der Dateien zu bewerten und um die Relevanz der Ergebnisse zuzuweisen.
  
Wenn mehr als ein Problem vorliegt, wird die Batch Berechnung pro Problem durchgeführt. Während der Batch Berechnung wird der Fortschritt bei der Verarbeitung aller Dateien überwacht. 
  
Hier lautet der Empfohlene nächste Schritt "None", was darauf hinweist, dass an dieser Stelle kein zusätzliches iteratives Relevanz-Training erforderlich ist. Die nächste Phase ist die Registerkarte **Relevanz \> entscheiden** . 
  
Wenn Sie neue Dateien nach der Batch Berechnung importieren möchten, kann der Administrator die importierten Dateien einer neuen Last hinzufügen.
  
> [!NOTE]
> Wenn Sie während der Batch Berechnung auf **Abbrechen** klicken, wird der Vorgang gespeichert, der bereits ausgeführt wurde. Wenn Sie die Batch Berechnung erneut ausführen, wird der Prozess vom letzten ausgeführten Endpunkt fortgesetzt. 
  
### <a name="assessing-tagging-consistency"></a>Bewerten der Konsistenz von Markierungen

Wenn es Inkonsistenzen bei der Dateikennzeichnung gibt, kann dies Auswirkungen auf die Analyse haben. Der erweiterte eDiscovery-Tagging-Konsistenz Prozess kann verwendet werden, wenn die Ergebnisse nicht optimal sind oder Konsistenz Zweifel aufkommen. Eine Liste der möglichen inkonsistente getaggten Dateien wird zurückgegeben, und Sie können bei Bedarf überprüft und neu markiert werden.
  
> [!NOTE]
> Nach sieben oder mehr Schulungs Runden nach der Bewertung kann die Markierungs Konsistenz in **Relevanz** \> **Track** - \> **Problem** \> **detaillierte Ergebnisse** \> **Schulungs Fortschritt** angezeigt werden. Diese Überprüfung erfolgt gleichzeitig für ein Problem.
  
1. Erweitern Sie in **Relevanz nach \> verfolgen** die Zeile eines Problems.
  
2. Klicken Sie rechts **neben nächster Schritt** auf **ändern**.
  
3. Wählen Sie nach sieben Schulungs Beispielen **Tag Inkonsistenzen** als **nächste Schritt** Option aus, und klicken Sie auf **OK**.
  
4. Wählen Sie **Inkonsistenzen für Tags** aus. Die Registerkarte **Tag** wird geöffnet und zeigt eine Liste der Inkonsistenzen an, die bei Bedarf Neuberechnung werden.
  
5. Klicken Sie auf **berechnen** , um die Änderungen zu übermitteln. Der nächste Schritt nach der Kennzeichnung von Inkonsistenzen ist "Training". 
  
## <a name="viewing-and-using-relevance-results"></a>Anzeigen und Verwenden von Relevanz-Ergebnissen

Erweitern Sie auf der Registerkarte **Relevanz \> Track** die Zeile eines Problems, und klicken Sie neben **detaillierte Ergebnisse** auf **Ansicht**. Die detaillierten Ergebnisbereiche werden angezeigt, wie im folgenden dargestellt und beschrieben.
  
![Relevanz Training detaillierte Ergebnisse](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a>Tagging-Zusammenfassung

 Im unten gezeigten Beispiel werden in der **Sammel Markierungs Zusammenfassung** die Gesamtwerte für die einzelnen Bewertungs-, Schulungs-und Catch-up-Datei Markierungs Prozesse angezeigt.
  
![Übersicht über die Relevanz von Track-Tags](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a>Schlüsselwörter

Ein Schlüsselwort ist eine eindeutige Zeichenfolge, ein Wort, eine Phrase oder eine Sequenz von Wörtern in einer Datei, die von Advanced eDiscovery als signifikanter Indikator dafür identifiziert wird, ob eine Datei relevant ist. Die Spalten "include" Listen Schlüsselwort und Gewichtungen in Dateien, die als relevant markiert sind, und in den Spalten "ausschließen" werden Stichwörter und Gewichtungen in Dateien aufgelistet, die als nicht relevant gekennzeichnet sind.
  
Advanced eDiscovery weist negative oder positive Keyword-Gewichtungswerte zu. Je höher die Gewichtung, desto höher ist die Wahrscheinlichkeit, dass eine Datei, in der das Stichwort angezeigt wird, bei der Batch Berechnung ein höheres Relevanz-Ergebnis erhält.
  
Die erweiterte eDiscovery-Liste mit Stichwörtern kann verwendet werden, um eine Liste, die von einem Experten erstellt wurde, oder als indirekte Plausibilitätsprüfung zu einem beliebigen Zeitpunkt im Datei Überprüfungsprozess zu ergänzen.
  
### <a name="training-progress"></a>Schulungs Fortschritt

Der Bereich **Trainingsfortschritt** enthält einen Fortschrittsdiagramm für den Trainingsfortschritt und eine Qualitätsanzeige, wie im folgenden Beispiel dargestellt.
  
![Relevanz Nachverfolgen des Schulungs Fortschritts](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
**Trainings Qualitätsindikator**: zeigt die Bewertung der Markierungs Konsistenz wie folgt an:
  
- **Gut**: Dateien werden konsistent markiert. (Grünes Licht wird angezeigt)
  
- **Medium**: einige Dateien werden möglicherweise inkonsistent gekennzeichnet. (Gelbe Anzeige)

- **Warnung**: viele Dateien werden möglicherweise inkonsistent gekennzeichnet. (Rotes Licht wird angezeigt)

**Trainingsfortschritt Graph**: zeigt den Grad der Relevanz der Trainings Stabilität nach vielen Relevanz-trainingszyklen im Vergleich zum F-Measure-Wert an. Wenn wir von links nach rechts über das Diagramm navigieren, verengt sich das Konfidenzintervall und wird zusammen mit der F-Maßnahme mit der erweiterten eDiscovery-Relevanz verwendet, um die Stabilität zu bestimmen, wenn die Relevanz-Trainingsergebnisse optimiert werden.
  
> [!NOTE]
> Relevanz verwendet F2, eine F-Measure-Metrik, bei der der Rückruf doppelt so viel Gewicht erhält wie die Genauigkeit. Für Fälle mit hohem Reichtum (über 25%) verwendet Relevanz F1 (1:1 Verhältnis). Das Verhältnis F-Measure kann unter **Relevanz Setup** \> **Erweiterte Einstellungen** konfiguriert werden.
  
### <a name="batch-calculation-results"></a>Ergebnisse der Batch Berechnung

Der Bereich **Batch Berechnungsergebnisse** enthält die Anzahl der Dateien, die für die Relevanz bewertet wurden, wie folgt: 
  
- **Success**
  
- **Empty**: enthält keinen Text, beispielsweise nur Leerzeichen/Tabstopps
  
- **Fehler**: aufgrund übermäßiger Größe oder konnte nicht gelesen werden
  
- **Ignoriert**: aufgrund übermäßiger Größe
  
- **Neblig**: enthält sinnlosen Text oder keine Features, die für das Problem relevant sind.
  
> [!NOTE]
> Leer, Fehler, ignoriert oder Nebel erhalten ein Relevanz-Ergebnis von-1.
  
### <a name="training-statistics"></a>Schulungs Statistiken

Im Bereich " **Trainingsstatistik** " werden Statistiken und Grafiken basierend auf Ergebnissen aus dem Advanced eDiscovery Relevanz Training angezeigt. 
  
![Relevanz Track Training Statistics](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
In dieser Ansicht wird Folgendes angezeigt:
  
- **Review-Recall Ratio**: Vergleich der Ergebnisse nach Relevanz Partituren in einer hypothetisch linearen Überprüfung. Recall wird anhand der Größe der Überprüfungs Sätze geschätzt.
  
- **Parameter**: kumulierte berechnete Statistiken im Zusammenhang mit der Überprüfungsgruppe im Verhältnis zur Datei Auffüllung für den gesamten Fall.
  
- **Review**: Prozentsatz der zu überprüfenden Dateien basierend auf diesem Cutoff.
  
- **Rückruf**: Prozentsatz relevanter Dateien im Überprüfungs Satz. 
  
- **Verteilung nach Relevanz-Ergebnis**: Dateien in der dunkelgrauen Anzeige links liegen unterhalb der Cutoff-Punktzahl. Ein QuickInfo zeigt das Relevanz-Ergebnis und den zugehörigen Prozentsatz der Dateien im Überprüfungs Dateisatz im Verhältnis zu den Gesamtdateien an.
