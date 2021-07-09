---
title: Massenbearbeitung von Inhaltssuchen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/29/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 39e4654a-9588-41f6-892b-c33ab57bfbe2
ms.custom:
- seo-marvel-apr2020
description: Verwenden Sie den Massensuch-Editor im Security and Compliance Center, um die Abfrage- und Inhaltsspeicherorte für eine oder mehrere Inhaltssuchen schnell zu ändern.
ms.openlocfilehash: be7e37ec22966e16dfa3c6d1f37a34e6441e632a
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341032"
---
# <a name="bulk-edit-content-searches"></a>Massenbearbeitung von Inhaltssuchen

Sie können den Massensuch-Editor im Tool für die Inhaltssuche verwenden, um mehrere Suchvorgänge gleichzeitig zu bearbeiten. Mit diesem Tool können Sie die Abfrage- und Inhaltsspeicherorte für eine oder mehrere Suchvorgänge schnell ändern. Anschließend können Sie die Suchvorgänge erneut ausführen und neue geschätzte Suchergebnisse für die überarbeiteten Suchvorgänge abrufen. Mit dem Editor können Sie auch Abfragen und Inhaltsspeicherorte aus einer Microsoft Excel- oder Textdatei kopieren und einfügen. Dies bedeutet, dass Sie das Suchstatistiktool verwenden können, um die Statistiken einer oder mehrerer Suchvorgänge anzuzeigen, die Statistiken in eine CSV-Datei zu exportieren, in der Sie die Abfragen und Inhaltsspeicherorte in Excel bearbeiten können. Anschließend verwenden Sie den Massensuch-Editor, um den Suchvorgängen die überarbeiteten Abfragen und Inhaltsspeicherorte hinzuzufügen. Nachdem Sie eine oder mehrere Suchvorgänge überprüft haben, können Sie sie neu starten und neue geschätzte Suchergebnisse erhalten.

Weitere Informationen zur Verwendung des Tools "Suchstatistik" finden Sie unter Anzeigen von [Schlüsselwortstatistiken für Inhaltssuchergebnisse.](view-keyword-statistics-for-content-search.md)

## <a name="use-the-bulk-search-editor-to-change-queries"></a>Verwenden des Massensuch-Editors zum Ändern von Abfragen

1. Wechseln Sie zu <https://compliance.microsoft.com> , und wählen Sie dann **Inhaltssuche** aus.

2. Wählen Sie in der Liste der Suchvorgänge eine oder mehrere Suchvorgänge aus, und wählen Sie dann die Schaltfläche **"Massensuch-Editor** ![ für Massensuche" ](../media/1ddb3d18-2f00-4a7b-98a6-817ca5ec7014.png) aus.

    ![Wählen Sie eine oder mehrere Suchvorgänge aus, und wählen Sie dann den Editor für die Massensuche aus.](../media/600c9716-89a2-4451-b111-fa7cfaad2006.png)

    Die folgenden Informationen werden auf der Seite **"Abfragen"** des Massensuch-Editors angezeigt.

    ![Auf der Editorseite für die Massensuche werden die Abfragen für die ausgewählten Suchvorgänge angezeigt.](../media/189659af-cc78-4479-b0bc-a93decad2f6c.png)

    a. In der **Suchspalte** wird der Name der Inhaltssuche angezeigt. Wie bereits erwähnt, können Sie die Abfrage für mehrere Suchvorgänge bearbeiten.

    b. In der Spalte **Abfrage** wird die Abfrage für die inhaltssuche angezeigt, die in der Spalte **Suche** aufgeführt ist. Wenn die Abfrage mithilfe des Schlüsselwortlistenfeatures erstellt wurde, werden die Schlüsselwörter durch den Text **`(c:s)`** getrennt. Dies gibt an, dass die Schlüsselwörter durch den **OR-Operator** verbunden sind. Wenn die Abfrage Außerdem Bedingungen enthält, werden die Schlüsselwörter und die Bedingungen durch den Text **`(c:c)`** getrennt. Dies gibt an, dass die Schlüsselwörter (oder Schlüsselwortphasen) mit den Bedingungen durch den **AND-Operator** verbunden sind. Beispiel: Im vorherigen Screenshot für die Suche ContosoSearch1 würde die KQL-Abfrage, die äquivalent ist, `customer (c:s) pricing(c:c)(date=2000-01-01..2016-09-30)`  `(customer OR pricing) AND (date=2002-01-01..2016-09-30)` sein.

