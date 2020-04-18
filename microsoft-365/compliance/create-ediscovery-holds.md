---
title: Erstellen von eDiscovery-Archiven in einem zentralen eDiscovery-Fall
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
description: Sie können einen Haltebereich erstellen, der einem zentralen eDiscovery-Fall zugeordnet ist, um Inhalte beizubehalten, die möglicherweise für eine Untersuchung relevant sind.
ms.openlocfilehash: 6405dac51c34163f8eadb359d9c29f1aa81a1b82
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551459"
---
# <a name="create-an-ediscovery-hold"></a>Erstellen eines eDiscovery-Speichers

Sie können einen zentralen eDiscovery-Fall zum Erstellen von Haltebereichen verwenden, um Inhalte beizubehalten, die möglicherweise für den Fall relevant sind. Sie können die Exchange-Postfächer und OneDrive für Unternehmen Konten von Personen, die Sie in dem Fall untersuchen, aufbewahren. Sie können auch die Postfächer und Websites, die Microsoft Teams, Office 365 Gruppen und Jammer Gruppen zugeordnet sind, aufbewahren. Wenn Sie inhaltsspeicherorte in der Warteschleife platzieren, wird der Inhalt beibehalten, bis Sie den Haltebereich vom Inhaltsspeicherort entfernen oder bis Sie den Haltebereich löschen.

Nachdem Sie einen eDiscovery-Haltestatus erstellt haben, kann es bis zu 24 Stunden dauern, bis der Haltestatus wirksam wird. 

Wenn Sie einen Haltebereich erstellen, haben Sie die folgenden Optionen, um den Inhalt zu belegen, der an den angegebenen Inhaltsspeicherorten aufbewahrt wird:
  
- Sie erstellen einen unbegrenzten Haltebereich, in dem der gesamte Inhalt aufbewahrt wird. Alternativ können Sie einen abfragebasierten Speicher erstellen, in dem nur der Inhalt, der mit einer Suchabfrage übereinstimmt, in die Warteschleife gestellt wird.

- Sie können einen Datumsbereich angeben, um nur den Inhalt beizubehalten, der innerhalb dieses Datumsbereichs gesendet, empfangen oder erstellt wurde. Alternativ können Sie alle Inhalte speichern, unabhängig davon, wann Sie gesendet, empfangen oder erstellt wurden.

> [!NOTE]
> Sie können maximal 10.000 eDiscovery für alle zentralen eDiscovery-Fälle in Ihrer Organisation bereithalten.
  
## <a name="how-to-create-an-ediscovery-hold"></a>Erstellen eines eDiscovery-Haltestatus

So erstellen Sie eine eDiscovery-Aufbewahrungsstelle, die einem zentralen eDiscovery-Fall zugeordnet ist:
  
1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und melden Sie sich mit den Anmeldeinformationen für das Benutzerkonto an, dem die entsprechenden eDiscovery-Berechtigungen zugewiesen wurden.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Center auf **Alle anzeigen**, und klicken Sie dann auf **eDiscovery > Kern**.

3. Wählen Sie auf der **zentralen eDiscovery** -Seite den Fall aus, in dem Sie den Haltestatus erstellen möchten, und klicken Sie dann auf **Groß-/Kleinschreibung öffnen**.

4. Klicken Sie auf der **Start** Seite für den Fall auf die Registerkarte halte **Status** .
  
5. Klicken Sie auf der Seite halte **Status** auf **Erstellen**.

6. Geben Sie auf der Seite **Name Ihres Haltestatus** -Assistenten dem Haltestatus einen Namen und fügen Sie eine optionale Beschreibung hinzu, und klicken Sie dann auf **weiter**. Der Name des haltebereichs muss in Ihrer Organisation eindeutig sein.

