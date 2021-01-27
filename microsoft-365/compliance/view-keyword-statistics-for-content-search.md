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
ms.openlocfilehash: f7faf956aaec5619655818036b969086e0af0c6a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49987830"
---
# <a name="view-keyword-statistics-for-content-search-results"></a>Anzeigen der Schlüsselwortstatistik für Inhaltssuchergebnisse

Nachdem Sie eine Inhaltssuche erstellt und ausgeführt haben, können Sie Statistiken zu den geschätzten Suchergebnissen anzeigen. Dies umfasst eine Zusammenfassung der Suchergebnisse (ähnlich der Zusammenfassung der geschätzten Suchergebnisse, die im Detailbereich angezeigt werden), die Abfragestatistiken, z. B. die Anzahl der Inhaltsorte mit Elementen, die der Suchabfrage entsprechen, und den Namen der Inhaltsorte, die die am besten übereinstimmenden Elemente enthalten. Sie können Statistiken für eine oder mehrere Inhaltssuchen anzeigen. Auf diese Weise können Sie die Ergebnisse für mehrere Suchen schnell vergleichen und Entscheidungen zur Effektivität Ihrer Suchabfragen treffen.
  
Darüber hinaus können Sie neue und vorhandene Suchabfragen so konfigurieren, dass Statistiken für jedes Schlüsselwort in einer Suchabfrage zurückgegeben werden. Auf diese Weise können Sie die Anzahl der Ergebnisse für jedes Schlüsselwort in einer Abfrage vergleichen und die Schlüsselwortstatistik aus mehreren Suchen vergleichen.
  
Sie können auch die Such- und Schlüsselwortstatistik in einer CSV-Datei herunterladen. Auf diese Weise können Sie die Filter- und Sortierfunktionen in Excel dazu verwenden, um Ergebnisse zu vergleichen und Berichte für Ihre Suchergebnisse vorzubereiten.
  
## <a name="get-statistics-for-content-searches"></a>Statistiken für Inhaltssuchen erhalten

So zeigen Sie Statistiken für Inhaltssuchen an:
  
1. Wechseln Sie im Microsoft 365 Compliance Center zu **"Alle**  >  **Inhaltssuche anzeigen".**

