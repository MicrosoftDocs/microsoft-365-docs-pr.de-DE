---
title: Anzeigen der Aktivitäten von Verwaltungsberechtigten für die Überwachung
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
description: Verwenden Sie Advanced eDiscovery Custodian Management-Tool, um auf einfache Weise auf die Aktivitäten in Ihrem Fall zu zugreifen und nach Custodians zu suchen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9e96d0b5dd3bf42dbba56a6e1be91014485ce98
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024765"
---
# <a name="view-custodian-audit-activity"></a>Anzeigen der Aktivitäten von Verwaltungsberechtigten für die Überwachung

Wollen Sie herausfinden, ob ein Benutzer ein bestimmtes Dokument angezeigt oder ein Element aus seinem Postfach gelöscht hat? Advanced eDiscovery ist jetzt in das vorhandene Überwachungsprotokollsuchtool im Security & Compliance Center integriert. Mithilfe dieser eingebetteten Erfahrung können Sie das tool Advanced eDiscovery Custodian Management verwenden, um Ihre Untersuchung zu erleichtern, indem Sie auf einfache Weise auf die Aktivitäten in Ihrem Fall zugreifen und die Aktivitäten nach Verwahrern durchsuchen.

## <a name="get-permissions"></a>Berechtigungen erhalten

Ihnen wurde in Exchange Online eine entweder die Rolle „Überwachungsprotokolle nur anzeigen“ oder „Überwachungsprotokolle“ zugewiesen, um das Überwachungsprotokoll zu durchsuchen. Standardmäßig sind diese Rollen im Exchange Admin Center zugewiesen den Rollengruppen „Complianceverwaltung“ und „Organisationsverwaltung“ auf der Seite Berechtigungen. Damit ein Benutzer die Möglichkeit hat, das Überwachungsprotokoll von Advanced eDiscovery mit minimalen Rechten zu durchsuchen, können Sie in Exchange Online eine benutzerdefinierte Rollengruppe erstellen, ihr die Rollen "Überwachungsprotokolle nur anzeigen" oder "Überwachungsprotokolle" hinzufügen und den Benutzer dann als Mitglied der neuen Rollengruppe hinzufügen. Weitere Informationen finden Sie unter Verwalten von Rollengruppen in Exchange Online.

> [!IMPORTANT]
> Wenn Sie einem Benutzer die Rolle View-Only Überwachungsprotokolle oder Überwachungsprotokolle auf der Seite Berechtigungen im Security & Compliance Center zuweisen, kann er das Überwachungsprotokoll nicht durchsuchen. Sie müssen die Berechtigungen in Exchange Online zuweisen. Der Grund dafür ist, dass es sich bei dem zugrundeliegenden Cmdlet, das für die Durchsuchung des Überwachungsprotokolls verwendet wird, um ein Exchange Online-Cmdlet handelt.

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a>Schritt 1: Durchsuchen des Überwachungsprotokolls nach Aktivitäten eines Verwahrers

1. Wechseln Sie **zu eDiscovery > Advanced eDiscovery,** und öffnen Sie den Fall.
  
2. Klicken Sie auf **die Registerkarte** Quellen.
  
3. Wählen Sie **auf der Seite** Verwahrer in der Liste einen Custodian aus, und klicken Sie dann auf der Flyoutseite auf **Custodian-Aktivität** anzeigen.

    Die Suchseite für Custodian-Aktivitäten wird angezeigt. Beachten Sie, dass der im vorherigen Schritt ausgewählte **Custodian** im Dropdownfeld Verwahrer angezeigt wird. Sie können verschiedene Custodians im Dropdownfeld auswählen, aber Sie können immer nur nach Aktivitäten für einen Custodian suchen.

    ![Suchseite "Aktivitäten von Verwaltungsberechtigten"](../media/AeDCustodianActivities1.png)
   
