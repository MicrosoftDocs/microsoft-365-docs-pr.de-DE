---
title: Manage Holds in Advanced eDiscovery
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
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 1334a90dc2e98e720aa9da392bd558adb34b37b2
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632960"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Manage Holds in Advanced eDiscovery

Sie können einen erweiterten eDiscovery-Fall zum Erstellen von Haltebereichen verwenden, um Inhalte beizubehalten, die für Ihren Fall relevant sein könnten. Mithilfe der erweiterten eDiscovery-Aufbewahrungsfunktionen können Sie Aufbewahrungen und deren Datenquellen platzieren. Außerdem können Sie Postfächern und OneDrive für Unternehmen Websites einen Aufbewahrungs freien Speicherplatz hinzufügen. Sie können auch das Gruppenpostfach, die SharePoint-Website und die OneDrive für Unternehmen Website für eine Microsoft 365-Gruppe aufbewahren. Ebenso können Sie das Postfach und die Website, die Microsoft Teams zugeordnet sind, aufbewahren. Wenn Sie inhaltsspeicherorte in der Warteschleife platzieren, wird der Inhalt so lange aufbewahrt, bis Sie die Depotbank freigeben, einen bestimmten Datenspeicherort entfernen oder die Aufbewahrungsrichtlinie vollständig löschen.

## <a name="manage-custodian-based-holds"></a>Verwalten von Depot basierten Haltestatus

In einigen Fällen verfügen Sie möglicherweise über eine Reihe von Depot Betreuern, die Sie identifiziert haben und die sich entschieden haben, Ihre Daten im Fall beizubehalten. Wenn diese Depotbanken in der erweiterten eDiscovery-Datenbank gespeichert werden, werden der Benutzer und die ausgewählten Datenquellen automatisch einer Depotbank-Aufbewahrungsrichtlinie hinzugefügt.

So zeigen Sie die Richtlinie für Depot Aufbewahrung an:

1. Klicken Sie im Microsoft 365 Compliance Center auf **eDiscovery > erweitert** , um die Liste der Fälle in Ihrer Organisation anzuzeigen.
   
2. Wechseln Sie zur Registerkarte **depotverwalter** , um Verwalter in Ihrem Fall hinzuzufügen. Weitere Informationen zum Hinzufügen und Platzieren von Depot Haltern in einem erweiterten eDiscovery-Fall finden Sie unter Hinzufügen von Depot Betreuern [zu einem erweiterten eDiscovery-Fall](add-custodians-to-case.md). Wenn Sie bereits Verwalter hinzugefügt und in die Warteschleife gesetzt haben, fahren Sie mit Schritt 3 fort.
   
3. Wechseln Sie zur Registerkarte halte **Status** , und klicken Sie auf **CustodianHold\<>**.
   
4. Auf der Flyout-Seite finden Sie Statistiken für die Richtlinie speichern. Sie können auch Aktionen wie das Anwenden einer Abfrage auf Ihren Depot-basierten Haltebereich ausführen. Weitere Informationen zum Erstellen einer halte Abfrage und zum Verwenden von Bedingungen finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
 
## <a name="manage-non-custodial-holds"></a>Verwalten von Aufbewahrungs freien Haltebereichen

Wenn Sie einen Haltebereich erstellen, haben Sie die folgenden Optionen, um den Inhalt zu belegen, der an den angegebenen Inhaltsspeicherorten gehalten wird:

- Sie erstellen einen unbegrenzten Haltebereich, in dem der gesamte Inhalt aufbewahrt wird. Alternativ können Sie einen abfragebasierten Speicher erstellen, in dem nur Inhalte, die einer Suchabfrage entsprechen, in die Warteschleife gestellt werden.
  
- Sie können einen Datumsbereich angeben, in dem nur der Inhalt gespeichert werden soll, der innerhalb dieses Datumsbereichs gesendet, empfangen oder erstellt wurde. Alternativ können Sie alle Inhalte speichern, unabhängig davon, wann Sie gesendet, empfangen oder erstellt wurden.

