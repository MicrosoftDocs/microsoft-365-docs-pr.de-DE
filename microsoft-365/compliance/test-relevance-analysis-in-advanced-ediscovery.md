---
title: Testen der Relevanz-Analyse in Advanced eDiscovery
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie, wie Sie die Registerkarte "Test" nach der Batch Berechnung in Advanced eDiscovery verwenden, um die Gesamtqualität der Verarbeitung zu testen, zu vergleichen und zu validieren.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769170"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a>Testen der Relevanz-Analyse in Advanced eDiscovery
  
Auf der Registerkarte Test in Advanced eDiscovery können Sie die Gesamtqualität der Verarbeitung testen, vergleichen und validieren. Diese Tests werden nach der Batch Berechnung ausgeführt. Durch das Markieren der Dateien in der Sammlung entscheidet ein Experte darüber, ob jede markierte Datei für den Fall relevant ist.
  
Bei Szenarien mit einem oder mehreren Problemen werden normalerweise Tests pro Problem durchgeführt. Ergebnisse können nach jedem Test angezeigt werden, und die Testergebnisse können mit den angegebenen Beispiel Testdateien überarbeitet werden.
  
## <a name="testing-the-rest"></a>Testen des Rests

Der Test "Rest testen" wird zum Validieren von Culling-Entscheidungen verwendet, zum Beispiel, um nur Dateien über einem bestimmten Relevanz-Cutoff-Ergebnis basierend auf den endgültigen erweiterten eDiscovery-Ergebnissen zu überprüfen. Der Experte überprüft ein Beispiel von Dateien unter einem ausgewählten Cutoff-Ergebnis, um die Anzahl der relevanten Dateien innerhalb dieses Satzes auszuwerten.
  
Dieser Test enthält Statistiken und einen Vergleich zwischen dem Überprüfungs Sätze und dem Test der Rest-Auffüllung. Die Ergebnisse des Überprüfungs Satzes werden von Relevanz während der Schulung berechnet. Die Ergebnisse umfassen Berechnungen basierend auf Einstellungen und Eingabeparametern, beispielsweise:
  
- Testen Sie die Beispiel Statistiken über die Anzahl der Dateien in einem Beispiel und die identifizierten relevanten Dateien.

- Tabellarischer Vergleich der Populations Parameter des Überprüfungs Satzes und des Rests, beispielsweise die Anzahl der Dateien, die geschätzte Anzahl relevanter Dateien, die geschätzte Reichhaltigkeit und die durchschnittlichen Kosten für die Suche nach einer anderen relevanten Datei. Kosten Parametereinstellungen können vom Administrator festgelegt werden.

So führen Sie den Test "Test the Rest" aus:

1. Öffnen Sie die Registerkarte **Relevanz- \> Test** .

2. Klicken Sie auf der Registerkarte **Test** auf **neuer Test**. Das Dialogfeld zum **Erstellen eines Tests** wird angezeigt, wie im folgenden Beispiel dargestellt.

    ![Relevanz Testen der Rest-Ergebnisse](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. Geben Sie unter **Test Name** und **Beschreibung** den Namen und die Beschreibung ein.

4. Wählen Sie in der Liste **Testtyp** **die Option Rest testen** aus.

5. Wählen Sie in der Liste **Problem/Kategorie** den Namen des Problems aus.

6. Wählen Sie in der Liste **Laden** die Option Laden aus. 

7. Übernehmen Sie in **Read%** den Standardwert, oder wählen Sie einen Wert für das Ergebnis der Cutoff-Relevanz aus. 

8. Legen Sie die **Größe fest**, oder übernehmen Sie den Standardwert. Mit den Wiederherstellungs Symbolen werden die Standardwerte wiederhergestellt.

9. Klicken Sie auf **Tagging starten**. Ein Test Beispiel wird generiert.

10. Überprüfen und markieren Sie die Dateien auf der Registerkarte **Relevanz- \> Tag** , und klicken Sie dann auf **berechnen**.

11. Auf der Registerkarte Test können Sie auf **Ergebnisse anzeigen** klicken, um die Testergebnisse anzuzeigen. Ein Beispiel ist im folgenden Screenshot dargestellt.

    ![Testen der Rest-Ergebnisse](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
Im vorherigen Screenshot enthält der Abschnitt " **Sample Parameters** " der Tabelle Details zur Anzahl der Dateien im Beispiel, die vom Experten markiert wurden, sowie die Anzahl relevanter Dateien, die in diesem Beispiel gefunden wurden.
  
Der Abschnitt " **Population Parameters** " der Tabelle enthält die Testergebnisse, einschließlich der Überprüfungsgruppen Auffüllung von Dateien mit einer Partitur unter dem ausgewählten Cutoff und der "Rest"-Auffüllung von Dateien mit einer Bewertung über dem ausgewählten Cutoff. Für jede Auffüllung werden die folgenden Ergebnisse angezeigt:
  
- Enthält Dateien mit dem Read%-angegebenen Cutoff

- Die Gesamtzahl der Dateien

- Die geschätzte Anzahl relevanter Dateien

- Die geschätzte Reichhaltigkeit

- Durchschnittliche Überprüfungskosten für die Suche nach einer anderen relevanten Datei

## <a name="testing-the-slice"></a>Testen des Slices

Der Test "Test the Slice" führt Tests aus, die dem Test "Test the Rest" ähneln, jedoch auf ein Segment des Dateisatzes, wie von Relevanz Read% angegeben.

So führen Sie den Test "Test the Slice" aus:
  
1. Öffnen Sie die Registerkarte **Relevanz- \> Test** .

2. Klicken Sie auf der Registerkarte **Test** auf **neuer Test**. Das Dialogfeld **Test erstellen** wird angezeigt.

3. Geben Sie unter Name und **Beschreibung** **Testen** die Informationen ein.

4. Wählen Sie in der Liste **Testtyp** **die Option Segment testen** aus.

5. Wählen Sie in der Liste **Problem** den Namen des Problems aus.

6. Wählen Sie in der Liste **Laden** die Option Laden aus.

7. Akzeptieren Sie in **Read% zwischen** die Standardwerte Low und High Range, oder wählen Sie Werte für die Punkte für die Grenz Wert Relevanz aus.

8. Wählen Sie unter **festgelegte Größe** einen Wert aus, oder übernehmen Sie den Standardwert.

    Mit den Wiederherstellungs Symbolen wird der Standardwert wiederhergestellt.

9. Klicken Sie auf **Tagging starten**. Ein Test Beispiel wird generiert.

10. Überprüfen und markieren Sie die Dateien auf der Registerkarte **Relevanz- \> Tag** , und klicken Sie dann auf **berechnen**.

11. Auf der Registerkarte Test können Sie auf **Ergebnisse anzeigen** klicken, um die Testergebnisse anzuzeigen.
