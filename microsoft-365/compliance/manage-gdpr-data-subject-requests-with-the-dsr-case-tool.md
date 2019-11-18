---
title: 'Verwalten von dsgvo-Datensubjekt Anforderungen mit dem DSR Case-Tool im Security #a0 Compliance Center'
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
ms.assetid: ce9eb942-3589-42cb-88fd-1576ecb09c5c
description: Das dsgvo gibt EU-Bürgern (sogenannte Datensubjekte) bestimmte Rechte für Ihre personenbezogenen Daten. Diese Rechte umfassen das Abrufen von Kopien davon, das Anfordern von Änderungen, das Einschränken der Verarbeitung, das Löschen oder das empfangen im elektronischen Format. Eine formelle Anforderung einer betroffenen Person, eine Aktion für Ihre personenbezogenen Daten durchführen zu können, wird als Datensubjekt Anforderung oder DSR bezeichnet. Sie können DSR-Fälle im Compliance Center in Office 365 und Microsoft 365 verwenden, um die DSR-Untersuchungen Ihrer Organisation zu verwalten.
ms.openlocfilehash: 4b1e6eac17c95e3d0fe638711483802c829fdd56
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686232"
---
# <a name="manage-gdpr-data-subject-requests-with-the-dsr-case-tool-in-the-security--compliance-center"></a>Verwalten von dsgvo-Datensubjekt Anforderungen mit dem DSR Case-Tool im Security #a0 Compliance Center

