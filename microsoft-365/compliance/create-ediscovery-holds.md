---
title: Erstellen von eDiscovery-Haltebereich in einem Core eDiscovery-Fall
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
description: Sie können einen Haltebereich erstellen, der einem Core eDiscovery-Fall in Microsoft 365, um Inhalte zu erhalten, die für eine Untersuchung oder einen Rechtsstreit relevant sind.
ms.openlocfilehash: 61bbe2e8d2713c2960105e2ec4eb4beffcd4306e
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311609"
---
# <a name="create-an-ediscovery-hold"></a>Erstellen eines eDiscovery-Speichers

Sie können einen Core eDiscovery-Fall verwenden, um Haltebereich zu erstellen, um Inhalte zu erhalten, die für den Fall relevant sein könnten. Sie können die Postfächer Exchange und OneDrive for Business Konten von Personen, die Sie in dem Fall untersuchen, in den Archiven platzieren. Sie können auch die Postfächer und Websites, die Microsoft Teams, Office 365 und Yammer zugeordnet sind, in den Halteraum setzen. Wenn Sie Inhaltsspeicherorte in der Warteschleife platzieren, werden Inhalte beibehalten, bis Sie den Inhaltsspeicherort aus dem Halteraum entfernen oder bis Sie den Haltespeicher löschen.

Nachdem Sie einen eDiscovery-Halteschutz erstellt haben, kann es bis zu 24 Stunden dauern, bis die Haltezeit wirksam wird.

Wenn Sie einen Haltebereich erstellen, haben Sie die folgenden Optionen, um den Inhalt zu bereichern, der an den angegebenen Inhaltsstandorten aufbewahrt wird:
  
- Erstellen Sie einen unendlichen Halteraum, in dem alle Inhalte an den angegebenen Speicherorten in der Warteschleife platziert werden. Alternativ können Sie einen abfragebasierten Halteraum erstellen, bei dem nur der Inhalt an den angegebenen Speicherorten, die mit einer Suchabfrage übereinstimmen, in der Warteschleife platziert wird.

- Geben Sie einen Datumsbereich an, um nur den Inhalt zu erhalten, der innerhalb dieses Datumsbereichs gesendet, empfangen oder erstellt wurde. Alternativ können Sie alle Inhalte an angegebenen Speicherorten enthalten, unabhängig davon, wann sie gesendet, empfangen oder erstellt wurden.
  
## <a name="how-to-create-an-ediscovery-hold"></a>Erstellen eines eDiscovery-Halteraums

So erstellen Sie einen eDiscovery-Haltebereich, der einem Core eDiscovery-Fall zugeordnet ist:
  
