---
title: Ausführen einer Inhaltssuche im Security & Compliance Center
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ComplianceSearch
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 61852fd9-fe8a-4880-a339-cb19ed3bff4a
description: 'Verwenden Sie die Inhaltssuche im Security #a0 Compliance Center zum Durchsuchen von Postfächern, SharePoint Online Websites und OneDrive für Unternehmen Speicherorten. '
ms.openlocfilehash: cebdbf7808534b82085affa16c06ac1929b3fd8d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081985"
---
# <a name="run-a-content-search-in-the-security--compliance-center"></a>Ausführen einer Inhaltssuche im Security & Compliance Center

Sie können das eDiscovery-Tool für die Inhaltssuche im Security #a0 Compliance Center verwenden, um nach Elementen wie e-Mails, Dokumenten und Chat Unterhaltungen in Ihrer Office 365 Organisation zu suchen. Verwenden Sie dieses Tool, um nach Elementen in diesen Office 365 Diensten zu suchen:
  
- Exchange Online von Postfächern und öffentlichen Ordnern
    
- SharePoint Online-und OneDrive für Unternehmen-Websites
    
- Skype for Business Unterhaltungen
    
- Microsoft Teams 
    
- Office 365-Gruppen
    
Die Inhaltssuche ist ein neues eDiscovery-Such Tool mit neuen und verbesserten Skalierungs-und Leistungsfunktionen. Verwenden Sie die Inhaltssuche, um sehr umfangreiche eDiscovery-suchen auszuführen. Sie können alle Postfächer, alle öffentlichen Exchange-Ordner und alle SharePoint Online Websites und OneDrive für Unternehmen Konten in einer einzigen Inhaltssuche durchsuchen. Es gibt keine Beschränkungen für die Anzahl der inhaltsspeicherorte, die Sie durchsuchen können. Außerdem gibt es keine Beschränkungen für die Anzahl der Suchvorgänge, die gleichzeitig ausgeführt werden können. Nachdem Sie eine Inhaltssuche ausgeführt haben, werden die Anzahl der inhaltsspeicherorte und die geschätzte Anzahl der Suchergebnisse im Detailbereich auf der Seite **Inhaltssuche** angezeigt. Nachdem Sie eine Suche ausgeführt haben, können Sie eine Vorschau der Ergebnisse anzeigen, Schlüsselwort Statistiken für eine oder mehrere Suchvorgänge abrufen, die Inhaltssuche Massen bearbeiten und die Ergebnisse auf einen lokalen Computer exportieren. 
  
 **Inhalt**
  
