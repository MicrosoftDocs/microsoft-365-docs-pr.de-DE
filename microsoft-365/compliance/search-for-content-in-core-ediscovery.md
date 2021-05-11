---
title: Suchen nach Inhalten in einem zentralen eDiscovery-Fall
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
description: Suchen Sie nach Inhalten, die für einen Core eDiscovery-Fall relevant sein können.
ms.openlocfilehash: 8d2e2a20135312a8f111a071abbe77b03b8e8363
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311777"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a>Suchen nach Inhalten in einem Core eDiscovery-Fall

Nachdem ein Core eDiscovery-Fall erstellt wurde und Personen, die für den Fall von Interesse sind, in einem Haltebereich platziert wurden, können Sie eine oder mehrere Suchen nach für den Fall relevanten Inhalten erstellen und ausführen. Einem Core eDiscovery-Fall zugeordnete Suchen werden  nicht auf der Seite Inhaltssuche im compliance center Microsoft 365 aufgelistet. Diese Suchen werden auf  der Seite Suchen des Core eDiscover-Falls aufgeführt, dem die Suchen zugeordnet sind. Dies bedeutet auch, dass auf Die einem Fall zugeordneten Suchen nur von Fallmitgliedern zugegriffen werden kann.

So erstellen Sie eine Core eDiscovery-Suche:
  
1. Wechseln Sie zu, und melden Sie sich mit den Anmeldeinformationen für ein Benutzerkonto an, dem die entsprechenden eDiscovery-Berechtigungen zugewiesen wurden und Mitglied <https://compliance.microsoft.com> des Falls ist.

2. Klicken Sie im linken Navigationsbereich Microsoft 365 Compliance Center auf Alle **anzeigen,** und klicken Sie dann auf **eDiscovery > Core**.

3. Wählen Sie auf der Seite Core **eDiscovery** den Fall aus, für den Sie eine zugeordnete Suche erstellen möchten, und klicken Sie dann auf **Fall öffnen**.

4. Klicken Sie **auf der** Startseite für den Fall auf **die** Registerkarte Suchen, und klicken Sie dann auf **Neue Suche**.

   ![Klicken Sie auf Neue Suche, um eine Core eDiscovery-Suchsuche zu erstellen.](../media/CoreeDiscoverySearch1.png)

   > [!NOTE]
   > Mit **der Listenoption** Nach ID suchen können Sie nach bestimmten E-Mail-Nachrichten und anderen Postfachelementen mithilfe einer Liste von Exchange suchen. Um eine ID-Listensuche zu erstellen, übermitteln Sie eine durch Kommata getrennte Wertedatei (CSV), in der Sie die spezifischen Postfachelemente angeben, nach denen Sie suchen. Eine Anleitung finden Sie unter [CSV-Datei für eine ID-Listensuche vorbereiten](csv-file-for-an-id-list-content-search.md).

5. Geben Sie **im Assistenten** Für neue Suchfunktion einen Namen für die Suche und eine optionale Beschreibung ein, mit der die Suche identifiziert werden kann. Der Name der Suche muss in Ihrer Organisation eindeutig sein.

6. Wählen Sie **auf** der Seite Speicherorte die Inhaltsorte aus, die Sie durchsuchen möchten. Sie können Postfächer, Websites und öffentliche Ordner durchsuchen.

    ![Wählen Sie Inhaltsspeicherorte aus, die im Haltebereich platziert werden sollen.](../media/ContentSearchLocations.png)
  
   1. **Exchange Postfächer:** Legen Sie den Umschalter auf **Ein** fest, und klicken Sie dann auf **Benutzer, Gruppen** oder Teams auswählen, um die Postfächer anzugeben, die in der Warteschleife gespeichert werden. Verwenden Sie das Suchfeld, um Benutzerpostfächer und Verteilergruppen zu finden (um die Postfächer von Gruppenmitgliedern in den Halteraum zu setzen). Sie können auch das Postfach durchsuchen, das einem Microsoft Team zugeordnet ist (nach Kanalnachrichten), Office 365 Gruppe und Yammer Gruppe. Weitere Informationen zu den in Postfächern gespeicherten Anwendungsdaten finden Sie unter Inhalt, der in Postfächern für [eDiscovery gespeichert ist.](what-is-stored-in-exo-mailbox.md)

   2. **SharePoint** Websites: Legen Sie die Umschaltflächen auf  **Ein** fest, und klicken Sie dann auf Websites auswählen, um SharePoint websites und OneDrive konten anzugeben, die in der Warteschleife platzieren werden. Geben Sie die URL für jede Website ein, die Sie in der Warteschleife platzieren möchten. Sie können auch die URL für die SharePoint für ein Microsoft Team, eine Office 365 oder eine Yammer hinzufügen.
  
   3. **Exchange öffentlichen Ordner**: Legen Sie die Umschalte auf **Ein** fest, um alle öffentlichen Ordner in Exchange Online organisation zu speichern. Sie können keine bestimmten öffentlichen Ordner auswählen, die in der Warteschleife gespeichert werden. Lassen Sie den Umschalter deaktiviert, wenn Sie öffentliche Ordner nicht in den Halteraum setzen möchten.
  
   4. Aktivieren Sie dieses Kontrollkästchen, um nach inhalten Teams lokalen Benutzern zu suchen. Wenn Sie beispielsweise alle Exchange-Postfächer in der Organisation durchsuchen und dieses Kontrollkästchen aktiviert ist, wird der cloudbasierte Speicher zum Speichern von Teams-Chatdaten für lokale Benutzer in den Bereich der Suche einbezogen. Weitere Informationen finden Sie unter [Nach Teams-Chatdaten für lokale Benutzer suchen](search-cloud-based-mailboxes-for-on-premises-users.md).

