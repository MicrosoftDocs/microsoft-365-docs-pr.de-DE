---
title: Anzeigen der Schlüsselwortstatistik für Inhaltssuchergebnisse
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/30/2017
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 9701a024-c52e-43f0-b545-9a53478aec04
description: Erfahren Sie, wie Sie das Feature Suchstatistik verwenden, um Statistiken für mehrere Inhaltssuchen im Security & Compliance Center anzuzeigen und zu vergleichen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f12c51c47045996e450772c081bd26ef4a520b5f
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838698"
---
# <a name="view-keyword-statistics-for-content-search-results"></a>Anzeigen der Schlüsselwortstatistik für Inhaltssuchergebnisse

Nachdem Sie eine Inhaltssuche erstellt und ausgeführt haben, können Sie Statistiken zu den geschätzten Suchergebnissen anzeigen. Dies umfasst eine Zusammenfassung der Suchergebnisse (ähnlich der Zusammenfassung der geschätzten Suchergebnisse, die im Detailbereich angezeigt werden), die Abfragestatistiken, z. B. die Anzahl der Inhaltsorte mit Elementen, die mit der Suchabfrage übereinstimmen, und den Namen von Inhaltsstandorten mit den meisten übereinstimmenden Elementen. Sie können Statistiken für eine oder mehrere Inhaltssuchen anzeigen. Auf diese Weise können Sie die Ergebnisse für mehrere Suchanfragen schnell vergleichen und Entscheidungen über die Effektivität Ihrer Suchabfragen treffen.
  
Darüber hinaus können Sie neue und vorhandene Suchabfragen so konfigurieren, dass Statistiken für jedes Schlüsselwort in einer Suchabfrage zurückgegeben werden. Auf diese Weise können Sie die Anzahl der Ergebnisse für jedes Schlüsselwort in einer Abfrage vergleichen und die Schlüsselwortstatistiken aus mehreren Suchen vergleichen.
  
Sie können auch die Such- und Schlüsselwortstatistik in einer CSV-Datei herunterladen. Auf diese Weise können Sie die Filter- und Sortierfunktionen in Excel dazu verwenden, um Ergebnisse zu vergleichen und Berichte für Ihre Suchergebnisse vorzubereiten.
  
## <a name="get-statistics-for-content-searches"></a>Statistiken für Inhaltssuchen erhalten

So zeigen Sie Statistiken für Inhaltssuchen an:
  
1. Wechseln Sie im Microsoft 365 Compliance Center zu **Alle**  >  **Inhaltssuche anzeigen.**

