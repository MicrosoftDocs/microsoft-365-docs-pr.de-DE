---
title: Anwenden eines Dokumentverständnismodells auf eine Dokumentbibliothek
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Informationen zum Anwenden eines veröffentlichten Modells auf eine SharePoint-Dokumentbibliothek
ms.openlocfilehash: 42168537c8d449a075b5e29ef9905b6b98b8d714
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925400"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Anwenden eines Dokumentverständnismodells in Microsoft SharePoint Syntex

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Nach der Veröffentlichung des Dokumentverständnismodells können Sie es auf eine oder mehrere SharePoint-Dokumentbibliotheken in Ihrem Microsoft 365-Mandanten anwenden.

> [!NOTE]
> Sie können das Modell nur auf Dokumentbibliotheken anwenden, auf die Sie Zugriff haben.


## <a name="apply-your-model-to-a-document-library"></a>Wenden Sie Ihr Modell auf eine Dokumentbibliothek an.

So wenden Sie Ihr Modell auf eine SharePoint-Dokumentbibliothek an:

1. Wählen Sie auf der Modellstartseite auf der Kachel **Modell auf Bibliotheken anwenden** die Option **Modell veröffentlichen** aus. Sie können auch  **+ Bibliothek hinzufügen** im Abschnitt **Bibliotheken mit diesem Modell** auswählen. </br>

    ![Hinzufügen des Modells zur Bibliothek](../media/content-understanding/apply-to-library.png)</br>

