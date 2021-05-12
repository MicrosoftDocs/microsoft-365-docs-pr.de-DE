---
title: Erstellen und Ausführen einer Inhaltssuche im Microsoft 365 Compliance Center
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Verwenden Sie das eDiscovery-Tool für Inhaltssuche im Compliance Center, um nach Inhalten in verschiedenen Microsoft 365-Diensten zu suchen.
ms.openlocfilehash: a058c07d080962723e9f6bc7a150cbfb5074e7db
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311667"
---
# <a name="create-a-content-search"></a>Erstellen einer Inhaltssuche

Sie können das Tool Inhaltssuche eDiscovery im Microsoft 365 Compliance Center verwenden, um nach Inhalten wie E-Mails, Dokumenten und Instant-Messaging-Konversationen in Ihrer Organisation zu suchen. Verwenden Sie dieses Tool, um in den folgenden Microsoft 365-Datenquellen nach Inhalten zu suchen:
  
- Exchange Online-Postfächer

- SharePoint Online-Websites und OneDrive for Business-Konten

- Microsoft Teams

- Microsoft 365-Gruppen

- Yammer-Gruppen

Nachdem Sie eine Suche durchgeführt haben, werden die Anzahl der Inhaltsspeicherorte und eine geschätzte Anzahl von Suchergebnissen auf der Flyout-Seite angezeigt. Sie können schnell Statistiken anzeigen, beispielsweise zu den inhaltsspeicherorten mit den meisten Elementen, die der Suchabfrage entsprechen. Nach dem Ausführen einer Suche können Sie eine Vorschau der Ergebnisse anzeigen oder Sie auf einen lokalen Computer exportieren.

## <a name="create-and-run-a-search"></a>Eine Suche erstellen und ausführen

Um auf die Seite **Inhaltssuche** im Microsoft 365 Compliance Center zuzugreifen, (um Inhaltssuchen auszuführen und die Ergebnisse in der Vorschau anzuzeigen und zu exportieren), müssen Administratoren, Compliance Officer oder eDiscovery-Manager Mitglied der Rollengruppe "eDiscovery-Manager" im Security & Compliance Center sein. Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).
  
1. Wechseln Sie zu <https://compliance.microsoft.com> und melden Sie sich mit den Anmeldeinformationen eines Kontos an, dem die entsprechenden Berechtigungen zugewiesen wurden.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Centers auf **Alle anzeigen** und dann auf **Inhaltssuche**.

3. Klicken Sie auf der Seite **Inhaltssuche** auf **Neue Suche**.

   > [!NOTE]
   > Die Option **Nach ID-Liste suchen:** erlaubt Ihnen bestimmte E-Mails und andere Elemente in Postfächern anhand einer Liste von Exchange-IDs durchzusuchen. Um eine ID-Listensuche zu erstellen, übermitteln Sie eine durch Kommata getrennte Wertedatei (CSV), in der Sie die spezifischen Postfachelemente angeben, nach denen Sie suchen. Eine Anleitung finden Sie unter [CSV-Datei für eine ID-Listensuche vorbereiten](csv-file-for-an-id-list-content-search.md).

4. Geben Sie einen Namen für diese Suche ein. Das ist eine optionale Beschreibung, durch die sich die Suche leichter identifizieren lässt. Der Name der Suche darf in Ihrer Organisation nur einmalig vorkommen.

5. Wählen Sie auf der Seite **Speicherorte** die Inhaltsspeicherorte aus, die Sie durchsuchen möchten. Sie können Postfächer, Websites und öffentliche Ordner durchsuchen.

    ![Wählen Sie Inhaltsspeicherorte aus, die im Haltebereich platziert werden sollen.](../media/ContentSearchLocations.png)
  
   1. **Exchange-Postfächer**: Setzen Sie den Schalter auf **Ein** und klicken Sie dann auf **Benutzer, Gruppen oder Teams auswählen**, um die Postfächer anzugeben, die im Haltebereich platziert werden sollen. Verwenden Sie das Suchfeld, um Benutzerpostfächer und Verteilergruppen zu finden, (um die Postfächer von Gruppenmitgliedern aufzubewahren), die in den Haltebereich gesetzt werden sollen. Sie können auch Postfächer durchsuchen, die mit einem Microsoft Team (für Kanalnachrichten), einer Office 365-Gruppe und einer Yammer-Gruppe verbunden sind. Weitere Informationen zu den in Postfächern gespeicherten Anwendungsdaten finden Sie unter [Für eDiscovery in Postfächern gespeicherte Inhalte](what-is-stored-in-exo-mailbox.md).

   2. **SharePoint-Websites**: Setzen Sie den Schalter auf **Ein** und klicken Sie dann auf **Websites wählen** aus, um SharePoint-Websites und OneDrive-Konten anzugeben, die im Haltebereich platziert werden sollen. Geben Sie die URL für jede Website ein, die Sie im Haltebereich platzieren möchten. Sie können auch die URL für die SharePoint-Website eines Microsoft-Teams, einer Office 365-Gruppe oder einer Yammer-Gruppe hinzufügen.
  
   3. **Öffentliche Exchange-Ordner**: Setzen Sie den Schalter auf **Ein**, um alle öffentlichen Ordner in Ihrer Exchange Online-Organisation in den Haltebereich zu versetzen. Sie können keine bestimmten öffentlichen Ordner auswählen, die im Haltebereich platziert werden sollen. Lassen Sie den Umschalter deaktiviert, wenn Sie öffentliche Ordner nicht in den Haltebereich platzieren möchten.
  
   4. Lassen Sie dieses Kontrollkästchen aktiviert, um nach Teams-Inhalten für lokale Benutzer zu suchen. Wenn Sie z. B. alle Exchange-Postfächer in der Organisation durchsuchen und dieses Kontrollkästchen aktiviert ist, wird der cloudbasierte Speicher, der zum Speichern von Teams-Chatdaten für lokale Benutzer verwendet wird, in den Umfang der Suche einbezogen. Weitere Informationen finden Sie unter [Nach Teams-Chatdaten für lokale Benutzer suchen](search-cloud-based-mailboxes-for-on-premises-users.md).

