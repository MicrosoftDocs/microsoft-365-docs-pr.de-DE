---
title: Überprüfen von Unterhaltungen in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Erfahren Sie mehr über die Unterhaltungswiederherstellungsfunktion in Advanced eDiscovery (als Unterhaltungsthreading bezeichnet), um Chatunterhaltungen in Microsoft Teams und Yammer Gruppen zu rekonstruieren, zu überprüfen und zu exportieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9848280a7d6dbcbd6128fff06f150c8458f09701
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227187"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a>Unterhaltungsthreading in Advanced eDiscovery

Chat ist eine bequeme Möglichkeit, Fragen zu stellen, Ideen zu teilen oder schnell über große Zielgruppen hinweg zu kommunizieren. Da Chatplattformen wie Microsoft Teams und Yammer-Gruppen zum Kern der Zusammenarbeit im Unternehmen werden, müssen Organisationen bewerten, wie ihr eDiscovery-Workflow diese neuen Formen der Kommunikation und Zusammenarbeit adressiert.

Die Unterhaltungswiederherstellungsfunktion in Advanced eDiscovery soll Ihnen helfen, kontextbezogene Inhalte zu identifizieren und unterschiedliche Unterhaltungsansichten zu erzeugen. Mit dieser Funktion können Sie vollständige Chatunterhaltungen (auch *als Threadunterhaltungen* bezeichnet) effizient und schnell überprüfen, die auf Plattformen wie Microsoft Teams generiert werden.

Mit der Unterhaltungswiederherstellung können Sie integrierte Funktionen verwenden, um Threadunterhaltungen zu rekonstruieren, zu überprüfen und zu exportieren. Verwenden Sie Advanced eDiscovery Unterhaltungswiederherstellung für Folgendes:

- Beibehalten eindeutiger Metadaten auf Nachrichtenebene für alle Nachrichten innerhalb einer Unterhaltung.

- Sammeln Sie Kontextnachrichten in Ihren Suchergebnissen.

- Überprüfen, Kommentieren und Bearbeiten von Threadunterhaltungen.

- Exportieren einzelner Nachrichten oder Threadunterhaltungen

## <a name="terminology"></a>Terminologie

Hier sind einige Definitionen, die Ihnen bei den ersten Schritten mit der Wiederherstellung von Unterhaltungen helfen.

- **Nachrichten:** Stellt die kleinste Einheit einer Unterhaltung dar. Nachrichten können in Größe, Struktur und Metadaten variieren.

- **Unterhaltung:** Stellt eine Gruppierung einer oder mehrerer Nachrichten dar. Unterhaltungen können in verschiedenen Anwendungen auf unterschiedliche Weise dargestellt werden. In einigen Anwendungen gibt es eine explizite Aktion, die aus dem Antworten auf eine vorhandene Nachricht resultiert. Unterhaltungen werden explizit als Ergebnis dieser Benutzeraktion gebildet. Hier sehen Sie beispielsweise einen Screenshot einer Kanalunterhaltung in Microsoft Teams.

   ![Microsoft Teams Kanalunterhaltung](../media/threadedchat.png)

   In anderen Apps (z. B. 1xN-Chatnachrichten in Teams) gibt es keine formale Antwortkette, und stattdessen werden Nachrichten in einem einzigen Thread als "flacher Fluss von Nachrichten" angezeigt. In diesen Typen von Apps werden Unterhaltungen aus einer Gruppe von Nachrichten abgeleitet, die innerhalb eines bestimmten Zeitraums auftreten. Diese "Soft-Grouping" von Nachrichten (im Gegensatz zu einer Antwortkette) stellt die "Hin- und Her"-Unterhaltung zu einem bestimmten interessanten Thema dar.

## <a name="step-1-create-a-draft-collection"></a>Schritt 1: Erstellen einer Entwurfssammlung

Nachdem Sie relevante Verwahrer und Inhaltsspeicherorte identifiziert haben, können Sie eine Suche erstellen, um potenziell relevante Inhalte zu finden. Auf der Registerkarte **"Sammlungen"** im Advanced eDiscovery Fall können Sie eine Auflistung erstellen, indem Sie auf **"Neue Auflistung"** klicken und dem Assistenten folgen. Informationen dazu, wie Sie eine Sammlung erstellen, eine Suchabfrage erstellen und eine Vorschau der Suchergebnisse anzeigen können, finden Sie unter [Erstellen einer Entwurfssammlung.](create-draft-collection.md)

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a>Schritt 2: Commit einer Entwurfssammlung in einen Prüfdateisatz