2. Wählen Sie in der Liste der Suchen mindestens zwei  Suchen aus,  und klicken Sie dann auf der Flyoutseite für Massenaktionen auf Suchstatistiken.
    
    ![Wählen Sie mehrere Suchen aus, und klicken Sie dann auf "Suchstatistik"](../media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. Klicken Sie **auf der Seite** Suchstatistiken auf einen der folgenden Links, um Statistiken zu den ausgewählten Suchen anzeigen zu können. 
    
    **Zusammenfassung**
    
    Auf dieser Seite werden Statistiken angezeigt, die den im Detailbereich auf der Seite "Inhaltssuche" **angezeigten Statistiken** ähneln. Es werden Statistiken für alle ausgewählten Suchen angezeigt. Beachten Sie, dass Sie die ausgewählten Suchen auf dieser Seite auch erneut ausführen können, um die Statistik zu aktualisieren. 
    
    ![Zusammenfassung der Statistiken für die ausgewählten Suchen](../media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    a.  Der Name der Inhaltssuche. Wie bereits erwähnt, können Sie Statistiken für mehrere Suchen anzeigen und vergleichen.
    
    b. Der Typ des Inhaltsspeicherorts, der durchsucht wurde. In jeder Zeile werden Statistiken für Postfächer, Websites und öffentliche Ordner aus der angegebenen Suche angezeigt.
    
    c. Die Anzahl der Inhaltsorte, die Elemente enthalten, die der Suchabfrage entsprechen. Bei Postfächern enthält diese Statistik auch die Anzahl der Archivpostfächer, die Elemente enthalten, die mit der Suchabfrage übereinstimmen.
    
    d. Die Gesamtzahl der Elemente aller angegebenen Inhaltsorte, die der Suchabfrage entsprechen. Beispiele für Elementtypen sind E-Mail-Nachrichten, Kalenderelemente und Dokumente. Wenn ein Element mehrere Instanzen eines Schlüsselworts enthält, nach dem gesucht wird, wird es nur einmal in der Gesamtzahl der Elemente gezählt. Wenn Sie beispielsweise nach den Wörtern "stock" oder "fraud" suchen und eine E-Mail-Nachricht drei Instanzen des  Worts "stock" enthält, wird sie nur einmal in der Spalte "Elemente" gezählt. 
    
    e. Die Gesamtgröße aller Elemente, die am angegebenen Inhaltsspeicherort gefunden wurden, die der Suchabfrage entsprechen. 
    
    **Abfragen**
    
    Auf dieser Seite werden Statistiken zur Suchabfrage angezeigt.
    
    ![Suchabfragestatistiken für die ausgewählten Suchen](../media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    a. Der Name der Inhaltssuche, für die die Zeile Abfragestatistiken enthält.
    
    b. Der Typ des Inhaltsspeicherorts, auf den die Abfragestatistiken anwendbar sind.
    
    c. Diese Spalte gibt an, auf welchen Teil der Suchabfrage die Statistiken anwendbar sind. **"Primär"** gibt die gesamte Suchabfrage an. Wenn Sie beim Erstellen oder Bearbeiten einer Suchabfrage eine Stichwortliste verwenden, sind Statistiken für jede Komponente der Abfrage in dieser Tabelle enthalten. Weitere Informationen finden Sie im Abschnitt "Get [keyword statistics for Content Searches"](#get-keyword-statistics-for-content-searches) in diesem Artikel. 
    
    d. Diese Spalte enthält die tatsächliche Suchabfrage, die vom Tool für die Inhaltssuche ausgeführt wird. Beachten Sie, dass das Tool der von Ihnen erstellten Abfrage automatisch einige zusätzliche Komponenten hinzufügt. 

    - Wenn Sie nach allen Inhalten in Postfächern suchen (ohne Schlüsselwörter anzugeben), ist die tatsächliche Schlüsselwortabfrage so, dass alle Elemente  `size>=0` zurückgegeben werden. 
    
     - Wenn Sie SharePoint Online- und OneDrive for #A0 durchsuchen, werden die beiden folgenden Komponenten hinzugefügt:
    
          **NOT IsExternalContent:1** – Schließt alle Inhalte aus einer lokalen SharePoint-Organisation aus. 
    
          **NOT IsOneNotePage:1** – Schließt alle OneNote-Dateien aus, da es sich dabei um Duplikate aller Dokumente handelt, die der Suchabfrage entsprechen. 

    
    e. Die Anzahl der Inhaltsspeicherorte (angegeben durch die Spalte ** Speicherorttyp ** ), die Elemente enthalten, die der in der Abfragespalte aufgelisteten **Suchabfrage** entsprechen. 
    
    f. Die Anzahl der Elemente (vom angegebenen Inhaltsspeicherort), die der in der Spalte **"Abfrage"** aufgelisteten Suchabfrage entsprechen. Wie bereits erläutert, wird ein Element nur einmal in dieser Spalte gezählt, wenn es mehrere Instanzen eines Schlüsselworts enthält, nach dem gesucht wird. 
    
    g. Die Gesamtgröße aller Elemente, die (am angegebenen Inhaltsspeicherort) gefunden wurden, die der Suchabfrage in der Spalte **"Abfrage"** entsprechen. 
    
    **Die am besten verteilten Speicherorte**
    
    Auf dieser Seite werden Statistiken zur Anzahl der Elemente angezeigt, die der Suchabfrage an jedem durchsuchten Inhaltsspeicherort entsprechen. Es werden die ersten 1.000 Speicherorte angezeigt. Wenn Sie Statistiken für mehrere Suchen anzeigen, werden die 1.000 am besten 1.000 Speicherorte für jede Suche angezeigt. Beachten Sie, dass ein Inhaltsspeicherort auf dieser Seite nicht enthalten ist, wenn er keine Elemente enthält, die mit der Suchabfrage übereinstimmen.
    
    ![Statistiken zur Anzahl der in den durchsuchten Inhaltsstandorten gefundenen Elemente](../media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    a. Der Name des Inhaltsspeicherorts.
    
    b. Der Typ des Inhaltsspeicherorts, für den die Standortstatistik gilt.
    
    c. Es gibt Spalten für jede Suche, für die Sie Statistiken anzeigen. In dieser Spalte wird die Anzahl (und Gesamtgröße) der Elemente angezeigt, die der Suchabfrage an jedem Inhaltsspeicherort entsprechen. Beachten Sie, dass beim Anzeigen von Statistiken für mehrere Suchen die "NA" in dieser Spalte angibt, dass der Inhaltsspeicherort nicht in diese Suche einbezogen wurde. 

## <a name="get-keyword-statistics-for-content-searches"></a>Schlüsselwortstatistik für Inhaltssuchen erhalten

Wie bereits erläutert, werden auf der Seite "Abfragen" die Suchabfrage und die Anzahl (und Größe) der Elemente angezeigt, die mit der Abfrage übereinstimmen.  Wenn Sie beim Erstellen oder Bearbeiten einer Suchabfrage eine Stichwortliste verwenden, erhalten Sie erweiterte Statistiken, die zeigen, wie viele Elemente mit jedem Stichwort oder Stichwortbegriff übereinstimmen. Auf diese Weise können Sie schnell erkennen, welche Teile der Abfrage am effektivsten (und am wenigsten effektiv) sind. Wenn ein Schlüsselwort beispielsweise eine große Anzahl von Elementen zurückgibt, können Sie die Stichwortabfrage verfeinern, um die Suchergebnisse einengt. Sie können eine Stichwortliste einrichten, wenn Sie eine Inhaltssuche erstellen oder bearbeiten. 

So erstellen Sie eine Stichwortliste und zeigen Schlüsselwortstatistiken für eine Inhaltssuche an:
  
1. Wechseln Sie im Microsoft 365 Compliance Center zu **"Alle**  >  **Inhaltssuche anzeigen".**
    
2. Klicken Sie in der Liste der Inhaltssuchen auf eine Suche, und klicken Sie dann auf **das** Symbol ![ "Bearbeiten". ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)
    
3. Klicken **Sie auf** "Abfrage", und gehen Sie dann wie folgt vor: 
    
    ![Klicken Sie auf das Kontrollkästchen "Schlüsselwortliste anzeigen", und geben Sie in jeder Zeile ein Schlüsselwort ein.](../media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    a. Klicken Sie auf das **Kontrollkästchen Schlüsselwortliste** anzeigen. 
    
    b. Geben Sie ein Schlüsselwort oder eine Schlüsselwortphase in eine Zeile in der Schlüsselworttabelle ein. Geben Sie beispielsweise **in der ersten** Zeile das Budget ein, und geben Sie dann in der zweiten Zeile die Sicherheit ein.  
    
4. Nachdem Sie die Schlüsselwörter hinzugefügt haben, nach  deren Statistiken Sie suchen möchten, klicken Sie auf "Suchen", um die überarbeitete Suche ausführen zu können. 
    
5. Wenn die Suche abgeschlossen ist, wählen Sie sie in der Liste der Suchen aus, und klicken Sie dann auf die Schaltfläche **Suchstatistik** ![ Suchstatistik ](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png) . Sie können auch Schlüsselwortstatistiken für mehrere Suchen anzeigen und vergleichen.
    
6. Klicken Sie **auf der Seite Suchstatistiken** **auf** "Abfrage", um die Schlüsselwortstatistik für die ausgewählten Suchabfragen anzeigen zu können. 
    
    ![Die Statistiken für jedes Schlüsselwort für die ausgewählten Suchen werden angezeigt.](../media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    Wie im vorherigen Screenshot gezeigt, werden die Statistiken für jedes Schlüsselwort angezeigt. Dies umfasst: 
    
    - Die Schlüsselwortstatistik für jeden Inhaltsspeicherorttyp, der in der Suche enthalten ist.
    
    - Die tatsächliche Suchabfrage für jedes Schlüsselwort, die alle Bedingungen aus der Suchabfrage enthält. 
    
    - Die vollständige Suchabfrage  (in der Spalte **"Teil"** als "Primär" identifiziert) und die Statistik für die vollständige Abfrage. Beachten Sie, dass es sich um dieselben Statistiken handelt, die auf der Seite **"Zusammenfassung" angezeigt** werden. 

> [!NOTE]
> Um Probleme zu reduzieren, die durch umfangreiche Stichwortlisten verursacht werden, sind Sie jetzt auf maximal 20 Zeilen in der Schlüsselwortliste einer Suchabfrage beschränkt.