So erstellen Sie einen Aufbewahrungs freien Speicher für einen erweiterten eDiscovery-Fall:

1. Klicken Sie im Microsoft 365 Compliance Center auf **eDiscovery > erweitert** , um die Liste der Fälle in Ihrer Organisation anzuzeigen.
  
2. Klicken Sie neben dem Fall, in dem Sie die Aufbewahrungspflicht erstellen möchten, auf **Öffnen** .
  
3. Klicken Sie auf der Startseite für den Fall auf die Registerkarte halte **Status** .
  
4. Klicken Sie auf der Registerkarte halte **Status** auf **Erstellen**.
  
5. Geben Sie auf der Seite **Name Ihres Haltestatus** dem Haltestatus einen Namen. Der Name des haltebereichs muss in Ihrer Organisation eindeutig sein.
 
6. Optional Fügen Sie im Feld **Beschreibung** eine Beschreibung des Haltestatus hinzu.
  
7. Klicken Sie auf **Weiter**.
  
8. Wählen Sie die inhaltsspeicherorte aus, die Sie in die Warteschleife stellen möchten. Sie können Postfächer, Websites und öffentliche Ordner in der Warteschleife platzieren.

   a. **Exchange-e-Mail** -klicken Sie auf **Benutzer, Gruppen oder Teams auswählen** , und klicken Sie dann erneut auf **Benutzer, Gruppen oder Teams** auswählen, um die Aufbewahrungszeit für Postfächer festzulegen. Verwenden Sie das Suchfeld, um nach Benutzerpostfächern und Verteilergruppen zu suchen (um die Postfächer der Gruppenmitglieder festhalten zu können), damit Sie in der Warteschleife platziert werden. Sie können das zugeordnete Postfach auch für eine Microsoft 365-Gruppe oder ein Microsoft-Team aufbewahren. Aktivieren Sie das Kontrollkästchen Benutzer, Gruppe, Team, klicken Sie auf **auswählen**, und klicken Sie dann auf **Fertig**.
 
    > [!NOTE]
    > Wenn Sie auf **Benutzer, Gruppen oder Teams auswählen** klicken, um festzulegende Postfächer anzugeben, ist die angezeigte Post Fachauswahl leer. Dies ist beabsichtigt, um die Leistung zu verbessern. Geben Sie einen Namen (mindestens 3 Zeichen) in das Suchfeld ein, um Personen zu dieser Liste hinzuzufügen.

    b. **SharePoint-Websites** – klicken Sie auf **Websites auswählen** , und klicken Sie dann erneut auf **Websites auswählen** , um SharePoint und OneDrive für Unternehmen Websites für die Aufbewahrung festzulegen. Geben Sie die URL für jede Website ein, die Sie in die Warteschleife stellen möchten. Sie können auch die URL für die SharePoint-Website für eine Microsoft 365-Gruppe oder ein Microsoft-Team hinzufügen. Klicken Sie auf **auswählen**, und klicken Sie dann auf **Fertig**.
    
     Im Abschnitt **häufig gestellte Fragen** finden Sie Tipps dazu, wie Sie Microsoft 365-Gruppen und Microsoft Teams in die Warteschleife versetzen.

    > [!NOTE]
    > Die URL für das OneDrive-Konto eines Benutzers enthält den Benutzerprinzipalnamen (User Principal Name, `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com`UPN) (beispielsweise). Im seltenen Fall, dass der UPN eines Benutzers geändert wird, ändert sich auch die OneDrive-URL, um den neuen UPN zu integrieren. Wenn das OneDrive-Konto eines Benutzers Teil eines Speichers ohne Freiheitsentzug ist und sein UPN geändert wird, müssen Sie den Haltestatus aktualisieren und auf die neue OneDrive-URL deuten. Weitere Informationen hierzu finden Sie unter [Wie sich UPN-Änderungen auf die OneDrive-URL auswirken](https://docs.microsoft.com/onedrive/upn-changes).

     c. **Öffentliche Exchange-Ordner** – verschieben Sie die Umschaltfläche in die Position alle, um alle öffentlichen Ordner in Ihrer Exchange Online Organisation zu speichern. Beachten Sie, dass Sie keine bestimmten öffentlichen Ordner für die Aufbewahrung auswählen können. Lassen Sie den Toggle-Schalter auf " **None** " festgelegt, wenn Sie öffentliche Ordner nicht in den Speicher setzen möchten.

9. Wenn Sie das Hinzufügen von Inhaltsspeicherorten in der Warteschleife abgeschlossen haben, klicken Sie auf **weiter**.
  
10. Um eine abfragebasierte Aufbewahrung mit Bedingungen zu erstellen, führen Sie die folgenden Schritte aus. Klicken Sie andernfalls einfach auf **weiter**.
    
    - Geben Sie im Feld unter **Schlüsselwörter**eine Suchabfrage in das Feld ein, sodass nur der Inhalt, der die Suchkriterien erfüllt, in der Warteschleife gespeichert wird. Sie können Schlüsselwörter, Nachrichteneigenschaften oder Dokumenteigenschaften wie Dateinamen angeben. Sie können auch komplexere Abfragen verwenden, die einen booleschen Operator wie and, or oder not verwenden. Wenn Sie das Feld Schlüsselwort leer lassen, werden alle Inhalte, die sich an den angegebenen Inhaltsspeicherorten befinden, aufbewahrt.

    - Klicken Sie auf Bedingungen **Hinzufügen** , um eine oder mehrere Bedingungen hinzuzufügen, um die Suchabfrage für den Haltebereich einzuschränken. Jede Bedingung fügt der KQL-Suchabfrage, die erstellt und ausgeführt wird, eine Klausel hinzu, wenn Sie den Haltebereich erstellen. Sie können beispielsweise einen Datumsbereich angeben, damit e-Mail-oder Website Dokumente, die innerhalb des Datumsbereichs erstellt wurden, in der Warteschleife gespeichert werden. Eine Bedingung ist durch AND-Operator logisch mit der (im Schlüsselwortfeld angegebenen) Schlüsselwortabfrage verbunden. Das bedeutet, dass Elemente sowohl die Stichwortabfrage als auch die Bedingung erfüllen müssen, die in der Warteschleife gespeichert werden soll.

     Weitere Informationen zum Erstellen einer Suchabfrage und zum Verwenden von Bedingungen finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](https://docs.microsoft.com/office365/SecurityCompliance/keyword-queries-and-search-conditions).

11. Klicken Sie nach dem Konfigurieren eines abfragebasierten Haltestatus auf **weiter**.

12. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **diesen Haltebereich erstellen**.

## <a name="view-hold-statistics"></a>Statistiken zum Anzeigen von Haltestatus

Nach einiger Zeit werden Informationen zum neuen Haltestatus im Detailbereich auf der Registerkarte halte **Status** des ausgewählten haltebereichs angezeigt. Diese Informationen umfassen die Anzahl der zu speichernden Postfächer und Websites sowie Statistiken zu den Inhalten, die in der Warteschleife gespeichert wurden, beispielsweise die Gesamtanzahl und Größe der zu speichernden Elemente sowie die Uhrzeit, zu der die Aufbewahrungs Statistik zuletzt berechnet wurde. Diese Aufbewahrungs Statistiken helfen Ihnen zu ermitteln, wie viele Inhalte im Zusammenhang mit dem eDiscovery-Fall gehalten werden.

Beachten Sie die folgenden Aspekte bei Aufbewahrungs Statistiken:

- Die Gesamtanzahl der Elemente in der Warteschleife gibt die Anzahl der Elemente aus allen Inhaltsquellen an, die in der Warteschleife gespeichert werden. Wenn Sie einen abfragebasierten Haltebereich erstellt haben, gibt diese Statistik die Anzahl der Elemente an, die mit der Abfrage übereinstimmen.
  
- Die Anzahl der zu speichernden Elemente umfasst auch nicht indizierte Elemente, die an den Inhaltsspeicherorten gefunden wurden. Beachten Sie, dass beim Erstellen eines abfragebasierten haltebereichs alle nicht indizierten Elemente in den Inhaltsspeicherorten in der Warteschleife gespeichert werden. Dies umfasst nicht indizierte Elemente, die nicht mit den Suchkriterien eines abfragebasierten haltebereichs und nicht indizierten Elementen übereinstimmen, die möglicherweise außerhalb einer Datumsbereichs Bedingung liegen. Dies unterscheidet sich von dem, was passiert, wenn Sie eine Inhaltssuche ausführen, in der nicht indizierte Elemente, die nicht mit der Suchabfrage übereinstimmen oder von einer Datumsbereichs Bedingung ausgeschlossen werden, nicht in den Suchergebnissen enthalten sind. Weitere Informationen zu nicht indizierten Elementen finden Sie unter [teilweise indizierte Elemente in der Inhaltssuche in Office 365](partially-indexed-items-in-content-search.md). 

- Sie können die neuesten Aufbewahrungs Statistiken abrufen, indem Sie auf Statistik aktualisieren klicken, um eine Such Schätzung erneut auszuführen, mit der die aktuelle Anzahl der zu speichernden Elemente berechnet wird.

- Klicken Sie gegebenenfalls in der Symbolleiste auf aktualisieren, um die Aufbewahrungs Statistiken im Detailbereich zu aktualisieren.

- Es ist normal, dass die Anzahl der zu speichernden Elemente im Laufe der Zeit steigt, da Benutzer, deren Postfach oder Standort in der Warteschleife ist, normalerweise neue e-Mail-Nachrichten senden oder empfangen und neue SharePoint-und OneDrive für Unternehmen-Dokumente erstellen.

- Wenn ein SharePoint-Website-oder OneDrive-Konto in eine andere Region in einer Multi-Geo-Umgebung verschoben wird, werden die Statistiken für diese Website nicht in die halte Statistik aufgenommen. Der Inhalt der Website bleibt jedoch weiterhin gespeichert. Wenn eine Website in einen anderen Bereich verschoben wird, wird auch die im Haltestatus angezeigte URL nicht aktualisiert. Sie müssen den Haltebereich bearbeiten und die URL aktualisieren.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Aufbewahren von Microsoft Teams und Office 365 Gruppen

Microsoft Teams sind auf Office 365 Gruppen aufgebaut. Daher ist es sehr ähnlich, dass Sie in Advanced eDiscovery in die Warteschleife versetzt werden. 

- **Wie kann ich eine zusätzliche Microsoft 365-Gruppe oder Microsoft Teams-Website einer Depotbank zuordnen? Und was ist mit dem Platzieren eines nicht-Freiheits behaltes für Microsoft 365-Gruppen und Microsoft Teams?** Microsoft Teams basiert auf Microsoft 365-Gruppen. Daher ist es sehr ähnlich, dass Sie in einem eDiscovery-Fall aufbewahrt werden. Beachten Sie beim Platzieren von Microsoft 365-Gruppen und Microsoft Teams die folgenden Aspekte.
  - Um Inhalte in Microsoft 365-Gruppen und Microsoft Teams in der Warteschleife zu platzieren, müssen Sie das Postfach und die SharePoint-Website angeben, die einer Gruppe oder einem Team zugeordnet ist.
  
  - Führen Sie das Cmdlet **Get-Unifiedgroup** in Exchange Online aus, um Eigenschaften für eine Microsoft 365-Gruppe oder ein Microsoft-Team anzuzeigen. Dies ist eine gute Möglichkeit, die URL für die Website abzurufen, die einer Microsoft 365-Gruppe oder einem Microsoft-Team zugeordnet ist. Mit dem folgenden Befehl werden beispielsweise ausgewählte Eigenschaften für eine Microsoft 365-Gruppe mit dem Namen "Senior Leadership Team" angezeigt:


    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Zum Ausführen des Get-UnifiedGroup-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde.

 - Wenn das Postfach eines Benutzers durchsucht wird, werden alle Microsoft 365-Gruppen oder Microsoft-Teams, bei denen der Benutzer Mitglied ist, nicht durchsucht. Wenn Sie eine Microsoft 365-Gruppe oder ein Microsoft-Team halten, werden nur das Gruppenpostfach und die Gruppen Website in den Wartebereich verschoben. die Postfächer und OneDrive für Unternehmen Websites von Gruppenmitgliedern werden nur gespeichert, wenn Sie Sie explizit als Verwalter hinzufügen oder Ihre Datenquellen halten. Wenn Sie daher eine Microsoft 365-Gruppe oder ein Microsoft-Team für eine bestimmte Depotbank in der Warteschleife platzieren möchten, sollten Sie die Gruppen Website und das Gruppenpostfach der Depotbank zuordnen (siehe Managing custodys in Advanced eDiscovery). Wenn die Microsoft 365-Gruppe oder das Microsoft-Team nicht auf eine einzige Depotbank zurückzuführen ist, sollten Sie die Quelle einem nicht-Freiheitsentzug-Aufbewahrungsplatz hinzufügen. 
 
 - Wenn Sie eine Liste der Mitglieder einer Microsoft 365-Gruppe oder eines Microsoft-Teams erhalten möchten, können Sie die Eigenschaften auf der Seite Start > Gruppen im Microsoft 365 Admin Center anzeigen. Alternativ können Sie den folgenden Befehl in Exchange Online-PowerShell ausführen:

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > Zum Ausführen des **Get-UnifiedGroupLinks**-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde.

- Kanal Unterhaltungen, die Teil eines Microsoft Teams-Kanals sind, werden in dem Postfach gespeichert, das dem Team zugeordnet ist. Gleichermaßen werden Dateien, die Teammitglieder in einem Kanal freigeben, auf der SharePoint-Website des Teams gespeichert. Daher müssen Sie das Microsoft Team-Postfach und die SharePoint-Website speichern, um Unterhaltungen und Dateien in einem Kanal beizubehalten.
  
- Alternativ werden Unterhaltungen, die Teil der Chatliste in Microsoft Teams sind, im Postfach des Benutzers gespeichert, der am Chat teilnimmt.  Dateien, die ein Benutzer in Chat Unterhaltungen freigibt, werden auf der OneDrive für Unternehmen Website des Benutzers gespeichert, der die Datei freigibt. Daher müssen Sie die einzelnen Benutzerpostfächer und OneDrive für Unternehmen Websites in der Warteschleife platzieren, um Unterhaltungen und Dateien in der Chat Liste beizubehalten. 
  
- Jeder Microsoft-Team-oder Team Kanal enthält ein wiki für die Notizen und die Zusammenarbeit. Die Wiki-Inhalte werden automatisch in einer Datei im MHT-Format gespeichert. Diese Datei wird in der Dokumentbibliothek für Wiki-Daten auf der SharePoint-Website des Teams gespeichert. Sie können die Inhalte im wiki in der Warteschleife platzieren, indem Sie die SharePoint-Website des Teams in der Warteschleife platzieren.

  > [!NOTE]
  > Die Funktion zum Beibehalten von wiki-Inhalten für einen Microsoft-Team-oder Team Kanal (wenn Sie die SharePoint-Website des Teams in der Warteschleife platzieren) wurde am 22. Juni 2017 veröffentlicht. Wenn eine Teamwebsite gespeichert ist, wird der Inhalt des Wikis ab diesem Datum beibehalten. Wenn jedoch eine Teamwebsite gespeichert ist und der Inhalt des Wikis vor dem 22. Juni 2017 gelöscht wurde, wurde der Inhalt des Wikis nicht beibehalten.
