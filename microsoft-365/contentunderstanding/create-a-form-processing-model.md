---
title: Erstellen eines Formular Verarbeitungsmodells
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
description: Erstellen Sie ein Formular Verarbeitungsmodell in Microsoft SharePoint Syntex.
ms.openlocfilehash: f61dbad837173c412daefb7285c4abff10a01817
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295478"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a>Erstellen eines Formular Verarbeitungsmodells in Microsoft SharePoint Syntex

Der Inhalt in diesem Artikel ist für die Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).

Verwenden von [AI Builder](https://docs.microsoft.com/ai-builder/overview) -ein Feature in Microsoft PowerApps-Project Cortex Benutzer können ein [Formular Verarbeitungsmodell](form-processing-overview.md) direkt aus einer SharePoint-Dokumentbibliothek erstellen. 

Das Erstellen eines Formular Verarbeitungsmodells umfasst Folgendes:
 - Schritt 1: Erstellen des von-Verarbeitungsmodells zum Erstellen des Inhaltstyps
 - Schritt 2: Hinzufügen und Analysieren von Beispieldateien
 - Schritt 3: Auswählen der Formularfelder
 - Schritt 4: trainieren und Testen des Modells
 - Schritt 5: Veröffentlichen des Modells
 - Schritt 6: Verwenden des Modells

## <a name="requirements"></a>Anforderungen

Sie können nur ein Formular Verarbeitungsmodell in SharePoint-Dokumentbibliotheken erstellen, für die es aktiviert ist. Wenn die Formularverarbeitung aktiviert ist, können Sie den AI- **Generator** **"Erstellen eines Formular Verarbeitungsmodells"** im Menü " **automatisieren** " in Ihrer Dokumentbibliothek anzeigen.  Wenn Sie die Verarbeitung in Ihrer Dokumentbibliothek aktivieren müssen, müssen Sie sich an Ihren SharePoint-Administrator wenden.

 ![Erstellen eines AI-Generator Modells](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a>Schritt 1: Erstellen eines Formular Verarbeitungsmodells

Der erste Schritt beim Erstellen eines Formular Verarbeitungsmodells besteht darin, diesen Namen zu benennen und den neuen Inhaltstyp define zu erstellen und eine neue Dokumentbibliotheksansicht dafür zu erstellen.

1. Wählen Sie in der Dokumentbibliothek das Menü **automatisieren** aus, wählen Sie **AI Builder**aus, und wählen Sie dann **Formular Verarbeitungsmodell erstellen**aus.

    ![Erstellen eines Modells](../media/content-understanding/create-ai-builder-model.png)</br>

2. Geben Sie im Bereich **Neues Formular Verarbeitungsmodell** im Feld  **Name** einen Namen für Ihr Modell ein (beispielsweise Bestel *Lungen*).

    ![Neues Formular Verarbeitungsmodell](../media/content-understanding/new-form-model.png)</br> 

3. Wenn Sie ein Formular Verarbeitungsmodell erstellen, erstellen Sie einen neuen SharePoint-Inhaltstyp. Ein SharePoint-Inhaltstyp stellt eine Kategorie von Dokumenten dar, die allgemeine Merkmale aufweisen und eine Auflistung von Spalten oder Metadaten-Eigenschaften für diesen bestimmten Inhalt gemeinsam verwenden. SharePoint-Inhaltstypen werden über den [Inhaltstypen Katalog]()verwaltet.

    Wählen Sie **Erweiterte Einstellungen** aus, wenn Sie dieses Modell einem vorhandenen Inhaltstyp im SharePoint-Inhaltstypen Katalog zuordnen möchten, um sein Schema zu verwenden. 

4. Ihr Modell erstellt eine neue Ansicht in Ihrer Dokumentbibliothek für die extrahierten Daten. Wenn die Standardansicht nicht angezeigt werden soll, deaktivieren Sie die Option **als Standardansicht festlegen**.

5. Wählen Sie **Erstellen** aus.

## <a name="step-2-add-and-analyze-documents"></a>Schritt 2: Hinzufügen und Analysieren von Dokumenten

Nachdem Sie Ihr neues Formular Verarbeitungsmodell erstellt haben, öffnet Ihr Browser eine neue Seite des PowerApps AI Builder-Formular Verarbeitungsmodells. Auf dieser Seite können Sie Ihre Beispiel Dokumente hinzufügen und analysieren. </br>

> [!NOTE]
> Wenn Sie nach Beispieldateien suchen, die verwendet werden sollen, lesen Sie das [Formular Verarbeitungsmodell Eingabedokument Anforderungen und Optimierungstipps](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

   ![Power apps AI-Generator](../media/content-understanding/powerapps.png)</br> 
 
1. Wählen Sie **Dokumente hinzufügen** aus, um das Hinzufügen von Beispiel Dokumenten zu beginnen, mit denen die benannten Wert Paare ermittelt werden, die extrahiert werden können. Sie können dann entweder **aus lokalem Speicher**, **SharePoint**oder **Azure-BLOB-Speicher**Hochladen auswählen. Sie müssen mindestens fünf Dateien für die Schulung verwenden.

2. Wählen Sie nach dem Hinzufügen von Dateien **analyze** aus, um nach allen Informationen zu suchen, die bei allen Dateien verwendet werden. Dieser Vorgang kann einige Minuten in Anspruch nehmen.</br> 
 
    ![Analysieren von Dateien](../media/content-understanding/analyze.png)</br> 

3. Nachdem Sie die Dateien analysiert haben, wählen Sie auf der Seite **Formularfelder, die Sie speichern möchten** die Datei aus, um die erkannten Felder anzuzeigen.</br>

    ![Auswählen von Formularfeldern](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Schritt 3: Auswählen der Formularfelder

Nachdem Sie die Dokumente für Felder analysiert haben, können Sie nun die gefundenen Felder anzeigen und diejenigen identifizieren, die Sie speichern möchten. Gespeicherte Felder werden als Spalten in der Dokumentbibliotheksansicht Ihres Modells angezeigt und zeigen die aus jedem Dokument extrahierten Werte an.

1. Auf der nächsten Seite wird eine der Beispieldateien angezeigt, und es werden alle gängigen Felder hervorgehoben, die vom System automatisch erkannt wurden. </br>

    ![Seite "Felder auswählen"](../media/content-understanding/select-fields-page.png)</br> 

2. Wählen Sie die Felder aus, die Sie speichern möchten, und aktivieren Sie das Kontrollkästchen, um die Auswahl zu bestätigen. Wählen Sie beispielsweise im Bestell Modell die Felder *Datum*, *po*und *Summe* aus.  Beachten Sie, dass Sie auch auswählen können, ein Feld umzubenennen, wenn Sie möchten. </br>

    ![Po auswählen #](../media/content-understanding/po.png)</br> 

3. Wenn ein Feld nicht von der Analyse erkannt wurde, können Sie es dennoch hinzufügen. Markieren Sie die Informationen, die extrahiert werden sollen, und geben Sie im Feld Name den gewünschten Namen ein. Aktivieren Sie dann das Kontrollkästchen. Beachten Sie, dass Sie unerkannte Felder in ihren verbleibenden Beispieldateien bestätigen müssen.

4. Klicken Sie auf **Felder bestätigen** , nachdem Sie die Felder ausgewählt haben, die Sie speichern möchten. </br>
 
    ![Felder bestätigen nach dem Auswählen von Feldern](../media/content-understanding/confirm-fields.png)</br> 
 
5. Auf der Seite **Wählen Sie die Formularfelder aus, die Sie speichern möchten** , wird die Anzahl der Felder angezeigt, die Sie ausgewählt haben. Wählen Sie **Fertig** aus.

## <a name="step-4-train-and-test-your-model"></a>Schritt 4: trainieren und Testen des Modells

Nachdem Sie die Felder ausgewählt haben, die Sie speichern möchten, können Sie mit der **Modell Zusammenfassungs** Seite trainieren und Ihr Modell testen.

1. Auf der Seite **Modellzusammenfassung** werden die gespeicherten Felder im Abschnitt **Ausgewählte Felder** angezeigt. Wählen Sie **Train** aus, um mit der Schulung in ihren Beispieldateien zu beginnen. Beachten Sie, dass dieser Vorgang einige Minuten dauern kann.</br>

     ![Auswählen von Feldern "Zug"](../media/content-understanding/select-fields-train.png)</br> 

2. Wenn die Benachrichtigung angezeigt wird, dass die Schulung abgeschlossen ist, wählen Sie **zur Seite Details wechseln**aus. 

3. Auf der Seite **Modelldetails** können Sie die Funktionsweise des Modells testen, indem Sie auf **Schnelltest**klicken. Auf diese Weise können Sie Dateien per Drag & Drop auf die Seite ziehen und prüfen, ob die Felder erkannt werden.

    ![Felder bestätigen](../media/content-understanding/select-fields-train.png)</br> 

2. Wenn die Benachrichtigung angezeigt wird, dass die Schulung abgeschlossen ist, wählen Sie **zur Seite Details wechseln**aus. 

3. Wählen Sie auf der Seite **Modelldetails** die Option **Schnelltest**aus, um zu testen, wie das Modell funktioniert. Auf diese Weise können Sie Dateien per Drag & Drop auf die Seite ziehen und prüfen, ob die Felder erkannt werden.

## <a name="step-5-publish-your-model"></a>Schritt 5: Veröffentlichen des Modells

1. Wenn Sie mit den Ergebnissen Ihres Modells zufrieden sind, wählen Sie **veröffentlichen** aus, um es zur Verwendung zur Verfügung zu stellen.

2. Wählen Sie nach dem Veröffentlichen des Modells **Modell verwenden**aus. Dadurch wird ein PowerAutomate-Fluss erstellt, der in Ihrer SharePoint-Dokumentbibliothek ausgeführt werden kann, und extrahiert die Felder, die im Modell identifiziert wurden, und wählen Sie dann **Flow erstellen**aus.
  
3. Wenn dieser Vorgang abgeschlossen ist, wird die Meldung angezeigt, dass **Ihr Flow erfolgreich erstellt**wurde.
 
## <a name="step-6-use-your-model"></a>Schritt 6: Verwenden des Modells

Nachdem Sie Ihr Modell veröffentlicht und den PowerAutomate-Fluss erstellt haben, können Sie Ihr Modell in Ihrer SharePoint-Dokumentbibliothek verwenden.

1. Wählen Sie nach der Veröffentlichung Ihres Modells zu **SharePoint wechseln** aus, um zu Ihrer Dokumentbibliothek zu wechseln.

2. Beachten Sie in der Ansicht Dokumentbibliothek Modell, dass die von Ihnen ausgewählten Felder jetzt als Spalten angezeigt werden.</br>

    ![Dokument Bibliotheksmodell angewendet](../media/content-understanding/doc-lib-view.png)</br> 

3. Beachten Sie, dass der Link Informationen neben **Dokumenten** darauf hinweist, dass auf diese Dokumentbibliothek ein Formular Verarbeitungsmodell angewendet wird.

    ![Schaltfläche "Info"](../media/content-understanding/info-button.png)</br>  

4. Laden Sie Dateien in Ihre Dokumentbibliothek hoch. Alle Dateien, die vom Modell als Inhaltstyp identifiziert werden, Listen die Dateien in ihrer Ansicht auf und zeigen die extrahierten Daten in den Spalten an.</br>

    ![Fertig](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a>Siehe auch
  
[Power Automation-Dokumentation](https://docs.microsoft.com/power-automate/)</br>
[Schulung: verbessern der Geschäftsleistung mit AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
