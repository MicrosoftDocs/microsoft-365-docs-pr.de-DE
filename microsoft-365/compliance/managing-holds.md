---
title: Verwalten von Halte halte in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Erfahren Sie, wie Sie Custodians und deren Datenquellen speichern, um relevante Inhalte für Ihren Advanced eDiscovery-Fall zu erhalten.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 07edcb2707d1dffecfa5a2aac6c4340ac6cbe53f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926373"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Verwalten von Halte halte in Advanced eDiscovery

Sie können einen Advanced eDiscovery-Fall verwenden, um Halte halte zu erstellen, um Inhalte zu erhalten, die für Ihren Fall relevant sein könnten. Mithilfe der Advanced eDiscovery-Haltefunktionen können Sie Custodians und deren Datenquellen speichern. Darüber hinaus können Sie postfächern und OneDrive for #A0 ein nicht verwahrungsfreies Archiv enhalten. Sie können auch die Gruppenpostfächer, die #A0 und die OneDrive for #A1 für eine Microsoft 365-Gruppe in den Haltepunkt setzen. Auf ähnliche Weise können Sie das Postfach und die Website, die Microsoft Teams zugeordnet sind, in einem Archiv halten. Wenn Sie Inhaltsspeicherorte speichern, werden Inhalte so lange gespeichert, bis Sie den Custodian los, einen bestimmten Datenspeicherort entfernen oder die Halterichtlinie vollständig löschen.

## <a name="manage-custodian-based-holds"></a>Verwalten von verwahrerbasierten Halterechten

In einigen Fällen verfügen Sie möglicherweise über eine Reihe von Verwahrern, die Sie identifiziert haben und ihre Daten während des Falls beibehalten möchten. Wenn diese Verwahrer in Advanced eDiscovery in den Warteschleifen platziert werden, werden der Benutzer und seine ausgewählten Datenquellen automatisch einer Custodian Hold-Richtlinie hinzugefügt.

So zeigen Sie die Halterichtlinie des Verwahrers an:

1. Klicken Sie im Microsoft 365 Compliance Center auf **eDiscovery > Erweitert,** um die Liste der Fälle in Ihrer Organisation anzeigen zu können.

2. Wechseln Sie zur Registerkarte **Quellen,** um Custodians in Ihrem Fall hinzuzufügen. Informationen dazu, wie Sie Verwahrer in einem Advanced eDiscovery-Fall hinzufügen und platzieren können, finden Sie unter [Add Custodians to a case](add-custodians-to-case.md). Wenn Sie bereits Custodians hinzugefügt und in die Warteschleife gesetzt haben, wechseln Sie zu Schritt 3.

3. Wechseln Sie  zur Registerkarte Halteregisterkarten, und klicken Sie **auf CustodianHold \<HoldId>**.

4. Auf der Flyoutseite sehen Sie haltestatistiken für die Richtlinie. Sie können auch Aktionen wie das Anwenden einer Abfrage auf Den Custodian-basierten Halteraum ausführen. Weitere Informationen zum Erstellen einer Halteabfrage und zum Verwenden von Bedingungen finden Sie unter [Schlüsselwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).

## <a name="manage-non-custodial-holds"></a>Verwalten von nicht verwahrungsverwahrten Halterechten

Wenn Sie einen Haltebereich erstellen, haben Sie die folgenden Optionen, um den Inhalt, der an den angegebenen Inhaltsstandorten gehalten wird, zu bereichern:

- Sie erstellen einen unendlichen Halteraum, in dem alle Inhalte in der Warteschleife platziert werden. Alternativ können Sie einen abfragebasierten Halteraum erstellen, bei dem nur Inhalte, die mit einer Suchabfrage übereinstimmen, in der Warteschleife platziert werden.
  
- Sie können einen Datumsbereich angeben, der nur den Inhalt enthält, der innerhalb dieses Datumsbereichs gesendet, empfangen oder erstellt wurde. Alternativ können Sie alle Inhalte unabhängig davon, wann sie gesendet, empfangen oder erstellt wurden, enthalten.

