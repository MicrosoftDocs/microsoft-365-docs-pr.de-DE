---
title: Anzeigen der Schlüsselwortstatistik für Inhaltssuchergebnisse
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/30/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 9701a024-c52e-43f0-b545-9a53478aec04
description: Verwenden Sie das Feature Suchstatistik, um Statistiken für mehrere Inhalts suchen im Security & Compliance Center anzuzeigen und zu vergleichen. Sie können die Keyword-Liste auch konfigurieren, wenn Sie eine Suchabfrage erstellen oder bearbeiten, um Erweiterte Statistiken zu erhalten, die zeigen, wie viele Elemente den einzelnen Schlüsselwörtern oder Schlüsselwörtern entsprechen.
ms.openlocfilehash: 07a13ab2f183cfa9349f827cf410e417c0944869
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068950"
---
# <a name="view-keyword-statistics-for-content-search-results"></a>Anzeigen der Schlüsselwortstatistik für Inhaltssuchergebnisse

Nachdem Sie eine Inhaltssuche erstellt und ausgeführt haben, können Sie Statistiken zu den geschätzten Suchergebnissen anzeigen. Dies umfasst eine Zusammenfassung der Suchergebnisse (ähnlich der Zusammenfassung der geschätzten Suchergebnisse, die im Detailbereich angezeigt werden), die Abfragestatistik, beispielsweise die Anzahl der inhaltsspeicherorte mit Elementen, die mit der Suchabfrage übereinstimmen, und der Name der inhaltsspeicherorte. mit den am besten übereinstimmenden Elementen. Sie können Statistiken für eine oder mehrere Inhaltssuchen anzeigen. Auf diese Weise können Sie die Ergebnisse für mehrere Suchvorgänge schnell vergleichen und Entscheidungen hinsichtlich der Effektivität ihrer Suchabfragen treffen.
  
Darüber hinaus können Sie neue und vorhandene Suchvorgänge so konfigurieren, dass Statistiken für jedes Schlüsselwort in einer Suchabfrage zurückgegeben werden. Auf diese Weise können Sie die Anzahl der Ergebnisse für jedes Keyword in einer Abfrage vergleichen und die Keyword-Statistik von mehreren Suchvorgängen vergleichen.
  
Sie können auch die Such- und Schlüsselwortstatistik in einer CSV-Datei herunterladen. Auf diese Weise können Sie die Filter- und Sortierfunktionen in Excel dazu verwenden, um Ergebnisse zu vergleichen und Berichte für Ihre Suchergebnisse vorzubereiten.
  
## <a name="get-statistics-for-content-searches"></a>Abrufen von Statistiken für Inhalts suchen

So zeigen Sie Statistiken für die Inhaltssuche an:
  
1. Wechseln Sie im Security & Compliance Center zu **Such** \> **Inhaltssuche**.
    