1. Wechseln Sie zu, und melden Sie sich mit den Anmeldeinformationen für ein Benutzerkonto an, dem die entsprechenden [https://compliance.microsoft.com](https://compliance.microsoft.com) eDiscovery-Berechtigungen zugewiesen wurden.

2. Klicken Sie im linken Navigationsbereich Microsoft 365 Compliance Center auf Alle **anzeigen,** und klicken Sie dann auf **eDiscovery > Core**.

3. Klicken Sie auf der Seite **Core eDiscovery** auf den Namen des Falls, in dem Sie den Haltebereich erstellen möchten.

4. Klicken Sie **auf der** Startseite für den Fall auf die Registerkarte **Halten.**
  
5. Klicken Sie **auf der** Seite Halten auf **Erstellen**.

6. Geben Sie **dem Halteassistenten** auf der Seite Name des Halteassistenten einen Namen, fügen Sie eine optionale Beschreibung hinzu, und klicken Sie dann auf **Weiter**. Der Name des Halteraums muss in Ihrer Organisation eindeutig sein.

7. Wählen Sie **auf der Seite** Speicherorte auswählen die Speicherorte aus, die Sie in der Warteschleife platzieren möchten. Sie können Postfächer, Websites und öffentliche Ordner in der Warteschleife platzieren.

    ![Wählen Sie Inhaltsspeicherorte aus, die im Haltebereich platziert werden sollen.](../media/eDiscoveryHoldLocations.png)
  
   1. **Exchange Postfächer:** Legen Sie den Umschalter auf **Ein** fest, und klicken Sie dann auf **Benutzer, Gruppen** oder Teams auswählen, um die Postfächer anzugeben, die in der Warteschleife gespeichert werden. Verwenden Sie das Suchfeld, um Benutzerpostfächer und Verteilergruppen zu finden (um die Postfächer von Gruppenmitgliedern in den Halteraum zu setzen). Sie können das zugeordnete Postfach auch für ein Microsoft Team, eine Office 365 und eine Yammer platzieren. Weitere Informationen zu den Anwendungsdaten, die beim Speichern eines Postfachs aufbewahrt werden, finden Sie unter Inhalt, der in Postfächern für [eDiscovery gespeichert ist.](what-is-stored-in-exo-mailbox.md)

   1. **SharePoint** Websites: Legen Sie die Umschaltflächen auf  **Ein** fest, und klicken Sie dann auf Websites auswählen, um SharePoint websites und OneDrive konten anzugeben, die in der Warteschleife platzieren werden. Geben Sie die URL für jede Website ein, die Sie in der Warteschleife platzieren möchten. Sie können auch die URL für die SharePoint für ein Microsoft Team, eine Office 365 oder eine Yammer hinzufügen.
  
   1. **Exchange öffentlichen Ordner**: Legen Sie die Umschalte auf **Ein** fest, um alle öffentlichen Ordner in Exchange Online organisation zu speichern. Sie können keine bestimmten öffentlichen Ordner auswählen, die in der Warteschleife gespeichert werden. Lassen Sie den Umschalter deaktiviert, wenn Sie öffentliche Ordner nicht in den Halteraum setzen möchten.

   > [!NOTE]
   > Sie müssen dem Haltespeicherort mindestens einen Inhaltsspeicherort hinzufügen. Andernfalls zeigt die eDiscovery-Haltestatistik, dass keine Elemente im Halteraum sind.

8. Wenn Sie mit dem Hinzufügen von Speicherorten zum Halteraum fertig sind, klicken Sie auf **Weiter**.

9. Führen Sie die folgenden Schritte aus, um einen abfragebasierten Halteraum mithilfe von Schlüsselwörtern oder Bedingungen zu erstellen. Klicken Sie auf Weiter, um alle Inhalte an den angegebenen Inhaltspositionen **zu erhalten.**

    ![Erstellen eines abfragebasierten Halteraums mit Schlüsselwort und Bedingungen](../media/eDiscoveryHoldQuery.png)
  
    1. Geben Sie im Feld unter **Schlüsselwörter** eine Abfrage ein, um nur den Inhalt zu erhalten, der den Abfragekriterien entspricht. Sie können Schlüsselwörter, E-Mail-Nachrichteneigenschaften oder Websiteeigenschaften angeben, z. B. Dateinamen. Sie können auch komplexere Abfragen verwenden, die einen booleschen Operator verwenden, z. B. **AND**, **OR** oder **NOT**.

    2. Klicken **Sie auf Bedingung hinzufügen,** um eine oder mehrere Bedingungen hinzuzufügen, um die Abfrage für den Haltezustand zu einenten. Jede Bedingung fügt der KQL-Suchabfrage eine Klausel hinzu, die beim Erstellen des Haltezustands erstellt und ausgeführt wird. Sie können z. B. einen Datumsbereich angeben, damit E-Mails oder Websitedokumente, die innerhalb des Datumsbereichs erstellt wurden, beibehalten werden. Eine Bedingung ist logisch mit der Schlüsselwortabfrage (angegeben im Feld **Schlüsselwörter)** und anderen Bedingungen durch den **AND-Operator** verbunden. Das bedeutet, dass Elemente sowohl die Schlüsselwortabfrage als auch die bedingung erfüllen müssen, die beibehalten werden soll.

    Weitere Informationen zum Erstellen einer Suchabfrage und zum Verwenden von Bedingungen finden Sie unter Schlüsselwortabfragen und Suchbedingungen [für eDiscovery](keyword-queries-and-search-conditions.md).

10. Klicken Sie nach dem Konfigurieren eines abfragebasierten Halteraums auf **Weiter**.

11. Überprüfen Sie Ihre Einstellungen (und bearbeiten Sie sie bei Bedarf), und klicken Sie dann auf **Absenden**.

## <a name="query-based-holds-placed-on-sites"></a>Abfragebasierte Halteplätze auf Websites

Beachten Sie folgendes, wenn Sie einen abfragebasierten eDiscovery-Halteschutz für Dokumente in SharePoint platzieren:

- Ein abfragebasierter Haltezeitraum bewahrt zunächst alle Dokumente auf einer Website für einen kurzen Zeitraum auf, nachdem sie gelöscht wurden. Das heißt, wenn ein Dokument gelöscht wird, wird es in die Erhaltungsarchivbibliothek verschoben, auch wenn es nicht den Kriterien des abfragebasierten Haltezustands entspricht. Gelöschte Dokumente, die keinem abfragebasierten Haltezustand entsprechen, werden jedoch von einem Zeitgeberauftrag entfernt, der die Erhaltungsarchivbibliothek verarbeitet. Der Zeitgeberauftrag wird regelmäßig ausgeführt und vergleicht alle Dokumente in der Erhaltungsspeicherbibliothek mit ihren abfragebasierten eDiscovery-Speicher (und anderen Arten von Aufbewahrungs- und Aufbewahrungsrichtlinien). Der Zeitgeberauftrag löscht die Dokumente, die nicht mit einem abfragebasierten Halteraum übereinstimmen, und behält die dokumente bei, die dies tun.

- Abfragebasierte Aufbewahrungsspeicher sollten nicht zur gezielten Aufbewahrung verwendet werden, z. B. zum Beibehalten von Dokumenten in einem bestimmten Ordner oder einer bestimmten Website oder unter Verwendung anderer standortbasierter Aufbewahrungskriterien. Dies kann unbeabsichtigte Ergebnisse haben. Es wird empfohlen, nicht standortbasierte Haltekriterien wie Schlüsselwörter, Datumsbereiche oder andere Dokumenteigenschaften zu verwenden, um Websitedokumente zu erhalten.

## <a name="ediscovery-hold-statistics"></a>eDiscovery-Haltestatistik

Nachdem Sie ein eDiscovery-Halteverbot erstellt haben, werden Informationen zum neuen Halteraum auf der Flyoutseite für den ausgewählten Halteraum angezeigt. Diese Informationen umfassen die Anzahl von Postfächern und Websites, die in einem Archiv gespeichert sind, sowie Statistiken zu den Inhalten, die in einem Haltespeicher platziert wurden, z. B. die Gesamtanzahl und Größe der in der Warteschleife platzierten Elemente und das letzte Mal, zu dem die Haltestatistiken berechnet wurden. Diese Haltestatistiken helfen Ihnen zu ermitteln, wie viele Inhalte im Zusammenhang mit dem Fall aufbewahrt werden.
  
![Halten von Statistiken](../media/eDiscoveryHoldStatistics.png)
  
Beachten Sie die folgenden Punkte zu eDiscovery-Haltestatistiken:
  
- Die Gesamtanzahl der in der Warteschleife platzierten Elemente gibt die Anzahl der Elemente aus allen Inhaltsquellen an, die in der Warteschleife platziert werden. Wenn Sie einen abfragebasierten Halteraum erstellt haben, gibt diese Statistik die Anzahl der Elemente an, die mit der Abfrage übereinstimmen.

- Die Anzahl der In-Hold-Elemente umfasst auch nicht indizierte Elemente, die in den Inhaltsverzeichnissen gefunden wurden. Wenn Sie einen abfragebasierten Halteraum erstellen, werden alle nicht indizierten Elemente in den Inhaltsverzeichnissen in der Warteschleife platziert. Dies umfasst nicht indizierte Elemente, die nicht den Suchkriterien eines abfragebasierten Haltebereichs entsprechen, und nicht indizierte Elemente, die möglicherweise außerhalb einer Datumsbereichsbedingung liegen. Dies ist anders als beim Ausführen einer Suche, bei der nicht indizierte Elemente, die nicht mit der Suchabfrage übereinstimmen oder von einer Datumsbereichsbedingung ausgeschlossen werden, nicht in den Suchergebnissen enthalten sind. Weitere Informationen zu nicht indizierten Elementen finden Sie unter [Teilweise indizierte Elemente](partially-indexed-items-in-content-search.md).

- Sie können die neuesten Haltestatistiken erhalten, indem Sie auf **Statistik** aktualisieren klicken, um eine Suchschätzung erneut ausführen zu können, mit der die aktuelle Anzahl von Elementen im Halteraum berechnet wird.

- Es ist normal, dass die Anzahl der in der Warteschleife gespeicherten Elemente im Laufe der Zeit zunimmt, da Benutzer, deren Postfach oder Website im Archiv ist, in der Regel neue E-Mail-Nachrichten senden oder empfangen und neue Dokumente in SharePoint und OneDrive.

- Wenn ein Exchange-, SharePoint- oder OneDrive-Konto in eine andere Region in einer Multi-Geo-Umgebung verschoben wird, werden die Statistiken für diese Website nicht in die Haltestatistik einbezogen. Der Inhalt an diesen Speicherorten bleibt jedoch erhalten. Wenn ein Postfach oder eine Website in eine andere Region verschoben wird, wird auch die im Archiv angezeigte SMTP-Adresse oder URL nicht automatisch aktualisiert. Sie müssen den Haltemodus bearbeiten und die URL oder SMTP-Adresse aktualisieren, damit die Inhaltsorte erneut in die Haltestatistik aufgenommen werden.

## <a name="search-locations-on-ediscovery-hold"></a>Suchstandorte im eDiscovery-Halteraum

Wenn Sie [in](search-for-content-in-core-ediscovery.md) einem Core eDiscovery-Fall nach Inhalten suchen, können Sie die Suche schnell so konfigurieren, dass nur die Speicherorte durchsucht werden, die dem Fall zugeordnet sind.

Wählen Sie **die Option Speicherorte** im Halteraum aus, um alle Inhaltsstandorte zu durchsuchen, die in der Warteschleife platziert wurden. Wenn der Fall mehrere eDiscovery-Halteorte enthält, werden die Inhaltspositionen aus allen Haltepositionen durchsucht, wenn Sie diese Option auswählen. Wenn ein Inhaltsspeicherort in einem abfragebasierten Haltefeld platziert wurde, werden außerdem nur die Elemente durchsucht, die der Halteabfrage entsprechen, wenn Sie die Suche ausführen. Mit anderen Worten, nur der Inhalt, der sowohl den Haltekriterien als auch den Suchkriterien entspricht, wird mit den Suchergebnissen zurückgegeben. Wenn ein Benutzer z. B. in einen abfragebasierten Fall hold gesetzt wurde, in dem Elemente beibehalten werden, die vor einem bestimmten Datum gesendet oder erstellt wurden, würden nur diese Elemente durchsucht. Dies erfolgt durch Verbinden der Fall-Hold-Abfrage mit der Suchabfrage durch einen **AND-Operator.**

Hier sind einige andere Dinge, die Sie beim Durchsuchen von Speicherorten im eDiscovery-Halteraum beachten sollten:

- Wenn ein Inhaltsspeicherort Teil mehrerer Haltespeicher in demselben Fall  ist, werden die Halteabfragen von OR-Operatoren kombiniert, wenn Sie diesen Inhaltsspeicherort mithilfe der Option Für alle Fallinhalte durchsuchen. Wenn ein Inhaltsspeicherort Teil von zwei unterschiedlichen Haltespeicherorten ist, wobei einer abfragebasierter und der andere ein unendlicher Haltespeicher ist (bei dem alle Inhalte in der Warteschleife platziert werden), ist der Inhalt aufgrund des unendlichen Halteraums auf der Suche.

- Wenn eine Suche so konfiguriert ist, dass Speicherorte im Halteraum durchsucht werden, und Sie in diesem Fall eine eDiscovery-Halteposition ändern (durch Hinzufügen oder Entfernen eines Speicherorts oder Ändern einer Halteabfrage), wird die Suchkonfiguration mit diesen Änderungen aktualisiert. Sie müssen die Suche jedoch erneut ausführen, nachdem das Haltefeld geändert wurde, um die Suchergebnisse zu aktualisieren.

- Wenn mehrere eDiscovery-Halteorte an einem einzigen Speicherort in einem eDiscovery-Fall platziert werden und Sie auswählen, dass Speicherorte im Halteraum durchsucht werden, beträgt die maximale Anzahl von Schlüsselwörtern für diese Suchabfrage 500. Der Grund dafür ist, dass bei der Suche alle abfragebasierten Haltekriterien mithilfe des **OR-Operators kombiniert** werden. Wenn die kombinierten Halteabfragen und die Suchabfrage mehr als 500 Schlüsselwörter enthalten, werden alle Inhalte im Postfach durchsucht, nicht nur der Inhalt, der dem abfragebasierten Fall entspricht.

- Wenn ein eDiscovery-Haltestatus den Status **Ein (Ausstehend)** hat, können Sie die Halteorte weiterhin durchsuchen, während der Haltestatus aktiviert ist.

## <a name="preserve-content-in-microsoft-teams"></a>Beibehalten von Inhalten in Microsoft Teams

Unterhaltungen, die Teil eines Microsoft Teams kanal sind, werden im Postfach gespeichert, das dem Microsoft Team zugeordnet ist. Gleichermaßen werden Dateien, die Teammitglieder in einem Kanal freigeben, auf der SharePoint-Website des Teams gespeichert. Daher müssen Sie das Teampostfach und SharePoint eDiscovery-Archiv platzieren, um Unterhaltungen und Dateien in einem Kanal zu speichern.

Alternativ werden Unterhaltungen, die Teil der Chatliste in Teams sind *(1:1-Chats* oder *1:N-Gruppenchats)* in den Postfächern der Benutzer gespeichert, die am Chat teilnehmen. Und Dateien, die Benutzer in Chatunterhaltungen freigeben, werden im OneDrive des Benutzers gespeichert, der die Datei gemeinsam verwendet. Daher müssen Sie die einzelnen Benutzerpostfächer und OneDrive einem eDiscovery-Archiv hinzufügen, um Unterhaltungen und Dateien in der Chatliste zu erhalten. Es ist eine gute Idee, die Postfächer von Mitgliedern eines Microsoft Teams in einem Archiv zu halten und das Teampostfach und die Website in der Warteschleife zu platzieren.

> [!NOTE]
> Wenn Ihre Organisation über eine Exchange-Hybridbereitstellung verfügt (oder Ihre Organisation eine lokale Exchange-Organisation mit Office 365 synchronisiert) und Microsoft Teams aktiviert hat, können lokale Benutzer die Teams-Chatanwendung verwenden und an 1:1-Chats und 1:N-Gruppenchats teilnehmen. Diese Unterhaltungen werden in einem cloudbasierten Speicher gespeichert, der einem lokalen Benutzer zugeordnet ist. Wenn ein lokales Benutzer in einem eDiscovery-Speicher platziert wird, bleiben Teams Chatinhalte im cloudbasierten Speicher erhalten. Weitere Informationen finden Sie unter [Nach Teams-Chatdaten für lokale Benutzer suchen](search-cloud-based-mailboxes-for-on-premises-users.md).

Weitere Informationen zum Beibehalten von Teams finden Sie unter [Place a Microsoft Teams user or team on legal hold](/MicrosoftTeams/legal-hold).

### <a name="preserve-card-content"></a>Beibehalten von Karteninhalten

Gleichermaßen werden von Apps in Teams-Kanälen, 1:1-Chats und 1:N-Gruppenchats generierte Karteninhalte in Postfächern gespeichert und beibehalten, wenn ein Postfach in einem eDiscovery-Archiv platziert wird. Eine *Karte* ist ein UI-Container für kurze Inhaltsteile. Karten können mehrere Eigenschaften und Anlagen aufweisen und Schaltflächen enthalten, die Kartenaktionen auslösen. Weitere Informationen finden Sie unter [Karten](/microsoftteams/platform/task-modules-and-cards/what-are-cards). Wie bei anderen Teams-Inhalten hängt der Speicherort der Karteninhalte davon ab, wo die Karte verwendet wurde. Inhalte für Karten, die in einem Teams-Kanal verwendet werden, werden im Postfach der Teams-Gruppe gespeichert. Karteninhalte für 1:1- und 1xN-Chats werden in den Postfächern der Chat-Teilnehmer gespeichert.

### <a name="preserve-meeting-and-call-information"></a>Beibehalten von Besprechungs- und Anrufinformationen

Zusammenfassungsinformationen für Besprechungen und Anrufe in einem Teams werden auch in den Postfächern von Benutzern gespeichert, die sich an der Besprechung oder dem Anruf einwählten. Dieser Inhalt wird auch beibehalten, wenn ein eDiscovery-Archiv für Benutzerpostfächer platziert wird.

### <a name="preserve-content-in-private-channels"></a>Beibehalten von Inhalten in privaten Kanälen

Ab Februar 2020 haben wir auch die Möglichkeit aktiviert, Inhalte in privaten Kanälen zu erhalten. Da Chats für private Kanäle in den Postfächern der Chatteilnehmer gespeichert werden, wird ein Benutzerpostfach im eDiscovery-Archiv beibehalten. Wenn ein Benutzerpostfach vor Februar 2020 in einem eDiscovery-Speicher platziert wurde, gilt der Halteraum nun automatisch für nachrichten des privaten Kanals, die in diesem Postfach gespeichert sind. Das Beibehalten von Dateien, die in privaten Kanälen freigegeben sind, wird ebenfalls unterstützt.

### <a name="preserve-wiki-content"></a>Beibehalten von Wikiinhalten

Jeder Team- oder Teamkanal enthält auch ein Wiki zur Notizen- und Zusammenarbeit. Die Wiki-Inhalte werden automatisch in einer Datei im MHT-Format gespeichert. Diese Datei wird in der Dokumentbibliothek für Wiki-Daten auf der SharePoint-Website des Teams gespeichert. Sie können die Wikiinhalte beibehalten, indem Sie die SharePoint des Teams zu einem eDiscovery-Halteraum hinzufügen.

> [!NOTE]
> Die Funktion zum Beibehalten von Wiki-Inhalten für einen Team- oder Teamkanal (wenn Sie die SharePoint-Website des Teams in der Warteschleife platzieren) wurde am 22. Juni 2017 veröffentlicht. Wenn eine Teamwebsite in der Warteschleife ist, werden die Wikiinhalte ab diesem Datum aufbewahrt. Wenn jedoch eine Teamwebsite in der Warteschleife ist und die Wikiinhalte vor dem 22. Juni 2017 gelöscht wurden, wurden die Wikiinhalte nicht beibehalten.

### <a name="office-365-groups"></a>Office 365-Gruppen

Teams baut auf Office 365 Gruppen auf. Daher ist das Office 365 von Gruppen im eDiscovery-Halteraum ähnlich, wenn Teams in der Warteschleife platziert werden.

Beachten Sie folgendes, wenn Sie sowohl Teams als auch Office 365 Gruppen in einem eDiscovery-Halteraum platzieren:

- Wie bereits erläutert, müssen Sie das Postfach und die SharePoint,die einer Gruppe oder einem Team zugeordnet sind, angeben, um Inhalte in Teams- und Office 365-Gruppen in der Warteschleife zu platzieren.

- Führen Sie **das Cmdlet Get-UnifiedGroup** in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) aus, um Eigenschaften für Teams und Office 365 anzeigen. Dies ist eine gute Möglichkeit, um die URL für die Website zu erhalten, die einem Team oder einer Office 365 zugeordnet ist. Mit dem folgenden Befehl werden z. B. ausgewählte Eigenschaften für die Office 365-Gruppe „Geschäftsleitung“ angezeigt:

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Zum Ausführen des **Get-UnifiedGroup**-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde. 
  