So erstellen Sie einen nicht verwaisten Halteraum für einen Advanced eDiscovery-Fall:

1. Klicken Sie im Microsoft 365 Compliance Center auf **eDiscovery > Erweitert,** um die Liste der Fälle in Ihrer Organisation anzeigen zu können.
  
2. Klicken **Sie neben** dem Fall, in dem Sie die Halte halten erstellen möchten, auf Öffnen.
  
3. Klicken Sie auf der Startseite für den Fall auf die Registerkarte **Halte.**
  
4. Klicken Sie **auf der** Registerkarte Halte halte auf **Erstellen**.
  
5. Geben Sie **auf der Seite** Halten name your hold einen Namen für die Halteschleife ein. Der Name des Halteraums muss in Ihrer Organisation eindeutig sein.
 
6. (Optional) Fügen Sie **im Feld** Beschreibung eine Beschreibung des Haltefelds hinzu.
  
7. Klicken Sie auf **Weiter**.
  
8. Wählen Sie die Inhaltsorte aus, die Sie in der Warteschleife platzieren möchten. Sie können Postfächer, Websites und öffentliche Ordner in der Warteschleife platzieren.

   1. **Exchange-E-Mail:** Klicken Sie **auf Benutzer, Gruppen** oder Teams auswählen, und klicken Sie dann erneut auf **Benutzer, Gruppen** oder Teams auswählen, um Postfächer anzugeben, die in der Warteschleife gespeichert werden. Verwenden Sie das Suchfeld, um Benutzerpostfächer und Verteilergruppen zu finden (um die Postfächer von Gruppenmitgliedern in den Halteraum zu setzen). Sie können das zugeordnete Postfach auch für eine Microsoft 365-Gruppe oder ein Microsoft-Team in einem Archiv platzieren. Aktivieren Sie das Kontrollkästchen Benutzer, Gruppe, Team, klicken Sie auf **Auswählen** und dann auf **Fertig**.
 
      > [!NOTE]
      > Wenn Sie auf **Benutzer, Gruppen** oder Teams auswählen klicken, um Postfächer anzugeben, die in der Warteschleife gespeichert werden, ist die angezeigte Postfachauswahl leer. Dies ist beabsichtigt, um die Leistung zu verbessern. Um dieser Liste Personen hinzuzufügen, geben Sie einen Namen (mindestens 3 Zeichen) in das Suchfeld ein.

   1. **SharePoint-Websites** – Klicken Sie  **auf Websites auswählen,** und klicken Sie dann erneut auf Websites auswählen, um SharePoint- und OneDrive for #A0 anzugeben, die in der Warteschleife gespeichert werden. Geben Sie die URL für jede Website ein, die Sie in der Warteschleife platzieren möchten. Sie können auch die URL für die SharePoint-Website für eine Microsoft 365-Gruppe oder ein Microsoft-Team hinzufügen. Klicken **Sie auf Auswählen** und dann auf **Fertig**.
    
      Im Abschnitt **Häufig gestellte** Fragen finden Sie Tipps zum Halten von Microsoft 365-Gruppen und Microsoft Teams.

      > [!NOTE]
      > Die URL für das #A0 eines Benutzers enthält ihren Benutzerprinzipalnamen (z. B. `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). In dem seltenen Fall, dass der UPN einer Person geändert wird, ändert sich auch die OneDrive-URL, um den neuen UPN zu integrieren. Wenn das #A0 eines Benutzers Teil eines nicht verwahrten Speichers ist und der UPN geändert wird, müssen Sie den Haltepunkt aktualisieren und auf die neue OneDrive-URL verweisen. Weitere Informationen hierzu finden Sie unter [Wie sich UPN-Änderungen auf die OneDrive-URL auswirken](/onedrive/upn-changes).

   1. **Öffentliche Exchange-Ordner** : Verschieben Sie den Umschalter an die Position Alle, um alle öffentlichen Ordner in Ihrer Exchange Online-Organisation in den Halteraum zu setzen. Beachten Sie, dass Sie keine bestimmten öffentlichen Ordner auswählen können, die in der Warteschleife gespeichert werden. Lassen Sie den Umschalter auf **Keine festgelegt,** wenn Sie öffentliche Ordner nicht in der Warteschleife halten möchten.

