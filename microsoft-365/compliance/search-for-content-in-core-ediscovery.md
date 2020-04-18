---
title: Suchen nach Inhalten in einem zentralen eDiscovery-Fall
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Sie können nach Inhalten suchen, die möglicherweise für einen zentralen eDiscovery-Fall relevant sind.
ms.openlocfilehash: b8aa090094dc2699ee774a9b662da17fefde1188
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551451"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a>Suchen nach Inhalten in einem zentralen eDiscovery-Fall

Nachdem ein zentraler eDiscovery-Fall erstellt wurde und Personen mit Interesse im Fall in der Warteschleife gespeichert wurden, können Sie eine oder mehrere Suchen nach Inhalten erstellen und ausführen, die für den Fall relevant sind. Suchvorgänge im Zusammenhang mit einem zentralen eDiscovery-Fall werden nicht auf der Seite **Inhaltssuche** im Microsoft 365 Compliance Center aufgeführt. Diese Suchvorgänge werden auf der Seite **Suchvorgänge** im Kern eDiscover-Fall aufgeführt, dem die Suchvorgänge zugeordnet sind. Dies bedeutet auch, dass Suchvorgängen, die einem Fall zugeordnet sind, nur von Fall Mitgliedern zugegriffen werden kann.

So erstellen Sie eine zentrale eDiscovery-Suche:
  
1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und melden Sie sich mit den Anmeldeinformationen für das Benutzerkonto an, dem die entsprechenden eDiscovery-Berechtigungen zugewiesen wurden.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Center auf **Alle anzeigen**, und klicken Sie dann auf **eDiscovery > Kern**.

3. Wählen Sie auf der **zentralen eDiscovery** -Seite den Fall aus, dass Sie eine zugeordnete Suche erstellen möchten, und klicken Sie dann auf **Groß-/Kleinschreibung öffnen**.

4. Klicken Sie auf der **Start** Seite für den Fall auf die Registerkarte **Suchen** .
  
5. Klicken Sie auf der Seite **Suchen** auf **neue Suche**.