7. Wählen Sie auf der Seite **inhaltsspeicherorte** die inhaltsspeicherorte aus, die Sie in die Warteschleife stellen möchten. Sie können Postfächer, Websites und öffentliche Ordner in der Warteschleife platzieren.

    ![Wählen Sie Inhaltsspeicherorte aus, die im Haltebereich platziert werden sollen.](../media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   a. **Postfachspeicher Orte** – klicken Sie auf **Benutzer, Gruppen oder Teams auswählen** , und klicken Sie dann erneut auf **Benutzer, Gruppen oder Teams** auswählen, um die zu speichernden Postfächer anzugeben. Verwenden Sie das Suchfeld, um nach Benutzerpostfächern und Verteilergruppen zu suchen (um die Postfächer der Gruppenmitglieder festhalten zu können), damit Sie in der Warteschleife platziert werden. Sie können das zugeordnete Postfach auch für ein Microsoft-Team, eine Office 365 Gruppe oder eine Jammer Gruppe aufbewahren. Aktivieren Sie das Kontrollkästchen Benutzer, Gruppe, Team, klicken Sie auf **auswählen**, und klicken Sie dann auf **Fertig**.

   b. **Website Standorte** – klicken Sie auf **Websites auswählen** , und klicken Sie dann erneut auf **Websites auswählen** , um SharePoint-und OneDrive-Konten für die Aufbewahrung anzugeben. Geben Sie die URL für jede Website ein, die Sie in die Warteschleife stellen möchten. Sie können auch die URL für die SharePoint-Website für ein Microsoft-Team, Office 365 Gruppe oder eine Gruppe jammern hinzufügen. Klicken Sie auf **auswählen**, und klicken Sie dann auf **Fertig**.
  
   c. **Öffentliche Exchange-Ordner.** Verschieben Sie das Toggle ![-Steuer](../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) Element der Umschaltfläche in die **all** -Position, um alle öffentlichen Ordner in Ihrer Exchange Online Organisation zu speichern. Sie können keine bestimmten öffentlichen Ordner auswählen, die in die Warteschleife gestellt werden sollen. Lassen Sie den Toggle-Schalter auf " **None** " festgelegt, wenn Sie öffentliche Ordner nicht in den Speicher setzen möchten.

8. Wenn Sie das Hinzufügen von Inhaltsspeicherorten in der Warteschleife abgeschlossen haben, klicken Sie auf **weiter**.

9. Um eine abfragebasierte Aufbewahrung mit Bedingungen zu erstellen, führen Sie die folgenden Schritte aus. Klicken Sie andernfalls auf **weiter** , um den gesamten Inhalt der angegebenen inhaltsspeicherorte beizubehalten.

    ![Erstellen eines abfragebasierten haltebereichs mit Bedingungen](../media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    a. Geben Sie im Feld unter **Schlüsselwörter**eine Suchabfrage ein, sodass nur die Inhalte beibehalten werden, die die Suchkriterien erfüllen. Sie können Schlüsselwörter, Eigenschaften von e-Mail-Nachrichten oder Dokumenteigenschaften wie Dateinamen angeben. Sie können auch komplexere Abfragen verwenden, die einen booleschen Operator wie **and**, **or**oder **Not**verwenden.

    b. Klicken Sie auf **Bedingungen hinzufügen** , um eine oder mehrere Bedingungen hinzuzufügen, um die Suchabfrage für den Haltebereich einzuschränken. Jede Bedingung fügt der KQL-Suchabfrage, die erstellt und ausgeführt wird, eine Klausel hinzu, wenn Sie den Haltebereich erstellen. Sie können beispielsweise einen Datumsbereich angeben, damit e-Mail-oder Website Dokumente, die innerhalb des Datumsbereichs erstellt wurden, in der Warteschleife gespeichert werden. Eine Bedingung ist logisch mit der Stichwortabfrage (im Feld **Schlüsselwörter** angegeben) durch den **and-** Operator verbunden. Das bedeutet, dass Elemente sowohl die Stichwortabfrage als auch die beizubehaltende Bedingung erfüllen müssen.

    Weitere Informationen zum Erstellen einer Suchabfrage und zum Verwenden von Bedingungen finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).

10. Klicken Sie nach dem Konfigurieren eines abfragebasierten Haltestatus auf **weiter**.

11. Überprüfen Sie Ihre Einstellungen (und bearbeiten Sie Sie, falls erforderlich), und klicken Sie dann auf **diesen Haltebereich erstellen**.

## <a name="ediscovery-hold-statistics"></a>eDiscovery-Aufbewahrungs Statistiken

Nachdem Sie einen eDiscovery-Haltestatus erstellt haben, werden Informationen zum neuen Haltestatus auf der Flyout-Seite für den ausgewählten Haltebereich angezeigt. Diese Informationen umfassen die Anzahl der zu speichernden Postfächer und Websites sowie Statistiken zu den Inhalten, die in der Warteschleife gespeichert wurden, beispielsweise die Gesamtanzahl und Größe der zu speichernden Elemente sowie die Uhrzeit, zu der die Aufbewahrungs Statistik zuletzt berechnet wurde. Diese Aufbewahrungs Statistiken helfen Ihnen dabei zu ermitteln, wie viel Inhalt im Zusammenhang mit dem Fall erhalten bleibt.
  
![Aufbewahrungs Statistik](../media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
Beachten Sie die folgenden Aspekte hinsichtlich der eDiscovery-Aufbewahrungs Statistiken:
  
- Die Gesamtanzahl der Elemente in der Warteschleife gibt die Anzahl der Elemente aus allen Inhaltsquellen an, die in der Warteschleife gespeichert werden. Wenn Sie einen abfragebasierten Haltebereich erstellt haben, gibt diese Statistik die Anzahl der Elemente an, die mit der Abfrage übereinstimmen.

- Die Anzahl der zu speichernden Elemente umfasst auch nicht indizierte Elemente, die an den Inhaltsspeicherorten gefunden wurden. Wenn Sie einen abfragebasierten Haltebereich erstellen, werden alle nicht indizierten Elemente in den Inhaltsspeicherorten in die Warteschleife gesetzt. Dies umfasst nicht indizierte Elemente, die nicht mit den Suchkriterien eines abfragebasierten haltebereichs und nicht indizierten Elementen übereinstimmen, die möglicherweise außerhalb einer Datumsbereichs Bedingung liegen. Dies unterscheidet sich von dem, was passiert, wenn Sie eine Suche ausführen, in der nicht indizierte Elemente, die nicht mit der Suchabfrage übereinstimmen oder von einer Datumsbereichs Bedingung ausgeschlossen werden, nicht in den Suchergebnissen enthalten sind. Weitere Informationen zu nicht indizierten Elementen finden Sie unter [teilweise indizierte Elemente](partially-indexed-items-in-content-search.md).

- Sie können die neuesten Aufbewahrungs Statistiken abrufen, indem Sie auf **Statistik aktualisieren** klicken, um eine Such Schätzung erneut auszuführen, mit der die aktuelle Anzahl der zu speichernden Elemente berechnet wird.

- Es ist normal, dass die Anzahl der zu speichernden Elemente im Laufe der Zeit ansteigt, da Benutzer, deren Postfach oder Standort in der Warteschleife ist, in der Regel neue e-Mail-Nachrichten senden oder empfangen und neue Dokumente in SharePoint und OneDrive erstellen.

- Wenn ein Exchange-Postfach, eine SharePoint-Website oder ein OneDrive-Konto in eine andere Region in einer Multi-Geo-Umgebung verschoben wird, werden die Statistiken für diese Website nicht in die halte Statistik aufgenommen. Der Inhalt an diesen Speicherorten bleibt jedoch erhalten. Wenn ein Postfach oder eine Website in eine andere Region verschoben wird, wird die SMTP-Adresse oder-URL, die im Haltestatus angezeigt wird, aber nicht automatisch aktualisiert. Sie müssen den Aufbewahrungsplatz bearbeiten und die URL oder SMTP-Adresse aktualisieren, damit die inhaltsspeicherorte wieder in die halte Statistik aufgenommen werden.

## <a name="search-locations-on-ediscovery-hold"></a>Suchspeicher Orte in eDiscovery Hold

Wenn Sie in einem zentralen eDiscovery-Fall [nach Inhalten suchen](search-for-content-in-core-ediscovery.md) , können Sie die Suche schnell so konfigurieren, dass nur die inhaltsspeicherorte durchsucht werden, die in einem der Anfrage zugeordneten Haltebereich gespeichert sind.

![Speicherorte, Aufbewahrungsorte](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)

Wählen Sie die Option **Speicherorte** aus, um alle inhaltsspeicherorte zu durchsuchen, die in der Warteschleife gespeichert wurden. Wenn die Anfrage mehrere eDiscovery-Haltestatus enthält, werden die inhaltsspeicherorte aus allen Haltebereichen durchsucht, wenn Sie diese Option auswählen. Wenn ein Inhaltsspeicherort auf einem abfragebasierten Haltebereich positioniert wurde, werden beim Ausführen der Suche nur die Elemente durchsucht, die mit der halte Abfrage übereinstimmen. Mit anderen Worten: nur der Inhalt, der sowohl den Aufbewahrungs Kriterien als auch den Suchkriterien entspricht, wird mit den Suchergebnissen zurückgegeben. Wenn beispielsweise ein Benutzer auf Abfrage basiertem Case Hold gesetzt wurde, der Elemente aufrecht erhält, die vor einem bestimmten Datum gesendet oder erstellt wurden, werden nur diese Elemente durchsucht. Dies wird erreicht, indem die Case Hold-Abfrage und die Suchabfrage durch einen **and-** Operator verbunden werden.

Im folgenden sind einige andere Punkte aufgeführt, die beim Suchen von Speicherorten in eDiscovery Hold beachtet werden sollten:

- Wenn ein Inhaltsspeicherort Teil mehrerer haltebereiche innerhalb desselben Falles ist, werden die Aufbewahrungs Abfragen bei der Suche des Inhaltsspeicherorts mithilfe der Option "alle Groß-/Kleinschreibung" durch **or** -Operatoren kombiniert. Wenn ein Inhaltsspeicherort Teil von zwei unterschiedlichen Haltebereichen ist, wobei einer auf Abfrage basiert und der andere ein unbegrenzter Speicher ist (wobei der gesamte Inhalt in den Haltebereich gesetzt wird), wird der gesamte Inhalt aufgrund des unbegrenzten Haltestatus durchsucht.

- Wenn eine Suche für Suchspeicher Orte in der Warteschleife konfiguriert ist und Sie dann einen eDiscovery-Haltestatus in dem Fall ändern (durch Hinzufügen oder Entfernen eines Speicherorts oder Ändern einer halte Abfrage), wird die Suchkonfiguration mit diesen Änderungen aktualisiert. Sie müssen die Suche jedoch erneut ausführen, nachdem der Haltebereich geändert wurde, um die Suchergebnisse zu aktualisieren.

- Wenn mehrere eDiscovery-Halterungen an einem einzigen Speicherort in einem eDiscovery-Fall gespeichert werden und Sie Speicherorte für die Suche in der Warteschleife auswählen, beträgt die maximale Anzahl von Stichwörtern für diese Suchabfrage 500. Das liegt daran, dass die Suche alle abfragebasierten haltebereiche mit dem **or** -Operator kombiniert. Wenn in den kombinierten halte Abfragen und der Suchabfrage mehr als 500 Schlüsselwörter vorhanden sind, wird der gesamte Inhalt im Postfach durchsucht, und nicht nur der Inhalt, der mit dem abfragebasierten Fall übereinstimmt. 
    
- Wenn ein eDiscovery-Haltestatus aktiviert ist, können Sie die Speicherorte weiterhin durch **suchen, während**der Haltebereich aktiviert ist.

## <a name="preserve-content-in-microsoft-teams"></a>Beibehalten von Inhalten in Microsoft Teams

Unterhaltungen, die Teil eines Microsoft Teams-Kanals sind, werden in dem Postfach gespeichert, das dem Microsoft-Team zugeordnet ist. Gleichermaßen werden Dateien, die Teammitglieder in einem Kanal freigeben, auf der SharePoint-Website des Teams gespeichert. Daher müssen Sie das Team Postfach und die SharePoint-Website in eDiscovery Hold platzieren, um Unterhaltungen und Dateien in einem Kanal beizubehalten.

Alternativ werden Unterhaltungen, die Teil der Chat Liste in Microsoft Teams sind (so genannte *1:1-Chats* oder *1: N-Gruppenchats*), in den Postfächern der Benutzer gespeichert, die am Chat teilnehmen. Und Dateien, die Benutzer in Chat Unterhaltungen freigeben, werden im OneDrive-Konto des Benutzers gespeichert, der die Datei freigibt. Daher müssen Sie die einzelnen Benutzerpostfächer und OneDrive-Konten zu einer eDiscovery-Aufbewahrungs Liste hinzufügen, um Unterhaltungen und Dateien in der Chatliste beizubehalten. Es empfiehlt sich, die Postfächer von Mitgliedern eines Microsoft-Teams zusätzlich zur Platzierung des Team Postfachs und der Website aufzubewahren.

Ab dem 2020. Februar haben wir die Möglichkeit zum Beibehalten von Inhalten in privaten Kanälen aktiviert. Da private Kanal Chats in den Postfächern der Chat Teilnehmer gespeichert werden, werden durch das Platzieren eines Benutzerpostfachs in eDiscovery Hold private Kanal Chats beibehalten. Wenn ein Benutzerpostfach vor dem Februar 2020 auf einem eDiscovery-Speicher abgelegt wurde, wird der Aufbewahrungs Status nun automatisch auf private Kanal Nachrichten angewendet, die in diesem Postfach gespeichert sind. Das Beibehalten von Dateien, die in privaten Kanälen freigegeben sind, wird ebenfalls unterstützt.

Weitere Informationen zum Beibehalten von Teams-Inhalten finden Sie unter [platzieren eines Microsoft Teams-Benutzers oder-Teams in Legal Hold](https://docs.microsoft.com/MicrosoftTeams/legal-hold).
    
> [!IMPORTANT]
> In einer cloudbasierten Organisation müssen Benutzer, die an Unterhaltungen teilnehmen, die Teil der Chat Liste in Microsoft Teams sind, über ein Exchange Onlinees Postfach verfügen, damit Chat Unterhaltungen beibehalten werden, wenn das Postfach in einem eDiscovery-Archiv gespeichert wird. Das liegt daran, dass Unterhaltungen, die Teil der Chat Liste sind, in den cloudbasierten Postfächern der Chat Teilnehmer gespeichert werden. Wenn ein Chat Teilnehmer kein Exchange Online Postfach hat, können Sie diese Chat Unterhaltungen nicht beibehalten. Beispielsweise können Benutzer mit einem lokalen Postfach in einer Exchange-hybridbereitstellung an Unterhaltungen teilnehmen, die Teil der Chat Liste in Microsoft Teams sind. In diesem Fall können Inhalte aus diesen Unterhaltungen jedoch nicht beibehalten werden, da diese Benutzer keine Cloud-basierten Postfächer haben, die in die Warteschleife gestellt werden können.
  
Jeder Team-oder Team Kanal enthält auch ein wiki für Notizen und die Zusammenarbeit. Die Wiki-Inhalte werden automatisch in einer Datei im MHT-Format gespeichert. Diese Datei wird in der Dokumentbibliothek für Wiki-Daten auf der SharePoint-Website des Teams gespeichert. Sie können den Inhalt des Wikis beibehalten, indem Sie die SharePoint-Website des Teams einem eDiscovery-Speicher hinzufügen.
    
> [!NOTE]
> Die Möglichkeit, den wiki-Inhalt für einen Team-oder Team Kanal beizubehalten (wenn Sie die SharePoint-Website des Teams in der Warteschleife platzieren) wurde am 22. Juni 2017 veröffentlicht. Wenn eine Teamwebsite gespeichert ist, wird der Inhalt des Wikis ab diesem Datum beibehalten. Wenn jedoch eine Teamwebsite gespeichert ist und der Inhalt des Wikis vor dem 22. Juni 2017 gelöscht wurde, wurde der Inhalt des Wikis nicht beibehalten.

### <a name="office-365-groups"></a>Office 365-Gruppen

Teams ist auf Office 365 Gruppen aufgebaut. Daher ist das Platzieren von Office 365 Gruppen in eDiscovery-Archiven vergleichbar, wenn Sie den Inhalt von Microsoft Teams halten.

Beachten Sie beim Platzieren von Teams und Office 365 Gruppen in einer eDiscovery-Aufbewahrung Folgendes:

- Wie bereits erläutert, müssen Sie das Postfach und die SharePoint-Website angeben, die einer Gruppe oder einem Team zugeordnet sind, um Inhalte zu platzieren, die in Teams und Office 365 Gruppen gespeichert sind.

- Führen Sie das Cmdlet **Get-Unifiedgroup** in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) aus, um Eigenschaften für Teams und Office 365 Gruppen anzuzeigen. Dies ist eine gute Möglichkeit, die URL für die Website abzurufen, die einem Team oder einer Office 365 Gruppe zugeordnet ist. Mit dem folgenden Befehl werden z. B. ausgewählte Eigenschaften für die Office 365-Gruppe „Geschäftsleitung“ angezeigt:

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Zum Ausführen des **Get-UnifiedGroup**-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde. 
  
- Wenn das Postfach eines Benutzers durchsucht wird, werden alle Teams oder Office 365 Gruppen, in denen der Benutzer Mitglied ist, nicht durchsucht. Wenn Sie eine Team-oder Office 365 Gruppe in eDiscovery Hold platzieren, werden nur das Gruppenpostfach und die Gruppen Website in den Haltebereich verschoben. Die Postfächer und OneDrive für Unternehmen Websites von Gruppenmitgliedern werden nur gespeichert, wenn Sie Sie explizit dem eDiscovery-Haltestatus hinzufügen. Wenn Sie also ein Team oder eine Office 365 Gruppe aus einem rechtlichen Grund in die Warteschleife stellen müssen, können Sie die Postfächer und OneDrive-Konten von Team-oder Gruppenmitgliedern in demselben Haltebereich hinzufügen.

- Wenn Sie eine Liste der Mitglieder eines Teams oder einer Office 365 Gruppe erhalten möchten, können Sie die Eigenschaften auf der Seite " **Gruppen** " im Microsoft 365 Admin Center anzeigen. Alternativ können Sie den folgenden Befehl in Exchange Online-PowerShell ausführen: 
    
    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > Zum Ausführen des **Get-UnifiedGroupLinks**-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde.

## <a name="onedrive-accounts"></a>OneDrive-Konten

Informationen zum Sammeln einer Liste der URLs für die OneDrive für Unternehmen Websites in Ihrer Organisation, damit Sie Sie zu einem Haltestatus oder einer Suche hinzufügen können, die einem eDiscovery-Fall zugeordnet ist, finden Sie unter [Erstellen einer Liste aller OneDrive-Standorte in Ihrer Organisation](https://docs.microsoft.com/onedrive/list-onedrive-urls). Das Skript in diesem Artikel erstellt eine Textdatei, die eine Liste aller OneDrive-Websites in Ihrer Organisation enthält. Um dieses Skript ausführen zu können, müssen Sie die SharePoint Online-Verwaltungsshell installieren und verwenden. Achten Sie darauf, die URL für die "MeineWebsite"-Domäne Ihrer Organisation an jede OneDrive-Website anzuhängen, die Sie durchsuchen möchten. Dies ist die Domäne, die Ihr gesamtes OneDrive enthält, z. B. `https://contoso-my.sharepoint.com`. Hier ein Beispiel für die URL der OneDrive-Website eines Benutzers: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

> [!IMPORTANT]
> Die URL für das OneDrive-Konto eines Benutzers enthält den Benutzerprinzipalnamen (User Principal Name, `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com`UPN) (beispielsweise). Im seltenen Fall, dass der UPN eines Benutzers geändert wird, ändert sich auch die OneDrive-URL, um den neuen UPN zu integrieren. Wenn das OneDrive-Konto eines Benutzers Teil eines eDiscovery-Speichers ist, wenn alt und sein UPN geändert wurden, müssen Sie den Haltestatus aktualisieren, und Sie müssen den Haltestatus aktualisieren und die neue OneDrive-URL des Benutzers hinzufügen und die alte entfernen. Weitere Informationen hierzu finden Sie unter [Wie sich UPN-Änderungen auf die OneDrive-URL auswirken](https://docs.microsoft.com/onedrive/upn-changes).

## <a name="ediscovery-hold-limits"></a>eDiscovery-Aufbewahrungs Grenzwerte

In der folgenden Tabelle sind die Grenzwerte für eDiscovery-Fälle und Case-Holds aufgeführt.
    
  |**Beschreibung der Beschränkung**|**Grenzwert**|
  |:-----|:-----|
  |Maximale Anzahl von Fällen für eine Organisation  <br/> |Keine Begrenzung  <br/> |
  |Maximale Anzahl von eDiscovery-Haltestatus für eine Organisation  <br/> |10.000  <br/> |
  |Maximale Anzahl von Postfächern in einer einzelnen eDiscovery-Aufbewahrung  <br/> |1.000  <br/> |
  |Maximale Anzahl von SharePoint-und OneDrive für Unternehmen-Websites in einem einzelnen eDiscovery-Haltebereich  <br/> |100  <br/> |
  |Maximale Anzahl der auf der eDiscovery-Startseite angezeigten Fälle und die maximale Anzahl von Elementen, die auf den Registerkarten Holds, suchen und Exportieren in einem Fall angezeigt werden. <sup>1</sup> |1.000|
  |||

   > [!NOTE]
   > <sup>1</sup> Wenn Sie eine Liste mit mehr als 1.000 Fällen, Aufbewahrungen, Suchvorgängen oder Exporten anzeigen möchten, können Sie das entsprechende PowerShell-Cmdlet Office 365 Security & Compliance verwenden:<br/> [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase) <br/> [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)<br/> [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)<br/> [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)