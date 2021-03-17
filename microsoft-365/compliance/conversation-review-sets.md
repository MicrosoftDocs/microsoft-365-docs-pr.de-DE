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
description: Erfahren Sie mehr über das Unterhaltungsrekonstruktionsfeature in Advanced eDiscovery (unterhaltungsthreading) zum Rekonstruieren, Überprüfen und Exportieren von Chatunterhaltungen in Microsoft Teams und Yammer Gruppen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 12887ba8dd74c3dab445dcc76e155e274a371539
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838304"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a>Unterhaltungsthreading in Advanced eDiscovery

Instant Messaging ist eine bequeme Möglichkeit, Fragen zu stellen, Ideen auszutauschen oder schnell über große Zielgruppen zu kommunizieren. Da Instant Messaging-Plattformen wie Microsoft Teams und Yammer-Gruppen zum Kern der Zusammenarbeit in Unternehmen werden, müssen Organisationen bewerten, wie ihr eDiscovery-Workflow diese neuen Formen der Kommunikation und Zusammenarbeit behandelt.

Das Feature Unterhaltungsrekonstruktion in Advanced eDiscovery soll Ihnen dabei helfen, kontextbezogene Inhalte zu identifizieren und unterschiedliche Unterhaltungsansichten zu erzeugen. Mit dieser Funktion können Sie vollständige Chatunterhaltungen (auch Threadunterhaltungen *genannt)* effizient und schnell überprüfen, die auf Plattformen wie Microsoft Teams generiert werden.

Mit der Unterhaltungsrekonstruktion können Sie integrierte Funktionen zum Rekonstruieren, Überprüfen und Exportieren von Threadunterhaltungen verwenden. Verwenden Sie Advanced eDiscovery Conversation Reconstruction für:

- Bewahren Sie eindeutige Metadaten auf Nachrichtenebene für alle Nachrichten in einer Unterhaltung auf.

- Sammeln von Kontextnachrichten rund um Ihre Suchergebnisse.

- Überprüfen, Kommentieren und Redact-Threadunterhaltungen.

- Exportieren einzelner Nachrichten oder Threadunterhaltungen

## <a name="terminology"></a>Terminologie

Im Folgenden finden Sie einige Definitionen, mit deren Hilfe Sie mit der Unterhaltungsrekonstruktion beginnen können.

- **Nachrichten:** Stellen Sie die kleinste Einheit einer Unterhaltung dar. Nachrichten können in Größe, Struktur und Metadaten variieren. 

- **Unterhaltung:** Stellt eine Gruppierung einer oder mehreren Nachrichten dar. In verschiedenen Anwendungen können Unterhaltungen auf unterschiedliche Weise dargestellt werden. In einigen Anwendungen gibt es eine explizite Aktion, die aus der Antwort auf eine vorhandene Nachricht resultiert. Unterhaltungen werden explizit als Ergebnis dieser Benutzeraktion gebildet. Hier finden Sie beispielsweise einen Screenshot einer Kanal unterhaltung in Microsoft Teams.

   ![Microsoft Teams Channel Conversation](../media/threadedchat.png)

   In anderen Apps (z. B. 1xN-Chatnachrichten in Teams) gibt es keine formale Antwortkette, sondern Nachrichten werden in einem einzigen Thread als "flacher Fluss von Nachrichten" angezeigt. In diesen Typen von Apps werden Unterhaltungen aus einer Gruppe von Nachrichten abgeleitet, die innerhalb einer bestimmten Zeit auftreten. Diese "soft-grouping" von Nachrichten (im Gegensatz zu einer Antwortkette) stellt die "Hin und Her"-Unterhaltung zu einem bestimmten Thema dar, das von Interesse ist.

## <a name="step-1-create-a-draft-collection"></a>Schritt 1: Erstellen einer Entwurfssammlung

Nachdem Sie relevante Custodians und Inhaltsstandorte identifiziert haben, können Sie eine Suche erstellen, um potenziell relevante Inhalte zu finden. Auf der **Registerkarte Sammlungen** im Fall Advanced eDiscovery können Sie eine Auflistung erstellen, indem Sie auf Neue Auflistung **klicken** und dem Assistenten folgen. Informationen dazu, wie Sie eine Auflistung erstellen, eine Suchabfrage erstellen und eine Vorschau der Suchergebnisse anzeigen können, finden Sie unter [Create a draft collection](create-draft-collection.md).

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a>Schritt 2: Commit einer Entwurfssammlung für einen Überprüfungssatz