4. Konfigurieren Sie die folgenden Suchkriterien: 
      
   1. **Aktivitäten** – Klicken Sie auf die Dropdownliste, um die Aktivitäten anzeigen zu können, nach der Sie suchen können. Nachdem Sie die Suche ausgeführt haben, werden nur die Überwachungsdatensätze für die ausgewählten Aktivitäten angezeigt. Wenn **Sie Ergebnisse für alle Aktivitäten anzeigen auswählen,** werden Ergebnisse für alle Aktivitäten angezeigt, die vom Verwahrer ausgeführt werden, die den anderen Suchkriterien entsprechen.

      ![Liste der Aktivitäten](../media/CustodianActivityAudit.PNG)
      
   1. **Startdatum und Enddatum** : Wählen Sie einen Datums- und Uhrzeitbereich aus, um die Ereignisse zu anzeigen, die innerhalb dieses Zeitraums aufgetreten sind. Die letzten sieben Tage sind standardmäßig ausgewählt. Das Datum und die Uhrzeit werden im UTC-Format (Coordinated Universal Time) angezeigt. Der maximale Datumsbereich, den Sie angeben können, ist ein Jahr.
      
   1. **Verwahrer** – Klicken Sie in dieses Feld, und wählen Sie dann einen bestimmten Verwahrer aus, für den Suchergebnisse angezeigt werden sollen. Überwachungsdatensätze für die ausgewählte Aktivität, die von den in diesem Feld ausgewählten Benutzern ausgeführt werden, werden in der Liste der Ergebnisse angezeigt.
      
5. Klicken Sie auf ![Suchschaltfläche](../media/SearchButton.PNG)  , um die Suche mithilfe Ihrer Suchkriterien ausführen. Die Suchergebnisse werden geladen und nach einigen Momenten unter Ergebnisse auf der Suchseite "Verwahreraktivitäten" angezeigt. 

## <a name="step-2-view-the-audit-log-search-results"></a>Schritt 2: Anzeigen der Suchergebnisse des Überwachungsprotokolls

Die Ergebnisse einer Überwachungsprotokollsuche werden unter Ergebnisse auf der Seite Überwachungsprotokoll der Verwahrer angezeigt. Maximal 5.000 (neueste) Ereignisse werden in Schritten von 150 Ereignissen angezeigt. Zum Anzeigen weiterer Ereignisse können Sie die Bildlaufleiste im Bereich Ergebnisse verwenden oder UMSCHALT+ENDE drücken, um die nächsten 150 Ereignisse anzuzeigen.

Die Ergebnisse enthalten die folgenden Informationen zu den einzelnen Ereignissen, die bei der Suche zurückgegeben werden.
- **Datum**: Das Datum und die Uhrzeit (im UTC-Format), zu der das Ereignis auftrat.

- **IP-Adresse**: Die IP-Adresse des Geräts, das verwendet wurde, als die Aktivität protokolliert wurde. Die IP-Adresse wird im Adressformat IPv4 oder IPv6 angezeigt.

- **Benutzer**: Der Benutzer (oder das Dienstkonto), der die Aktion ausführte, durch die das Ereignis ausgelöst wurde.

- **Aktivität**: Die vom Benutzer ausgeführte Aktivität. Dieser Wert entspricht den Aktivitäten, die Sie in der Dropdownliste "Aktivitäten" ausgewählt haben. Bei einem Ereignis aus dem Exchange-Administratorüberwachungsprotokoll ist der Wert in dieser Spalte ein Exchange-Cmdlet.

- **Element**: Das Objekt, das als Ergebnis der entsprechenden Aktivität erstellt oder geändert wurde. Dies kann z. B. die Datei sein, die angezeigt oder geändert wurde, oder das Benutzerkonto, das aktualisiert wurde. Nicht alle Aktivitäten haben in dieser Spalte einen Wert.

- **Detail**: Zusätzliches Detail zu einer Aktivität. Auch hier weisen nicht alle Aktivitäten einen Wert auf.

## <a name="step-3-filter-the-search-results"></a>Schritt 3: Filtern der Suchergebnisse

Zusätzlich zur Sortierung können Sie die Ergebnisse einer Überwachungsprotokollsuche auch filtern. Dies kann Ihnen dabei helfen, die Ergebnisse für einen bestimmten Benutzer oder eine bestimmte Aktivität schnell zu filtern. 

So filtern Sie die Ergebnisse:

 1. Erstellen und Ausführen einer Überwachungsprotokollsuche.
  
2. Sobald die Ergebnisse angezeigt werden, klicken Sie auf **Ergebnisse filtern**.
 
3. Unter den einzelnen Spaltenüberschriften werden Felder für Schlüsselwörter angezeigt.
  
