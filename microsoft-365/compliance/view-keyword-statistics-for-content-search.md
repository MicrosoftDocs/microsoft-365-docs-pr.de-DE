---
title: Anzeigen von Statistiken für eDiscovery-Suchergebnisse
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie das Suchstatistikfeature verwenden, um Statistiken für Inhaltssuchen und -suchen anzuzeigen, die einem Core eDiscovery-Fall im Microsoft 365 zugeordnet sind.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311113"
---
# <a name="view-statistics-for-ediscovery-search-results"></a>Anzeigen von Statistiken für eDiscovery-Suchergebnisse

Nachdem Sie eine Inhaltssuche oder eine Suche erstellt und ausgeführt haben, die einem Core eDiscovery-Fall zugeordnet ist, können Sie Statistiken zu den geschätzten Suchergebnissen anzeigen. Dies umfasst eine Zusammenfassung der Suchergebnisse (ähnlich der Zusammenfassung der geschätzten Suchergebnisse, die auf der Flyoutseite der Suche angezeigt werden), die Abfragestatistiken wie die Anzahl der Inhaltsspeicherorte mit Elementen, die mit der Suchabfrage übereinstimmen, und die Identität von Inhaltsspeicherorten mit den am besten übereinstimmenden Elementen.
  
Darüber hinaus können Sie die Stichwörterliste verwenden, um eine Suche so zu konfigurieren, dass Statistiken für jedes Schlüsselwort in einer Suchabfrage zurückgegeben werden. Auf diese Weise können Sie die Anzahl der Ergebnisse vergleichen, die von jedem Schlüsselwort in einer Abfrage zurückgegeben werden.
  
Sie können suchstatistiken auch in eine CSV-Datei herunterladen. Auf diese Weise können Sie die Filter- und Sortierfunktionen in Excel dazu verwenden, um Ergebnisse zu vergleichen und Berichte für Ihre Suchergebnisse vorzubereiten.
  
## <a name="get-statistics-for-searches"></a>Statistiken für Suchen erhalten

So zeigen Sie Statistiken für eine Inhaltssuche oder eine Suche an, die einem Core eDiscovery-Fall zugeordnet ist::
  
1. Klicken Sie Microsoft 365 Compliance Center auf **Alle** anzeigen, und gehen Sie dann wie folgt vor:

   - Klicken **Sie auf Inhaltssuche,** und wählen Sie dann eine Suche aus, um die Flyoutseite anzuzeigen.

     ODER

   - Klicken **Sie auf eDiscovery** Core, wählen Sie einen Fall aus, und wählen Sie dann auf der Registerkarte Suchen eine Suche aus, um die  >  Flyoutseite anzeigen zu können. 

2. Klicken Sie auf der Flyoutseite der ausgewählten Suche auf die Registerkarte **Suchstatistik.**
  
   ![Die Registerkarte Suchstatistik](../media/SearchStatistics1.png)

Die **Registerkarte Suchstatistik** enthält für die folgenden Abschnitte, die unterschiedliche Arten von Statistiken zur Suche enthalten.

### <a name="search-content"></a>Suchinhalt

In diesem Abschnitt wird eine grafische Zusammenfassung der von der Suche zurückgegebenen geschätzten Elemente angezeigt. Dies gibt die Anzahl der Elemente an, die den Suchkriterien entsprechen. Diese Informationen geben Ihnen eine Vorstellung von der geschätzten Anzahl von Elementen, die von der Suche zurückgegeben werden.

![Suchschätzungen für eine Suche](../media/SearchContentReport.png)

- **Geschätzte Elemente nach Speicherorten:** Die Gesamtanzahl der geschätzten Elemente, die von der Suche zurückgegeben werden. Die bestimmte Anzahl von Elementen, die sich in Postfächern und auf Websites befinden, wird ebenfalls angezeigt.

- **Geschätzte Speicherorte mit Treffern:** Die Gesamtanzahl der Inhaltsstandorte, die von der Suche zurückgegebene Elemente enthalten. Die spezifische Anzahl von Postfach- und Standortspeicherorten wird ebenfalls angezeigt.

- **Datenvolumen nach Speicherort (in MB):** Die Gesamtgröße aller geschätzten Elemente, die von der Suche zurückgegeben werden. Die spezifische Größe von Postfachelementen und Websiteelementen wird ebenfalls angezeigt.

### <a name="condition-report"></a>Bedingungsbericht

In diesem Abschnitt werden Statistiken zur Suchabfrage und zur Anzahl der geschätzten Elemente angezeigt, die verschiedenen Teilen der Suchabfrage entsprechen. Sie können diese Statistiken verwenden, um die Anzahl der Elemente zu analysieren, die mit jeder Komponente der Suchabfrage übereinstimmen. Dies kann Ihnen helfen, die Suchkriterien zu verfeinern und bei Bedarf den Bereich zu einenten. Sie können auch eine Kopie dieses Berichts im CSV-Format herunterladen.

![Bedingungsbericht](../media/SearchContentReportNoKeywordList.png)

- **Speicherorttyp**: Der Typ des Inhaltsspeicherorts, auf den die Abfragestatistiken anwendbar sind. Der Wert von **Exchange** gibt einen Postfachspeicherort an. ein Wert von **SharePoint** einen Standort angibt.