2. Sie können dann die SharePoint-Website auswählen, die die Dokumentbibliothek enthält, auf die Sie das Modell anwenden möchten. Wenn die Website in der Liste nicht angezeigt wird, verwenden Sie das Suchfeld, um Sie zu finden.</br>

    ![Auswählen einer Website](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > Sie müssen über die Berechtigung *Listen verwalten* oder *Bearbeiten* für die Dokumentbibliothek verfügen, auf die Sie das Modell anwenden möchten.</br>

3. Nachdem Sie die Website ausgewählt haben, wählen Sie die Dokumentbibliothek aus, auf die Sie das Modell anwenden möchten. Wählen Sie im Beispiel die Dokumentbibliothek *Dokumente* auf der Website *Contoso-Fallnachverfolgung* aus.</br>

    ![Auswählen einer Dokumentbibliothek](../media/content-understanding/select-doc-library.png)</br>

4. Da das Modell einem Inhaltstyp zugeordnet ist, fügt es, wenn Sie es auf die Bibliothek anwenden, den Inhaltstyp und dessen Ansicht hinzu, wobei die Bezeichnungen, die Sie extrahiert haben, als Spalten angezeigt werden. Diese Ansicht ist die Standardansicht der Bibliothek. Sie können aber auch eine andere Aussicht auswählen, indem Sie **Erweiterte Einstellungen** auswählen und die Auswahl für **Diese neue Anzeige als Standard festlegen** deaktivieren.</br>

    ![Bibliotheksansicht](../media/content-understanding/library-view.png)</br>

5. Wählen Sie **Hinzufügen** aus, um das Modell auf die Bibliothek anzuwenden. 
6. Auf der Modellstartseite sollte im Abschnitt **Bibliotheken mit diesem Modell** die URL der aufgelisteten SharePoint-Website angezeigt werden.</br>

    ![Ausgewählte Bibliothek](../media/content-understanding/selected-library.png)</br>

7. Wechseln Sie zu Ihrer Dokumentbibliothek, und vergewissern Sie sich, dass Sie sich in der Dokumentbibliotheksanzeige des Modells befinden. Wenn Sie die Informationsschaltfläche neben dem Namen der Dokumentbibliothek auswählen, wird eine Nachricht angezeigt, die besagt, dass ein Modell auf die Dokumentbibliothek angewendet wurde.

    ![Informationsansicht](../media/content-understanding/info-du.png)</br> 

    Sie können **Aktiven Modelle anzeigen** auswählen, um Details zu allen Modellen anzuzeigen, die auf die Dokumentbibliothek angewendet wurden.

8. Im Bereich **Aktive Modelle** werden die Modelle angezeigt, die auf die Dokumentbibliothek angewendet wurden. Wählen Sie ein Modell aus, um weitere Details dazu anzuzeigen, z. B. eine Beschreibung des Modells, wer das Modell veröffentlicht hat und ob das Modell eine Aufbewahrungsbezeichnung auf die von ihm klassifizierten Dateien zutrifft.

    ![Bereich „Aktive Modelle“](../media/content-understanding/active-models.png)</br> 

Nachdem Sie das Modell auf die Dokumentbibliothek angewendet haben, können Sie mit dem Hochladen von Dokumenten auf die Website beginnen und die Ergebnisse anzeigen.

Das Modell identifiziert alle Dateien mit dem zugeordneten Inhaltstyp des Modells und listet sie in Ihrer Ansicht auf. Wenn Ihr Modell Extraktoren enthält, werden in der Ansicht Spalten für die Daten angezeigt, die Sie aus den einzelnen Dateien extrahieren.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Anwenden des Modells auf Dateien, die sich bereits in der Dokumentbibliothek befinden

Während ein angewendetes Modell alle Dateien verarbeitet, die nach der Anwendung in die Dokumentbibliothek hochgeladen wurden, können Sie auch die folgenden Schritte ausführen, um das Modell für Dateien auszuführen, die bereits vor dem Anwenden des Modells in der Dokumentbibliothek vorhanden sind:

1. Wählen Sie in Ihrer Dokumentbibliothek die Dateien aus, die vom Modell verarbeitet werden sollen.
2. Nach dem Auswählen der Dateien wird **Klassifizieren und extrahieren** im Menüband der Dokumentbibliothek angezeigt. Wählen Sie **Klassifizieren und extrahieren** aus.
3. Die ausgewählten Dateien werden der Warteschlange zur Verarbeitung hinzugefügt.

      ![Klassifizieren und extrahieren](../media/content-understanding/extract-classify.png)</br> 

> [!NOTE]
> Sie können einzelne Dateien in eine Bibliothek kopieren und auf ein Modell anwenden, aber keine Ordner.

### <a name="the-classification-date-field"></a>Das Feld „Klassifizierungsdatum“

Wenn ein SharePoint Syntex-Dokumentverständnis oder ein Formularverarbeitungsmodell auf eine Dokumentbibliothek angewendet wird, wird in das Bibliotheksschema ein Feld <b>Klassifizierungsdatum </b> aufgenommen. Dieses Feld ist standardmäßig leer, aber wenn Dokumente von einem Modell verarbeitet und klassifiziert werden, wird dieses Feld mit einem Datums-/Uhrzeitstempel der Fertigstellung aktualisiert. 

   ![Die Spalte „Klassifizierungsdatum“](../media/content-understanding/class-date-column.png)</br> 

Das Feld für das Klassifizierungsdatum wird vom Trigger [<b>Wenn eine Datei von einem Inhaltsverständnismodell klassifiziert wird</b> verwendet, ](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) um einen Power Automate-Ablauf auszuführen, nachdem ein Syntex-Modell für das Verstehen von Inhalten die Verarbeitung einer Datei abgeschlossen und das Feld „Klassifizierungsdatum“ aktualisiert hat.

   ![Flusstrigger](../media/content-understanding/trigger.png)</br>

Der Trigger <b>Wenn eine Datei von einem Inhaltsverständnissmodell klassifiziert wird</b> kann dann verwendet werden, um einen anderen Workflow unter Verwendung extrahierter Informationen aus der Datei zu starten.



## <a name="see-also"></a>Siehe auch
[Erstellen einer Klassifizierung](create-a-classifier.md)

[Erstellen eines Extraktors](create-an-extractor.md)

[Übersicht über das Dokumentenverständnis](document-understanding-overview.md)