[Create a search](run-a-content-search-in-the-security-and-compliance-center.md#create)
  
[Exportieren der Suchergebnisse](run-a-content-search-in-the-security-and-compliance-center.md#export)
  
[Preview search results](run-a-content-search-in-the-security-and-compliance-center.md#preview)
  
[Update search results](run-a-content-search-in-the-security-and-compliance-center.md#restart)
  
[Edit a search](run-a-content-search-in-the-security-and-compliance-center.md#edit)
  
[Retry a search](run-a-content-search-in-the-security-and-compliance-center.md#retry)
  

  
## <a name="before-you-begin"></a>Bevor Sie beginnen

- Informationen und Anleitungen zum Erstellen von Suchabfragen und zum Verwenden von booleschen Suchoperatoren finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md). Dieser Artikel enthält auch Informationen zum Suchen nach vertraulichen Informationstypen und zum Suchen nach Inhalten, die für Personen innerhalb und außerhalb Ihrer Organisation freigegeben sind.
    
- Wenn Sie Zugriff auf die Seite für die **Inhaltssuche** haben möchten, um Suchergebnisse durchzuführen und eine Vorschau anzuzeigen und zu exportieren, müssen ein Administrator, ein Compliance Officer oder ein eDiscovery-Manager Mitglied der Rollengruppe "eDiscovery-Manager" im Security #a0 Compliance Center sein. Sie müssen keine zusätzlichen Suchberechtigungen in Exchange Online, SharePoint Online oder für OneDrive für Unternehmen Websites zuweisen. Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Office 365 Security #a0 Compliance Center](assign-ediscovery-permissions.md).
    
- Es gibt Beschränkungen, die auf die Inhaltssuche angewendet werden, um die Integrität und Qualität von Diensten zu gewährleisten, die Office 365 Organisationen bereitgestellt werden. In den meisten Fällen können diese Grenzwerte nicht geändert werden, Sie sollten die Werte jedoch beachten, damit Sie die Grenzen bei der Planung, beim Ausführen und bei der Problembehandlung von Suchvorgängen berücksichtigen können. Weitere Informationen finden Sie unter [Grenzwerte für die Suche im Security #a0 Compliance Center](limits-for-content-search.md).
    
- Lesen Sie den Abschnitt Geschätzte Suchzeiten basierend auf der Anzahl von Postfächern, die in einer einzelnen Inhaltssuche durchsucht werden. 
    
- Wie bereits erwähnt, können Sie die Inhaltssuche verwenden, um nach Inhalten in Office 365 Gruppen und Microsoft Teams zu suchen. Dies bedeutet, dass Sie das Gruppenpostfach, den freigegebenen Kalender und die SharePoint-Websites durchsuchen können, die einer Office 365 Gruppe und einem Microsoft-Team zugeordnet sind. Darüber hinaus können Sie die Kanal Unterhaltungen in einem Microsoft-Team durchsuchen. Informationen zu Office 365 Gruppen und Microsoft Teams finden Sie unter:
    
  - [Informationen zu Office 365 Gruppen](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
    
  - [Hilfe zu Microsoft Teams](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
    Im Abschnitt finden Sie Tipps zum Suchen nach Inhalten in Office 365 Gruppen und Microsoft Teams. 
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="create-a-search"></a>Create a search
<a name="create"> </a>

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich bei Office 365 mit Ihrem Geschäfts-, Schul- oder Unikonto an.
    
3. Klicken Sie im linken Bereich des Security #a0 Compliance Centers auf **Such** \> **Inhaltssuche**.
    
4. Klicken Sie auf **Neu**![Hinzufügen (Symbol)](media/O365-MDM-CreatePolicy-AddIcon.gif).
    
5. Geben Sie auf der Seite **Neue Suche** einen Namen für die Inhaltssuche ein. Dieser Name muss in der Organisation eindeutig sein. 
    
6. Wählen Sie die inhaltsspeicherorte aus, die Sie durchsuchen möchten. Sie können Postfächer, Websites und öffentliche Ordner in derselben Suche durchsuchen.
    
    ![Wählen Sie die inhaltsspeicherorte aus, die Sie durchsuchen möchten.](media/da32e3f9-6cd6-4a26-8217-e97a5a7071e4.png)
  
1. **Überall suchen** Wählen Sie diese Option aus, um alle inhaltsspeicherorte in Ihrer Organisation zu durchsuchen. Wenn Sie diese Option auswählen, können Sie auswählen, dass alle Postfächer durchsucht werden sollen (einschließlich inaktiver Postfächer und der Postfächer für alle Office 365 Gruppen und Microsoft Teams), alle SharePoint-und OneDrive für Unternehmen-Websites (die die Websites für alle Office 365 Gruppen enthalten und Microsoft Teams) und alle öffentlichen Ordner.
    
    ![Klicken Sie auf die Option überall suchen, um alle inhaltsspeicherorte zu durchsuchen.](media/86f132f1-0a2a-4048-900c-9f219d909ef2.png)
  
2. **Benutzerdefinierte Standortauswahl** Wählen Sie diese Option aus, um die Postfächer und Websites auszuwählen, die Sie durchsuchen möchten. Wenn Sie diese Option auswählen, haben Sie die Flexibilität, alle inhaltsspeicherorte für einen bestimmten Dienst zu durchsuchen (beispielsweisedurch Suchen aller Exchange-Postfächer), oder Sie können bestimmte inhaltsspeicherorte für einen Office 365 Dienst durchsuchen.
    
    Beachten Sie beim Hinzufügen von Inhaltsspeicherorten zur Suche Folgendes:
    
    **Postfächer**
    
  - Wenn Sie auf Add-Symbol](media/ITPro-EAC-AddIcon.gif) **Hinzufügen**![klicken, um die zu durchsuchenden Postfächer anzugeben, ist die angezeigte Post Fachauswahl leer. Dies ist beabsichtigt, um die Leistung zu verbessern. Wenn Sie dieser Liste Empfänger hinzufügen möchten, geben Sie einen Namen (mindestens 3 Zeichen) in das Suchfeld ein, ****![und klicken Sie](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)auf Suchsymbol suchen.
    
  - Sie können inaktive Postfächer und Verteilergruppen zur Liste der zu durchsuchenden Postfächer hinzufügen. Für Verteilergruppen werden die Postfächer von Gruppenmitgliedern durchsucht. Beachten Sie, dass dynamische Verteilergruppen nicht unterstützt werden.
    
  - Um eine Liste der inaktiven Postfächer in Ihrer Organisation abzurufen, führen `Get-Mailbox -InactiveMailboxOnly` Sie den Befehl in Exchange Online PowerShell aus. Alternativ können Sie im Security #a0 Compliance Center zur **Aufbewahrung** von **Datenverwaltung** \> wechseln und dann auf **Weitere**![Navigationsleiste Ellipsen](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **inaktive Postfächer**klicken.
    
  - Sie können auch das Postfach hinzufügen, das einer Office 365 Gruppe oder einem Microsoft-Team zugeordnet ist. In diesem Fall wird nur das Gruppen-oder Team Postfach durchsucht; die Postfächer der Gruppe oder der Teammitglieder werden nicht durchsucht. Um Sie durchsuchen zu können, müssen Sie Sie explizit der Suche hinzufügen.
    
  - Wenn Sie keine Postfächer für die Suche einbeziehen möchten, wählen Sie **bestimmte Postfächer für die Suche auswählen**aus, aber fügen Sie der Liste kein Postfach hinzu.
    
    **Websites**
    
  - Klicken ****![Sie auf Add](media/ITPro-EAC-AddIcon.gif) -Symbol hinzufügen, um der Suche Websites hinzuzufügen. Geben Sie die URL für jede Website ein, die Sie durchsuchen möchten. Das Inhalts Such Tool überprüft die URL und fügt Sie dann der Liste der zu durchsuchenden Websites hinzu. 
    
  - Sie können die SharePoint-Datei hinzufügen, die einer Office 365 Gruppe oder einem Microsoft-Team zugeordnet ist. Im Abschnitt finden Sie Anleitungen dazu, wie Sie die URL für die Gruppe oder das Team finden. 
    
  - Wenn Sie keine Websites in eine Suche einbeziehen möchten, wählen Sie **bestimmte Websites für die Suche auswählen**aus, aber fügen Sie der Liste keine Website hinzu.
    
    **Öffentliche Ordner**
    
    Bei öffentlichen Ordnern können Sie alle öffentlichen Ordner in Ihrer Exchange Online Organisation durchsuchen oder keine öffentlichen Ordner durchsuchen.
    
7. Klicken Sie dann auf **Weiter**.
    
8. Auf der Seite **Neue Suche** können Sie Schlüsselwörter und Bedingungen zum Erstellen der Suchabfrage hinzufügen. 
    
    ![Erstellen einer Suchabfrage mit Schlüsselwörtern und Bedingungen](media/1b7cf7b5-f1e1-471a-ad5c-48aad8435b00.png)
  
1. Geben Sie im Feld unter **Wonach sollen wir für Sie suchen?** eine Suchabfrage ein. Sie können Schlüsselwörter, Nachrichteneigenschaften , z. B. Sende- und Empfangsdatum, oder Dokumenteigenschaften angeben, z. B. Dateinamen oder das Datum der letzten Dokumentänderung. Sie können komplexere Abfragen verwenden, die einen booleschen Operator verwenden, beispielsweise **and**, **or**, **Not**, **near**oder **ONEAR**. Sie können auch nach vertraulichen Informationen (wie etwa Sozialversicherungsnummern) in Dokumenten suchen oder nach Dokumenten suchen, die extern freigegeben wurden. Wenn Sie das Feld Schlüsselwort leer lassen, werden alle Inhalte, die sich an den angegebenen Inhaltsspeicherorten befinden, in die Suchergebnisse eingeschlossen. 
    
2. Sie können auf das Kontrollkästchen **Keyword-Liste anzeigen** und in jeder Zeile ein Stichwort eingeben. Wenn Sie dies tun, werden die Schlüsselwörter für jede Zeile durch den **or** -Operator in der erstellten Suchabfrage miteinander verbunden. 
    
    ![Sie können ein Stichwort oder eine Stichwort Phase in eine Zeile in der Liste Stichwörter eingeben.](media/aea1a361-639d-4a82-8c3c-48645ef3fc05.png)
  
    Gründe für die Verwendung der Stichwortliste Sie können Statistiken abrufen, die zeigen, wie viele Elemente mit den einzelnen Schlüsselwörtern übereinstimmen. Auf diese Weise können Sie schnell erkennen, welche Stichwörter am häufigsten (und am wenigsten) effektiv sind. Sie können auch eine Stichwort Phrase (umgeben von Klammern) in einer Zeile verwenden. Weitere Informationen zu Suchstatistiken finden Sie unter [Anzeigen von Keyword-Statistiken für Inhalts Suchergebnisse](view-keyword-statistics-for-content-search.md).
    
    Im Abschnitt finden Sie Anleitungen zur Verwendung der Stichwortliste. 
    
3. Klicken Sie auf **Abfrage für Tippfehler überprüfen** , um Ihre Abfrage auf nicht unterstützte Zeichen und boolesche Operatoren zu überprüfen, die möglicherweise nicht groß geschrieben werden. Nicht unterstützte Zeichen werden häufig ausgeblendet und verursachen in der Regel einen Suchfehler oder geben unbeabsichtigte Ergebnisse zurück. Weitere Informationen zu den nicht unterstützten Zeichen, die überprüft werden, finden Sie unter [Überprüfen der Inhalts Suchabfrage auf Fehler](check-your-content-search-query-for-errors.md).
    
4. Fügen Sie unter **Bedingungen**einer Suchabfrage Bedingungen hinzu, um eine Suche einzuschränken und eine verfeinerte Ergebnismenge zurückzugeben. Jede Bedingung fügt eine Klausel zu der KQL-Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird. Eine Bedingung ist durch **AND**-Operator logisch mit der (im Schlüsselwortfeld angegebenen) Schlüsselwortabfrage verbunden. Dies bedeutet, dass Elemente sowohl die Schlüsselwortabfrage als auch die Bedingung erfüllen muss, damit sie in die Suchergebnisse aufgenommen werden. Auf diese Weise können Sie Ihre Ergebnisse mit Bedingungen eingrenzen. 
    
||
|:-----|
|Weitere Informationen zum Erstellen einer Suchabfrage und zum Verwenden von Bedingungen finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche ](keyword-queries-and-search-conditions.md). |
   
9. Klicken Sie auf **Suche**, um die Sucheinstellungen zu speichern und die Suche zu starten. 
    
    Die Suche wird gestartet. Wenn die Suche abgeschlossen ist, werden die folgenden Informationen im Detailbereich angezeigt.
    
    ![Suchstatistiken werden im Detailbereich der ausgewählten Inhaltssuche angezeigt.](media/2046bb5e-f4cb-4ba7-b7fc-8e5e53dae567.png)
  
1. Das Datum und die Uhrzeit der letzten Ausführung der Suche.
    
2. Die Anzahl (und Gesamtgröße) der gefundenen Elemente, die mit der Suchabfrage übereinstimmten. Beispiele für Elementtypen sind e-Mail-Nachrichten, Kalenderelemente und Dokumente. Wenn ein Element mehrere Instanzen eines Schlüsselworts enthält, nach dem gesucht wird, wird es nur einmal in der Gesamtanzahl der Elemente gezählt. Wenn Sie beispielsweise nach Wörtern "Stock" oder "Tip" suchen und eine e-Mail-Nachricht drei Instanzen des Wortes "Stock" enthält, wird Sie nur einmal im **Element** Feld gezählt. 
    
3. Die Anzahl und Gesamtgröße von nicht indizierten Elementen in den durchsuchten Inhaltsspeicherorten. Die Anzahl nicht indizierter Elemente, die den Suchkriterien nicht entsprechen, werden in die Suchstatistiken einbezogen, die im Detailbereich angezeigt werden. Wenn ein nicht indiziertes Element mit der Suchabfrage übereinstimmt (da andere Nachrichten-oder Dokumenteigenschaften die Suchkriterien erfüllen), wird es nicht in die geschätzte Anzahl nicht indexierter Elemente aufgenommen. Wenn ein nicht indiziertes Element jedoch durch die Suchkriterien ausgeschlossen wird, wird es nicht in die Schätzung nicht indexierter Elemente einbezogen.
    
4. Die Anzahl der einzelnen Inhaltsverzeichnis Typen, die durchsucht wurden. Beachten Sie bei Postfächern, dass Archivpostfächer in der Gesamtzahl der durchsuchten Postfächer enthalten sind. Im vorherigen Beispiel wurden vier Benutzerpostfächer durchsucht, und das Archivpostfach für jeden dieser Benutzer ist aktiviert. Deshalb werden in den Suchstatistiken acht Postfächer zitiert.
    
5. Links zur Vorschau der Suchergebnisse oder zum erneuten Ausführen der Suche, um die Suchstatistiken zu aktualisieren.
    
    Klicken Sie bei Bedarf ****![auf Aktualisierungssymbol](media/O365-MDM-Policy-RefreshIcon.gif) aktualisieren, um die Informationen im Detailbereich für die ausgewählte Suche zu aktualisieren. 
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="export-search-results"></a>Exportieren der Suchergebnisse
<a name="export"> </a>

Nachdem eine Suche erfolgreich ausgeführt wurde, können Sie die Suchergebnisse auf einen lokalen Computer exportieren. Wenn Sie E-Mail-Ergebnisse exportieren, werden diese als PST-Dateien auf Ihren Computer heruntergeladen. Wenn Sie Inhalte aus SharePoint und OneDrive für Unternehmen Websites exportieren, werden Kopien von systemeigenen Office-Dokumenten exportiert. Es gibt auch zusätzliche Dokumente und Berichte, die in den exportierten Suchergebnissen enthalten sind. Weitere Informationen finden Sie unter [Exportieren von Suchergebnissen aus dem Security #a0 Compliance Center](export-search-results.md).
  
## <a name="preview-search-results"></a>Suchergebnisse in der Vorschau anzeigen
<a name="preview"> </a>

Nachdem die Suche erfolgreich abgeschlossen wurde, können Sie eine Vorschau der Suchergebnisse anzeigen. Im Zusammenhang mit dem Anzeigen von Inhaltssuchergebnissen in der Vorschau gibt es einige Einschränkungen. Weitere Informationen finden Sie unter [Grenzwerte für die Suche im Security #a0 Compliance Center](limits-for-content-search.md). Beachten Sie, dass nicht indizierte Elemente für die Vorschau nicht verfügbar sind.
  
1. Wählen Sie auf der Seite **Inhaltssuche** eine Suche aus. 
    
2. Klicken Sie im Detailbereich unter **Ergebnisse** auf **Vorschau der Suchergebnisse anzeigen**. Die Seite **Vorschau der Suchergebnisse anzeigen** wird geöffnet und enthält eine Liste der Suchergebnisse. 
    
    Sie können auf eine Spaltenüberschrift klicken, um die Ergebnisse basierend auf Betreff, Typ, Absender oder dem Datum zu sortieren, an dem ein Element im Quellpostfach empfangen wurde.
    
3. Klicken Sie auf ein Element, um es anzuzeigen.
    
    Das Element wird im Vorschaufenster geöffnet.
    
4. Wenn ein Dateityp nicht für die Vorschau oder zum Herunterladen einer Kopie eines Dokuments unterstützt wird, können Sie auf **ursprüngliche Datei herunterladen** klicken, um Sie auf den lokalen Computer herunterzuladen. Für aspx-Webseiten ist die URL für die Seite enthalten, obwohl Sie möglicherweise nicht über Berechtigungen für den Zugriff auf die Seite verfügen. 
    
> [!NOTE]
> Wenn Sie die Suchergebnisse einer Suche, die vor mehr als sieben Tagen ausgeführt wurde, in der Vorschau anzeigen, werden Sie aufgefordert, die Suchergebnisse zu aktualisieren. Die Suche wird erneut ausgeführt, um die aktuellsten Ergebnisse abzurufen, die die Suchabfrage erfüllen. 
  
### <a name="file-types-that-can-be-previewed"></a>Dateitypen, die in der Vorschau angezeigt werden können

Unterstützte Dateitypen können im Vorschaufenster angezeigt werden. Wenn ein Dateityp nicht unterstützt wird, müssen Sie eine Kopie der Datei auf den lokalen Computer herunterladen, um Sie anzuzeigen. Die folgenden Dateitypen werden unterstützt und können in der Vorschau auf der **Suchergebnis** Seite angezeigt werden. 
  
- txt, HTML, MHTML
    
- EML
    
- doc-, docx-, DOCM-
    
- . pptm,. pptx
    
- .pdf
    
Darüber hinaus werden die folgenden Dateicontainer Typen unterstützt. Sie können die Liste der Dateien im Container im Bereich Vorschau anzeigen.
  
- . zip
    
- gzip
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="update-search-results"></a>Aktualisieren von Suchergebnissen
<a name="restart"> </a>

Wenn Sie die Ergebnisse einer vorhandenen Inhaltssuche aktualisieren, wird die Suchabfrage an allen angegebenen Inhaltsspeicherorten erneut ausgeführt. Der offensichtliche Grund, die Suchergebnisse zu aktualisieren, besteht darin, die neuesten Daten abzurufen.
  
1. Wählen Sie auf der Seite **Inhaltssuche** die Suche aus, für die Sie die Ergebnisse aktualisieren möchten. 
    
2. Klicken Sie im Detailbereich unter **Ergebnisse** auf **Suchergebnisse aktualisieren**.
    
    Es wird eine Statusmeldung angezeigt, dass die Ergebnisse abgerufen werden. Wenn die Suche abgeschlossen ist, werden die aktualisierten Informationen unter **Ergebnisse** im Detailbereich angezeigt. Beachten Sie, dass das Datum im Feld **Durchsucht am** im Detailbereich auf das aktuelle Datum und die Uhrzeit aktualisiert wird. Wenn Sie die Informationen in der Liste der Inhalts suchen aktualisieren möchten **, klicken**![Sie](media/O365-MDM-Policy-RefreshIcon.gif)auf Aktualisierungssymbol aktualisieren.
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="edit-a-search"></a>Bearbeiten einer Suche
<a name="edit"> </a>

Sie können die Quellpostfächer und die Suchabfrage für eine vorhandene Inhaltssuche ändern.
  
1. Wählen Sie auf der Seite **Inhaltssuche** eine Suche aus. 
    
2. Klicken Sie im Detailbereich unter **Abfrage** auf **Suche bearbeiten**.
    
3. Auf der Seite **Speicherorte** können Sie die zu durchsuchenden Postfächer, Gruppen, SharePoint-Websites oder OneDrive für Unternehmen Websites ändern. Sie können auch alle öffentlichen Ordner in Exchange durchsuchen oder auswählen. 
    
4. Auf der Seite **Abfrage** können Sie die Suchabfrage bearbeiten. 
    
5. Um die überarbeitete Suche zu starten, klicken Sie auf der Seite **Quellen** oder **Speicherorte** auf **Suchen** . 
    
    Die überarbeitete Suche wird gestartet. Wenn die Suche abgeschlossen ist, werden die geschätzten Ergebnisse für die überarbeitete Suche im Detailbereich angezeigt.
    
## <a name="retry-a-search"></a>Erneutes Ausführen einer Suche
<a name="retry"> </a>

Wenn bei einer Suche Fehler zurückgegeben werden, müssen Sie nicht alle inhaltsspeicherorte erneut durchsuchen. Sie können die Suche erneut ausführen, sodass nur die gescheiterten inhaltsspeicherorte erneut durchsucht werden. Zum erneuten Durchsuchen aller inhaltsspeicherorte können Sie die Suchergebnisse aktualisieren.
  
1. Wählen Sie auf der Seite **Inhaltssuche** die Suche aus, die die inhaltsspeicherorte enthält, die Sie erneut durchsuchen möchten. 
    
2. Klicken Sie im Detailbereich unter **Fehler** auf **Suche wiederholen**.
    
    Es wird eine Statusmeldung angezeigt, dass die Ergebnisse abgerufen werden. Wenn die Suche abgeschlossen ist, werden im Detailbereich unter **Ergebnisse** die aktualisierten Informationen angezeigt. Beachten Sie, dass das Datum im Feld **Durchsucht am** im Detailbereich auf das aktuelle Datum und die Uhrzeit aktualisiert wird. Wenn Sie die Informationen in der Liste der Suchvorgänge aktualisieren möchten **, klicken Sie**![auf Aktualisierungssymbol](media/O365-MDM-Policy-RefreshIcon.gif)aktualisieren.
    
[Nach oben](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="more-information"></a>Weitere Informationen
<a name="moreinfo"> </a>

Hier finden Sie weitere Informationen zu Inhalts suchen.
  
[Grenzwerte und Leistung](#limits-and-performance)
  
[Nicht indizierte Elemente](#unindexed-items) 
 
[Microsoft Teams und Office 365 Gruppen](#microsoft-teams-and-office-365-groups)
  
[OneDrive for Business](#onedrive-for-business)
  
[Suchabfragen](#search-queries)
  
[Durchsuchen inaktiver Postfächer](#searching-inactive-mailboxes)
  
[Sonstiges](#miscellaneous)
  
[Return to top](#before-you-begin)
  
### <a name="limits-and-performance"></a>Grenzwerte und Leistung
  
- Eine Beschreibung der Grenzwerte, die auf das Feature für die Inhaltssuche angewendet werden, finden Sie unter [Grenzwerte für die Suche im Security #a0 Compliance Center](limits-for-content-search.md).
    
- Microsoft sammelt Leistungsinformationen für Inhalts suchen, die von allen Office 365 Organisationen ausgeführt werden. Während sich die Komplexität der Suchabfrage auf die Suchzeiten auswirken kann, ist der größte Faktor, der sich auf die Dauer der Suche auswirkt, die Anzahl der durchsuchten Postfächer. Obwohl Microsoft keine Vereinbarung zum Service Level für Suchzeiten bereitstellt, werden in der folgenden Tabelle die durchschnittlichen Suchzeiten für eine Inhaltssuche basierend auf der Anzahl der in der Suche enthaltenen Postfächer aufgeführt.
    
|**Anzahl der Postfächer**|**Durchschnittliche Such Dauer**|
|:-----|:-----|
|100  <br/> |30 Sekunden  <br/> |
|1,000  <br/> |45 Sekunden  <br/> |
|10,000  <br/> |4 Minuten  <br/> |
|25.000  <br/> |10 Minuten  <br/> |
|50.000  <br/> |20 Minuten  <br/> |
|100,000  <br/> |25 Minuten  <br/> |
   
  
### <a name="unindexed-items"></a>Nicht indizierte Elemente
  
- Wie bereits erläutert, sind nicht indizierte Elemente in durchsuchten Inhaltsspeicherorten in den geschätzten Suchergebnissen enthalten. Wenn ein nicht indiziertes Element mit der Suchabfrage übereinstimmt (da andere Nachrichten-oder Dokumenteigenschaften die Suchkriterien erfüllen), wird es nicht in die geschätzte Anzahl nicht indexierter Elemente aufgenommen. Wenn ein nicht indiziertes Element durch die Suchkriterien ausgeschlossen wird, wird es auch nicht in die geschätzte Anzahl nicht indexierter Elemente eingeschlossen. Weitere Informationen finden Sie unter nicht [indizierte Elemente in der Inhaltssuche](https://go.microsoft.com/fwlink/p/?LinkId=780739).
    

  
### <a name="microsoft-teams-and-office-365-groups"></a>Microsoft Teams und Office 365 Gruppen
  
- Microsoft Teams sind auf Office 365 Gruppen aufgebaut. Daher ist die Suche sehr ähnlich. Beachten Sie bei der Suche nach Inhalten in Microsoft Teams und Office 365 Gruppen die folgenden Punkte.
    
  - Um nach Inhalten zu suchen, die sich in Microsoft Teams und Office 365 Gruppen befinden, müssen Sie das Postfach und die SharePoint-Website angeben, die einem Team oder einer Gruppe zugeordnet sind.
    
  - Führen Sie das Cmdlet **Get-Unifiedgroup** in Exchange Online aus, um Eigenschaften für ein Microsoft-Team oder eine Office 365 Gruppe anzuzeigen. Dies ist eine gute Möglichkeit, die URL für die Website abzurufen, die einem Team oder einer Gruppe zugeordnet ist. Mit dem folgenden Befehl werden beispielsweise ausgewählte Eigenschaften für eine Office 365 Gruppe mit dem Namen "Senior Leadership Team" angezeigt: 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > Damit Sie das Cmdlet **Get-Unifiedgroup** ausführen können, müssen Sie in Exchange Online die Rolle "nur-Ansicht-Empfänger" besitzen oder Mitglied einer Rollengruppe sein, der die Rolle "nur-Empfänger" zugewiesen ist. 
  
  - Wenn das Postfach eines Benutzers durchsucht wird, werden alle Microsoft Teams oder Office 365 Gruppen, in denen der Benutzer Mitglied ist, nicht durchsucht. Wenn Sie ein Microsoft-Team oder eine Office 365 Gruppe durchsuchen, wird auf ähnliche Weise nur das Gruppenpostfach und die von Ihnen angegebene Gruppen Website durchsucht. die Postfächer und OneDrive für Unternehmen Konten von Gruppenmitgliedern werden nur durchsucht, wenn Sie Sie explizit der Suche hinzugefügt haben.
    
  - Wenn Sie eine Liste der Mitglieder eines Microsoft-Teams oder einer Office 365 Gruppe erhalten möchten, können Sie die Eigenschaften auf der Seite " **Start \> Gruppen** " im Microsoft 365 Admin Center anzeigen. Alternativ können Sie den folgenden Befehl in Exchange Online PowerShell ausführen: 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > Damit Sie das Cmdlet **Get-UnifiedGroupLinks** ausführen können, müssen Sie in Exchange Online die Rolle "nur-Ansicht-Empfänger" besitzen oder Mitglied einer Rollengruppe sein, der die Rolle "nur-Ansicht-Empfänger" zugewiesen ist. 
  
  - Unterhaltungen, die Teil eines Microsoft Teams-Kanals sind, werden in dem Postfach gespeichert, das dem Microsoft-Team zugeordnet ist. Auf ähnliche Weise werden Dateien, die Teammitglieder in einem Kanal freigeben, auf der SharePoint-Website des Teams gespeichert. Daher müssen Sie das Microsoft Team-Postfach und die SharePoint-Website als Inhaltsspeicherort hinzufügen, um Unterhaltungen und Dateien in einem Kanal zu durchsuchen.
    
  - 
    
    Alternativ werden Unterhaltungen, die Teil der Chat Liste in Microsoft Teams sind, im Exchange Online Postfach der Benutzer gespeichert, die an dem Chat teilnehmen. Und Dateien, die ein Benutzer in Chat Unterhaltungen freigibt, werden im OneDrive für Unternehmen Konto des Benutzers gespeichert, der die Datei freigibt. Daher müssen Sie die einzelnen Benutzerpostfächer und OneDrive für Unternehmen Konten als inhaltsspeicherorte hinzufügen, um Unterhaltungen und Dateien in der Chat Liste zu durchsuchen.
    
    > [!NOTE]
    > Benutzer, die an Unterhaltungen teilnehmen, die Teil der Chat Liste in Microsoft Teams sind, müssen über ein Exchange Onlinees (Cloud-basiertes) Postfach verfügen, damit Sie Chat Unterhaltungen durchsuchen können. Das liegt daran, dass Unterhaltungen, die Teil der Chat Liste sind, in den cloudbasierten Postfächern der Chat Teilnehmer gespeichert werden. Wenn ein Chat Teilnehmer kein Exchange Online Postfach hat, können Sie keine Chat Unterhaltungen durchsuchen. Beispielsweise können Benutzer mit einem lokalen Postfach in einer Exchange-hybridbereitstellung an Unterhaltungen teilnehmen, die Teil der Chat Liste in Microsoft Teams sind. In diesem Fall können Inhalte aus diesen Unterhaltungen jedoch nicht durchsucht werden, da die Benutzer keine cloudbasierten Postfächer haben. 
  
  - Jeder Microsoft-Team-oder Team Kanal enthält ein wiki für die Notizen und die Zusammenarbeit. Der Inhalt des Wikis wird automatisch in einer Datei mit dem MHT-Format gespeichert. Diese Datei wird in der Microsoft Teams-wiki-Datendokument Bibliothek auf der SharePoint-Website des Teams gespeichert. Sie können das Inhaltssuche-Tool zum Durchsuchen des Wikis verwenden, indem Sie die SharePoint-Website des Teams als den zu durchsuchenden Inhaltsspeicherort angeben. 
    
    > [!NOTE]
    > Die Funktion zum Durchsuchen des Wikis nach einem Microsoft-Team oder-Kanal (wenn Sie die SharePoint-Website des Teams durchsuchen) wurde am 22. Juni 2017 veröffentlicht. Wiki-Seiten, die an diesem Datum oder später gespeichert oder aktualisiert wurden, stehen für die Durchsuchung zur Verfügung. Wiki-Seiten, die zuletzt gespeichert oder vor diesem Datum aktualisiert wurden, stehen nicht für die Suche zur Verfügung. 
  
### <a name="onedrive-for-business"></a>OneDrive for Business
  
- Informationen zum Sammeln einer Liste der URLs für die OneDrive für Unternehmen Websites in Ihrer Organisation finden Sie unter [Erstellen einer Liste aller OneDrive-Standorte in Ihrer Organisation](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Das Skript in diesem Artikel erstellt eine Textdatei, die eine Liste aller OneDrive für Unternehmen Websites enthält. Um dieses Skript auszuführen, müssen Sie die SharePoint Online-Verwaltungsshell installieren und verwenden. Stellen Sie sicher, dass Sie die URL für die mysite-Domäne Ihrer Organisation an jede OneDrive für Unternehmen Website anfügen, die Sie durchsuchen möchten. Dies ist die Domäne, die alle OneDrive für Unternehmen enthält. Beispiel: `https://contoso-my.sharepoint.com`. Hier ist ein Beispiel für eine URL für die OneDrive für Unternehmen Website eines Benutzers: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.
    

### <a name="search-queries"></a>Suchabfragen
  
- Beachten Sie beim Erstellen einer Suchabfrage die folgenden Aspekte, wenn Sie die Stichwortliste verwenden.
    
  - Sie müssen das Kontrollkästchen **Keyword-Liste anzeigen** aktivieren und dann jedes Schlüsselwort in eine separate Zeile eingeben, um eine Suchabfrage zu erstellen, bei der die Schlüsselwörter (oder Keyword-Phrasen) in jeder Zeile durch den **or** -Operator miteinander verbunden sind. Wenn Sie einfach eine Liste mit Stichwörtern in das Feld Stichwort einfügen oder die **Eingabe** Taste drücken, nachdem Sie ein Stichwort eingegeben haben, wird Sie nicht durch den Operator **oder** verbunden. Im folgenden finden Sie ein falsches und korrektes Beispiel für das Hinzufügen einer Liste von Schlüsselwörtern. 
    
    **Falsche**
    
    ![Falsche Vorgehensweise zum Formatieren einer Keyword-Liste (durch Einfügen der Liste in das Feld "Stichwort")](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **Richtig**
    
    ![Die richtige Möglichkeit zum Formatieren einer Keyword-Liste (durch Markieren von CheckBox und Einfügen der Liste)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
  - Sie können auch eine Liste von Schlüsselwörtern oder Keyword-Phrasen in einer Excel-Datei oder einer nur-Text-Datei vorbereiten und dann die Liste in die Stichwortliste kopieren und einfügen. Dazu müssen Sie das Kontrollkästchen **Schlüsselwortliste anzeigen** aktivieren. Klicken Sie dann in der Liste Stichwort auf die erste Zeile, und fügen Sie Ihre Liste ein. Jede Zeile aus der Excel-oder Textdatei wird in in die separate Zeile in der Schlüsselwortliste eingefügt. 
    
  - Nachdem Sie eine Abfrage mithilfe der Stichwortliste erstellt haben, sollten Sie die Suchabfrage Syntax (im Detailbereich der ausgewählten Suche) überprüfen, um die beabsichtigte Suchabfrage zu machen. In der Suchabfrage, die unter **Query** im Detailbereich angezeigt wird, werden die Schlüsselwörter durch den Text **(c:s)** getrennt. Dies deutet darauf hin, dass die Schlüsselwörter durch den **or** -Operator verbunden sind. Wenn Ihre Suchabfrage Bedingungen enthält, werden die Schlüsselwörter und Bedingungen entsprechend durch den Text **(c:c)** getrennt. Dies deutet darauf hin, dass die Schlüsselwörter durch den **and-** Operator mit den Bedingungen verbunden sind. Im folgenden finden Sie ein Beispiel für die Suchabfrage (die im Detailbereich angezeigt wird), die bei Verwendung der Stichwortliste und einer Bedingung resultiert. 
    
    ![Beispiel für die Abfrage, die erstellt wird, wenn die Stichwortliste verwendet wird und eine Bedingung](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
  - Wenn Sie über eine Suchabfrage verfügen, die Stichwörter für nicht englische Zeichen (beispielsweise chinesische Zeichen) enthält, müssen Sie möglicherweise das Cmdlet " **ComplianceSearch** " verwenden, um die Language-Eigenschaft für die Inhaltssuche zu konfigurieren. Wenn Sie eine Inhaltssuche mithilfe der GUI im Security #a0 Compliance Center erstellen, ist die Standardsprache neutral. 
    
    Wie können Sie erkennen, ob Sie die Spracheinstellung für eine Inhaltssuche ändern müssen? Wenn Sie bestimmte inhaltsspeicherorte enthalten, die nicht englische Zeichen sind, die Sie suchen, aber die Suche keine Ergebnisse zurückgibt, ist die Spracheinstellung möglicherweise die Ursache.
    
    Um die Spracheinstellung für eine vorhandene Inhaltssuche zu ändern, führen Sie den folgenden Befehl in Security #a0 Compliance Center PowerShell aus:
    
  ```
  Set-ComplianceSearch <name of content search> -Language <culture code value>
  ```

    Um beispielsweise die Spracheinstellung in Chinesisch zu ändern, verwenden `zh-CN` Sie den Wert für Kulturcode. Nachdem Sie die Spracheinstellung geändert haben, müssen Sie die Suche erneut ausführen. Eine Liste der möglichen Kulturcode Werte finden Sie unter [CultureInfo-Klasse](https://go.microsoft.com/fwlink/p/?LinkID=184859). Für die Inhaltssuche wird empfohlen, dass Sie zweiteilige Kulturcodes für den Wert der Spracheinstellung verwenden. Beispiel: `ja-JP` und nicht `ja`.
    

### <a name="searching-inactive-mailboxes"></a>Durchsuchen inaktiver Postfächer
  
Wie bereits erwähnt, können Sie inaktive Postfächer in einer Inhaltssuche durchsuchen. Im folgenden finden Sie einige Punkte, die Sie bei der Suche inaktiver Postfächer beachten sollten.
  
- Wenn eine Inhaltssuche ein Benutzerpostfach enthält und dieses Postfach dann inaktiv gemacht wird, wird durch die Inhaltssuche weiterhin das inaktive Postfach durchsucht, wenn Sie die Suche erneut ausführen, nachdem Sie inaktiv geworden ist.
    
- In einigen Fällen verfügt ein Benutzer möglicherweise über ein aktives Postfach und ein inaktives Postfach mit der gleichen SMTP-Adresse. In diesem Fall wird nur das bestimmte Postfach durchsucht, das Sie als Speicherort für eine Inhaltssuche ausgewählt haben. Wenn Sie also das Postfach eines Benutzers zu einer Suche hinzufügen, können Sie nicht davon ausgehen, dass sowohl die aktiven als auch die inaktiven Postfächer durchsucht werden. nur das Postfach, das Sie explizit zur Suche hinzufügen, wird durchsucht.
    
- Es wird dringend empfohlen, ein aktives Postfach und ein inaktives Postfach mit derselben SMTP-Adresse zu vermeiden. Wenn Sie die SMTP-Adresse, die derzeit einem inaktiven Postfach zugewiesen ist, wieder verwenden müssen, wird empfohlen, das inaktive Postfach wiederherzustellen oder den Inhalt eines inaktiven Postfachs in einem aktiven Postfach (oder im Archiv eines aktiven Postfachs) wiederherzustellen, und löschen Sie dann die inaktives Postfach. Weitere Informationen finden Sie unter einem der folgenden Themen:
    
  - [Wiederherstellen eines inaktiven Postfachs in Office 365](recover-an-inactive-mailbox.md)
    
  - [Wiederherstellen eines inaktiven Postfachs in Office 365](restore-an-inactive-mailbox.md)
    
  - [Löschen eines inaktiven Postfachs in Office 365](delete-an-inactive-mailbox.md)
    
### <a name="miscellaneous"></a>Sonstiges
  
- Auf der Seite " **Inhaltssuche** " im Security #a0 Compliance Center erstellte Inhalts Suchvorgänge werden auf der Seite **in- &amp; situ-eDiscovery-Aufbewahrungs** Dienst im Exchange Admin Center nicht angezeigt. Dies liegt daran, dass die Architektur der Inhaltssuche und die im Security #a0 Compliance Center erstellten Suchobjekte völlig anders sind als das in-Place-eDiscovery-Feature in Exchange Online. 
    
    Aus demselben Grund werden auf der Seite " **Inhaltssuche** " erstellte Suchvorgänge auf der Seite " **Suchen** " eines eDiscovery-Falls im Security #a0 Compliance Center nicht angezeigt. 
    
- Was ist der Unterschied zwischen dem Neustarten einer Suche und dem Wiederholen einer Suche? Wenn Sie eine Suche neu starten, werden alle in der Suche angegebenen inhaltsspeicherorte in einer neuen Vorschau Suche erneut durchsucht. Wenn Sie jedoch eine Suche wiederholen, werden erneut die inhaltsspeicherorte durchsucht, bei denen bei der letzten Ausführung der Suche ein Fehler aufgetreten ist.
   