3. Um eine Abfrage zu bearbeiten, wählen Sie in der Zelle der Abfrage, die Sie ändern möchten, eine der folgenden Aktionen aus. Die Zelle wird durch ein blaues Feld umrandet, wenn Sie sie auswählen.

   - Geben Sie die neue Abfrage in die Zelle ein. Sie können einen Teil der Abfrage nicht bearbeiten. Sie müssen die gesamte Abfrage eingeben.

      Oder

   - Fügen Sie eine neue Abfrage in die Zelle ein. Dies setzt voraus, dass Sie den Abfragetext aus einer Datei kopiert haben, z. B. einer Textdatei oder einer Excel Datei.

4. Nachdem Sie eine oder mehrere Abfragen auf der Seite **"Abfragen"** bearbeitet haben, wählen Sie **"Speichern"** aus.

    Die überarbeitete Abfrage wird in der Spalte **Abfrage** für die ausgewählte Suche angezeigt.

5. Wählen Sie **"Schließen"** aus, um den Massensuch-Editor zu schließen.

6. Wählen Sie auf der Seite **"Inhaltssuche"** die von Ihnen bearbeitete Suche aus, und wählen Sie "Suche **starten"** aus, um die Suche mithilfe der überarbeiteten Abfrage neu zu starten.

Hier sind einige Tipps zum Bearbeiten von Abfragen mit dem Massensuch-Editor:

- Kopieren Sie die vorhandene Abfrage (mit **STRG C)** in eine Textdatei. Bearbeiten Sie die Abfrage in der Textdatei, kopieren Sie die überarbeitete Abfrage, und fügen Sie sie (mit **STRG V)** zurück in die Zelle auf der Seite **"Abfragen"** ein.

- Sie können auch Abfragen aus anderen Anwendungen kopieren (z. B. Microsoft Word oder Microsoft Excel). Möglicherweise fügen Sie einer Abfrage jedoch versehentlich nicht unterstützte Zeichen mithilfe des Massensuch-Editors hinzu. Die beste Möglichkeit, nicht unterstützte Zeichen zu verhindern, besteht darin, einfach die Abfrage in eine Zelle auf der Seite **"Abfragen"** einzugeben. Sie können auch eine Abfrage aus Word oder Excel kopieren und dann in einen Nur-Text-Editor einfügen, z. B. Microsoft Editor. Speichern Sie dann die Textdatei, und wählen Sie **ANSI** in der Dropdownliste **Codierung** aus. Dadurch werden alle Formatierungen und nicht unterstützten Zeichen entfernt. Anschließend können Sie die Abfrage aus der Textdatei kopieren und auf die Seite **Abfragen** einfügen.

## <a name="use-the-bulk-search-editor-to-change-content-locations"></a>Verwenden des Massensuch-Editors zum Ändern von Inhaltsspeicherorten

1. Wählen Sie im Editor für die Massensuche für eine oder mehrere ausgewählte Suchvorgänge die Option **"Massenspeicherort-Editor aktivieren"** aus, und wählen Sie dann den Link **"Speicherorte"** aus, der auf der Seite angezeigt wird.

    Die folgenden Informationen werden auf der Seite **"Speicherorte"** des Massensuch-Editors angezeigt.

    ![Wählen Sie "Massenspeicherort-Editor aktivieren" und dann "Speicherorte" aus, um Inhaltsspeicherorte hinzuzufügen oder zu entfernen.](../media/a5a468ce-bd63-4c53-bc37-ff64cf769e59.png)

    a. **Zu durchsuchende Postfächer** In diesem Abschnitt werden eine Spalte für jede ausgewählte Inhaltssuche und eine Zeile für jedes Postfach angezeigt, das in der Suche enthalten ist. Ein Häkchen gibt an, dass das Postfach in der Suche enthalten ist. Sie können einer Suche Postfächer hinzufügen, indem Sie die E-Mail-Adresse des Postfachs in einer leeren Zeile eingeben und dann das Kontrollkästchen für die Inhaltssuche aktivieren, der Sie es hinzufügen möchten. Sie können auch ein Postfach aus einer Suche entfernen, indem Sie das Kontrollkästchen deaktivieren.

    b. **SharePoint zu durchsuchende Websites** In diesem Abschnitt wird eine Zeile für jede SharePoint und OneDrive Website angezeigt, die in jeder ausgewählten Inhaltssuche enthalten ist. Ein Häkchen gibt an, dass die Website in der Suche enthalten ist. Sie können einer Suche Websites hinzufügen, indem Sie die URL für die Website in einer leeren Zeile eingeben und dann das Kontrollkästchen für die Inhaltssuche aktivieren, der Sie sie hinzufügen möchten. Sie können auch eine Website aus einer Suche entfernen, indem Sie das Kontrollkästchen deaktivieren.

    c. **Andere Suchoptionen** In diesem Abschnitt wird angegeben, ob nicht indizierte Elemente und öffentliche Ordner in die Suche einbezogen werden. Um sie einzuschließen, stellen Sie sicher, dass das Kontrollkästchen aktiviert ist. Deaktivieren Sie das Kontrollkästchen, um sie zu entfernen.

