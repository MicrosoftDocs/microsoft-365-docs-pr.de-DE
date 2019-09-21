---
title: Anzeigen der Depot Überwachungsaktivität
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 91123838ec0ab649aca93bfd210b94d5a5cab3f8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082097"
---
# <a name="view-custodian-audit-activity"></a>Anzeigen der Depot Überwachungsaktivität

Sie müssen herausfinden, ob ein Benutzer ein bestimmtes Dokument gesehen oder ein Element aus seinem Postfach gelöscht hat? Advanced eDiscovery ist jetzt in das vorhandene Überwachungsprotokoll-Such Tool im Security #a0 Compliance Center integriert. Mithilfe dieser eingebetteten Oberfläche können Sie das erweiterte eDiscovery Depotbank-Verwaltungstool verwenden, um Ihre Untersuchung durch einfaches zugreifen auf und Durchsuchen der Aktivitäten für Verwalter in Ihrem Fall zu erleichtern.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Sie müssen in Exchange Online die Rolle "nur Ansichts Überwachungsprotokolle" oder "Überwachungsprotokolle" zugewiesen sein, um das Office 365 Überwachungsprotokoll durchsuchen zu können. Diese Rollen werden standardmäßig den Rollengruppen Compliance Management und Organisationsverwaltung auf der Seite Berechtigungen im Exchange Admin Center zugewiesen. Um einem Benutzer die Möglichkeit zu geben, das erweiterte eDiscovery-Überwachungsprotokoll mit der minimalen Berechtigungsstufe zu durchsuchen, können Sie eine benutzerdefinierte Rollengruppe in Exchange Online erstellen, die nur-Ansicht-Überwachungsprotokolle oder die Rolle "Überwachungsprotokolle" hinzufügen und dann den Benutzer als Mitglied der neuen Rollengruppe hinzufügen. Weitere Informationen finden Sie unter Verwalten von Rollengruppen in Exchange Online.

> [!IMPORTANT]
> Wenn Sie einem Benutzer die Rolle "nur Ansichts Überwachungsprotokolle" oder "Überwachungsprotokolle" auf der Seite Berechtigungen im Security #a0 Compliance Center zuweisen, kann er das Office 365 Überwachungsprotokoll nicht durchsuchen. Sie müssen die Berechtigungen in Exchange Online zuweisen. Dies liegt daran, dass das zugrunde liegende Cmdlet, das zum Durchsuchen des Überwachungsprotokolls verwendet wird, ein Exchange Online-Cmdlet ist.

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a>Schritt 1: Durchsuchen des Überwachungsprotokolls nach Aktivitäten, die von einer Depotbank ausgeführt werden

1. Wechseln Sie zu **eDiscovery #a0 Advanced eDiscovery** , und öffnen Sie die Anfrage.
  
2. Klicken Sie auf die Registerkarte **depotverwalter** .
  
3. Wählen Sie in der Liste eine Depotbank aus, und klicken Sie dann auf der Flyout-Seite auf **Depot Aktivität anzeigen** .

    Die Seite Depot Aktivitätssuche wird angezeigt. Hinweis die Depotbank, die Sie im vorherigen Schritt ausgewählt haben, wird im Dropdownfeld **Depot** angezeigt. Sie können im Dropdownfeld unterschiedliche depotverwalter auswählen, aber Sie können jeweils nur nach Aktivitäten für eine Depotbank suchen.

    ![Seite "Depotbank-Aktivitätssuche"](media/AeDCustodianActivities1.png)
   