Nachdem Sie die Suchabfrage in einer Auflistung überprüft und abschließend erstellt haben, können Sie die Suchergebnisse einem Überprüfungssatz hinzufügen. Wenn Sie Ihre Suchergebnisse zu einem Überprüfungssatz hinzufügen, werden die ursprünglichen Daten in einen Azure Storage-Bereich kopiert, um den Überprüfungs- und Analyseprozess zu erleichtern. Weitere Informationen zum Hinzufügen von Suchergebnissen zu einem Überprüfungssatz finden Sie unter [Commit a draft collection to a review set](commit-draft-collection.md).

Wenn Sie Einem Überprüfungssatz Elemente aus Unterhaltungen hinzufügen, können Sie die Option Threadunterhaltungen verwenden, um kontextbezogene Nachrichten aus Unterhaltungen zu sammeln, die Elemente enthalten, die den Suchkriterien der Auflistung entsprechen. Nachdem Sie die Option Threadunterhaltungen ausgewählt haben, können die folgenden Schritte ausgeführt werden:

  ![Unterhaltungsabruf](../media/messagesandconversations.png)
  
1. Mithilfe einer Schlüsselwort- und Datumsbereichsabfrage hat die Suche einen Treffer in *Nachricht 3 zurückgegeben.* Diese Nachricht war Teil einer größeren Unterhaltung, dargestellt von *CRC1*.
  
2. Wenn Sie die Daten zu einem Überprüfungssatz hinzufügen und die Unterhaltungsabrufoptionen aktivieren, wird Advanced eDiscovery zurück und sammelt andere Elemente in *CRC1*.
  
3. Nachdem die Elemente dem Überprüfungssatz hinzugefügt wurden, können Sie alle einzelnen Nachrichten aus *CRC1 überprüfen.*

Informationen zum Aktivieren der Option threaded conversations finden Sie unter [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).
  
## <a name="step-3-review-and-export-threaded-conversations"></a>Schritt 3: Überprüfen und Exportieren von Threadunterhaltungen

Nachdem der Inhalt verarbeitet und dem Überprüfungssatz hinzugefügt wurde, können Sie mit der Überprüfung der Daten im Überprüfungssatz beginnen. Die Überprüfungsfunktionen unterscheiden sich je nachdem, ob der Inhalt einem Standardüberprüfungssatz oder einem Unterhaltungsüberprüfungssatz hinzugefügt wurde.

### <a name="reviewing-conversations-in-a-standard-review-set"></a>Überprüfen von Unterhaltungen in einem Standardüberprüfungssatz