9. Wenn Sie mit dem Hinzufügen von Inhaltsstandorten zum Halteraum fertig sind, klicken Sie auf **Weiter**.
  
10. Führen Sie folgendes aus, um einen abfragebasierten Halteraum mit Bedingungen zu erstellen. Klicken Sie andernfalls einfach auf **Weiter**.
    
    - Geben Sie im Feld unter **Schlüsselwörter** eine Suchabfrage in das Feld ein, damit nur der Inhalt, der die Suchkriterien erfüllt, in der Warteschleife platziert wird. Sie können Schlüsselwörter, Nachrichteneigenschaften oder Dokumenteigenschaften angeben, z. B. Dateinamen. Sie können auch komplexere Abfragen verwenden, die einen booleschen Operator verwenden, z. B. AND, OR oder NOT. Wenn Sie das Schlüsselwortfeld leer lassen, werden alle Inhalte, die sich an den angegebenen Inhaltsstandorten befinden, in der Warteschleife platziert.

    - Klicken  **Sie auf Bedingungen** hinzufügen, um eine oder mehrere Bedingungen hinzuzufügen, um die Suchabfrage für den Halteraum zu einenten. Jede Bedingung fügt der KQL-Suchabfrage eine Klausel hinzu, die beim Erstellen des Haltezustands erstellt und ausgeführt wird. Sie können z. B. einen Datumsbereich angeben, damit E-Mails oder Websitedokumente, die innerhalb des Datumsbereichs erstellt wurden, in einem Haltebereich platziert werden. Eine Bedingung ist durch AND-Operator logisch mit der (im Schlüsselwortfeld angegebenen) Schlüsselwortabfrage verbunden. Das bedeutet, dass Elemente sowohl die Schlüsselwortabfrage als auch die Bedingung erfüllen müssen, die in der Warteschleife platziert werden soll.

     Weitere Informationen zum Erstellen einer Suchabfrage und zum Verwenden von Bedingungen finden Sie unter [Schlüsselwortabfragen und Suchbedingungen für die Inhaltssuche](/office365/SecurityCompliance/keyword-queries-and-search-conditions).

11. Klicken Sie nach dem Konfigurieren eines abfragebasierten Halteraums auf **Weiter**.

12. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann **auf Diesen Halteraum erstellen.**

## <a name="view-hold-statistics"></a>Anzeigen von Haltestatistiken

Nach einiger Zeit werden Informationen zum neuen Haltebereich im  Detailbereich auf der Registerkarte Haltebereiche für den ausgewählten Haltebereich angezeigt. Diese Informationen umfassen die Anzahl von Postfächern und Websites, die in einem Archiv gespeichert sind, sowie Statistiken zu den Inhalten, die in einem Haltespeicher platziert wurden, z. B. die Gesamtanzahl und Größe der in der Warteschleife platzierten Elemente und das letzte Mal, zu dem die Haltestatistiken berechnet wurden. Diese Haltestatistiken helfen Ihnen zu ermitteln, wie viel Inhalt im Zusammenhang mit dem eDiscovery-Fall gehalten wird.

Beachten Sie die folgenden Punkte bei der Haltestatistik:

- Die Gesamtanzahl der in der Warteschleife platzierten Elemente gibt die Anzahl der Elemente aus allen Inhaltsquellen an, die in der Warteschleife platziert werden. Wenn Sie einen abfragebasierten Halteraum erstellt haben, gibt diese Statistik die Anzahl der Elemente an, die mit der Abfrage übereinstimmen.
  