Die allgemeine Datenschutzverordnung (dsgvo) in der EU beruht auf dem Schutz und der Aktivierung von Datenschutz rechten für einzelne Personen innerhalb der Europäischen Union (EU). Das dsgvo gibt einzelnen in der Europäischen Union (als betroffene Personen bezeichnet) das Recht, auf die Verarbeitung Ihrer personenbezogenen Daten zuzugreifen, diese abzurufen, zu korrigieren, zu löschen und zu beschränken. Unter dem dsgvo sind personenbezogene Daten alle Informationen, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen. Eine formelle Anforderung einer Person an Ihre Organisation, eine Aktion für Ihre personenbezogenen Daten durchführen zu können, wird als Datensubjekt Anforderung oder DSR bezeichnet. Ausführliche Informationen zur Reaktion auf DSRs auf Daten in Office 365 finden Sie unter [Office 365 Data Subject Request Guide](https://go.microsoft.com/fwlink/?linkid=871169 ).
  
Wenn Sie Untersuchungen als Reaktion auf einen von einer Person in Ihrer Organisation übermittelten DSR durchführen möchten, können Sie das DSR Case-Tool im Security #a0 Compliance Center verwenden, um nach Inhalten zu suchen, die in folgendem gespeichert sind:
  
- Beliebiges Benutzerpostfach in Ihrer Organisation. Dies umfasst Skype for Business Unterhaltungen und 1:1-Chats in Microsoft Teams.
    
- Alle Postfächer, die einer Office 365 Gruppe und allen Team Postfächern in Microsoft Teams zugeordnet sind
    
- Alle SharePoint Online-Websites und OneDrive for Business-Konten in Ihrer Organisation
    
- Alle Teams-Websites und Office 365 Gruppen Websites in Ihrer Organisation
    
- Alle öffentlichen Ordner in Exchange Online
    
Mit dem DSR Case-Tool können Sie Folgendes tun:
  
- Erstellen Sie einen separaten Fall für jede Untersuchung eines Antrags einer betroffenen Person.
    
- Steuern Sie, wer Zugriff auf den DSR-Fall hat, indem Sie Personen als Mitglieder des Falles hinzufügen. nur Mitglieder können auf den Fall zugreifen und können ihre Fälle nur in der Liste der Fälle auf der Seite " **DSR-Anfragen** " im Security #a0 Compliance Center anzeigen. Außerdem können Sie verschiedenen Mitgliedern desselben falls unterschiedliche Berechtigungen zuweisen. Beispielsweise können Sie einigen Mitgliedern erlauben, die Groß-/Kleinschreibung und die Suchergebnisse nur anzuzeigen und anderen Mitgliedern das Erstellen von suchen und das Exportieren von Suchergebnissen zu gestatten. 
    
- Verwenden Sie die integrierte Suche, um nach allen Inhalten zu suchen, die von einer bestimmten betroffenen Person erstellt oder hochgeladen wurden.
    
- Überprüfen Sie optional die integrierte Suchabfrage, und führen Sie die Suche erneut aus, um die Suchergebnisse einzuschränken.
    
- Fügen Sie weitere Inhalts suchen hinzu, die dem DSR-Fall zugeordnet sind. Dies umfasst das Erstellen von Suchvorgängen, die teilweise indizierte Elemente und vom System generierte Protokolle vom Office-Roamingdienst zurückgeben.
    
- Exportieren von Daten als Reaktion auf eine DSR-Zugriffs-oder Exportanforderung.
    
- Löschvorgänge, wenn der DSR-Untersuchungsprozess abgeschlossen ist. Dadurch werden alle Suchvorgänge und Exportaufträge entfernt, die mit der Anfrage verknüpft sind.
    
Hier ist der allgemeine Prozess für die Verwendung des DSR-Fall Tools zum Verwalten von DSR-Untersuchungen:
  
[Step 1: Assign eDiscovery permissions to potential case members](#step-1-assign-ediscovery-permissions-to-potential-case-members)

[Schritt 2: Erstellen eines DSR-Falls und Hinzufügen von Mitgliedern](#step-2-create-a-dsr-case-and-add-members)

[Schritt 3: Ausführen der Suchabfrage](#step-3-run-the-search-query)

[Schritt 4: Exportieren der Daten](#step-4-export-the-data)

[Optional Schritt 5: Überarbeiten der integrierten Suchabfrage](#optional-step-5-revise-the-built-in-search-query)

[Weitere Informationen zur Verwendung des DSR-Fall Tools](#more-information-about-using-the-dsr-case-tool)
  
> [!IMPORTANT]
> Mithilfe unserer Tools können Administratoren den DSR-Zugriff oder den Export von Anforderungen durchführen, indem Sie die integrierte Such-und Exportfunktionalität des DSR-Case-Tools nutzen. Das Tool hilft, eine Best-Effort-Methode zum Exportieren von Daten zu vereinfachen, die für eine von einer betroffenen Person übermittelte DSR-Anforderung relevant sind. Es ist jedoch wichtig zu beachten, dass die Suchergebnisse je nach der betroffenen Person oder den ausgeführten Administratoraktionen variieren können, was sich auf die Frage auswirken kann, ob ein Element für Exportzwecke als "personenbezogene Daten" betrachtet würde. Wenn beispielsweise der Betroffene die letzte Person war, die eine Datei geändert hat, die Sie nicht erstellt haben, wird die Datei möglicherweise nicht in den Suchergebnissen zurückgegeben. Auf ähnliche Weise könnte ein Administrator Daten exportieren, ohne teilweise indizierte Elemente oder alle Versionen von SharePoint-Dokumenten einzubinden. Daher können die bereitgestellten Tools dazu beitragen, den Zugriff auf und den Export von Datenanforderungen zu erleichtern. die Ergebnisse unterliegen jedoch bestimmten Verwendungsszenarien für Administratoren und Datensubjekte. 
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a>Schritt 1: Zuweisen von eDiscovery-Berechtigungen zu potenziellen Fallmitgliedern

Standardmäßig kann ein Office 365 globaler Administrator im Security #a0 Compliance Center auf das DSR Case-Tool zugreifen. Andere Benutzer wie ein Datenschutzbeauftragter, ein Personalmanager oder andere Personen, die an DSR-Untersuchungen beteiligt sind, haben keinen Zugriff auf das DSR-Fall Tool und müssen die entsprechenden Berechtigungen für den Zugriff auf das Tool erhalten. Die einfachste Möglichkeit besteht darin, auf die Seite **Berechtigungen** im Security #a0 Compliance Center zu wechseln und Benutzer zur eDiscovery-Manager-Rollengruppe hinzuzufügen. Sie müssen diese Berechtigungen auch zuweisen, damit Sie Sie als Mitglieder des in Schritt 2 erstellten DSR-Falls hinzufügen können. 
  
Eine Schritt-für-Schritt-Anleitung finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Office 365 Security #a0 Compliance Center](assign-ediscovery-permissions.md).
  
> [!NOTE]
> Standardmäßig verfügen ein Office 365 globaler Administrator (oder andere Mitglieder der Rollengruppe "Organisationsverwaltung" im Security #a0 Compliance Center nicht über die erforderlichen Berechtigungen zum Exportieren von Inhalts Suchergebnissen (siehe Schritt 4 in diesem Artikel). Um dies zu beheben, kann ein Administrator sich selbst als Mitglied der Rollengruppe "eDiscovery-Manager" hinzufügen. 
  
## <a name="step-2-create-a-dsr-case-and-add-members"></a>Schritt 2: Erstellen eines DSR-Falls und Hinzufügen von Mitgliedern

Der nächste Schritt besteht darin, einen DSR-Fall zu erstellen. Wenn Sie eine Anfrage erstellen, können Sie die integrierte Suche starten, oder Sie können den Fall erstellen, ohne die Suche zu starten. Mit dem folgenden Verfahren werden Sie aufgefordert, den Fall zu erstellen, ohne die Suche zu starten und anschließend anzuzeigen, wie der Anfrage Mitglieder hinzugefügt werden.
  
1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu, und melden Sie sich bei Office 365 mit ihrem geschäftlichen oder Schulkonto an. 
    
2. Klicken Sie im Security #a0 Compliance Center auf **Datenschutz** \> **Antragsteller Anforderungen**, und klicken ![Sie dann](media/ITPro-EAC-AddIcon.gif) auf Symbol hinzufügen **neuer DSR-Fall**.
    
3. Geben Sie auf der **neuen DSR-Fall** Flyout-Seite den Fall einen Namen ein, geben Sie eine optionale Beschreibung ein, und klicken Sie dann auf **weiter**. Der Name des Falls muss in Ihrer Organisation eindeutig sein.
    
    > [!TIP]
    > Sie können den Namen der Person, die die DSR-Anforderung übermittelt hat, im Namen und/oder in der Beschreibung des neuen Falls untersuchen. Beachten Sie, dass nur Mitglieder dieses Falles (und eDiscovery-Administratoren) den Fall in der Liste der Fälle auf der Seite mit den **Anforderungen von Datensubjekten** anzeigen können. 
  
4. Wählen Sie auf der Seite **Anforderungsdetails** unter **Datensubjekt (die Person, die diese Anforderung eingereicht hat)** die Person aus, für die Sie die Daten suchen und exportieren möchten, und klicken Sie dann auf **weiter**.
    
5. Auf der Seite **Fall Einstellungen bestätigen** können Sie den Fall Namen und die Beschreibung ändern und eine andere betroffene Person auswählen. Klicken Sie andernfalls auf **Speichern**.
    
    Eine Seite wird angezeigt, die bestätigt, dass der neue DSR-Fall erstellt wurde.
    
    ![Starten der Suche oder Schließen der neuen Seite für den DSR-Fall](media/b5e62c2c-cafe-4a8d-a38c-789ed9f9ccbd.png)
  
    Zu diesem Zeitpunkt können Sie eine der folgenden Aktionen ausführen:
    
    a. Wenn Sie auf **Suchergebnisse anzeigen klicken,** wird die Suche gestartet. Dies ist die Standardauswahl. Die integrierte Suche, die ausgeführt wird, wenn Sie diese Option auswählen, und die zurückgegebenen Ergebnisse werden in Schritt 3 erläutert.
    
    b. Durch Klicken auf **Fertig stellen** wird der neue DSR-Fall geschlossen, ohne die integrierte Suche zu starten. Wenn Sie diese Option auswählen, wird der neue DSR-Fall auf der Seite mit den **Anforderungen von Datensubjekten** angezeigt.
    
6. Klicken Sie auf **Fertig stellen** , damit Sie zum neuen DSR-Fall wechseln und ihm Mitglieder hinzufügen können. 
    
7. Klicken Sie auf der Seite **Datensubjekt Anforderungen** auf den Namen des von Ihnen erstellten DSR-Falls. 
    
8. Klicken Sie auf der Seite **diesen Fall Flyout verwalten** unter **Mitglieder verwalten**auf **Hinzufügen**. 
    
    Unter **Benutzer**wird eine Liste mit Personen angezeigt, denen die entsprechenden eDiscovery-Berechtigungen zugewiesen sind. Die Personen, denen Sie in Schritt 1 eDiscovery-Berechtigungen zugewiesen haben, werden in dieser Liste angezeigt. 
    
9. Wählen Sie die Personen aus, die Sie als Mitglieder des DSR-Falls hinzufügen möchten, klicken Sie auf **Hinzufügen**, und speichern Sie dann die Änderungen.
    
    Sie können auch Rollengruppen als Mitglieder des DSR-Falls hinzufügen, indem Sie unter **Rollengruppen verwalten**auf **Hinzufügen** klicken. 
    
## <a name="step-3-run-the-search-query"></a>Schritt 3: Ausführen der Suchabfrage

Nachdem Sie einen DSR-Fall erstellt und Mitglieder hinzugefügt haben, besteht der nächste Schritt darin, die integrierte Suche auszuführen, die der Anfrage zugeordnet ist. Diese Standardsuch Abfrage führt folgende Schritte aus:
  
- Durchsucht alle Postfächer in Ihrer Organisation nach allen e-Mail-Elementen, die von der betroffenen Person gesendet oder empfangen wurden. Dies wird mithilfe der e-Mail-Eigenschaft *Teilnehmer* erreicht, die in allen Personen Feldern in einer e-Mail-Nachricht nach der betroffenen Person sucht. Diese Eigenschaft gibt Elemente zurück, in denen sich die betroffene Person in den Feldern **from**, **to**, **CC**und **Bcc** befindet. Öffentliche Ordner in Exchange Online werden auch nach Nachrichten durchsucht, die von der betroffenen Person gesendet oder empfangen wurden. 
    
- Durchsucht alle Websites in Ihrer Organisation nach Dokumenten und Elementen, die von der betroffenen Person erstellt oder hochgeladen wurden. Dies wird mithilfe der folgenden Websiteeigenschaften erreicht:
    
  - Die *Author* -Eigenschaft gibt Elemente zurück, bei denen die betroffene Person im Feld Author in Office-Dokumenten aufgeführt ist. Dieser Wert bleibt auch dann erhalten, wenn das Dokument kopiert und von jemand anderem hochgeladen wird. 
    
  - Die *CreatedBy* -Eigenschaft gibt Elemente zurück, die von der betroffenen Person erstellt oder hochgeladen wurden. 
    
Hier erfahren Sie, wie die Stichwortabfrage für die integrierte Suche aussieht, die beim Erstellen eines DSR-Falls automatisch erstellt wird.
  
```powershell
participants:"<email address>" OR author:"<display name>" OR createdby:"<display name>"
```

Wenn beispielsweise der Name der betroffenen Person Ina Leonte ist, würde die Stichwortabfrage wie folgt aussehen:
  
```powershell
participants:"ina@contoso.com" OR author:"Ina Leonte" OR createdby:"Ina Leonte"
```

 **So führen Sie die integrierte Suche für einen DSR-Fall aus:**
  
1. Klicken Sie im Security #a0 Compliance Center auf **Datenschutz** \> **Antragsteller Anforderungen**, und klicken Sie dann neben dem in Schritt 2 erstellten DSR-Fall auf **Öffnen** . 
    
    Klicken Sie oben auf der Seite auf die Registerkarte **Suche** , und klicken Sie dann auf das Kontrollkästchen neben der integrierten Suche, die beim Erstellen des DSR-Falls erstellt wurde. Die Suche hat den gleichen Namen wie der DSR-Fall. 
    
2. Klicken Sie auf der Seite Flyout durchsuchen auf **Abfrage öffnen**.
    
    Wenn Sie die Abfrage öffnen, wird die Suche gestartet und wird in wenigen Augenblicken abgeschlossen. 
    
3. Wenn die Suche abgeschlossen ist, klicken Sie auf **Ergebnisse anzeigen** , um eine Vorschau der Suchergebnisse anzuzeigen. Weitere Informationen finden Sie unter [Vorschau der Suchergebnisse](content-search.md#preview-search-results).
    
    > [!TIP]
    > Sie können auch die Suchabfrage Statistik anzeigen, um die Anzahl der Post Fach-und Websiteelemente anzuzeigen, die von der Suche zurückgegeben werden, und die oberen inhaltsspeicherorte, die Elemente enthalten, die mit der Suchabfrage übereinstimmen. Weitere Informationen finden Sie unter [Anzeigen von Informationen und Statistiken zu einer Suche](content-search.md#view-information-and-statistics-about-a-search). 
  
Sie können die integrierte Suchabfrage bearbeiten, die durchsuchten inhaltsspeicherorte ändern und dann die Suche erneut ausführen. Weitere Informationen finden Sie in [Schritt 5](#optional-step-5-revise-the-built-in-search-query) . 
  
## <a name="step-4-export-the-data"></a>Schritt 4: Exportieren der Daten

Nachdem Sie die integrierte Suche ausgeführt haben, können Sie die Suchergebnisse exportieren. Alternativ können Sie vor dem Exportieren der Daten die Abfrage überarbeiten, um die Anzahl der Suchergebnisse zu verringern. Weitere Informationen zum Einschränken der Suchergebnisse finden Sie in Schritt 5.
  
Wenn Sie Suchergebnisse exportieren, können Postfachelemente in PST-Dateien oder als einzelne Nachrichten heruntergeladen werden. Wenn Sie Inhalte aus SharePoint-und OneDrive-Konten exportieren, werden Kopien von systemeigenen Office-Dokumenten und anderen Dokumenten exportiert. In den Suchergebnissen ist eine Ergebnisdatei enthalten, die Informationen zu allen exportierten Elementen enthält. Ausführlichere Informationen zum Exportieren finden Sie unter [Exportieren von Inhalts Suchergebnissen](export-search-results.md).
  
> [!NOTE]
> Ein Office 365 globaler Administrator (oder andere Mitglieder der Rollengruppe "Organisationsverwaltung" im Security #a0 Compliance Center) verfügen standardmäßig nicht über die erforderlichen Berechtigungen zum Exportieren von Inhalts Suchergebnissen. Um dies zu beheben, kann ein Administrator sich selbst als Mitglied der Rollengruppe "eDiscovery-Manager" hinzufügen. 
  
Der Computer, den Sie zum Exportieren von Daten verwenden, muss die folgenden Systemanforderungen erfüllen:
  
- 32-Bit-oder 64-Bit-Versionen von Windows 7 und höheren Versionen
    
- Microsoft .NET Framework 4,7
    
- Einen unterstützten Browser:
    
  - Microsoft Edge
    
    Oder
    
  - Microsoft Internet Explorer 10 und höhere Versionen
    
    > [!NOTE]
    > Microsoft stellt keine Drittanbietererweiterungen oder Add-ons für ClickOnce-Anwendungen her. Das Exportieren von Daten mit einem nicht unterstützten Browser mit Erweiterungen oder Add-ons von Drittanbietern wird nicht unterstützt. 
  
 **So exportieren Sie Daten aus der integrierten Suche in einem DSR-Fall:**
  
1. Klicken Sie im Security #a0 Compliance Center auf **Datenschutz** \> **Antragsteller Anforderungen**, und klicken Sie dann neben dem DSR-Fall, aus dem Sie Daten exportieren möchten, auf **Öffnen** . 
    
2. Klicken Sie oben auf der Seite auf die Registerkarte **Suche** , und klicken Sie dann auf das Kontrollkästchen neben der integrierten Suche, die beim Erstellen des DSR-Falls erstellt wurde. Oder klicken Sie auf eine andere Suche, um Daten aus dieser Suche zu exportieren. 
    
3. Klicken Sie ![auf der Seite Flyout-Suche auf Suchergebnisse](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **exportieren, und**wählen Sie dann **Ergebnisse exportieren** aus der Dropdownliste aus. 
    
4. Wählen Sie auf der Seite **Ergebnisse exportieren** die folgenden empfohlenen Optionen für DSR-Exportanforderungen aus. 
    
    ![Konfigurieren der Exporteinstellungen](media/25416b79-57da-46a1-ae07-e640602a8fa4.png)
  
    a. Wählen Sie unter **Ausgabeoptionen**die erste Option (**alle Elemente, ausgenommen diejenigen, die über ein nicht erkanntes Format verfügen, verschlüsselt sind oder aus anderen Gründen nicht indiziert**wurden) aus, um nur indizierte Elemente zu exportieren. Der Grund, warum Sie nicht teilweise indizierte Elemente aus der integrierten Suche exportieren möchten, liegt daran, dass teilweise indizierte Elemente von anderen Benutzern ebenfalls exportiert werden. Um nur die teilweise indizierten Elemente für die betroffene Person zu exportieren, empfiehlt es sich, eine separate Suche zu erstellen. Weitere Informationen finden Sie unter [Export von teilweise indizierten Elementen](#exporting-partially-indexed-items) im Abschnitt "Weitere Informationen zum Verwenden des DSR-Fall Tools".
    
    b. Wählen Sie unter **Exchange-Inhalt exportieren als**die dritte Option aus, **eine PST-Datei, die alle Nachrichten in einem einzelnen Ordner enthält**. Da einige der Ergebnisse möglicherweise für Elemente gelten, die im Postfach eines anderen Benutzers entstanden sind, wird mit dieser Option nur das Element in einem einzelnen Ordner aufgelistet, ohne das tatsächliche Postfach anzugeben, und es ist die beste Option, wenn Sie die Ergebnisse nach dem nächsten Element de duplizieren (empfohlen). . Mit dieser Option können die Elemente des Datensubjekts auch in chronologischer Reihenfolge überprüft werden (Elemente werden nach dem gesendeten Datum sortiert), ohne dass Sie durch die ursprüngliche Postfachordnerstruktur für jedes Element navigieren müssen.
    
    c. Wählen Sie die Option **Deduplizierung aktivieren** aus, um doppelte e-Mail-Nachrichten auszuschließen. Diese Option wird empfohlen, da die integrierte Suche alle Postfächer in Ihrer Organisation durchsucht. Wenn also mehrere Kopien derselben Nachricht in den durchsuchten Postfächern gefunden werden, bedeutet diese Option, dass nur eine Kopie einer Nachricht exportiert wird. Mit dieser Option werden Nachrichten zusammen in einer PST-Datei in einem einzigen Ordner exportiert, was zu einer optimalen Benutzererfahrung für DSR-Exportanforderungen führt. Der Bericht results. CSV Export listet alle Orte auf, an denen doppelte Nachrichten gefunden wurden.
    
    Optional können Sie die Option **Versionen für SharePoint-Dokumente einschließen** auswählen, um alle Versionen von SharePoint-und OneDrive-Dokumenten zu exportieren. Dies erfordert, dass die Versionsverwaltung für Dokumentbibliotheken aktiviert ist. Mit dieser Option können Sie sicherstellen, dass alle relevanten Daten exportiert werden.
    
5. Nachdem Sie die Exporteinstellungen ausgewählt haben, klicken Sie auf **exportieren**.
    
    Die Suchergebnisse werden zum Herunterladen vorbereitet, was bedeutet, dass Sie in den Azure-Speicherbereich für Ihre Organisation in der Microsoft-Cloud hochgeladen werden. In den nächsten Schritten wird gezeigt, wie Sie diese Daten auf den lokalen Computer herunterladen.
    
6. Klicken Sie auf die Registerkarte **exportieren** , um den von Ihnen erstellten Exportauftrag anzuzeigen. Export Aufträge haben denselben Namen wie die entsprechende Suche, wobei **_Export** an das Ende des Such namens angehängt wird. 
    
7. Klicken Sie auf den soeben erstellten Exportauftrag, um die Seite Flyout exportieren anzuzeigen. Auf dieser Seite werden Informationen zur Suche angezeigt, beispielsweise die Größe und Gesamtanzahl der zu exportierenden Elemente sowie der Prozentsatz der Elemente, die in einen Azure-Speicherbereich übertragen wurden. Klicken Sie auf **Aktualisieren** , um die Statusinformationen für den Upload zu aktualisieren. 
    
8. Klicken Sie unter **Schlüssel exportieren** auf **In Zwischenablage kopieren**. Sie verwenden diesen Schlüssel in Schritt 11, um die Suchergebnisse herunterzuladen.
    
9. Klicken ![Sie oben auf der](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) Seite Flyout exportieren auf Suchergebnisse-Symbol **Download Ergebnisse** exportieren. 
    
10. Klicken Sie im Popupfenster unten auf der Seite auf **Öffnen** , um das **eDiscovery-Export Tool Microsoft Office 365**zu öffnen. Das **eDiscovery-Export Tool** wird installiert, wenn Sie die Suchergebnisse zum ersten Mal herunterladen. 
    
11. Fügen Sie im **eDiscovery-Export Tool**den Exportschlüssel, den Sie in Schritt 8 kopiert haben, in das entsprechende Feld ein.
    
12. Klicken Sie auf **Durchsuchen**, um das Verzeichnis anzugeben, in das die Dateien mit den Suchergebnissen heruntergeladen werden sollen. 
    
    > [!NOTE]
    > Aufgrund der hohen Menge an Datenträgeraktivität (Lese-und Schreibvorgänge) sollten Sie Suchergebnisse auf ein lokales Laufwerk herunterladen. Laden Sie Sie nicht auf ein zugeordnetes Netzlaufwerk oder einen anderen Netzwerkspeicherort herunter. 
  
13. Klicken Sie zum Herunterladen der Suchergebnisse auf Ihren Computer auf **Starten**. 
    
    Im **eDiscovery-Export Tool** werden Statusinformationen zum Exportprozess angezeigt, einschließlich einer Schätzung der Zahl (und der Größe) der restlichen Elemente, die heruntergeladen werden sollen. Wenn der Exportvorgang abgeschlossen ist, können Sie auf die Dateien an dem Speicherort zugreifen, an dem Sie heruntergeladen wurden. Weitere Informationen zu den Berichten, die beim Herunterladen von Inhalts Suchergebnissen enthalten sind, finden Sie im Abschnitt [Weitere Informationen](export-search-results.md#more-information) unter "Exportieren von Inhalts Suchergebnissen". 
    
Nachdem die Daten exportiert wurden, befinden sich die Suchergebnisse und Export Berichte in einem Ordner mit demselben Namen wie der DSR-Fall. Die PST-Dateien, die Postfachelemente enthalten, befinden sich in einem Unterordner mit dem Namen **Exchange**. Dokumente und andere Elemente von Websites befinden sich in einem Unterordner mit dem Namen **SharePoint**. 
  
## <a name="optional-step-5-revise-the-built-in-search-query"></a>Optional Schritt 5: Überarbeiten der integrierten Suchabfrage

Nachdem Sie die integrierte Suche ausgeführt haben, können Sie Sie überarbeiten, um den Bereich einzuschränken, sodass weniger Suchergebnisse zurückgegeben werden. Sie können dies tun, indem Sie der Abfragebedingungen hinzufügen. Eine Bedingung ist logisch mit der Stichwortabfrage durch den **and-** Operator verbunden. Das bedeutet, dass in den Suchergebnissen zurückgegeben werden soll, dass Elemente sowohl die Stichwortabfrage als auch alle Bedingungen erfüllen müssen, die Sie hinzufügen. So helfen Bedingungen beim Eingrenzen der Ergebnisse. Wenn Sie einer Suchabfrage zwei oder mehr eindeutige Bedingungen hinzufügen (Bedingungen, die unterschiedliche Eigenschaften angeben), werden diese Bedingungen durch den **and-** Operator logisch miteinander verbunden. Das bedeutet, dass nur Elemente zurückgegeben werden, die alle Bedingungen (zusätzlich zur Stichwortabfrage) erfüllen. Wenn Sie mehrere Werte (durch Kommas oder Semikolons getrennt) zu einer einzelnen Bedingung hinzufügen, werden diese Werte durch den **or** -Operator miteinander verbunden. Das bedeutet, es werden Elemente zurückgegeben, die einen der angegebenen Werte für die Eigenschaft in der Bedingung enthalten. 
  
Im folgenden finden Sie einige Beispiele für die Bedingungen, die Sie der integrierten Suchabfrage eines DSR-Falls hinzufügen können. Der Name der tatsächlichen Eigenschaft, die in einer Suchabfrage verwendet wird, wird in Klammern angezeigt.
  
- **Dateityp ( `filetype`)** – gibt die Erweiterung eines Dokuments oder einer Datei an. Verwenden Sie diese Bedingung, um nach Dokumenten und Dateien zu suchen, die von bestimmten Office-Anwendungen wie Word, Excel und OneNote erstellt wurden. 
    
- **Message Type ( `kind`)** – gibt den Typ des zu suchenden e-Mail-Elements an. Beispielsweise können Sie die Syntax `kind:email OR kind:im` verwenden, um nur e-Mail-Nachrichten und Skype for Business-Unterhaltungen oder 1:1-Chats in Microsoft Teams zurückzugeben. 
    
- **Compliance-Tag`compliancetag`()** – gibt eine Bezeichnung an, die einer e-Mail-Nachricht oder einem Dokument zugewiesen ist. Diese Bedingung gibt Elemente zurück, die mit einer bestimmten Bezeichnung klassifiziert sind. Bezeichnungen werden verwendet, um e-Mails und Dokumente für die Datensteuerung zu klassifizieren und Aufbewahrungsregeln basierend auf der Klassifizierung durchzusetzen, die von der Bezeichnung definiert wird. Dies ist eine nützliche Bedingung für DSR-Untersuchungen, da Ihre Organisation möglicherweise Bezeichnungen verwendet, um Inhalte im Zusammenhang mit dem Datenschutz zu klassifizieren oder personenbezogene Daten oder vertrauliche Informationen enthält. Verwenden Sie für den Wert dieser Bedingung den vollständigen Bezeichnungsnamen oder den ersten Teil des Bezeichnungsnamens mit einem Platzhalter. Weitere Informationen finden Sie unter [Overview of Labels in Office 365](labels.md).
    
Eine Liste und eine Beschreibung aller im DSR-Case-Tool verfügbaren Bedingungen finden Sie unter [Suchbedingungen](keyword-queries-and-search-conditions.md#search-conditions) im Artikel "Stichwortabfragen und Suchbedingungen für die Inhaltssuche". 
  
### <a name="changing-the-content-locations-that-are-searched"></a>Ändern der durchsuchten inhaltsspeicherorte

Zusätzlich zur Überarbeitung der integrierten Suche für einen DSR-Fall können Sie auch die durchsuchten inhaltsspeicherorte ändern. Wie bereits erläutert, durchsucht die integrierte Suche alle Postfächer und Websites in der Organisation sowie alle Exchange Online öffentlichen Ordner. Beispielsweise können Sie die Suche einschränken, um nur das Postfach und das OneDrive-Konto der betroffenen Person und ausgewählte SharePoint-Websites zu durchsuchen. Wenn Sie bestimmte Websites durchsuchen möchten, müssen Sie jede Website hinzufügen, die Sie durchsuchen möchten.
  
So ändern Sie die inhaltsspeicherorte für die Suche:
  
1. Öffnen Sie die integrierte Suche, für die Sie die inhaltsspeicherorte ändern möchten.
    
2. Klicken Sie in der Suchabfrage unter **Standorte**neben der Option **bestimmte Speicherorte** auf **ändern** . 
    
    ![Klicken Sie auf ändern, um die inhaltsspeicherorte der integrierten Suchabfrage zu ändern.](media/d66f7ba7-b71f-4ff5-a030-460ff02e3123.png)
  
    Die Flyout-Seite " **Speicherorte ändern** " wird angezeigt. Im folgenden finden Sie eine Beschreibung der inhaltsspeicherorte in der integrierten Suche und einige Informationen zum Ändern der Speicherorte, die durchsucht werden. 
    
    ![Flyout-Seite "Speicherorte ändern"](media/56c033f6-6735-46ba-abb2-a263a2b79836.png)
  
    a. Die Umschaltfläche unter alle in Postfach **auswählen** im oberen Bereich der Flyout-Seite ist aktiviert, was bedeutet, dass alle Postfächer durchsucht werden. Um den Suchbereich einzuschränken, klicken Sie auf die Umschaltfläche, um die Auswahl aufzuheben, und klicken Sie dann auf **Benutzer, Gruppen oder Teams auswählen** , und wählen Sie die zu durchsuchenden bestimmten Postfächer aus.
    
    b. Die Umschaltfläche unter **Alle auswählen** im Abschnitt Websites in der Mitte der Flyout-Seite wird ausgewählt, wodurch angegeben wird, dass alle Websites durchsucht werden. Um die Suche auf ausgewählte Websites einzuschränken, deaktivieren Sie die Auswahl der Umschaltfläche, und klicken Sie dann auf **Websites auswählen**. Sie müssen jede einzelne Website hinzufügen, die Sie durchsuchen möchten, einschließlich des OneDrive-Kontos der betroffenen Person.
    
    c. Die Umschaltfläche im Abschnitt Öffentliche Ordner in Exchange wird ausgewählt, was bedeutet, dass alle öffentlichen Exchange-Ordner durchsucht werden. Sie können nur alle öffentlichen Exchange-Ordner oder keine dieser Personen durchsuchen. Sie können keine bestimmten Suchkriterien auswählen.
    
3. Wenn Sie die inhaltsspeicherorte in der integrierten Suche ändern, klicken Sie **auf &amp; Run speichern** , um die Suche neu zu starten. 

> [!NOTE]
> Wenn Sie alle Postfachspeicher Orte oder nur bestimmte Postfächer durchsuchen, werden Daten aus anderen Office 365-Anwendungen, die in Benutzerpostfächern gespeichert sind, beim Exportieren der Suchergebnisse eingeschlossen. Diese Daten werden nicht in die geschätzten Suchergebnisse einbezogen und sind für die Vorschau nicht verfügbar. Aber es ist enthalten, wenn Sie die Suchergebnisse exportieren und herunterladen. Weitere Informationen zu den Anwendungen, die Daten im Postfach eines Benutzers speichern, finden Sie unter [in Exchange Online Postfächern gespeicherte Inhalte](what-is-stored-in-exo-mailbox.md).
  
## <a name="more-information-about-using-the-dsr-case-tool"></a>Weitere Informationen zur Verwendung des DSR-Fall Tools

Die folgenden Abschnitte enthalten weitere Informationen zur Verwendung des DSR-Fall Tools, um auf DSR-Exportanforderungen zu reagieren.
  
[Exportieren von Daten aus dem Office Roaming-Dienst](#exporting-data-from-the-office-roaming-service)

[Exportieren von teilweise indizierten Elementen](#exporting-partially-indexed-items)

[Suchen und Exportieren von Daten aus Microsoft Teams und Office 365 Gruppen](#searching-and-exporting-data-from-microsoft-teams-and-office-365-groups)

[Durchsuchen öffentlicher Exchange-Ordner](#searching-exchange-public-folders)
  
### <a name="exporting-data-from-the-office-roaming-service"></a>Exportieren von Daten aus dem Office Roaming-Dienst

Sie können das DSR-Case-Tool verwenden, um Verwendungsdaten zu suchen und zu exportieren, die vom Office-Roamingdienst generiert wurden. Roaming ist ein Dienst, in dem Office-bezogene Einstellungen wie Office-Design, Benutzerwörterbuch, Spracheinstellungen, Entwicklermodus und automatische Korrektur gespeichert werden. 
    
Die Daten aus dem Office-Roamingdienst werden in einem Datensubjekt Postfach in einem verborgenen Ordner gespeichert, der sich in einer nicht-zwischenmenschlichen Nachricht (nicht IPM) Unterstruktur von Exchange Online Postfächern befindet. Dies bedeutet, dass die Daten aus der Sicht des Benutzers ausgeblendet werden, wenn Sie Outlook oder andere e-Mail-Clients verwenden, um auf Ihr Postfach zuzugreifen. Weitere Informationen zu ausgeblendeten Ordnern finden Sie unter [MAPI Hidden Folders](https://go.microsoft.com/fwlink/?linkid=872758).
  
Sie können eine separate Inhaltssuche erstellen (und Sie einem DSR-Fall zuordnen), der die Nutzungsdaten des Office-Roaming-Diensts im Postfach der betroffenen Person zurückgibt. Diese Daten sind nicht in den Suchstatistiken enthalten und stehen nicht für die Vorschau zur Verfügung. Sie können Sie jedoch exportieren und dann als Reaktion auf eine Anforderung des DSR-Exports an die betroffene Person weitergeben.
  
Wenn Sie Daten aus dem Office-Roamingdienst exportieren, werden die Daten in einem separaten Ordner gespeichert, der sich im Ordner **ApplicationDataRoot** befindet, der sich unter einem Ordner namens mit der e-Mail-Adresse der betroffenen Person befindet. Diese Daten werden als JSON-Dateien exportiert, bei denen es sich um lesbare Textdateien wie XML-oder TXT-Dateien handelt, die an e-Mail-Nachrichten angefügt sind. Derzeit ist dieser Ordner mit dem Globally Unique Identifier (GUID) benannt: **1caee58f-eb14-4a6b-9339-1fe2ddf6692b**. In zukünftigen Versionen des DSR-Fall Tools wird die GUID durch den Namen der tatsächlichen Anwendung ersetzt. 

   
 **So suchen und exportieren Sie Office-Server gespeicherte Dienst Daten:**
  
1. Klicken Sie im Security #a0 Compliance Center auf **Datenschutz** \> **Antragsteller Anforderungen**, und klicken Sie dann neben dem DSR-Fall für die betroffene Person, für die Sie Verwendungsdaten exportieren möchten, auf **Öffnen** . 
    
2. Klicken Sie oben auf der Seite auf die Registerkarte **Suche** , und klicken ![Sie dann](media/ITPro-EAC-AddIcon.gif) auf Symbol **gesteuerte Suche**hinzufügen.
    
3. Klicken Sie auf der Seite **Name Ihrer Suche** auf **Abbrechen** . 
    
4. Aktivieren Sie unter **Suchabfrage**in der Bedingung **Typ** das Kontrollkästchen neben Office- **Roamingdienst**. 
    
    ![Aktivieren Sie das Kontrollkästchen Office Roaming Service, um Verwendungsdaten zu exportieren.](media/O365_DSRCase_SDSDataExport1.png)
  
    Die **Typ** -Bedingung (e-Mail-Nachrichtenklassen) sollte das einzige Element in der Suchabfrage sein. Sie können das Feld **Schlüsselwörter** löschen oder leer lassen. 
    
5. Stellen Sie sicher, dass unter **Standorte**die Option **bestimmte Speicherorte** ausgewählt ist, und klicken Sie dann auf **ändern**.
    
6. Klicken Sie im oberen Teil der Flyout-Seite " **Speicherorte ändern** " (Postfach) auf **Benutzer, Gruppen oder Teams auswählen**.
    
7. Klicken Sie auf der Seite " **Speicherorte bearbeiten** " auf **Benutzer, Gruppen oder Teams auswählen**, wählen Sie das Postfach des Daten Antragstellers aus, und speichern Sie dann Ihre Auswahl. 
    
8. Klicken Sie auf **#a0 ausführen speichern**, und benennen Sie die Suche, und speichern Sie Sie.
    
    Die Suche wird gestartet.
    
 **So exportieren Sie Office-Roaming-Dienst Daten:**
  
1. Wenn die im vorherigen Schritt erstellte Suche abgeschlossen ist, klicken Sie oben auf der Seite auf die Registerkarte **Suche** , und klicken Sie dann auf das Kontrollkästchen neben der Suche. Möglicherweise müssen Sie ![auf](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) **Aktualisierung aktualisieren klicken, um die** Suche anzuzeigen. 
    
2. Klicken Sie ![auf der Seite Flyout-Suche auf Suchergebnisse](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **exportieren, und**wählen Sie dann **Ergebnisse exportieren** aus der Dropdownliste aus. 
    
3. Wählen Sie auf der Seite **Ergebnisse exportieren** die empfohlenen Optionen zum Exportieren von Verwendungsdaten aus. 
    
    ![Exportoptionen beim Exportieren von Nutzungsdaten des Office-Roaming-Diensts](media/470a7d1e-eeae-4b42-95aa-15cb82ce2f68.png)
  
    a. Wählen Sie unter **Ausgabeoptionen**die erste Option (**alle Elemente, ausgenommen diejenigen, die über ein nicht erkanntes Format verfügen, verschlüsselt sind oder aus anderen Gründen nicht indiziert**wurden) aus, um nur indizierte Elemente zu exportieren.
    
    b. Wählen Sie unter **Exchange-Inhalt exportieren als**die zweite Option aus, **eine PST-Datei, die alle Nachrichten enthält**.
    
    c. Lassen Sie die restlichen Exportoptionen nicht ausgewählt.
    
4. Nachdem Sie die Exporteinstellungen ausgewählt haben, klicken Sie auf **exportieren**.
    
    Die Suchergebnisse werden zum Herunterladen vorbereitet, was bedeutet, dass Sie in den Azure-Speicherbereich für Ihre Organisation in der Microsoft-Cloud hochgeladen werden. In den nächsten Schritten wird gezeigt, wie Sie diese Daten auf den lokalen Computer herunterladen.
    
5. Klicken Sie auf die Registerkarte **exportieren** , um den von Ihnen erstellten Exportauftrag anzuzeigen. Die Exportaufträge haben den gleichen Namen wie die entsprechende Suche, wobei **_Export** an das Ende des Such namens angehängt wird. 
    
6. Klicken Sie auf den soeben erstellten Exportauftrag, um die Seite Flyout exportieren anzuzeigen. 
    
7. Klicken Sie unter **Schlüssel exportieren** auf **In Zwischenablage kopieren**. Sie verwenden diesen Schlüssel in Schritt 10, um die Suchergebnisse herunterzuladen.
    
8. Klicken ![Sie oben auf der](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) Seite Flyout exportieren auf Suchergebnisse-Symbol **Download Ergebnisse** exportieren. 
    
9. Klicken Sie im Popupfenster unten auf der Seite auf **Öffnen** , um das **eDiscovery-Export Tool Microsoft Office 365**zu öffnen. Das **eDiscovery-Export Tool** wird installiert, wenn Sie die Suchergebnisse zum ersten Mal herunterladen. 
    
10. Fügen Sie im **eDiscovery-Exporttool** den Export-Schlüssel, den Sie in Schritt 7 kopiert haben, in das entsprechende Feld ein.
    
11. Klicken Sie auf **Durchsuchen**, um das Verzeichnis anzugeben, in das die Dateien mit den Suchergebnissen heruntergeladen werden sollen. 
    
    > [!NOTE]
    > Aufgrund der hohen Menge an Datenträgeraktivität (Lese-und Schreibvorgänge) sollten Sie Suchergebnisse auf ein lokales Laufwerk herunterladen. Laden Sie Sie nicht auf ein zugeordnetes Netzlaufwerk oder einen anderen Netzwerkspeicherort herunter. 
  
12. Klicken Sie zum Herunterladen der Suchergebnisse auf Ihren Computer auf **Starten**. 
    
    Im **eDiscovery-Export Tool** werden Statusinformationen zum Exportprozess angezeigt, einschließlich einer Schätzung der Zahl (und der Größe) der restlichen Elemente, die heruntergeladen werden sollen. Wenn der Exportvorgang abgeschlossen ist, können Sie die Exchange-PST-Datei in Outlook öffnen und dann zum Ordner **ApplicationDataRoot** wechseln, um auf den Unterordner des Roaming-Diensts zuzugreifen. 
    
    Wie bereits erläutert, werden die JSON-Dateien, die Verwendungsdaten enthalten, an Nachrichten angefügt. Wenn Sie eine JSON-Datei anzeigen möchten, klicken Sie auf eine Nachricht, und öffnen Sie dann die angefügte JSON-Datei. 
  
### <a name="exporting-partially-indexed-items"></a>Exportieren von teilweise indizierten Elementen

Es wird empfohlen, nicht teilweise indizierte Elemente (auch nicht indexierte Elemente genannt) aus der integrierten Suche zu exportieren, die beim Erstellen eines DSR-Falls erstellt wurde. Das liegt daran, dass die Suchergebnisse mehr als wahrscheinlich teilweise indizierte Elemente für andere Benutzer in Ihrer Organisation und nicht nur teilweise indizierte Elemente für die betroffene Person enthalten werden). Stattdessen wird empfohlen, eine separate Inhaltssuche zu erstellen, die dem DSR-Fall zugeordnet ist, der nur die teilweise indizierten Elemente im Zusammenhang mit der betroffenen Person exportieren soll. 
  
Im folgenden finden Sie einen allgemeinen Prozess zum Exportieren von teilweise indizierten Elementen. Nachdem Sie exportiert wurden, können Sie diese überprüfen, um zu ermitteln, ob ein Element auf eine DSR-Zugriffs-oder Exportanforderung reagiert.
  
1. Öffnen Sie den DSR-Fall, und erstellen Sie eine Suche auf der Seite **Suche** . 
    
2. Verwenden Sie die folgenden Kriterien zum Konfigurieren der Suchabfrage und der inhaltsspeicherorte für die Suche:
    
    - Verwenden Sie eine leere/leere Stichwortabfrage. Dadurch werden alle Elemente an den durchsuchten Inhaltsspeicherorten zurückgegeben.
    
    - Durchsuchen Sie nur die Exchange Online Postfachs der betroffenen Person und Ihr OneDrive-Konto.
    
3. Nachdem Sie die Suche ausgeführt und abgeschlossen haben, können Sie die Suchergebnisse exportieren und herunterladen (wie in [Schritt 4](#step-4-export-the-data)beschrieben). Verwenden Sie die folgenden Einstellungen, um teilweise indizierte Elemente zu exportieren. 
    
    - Wählen Sie unter **Ausgabeoptionen**die dritte Option (**nur Elemente, die über ein nicht erkanntes Format verfügen, verschlüsselt sind oder aus anderen Gründen nicht indiziert**wurden) aus, um nur teilweise indizierte Elemente zu exportieren.
    
    - Unter **Exchange-Inhalte exportieren als**können Sie eine beliebige Option basierend auf Ihren Einstellungen auswählen. 
    
    - Wenn Sie die Option **Versionen für SharePoint-Dokumente einschließen** auswählen, werden Versionen von Dokumenten exportiert, wenn eine Version teilweise indiziert ist. 
    
Weitere Informationen zu teilweise indizierten Elementen finden Sie unter: 
  
- [Teilweise indizierte Elemente in der Inhaltssuche in Office 365](partially-indexed-items-in-content-search.md)

- [Exportieren von teilweise indizierten Elementen](export-search-results.md#exporting-partially-indexed-items)
    
### <a name="searching-and-exporting-data-from-microsoft-teams-and-office-365-groups"></a>Suchen und Exportieren von Daten aus Microsoft Teams und Office 365 Gruppen

Unterhaltungen, die Teil der Chat Liste in Microsoft Teams sind (als teamchats oder One-to-One-Chat bezeichnet) werden im Exchange Online Postfach der Benutzer gespeichert, die an den Chats teilnehmen. Außerdem werden die Dateien, die eine Person in einem eins-zu-eins-Chat freigibt, im OneDrive-Konto der Person gespeichert, die die Datei freigibt. Da die integrierte Suche alle Postfächer und OneDrive-Konten in der Organisation durchsucht, werden Team-Chats und Dokumente, die in einer Chatsitzung freigegeben sind (dass die betroffene Person erstellt oder hochgeladen hat) von der integrierten Suche in einem DSR-Fall zurückgegeben.
  
Alternativ werden Unterhaltungen, die Teil eines Teams-Kanals (auch Kanal Nachrichten genannt) sind, in dem Postfach gespeichert, das einem Team zugeordnet ist. Diese Arten von Unterhaltungen, an denen die betroffene Person teilgenommen hat, werden auch von der integrierten Suche zurückgegeben, da alle mit Microsoft Teams verknüpften Postfächer durchsucht werden. Darüber hinaus werden Dateien, die ein Datensubjekt in einem Teams-Kanal freigibt, auf der SharePoint-Website des Teams gespeichert. Dateien, die von der betroffenen Person erstellt oder hochgeladen wurden, werden von der integrierten Suche in einem DSR-Fall zurückgegeben, da die mit Microsoft Teams verknüpften Websites in der Suche enthalten sind.
  
Ebenso sind Postfächer und SharePoint-Websites, die einer Office 365 Gruppe entsprechen, ebenfalls in der integrierten Suche enthalten. Dies bedeutet, dass e-Mail-Nachrichten, die von der betroffenen Person gesendet oder empfangen werden, und Dateien zurückgegeben werden, die von der betroffenen Person erstellt oder hochgeladen wurden 
  
Weitere Informationen zum Verwenden der Inhaltssuche zum Suchen nach Elementen in Microsoft Teams und Office 365 Gruppen oder zum Abrufen einer Liste von Mitgliedern finden Sie im Abschnitt "Durchsuchen von Microsoft Teams und Office 365 Gruppen" in der [Inhaltssuche in Office 365](content-search.md#searching-microsoft-teams-and-office-365-groups). 
  
### <a name="searching-exchange-public-folders"></a>Durchsuchen öffentlicher Exchange-Ordner

Bei der integrierten Suche in einem DSR-Fall werden nur e-Mail-Nachrichten zurückgegeben, die von der betroffenen Person an einen e-Mail-aktivierten Öffentlichen Ordner gesendet wurden, oder Nachrichten, die ein anderer Benutzer an einen öffentlichen Ordner gesendet und auch die betroffene Person kopiert hat. Es werden keine Nachrichten zurückgegeben, die die betroffene Person in einen öffentlichen Ordner gepostet hat. Um nach Elementen zu suchen, die die betroffene Person in einem öffentlichen Ordner veröffentlicht hat, können Sie eine separate Erstellen einer separaten Inhaltssuche erstellen, die nach jedem Element sucht, das von der betroffenen Person in einem öffentlichen Ordner gepostet wurde.
  
Im folgenden finden Sie einen allgemeinen Prozess für die Suche nach Elementen, die die betroffene Person in einem öffentlichen Ordner veröffentlicht hat. 
  
1. Öffnen Sie den DSR-Fall, und erstellen Sie eine Suche auf der Seite **Suche** . 
    
2. Verwenden Sie die folgenden Kriterien zum Konfigurieren der Suchabfrage und der inhaltsspeicherorte für die Suche:
    
  - Verwenden Sie im Feld **Schlüsselwörter** die folgende Suchabfrage: 
    
    ```powershell
    itemclass:ipm.post AND "<email address of the data subject>"
    ```

  - Durchsuchen aller öffentlichen Exchange-Ordner
    
  - Nachdem Sie die Suche ausgeführt und abgeschlossen haben, können Sie die Suchergebnisse exportieren und herunterladen (wie in [Schritt 4](#step-4-export-the-data)beschrieben). Verwenden Sie die folgenden Einstellungen, um teilweise indizierte Elemente zu exportieren. 
