---
title: Anzeigen der Überwachungsaktivität von Personen von Interesse
f1.keywords:
- NOCSH
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
ms.openlocfilehash: eac58e10e97b639a296717210f7a9576abef5e35
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597242"
---
# <a name="view-the-audit-activity-of-people-of-interest"></a>Anzeigen der Überwachungsaktivität von Personen von Interesse

Wollen Sie herausfinden, ob ein Benutzer ein bestimmtes Dokument angezeigt oder ein Element aus seinem Postfach gelöscht hat? Data Investigations (Preview) ist jetzt in das vorhandene Überwachungsprotokoll-Such Tool im Security #a0 Compliance Center integriert. Mithilfe dieser eingebetteten Benutzeroberfläche können Sie das Verwaltungstool "Daten Ermittlungen (Preview) People of Interest" verwenden, um Ihre Untersuchung zu vereinfachen, indem Sie die Aktivität für Personen, die in ihrer Untersuchung interessant sind, leicht aufrufen und durchsuchen.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Ihnen wurde in Exchange Online eine entweder die Rolle „Überwachungsprotokolle nur anzeigen“ oder „Überwachungsprotokolle“ zugewiesen, um das Office 365-Überwachungsprotokoll zu durchsuchen. Standardmäßig sind diese Rollen im Exchange Admin Center zugewiesen den Rollengruppen „Complianceverwaltung“ und „Organisationsverwaltung“ auf der Seite Berechtigungen. Um einem Benutzer die Möglichkeit zu geben, das Überwachungsprotokoll mit den Mindestberechtigungen zu durchsuchen, können Sie eine benutzerdefinierte Rollengruppe in Exchange Online erstellen, die Ansichts Überwachungsprotokolle oder die Rolle "Überwachungsprotokolle" hinzufügen und dann den Benutzer als Mitglied der neuen Rolle "GR" hinzufügen. OUP. Weitere Informationen finden Sie unter Verwalten von Rollengruppen in Exchange Online.

> [!IMPORTANT]
> Wenn Sie einem Benutzer die Rolle "nur Ansichts Überwachungsprotokolle" oder "Überwachungsprotokolle" auf der Seite Berechtigungen im Security #a0 Compliance Center zuweisen, kann er das Office 365 Überwachungsprotokoll nicht durchsuchen. Sie müssen die Berechtigungen in Exchange Online zuweisen. Der Grund dafür ist, dass es sich bei dem zugrundeliegenden Cmdlet, das für die Durchsuchung des Überwachungsprotokolls verwendet wird, um ein Exchange Online-Cmdlet handelt.

## <a name="step-1-create-an-data-investigations-preview-audit-log-search"></a>Schritt 1: Erstellen einer Daten Untersuchung (Vorschau)-Überwachungsprotokoll Suche

   1. Wählen Sie eine vorhandene Untersuchung im **Security #a0 Compliance Center #a1 Data Investigations (Preview)** aus.
   
   2. Navigieren Sie zur Registerkarte **interessante Personen** , und wählen Sie eine Person aus.
   
   3. Nachdem Sie eine Person ausgewählt haben, klicken Sie im Bereich Details auf **Aktivität anzeigen** .
   
   4. Konfigurieren Sie die folgenden Suchkriterien: 
      
      a. **Aktivitäten** – klicken Sie auf die Dropdownliste, um die Aktivitäten anzuzeigen, nach denen Sie suchen können. Nachdem Sie die Suche ausgeführt haben, werden nur die Überwachungseinträge für die ausgewählten Aktivitäten angezeigt. Wenn Sie **Ergebnisse für alle Aktivitäten anzeigen** auswählen, werden die Ergebnisse für alle Aktivitäten angezeigt, die den anderen Suchkriterien entsprechen.
      
      b. **Start Datum und Enddatum** – wählen Sie einen Datums-und Zeitbereich aus, um die Ereignisse anzuzeigen, die innerhalb dieses Zeitraums aufgetreten sind. Die letzten sieben Tage sind standardmäßig ausgewählt. Das Datum und die Uhrzeit werden im UTC-Format (Coordinated Universal Time) angezeigt. Der maximale Datumsbereich, den Sie angeben können, ist ein Jahr.
      
      c. **Personen mit Interesse** – klicken Sie in dieses Feld, und wählen Sie dann eine bestimmte Depotbank aus, für die Suchergebnisse angezeigt werden sollen. Überwachungsdatensätze für die ausgewählte Aktivität, die von den Benutzern ausgeführt werden, die Sie in diesem Feld ausgewählt haben, werden in der Ergebnisliste angezeigt.
    
    1. Klicken Sie auf **Suchen**, um die Suche anhand der Suchkriterien auszuführen.  Die Suchergebnisse werden geladen, und nach ein paar Augenblicken werden Sie unter Ergebnisse auf der Suchseite für die Aktivitäten der Interessenten-Suche angezeigt. 

