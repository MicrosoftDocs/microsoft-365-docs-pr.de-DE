---
title: Nachverfolgen der Relevanzanalyse in Advanced eDiscovery
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
description: Erfahren Sie, wie Sie den Status und die Ergebnisse des Relevanztrainings für Fallprobleme in Advanced eDiscovery anzeigen und interpretieren.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769180"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a>Nachverfolgen der Relevanzanalyse in Advanced eDiscovery
  
In Advanced eDiscovery zeigt die Registerkarte Relevanzspur die berechnete Gültigkeit der Relevanzschulung an, die auf der Registerkarte Tag durchgeführt wurde, und gibt den nächsten Schritt im iterativen Schulungsprozess in Relevanz an. 
  
## <a name="tracking-relevance-training-status"></a>Nachverfolgen des Relevanzschulungsstatus

1. Sehen Sie sich die folgenden Details in Relevanzspur für die Fallprobleme an, wie im folgenden Beispiel eines Dialogfelds **Problemname unten** gezeigt.

   - **Bewertung**: Dieser Fortschrittsindikator zeigt, in welchem Umfang die bisher durchgeführte Relevanzschulung das Bewertungsziel hinsichtlich der Fehlermarge erreicht hat. Der Reichhaltige der Relevanztrainingsergebnisse wird ebenfalls angezeigt.

   - **Schulung**: Diese farbcodete Fortschrittsanzeige und Tooltipps gibt die Stabilität der Relevanztrainingsergebnisse und eine numerische Skalierung an, die die Anzahl der Relevanzschulungsbeispiele angibt, die für jedes Problem markiert sind. Der Experte überwacht den Fortschritt des iterativen Relevanzschulungsprozesses. 
  
   - **Batchberechnung**: Diese Statusanzeige enthält Informationen zum Abschluss der Batchberechnung.
  
   - **Nächster Schritt**: Zeigt die Empfehlung für den nächsten Schritt an. 
  
    Im Beispiel wird eine erfolgreich abgeschlossene Bewertung für ein Problem angezeigt, die durch die Statusanzeige für den abgeschlossenen Farbfortschritt und das Häkchen angegeben wird. Tagging ist im Gange, aber der Fall wird weiterhin als instabil betrachtet (Stabilitätsstatus wird auch in einer QuickInfo angezeigt). Die nächste Schrittempfehlung ist "Schulung". 
  
    ![Relevanz verfolgen Schulungsschritt 1](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    In der erweiterten Ansicht werden zusätzliche Informationen und Optionen angezeigt. Die angezeigte aktuelle Fehlerspanne ist die Fehlermarge des Rückrufs im aktuellen Bewertungsstatus, wenn die vorhandenen (bereits markierten) Bewertungsdateien verwendet werden.
  
    > [!NOTE]
    >  Die Bewertungsphase kann umgangen werden, indem sie das Kontrollkästchen **Bewertung** pro Problem und dann für "alle Probleme" ausräumt. Daher gibt es jedoch keine Statistiken für dieses Problem. > Das Löschen des **Kontrollkästchens Bewertung** kann nur durchgeführt werden, bevor die Bewertung durchgeführt wird. Wenn in einem Fall mehrere Probleme vorhanden sind, wird die Bewertung nur umgangen, wenn das Kontrollkästchen für jedes Problem behoben ist. 
  
    Wenn die Bewertung nicht mit dem ersten Beispielsatz von Dateien abgeschlossen ist, kann die Bewertung der nächste Schritt zum Markieren weiterer Dateien sein.
  
    In **Relevanzspur** geben die Fortschrittsanzeige und die QuickInfo der Schulung die geschätzte Anzahl zusätzlicher Beispiele an, die zum Erreichen der \> Stabilität erforderlich sind. Diese Schätzung bietet eine Richtlinie für die erforderlichen zusätzlichen Schulungen.
  
    ![Relevanz-Track-Schulung](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. Wenn Sie das Tagging fertig haben und die Schulung fortsetzen müssen, klicken Sie auf **Schulung**. Ein weiterer Beispielsatz von Dateien wird aus dem geladenen Dateisatz für zusätzliche Schulungen generiert. Anschließend werden Sie zur Registerkarte Tag zurückgegeben, um weitere Dateien zu kennzeichnen und zu schulen.

### <a name="reaching-stable-training-levels"></a>Erreichen stabiler Schulungsstufen

Nachdem die Bewertungsdateien ein stabiles Schulungsniveau erreicht haben, ist Advanced eDiscovery für die Batchberechnung bereit.
  
> [!NOTE]
> In der Regel ist nach drei stabilen Schulungsbeispielen der nächste Schritt "Batchberechnung". Es kann Ausnahmen geben, z. B. wenn änderungen am Tagging von Dateien aus früheren Beispielen vorgenommen wurden oder wenn Seeddateien hinzugefügt wurden. 
  
### <a name="performing-batch-calculation"></a>Ausführen von Batchberechnungen

Die Batchberechnung wird als nächster Schritt nach erfolgreichem Abschluss der Schulung ausgeführt (wenn ein stabiler Schulungsstatus in der Statusleiste angezeigt wird, ein Häkchen und ein Stable-Status in der QuickInfo).) Die Batchberechnung wendet die während der Relevanzschulung erworbenen Kenntnisse auf die gesamte Dateigesamtheit an, um die Relevanz der Dateien zu bewerten und Relevanzergebnisse zuzuordnen.
  
Wenn mehr als ein Problem vor liegt, wird die Batchberechnung pro Problem ausgeführt. Während der Batchberechnung wird der Fortschritt überwacht, während alle Dateien verarbeitet werden. 
  
Hier ist der empfohlene nächste Schritt "None", der angibt, dass derzeit keine zusätzlichen iterativen Relevanzschulungen erforderlich sind. Die nächste Phase ist die **Registerkarte Relevanz \> entscheiden.** 
  
Wenn Sie neue Dateien nach der Batchberechnung importieren möchten, kann der Administrator die importierten Dateien einer neuen Last hinzufügen.
  
> [!NOTE]
> Wenn Sie während **der Batchberechnung** auf Abbrechen klicken, speichert der Prozess, was bereits ausgeführt wurde. Wenn Sie die Batchberechnung erneut ausführen, wird der Vorgang ab dem letzten ausgeführten Punkt fortgesetzt. 
  
### <a name="assessing-tagging-consistency"></a>Bewerten der Taggingkonsistenz

Wenn beim Tagging von Dateien Inkonsistenzen vorhanden sind, kann sich dies auf die Analyse auswirken. Der Advanced eDiscovery-Taggingkonsistenzprozess kann verwendet werden, wenn die Ergebnisse nicht optimal sind oder die Konsistenz in Frage kommt. Es wird eine Liste möglicher inkonsistent markierter Dateien zurückgegeben, die bei Bedarf überprüft und erneut erfasst werden können.
  
> [!NOTE]
> Nach sieben oder mehr Schulungsrunden nach der Bewertung  kann die Kennzeichnungskonsistenz unter \> **Relevanzspurproblem** Detaillierte Ergebnisse \>  \>  \> **Schulungsfortschritt angezeigt werden.** Diese Überprüfung wird für ein Problem nach dem anderen durchgeführt.
  
1. Erweitern **Sie in \> Relevanzspur** die Zeile eines Problems.
  
2. Klicken Sie rechts neben **Nächster Schritt** auf **Ändern**.
  
3. Wählen **Sie nach sieben Schulungsbeispielen** die Option Inkonsistenzen als **Nächster** Schritt markieren aus, und klicken Sie auf **OK**.
  
4. Wählen **Sie Tag inconsistencies aus.** Die **Registerkarte Tag** wird geöffnet und zeigt eine Liste der Inkonsistenzen an, die bei Bedarf neu zentriert werden müssen.
  
5. Klicken Sie **auf Berechnen,** um die Änderungen zu übermitteln. Der nächste Schritt nach dem Taggen von Inkonsistenzen ist "Training". 
  
## <a name="viewing-and-using-relevance-results"></a>Anzeigen und Verwenden von Relevanzergebnissen

Erweitern Sie **auf \> der** Registerkarte Relevanzspur die Zeile eines Problems, und klicken Sie neben **Detaillierte** Ergebnisse auf **Ansicht**. Die Detaillierten Ergebnisbereiche werden angezeigt, wie unten gezeigt und beschrieben.
  
![Detaillierte Ergebnisse der Relevanzschulung](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a>Zusammenfassung des Taggings

 Im unten gezeigten Beispiel zeigt die **Zusammenfassung tagging** Summen für jeden Bewertungs-, Schulungs- und Nachholdateitaggingprozess an.
  
![Zusammenfassung der Relevanz-Track-Tagging](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a>Schlüsselwörter

Ein Schlüsselwort ist eine eindeutige Zeichenfolge, ein Wort, eine Phrase oder eine Sequenz von Wörtern in einer Datei, die von Advanced eDiscovery als wichtiger Indikator dafür identifiziert wird, ob eine Datei relevant ist. Die Spaltenliste "Include" listet Schlüsselwort und Gewichtungen in Dateien auf, die als relevant gekennzeichnet sind, und die Spalten "Exclude" listet Schlüsselwörter und Gewichtungen in Dateien auf, die als Nicht relevant gekennzeichnet sind.
  
Advanced eDiscovery weist negative oder positive Schlüsselwortgewichtungswerte zu. Je höher die Gewichtung, desto höher ist die Wahrscheinlichkeit, dass einer Datei, in der das Schlüsselwort angezeigt wird, während der Batchberechnung eine höhere Relevanznote zugewiesen wird.
  
Die Advanced eDiscovery-Liste mit Schlüsselwörtern kann verwendet werden, um eine liste zu ergänzen, die von einem Experten erstellt wurde, oder als indirekte Überprüfung der Sanität an jedem Punkt des Dateiüberprüfungsprozesses.
  
### <a name="training-progress"></a>Schulungsfortschritt

Der **Bereich Schulungsfortschritt** enthält ein Schulungsfortschrittsdiagramm und eine Qualitätsindikatoranzeige, wie im folgenden Beispiel gezeigt.
  
![Relevanz Nachverfolgen des Schulungsfortschritts](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
**Indikator für die** Schulungsqualität : Zeigt die Bewertung der Taggingkonsistenz wie folgt an:
  
- **Gut:** Dateien werden konsistent markiert. (Grünes Licht wird angezeigt)
  
- **Medium**: Einige Dateien können inkonsistent markiert werden. (Gelbes Licht angezeigt)

- **Warnung:** Viele Dateien können inkonsistent markiert werden. (Rotes Licht angezeigt)

**Abbildung des Schulungsfortschritts**: Zeigt den Grad der Relevanztrainingsstabilität nach vielen Relevanztrainingszyklen im Vergleich zum F-Measure-Wert an. Während wir uns von links nach rechts im Diagramm bewegen, wird das Konfidenzintervall verengt und zusammen mit dem F-Measure von Advanced eDiscovery Relevance verwendet, um die Stabilität zu bestimmen, wenn die Relevanztrainingsergebnisse optimiert werden.
  
> [!NOTE]
> Relevanz verwendet F2, eine F-Measure-Metrik, bei der Rückruf doppelt so viel Gewicht wie Precision erhält. Für Fälle mit hoher Reicherkeit (über 25 %) verwendet relevanz F1 (Verhältnis 1:1). Das F-Measure-Verhältnis kann  unter Relevanzeinrichtung Erweiterte \> **Einstellungen konfiguriert werden.**
  
### <a name="batch-calculation-results"></a>Ergebnisse der Batchberechnung

Der **Ergebnisbereich** Batchberechnung enthält die Anzahl der Dateien, die wie folgt für relevanzpunktiert wurden: 
  
- **Success**
  
- **Leer**: Enthält keinen Text, z. B. nur Leerzeichen/Registerkarten
  
- **Failed**: Due to excessive size or could not be read
  
- **Ignoriert:** Aufgrund einer übermäßig hohen Größe
  
- **Nebulous**: Enthält bedeutungslosen Text oder keine für das Problem relevanten Features.
  
> [!NOTE]
> Leer, Fehlgeschlagen, Ignoriert oder Nebulous erhält die Relevanznote -1.
  
### <a name="training-statistics"></a>Schulungsstatistiken

Im **Bereich Schulungsstatistik** werden Statistiken und Diagramme basierend auf den Ergebnissen von Advanced eDiscovery Relevance Training angezeigt. 
  
![Relevanz nachverfolgen von Schulungsstatistiken](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
Diese Ansicht zeigt Folgendes:
  
- **Review-Recall-Verhältnis:** Vergleich der Ergebnisse nach Relevanzbewertung in einer hypothetisch linearen Überprüfung. Der Rückruf wird geschätzt, wenn die Größe des Überprüfungssatzs festgelegt ist.
  
- **Parameter**: Kumulierte berechnete Statistiken im Zusammenhang mit dem Überprüfungssatz in Bezug auf die Dateigesamtheit für den gesamten Fall.
  
- **Review**: Prozentsatz der Dateien, die basierend auf dieser Stichwahl überprüft werden.
  
- **Rückruf**: Prozentsatz der relevanten Dateien im Überprüfungssatz. 
  
- **Verteilung nach Relevanzpunktzahl:** Dateien in der dunkelgrauen Anzeige auf der linken Seite liegen unterhalb der Cutoff-Bewertung. Eine QuickInfo zeigt die Relevanzbewertung und den zugehörigen Prozentsatz der Dateien in der Überprüfungsdatei im Verhältnis zu den Gesamtdateien an.