4. Klicken Sie auf eines der Felder unter einer Spaltenüberschrift, und geben Sie abhängig von der Spalte ein Wort oder einen Ausdruck ein, nach dem Sie filtern möchten. Die Ergebnisse werden dynamisch angepasst und die Ereignisse angezeigt, die den Filterkriterien entsprechen.
  
5. Klicken Sie zum Löschen eines Filters im Filterfeld auf **das X,** oder klicken Sie einfach **auf Filter ausblenden.**

## <a name="export-the-search-results-to-a-file"></a>Exportieren der Suchergebnisse in eine Datei

Sie können die Ergebnisse einer Überwachungsprotokollsuche in eine CSV-Datei (Comma Separated Value) auf Ihrem lokalen Computer exportieren. Sie können diese Datei in Microsoft Excel öffnen und Features wie Suchen, Sortieren, Filtern und Aufteilen einer einzelnen Spalte (die mehrwertige Zellen enthält) in mehrere Spalten verwenden.

1. Führen Sie eine Überwachungsprotokollsuche aus, und bearbeiten Sie dann die Suchkriterien, bis Sie die gewünschten Ergebnisse erhalten.
  
2. Klicken Sie auf Ergebnisse exportieren, und wählen Sie eine der folgenden Optionen aus:

    - **Geladene Ergebnisse speichern:** Wählen Sie diese Option aus, um nur die Einträge zu exportieren, die unter **Ergebnisse** auf der Suchseite des Überwachungsprotokolls des Verwahrerprotokolls **angezeigt** werden. Die heruntergeladene CSV-Datei enthält dieselben Spalten (und Daten), die auch auf der Seite angezeigt werden (Datum, Benutzer, Aktivität, Element und Details). Eine zusätzliche Spalte (mit dem Titel **Mehr**) ist in der CSV-Datei enthalten, die weitere Informationen aus dem Überwachungsprotokolleintrag enthält. Da Sie dieselben Ergebnisse exportieren, die auf der Seite Überwachungsprotokollsuche geladen werden (und angezeigt werden können), werden maximal 5.000 Einträge exportiert.
        
    - **Laden Sie alle Ergebnisse herunter:** Wählen Sie diese Option aus, um alle Einträge aus dem Überwachungsprotokoll zu exportieren, die den Suchkriterien entsprechen. Für einen großen Satz von Suchergebnissen wählen Sie diese Option aus, um alle Einträge aus dem Überwachungsprotokoll zusätzlich  zu den 5.000 Ergebnissen herunterzuladen, die auf der Suchseite des Überwachungsprotokolls des Verwahrerprotokolls angezeigt werden können. Diese Option laden die Rohdaten aus dem Überwachungsprotokoll in eine CSV-Datei herunter und enthält zusätzliche Informationen aus dem Überwachungsprotokolleintrag in der Spalte AuditData. Bei Auswahl dieser Exportoption kann das Herunterladen der Datei etwas länger dauern, da die Datei möglicherweise wesentlich größer als diejenige ist, die bei Auswahl einer anderen Option heruntergeladen wird.
    
      > [!IMPORTANT]
      > Aus seiner einzigen Suche in einer Protokolldatei können Sie maximal 50.000 Einträge in eine CSV-Datei herunterladen. Wenn 50.000 Einträge in die CSV-Datei heruntergeladen werden, können Sie wahrscheinlich davon ausgehen, dass mehr als 50.000 Ereignisse die Suchkriterien erfüllen. Wenn Sie mehr als diesen Grenzwert exportieren möchten, versuchen Sie es mit einem Datenbereich, um die Anzahl der Einträge im Überwachungsprotokoll zu verringern. Möglicherweise müssen Sie mehrere Suchläufe mit kleineren Datumsbereichen durchführen, um mehr als 50.000 Einträge zu exportieren.
        

3. Nachdem Sie eine Exportoption ausgewählt haben, wird am unteren Rand des Fensters eine Meldung angezeigt, in der Sie aufgefordert werden, die CSV-Datei zu öffnen, sie im Ordner Downloads zu speichern oder sie in einem bestimmten Ordner zu speichern.

Weitere Informationen zum Anzeigen, Filtern oder Exportieren von Überwachungsprotokollsuchergebnissen finden Sie unter Durchsuchen des Überwachungsprotokolls im [Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).