2. Wählen Sie in der Liste der Suchaktionen zwei oder  mehr Suchaktionen aus, und klicken Sie dann auf der Flyoutseite **Massenaktionen** auf Suchstatistik.
    
    ![Wählen Sie mehrere Suchen aus, und klicken Sie dann auf Suchstatistik](../media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. Klicken Sie **auf der** Seite Suchstatistik auf einen der folgenden Links, um Statistiken zu den ausgewählten Suchen anzeigen zu können. 
    
    **Zusammenfassung**
    
    Diese Seite zeigt Statistiken ähnlich denen an, die im Detailbereich auf der Seite **Inhaltssuche angezeigt** werden. Statistiken für alle ausgewählten Suchen werden angezeigt. Beachten Sie, dass Sie die ausgewählten Suchen auch auf dieser Seite erneut ausführen können, um die Statistiken zu aktualisieren. 
    
    ![Zusammenfassung der Statistiken für die ausgewählten Suchen](../media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    a.  Der Name der Inhaltssuche. Wie bereits erwähnt, können Sie Statistiken für mehrere Suchen anzeigen und vergleichen.
    
    b. Der Typ des Inhaltsspeicherorts, der durchsucht wurde. Jede Zeile zeigt Statistiken für Postfächer, Websites und öffentliche Ordner aus der angegebenen Suche an.
    
    c. Die Anzahl der Inhaltspositionen, die Elemente enthalten, die mit der Suchabfrage übereinstimmen. Bei Postfächern enthält diese Statistik auch die Anzahl der Archivpostfächer, die Elemente enthalten, die mit der Suchabfrage übereinstimmen.
    
    d. Die Gesamtanzahl der Elemente aller angegebenen Inhaltspositionen, die mit der Suchabfrage übereinstimmen. Beispiele für Elementtypen sind E-Mail-Nachrichten, Kalenderelemente und Dokumente. Wenn ein Element mehrere Instanzen eines Schlüsselworts enthält, nach dem gesucht wird, wird es nur einmal in der Gesamtanzahl der Elemente gezählt. Wenn Sie beispielsweise nach wörtern "stock" oder "fraud" suchen und eine E-Mail-Nachricht drei Instanzen des Worts "stock" enthält, wird sie nur einmal in der Spalte Elemente **gezählt.** 
    
    e. Die Gesamtgröße aller Elemente, die am angegebenen Inhaltsspeicherort gefunden wurden, die mit der Suchabfrage übereinstimmen. 
    
    **Abfragen**
    
    Auf dieser Seite werden Statistiken zur Suchabfrage angezeigt.
    
    ![Suchabfragestatistiken für die ausgewählten Suchabfragen](../media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    a. Der Name der Inhaltssuche, für die die Zeile Abfragestatistiken enthält.
    
    b. Der Typ des Inhaltsspeicherorts, auf den die Abfragestatistiken anwendbar sind.
    
    c. Diese Spalte gibt an, auf welchen Teil der Suchabfrage die Statistiken anwendbar sind. **Primär** gibt die gesamte Suchabfrage an. Wenn Sie beim Erstellen oder Bearbeiten einer Suchabfrage eine Stichwortliste verwenden, sind Statistiken für jede Komponente der Abfrage in dieser Tabelle enthalten. Weitere Informationen finden Sie im Abschnitt Get [keyword statistics for Content Searches](#get-keyword-statistics-for-content-searches) in diesem Artikel. 
    
    d. Diese Spalte enthält die tatsächliche Suchabfrage, die vom Tool für die Inhaltssuche ausgeführt wird. Beachten Sie, dass das Tool der von Ihnen erstellten Abfrage automatisch einige zusätzliche Komponenten hinzufügt. 

    - Wenn Sie in Postfächern nach allen Inhalten suchen (indem Sie keine Schlüsselwörter angeben), ist die eigentliche Schlüsselwortabfrage so, dass alle  `size>=0` Elemente zurückgegeben werden. 
    
     - Wenn Sie SharePoint Online- und OneDrive for #A0 durchsuchen, werden die beiden folgenden Komponenten hinzugefügt:
    
          **NOT IsExternalContent:1** – Schließt alle Inhalte aus einer lokalen SharePoint-Organisation aus. 
    
          **NOT IsOneNotePage:1** – Schließt alle OneNote-Dateien aus, da es sich dabei um Duplikate eines Dokuments handelt, das der Suchabfrage entspricht. 

    
    e. Die Anzahl der Inhaltsspeicherorte (angegeben durch die Spalte ** Speicherorttyp ** ), die Elemente enthalten, die der in der Spalte **Abfrage** aufgeführten Suchabfrage entsprechen. 
    
    f. Die Anzahl der Elemente (vom angegebenen Inhaltsspeicherort), die der in der Spalte Abfrage aufgeführten **Suchabfrage** entsprechen. Wie bereits erläutert, wird ein Element nur einmal in dieser Spalte gezählt, wenn es mehrere Instanzen eines gesuchten Schlüsselworts enthält. 
    
    g. Die Gesamtgröße aller Gefundenen (am angegebenen Inhaltsspeicherort), die der Suchabfrage in der **Spalte Abfrage** entsprechen. 
    
    **Top locations**
    
    Auf dieser Seite werden Statistiken zur Anzahl der Elemente angezeigt, die der Suchabfrage an jedem durchsuchten Inhaltsspeicherort entsprechen. Es werden die ersten 1.000 Speicherorte angezeigt. Wenn Sie Statistiken für mehrere Suchen anzeigen, werden die 1.000 besten Speicherorte für jede Suche angezeigt. Beachten Sie, dass ein Inhaltsspeicherort nicht auf dieser Seite enthalten ist, wenn er keine Elemente enthält, die mit der Suchabfrage übereinstimmen.
    
    ![Statistiken zur Anzahl der Elemente, die in den durchsuchten Inhaltsstandorten gefunden wurden](../media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    a. Der Name des Inhaltsspeicherorts.
    
    b. Der Typ des Inhaltsspeicherorts, auf den die Standortstatistik anwendbar ist.
    
    c. Es gibt Spalten für jede Suche, für die Sie Statistiken anzeigen. Diese Spalte zeigt die Anzahl (und Gesamtgröße) von Elementen an, die der Suchabfrage an jedem Inhaltsspeicherort entsprechen. Beachten Sie, dass beim Anzeigen von Statistiken für mehrere Suchen die "NA" in dieser Spalte angibt, dass der Inhaltsspeicherort nicht in diese Suche einbezogen wurde. 

## <a name="get-keyword-statistics-for-content-searches"></a>Get keyword statistics for Content Searches

Wie bereits erläutert, zeigt die **Seite Abfragen** die Suchabfrage und die Anzahl (und Größe) von Elementen an, die mit der Abfrage übereinstimmen. Wenn Sie beim Erstellen oder Bearbeiten einer Suchabfrage eine Stichwortliste verwenden, können Sie erweiterte Statistiken erhalten, die anzeigen, wie viele Elemente mit den einzelnen Schlüsselwort- oder Schlüsselwortausdrücken übereinstimmen. Dadurch können Sie schnell ermitteln, welche Teile der Abfrage am effektivsten (und am wenigsten) sind. Wenn ein Schlüsselwort beispielsweise eine große Anzahl von Elementen zurückgibt, können Sie die Schlüsselwortabfrage so verfeinern, dass die Suchergebnisse einengt werden. Sie können eine Stichwortliste einrichten, wenn Sie eine Inhaltssuche erstellen oder bearbeiten. 

So erstellen Sie eine Stichwortliste und zeigen Stichwortstatistiken für eine Inhaltssuche an:
  
1. Wechseln Sie im Microsoft 365 Compliance Center zu **Alle**  >  **Inhaltssuche anzeigen.**
    
2. Klicken Sie in der Liste der Inhaltssuchen auf und eine Suche, und klicken Sie dann auf **Bearbeiten** ![ -Symbol ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
3. Klicken **Sie auf Abfrage,** und gehen Sie dann wie folgt vor: 
    
    ![Klicken Sie auf das Kontrollkästchen Stichwortliste anzeigen, und geben Sie in jeder Zeile ein Schlüsselwort ein.](../media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    a. Klicken Sie **auf das Kontrollkästchen Stichwortliste** anzeigen. 
    
    b. Geben Sie ein Schlüsselwort oder eine Schlüsselwortphase in einer Zeile in der Schlüsselwörtertabelle ein. Geben Sie beispielsweise **budget** in der ersten Zeile ein, und geben Sie **dann** Sicherheit in die zweite Zeile ein. 
    
4. Nachdem Sie die Schlüsselwörter hinzugefügt haben, für  die Sie suchen und Statistiken erhalten möchten, klicken Sie auf Suchen, um die überarbeitete Suche ausführen zu können. 
    
5. Wenn die Suche abgeschlossen ist, wählen Sie sie in der Liste der Suchbegriffe aus, und klicken Sie dann auf **Suchstatistik** ![ Suchstatistik Schaltfläche ](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png) Suchstatistik . Sie können auch Schlüsselwortstatistiken für mehrere Suchen anzeigen und vergleichen.
    
6. Klicken Sie **auf der** Seite Suchstatistik auf **Abfrage,** um die Stichwortstatistik für die ausgewählten Suchabfragen anzeigen zu können. 
    
    ![Die Statistiken für jedes Schlüsselwort für die ausgewählten Suchen werden angezeigt.](../media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    Wie im vorherigen Screenshot gezeigt, werden die Statistiken für jedes Schlüsselwort angezeigt. Dazu gehören: 
    
    - Die Schlüsselwortstatistik für jeden Inhaltsspeicherort, der in der Suche enthalten ist.
    
    - Die tatsächliche Suchabfrage für jedes Schlüsselwort, die alle Bedingungen aus der Suchabfrage enthält. 
    
    - Die vollständige Suchabfrage (in  der **Spalte Teil** als Primär identifiziert) und die Statistiken für die vollständige Abfrage. Beachten Sie, dass es sich um dieselben Statistiken handelt, die auf der Seite **Zusammenfassung angezeigt** werden. 

> [!NOTE]
> Um Probleme zu reduzieren, die durch große Stichwortlisten verursacht werden, sind Sie jetzt auf maximal 20 Zeilen in der Stichwortliste einer Suchabfrage beschränkt.
