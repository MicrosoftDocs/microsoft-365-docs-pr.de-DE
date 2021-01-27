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
description: Sie können einen Haltebereich erstellen, der einem Core eDiscovery-Fall zugeordnet ist, um Inhalte zu erhalten, die für eine Untersuchung relevant sein können.
ms.openlocfilehash: 76ea455af0a7600cd901bdcdaeb0e4b15ef9bc43
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988149"
---
# <a name="create-an-ediscovery-hold"></a>Erstellen eines eDiscovery-Speichers

Sie können einen Core eDiscovery-Fall verwenden, um Haltebereich zu erstellen, um Inhalte zu erhalten, die möglicherweise für den Fall relevant sind. Sie können die #A0 und OneDrive for #A1 von Personen, die Sie in dem Fall untersuchen, in einem Archiv platzieren. Sie können auch die Postfächer und Websites, die Microsoft Teams, Office 365-Gruppen und -Gruppen zugeordnet sind, in Yammer platzieren. Wenn Sie Inhaltsspeicherorte im Haltespeicherort platzieren, werden Inhalte aufbewahrt, bis Sie den Haltespeicherort entfernen oder bis Sie den Haltespeicherort löschen.

Nachdem Sie ein eDiscovery-Hold erstellt haben, kann es bis zu 24 Stunden dauern, bis die Schleife wirksam wird. 

Wenn Sie einen Haltebereich erstellen, haben Sie die folgenden Optionen, um den Bereich des Inhalts zu ändern, der an den angegebenen Inhaltspositionen beibehalten wird:
  
- Sie erstellen einen unendlichen Halteraum, in dem alle Inhalte an den angegebenen Speicherorten im Halteschleifen platziert werden. Alternativ können Sie ein abfragebasiertes Haltefeld erstellen, in dem nur der Inhalt an den angegebenen Speicherorten, der einer Suchabfrage entspricht, in der Warteschleife platziert wird.

- Sie können einen Datumsbereich angeben, damit nur der Inhalt beibehalten wird, der innerhalb dieses Datumsbereichs gesendet, empfangen oder erstellt wurde. Alternativ können Sie alle Inhalte an bestimmten Speicherorten unabhängig davon, wann sie gesendet, empfangen oder erstellt wurden, enthalten.
  
## <a name="how-to-create-an-ediscovery-hold"></a>Erstellen eines eDiscovery-Halteschleifens

So erstellen Sie ein eDiscovery-Hold, das einem Core eDiscovery-Fall zugeordnet ist:
  