## <a name="step-2-view-the-audit-log-search-results"></a>Schritt 2: Anzeigen der Suchergebnisse des Überwachungsprotokolls

Die Ergebnisse einer Überwachungsprotokoll Suche werden unter Ergebnisse auf der Seite Überwachungsprotokoll für Personen mit Interesse angezeigt. Es werden maximal 5.000 (neueste) Ereignisse in Schritten von 150 Ereignissen angezeigt. Zum Anzeigen weiterer Ereignisse können Sie die Bildlaufleiste im Bereich Ergebnisse verwenden oder UMSCHALT+ENDE drücken, um die nächsten 150 Ereignisse anzuzeigen.

Die Ergebnisse enthalten die folgenden Informationen zu jedem Ereignis, das von der Suche zurückgegeben wird.
- **Datum**: Das Datum und die Uhrzeit (im UTC-Format), zu der das Ereignis auftrat.

- **IP-Adresse**: Die IP-Adresse des Geräts, das verwendet wurde, als die Aktivität protokolliert wurde. Die IP-Adresse wird im Adressformat IPv4 oder IPv6 angezeigt.

- **Benutzer**: Der Benutzer (oder das Dienstkonto), der die Aktion ausführte, durch die das Ereignis ausgelöst wurde.

- **Aktivität**: Die vom Benutzer ausgeführte Aktivität. Dieser Wert entspricht den Aktivitäten, die Sie in der Dropdownliste Aktivitäten ausgewählt haben. Bei einem Ereignis aus dem Exchange-Administratorüberwachungsprotokoll ist der Wert in dieser Spalte ein Exchange-Cmdlet.

- **Element**: Das Objekt, das als Ergebnis der entsprechenden Aktivität erstellt oder geändert wurde. Dies kann z. B. die Datei sein, die angezeigt oder geändert wurde, oder das Benutzerkonto, das aktualisiert wurde. Nicht alle Aktivitäten haben in dieser Spalte einen Wert.

- **Detail**: Weitere Details zu einer Aktivität. Auch hier haben nicht alle Aktivitäten einen Wert.

## <a name="step-3-filter-the-search-results"></a>Schritt 3: Filtern der Suchergebnisse

Zusätzlich zur Sortierung können Sie die Ergebnisse einer Überwachungsprotokollsuche auch filtern. Dies kann Ihnen helfen, die Ergebnisse für einen bestimmten Benutzer oder eine bestimmte Aktivität schnell zu filtern. 

So filtern Sie die Ergebnisse:

 1. Erstellen Sie eine Überwachungsprotokoll Suche, und führen Sie Sie aus.
  
2. Sobald die Ergebnisse angezeigt werden, klicken Sie auf **Ergebnisse filtern**.
 
3. Unter den einzelnen Spaltenüberschriften werden Felder für Schlüsselwörter angezeigt.
  
4. Klicken Sie auf eines der Felder unter einer Spaltenüberschrift, und geben Sie abhängig von der Spalte ein Wort oder einen Ausdruck ein, nach dem Sie filtern möchten. Die Ergebnisse werden dynamisch angepasst und die Ereignisse angezeigt, die den Filterkriterien entsprechen.
  