7. Geben Sie **auf der Seite Suchbedingungen** definieren eine Schlüsselwortabfrage ein, und fügen Sie der Suchabfrage bei Bedarf Bedingungen hinzu.

   ![Konfigurieren der Suchabfrage](../media/ContentSearchQuery.png)

   1. Geben Sie Schlüsselwörter, Nachrichteneigenschaften wie gesendete und empfangene Datumsangaben oder Dokumenteigenschaften wie Dateinamen oder das Datum an, an dem ein Dokument zuletzt geändert wurde. Sie können auch komplexere Abfragen mit booleschen Operatoren wie **AND**, **OR**, **NOT** und **NEAR** verwenden. Wenn Sie das Schlüsselwortfeld leer lassen, werden alle Inhalte in den angegebenen Inhaltsspeicherorten in die Suchergebnisse eingeschlossen. Weitere Informationen finden Sie unter [Schlüsselwortabfragen und Suchbedingungen für eDiscovery](keyword-queries-and-search-conditions.md).

   2. Alternativ können Sie auf das Kontrollkästchen **Schlüsselwortliste anzeigen** klicken, und dann in jede Zeile ein Schlüsselwort eingeben. Wenn Sie dies tun, werden die Schlüsselwörter in den einzelnen Zeilen der erstellten Suchabfrage mit einem logischen (**c:s**)-Operator verknüpft. Dessen Funktionsweise ist mit jener des **OR**-Operators vergleichbar.

      Gründe für die Verwendung der Schlüsselwortliste Sie können Statistiken abrufen, die zeigen, wie viele Elemente den einzelnen Schlüsselwörtern entsprechen. Dadurch können Sie schnell erkennen, welche Schlüsselwörter am effektivsten (und am wenigsten effektiv) sind. Sie können auch einen (in Klammern eingeschlossenen) Schlüsselwortausdruck in einer Zeile verwenden. Weitere Informationen zur Stichwortliste und suchstatistik finden Sie unter [Get keyword statistics for searches](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).

      > [!NOTE]
      > Um Probleme zu reduzieren, die durch große Stichwortlisten verursacht werden, sind Sie auf maximal 20 Zeilen in der Stichwortliste beschränkt.

   3. Sie können Suchbedingungen hinzufügen, um eine Suche zu eindrücken und einen verfeinerten Satz von Ergebnissen zurücksennen. Jede Bedingung fügt eine Klausel zur Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird. Eine Bedingung ist logisch mit der Schlüsselwortabfrage (im Feld „Schlüsselwort“ angegeben) durch einen logischen (**c:s**)-Operator verknüpft. Dessen Funktionsweise ist mit jener des **OR**-Operators vergleichbar. Dies bedeutet, dass Elemente sowohl die Schlüsselwortabfrage als auch eine oder mehrere Bedingungen erfüllen muss, damit sie in die Suchergebnisse aufgenommen werden. Auf diese Weise können die Suchergebnisse mithilfe von Bedingungen weiter eingegrenzt werden. Eine Liste und Beschreibung der Bedingungen, die Sie in einer Suchabfrage verwenden können, finden Sie unter [Suchbedingungen](keyword-queries-and-search-conditions.md#search-conditions).

8. Überprüfen Sie die Sucheinstellungen (und bearbeiten Sie bei Bedarf), und übermitteln Sie die Suche, um sie zu starten.

Wenn die Suche abgeschlossen ist, können Sie eine Vorschau der Suchergebnisse anzeigen. Klicken Sie bei Bedarf **auf der** Seite **Suchen** auf Aktualisieren, um die von Ihnen erstellte Suche anzeigen zu können.

## <a name="more-information-about-searching-content-locations"></a>Weitere Informationen zum Durchsuchen von Inhaltsstandorten

- Wenn Sie auf **Benutzer, Gruppen** oder Teams auswählen klicken, um zu suchende Postfächer anzugeben, ist die angezeigte Postfachauswahl leer. Dies ist beabsichtigt, um die Leistung zu verbessern. Klicken Sie zum Hinzufügen von Empfängern zu dieser Liste auf **Benutzer,** Gruppen oder Teams auswählen, geben Sie einen Namen (mindestens drei Zeichen) in das Suchfeld ein, aktivieren Sie das Kontrollkästchen neben dem Namen, und klicken Sie dann auf **Auswählen**.

- Sie können inaktive Postfächer, Microsoft Teams, Yammer Gruppen, Office 365 Gruppen und Verteilergruppen zur Liste der zu durchsuchende Postfächer hinzufügen. Dynamische Verteilergruppen werden nicht unterstützt. Wenn Sie Microsoft Teams, Yammer gruppen oder Office 365 hinzufügen, wird das Gruppen- oder Teampostfach durchsucht. Die Postfächer der Gruppenmitglieder werden nicht durchsucht.

- Um der Suche Websites hinzuzufügen, aktivieren Sie die Umschaltflächen, und klicken Sie dann **auf Websites auswählen.** Geben Sie die URL für jede Website ein, die Sie durchsuchen möchten. Sie können auch die URL für die SharePoint für ein Microsoft Team, eine Yammer oder eine Office 365 hinzufügen.
