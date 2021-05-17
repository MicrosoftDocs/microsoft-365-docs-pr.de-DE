---
title: Testen der Relevanzanalyse in Advanced eDiscovery
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
description: Erfahren Sie, wie Sie die Registerkarte Test nach der Batchberechnung in Advanced eDiscovery verwenden, um die Allgemeine Verarbeitungsqualität zu testen, zu vergleichen und zu überprüfen.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769170"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a>Testen der Relevanzanalyse in Advanced eDiscovery
  
Auf der Registerkarte Test in Advanced eDiscovery können Sie die Allgemeine Verarbeitungsqualität testen, vergleichen und überprüfen. Diese Tests werden nach der Batchberechnung durchgeführt. Durch Markieren der Dateien in der Auflistung gibt ein Experte die endgültige Entscheidung darüber ab, ob jede markierte Datei für den Fall relevant ist.
  
In Einzel- und Multiple-Issue-Szenarien werden Tests in der Regel pro Problem durchgeführt. Ergebnisse können nach jedem Test angezeigt werden, und Testergebnisse können mit angegebenen Beispieltestdateien überarbeitet werden.
  
## <a name="testing-the-rest"></a>Testen des Rests

Der Test "Rest testen" dient zum Überprüfen von Entscheidungen zur Ausmerzung, z. B. zum Überprüfen nur von Dateien über einem bestimmten Relevanz-Cutoff-Wert basierend auf den endgültigen Advanced eDiscovery-Ergebnissen. Der Experte überprüft ein Beispiel von Dateien unter einer ausgewählten Stichprobe, um die Anzahl relevanter Dateien innerhalb dieses Ausschnitts auszuwerten.
  
Dieser Test bietet Statistiken und einen Vergleich zwischen dem Prüfsatz und der Rest-Test-Population. Die Ergebnisse des Überprüfungssatzs sind diejenigen, die durch Relevanz während des Training berechnet werden. Die Ergebnisse umfassen Berechnungen basierend auf Einstellungen und Eingabeparametern, z. B.:
  
- Testen Sie Beispielstatistiken zur Anzahl der Dateien in einem Beispiel und identifizierten relevanten Dateien.

- Tabellarischer Vergleich der Population-Parameter des Überprüfungssatzs und des Rests, z. B. die Anzahl der Dateien, die geschätzte Anzahl relevanter Dateien, der geschätzte Reichhaltige und die durchschnittlichen Kosten für die Suche nach einer anderen relevanten Datei. Einstellungen für den Kostenparameter können vom Administrator festgelegt werden.

So führen Sie den Test "Rest testen" aus:

1. Öffnen Sie die **Registerkarte \> Relevanztest.**

2. Klicken Sie **auf der** Registerkarte Test auf **Neuer Test**. Das **Dialogfeld Test erstellen** wird angezeigt, wie im folgenden Beispiel gezeigt.

    ![RelevanzTest der Restergebnisse](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. Geben **Sie unter Testname** und **Beschreibung** den Namen und die Beschreibung ein.

4. Wählen Sie **in der Liste** Testtyp die Option Rest testen **aus.**

5. Wählen Sie **in der Liste Problem/Kategorie** den Problemnamen aus.

6. Wählen Sie **in der Liste** Laden die Last aus. 

7. Akzeptieren **Sie in Read %** den Standardwert, oder wählen Sie einen Wert für die Relevanzsentwertung für die Stichwahl aus. 

8. In **Set size** oder accept the default value. Die Wiederherstellungssymbole stellen die Standardwerte wieder dar.

9. Klicken **Sie auf Starttagging**. Es wird ein Testbeispiel generiert.

10. Überprüfen und kennzeichnen Sie die einzelnen Dateien auf der Registerkarte **\> Relevanztag,** und klicken Sie nach Getan auf **Berechnen**.

11. Klicken Sie auf der Registerkarte Test auf Ergebnisse **anzeigen,** um die Testergebnisse zu sehen. Ein Beispiel ist im folgenden Screenshot dargestellt.

    ![Testen der restlichen Ergebnisse](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
Im vorherigen Screenshot  enthält der Abschnitt Beispielparameter der Tabelle Details zur Anzahl der Dateien im Beispiel, die vom Experten markiert wurden, und zur Anzahl der relevanten Dateien in diesem Beispiel.
  
Der **Abschnitt Population-Parameter** der Tabelle enthält die Testergebnisse, einschließlich der Prüfsatzgesamtheit von Dateien mit einer Bewertung unterhalb des ausgewählten Cutoffs und der "Rest"-Aufgesamtheit von Dateien mit einer Bewertung über dem ausgewählten Cutoff. Für jede Grundgesamtheit werden die folgenden Ergebnisse angezeigt:
  
- Enthält Dateien mit "% gelesen" – Angegebener Cutoff

- Die Gesamtanzahl der Dateien

- Die geschätzte Anzahl relevanter Dateien

- Der geschätzte Reichhaltige

- Die durchschnittlichen Überprüfungskosten für die Suche nach einer anderen relevanten Datei

## <a name="testing-the-slice"></a>Testen des Datenschnitts

Der Test "Test the Slice" führt Tests ähnlich dem Test "Test the Rest" durch, aber mit einem Abschnitt der Datei, wie durch Relevanz read %angegeben.

So führen Sie den Test "Test the Slice" aus:
  
1. Öffnen Sie die **Registerkarte \> Relevanztest.**

2. Klicken Sie **auf der** Registerkarte Test auf **Neuer Test**. Das **Dialogfeld Test erstellen** wird angezeigt.

3. Geben **Sie unter Testname** **und Beschreibung** die Informationen ein.

4. Wählen Sie **in der Liste Testtyp** die Option **Slice testen aus.**

5. Wählen Sie **in der** Liste Problem den Problemnamen aus.

6. Wählen Sie **in der Liste** Laden die Last aus.

7. Akzeptieren **Sie in Read % between** die Standardmäßigen Werte für niedrigen und hohen Bereich oder wählen Sie Werte für die Stichwahlrelevanzwerte aus.

8. Wählen **Sie unter Größe festlegen** einen Wert aus, oder akzeptieren Sie den Standardwert.

    Mit den Wiederherstellungssymbolen wird der Standardwert wiederhergestellt.

9. Klicken **Sie auf Starttagging**. Es wird ein Testbeispiel generiert.

10. Überprüfen und kennzeichnen Sie die einzelnen Dateien auf der Registerkarte **\> Relevanztag,** und klicken Sie nach Getan auf **Berechnen**.

11. Klicken Sie auf der Registerkarte Test auf Ergebnisse **anzeigen,** um die Testergebnisse zu sehen.