- Wenn das Postfach eines Benutzers durchsucht wird, wird nicht jedes Team oder jede Office 365 Gruppe durchsucht, in der der Benutzer Mitglied ist. Wenn Sie ein Team oder eine gruppe Office 365 eDiscovery-Archiv platzieren, werden auch nur das Gruppenpostfach und die Gruppenwebsite in der Warteschleife platziert. Die Postfächer und OneDrive for Business Websites von Gruppenmitgliedern werden nur dann in einem Archiv gespeichert, wenn Sie sie explizit zum eDiscovery-Archiv hinzufügen. Wenn Sie also ein Team oder eine Office 365-Gruppe aus rechtlichen Gründen in der Warteschleife platzieren müssen, sollten Sie die Postfächer und OneDrive Konten von Team- oder Gruppenmitgliedern in derselben Warteschleife hinzufügen.

- Um eine Liste der Mitglieder einer Team- oder Office 365-Gruppe zu erhalten, können Sie die Eigenschaften auf der Seite Gruppen im Microsoft 365 anzeigen.  Alternativ können Sie den folgenden Befehl in Exchange Online-PowerShell ausführen:

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > Zum Ausführen des **Get-UnifiedGroupLinks**-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde.

## <a name="preserve-content-in-onedrive-accounts"></a>Beibehalten von Inhalten in OneDrive Konten

