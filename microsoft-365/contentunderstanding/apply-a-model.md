---
title: Anwenden eines Dokument Verständnisses-Modells auf eine Dokumentbibliothek
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informationen zum Anwenden eines veröffentlichten Modells auf eine SharePoint-Dokumentbibliothek
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295490"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Anwenden eines Dokument Verständnisses für das Modell in Microsoft SharePoint Syntex

Der Inhalt dieses Artikels ist für die Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Nachdem Sie Ihr Dokument grundlegendes Modell veröffentlicht haben, können Sie es auf eine SharePoint-Dokumentbibliothek in Ihrem Microsoft 365-Mandanten anwenden.

> [!NOTE]
> Sie können das Modell nur auf Dokumentbibliotheken anwenden, auf die Sie Zugriff haben.


## <a name="apply-your-model-to-a-document-library"></a>Wenden Sie Ihr Modell auf eine Dokumentbibliothek an.

So wenden Sie Ihr Modell auf eine SharePoint-Dokumentbibliothek an:

1. Wählen Sie auf der Startseite des Modells auf der Kachel **Modell auf Bibliotheken anwenden** die Option **Modell veröffentlichen**aus. Sie können auch im Abschnitt **Bibliotheken mit diesem Modell** die Option **+ Bibliothek hinzufügen** auswählen. </br>

    ![Hinzufügen eines Modells zur Bibliothek](../media/content-understanding/apply-to-library.png)</br>

2. Wählen Sie die SharePoint-Website mit der Dokumentbibliothek aus, auf die Sie das Modell anwenden möchten. Wenn die Website nicht in der Liste angezeigt wird, verwenden Sie das Suchfeld, um Sie zu finden.</br>

    ![Website auswählen](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > Sie müssen *Listenberechtigungen verwalten* oder *Bearbeitungs* Rechte für die Dokumentbibliothek haben, auf die Sie das Modell anwenden.</br>

3. Nachdem Sie die Website ausgewählt haben, wählen Sie die Dokumentbibliothek aus, auf die Sie das Modell anwenden möchten. Wählen Sie im Beispiel die Dokumentbibliothek *Dokumente* auf der *Fall Verfolgungs* Website von Contoso aus.</br>

    ![Auswählen einer doc-Bibliothek](../media/content-understanding/select-doc-library.png)</br>

4. Da das Modell einem Inhaltstyp zugeordnet ist, wird beim Anwenden auf die Bibliothek eine Ansicht für den Inhaltstyp erstellt, wobei die von Ihnen extrahierten Beschriftungen als Spalten angezeigt werden. Diese Ansicht ist standardmäßig die Standardansicht der Bibliothek, Sie können jedoch optional festlegen, dass Sie nicht die Standardansicht sein soll, indem Sie **Erweiterte Einstellungen** auswählen und die Option **Diese neue Ansicht als Standard festlegen**deaktivieren.</br>

    ![Bibliotheksansicht](../media/content-understanding/library-view.png)</br>

5. Wählen Sie **Hinzufügen** aus, um das Modell auf die Bibliothek anzuwenden. 
6. Auf der Modell Startseite sollte im Abschnitt **Bibliotheken mit diesem Modell** die URL der SharePoint-Website angezeigt werden.</br>

    ![Ausgewählte Bibliothek](../media/content-understanding/selected-library.png)</br>

7. Wechseln Sie zu Ihrer Dokumentbibliothek, und stellen Sie sicher, dass Sie sich in der Dokumentbibliotheksansicht des Modells befinden. Beachten Sie, dass bei Auswahl der Schaltfläche Informationen neben dem Namen der Dokumentbibliothek eine Meldung darauf hinweist, dass Ihr Modell auf die Dokumentbibliothek angewendet wurde.

    ![Informationsansicht](../media/content-understanding/info-du.png)</br> 


Nachdem Sie das Modell auf die Dokumentbibliothek angewendet haben, können Sie mit dem Hochladen von Dokumenten auf die Website beginnen und die Ergebnisse anzeigen.

Das Modell identifiziert alle Dateien mit dem Modell zugeordneten Inhaltstyp und listet diese in ihrer Ansicht auf. Wenn Ihr Modell über Extraktoren verfügt, werden in der Ansicht Spalten für die Daten angezeigt, die Sie aus jeder Datei extrahieren.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Anwenden des Modells auf Dateien, die sich bereits in der Dokumentbibliothek befinden

Während ein angewendetes Modell alle Dateien verarbeitet, die nach der Anwendung in die Dokumentbibliothek hochgeladen wurden, können Sie auch die folgenden Schritte ausführen, um das Modell für Dateien auszuführen, die bereits in der Dokumentbibliothek vorhanden sind, bevor das Modell angewendet wird:

1. Wählen Sie in Ihrer Dokumentbibliothek die Dateien aus, die von Ihrem Modell verarbeitet werden sollen.
2. Nachdem Sie Ihre Dateien ausgewählt haben, werden **klassifizieren und extrahieren** im Menüband der Dokumentbibliothek angezeigt. Wählen Sie **klassifizieren und extrahieren**aus.
3. Die ausgewählten Dateien werden der Warteschlange hinzugefügt, die verarbeitet werden soll.

      ![Klassifizieren und extrahieren](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a>Siehe auch
[Erstellen einer Klassifizierung](create-a-classifier.md)</br>
[Erstellen eines Extraktions Moduls](create-an-extractor.md)</br>
[Dokument Verständnis Übersicht](document-understanding-overview.md)</br>
[Erstellen eines Formular Verarbeitungsmodells](create-a-form-processing-model.md)  