6. Auf der Seite **Neue Suche** können Sie Schlüsselwörter und Bedingungen zum Erstellen der Suchabfrage hinzufügen. 

    ![Neue Suche](../media/0e9954e7-c0ea-4e05-820b-e4b81dc5f81d.png)
  
   a. Sie können Schlüsselwörter, Nachrichteneigenschaften wie gesendete und empfangene Datumsangaben oder Dokumenteigenschaften angeben, beispielsweise Dateinamen oder das Datum, an dem ein Dokument zuletzt geändert wurde. Sie können komplexere Abfragen verwenden, die einen booleschen Operator verwenden, beispielsweise **and**, **or**, **Not**, **near**oder **ONEAR**. Sie können auch nach vertraulichen Informationen (z. B. Sozialversicherungsnummern) in Dokumenten oder nach Dokumenten suchen, die extern freigegeben wurden. Wenn Sie das Feld Schlüsselwort leer lassen, werden alle Inhalte, die sich an den angegebenen Inhaltsspeicherorten befinden, in die Suchergebnisse eingeschlossen.

   b. Sie können auf das Kontrollkästchen **Schlüsselwortliste anzeigen** und in jede Zeile ein Stichwort eingeben. Wenn Sie dies tun, werden die Schlüsselwörter für jede Zeile durch den **or** -Operator in der erstellten Suchabfrage miteinander verbunden. Sie können maximal 20 Stichwörter für die Liste eingeben.

    ![Stichwortliste](../media/29cceb5d-2817-4fc4-b91a-ced1c5824a17.png)
  
    Gründe für die Verwendung der Schlüsselwortliste Sie können Statistiken abrufen, die zeigen, wie viele Elemente den einzelnen Schlüsselwörtern entsprechen. Dadurch können Sie schnell erkennen, welche Schlüsselwörter am effektivsten (und am wenigsten effektiv) sind. Sie können auch einen (in Klammern eingeschlossenen) Schlüsselwortausdruck in einer Zeile verwenden. Weitere Informationen zu Suchstatistiken finden Sie unter [Anzeigen der Schlüsselwortstatistik für Inhaltssuchergebnisse](view-keyword-statistics-for-content-search.md).

    Weitere Informationen zur Verwendung der Liste Stichwörter finden Sie unter [Erstellen einer Suchabfrage](content-search.md#building-a-search-query).

   c. Sie können auf **Bedingungen** klicken und einer Suchabfrage Bedingungen hinzufügen, um eine Suche einzuschränken und eine verfeinerte Ergebnisgruppe zurückzugeben. Jede Bedingung fügt eine Klausel zu der KQL-Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird. Eine Bedingung ist durch **AND**-Operator logisch mit der (im Schlüsselwortfeld angegebenen) Schlüsselwortabfrage verbunden. Das bedeutet, dass Elemente sowohl die Keyword-Abfrage als auch jede Bedingung erfüllen müssen, um in die Ergebnisse einbezogen zu werden. Auf diese Weise können die Suchergebnisse mithilfe von Bedingungen weiter eingegrenzt werden.

    Weitere Informationen zum Erstellen einer Suchabfrage sowie zur Verwendung von Bedingungen finden Sie unter [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).

7. Wählen Sie unter **Standorte: Aufbewahrungsorte**die inhaltsspeicherorte aus, die Sie durchsuchen möchten. Sie können Postfächer, Websites und öffentliche Ordner in derselben Suche durchsuchen.

    ![Speicherorte, Aufbewahrungsorte](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)
  
    - **Alle Standorte**. Wählen Sie diese Option aus, um alle inhaltsspeicherorte in Ihrer Organisation zu durchsuchen. Wenn Sie diese Option auswählen, können Sie auswählen, dass alle Exchange-Postfächer durchsucht werden sollen (einschließlich der Postfächer für alle Microsoft Teams, Jammer Gruppen und Office 365 Gruppen), alle SharePoint-und OneDrive für Unternehmen-Websites (einschließlich der Websites für alle Microsoft Teams, Jammer Gruppen und Office 365 Gruppen) sowie aller öffentlichen Ordner.
    
    - **Alle Aufbewahrungsorte**. Wählen Sie diese Option aus, um alle inhaltsspeicherorte zu durchsuchen, die in der Anfrage für eDiscovery gespeichert wurden. Wenn die Groß-/Kleinschreibung mehrere Haltestatus enthält, werden die inhaltsspeicherorte aus allen Haltebereichen durchsucht. Wenn ein Inhaltsspeicherort in einem abfragebasierten Speicherplatz gefunden wurde, werden beim Ausführen der Inhaltssuche, die Sie in diesem Schritt erstellen, nur die Elemente durchsucht, die in der Warteschleife gespeichert sind. Wenn beispielsweise ein Benutzer auf Abfrage basiertem Case Hold gesetzt wurde, der Elemente aufrecht erhält, die vor einem bestimmten Datum gesendet oder erstellt wurden, werden nur diese Elemente durchsucht. Dies wird erreicht, indem die Case Hold-Abfrage und die Inhalts Suchabfrage durch einen **and-** Operator verbunden werden. Weitere Informationen finden Sie unter [Suchorte in eDiscovery Hold](create-ediscovery-holds.md#search-locations-on-ediscovery-hold).
    
    - **Bestimmte Standorte**. Wählen Sie diese Option aus, um die Postfächer und Websites auszuwählen, die Sie durchsuchen möchten. Wenn Sie diese Option auswählen und auf **ändern**klicken, wird eine Liste der Speicherorte angezeigt. Sie können auswählen, ob Sie einen oder alle Benutzer, Gruppen, Teams oder Website Standorte durchsuchen möchten. Sie können auch die öffentlichen Ordner in Ihrer Organisation durchsuchen.
    
      ![Auswählen bestimmter Standorte](../media/97469b15-7be1-4aee-be27-f8343636152c.png)
  
     Wenn Sie diese Option auswählen und einen beliebigen Inhaltsspeicherort durchsuchen, wird keine Abfrage von einem abfragebasierten Aufbewahrungs Fall auf die Suchabfrage angewendet. In anderen Worten wird der gesamte Inhalt durchsucht, und nicht nur der Inhalt, der von einem abfragebasierten Aufbewahrungsplatz beibehalten wird.

8. Nachdem Sie die zu durchsuchenden inhaltsspeicherorte ausgewählt haben, klicken Sie auf **Fertig** und dann auf **Speichern**.

9. Klicken Sie auf der Seite **neue Suche** auf **& ausführen speichern** , und geben Sie dann einen Namen für die Suche ein. Suchvorgänge im Zusammenhang mit einem zentralen eDiscovery-Fall müssen Namen enthalten, die innerhalb Ihrer Office 365 Organisation eindeutig sind.

10. Klicken Sie auf **Speichern** , um die Sucheinstellungen zu speichern und die Suche zu starten.

  Wenn die Suche abgeschlossen ist, können Sie eine Vorschau der Suchergebnisse anzeigen. Klicken Sie bei Bedarf auf der Seite **Suchvorgänge** auf **Aktualisieren** , um die in der Liste erstellte Suche anzuzeigen.

11. Klicken Sie auf die Suche, um die Flyout-Seite anzuzeigen, die Statistiken zur Suche enthält, und um andere Aufgaben wie das Anzeigen von Suchstatistiken und das Exportieren der Suchergebnisse auszuführen.

## <a name="more-information-about-searching-content-locations"></a>Weitere Informationen zum Durchsuchen von Inhaltsspeicherorten

- Wenn Sie auf **Benutzer, Gruppen oder Teams auswählen** klicken, um die zu durchsuchenden Postfächer anzugeben, ist die angezeigte Post Fachauswahl leer. Dies ist beabsichtigt, um die Leistung zu verbessern. Klicken Sie zum Hinzufügen von Empfängern zu dieser Liste auf **Benutzer, Gruppen oder Teams auswählen**, geben Sie einen Namen (mindestens 3 Zeichen) in das Suchfeld ein, aktivieren Sie das Kontrollkästchen neben dem Namen, und klicken Sie dann auf **auswählen**.

- Sie können inaktive Postfächer, Microsoft Teams, Jammer Gruppen, Office 365 Gruppen und Verteilergruppen zur Liste der zu durchsuchenden Postfächer hinzufügen. Dynamische Verteilergruppen werden nicht unterstützt. Wenn Sie Microsoft Teams, Jammer Gruppen oder Office 365 Gruppen hinzufügen, wird das Gruppen-oder Team Postfach durchsucht. die Postfächer der Gruppenmitglieder werden nicht durchsucht.

- Klicken Sie zum Hinzufügen von Websites auf **Websites auswählen**, dann auf **Websites erneut auswählen** , und geben Sie dann die URL für jede Website ein, die Sie durchsuchen möchten. Sie können auch die URL für die SharePoint-Website für ein Microsoft-Team, eine Jammer Gruppe oder eine Office 365 Gruppe hinzufügen.