Informationen zum Sammeln einer Liste der URLs für die OneDrive for Business-Websites in Ihrer Organisation, damit Sie sie einem Halte- oder Suchfall hinzufügen können, der einem eDiscovery-Fall zugeordnet ist, finden Sie unter Create a [list of all OneDrive locations in your organization](/onedrive/list-onedrive-urls). Das Skript in diesem Artikel erstellt eine Textdatei, die eine Liste aller OneDrive in Ihrer Organisation enthält. Um dieses Skript ausführen zu können, müssen Sie die SharePoint Online-Verwaltungsshell installieren und verwenden. Achten Sie darauf, die URL für die "MeineWebsite"-Domäne Ihrer Organisation an jede OneDrive-Website anzuhängen, die Sie durchsuchen möchten. Dies ist die Domäne, die Ihr gesamtes OneDrive enthält, z. B. `https://contoso-my.sharepoint.com`. Hier ein Beispiel für die URL der OneDrive-Website eines Benutzers: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

> [!IMPORTANT]
> Die URL für das OneDrive eines Benutzers enthält den Benutzerprinzipalnamen (Z. B. `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). In den seltenen Fällen, in dem der UPN einer Person geändert wird, ändert sich auch die OneDrive-URL, um den neuen UPN zu integrieren. Wenn das OneDrive-Konto eines Benutzers Teil eines eDiscovery-Halteraums ist, alt ist und sein UPN geändert wird, müssen Sie den Halteraum aktualisieren, und Sie müssen den Halteraum aktualisieren und die neue OneDrive-URL des Benutzers hinzufügen und den alten entfernen. Weitere Informationen hierzu finden Sie unter [Wie sich UPN-Änderungen auf die OneDrive-URL auswirken](/onedrive/upn-changes).

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>Entfernen von Inhaltsstandorten aus einem eDiscovery-Halteraum

Nachdem ein Postfach, SharePoint Website oder ein OneDrive aus einem eDiscovery-Archiv entfernt wurde, wird ein *Verzögerungsspeicher* angewendet. Dies bedeutet, dass das tatsächliche Entfernen des Haltezustands um 30 Tage verzögert wird, um zu verhindern, dass Daten dauerhaft von einem Inhaltsspeicherort gelöscht (gelöscht) werden. Dadurch können Administratoren Inhalte suchen oder wiederherstellen, die gelöscht werden, nachdem ein eDiscovery-Haltebereich entfernt wurde. Die Details zur Funktionsweise des Verzögerungsspeichers für Postfächer und Websites unterscheiden sich.

- **Postfächer:** Ein Verzögerungsspeicher wird für ein Postfach platziert, wenn der Assistent für verwaltete Ordner das Postfach das nächste Mal verarbeitet und erkennt, dass ein eDiscovery-Archiv entfernt wurde. Insbesondere wird ein Verzögerungsspeicher auf ein Postfach angewendet, wenn der Assistent für verwaltete Ordner eine der folgenden Postfacheigenschaften auf **True legt:**

   - **DelayHoldApplied:** Diese Eigenschaft gilt für E-Mail-bezogene Inhalte (generiert von Personen, die Outlook und Outlook im Web verwenden), die im Postfach eines Benutzers gespeichert sind.

   - **DelayReleaseHoldApplied:** Diese Eigenschaft gilt für cloudbasierte Inhalte (generiert von nicht Outlook Apps wie Microsoft Teams, Microsoft Forms und Microsoft Yammer), die im Postfach eines Benutzers gespeichert sind. Von einer Microsoft-App generierte Clouddaten werden in der Regel in einem ausgeblendeten Ordner im Postfach eines Benutzers gespeichert.

   Wenn für das Postfach ein Verzögerungsspeicher eingerichtet wird (wenn eine der vorherigen Eigenschaften auf **True** festgelegt ist), gilt das Postfach weiterhin als für eine unbegrenzte Haltedauer, als ob sich das Postfach im Prozesssicherungsverfahren befindet. Nach 30 Tagen läuft die Verzögerungsverzögerung ab, und Microsoft 365 versucht automatisch, die Verzögerungsverzögerung zu entfernen (indem die Eigenschaft DelayHoldApplied oder DelayReleaseHoldApplied auf **False** gesetzt wird), sodass der Halteraum entfernt wird. Nachdem eine dieser Eigenschaften auf **False** festgelegt wurde, werden die entsprechenden Elemente, die zum Entfernen markiert sind, beim nächsten Verarbeiten des Postfachs durch den Assistenten für verwaltete Ordner gelöscht.

   Weitere Informationen finden Sie unter [Verwalten von Postfächern mit angehaltener Aufbewahrungszeit](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

- **SharePoint und OneDrive Websites:** Alle SharePoint oder OneDrive, die in der Aufbewahrungsarchivbibliothek aufbewahrt werden, werden während des 30-tägigen Verzögerungszeitraums nicht gelöscht, nachdem eine Website aus einem eDiscovery-Haltezustand entfernt wurde. Dies ähnelt dem, was geschieht, wenn eine Website aus einer Aufbewahrungsrichtlinie freigegeben wird. Darüber hinaus können Sie diesen Inhalt während des 30-tägigen Verzögerungszeitraums nicht manuell in der Erhaltungsarchivbibliothek löschen. 

   Weitere Informationen finden Sie unter [Freigeben einer Richtlinie für die Aufbewahrung](retention.md#releasing-a-policy-for-retention).

Beim Schließen eines Core eDiscovery-Falls wird auch eine Verzögerungsaufbehebung auf Inhaltsstandorte angewendet, da die Haltepositionen deaktiviert sind, wenn ein Fall geschlossen wird. Weitere Informationen zum Schließen eines Falls finden Sie unter [Close, reopen, and delete a Core eDiscovery case](close-reopen-delete-core-ediscovery-cases.md).

## <a name="ediscovery-hold-limits"></a>eDiscovery-Haltebeschränkungen

In der folgenden Tabelle sind die Grenzwerte für eDiscovery-Fälle und Fallaufbehebungsfälle aufgeführt.

  | Beschreibung der Beschränkung | Grenzwert |
  |:-----|:-----|
  |Maximale Anzahl von Fällen für eine Organisation.  <br/> |Keine Begrenzung  <br/> |
  |Maximale Anzahl der eDiscovery-Haltewerte für eine Organisation.  <br/> |10,000  <br/> |
  |Maximale Anzahl von Postfächern in einem einzigen eDiscovery-Archiv. Dieser Grenzwert umfasst die gesamtzahl der Benutzerpostfächer und die Postfächer, die Microsoft 365 Gruppen, Microsoft Teams und Yammer zugeordnet sind.  <br/> |1,000  <br/> |
  |Maximale Anzahl von Websites in einem einzigen eDiscovery-Halteraum. Dieser Grenzwert umfasst die gesamtzahl der OneDrive for Business Websites, SharePoint Websites und die Websites, die Microsoft 365-, Microsoft Teams- und Yammer-Gruppen zugeordnet sind.  <br/> |100  <br/> |
  |Maximale Anzahl von Fällen, die auf der eDiscovery-Startseite angezeigt werden, und die maximale Anzahl von Elementen, die auf den Registerkarten Halte-, Such- und Exportregisterkarten in einem Fall angezeigt werden. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> Zum Anzeigen einer Liste mit mehr als 1.000 Fällen, Halte-, Such- oder Exporten können Sie das entsprechende Office 365 Security & Compliance PowerShell-Cmdlet verwenden:
   >
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)