2. Wählen Sie in der Liste der Suchvorgänge eine oder mehrere Suchvorgänge aus, ****![und klicken Sie dann auf](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png)Statistik Suchstatistik-Schaltfläche Suchen.
    
    ![Wählen Sie mehrere Suchvorgänge aus, und klicken Sie dann auf Suchstatistik](../media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. Klicken Sie auf der Seite **Suchstatistik** auf einen der folgenden Links, um Statistiken zu den ausgewählten Suchvorgängen anzuzeigen. 
    
    **Zusammenfassung**
    
    Auf dieser Seite werden Statistiken angezeigt, die denen ähneln, die im Detailbereich auf der Seite **Inhaltssuche** angezeigt werden. Statistiken für alle ausgewählten Suchvorgänge werden angezeigt. Beachten Sie, dass Sie die ausgewählten Suchvorgänge auch auf dieser Seite erneut ausführen können, um die Statistiken zu aktualisieren. 
    
    ![Zusammenfassung der Statistik für die ausgewählten Suchvorgänge](../media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    a.  Der Name der Inhaltssuche. Wie bereits erwähnt, können Sie Statistiken für mehrere Suchvorgänge anzeigen und vergleichen.
    
    b. Der Typ des Inhaltsspeicherorts, der durchsucht wurde. Jede Zeile zeigt Statistiken für Postfächer, Websites und öffentliche Ordner aus der angegebenen Suche an.
    
    c. Die Anzahl der inhaltsspeicherorte, die Elemente enthalten, die mit der Suchabfrage übereinstimmen. Bei Postfächern enthält diese Statistik auch die Anzahl von archivpostfächern, die Elemente enthalten, die mit der Suchabfrage übereinstimmen.
    
    d. Die Gesamtzahl der Elemente aller angegebenen inhaltsspeicherorte, die mit der Suchabfrage übereinstimmen. Beispiele für Elementtypen sind e-Mail-Nachrichten, Kalenderelemente und Dokumente. Wenn ein Element mehrere Instanzen eines Schlüsselworts enthält, nach dem gesucht wird, wird es nur einmal in der Gesamtanzahl der Elemente gezählt. Wenn Sie beispielsweise nach Wörtern "Stock" oder "Betrug" suchen und eine e-Mail-Nachricht drei Instanzen des Wortes "Stock" enthält, wird Sie nur einmal in der **Items** -Spalte gezählt. 
    
    e. Die Gesamtgröße aller Elemente, die am angegebenen Inhaltsspeicherort gefunden wurden, die mit der Suchabfrage übereinstimmen. 
    
    **Abfragen**
    
    Auf dieser Seite werden Statistiken zur Suchabfrage angezeigt.
    
    ![Suchabfrage Statistik für die ausgewählten Suchvorgänge](../media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    a. Der Name der Inhaltssuche, für die die Zeile Abfragestatistiken enthält.
    
    b. Der Typ des Inhaltsspeicherorts, auf den die Abfragestatistik angewendet werden soll.
    
    c. In dieser Spalte wird angegeben, auf welchen Teil der Suchabfrage die Statistik angewendet werden soll. **Primary** gibt die gesamte Suchabfrage an. Wenn Sie beim Erstellen oder Bearbeiten einer Suchabfrage eine Stichwortliste verwenden, sind die Statistiken für jede Komponente der Abfrage in dieser Tabelle enthalten. Weitere Informationen finden Sie im Abschnitt [Get Keyword Statistics for Content searches](#get-keyword-statistics-for-content-searches) in diesem Artikel. 
    
    d. Diese Spalte enthält die tatsächliche Suchabfrage, die vom Inhalts Such Tool ausgeführt wird. Beachten Sie, dass das Tool automatisch einige zusätzliche Komponenten zur Abfrage hinzufügt, die Sie erstellen. 

    - Wenn Sie nach allen Inhalten in Postfächern suchen (indem Sie keine Stichwörter angeben), ist `size>=0` die tatsächliche Schlüsselwortabfrage so, dass alle Elemente zurückgegeben werden. 
    
     - Wenn Sie SharePoint Online-und OneDrive für Unternehmen-Websites Durchsuchen, werden die beiden folgenden Komponenten hinzugefügt:
    
          **Not IsExternalContent: 1** – schließt alle Inhalte einer lokalen SharePoint-Organisation aus. 
    
          **Not IsOneNotePage: 1** – schließt alle OneNote-Dateien aus, da es sich dabei um Duplikate eines Dokuments handeln würde, das mit der Suchabfrage übereinstimmt. 

    
    e. Die Anzahl der inhaltsspeicherorte (angegeben durch die Spalte * * Location Type * *), die Elemente enthalten, die mit der in der **Abfrage** Spalte aufgeführten Suchabfrage übereinstimmen. 
    
    f. Die Anzahl der Elemente (vom angegebenen Inhaltsspeicherort), die der in der **Abfrage** Spalte aufgeführten Suchabfrage entsprechen. Wenn ein Element mehrere Instanzen eines Schlüsselworts enthält, nach dem gesucht wird, wird es wie bereits beschrieben nur einmal in dieser Spalte gezählt. 
    
    g. Die Gesamtgröße aller Elemente, die gefunden wurden (am angegebenen Inhaltsspeicherort), die mit der Suchabfrage in der **Abfrage** Spalte übereinstimmen. 
    
    **Top-Standorte**
    
    Auf dieser Seite werden Statistiken zur Anzahl der Elemente angezeigt, die mit der Suchabfrage in jedem durchsuchten Inhaltsspeicherort übereinstimmen. Es werden die ersten 1.000 Speicherorte angezeigt. Wenn Sie Statistiken für mehrere Suchvorgänge anzeigen, werden die oberen 1.000 Speicherorte für jede Suche angezeigt. Beachten Sie, dass ein Inhaltsspeicherort auf dieser Seite nicht enthalten ist, wenn er keine Elemente enthält, die mit der Suchabfrage übereinstimmen.
    
    ![Statistiken zur Anzahl der Elemente, die in den durchsuchten Inhaltsspeicherorten gefunden wurden](../media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    a. Der Name des Inhaltsspeicherorts.
    
    b. Der Typ des Inhaltsspeicherorts, auf den die Standort Statistik angewendet werden soll.
    
    c. Für jede Suche gibt es Spalten, für die Sie Statistiken anzeigen. In dieser Spalte wird die Anzahl (und Gesamtgröße) der Elemente angezeigt, die mit der Suchabfrage in jedem Inhaltsspeicherort übereinstimmen. Beachten Sie, dass bei der Anzeige von Statistiken für mehrere Suchvorgänge die "na" in dieser Spalte angibt, dass der Inhaltsspeicherort nicht in dieser Suche enthalten war. 

## <a name="get-keyword-statistics-for-content-searches"></a>Abrufen von Schlüsselwort Statistiken für Inhalts suchen

Wie zuvor erläutert, zeigt die Seite **Abfragen** die Suchabfrage und die Anzahl (und Größe) der Elemente an, die mit der Abfrage übereinstimmen. Wenn Sie beim Erstellen oder Bearbeiten einer Suchabfrage eine Stichwortliste verwenden, erhalten Sie Erweiterte Statistiken, die zeigen, wie viele Elemente mit jedem Stichwort oder stichwortausdruck übereinstimmen. Auf diese Weise können Sie schnell erkennen, welche Teile der Abfrage am häufigsten (und am wenigsten) effektiv sind. Wenn ein Schlüsselwort beispielsweise eine große Anzahl von Elementen zurückgibt, können Sie die Stichwortabfrage verfeinern, um die Suchergebnisse einzuschränken. Sie können eine Stichwortliste einrichten, wenn Sie eine Inhaltssuche erstellen oder bearbeiten. 


So erstellen Sie eine Stichwortliste und zeigen Schlüsselwort Statistiken für eine Inhaltssuche an:
  
1. Wechseln Sie im Security & Compliance Center zu **Such** \> **Inhaltssuche**.
    
2. Klicken Sie in der Liste der Inhalts suchen auf und eine Suche, und klicken **** ![Sie dann auf](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)Bearbeitungssymbol bearbeiten.
    
3. Klicken Sie auf **Abfrage** , und führen Sie dann die folgenden Schritte aus: 
    
    ![Klicken Sie auf das Kontrollkästchen Schlüsselwortliste anzeigen, und geben Sie in jeder Zeile ein Schlüsselwort ein.](../media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    a. Aktivieren Sie das Kontrollkästchen **Schlüsselwort Liste anzeigen** . 
    
    b. Geben Sie in der Stichwörter-Tabelle ein Schlüsselwort oder eine Stichwort Phase in eine Zeile ein. Geben Sie beispielsweise **Budget** in die erste Zeile ein, und geben Sie dann **Sicherheit** in der zweiten Zeile ein. 
    
4. Nachdem Sie die Schlüsselwörter hinzugefügt haben, für die Sie die Suche ausführen und Statistiken erhalten möchten, klicken Sie auf **Suchen** , um die überarbeitete Suche auszuführen. 
    
5. Wenn die Suche abgeschlossen ist, wählen Sie Sie in der Liste der Suchvorgänge aus, **** ![und klicken Sie dann auf](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png)Statistik Suchstatistik-Schaltfläche Suchen. Sie können auch Keyword-Statistiken für mehrere Suchvorgänge anzeigen und vergleichen.
    
6. Klicken Sie auf der Seite **Suchstatistik** auf **Abfrage** , um die schlüsselwortstatistik für die ausgewählten Suchvorgänge anzuzeigen. 
    
    ![Die Statistik für jedes Keyword für die ausgewählten suchen wird angezeigt.](../media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    Wie im vorherigen Screenshot gezeigt, werden die Statistiken für jedes Keyword angezeigt; Dies umfasst Folgendes: 
    
    - Die schlüsselwortstatistik für jede Art von Inhaltsspeicherort, die in der Suche enthalten ist.
    
    - Die tatsächliche Suchabfrage für jedes Schlüsselwort, die alle Bedingungen aus der Suchabfrage enthält. 
    
    - Die gesamte Suchabfrage (als **primär** in der Spalte **Part** identifiziert) und die Statistik für die vollständige Abfrage. Hinweis Dies sind die gleichen Statistiken, die auf der **Zusammenfassungs** Seite angezeigt werden. 

> [!NOTE]
> Um Probleme aufgrund großer Stichwortlisten zu verringern, sind Sie jetzt auf maximal 20 Zeilen in der Stichwortliste einer Suchabfrage eingeschränkt.