4. Konfigurieren Sie die folgenden Suchkriterien:
      
   a. **Aktivitäten** – klicken Sie auf die Dropdownliste, um die Aktivitäten anzuzeigen, nach denen Sie suchen können. Nachdem Sie die Suche ausgeführt haben, werden nur die Überwachungseinträge für die ausgewählten Aktivitäten angezeigt. Wenn Sie **Ergebnisse für alle Aktivitäten anzeigen** auswählen, werden die Ergebnisse für alle von der Depotbank ausgeführten Aktivitäten angezeigt, die den anderen Suchkriterien entsprechen.

      ![Liste der Aktivitäten](media/CustodianActivityAudit.PNG)
      
      b. **Start Datum und Enddatum** – wählen Sie einen Datums-und Zeitbereich aus, um die Ereignisse anzuzeigen, die innerhalb dieses Zeitraums aufgetreten sind. Die letzten sieben Tage sind standardmäßig ausgewählt. Das Datum und die Uhrzeit werden im UTC-Format (Coordinated Universal Time) angezeigt. Der maximale Datumsbereich, den Sie angeben können, ist ein Jahr.
      
      c. **Depotverwalter** – klicken Sie in dieses Feld, und wählen Sie dann eine bestimmte Depotbank aus, für die Suchergebnisse angezeigt werden sollen. Überwachungsdatensätze für die ausgewählte Aktivität, die von den Benutzern ausgeführt werden, die Sie in diesem Feld ausgewählt haben, werden in der Ergebnisliste angezeigt.
      
   5. Click   ![Schaltfläche "suchen"](media/SearchButton.PNG)  , um die Suche mit Ihren Suchkriterien auszuführen. Die Suchergebnisse werden geladen, und nach einigen Momenten werden Sie unter Ergebnisse auf der Suchseite "Depotbank-Aktivitäten" angezeigt. 

## <a name="step-2-view-the-audit-log-search-results"></a>Schritt 2: Anzeigen der Suchergebnisse des Überwachungsprotokolls

Die Ergebnisse einer Überwachungsprotokoll Suche werden unter Ergebnisse auf der Seite Depot Überwachungsprotokoll angezeigt. Es werden maximal 5.000 (neueste) Ereignisse in Schritten von 150 Ereignissen angezeigt. Um weitere Ereignisse anzuzeigen, können Sie die Bildlaufleiste im Ergebnisbereich verwenden, oder Sie können Umschalt + Ende drücken, um die nächsten 150-Ereignisse anzuzeigen.

Die Ergebnisse enthalten die folgenden Informationen zu jedem Ereignis, das von der Suche zurückgegeben wird.
- **Date**: das Datum und die Uhrzeit (im UTC-Format), als das Ereignis aufgetreten ist.

- **IP-Adresse**: die IP-Adresse des Geräts, das verwendet wurde, als die Aktivität protokolliert wurde. Die IP-Adresse wird im Adressformat IPv4 oder IPv6 angezeigt.

- **User**: der Benutzer (oder das Dienstkonto), der die Aktion ausgeführt hat, die das Ereignis ausgelöst hat.

- **Activity**: die vom Benutzer ausgeführte Aktivität. Dieser Wert entspricht den Aktivitäten, die Sie in der Dropdownliste Aktivitäten ausgewählt haben. Bei einem Ereignis aus dem Exchange-administratorüberwachungsprotokoll handelt es sich bei dem Wert in dieser Spalte um ein Exchange-Cmdlet.

- **Item**: das Objekt, das als Ergebnis der entsprechenden Aktivität erstellt oder geändert wurde. Beispielsweise die Datei, die angezeigt oder geändert wurde, oder das Benutzerkonto, das aktualisiert wurde. Nicht alle Aktivitäten haben einen Wert in dieser Spalte.

- **Detail**: Weitere Details zu einer Aktivität. Auch hier haben nicht alle Aktivitäten einen Wert.

## <a name="step-3-filter-the-search-results"></a>Schritt 3: Filtern der Suchergebnisse

Neben der Sortierung können Sie auch die Ergebnisse einer Überwachungsprotokoll Suche filtern. Dies kann Ihnen helfen, die Ergebnisse für einen bestimmten Benutzer oder eine bestimmte Aktivität schnell zu filtern. 

So filtern Sie die Ergebnisse:

 1. Erstellen Sie eine Überwachungsprotokoll Suche, und führen Sie Sie aus.
  
2. Wenn die Ergebnisse angezeigt werden, klicken Sie auf **Filter Ergebnisse**.
 
3. Stichwort Felder werden unter jeder Spaltenüberschrift angezeigt.
  
4. Klicken Sie auf eines der Felder unter einer Spaltenüberschrift, und geben Sie je nach der Spalte, nach der Sie filtern, ein Wort oder einen Ausdruck ein. Die Ergebnisse werden dynamisch angepasst, um die Ereignisse anzuzeigen, die mit Ihrem Filter übereinstimmen.
  