2. Nachdem Sie einen oder mehrere Abschnitte auf der Seite **"Speicherorte"** bearbeitet haben, wählen Sie **"Speichern"** aus.

    Die überarbeiteten Inhaltsspeicherorte werden im entsprechenden Abschnitt für die ausgewählten Suchvorgänge angezeigt.

3. Wählen Sie **"Schließen"** aus, um den Massensuch-Editor zu schließen.

4. Wählen Sie auf der Seite **"Inhaltssuche"** die Suche aus, die Sie bearbeitet haben, und wählen Sie "Suche **starten"** aus, um die Suche mit den überarbeiteten Inhaltsspeicherorten neu zu starten.

Hier sind einige Tipps zum Bearbeiten von Inhaltsspeicherorten mithilfe des Massensuch-Editors:

- Sie können Inhaltssuchen bearbeiten, um alle Postfächer oder Websites in der Organisation zu durchsuchen, indem Sie **"Alle"** in einer leeren Zeile in den **Postfächern** eingeben, um den Abschnitt zu durchsuchen, oder **Websites SharePoint, um** den Abschnitt zu durchsuchen, und dann das Kontrollkästchen aktivieren.

- Sie können einer oder mehreren Suchvorgängen mehrere Inhaltsspeicherorte hinzufügen, indem Sie mehrere Zeilen aus einer Textdatei oder einer Excel datei kopieren und dann in einen Abschnitt auf der Seite **"Speicherorte"** einfügen. Nachdem Sie neue Speicherorte hinzugefügt haben, müssen Sie das Kontrollkästchen für jede Suche aktivieren, zu der Sie den Speicherort hinzufügen möchten.

    > [!TIP]
    > Um eine Liste der E-Mail-Adressen für alle Benutzer in Ihrer Organisation zu generieren, führen Sie den PowerShell-Befehl in Schritt 2 in [Schritt 2: Generieren einer Liste von Benutzern](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step-2-generate-a-list-of-users)aus. Oder führen Sie die Schritte unter [Abrufen einer Liste aller Benutzer-OneDrive-URLs in Ihrer Organisation](/onedrive/list-onedrive-urls) aus, um eine Liste aller OneDrive for Business Websites in Ihrer Organisation zu generieren. Beachten Sie, dass Sie die URL für die MySite-Domäne Ihrer Organisation anhängen müssen (z. https://contoso-my.sharepoint.com) B. an die OneDrive for Business Websites, die vom Skript erstellt werden. Nachdem Sie über eine Liste von E-Mail-Adressen oder OneDrive for Business Websites verfügen, können Sie sie kopieren und auf die Seite **"Speicherorte"** im Massensuch-Editor einfügen.

- Nachdem Sie **"Speichern"** ausgewählt haben, um Änderungen im Massensuch-Editor zu speichern, wird die E-Mail-Adresse für Postfächer, die Sie einer Suche hinzugefügt haben, überprüft. Wenn die E-Mail-Adresse nicht vorhanden ist, wird eine Fehlermeldung angezeigt, die besagt, dass das Postfach nicht gefunden werden kann. URLs für Websites werden nicht überprüft.