- Die Anzahl der In-Hold-Elemente umfasst auch nicht indizierte Elemente, die in den Inhaltsverzeichnissen gefunden wurden. Beachten Sie, dass beim Erstellen eines abfragebasierten Halteraums alle nicht indizierten Elemente in den Inhaltsverzeichnissen in der Warteschleife platziert werden. Dies umfasst nicht indizierte Elemente, die nicht den Suchkriterien eines abfragebasierten Haltebereichs entsprechen, und nicht indizierte Elemente, die möglicherweise außerhalb einer Datumsbereichsbedingung liegen. Dies ist anders als beim Ausführen einer Inhaltssuche, bei der nicht indizierte Elemente, die nicht mit der Suchabfrage übereinstimmen oder von einer Datumsbereichsbedingung ausgeschlossen werden, nicht in den Suchergebnissen enthalten sind. Weitere Informationen zu nicht indizierten Elementen finden Sie unter Teilweise indizierte Elemente [in der Inhaltssuche in Office 365](partially-indexed-items-in-content-search.md). 

- Sie können die neuesten Haltestatistiken erhalten, indem Sie auf Statistiken aktualisieren klicken, um eine Suchschätzung erneut ausführen zu können, die die aktuelle Anzahl von Halteelementen berechnet.

- Klicken Sie bei Bedarf in der Symbolleiste auf Aktualisieren, um die Haltestatistiken im Detailbereich zu aktualisieren.

- Es ist normal, dass die Anzahl der in der Warteschleife gespeicherten Elemente im Laufe der Zeit zunimmt, da Benutzer, deren Postfach oder Website im Archiv ist, in der Regel neue E-Mail-Nachrichten senden oder empfangen und neue SharePoint- und OneDrive for #A0 erstellen.

- Wenn eine #A0 oder ein #A1 in eine andere Region in einer Multi-Geo-Umgebung verschoben wird, werden die Statistiken für diese Website nicht in die Haltestatistik einbezogen. Die Inhalte auf der Website sind jedoch weiterhin in der Warteschleife. Wenn eine Website in einen anderen Bereich verschoben wird, wird auch die URL, die im Haltebereich angezeigt wird, nicht aktualisiert. Sie müssen den Haltemodus bearbeiten und die URL aktualisieren.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Halten von Microsoft Teams und Office 365-Gruppen

Microsoft Teams baut auf Office 365-Gruppen auf. Daher ist es sehr ähnlich, sie in Advanced eDiscovery in der Warteschleife zu platzieren. 