Nachdem Sie die Suchabfrage in einer Sammlung überprüft und abgeschlossen haben, können Sie die Suchergebnisse einem Prüfdateisatz hinzufügen. Wenn Sie Ihre Suchergebnisse zu einem Prüfdateisatz hinzufügen, werden die ursprünglichen Daten in einen Azure Storage Bereich kopiert, um den Überprüfungs- und Analysevorgang zu vereinfachen. Weitere Informationen zum Hinzufügen von Suchergebnissen zu einem Prüfdateisatz finden Sie unter [Commit einer Entwurfssammlung in einen Prüfdateisatz.](commit-draft-collection.md)

Wenn Sie Elemente aus Unterhaltungen zu einem Prüfdateisatz hinzufügen, können Sie die Threadunterhaltungsoption verwenden, um Kontextnachrichten aus Unterhaltungen zu sammeln, die Elemente enthalten, die den Suchkriterien der Sammlung entsprechen. Nachdem Sie die Option "Threadunterhaltungen" ausgewählt haben, kann Folgendes passieren:

  ![Abrufen von Unterhaltungen](../media/messagesandconversations.png)

1. Mithilfe einer Stichwort- und Datumsbereichsabfrage hat die Suche einen Treffer in *Nachricht 3* zurückgegeben. Diese Nachricht war Teil einer größeren Unterhaltung, die durch *CRC1* veranschaulicht wurde.

2. Wenn Sie die Daten zu einem Prüfdateisatz hinzufügen und die Optionen zum Abrufen von Unterhaltungen aktivieren, gehen Advanced eDiscovery zurück und sammeln andere Elemente in *CRC1.*

3. Nachdem die Elemente dem Prüfdateisatz hinzugefügt wurden, können Sie alle einzelnen Nachrichten von *CRC1* überprüfen.

Informationen zum Aktivieren der Threadunterhaltungsoption finden Sie unter [Commit einer Entwurfssammlung in einen Prüfdateisatz.](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set)

## <a name="step-3-review-and-export-threaded-conversations"></a>Schritt 3: Überprüfen und Exportieren von Threadunterhaltungen

Nachdem der Inhalt verarbeitet und dem Prüfdateisatz hinzugefügt wurde, können Sie mit der Überprüfung der Daten im Prüfdateisatz beginnen. Die Überprüfungsfunktionen sind unterschiedlich, je nachdem, ob der Inhalt einem Standardprüfdateisatz oder einem Unterhaltungsüberprüfungssatz hinzugefügt wurde.

### <a name="reviewing-conversations-in-a-standard-review-set"></a>Überprüfen von Unterhaltungen in einem Standardmäßigen Prüfdateisatz