In einem Standardüberprüfungssatz werden Nachrichten wie in einem Postfachordner verarbeitet und als einzelne Elemente angezeigt. In diesem Workflow wird jede Nachricht als separates Element verarbeitet. Dies hat zur Folge, dass die Zusammenfassungs- und Exportoptionen im Thread nicht in einem Standardüberprüfungssatz verfügbar sind.

  ![Standardüberprüfungssatz](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a>Überprüfen von Unterhaltungen in einem Unterhaltungsüberprüfungssatz

In einem Unterhaltungsüberprüfungssatz werden einzelne Nachrichten zusammengefädelt und als Unterhaltungen dargestellt. Auf diese Weise können Sie Kontextunterhaltungen überprüfen und exportieren. 

  ![Unterhaltungsüberprüfungssatz](../media/ConversationRSOptions.PNG)

In den folgenden Abschnitten wird das Überprüfen und Exportieren von Unterhaltungen in einem Unterhaltungsüberprüfungssatz beschrieben.

#### <a name="reviewing-conversations"></a>Überprüfen von Unterhaltungen

In einem Unterhaltungsüberprüfungssatz können Sie die folgenden Optionen verwenden, um den Überprüfungsprozess zu erleichtern.

- **Gruppieren nach Unterhaltung:** Gruppen von Nachrichten in derselben Unterhaltung, um Benutzern zu helfen, ihren Überprüfungsprozess zu vereinfachen und zu beschleunigen.

- **Zusammenfassungsansicht:** Zeigt die Thread-Unterhaltung an. In dieser Ansicht können Sie die gesamte Unterhaltung anzeigen und auch auf die Metadaten für jede einzelne Nachricht zugreifen.  
  
   - Anzeigen von Metadaten für einzelne Nachrichten
   
   - Herunterladen einzelner Nachrichten

- **Textansicht:** Stellt den extrahierten Text für die gesamte Unterhaltung.

- **Anmerkungsansicht:** Ermöglicht das Markup einer Threadansicht der Unterhaltung. Alle Nachrichten in der Unterhaltung haben dasselbe mit Anmerkungen versehene Dokument.

- **Tagging:** Wenn Sie Unterhaltungen in einem Überprüfungssatz anzeigen, können Sie Tags anzeigen und anwenden, indem Sie im Codierungspanel auf **Tagging-Bereich** klicken.

- **Erneutes Ausführen der Unterhaltungskonvertierung:** Wenn Nachrichten zu einem Unterhaltungsüberprüfungssatz hinzugefügt werden, wird automatisch ein Konvertierungsauftrag ausgeführt, um die Zusammenfassung im Thread zu erstellen und Ansichten mit Anmerkungen zu versehen. Wenn beim Auftrag Unterhaltungsrekonstruktion ein Fehler auftritt, können Sie diesen Auftrag erneut ausführen, indem Sie im Überprüfungssatz auf Aktion **> Unterhaltungs-PDFs** erstellen klicken.

#### <a name="exporting-conversations"></a>Exportieren von Unterhaltungen

In einem Unterhaltungsüberprüfungssatz können Sie die folgenden Optionen zum Exportieren von Unterhaltungen festlegen:

![Exportoptionen für Unterhaltungen](../media/export.png)

a. Metadatenoptionen

   - **Datei laden:** Metadaten sind für jede einzelne Nachricht, E-Mail und jedes Dokument enthalten. Es gibt eine Zeile für jede Nachricht in einer Unterhaltung. 

   - **Tags:** Tags aus Ihrem Überprüfungsprozess sind in der Metadatendatei enthalten. Nachrichten in einer Unterhaltung verwenden dieselben Tags. 

b. Unterhaltungsoptionen
  
   - **Unterhaltungsdateien:** Wenn Sie Unterhaltungsdateien exportieren, wird die mit Anmerkungen versehene Ansicht in eine PDF-Datei konvertiert und in den Exportordner heruntergeladen. Nachrichten in einer Unterhaltungsdatei verweisen auf die PDF-Version derselben Unterhaltungsdatei.  
  
   - **Einzelne Chatnachrichten:** Wenn Sie einzelne Nachrichten exportieren, wird jede eindeutige Nachricht in der Unterhaltung als eigenständiges Element exportiert. Die Datei wird im gleichen Format exportiert wie im Postfach. Für eine bestimmte Unterhaltung erhalten Sie mehrere MSG-Dateien.

     >[!NOTE]
     > Wenn Sie Anmerkungen auf die Unterhaltungsdatei angewendet haben, werden diese Anmerkungen nicht auf die einzelnen Nachrichten übertragen.

c. Weitere Optionen

   - **Generieren von Textdateien für alle exportierten Inhalte:** Generiert eine Textdatei für jede Unterhaltung, die aus dem Überprüfungssatz exportiert wurde.

   - **Ersetzen Sie exportierten Inhalt durch redaktierte PDFs:** Wenn während des Überprüfungsprozesses redaktierte Unterhaltungsdateien generiert werden, sind diese Dateien während des Exports verfügbar. Sie können entscheiden, ob Sie nur die systemeigenen Dateien exportieren (indem Sie diese Option nicht auswählen) oder die systemeigenen Dateien durch die rotierten Versionen der systemeigenen Dateien ersetzen (indem Sie diese Option auswählen), die als PDF-Dateien exportiert werden.

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen zum Überprüfen von Falldaten in Advanced eDiscovery finden Sie in den folgenden Artikeln:

- [Anzeigen von Falldaten](view-documents-in-review-set.md)

- [Analysieren von Falldaten](analyzing-data-in-review-set.md)

- [Exportieren von Falldaten](exporting-data-ediscover20.md)