- **Wie zuordnung ich eine zusätzliche Microsoft 365-Gruppen- oder Microsoft Teams-Website einem Verwahrer? Und wie sieht es mit einem nicht verwaisten Halterecht für Microsoft 365-Gruppen und Microsoft Teams aus?** Microsoft Teams baut auf Microsoft 365-Gruppen auf. Daher ist es sehr ähnlich, sie in einem eDiscovery-Fall zu halten. Beachten Sie folgendes, wenn Sie Microsoft 365-Gruppen und Microsoft Teams in der Warteschleife platzieren.
  - Um Inhalte in Microsoft 365-Gruppen und Microsoft Teams in der Warteschleife zu platzieren, müssen Sie das Postfach und die SharePoint-Website angeben, die einer Gruppe oder einem Team zugeordnet sind.
  
  - Führen Sie **das Cmdlet Get-UnifiedGroup** in Exchange Online aus, um Eigenschaften für eine Microsoft 365-Gruppe oder ein Microsoft Team anzeigen zu können. Dies ist eine gute Möglichkeit, um die URL für die Website zu erhalten, die einer Microsoft 365-Gruppe oder einem Microsoft-Team zugeordnet ist. Der folgende Befehl zeigt beispielsweise ausgewählte Eigenschaften für eine Microsoft 365-Gruppe mit dem Namen „Senior Leadership Team“ an:


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Zum Ausführen des Get-UnifiedGroup-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde.

 - Wenn das Postfach eines Benutzers durchsucht wird, wird keine Microsoft 365-Gruppe oder ein Microsoft Team durchsucht, bei der der Benutzer Mitglied ist. Wenn Sie eine Microsoft 365-Gruppe oder ein Microsoft #A0 platzieren, werden auch nur das Gruppenpostfach und die Gruppenwebsite in der Warteschleife platziert. Die Postfächer und OneDrive for #A0 von Gruppenmitgliedern werden nur dann in den Archiven gespeichert, wenn Sie sie explizit als Verwahrer hinzufügen oder deren Datenquellen speichern. Wenn Sie daher eine Microsoft 365-Gruppe oder ein Microsoft Team für einen bestimmten Verwahrer in der Warteschleife platzieren müssen, sollten Sie die Gruppenwebsite und das Gruppenpostfach dem Verwahrer zuordnen (siehe Managing Custodians in Advanced eDiscovery). Wenn die Microsoft 365-Gruppe oder das Microsoft Team nicht einem einzelnen Verwahrer zuzurechnen ist, sollten Sie die Quelle zu einem nicht verwahrten Halterecht hinzufügen. 
 
 - Um eine Liste der Mitglieder einer Microsoft 365-Gruppe oder eines Microsoft-Teams zu erhalten, können Sie die Eigenschaften auf der Seite Startseite >-Gruppen im Microsoft 365 Admin Center anzeigen. Alternativ können Sie den folgenden Befehl in Exchange Online-PowerShell ausführen:

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > Zum Ausführen des **Get-UnifiedGroupLinks**-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde.

- Kanalunterhaltungen, die Teil eines Microsoft Teams-Kanals sind, werden im Postfach gespeichert, das dem Team zugeordnet ist. Gleichermaßen werden Dateien, die Teammitglieder in einem Kanal freigeben, auf der SharePoint-Website des Teams gespeichert. Daher müssen Sie das Microsoft Team-Postfach und die SharePoint-Website in der Warteschleife platzieren, um Unterhaltungen und Dateien in einem Kanal zu speichern.
  
- Alternativ werden Unterhaltungen, die Teil der Chatliste in Microsoft Teams sind, im Postfach der Benutzer gespeichert, die am Chat teilnehmen.  Dateien, die ein Benutzer in Chatunterhaltungen teilt, werden auf der OneDrive for #A0 des Benutzers gespeichert, der die Datei teilt. Daher müssen Sie die einzelnen Benutzerpostfächer und OneDrive for #A0 in der Warteschleife platzieren, um Unterhaltungen und Dateien in der Chatliste zu speichern. 
  
- Jeder Microsoft-Team- oder Teamkanal enthält ein Wiki zur Notizen- und Zusammenarbeit. Die Wiki-Inhalte werden automatisch in einer Datei im MHT-Format gespeichert. Diese Datei wird in der Dokumentbibliothek für Wiki-Daten auf der SharePoint-Website des Teams gespeichert. Sie können die Inhalte im Wiki in den Haltebereich setzen, indem Sie die SharePoint-Website des Teams im Haltebereich platzieren.

  > [!NOTE]
  > Die Funktion zum Beibehalten von Wiki-Inhalten für einen Microsoft Team- oder Teamkanal (wenn Sie die SharePoint-Website des Teams in der Warteschleife platzieren) wurde am 22. Juni 2017 veröffentlicht. Wenn eine Teamwebsite in der Warteschleife ist, werden die Wikiinhalte ab diesem Datum aufbewahrt. Wenn sich jedoch eine Teamwebsite in der Warteschleife befindet und die Wikiinhalte vor dem 22. Juni 2017 gelöscht wurden, wurden die Wikiinhalte nicht beibehalten.