- **Teil**: Der Teil der Suchabfrage, auf den die Statistiken anwendbar sind. **Primär** gibt die gesamte Suchabfrage an. **Schlüsselwort** gibt an, dass die Statistiken in der Zeile für ein bestimmtes Schlüsselwort verwendet werden. Wenn Sie eine Schlüsselwortliste für suchabfragen verwenden, sind Statistiken für jede Komponente der Abfrage in dieser Tabelle enthalten. Weitere Informationen finden Sie unter [Get keyword statistics for searches](#get-keyword-statistics-for-searches).

- **Bedingung:** Die tatsächliche Komponente (Schlüsselwort oder Bedingung) der Suchabfrage, die die in der entsprechenden Zeile angezeigten Statistiken zurückgegeben hat.

- **Speicherorte mit Treffern**: Die Anzahl  der Inhaltsspeicherorte (angegeben durch die Spalte Standorttyp), die Elemente enthalten, die der primären abfrage oder der Schlüsselwortabfrage in der Spalte **Bedingung** entsprechen.

- **Elemente**: Die Anzahl der Elemente (vom angegebenen Inhaltsspeicherort), die der in der Spalte Bedingung aufgeführten **Abfrage** entsprechen. Wie bereits erläutert, wird ein Element nur einmal in dieser Spalte gezählt, wenn es mehrere Instanzen eines gesuchten Schlüsselworts enthält.

- **Size (MB)**: Die Gesamtgröße aller Gefundenen (am angegebenen Inhaltsspeicherort), die der Suchabfrage in der **Spalte Bedingung** entsprechen.

### <a name="top-locations"></a>Top locations

In diesem Abschnitt werden Statistiken zu den spezifischen Inhaltsstandorten mit den meisten von der Suche zurückgegebenen Elementen angezeigt. Es werden die ersten 1.000 Speicherorte angezeigt. Sie können auch eine Kopie dieses Berichts im CSV-Format herunterladen.

- Der Name des Standortnamens (die E-Mail-Adresse von Postfächern und die URL für Websites).

- Speicherorttyp (Postfach oder Standort).

- Geschätzte Anzahl von Elementen am Von der Suche zurückgegebenen Inhaltsspeicherort.

- Die Gesamtgröße der geschätzten Elemente an jedem Inhaltsspeicherort.

## <a name="get-keyword-statistics-for-searches"></a>Get keyword statistics for searches

Wie bereits erläutert, zeigt der **Abschnitt Bedingungsbericht** die Suchabfrage und die Anzahl (und Größe) von Elementen an, die mit der Abfrage übereinstimmen. Wenn Sie beim Erstellen oder Bearbeiten einer Suchabfrage eine Stichwortliste verwenden, können Sie erweiterte Statistiken erhalten, die anzeigen, wie viele Elemente mit den einzelnen Schlüsselwort- oder Schlüsselwortausdrücken übereinstimmen. Dadurch können Sie schnell ermitteln, welche Teile der Abfrage am effektivsten (und am wenigsten) sind. Wenn ein Schlüsselwort beispielsweise eine große Anzahl von Elementen zurückgibt, können Sie die Schlüsselwortabfrage so verfeinern, dass die Suchergebnisse einengt werden.

So erstellen Sie eine Stichwortliste und zeigen Die Stichwortstatistik für eine Suche an:
  
1. Erstellen Sie Microsoft 365 Compliance Center eine neue Inhaltssuche oder eine Suche, die einem Core eDiscovery-Fall zugeordnet ist.

2. Auf der **Seite Bedingungen** des Suchassistenten. Aktivieren Sie das **Kontrollkästchen Stichwortliste anzeigen.**

   ![Kontrollkästchen Stichwörterliste anzeigen](../media/SearchKeywordsList1.png)

3. Geben Sie ein Schlüsselwort oder eine Schlüsselwortphase in einer Zeile in der Schlüsselwörtertabelle ein. Geben Sie beispielsweise **budget** in der ersten Zeile ein, geben **Sie** Sicherheit in der zweiten Zeile ein, und geben Sie **FY2021** in die dritte Zeile ein.

   ![Geben Sie bis zu 20 Schlüsselwörter oder Stichwortausdrücke in die Liste ein.](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > Um Probleme zu reduzieren, die durch große Stichwortlisten verursacht werden, sind Sie auf maximal 20 Zeilen in der Stichwortliste einer Suchabfrage beschränkt.

4. Nachdem Sie die Schlüsselwörter zur Liste hinzugefügt haben, nach der Sie suchen und Statistiken erhalten möchten, führen Sie die Suche aus.

5. Wenn die Suche abgeschlossen ist, wählen Sie sie aus, um die Flyoutseite angezeigt zu werden.

6. Klicken Sie **auf der** Registerkarte Suchstatistik auf den **Bedingungsbericht,** um die Stichwortstatistik für die Suche anzeigen zu können.

    ![Die Statistiken für jedes Schlüsselwort werden angezeigt.](../media/SearchKeywordsList3.png)
  
    Wie im vorherigen Screenshot gezeigt, werden die Statistiken für jedes Schlüsselwort angezeigt. Dazu gehören:

    - Die Schlüsselwortstatistik für jeden Inhaltsspeicherort, der in der Suche enthalten ist.

    - Die Anzahl der nicht indizierten Postfachelemente.

    - Die tatsächliche Suchabfrage und die Ergebnisse für  jedes Schlüsselwort (identifiziert als **Schlüsselwort** in der Spalte Part), die alle Bedingungen aus der Suchabfrage enthält.

    - Die vollständige Suchabfrage  (in  der Spalte Teil als Primär identifiziert) und die Statistiken für die vollständige Abfrage für jeden Standorttyp. Beachten Sie, dass es sich um dieselben Statistiken handelt, die auf der Registerkarte **Zusammenfassung angezeigt** werden.