6. Geben Sie auf der Seite **Suchbedingungen definieren** eine Schlüsselwortabfrage ein und fügen Sie der Suchabfrage bei Bedarf Kriterien hinzu.

   ![Konfigurieren der Suchabfrage](../media/ContentSearchQuery.png)

   1. Schlüsselwörter, Nachrichteneigenschaften wie das Sende- und Empfangsdatum oder Dokumenteigenschaften wie Dateinamen oder das Datum angeben, an dem ein Dokument zuletzt geändert wurde. Sie können auch komplexere Abfragen mit booleschen Operatoren wie **AND**, **OR**, **NOT** und **NEAR** verwenden. Wenn Sie das Schlüsselwortfeld leer lassen, werden alle Inhalte in den angegebenen Inhaltsspeicherorten in die Suchergebnisse eingeschlossen. Weitere Informationen finden Sie unter [Stichwortabfragen und Suchbedingungen für eDiscovery](keyword-queries-and-search-conditions.md).

   2. Alternativ können Sie auf das Kontrollkästchen **Schlüsselwortliste anzeigen** klicken, und dann in jede Zeile ein Schlüsselwort eingeben. Wenn Sie dies tun, werden die Schlüsselwörter in den einzelnen Zeilen der erstellten Suchabfrage mit einem logischen (**c:s**)-Operator verknüpft. Dessen Funktionsweise ist mit jener des **OR**-Operators vergleichbar.

      Gründe für die Verwendung der Schlüsselwortliste Sie können Statistiken abrufen, die zeigen, wie viele Elemente den einzelnen Schlüsselwörtern entsprechen. Dadurch können Sie schnell erkennen, welche Schlüsselwörter am effektivsten (und am wenigsten effektiv) sind. Sie können auch einen (in Klammern eingeschlossenen) Schlüsselwortausdruck in einer Zeile verwenden. Weitere Informationen zur Schlüsselwortliste sowie zu Suchstatistiken finden Sie unter [Schlüsselwortstatistik für Suchen abrufen](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).

      > [!NOTE]
      > Um Probleme durch umfangreiche Schlüsselwortlisten zu verringern, ist die Schlüsselwortliste auf 20 Zeilen beschränkt.

   3. Sie können Suchbedingungen hinzufügen, um die Suche einzuschränken und eine verfeinerte Suchergebnisliste zu erhalten. Jede Bedingung fügt eine Klausel zur Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird. Eine Bedingung ist logisch mit der Schlüsselwortabfrage (im Feld „Schlüsselwort“ angegeben) durch einen logischen (**c:s**)-Operator verknüpft. Dessen Funktionsweise ist mit jener des **OR**-Operators vergleichbar. Dies bedeutet, dass Elemente sowohl die Schlüsselwortabfrage als auch eine oder mehrere Bedingungen erfüllen muss, damit sie in die Suchergebnisse aufgenommen werden. Auf diese Weise können die Suchergebnisse mithilfe von Bedingungen weiter eingegrenzt werden. Eine Liste und Beschreibung der Bedingungen, die Sie in einer Suchabfrage verwenden können, finden Sie unter [Suchbedingungen](keyword-queries-and-search-conditions.md#search-conditions).

7. Überprüfen Sie die Sucheinstellungen (und bearbeiten Sie sie bei Bedarf) und übermitteln Sie dann die Suche, um sie zu starten.
  
Um erneut auf diese Inhaltssuche oder auf andere Inhaltssuchen, die auf der Seite **Inhaltssuche** aufgelistet sind, zuzugreifen, wählen Sie die gewünschte Suche aus, und klicken Sie dann auf **Öffnen**.
  
## <a name="next-steps"></a>Nächste Schritte

Es folgt eine Liste der nächsten Schritte, die nach dem Erstellen und Ausführen einer Inhaltssuche ausgeführt werden müssen.

- [Anzeigen von Suchergebnissen in der Vorschau](preview-ediscovery-search-results.md)

- [Anzeigen von Statistiken für Suchergebnisse](view-keyword-statistics-for-content-search.md)

- [Exportieren der Suchergebnisse](export-search-results.md)

- [Exportieren eines Suchberichts](export-a-content-search-report.md)