5. Wenn Sie einen Filter löschen möchten, klicken Sie im Feld Filter auf das **X** , oder klicken Sie einfach auf **Filter ausblenden**.

## <a name="export-the-search-results-to-a-file"></a>Exportieren der Suchergebnisse in eine Datei

Sie können die Ergebnisse einer Überwachungsprotokoll Suche in eine CSV-Datei (Comma Separated Value) auf Ihrem lokalen Computer exportieren. Sie können diese Datei in Microsoft Excel öffnen und Features wie das suchen, sortieren, Filtern und Teilen einer einzelnen Spalte (die mehrwertige Zellen enthält) in mehrere Spalten verwenden.

1. Führen Sie eine Überwachungsprotokoll Suche aus, und überprüfen Sie dann die Suchkriterien, bis Sie die gewünschten Ergebnisse erhalten haben.
  
2. Klicken Sie auf Ergebnisse exportieren, und wählen Sie eine der folgenden Optionen aus:

    - **Geladene Ergebnisse speichern:** Wählen Sie diese Option aus, um nur die Einträge zu exportieren, die unter **Ergebnisse** auf der Suchseite für die **Depotbank-Überwachungsprotokoll-Suche** angezeigt werden. Die heruntergeladene CSV-Datei enthält dieselben Spalten (und Daten), die auf der Seite angezeigt werden (Datum, Benutzer, Aktivität, Element und Details). Eine zusätzliche Spalte (mit dem Titel **more**) ist in der CSV-Datei enthalten, die weitere Informationen aus dem Überwachungsprotokolleintrag enthält. Da Sie dieselben Ergebnisse exportieren, die auf der Seite Überwachungsprotokoll Suche geladen (und sichtbar) werden, werden maximal 5.000 Einträge exportiert.
        
    - **Alle Ergebnisse herunterladen:** Wählen Sie diese Option aus, um alle Einträge aus dem Office 365 Überwachungsprotokoll zu exportieren, die die Suchkriterien erfüllen. Für eine große Gruppe von Suchergebnissen wählen Sie diese Option aus, um alle Einträge aus dem Überwachungsprotokoll herunterzuladen, zusätzlich zu den 5.000-Ergebnissen, die auf der Suchseite der **Depot Überwachungsprotokoll** -Suche angezeigt werden können. Mit dieser Option werden die Rohdaten aus dem Überwachungsprotokoll in eine CSV-Datei heruntergeladen, und es werden zusätzliche Informationen aus dem Überwachungsprotokolleintrag in einer Spalte namens Auditdata. Das Herunterladen der Datei kann länger dauern, wenn Sie diese Exportoption auswählen, da die Datei viel größer sein kann als diejenige, die heruntergeladen wurde, wenn Sie die Option andere auswählen.
    
      > [!IMPORTANT]
      > Sie können maximal 50.000 Einträge aus einer einzigen Überwachungsprotokoll Suche in eine CSV-Datei herunterladen. Wenn 50.000-Einträge in die CSV-Datei heruntergeladen werden, können Sie wahrscheinlich davon ausgehen, dass es mehr als 50.000 Ereignisse gibt, die die Suchkriterien erfüllt haben. Um mehr als diesen Grenzwert zu exportieren, verwenden Sie einen Datumsbereich, um die Anzahl der Überwachungsprotokolleinträge zu verringern. Möglicherweise müssen Sie mehrere Suchvorgänge mit kleineren Datumsbereichen ausführen, um mehr als 50.000 Einträge zu exportieren.
        

3. Nachdem Sie eine Exportoption ausgewählt haben, wird am unteren Rand des Fensters eine Meldung angezeigt, in der Sie aufgefordert werden, die CSV-Datei zu öffnen, Sie im Ordner "Downloads" zu speichern oder in einem bestimmten Ordner zu speichern.

Weitere Informationen zum Anzeigen, Filtern oder Exportieren von Überwachungsprotokoll-Suchergebnissen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security #a0 Compliance Center](search-the-audit-log-in-security-and-compliance.md).