In einem standardmäßigen Prüfdateisatz werden Nachrichten verarbeitet und als einzelne Elemente angezeigt, ähnlich wie sie in einem Postfachordner gespeichert werden. In diesem Workflow wird jede Nachricht als separates Element verarbeitet. Daher sind die Thread-Zusammenfassungs- und Exportoptionen in einem Standardmäßigen Prüfdateisatz nicht verfügbar.

  ![Standardprüfdateisatz](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a>Überprüfen von Unterhaltungen in einem Unterhaltungsüberprüfungssatz

In einem Unterhaltungsüberprüfungssatz werden einzelne Nachrichten miteinander gethreadt und als Unterhaltungen dargestellt. Auf diese Weise können Sie Kontextunterhaltungen überprüfen und exportieren.

  ![Prüfdateisatz für Unterhaltungen](../media/ConversationRSOptions.PNG)

In den folgenden Abschnitten wird das Überprüfen und Exportieren von Unterhaltungen in einem Unterhaltungsüberprüfungssatz beschrieben.

#### <a name="reviewing-conversations"></a>Überprüfen von Unterhaltungen

In einem Unterhaltungsprüfdateisatz können Sie die folgenden Optionen verwenden, um den Überprüfungsprozess zu vereinfachen.

- **Gruppieren nach Unterhaltung:** Gruppiert Nachrichten innerhalb derselben Unterhaltung zusammen, um Benutzern zu helfen, ihren Überprüfungsprozess zu vereinfachen und zu beschleunigen.

- **Zusammenfassungsansicht:** Zeigt die Threadunterhaltung an. In dieser Ansicht können Sie die gesamte Unterhaltung anzeigen und auch auf die Metadaten für jede einzelne Nachricht zugreifen.

   - Anzeigen von Metadaten für einzelne Nachrichten

   - Herunterladen einzelner Nachrichten

- **Textansicht:** Stellt den extrahierten Text für die gesamte Unterhaltung bereit.

- **Kommentaransicht:** Hier können Sie eine Threadansicht der Unterhaltung markupen. Alle Nachrichten in der Unterhaltung teilen sich dasselbe kommentierte Dokument.

- **Tagging:** Beim Anzeigen von Unterhaltungen in einem Prüfdateisatz können Sie Tags anzeigen und anwenden, indem Sie im Codebereich auf den **Bereich "Tagging"** klicken.

- **Unterhaltungskonvertierung erneut ausführen:** Wenn Einem Unterhaltungsüberprüfungssatz Nachrichten hinzugefügt werden, wird automatisch ein Konvertierungsauftrag ausgeführt, um die Threadzusammenfassung zu erstellen und Ansichten mit Anmerkungen zu versehen. Wenn der Auftrag für die Wiederherstellung von Unterhaltungen fehlschlägt, können Sie diesen Auftrag erneut ausführen, indem Sie im Prüfdateisatz auf **Aktion > Unterhaltungs-PDFs erstellen** klicken.

#### <a name="exporting-conversations"></a>Exportieren von Unterhaltungen

In einem Prüfdateisatz für Unterhaltungen können Sie die folgenden Optionen zum Exportieren von Unterhaltungen festlegen:

![Exportoptionen für Unterhaltungen](../media/export.png)

1. Metadatenoptionen:
   - **Datei laden:** Metadaten sind für jede einzelne Nachricht, E-Mail und jedes Dokument enthalten. Es gibt eine Zeile für jede Nachricht in einer Unterhaltung.
   - **Tags:** Tags aus Ihrem Überprüfungsprozess sind in der Metadatendatei enthalten. Nachrichten in einer Unterhaltung verwenden dieselben Tags.

2. Unterhaltungsoptionen:
   - **Unterhaltungsdateien:** Wenn Sie Unterhaltungsdateien exportieren, wird die kommentierte Ansicht in eine PDF-Datei konvertiert und in den Exportordner heruntergeladen. Nachrichten in einer Unterhaltungsdatei verweisen auf die PDF-Version derselben Unterhaltungsdatei.
   - **Einzelne Chatnachrichten:** Wenn Sie einzelne Nachrichten exportieren, wird jede eindeutige Nachricht in der Unterhaltung als eigenständiges Element exportiert. Die Datei wird in demselben Format exportiert, wie sie im Postfach gespeichert wurde. Für eine bestimmte Unterhaltung erhalten Sie mehrere MSG-Dateien.

     > [!NOTE]
     > Wenn Sie Anmerkungen auf die Unterhaltungsdatei angewendet haben, werden diese Anmerkungen nicht auf die einzelnen Nachrichten übertragen.

3. Weitere Optionen:
   - **Generieren Sie Textdateien für alle exportierten Inhalte:** Generiert eine Textdatei für jede Unterhaltung, die aus dem Prüfdateisatz exportiert wurde.
   - **Ersetzen Sie exportierte Inhalte durch bearbeitete PDFs:** Wenn während des Überprüfungsprozesses bearbeitete Unterhaltungsdateien generiert werden, sind diese Dateien während des Exports verfügbar. Sie können entscheiden, ob Sie nur die systemeigenen Dateien exportieren (indem Sie diese Option nicht auswählen) oder die nativen Dateien durch die bearbeiteten Versionen der nativen Dateien (durch Auswahl dieser Option) ersetzen, die als PDF-Dateien exportiert werden.

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen zum Überprüfen von Falldaten in Advanced eDiscovery finden Sie in den folgenden Artikeln:

- [Anzeigen von Falldaten](view-documents-in-review-set.md)
- [Analysieren von Falldaten](analyzing-data-in-review-set.md)
- [Exportieren von Falldaten](exporting-data-ediscover20.md)