5. Wenn Sie einen Filter löschen möchten, klicken Sie im Feld Filter auf das **X** , oder klicken Sie einfach auf **Filter ausblenden**.

## <a name="export-the-search-results-to-a-file"></a>Exportieren der Suchergebnisse in eine Datei

Sie können die Ergebnisse einer Überwachungsprotokoll Suche in eine CSV-Datei (Comma Separated Value) auf Ihrem lokalen Computer exportieren. Sie können diese Datei in Microsoft Excel öffnen und Features wie das suchen, sortieren, Filtern und Teilen einer einzelnen Spalte (die mehrwertige Zellen enthält) in mehrere Spalten verwenden.

1. Führen Sie eine Überwachungsprotokollsuche aus, und bearbeiten Sie dann die Suchkriterien, bis Sie die gewünschten Ergebnisse erhalten.
  
2. Klicken Sie auf Ergebnisse exportieren, und wählen Sie eine der folgenden Optionen aus:

    - **Geladene Ergebnisse speichern:** Wählen Sie diese Option aus, um nur die Einträge zu exportieren, die unter **Ergebnisse** auf der Suchseite **für die Überwachungsprotokoll Suche für Personen mit Interesse** angezeigt werden. Die heruntergeladene CSV-Datei enthält dieselben Spalten (und Daten), die auch auf der Seite angezeigt werden (Datum, Benutzer, Aktivität, Element und Details). Eine zusätzliche Spalte (mit dem Titel **more**) ist in der CSV-Datei enthalten, die weitere Informationen aus dem Überwachungsprotokolleintrag enthält. Da Sie dieselben Ergebnisse exportieren, die auf der Seite Überwachungsprotokollsuche geladen werden (und angezeigt werden können), werden maximal 5.000 Einträge exportiert.
        
    - **Alle Ergebnisse herunterladen:** Wählen Sie diese Option aus, um alle Einträge aus dem Office 365 Überwachungsprotokoll zu exportieren, die die Suchkriterien erfüllen. Für eine große Gruppe von Suchergebnissen wählen Sie diese Option aus, um alle Einträge aus dem Überwachungsprotokoll zusätzlich zu den 5.000-Ergebnissen herunterzuladen, die auf der Seite **mit der Überwachungsprotokoll Suche für Personen mit Interesse** angezeigt werden können. Mit dieser Option werden die Rohdaten aus dem Überwachungsprotokoll in eine CSV-Datei heruntergeladen, und es werden zusätzliche Informationen aus dem Überwachungsprotokolleintrag in einer Spalte namens Auditdata. Bei Auswahl dieser Exportoption kann das Herunterladen der Datei etwas länger dauern, da die Datei möglicherweise wesentlich größer als diejenige ist, die bei Auswahl einer anderen Option heruntergeladen wird.
    
      > [!IMPORTANT]
      > Aus seiner einzigen Suche in einer Protokolldatei können Sie maximal 50.000 Einträge in eine CSV-Datei herunterladen. Wenn 50.000 Einträge in die CSV-Datei heruntergeladen werden, können Sie wahrscheinlich davon ausgehen, dass mehr als 50.000 Ereignisse die Suchkriterien erfüllen. Wenn Sie mehr als diesen Grenzwert exportieren möchten, versuchen Sie es mit einem Datenbereich, um die Anzahl der Einträge im Überwachungsprotokoll zu verringern. Möglicherweise müssen Sie mehrere Suchläufe mit kleineren Datumsbereichen durchführen, um mehr als 50.000 Einträge zu exportieren.
        

3. Nachdem Sie eine Exportoption ausgewählt haben, wird am unteren Rand des Fensters eine Meldung angezeigt, in der Sie aufgefordert werden, die CSV-Datei zu öffnen, Sie im Ordner "Downloads" zu speichern oder in einem bestimmten Ordner zu speichern.

Weitere Informationen zum Anzeigen, Filtern oder Exportieren von Überwachungsprotokoll-Suchergebnissen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Office 365](search-the-audit-log-in-security-and-compliance.md).