1. Wechseln Sie zu und melden Sie sich mit den Anmeldeinformationen für das Benutzerkonto an, dem die entsprechenden [https://compliance.microsoft.com](https://compliance.microsoft.com) eDiscovery-Berechtigungen zugewiesen wurden.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Centers auf "Alle anzeigen" **und** dann auf **eDiscovery > Core**.

3. Wählen Sie auf der **Core eDiscovery-Seite** den Fall aus, in dem Sie den Haltebereich erstellen möchten, und klicken Sie dann auf **"Fall öffnen".**

4. Klicken Sie **auf der Startseite** für den Fall auf die Registerkarte **"Halte halte".**
  
5. Klicken Sie **auf der Halteseite** auf **"Erstellen".**

6. Geben Sie **auf der Seite "Ihren Halteassistenten** benennen" einen Namen für die Halteschleife ein, fügen Sie eine optionale Beschreibung hinzu, und klicken Sie dann auf **"Weiter".** Der Name der Halteschleife muss in Ihrer Organisation eindeutig sein.

7. Wählen Sie **auf der Seite "Speicherorte** für Inhalte" die Speicherorte für Inhalte aus, die Sie in der Warteschleife platzieren möchten. Sie können Postfächer, Websites und öffentliche Ordner im Archiv platzieren.

    ![Wählen Sie Inhaltsspeicherorte aus, die im Haltebereich platziert werden sollen.](../media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   1. **Postfachspeicherorte** : Klicken Sie auf **"Benutzer, Gruppen** oder Teams auswählen", und klicken Sie dann erneut auf "Benutzer, Gruppen oder Teams **auswählen",** um die Postfächer anzugeben, die in der Warteschleife gespeichert werden. Verwenden Sie das Suchfeld, um nach Benutzerpostfächern und Verteilergruppen zu suchen (um die Postfächer von Gruppenmitgliedern im Archiv zu halten). Sie können auch das zugeordnete Postfach für ein Microsoft-Team, eine Office 365-Gruppe oder eine Gruppe Yammer platzieren. Aktivieren Sie das Kontrollkästchen Benutzer, Gruppe, Team, klicken **Sie** auf "Auswählen" und dann auf **"Fertig".**

   1. **Websitestandorte** – Klicken Sie **auf** "Websites auswählen" und dann erneut auf "Websites **auswählen",** um SharePoint- und #A0 anzugeben, die in der Warteschleife gespeichert werden. Geben Sie die URL für jede Website ein, für die Sie die Schleife in der Warteschleife platzieren möchten. Sie können auch die URL für die SharePoint-Website für ein Microsoft-Team, eine Office 365-Gruppe oder eine Yammer hinzufügen. Klicken **Sie auf "Auswählen"** und dann auf **"Fertig".**
  
   1. **Öffentliche Exchange-Ordner.** Verschieben Sie das Umschaltersteuerelement in die Stellung ![ ](../media/scc-toggle-on.png) **"Alle",** um alle öffentlichen Ordner in Ihrer Exchange Online-Organisation in die Warteschleife zu setzen. Sie können keine bestimmten öffentlichen Ordner auswählen, die in die Warteschleife verschoben werden. Lassen Sie den Umschalter auf **"None"** festgelegt, wenn Sie öffentliche Ordner nicht zurückhalten möchten.

   > [!NOTE]
   > Sie müssen dem Haltespeicherort mindestens einen Inhaltsspeicherort hinzufügen. Andernfalls zeigt die eDiscovery-Hold-Statik, dass keine Elemente in der Warteschleife sind.

8. Wenn Sie mit dem Hinzufügen von Inhaltsstandorten zum Halte halte fertig sind, klicken Sie auf **"Weiter".**

9. Führen Sie die folgenden Schritte aus, um einen abfragebasierten Halteraum mit Bedingungen zu erstellen. Klicken Sie andernfalls auf "Weiter", um alle Inhalte an den angegebenen Speicherorten zu **erhalten.**

    ![Erstellen eines abfragebasierten Halteraums mit Bedingungen](../media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    1. Geben Sie in das Feld unter **Schlüsselwörter** eine Suchabfrage ein, sodass nur der Inhalt, der die Suchkriterien erfüllt, beibehalten wird. Sie können Schlüsselwörter, E-Mail-Nachrichteneigenschaften oder Dokumenteigenschaften wie Dateinamen angeben. Sie können auch komplexere Abfragen verwenden, die einen booleschen Operator verwenden, z. B. **AND**, **OR** oder **NOT**.

    1. Klicken **Sie auf Bedingungen hinzufügen,** um eine oder mehrere Bedingungen hinzuzufügen, um die Suchabfrage für den Halteraum zu einengt. Jede Bedingung fügt der KQL-Suchabfrage eine Klausel hinzu, die beim Erstellen des Haltezustands erstellt und ausgeführt wird. Sie können beispielsweise einen Datumsbereich angeben, sodass E-Mail- oder Websitedokumente, die innerhalb des Datumsbereichs erstellt wurden, in einem Haltebereich platziert werden. Eine Bedingung ist logisch mit der Schlüsselwortabfrage  (im Feld "Schlüsselwörter" angegeben) durch den Operator **AND** verbunden. Das bedeutet, dass Elemente sowohl die Schlüsselwortabfrage als auch die Bedingung erfüllen müssen, die beibehalten werden soll.

    Weitere Informationen zum Erstellen einer Suchabfrage und zum Verwenden von Bedingungen finden Sie unter [Schlüsselwortabfragen und Suchbedingungen für die Inhaltssuche.](keyword-queries-and-search-conditions.md)

10. Klicken Sie nach dem Konfigurieren eines abfragebasierten Halteraums auf **"Weiter".**

11. Überprüfen Sie Ihre Einstellungen (und bearbeiten Sie sie bei Bedarf), und klicken Sie dann **auf "Diesen Haltemodus erstellen".**

## <a name="query-based-holds-placed-on-site-documents"></a>Abfragebasierte Halte halte für Websitedokumente

Beachten Sie folgendes, wenn Sie ein abfragebasiertes eDiscovery-Dokument für Dokumente in SharePoint-Websites platzieren:

- Ein abfragebasierter Halteraum bewahrt zunächst alle Dokumente auf einer Website für einen kurzen Zeitraum auf, nachdem sie gelöscht wurden. Das heißt, wenn ein Dokument gelöscht wird, wird es auch dann in das dokumentarchiv verschoben, wenn es nicht den Kriterien des abfragebasierten Halteschutzes entspricht. Gelöschte Dokumente, die keinem abfragebasierten Haltezustand entsprechen, werden jedoch von einem Zeitgeberauftrag entfernt, der das aufbewahrungsbasierte Dokumentarchiv verarbeitet. Der Zeitgeberauftrag wird regelmäßig ausgeführt und vergleicht alle Dokumente im dokumentbasierten Dokumentarchiv mit Ihren abfragebasierten eDiscovery-Speichern (und anderen Arten von Halte- und Aufbewahrungsrichtlinien). Der Zeitgeberauftrag löscht die Dokumente, die keinem abfragebasierten Halteraum entsprechen, und behält die Dokumente bei.

- Abfragebasierte Aufbewahrungsspeicher sollten nicht verwendet werden, um eine gezielte Aufbewahrung durchzuführen, z. B. das Beibehalten von Dokumenten in einem bestimmten Ordner oder einer bestimmten Website oder mithilfe anderer speicherortbasierter Aufbewahrungskriterien. Dies kann zu unbeabsichtigten Ergebnissen führen. Es wird empfohlen, nicht standortbasierte Haltekriterien wie Stichwörter, Datumsbereiche oder andere Dokumenteigenschaften zu verwenden, um Websitedokumente zu erhalten.

## <a name="ediscovery-hold-statistics"></a>eDiscovery-Haltestatistiken

Nachdem Sie ein eDiscovery-Haltefenster erstellt haben, werden Auf der Flyoutseite für den ausgewählten Halteraum Informationen zum neuen Halte hold angezeigt. Zu diesen Informationen gehören die Anzahl der Postfächer und Websites, die in einem Archiv platziert wurden, sowie Statistiken zu den Inhalten, die in einem Archiv platziert wurden, z. B. die Gesamtanzahl und Größe der in einem Archiv platzierten Elemente und der Zeitpunkt der letzten Berechnung der Haltestatistik. Mithilfe dieser Haltestatistiken können Sie ermitteln, wie viele Inhalte im Zusammenhang mit dem Fall aufbewahrt werden.
  
![Haltestatistiken](../media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
Beachten Sie die folgenden Punkte bei eDiscovery-Haltestatistiken:
  
- Die Gesamtzahl der in der Warteschleife platzierten Elemente gibt die Anzahl der Elemente aus allen Inhaltsquellen an, die in die Warteschleife gestellt wurden. Wenn Sie einen abfragebasierten Halteraum erstellt haben, gibt diese Statistik die Anzahl der Elemente an, die mit der Abfrage übereinstimmen.

- Die Anzahl der In-Hold-Elemente umfasst auch nicht indizierte Elemente, die sich in den Inhaltsverzeichnissen befinden. Wenn Sie einen abfragebasierten Halteraum erstellen, werden alle nicht indizierten Elemente in den Inhaltsverzeichnissen in die Warteschleife gestellt. Dazu gehören nicht indizierte Elemente, die nicht den Suchkriterien eines abfragebasierten Haltebereichs entsprechen, sowie nicht indizierte Elemente, die möglicherweise außerhalb einer Datumsbereichsbedingung liegen. Dies ist anders als beim Ausführen einer Suche, bei der nicht indizierte Elemente, die nicht mit der Suchabfrage übereinstimmen oder von einer Datumsbereichsbedingung ausgeschlossen werden, nicht in den Suchergebnissen enthalten sind. Weitere Informationen zu nicht indizierten Elementen finden Sie unter [Teilweise indizierte Elemente.](partially-indexed-items-in-content-search.md)

- Sie können die neuesten Haltestatistiken erhalten, indem Sie auf **"Statistik** aktualisieren" klicken, um eine Suchschätzung erneut ausführen zu können, die die aktuelle Anzahl von Elementen berechnet, die in der Warteschleife enthalten sind.

- Es ist normal, dass die Anzahl der In-Archiv-Elemente im Laufe der Zeit zunimmt, da Benutzer, deren Postfach oder Website in der Warteschleife sind, in der Regel neue E-Mail-Nachrichten senden oder empfangen und neue Dokumente in SharePoint und OneDrive erstellen.

- Wenn ein Exchange-Postfach, eine #A0 oder ein #A1 in eine andere Region in einer Multi-Geo-Umgebung verschoben wird, werden die Statistiken für diese Website nicht in die Haltebereichsstatistik aufgenommen. Der Inhalt an diesen Speicherorten bleibt jedoch erhalten. Wenn ein Postfach oder eine Website in eine andere Region verschoben wird, wird auch die im Haltebereich angezeigte SMTP-Adresse oder URL nicht automatisch aktualisiert. Sie müssen den Haltemodus bearbeiten und die URL oder die SMTP-Adresse aktualisieren, damit die Inhaltsorte wieder in die Haltestatistik aufgenommen werden.

## <a name="search-locations-on-ediscovery-hold"></a>Suchorte im eDiscovery-Haltefeld

Wenn Sie [in](search-for-content-in-core-ediscovery.md) einem Core eDiscovery-Fall nach Inhalten suchen, können Sie die Suche schnell so konfigurieren, dass nur die Inhaltsorte durchsucht werden, die für den Fall in einem Haltebereich platziert wurden.

![Halteorte](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)

Wählen Sie **die Option "Speicherorte im Haltefeld"** aus, um alle Inhaltsorte zu durchsuchen, die in die Warteschleife gestellt wurden. Wenn der Fall mehrere eDiscovery-Halteorte enthält, werden die Inhaltsorte aus allen Haltepositionen durchsucht, wenn Sie diese Option auswählen. Wenn ein Inhaltsspeicherort in einem abfragebasierten Haltefeld platziert wurde, werden beim Ausführen der Suche nur die Elemente durchsucht, die der Halteabfrage entsprechen. Mit anderen Worten, mit den Suchergebnissen wird nur der Inhalt zurückgegeben, der sowohl den Halte- als auch den Suchkriterien entspricht. Wenn beispielsweise ein Benutzer in ein abfragebasiertes Fallgewahrer gestellt wurde, in dem Elemente beibehalten werden, die vor einem bestimmten Datum gesendet oder erstellt wurden, werden nur diese Elemente durchsucht. Dies wird erreicht, indem die Fall-Hold-Abfrage und die Suchabfrage durch einen **AND-Operator verbunden** werden.

Hier sind einige andere Dinge, die Sie beim Durchsuchen von Speicherorten im eDiscovery-Halteraum beachten sollten:

- Wenn ein Inhaltsspeicherort Zu mehreren Haltespeicherorten innerhalb desselben Falls gehört, werden die Halteabfragen von **OR-Operatoren** kombiniert, wenn Sie diesen Speicherort mit der Option "All Case Content" durchsuchen. Ebenso gilt: Wenn ein Inhaltsspeicherort Teil von zwei verschiedenen Haltespeichern ist, wobei einer abfragebasierter und der andere ein unendlicher Haltespeicher ist (wo alle Inhalte in der Warteschleife platziert werden), wird der inhalt aufgrund des unendlichen Haltefelds durchsucht.

- Wenn eine Suche so konfiguriert ist, dass Speicherorte durchsucht werden, die sich in der Warteschleife befinden, und Sie dann ein eDiscovery-Haltefeld in dem Fall ändern (durch Hinzufügen oder Entfernen eines Speicherorts oder Ändern einer Halteabfrage), wird die Suchkonfiguration mit diesen Änderungen aktualisiert. Sie müssen die Suche jedoch erneut ausführen, nachdem die Halteschleife geändert wurde, um die Suchergebnisse zu aktualisieren.

- Wenn mehrere eDiscovery-Halteorte an einem einzigen Speicherort in einem eDiscovery-Fall platziert werden und Sie auswählen, dass Speicherorte im Haltefeld durchsucht werden, beträgt die maximale Anzahl von Schlüsselwörtern für diese Suchabfrage 500. Der Grund dafür ist, dass die Suche alle abfragebasierten Halte halte mit dem Operator **OR** kombiniert. Wenn die kombinierten Archivabfragen und die Suchabfrage mehr als 500 Schlüsselwörter enthalten, wird der ganze Inhalt des Postfachs durchsucht, nicht nur der Inhalt, der den abfragebasierten Fallspeichern entspricht.

- Wenn ein eDiscovery-Haltestatus den Status "Aktivieren" **hat,** können Sie die Haltestatus weiterhin durchsuchen, während der Haltestatus aktiviert ist.

## <a name="preserve-content-in-microsoft-teams"></a>Inhalte in Microsoft Teams beibehalten

Unterhaltungen, die Teil eines Microsoft Teams-Kanals sind, werden in dem Postfach gespeichert, das dem Microsoft Team zugeordnet ist. Gleichermaßen werden Dateien, die Teammitglieder in einem Kanal freigeben, auf der SharePoint-Website des Teams gespeichert. Daher müssen Sie das Teampostfach und die SharePoint-Website im eDiscovery-Archiv platzieren, um Unterhaltungen und Dateien in einem Kanal zu speichern.

Alternativ werden Unterhaltungen, die Teil der Chatliste in Teams sind (als *1:1-Chats* oder *1:N-Gruppenchats* bezeichnet), in den Postfächern der Benutzer gespeichert, die am Chat teilnehmen. Und Dateien, die Benutzer in Chatunterhaltungen freigeben, werden im #A0 des Benutzers gespeichert, der die Datei gemeinsam verwendet. Daher müssen Sie die einzelnen Benutzerpostfächer und #A0 einem eDiscovery-Archiv hinzufügen, um Unterhaltungen und Dateien in der Chatliste zu speichern. Es empfiehlt sich, die Postfächer von Mitgliedern eines Microsoft Teams in einem Archiv zu platzieren und das Teampostfach und die Website in der Warteschleife zu platzieren.

> [!IMPORTANT]
> In einer cloudbasierten Organisation müssen Benutzer, die an Unterhaltungen teilnehmen, die Teil der Chatliste in Teams sind, über ein Exchange Online-Postfach verfügen, damit Chatunterhaltungen beibehalten werden können, wenn das Postfach in einem eDiscovery-Archiv platziert wird. Der Grund dafür ist, dass Unterhaltungen, die Teil der Chatliste sind, in den cloudbasierten Postfächern der Chatteilnehmer gespeichert werden. Wenn ein Chatteilnehmer kein Exchange Online-Postfach hat, können Sie diese Chatunterhaltungen nicht beibehalten. Beispielsweise können Benutzer mit einem lokalen Postfach in einer Hybridbereitstellung von Exchange an Unterhaltungen teilnehmen, die Teil der Chatliste in Teams sind. In diesem Fall können Inhalte aus dieser Unterhaltung jedoch nicht beibehalten werden, da diese Benutzer nicht über cloudbasierte Postfächer verfügen, die in einem Archiv platziert werden können.

Weitere Informationen zum Beibehalten von Microsoft Teams-Inhalten finden Sie unter "Platzieren eines Microsoft Teams-Benutzers oder -Teams [in einem gesetzlichen Verfahren".](https://docs.microsoft.com/MicrosoftTeams/legal-hold)

### <a name="preserve-card-content"></a>Beibehalten des Karteninhalts

Ebenso werden von Apps in Teams-Kanälen generierte Karteninhalte, 1:1-Chats und 1:N-Gruppenchats in Postfächern gespeichert und beibehalten, wenn ein Postfach in einem eDiscovery-Archiv platziert wird. Eine *Karte* ist ein Benutzeroberflächencontainer für kurze Inhalte. Karten können mehrere Eigenschaften und Anlagen aufweisen und Schaltflächen enthalten, die Kartenaktionen auslösen. Weitere Informationen finden Sie unter [Karten](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards). Wie andere Teams-Inhalte, in denen Karteninhalte gespeichert werden, basieren auf dem Ort, an dem die Karte verwendet wurde. Inhalte für Karten, die in einem Kanal von Teams verwendet werden, werden im Gruppenpostfach von Teams gespeichert. Karteninhalte für 1:1- und 1xN-Chats werden in den Postfächern der Chatteilnehmer gespeichert.

### <a name="preserve-meeting-and-call-information"></a>Beibehalten von Besprechungs- und Anrufinformationen

Zusammenfassungsinformationen für Besprechungen und Anrufe in einem Teams-Kanal werden auch in den Postfächern der Benutzer gespeichert, die sich an der Besprechung oder dem Anruf einwählten. Dieser Inhalt wird auch beibehalten, wenn ein eDiscovery-Archiv für Benutzerpostfächer aktiviert wird.

### <a name="preserve-content-in-private-channels"></a>Inhalte in privaten Kanälen beibehalten

Ab Februar 2020 haben wir auch die Möglichkeit aktiviert, Inhalte in privaten Kanälen zu erhalten. Da Chats in privaten Kanälen in den Postfächern der Chatteilnehmer gespeichert werden, werden chats im privaten Kanal beibehalten, wenn ein Benutzerpostfach in das eDiscovery-Archiv verschoben wird. Wenn ein Benutzerpostfach vor Februar 2020 in einem eDiscovery-Archiv platziert wurde, gilt das Archiv jetzt automatisch für nachrichten, die in diesem Postfach gespeichert sind. Das Beibehalten von Dateien, die in privaten Kanälen freigegeben sind, wird ebenfalls unterstützt.

### <a name="preserve-wiki-content"></a>Beibehalten von Wiki-Inhalten

Jeder Team- oder Teamkanal enthält auch ein Wiki für notizen und Zusammenarbeit. Die Wiki-Inhalte werden automatisch in einer Datei im MHT-Format gespeichert. Diese Datei wird in der Dokumentbibliothek für Wiki-Daten auf der SharePoint-Website des Teams gespeichert. Sie können die Wiki-Inhalte beibehalten, indem Sie die SharePoint-Website des Teams zu einem eDiscovery-Haltepunkt hinzufügen.

> [!NOTE]
> Die Funktion zum Beibehalten von Wiki-Inhalten für einen Team- oder Teamkanal (wenn Sie die SharePoint-Website des Teams in die Warteschleife setzen) wurde am 22. Juni 2017 veröffentlicht. Wenn eine Teamwebsite in der Warteschleife ist, werden die Wiki-Inhalte ab diesem Datum aufbewahrt. Wenn eine Teamwebsite jedoch in der Warteschleife ist und die Wiki-Inhalte vor dem 22. Juni 2017 gelöscht wurden, wurden die Wiki-Inhalte nicht beibehalten.

### <a name="office-365-groups"></a>Office 365-Gruppen

Teams baut auf Office 365-Gruppen auf. Daher ist es ähnlich, Office 365-Gruppen in das eDiscovery-Hold zu setzen, um Die Inhalte von Teams in die Warteschleife zu setzen.

Beachten Sie folgendes, wenn Sie sowohl Teams als auch Office 365-Gruppen in einem eDiscovery-Halteschutz platzieren:

- Wie bereits erläutert, müssen Sie das Postfach und die SharePoint-Website angeben, die einer Gruppe oder einem Team zugeordnet sind, um Inhalte in Teams und Office 365-Gruppen zu archivieren.

- Führen Sie **das Cmdlet "Get-UnifiedGroup"** in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) aus, um Eigenschaften für Teams und Office 365-Gruppen anzeigen. Dies ist eine gute Möglichkeit, um die URL für die Website zu erhalten, die einem Team oder einer Office 365-Gruppe zugeordnet ist. Mit dem folgenden Befehl werden z. B. ausgewählte Eigenschaften für die Office 365-Gruppe „Geschäftsleitung“ angezeigt:

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Zum Ausführen des **Get-UnifiedGroup**-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde. 
  
- Wenn das Postfach eines Benutzers durchsucht wird, werden keine Teams oder Office 365-Gruppen durchsucht, in denen der Benutzer Mitglied ist. Ebenso werden beim Platzieren eines eDiscovery-Archivs für ein Team oder eine Office 365-Gruppe nur das Gruppenpostfach und die Gruppenwebsite im Archiv platziert. Die Postfächer und OneDrive for #A0 von Gruppenmitgliedern werden nicht in das Archiv gestellt, es sei denn, Sie fügen sie explizit dem eDiscovery-Archiv hinzu. Wenn Sie also ein Team oder eine Office 365-Gruppe aus rechtlichen Gründen in der Warteschleife platzieren müssen, erwägen Sie das Hinzufügen der Postfächer und #A0 von Team- oder Gruppenmitgliedern in demselben Archiv.

- Um eine Liste der Mitglieder eines Teams oder einer Office 365-Gruppe zu erhalten, können Sie die Eigenschaften auf der Seite "Gruppen" im Microsoft 365 Admin Center anzeigen.  Alternativ können Sie den folgenden Befehl in Exchange Online-PowerShell ausführen:

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > Zum Ausführen des **Get-UnifiedGroupLinks**-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde.

## <a name="preserve-content-in-onedrive-accounts"></a>Beibehalten von Inhalten in #A0

Informationen zum Sammeln einer Liste der URLs für die OneDrive for #A0 in Ihrer Organisation, damit Sie sie einem Halte- oder Suchfeld hinzufügen können, das einem eDiscovery-Fall zugeordnet ist, finden Sie unter Erstellen einer Liste aller #A1 [in](https://docs.microsoft.com/onedrive/list-onedrive-urls)Ihrer Organisation. Das Skript in diesem Artikel erstellt eine Textdatei, die eine Liste aller #A0 in Ihrer Organisation enthält. Um dieses Skript ausführen zu können, müssen Sie die SharePoint Online-Verwaltungsshell installieren und verwenden. Achten Sie darauf, die URL für die "MeineWebsite"-Domäne Ihrer Organisation an jede OneDrive-Website anzuhängen, die Sie durchsuchen möchten. Dies ist die Domäne, die Ihr gesamtes OneDrive enthält, z. B. `https://contoso-my.sharepoint.com`. Hier ein Beispiel für die URL der OneDrive-Website eines Benutzers: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

> [!IMPORTANT]
> Die URL für das #A0 eines Benutzers enthält den Benutzerprinzipalnamen (UPN) (z. B. `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). In dem seltenen Fall, dass der UPN einer Person geändert wird, ändert sich auch die OneDrive-URL, um den neuen UPN zu integrieren. Wenn das #A0 eines Benutzers Teil eines eDiscovery-Speichers ist, das alte und der UPN geändert wird, müssen Sie das Haltebehalten aktualisieren und die neue OneDrive-URL des Benutzers hinzufügen und die alte url entfernen. Weitere Informationen hierzu finden Sie unter [Wie sich UPN-Änderungen auf die OneDrive-URL auswirken](https://docs.microsoft.com/onedrive/upn-changes).

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>Entfernen von Inhaltsstandorten aus einem eDiscovery-Halteraum

Nachdem ein Postfach, eine #A0 oder ein #A1 aus einem eDiscovery-Archiv entfernt wurde, wird eine *Verzögerungsverzögerung* angewendet. Dies bedeutet, dass das tatsächliche Entfernen des Haltezustands um 30 Tage verzögert wird, um zu verhindern, dass Daten dauerhaft aus einem Inhaltsspeicherort gelöscht werden. Dadurch können Administratoren Inhalte suchen oder wiederherstellen, die gelöscht werden, nachdem ein eDiscovery-Haltebereich entfernt wurde. Die Details zur Funktionsweise der Verzögerungsspeicherung für Postfächer und Websites unterscheiden sich.

- **Postfächer:** Bei der nächsten Verarbeitet des Postfachs durch den Assistenten für verwaltete Ordner wird ein Verzögerungsspeicher für ein Postfach aktiviert, und es wird erkannt, dass ein eDiscovery-Archiv entfernt wurde. Insbesondere wird eine Verzögerungsverzögerung auf ein Postfach angewendet, wenn der Assistent für verwaltete Ordner eine der folgenden Postfacheigenschaften auf **"True" setzt:**

   - **DelayHoldApplied:** Diese Eigenschaft gilt für E-Mail-bezogene Inhalte (generiert von Personen, die Outlook und Outlook im Web verwenden), die im Postfach eines Benutzers gespeichert sind.

   - **DelayReleaseHoldApplied:** Diese Eigenschaft gilt für cloudbasierte Inhalte (generiert von Nicht-Outlook-Apps wie Microsoft Teams, Microsoft Forms und Microsoft Yammer), die im Postfach eines Benutzers gespeichert sind. Von einer Microsoft-App generierte Clouddaten werden in der Regel in einem ausgeblendeten Ordner im Postfach eines Benutzers gespeichert.

   Wenn eine Verzögerungsverzögerung für das Postfach aktiviert wird (wenn eine der vorherigen Eigenschaften auf **"True"** festgelegt ist), gilt das Postfach weiterhin als für unbegrenzte Zeit in der Warteschleife, als ob für das Postfach das Rechtsstreitigkeiten aktiviert war. Nach 30 Tagen läuft die Verzögerungsverzögerung ab, und Microsoft 365 versucht automatisch, die Verzögerungsverzögerung zu entfernen (indem die Eigenschaft "DelayHoldApplied" oder "DelayReleaseHoldApplied" auf **"False"** gesetzt wird), sodass der Halteraum entfernt wird. Nachdem eine dieser Eigenschaften auf **"False"** festgelegt wurde, werden die entsprechenden Elemente, die zum Entfernen markiert sind, gelöscht, wenn das Postfach das nächste Mal vom Assistenten für verwaltete Ordner verarbeitet wird.

   Weitere Informationen finden Sie unter [Verwalten von Postfächern mit angehaltener Aufbewahrungszeit](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

- **SharePoint- und OneDrive-Websites:** Alle SharePoint- oder OneDrive-Inhalte, die im aufbewahrungsgebewaisten Dokumentarchiv aufbewahrt werden, werden während der 30-tägigen Verzögerungszeit nicht gelöscht, nachdem eine Website aus einem eDiscovery-Speicher entfernt wurde. Dies ähnelt dem, was geschieht, wenn eine Website aus einer Aufbewahrungsrichtlinie freigegeben wird. Darüber hinaus können Sie diesen Inhalt während der 30-tägigen Verzögerungszeit nicht manuell im aufbewahrungsgebewahen Dokumentarchiv löschen. 

   Weitere Informationen finden Sie unter [Freigeben einer Richtlinie für die Aufbewahrung.](retention.md#releasing-a-policy-for-retention)

Beim Schließen eines Core eDiscovery-Falls wird auch eine Verzögerungsverzögerung auf Die Haltebereichsorte angewendet, da die Haltebereichsschalten deaktiviert werden, wenn ein Fall geschlossen wird. Weitere Informationen zum Schließen eines Falls finden Sie unter [Close, reopen, and delete a Core eDiscovery case](close-reopen-delete-core-ediscovery-cases.md).

## <a name="ediscovery-hold-limits"></a>eDiscovery-Haltelimits

In der folgenden Tabelle sind die Grenzwerte für eDiscovery-Fälle und Fallaufbebegrenzung aufgeführt.

  | Beschreibung der Beschränkung | Grenze |
  |:-----|:-----|
  |Maximale Anzahl von Fällen für eine Organisation  <br/> |Keine Begrenzung  <br/> |
  |Maximale Anzahl von eDiscovery-Halte halte für eine Organisation  <br/> |10.000  <br/> |
  |Maximale Anzahl von Postfächern in einem einzigen eDiscovery-Archiv  <br/> |1,000  <br/> |
  |Maximale Anzahl von SharePoint- und OneDrive for #A0 in einem einzigen eDiscovery-Speicher  <br/> |100  <br/> |
  |Die maximale Anzahl von Fällen, die auf der eDiscovery-Startseite angezeigt werden, und die maximale Anzahl von Elementen, die auf den Registerkarten "Halte halte", "Suchen" und "Exportieren" in einem Fall angezeigt werden. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> Um eine Liste mit mehr als 1.000 Fällen, Halte-, Such- oder Exporten anzeigen zu können, können Sie das entsprechende Office 365 Security & Compliance -PowerShell-Cmdlet verwenden:
   >
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
