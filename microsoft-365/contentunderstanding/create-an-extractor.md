---
title: Erstellen eines Extraktions Moduls
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
description: Erfahren Sie, wie Sie einen Extraktor in Microsoft SharePoint Syntex erstellen.
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295456"
---
# <a name="create-an-extractor-preview"></a>Erstellen eines Extraktors (Vorschau)

Der Inhalt in diesem Artikel ist für die Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Bevor oder nachdem Sie ein Klassifizierungsmodell erstellt haben, um die Identifizierung und Klassifizierung bestimmter Dokumenttypen zu automatisieren, können Sie dem Modell optional Extraktoren hinzufügen, um bestimmte Informationen aus diesen Dokumenten herauszuziehen. Möglicherweise möchten Sie, dass Ihr Modell nicht nur alle *Vertrags Erneuerungs* Dokumente identifiziert, die Ihrer Dokumentbibliothek hinzugefügt wurden, sondern auch das *Start Datum des Diensts* für jedes Dokument als Spalte in der Dokumentbibliothek anzeigen.

Sie müssen für jede Entität im Dokument, die extrahiert werden soll, einen Extraktor erstellen. Im Beispiel möchten Sie das *Start Datum des Diensts* für jedes *Vertrags Erneuerungs* Dokument extrahieren, das vom Modell identifiziert wird. Dies muss geschehen, wenn Sie eine Ansicht in der Dokumentbibliothek aller *Vertrags Erneuerungs* Dokumente mit einer Spalte anzeigen möchten, die den Wert für das Start Datum des Diensts für jedes Dokument enthält.

> [!NOTE]
> Vor dem Erstellen eines Extraktors müssen Sie [Ihre Beispieldateien hinzufügen](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) , um das Modell zu unterstützen, um die Informationen zu identifizieren, die extrahiert werden sollen. Verwenden Sie die gleichen Beispieldateien, die Sie zum Erstellen ihrer Klassifizierung verwendet haben.

## <a name="name-your-extractor"></a>Nennen Sie den Extraktor

1. Klicken Sie auf der Modell Startseite in der Kachel **Erstellen und trainieren von Extraktions** Modulen auf **Train Extractor**.
2. Geben Sie auf dem Bildschirm **neuer Entitäts Extraktions** Modul den Namen Ihres Extraktors in das Feld **neuer Extraktions Name** ein. Nennen Sie beispielsweise den **Starttermin** für den IT-Dienst, wenn Sie den Starttermin des Diensts aus jedem Vertrags Erneuerungs Dokument extrahieren möchten.
3. Klicken Sie auf **Erstellen**.

## <a name="add-a-label"></a>Hinzufügen einer Bezeichnung

Im nächsten Schritt bezeichnen Sie die Informationen, die Sie extrahieren möchten, in den Beispiel Schulungsdateien.

Durch Erstellen des Extraktions Moduls wird die Extraktions Seite geöffnet. Hier sehen Sie eine Liste der Beispieldateien, wobei die erste Datei in der Liste im Viewer angezeigt wird.

1. Wählen Sie im Viewer die Daten aus, die Sie aus den Dateien extrahieren möchten. Wenn Sie beispielsweise den *Start Dienst Termin*extrahieren möchten, markieren Sie den Datumswert in der ersten Datei (*Montag, Oktober 14, 2019*). und klicken Sie dann auf **Speichern**.  Sie sollten den Wert aus der Datei in der Liste mit den beschrifteten Beispielen unter der Spalte **Label** anzeigen.
2. Wählen Sie die Option **nächste Datei** zum automatischen Speichern aus, und öffnen Sie die nächste Datei in der Liste im Viewer. Oder wählen Sie **Speichern** aus, und wählen Sie dann in der Liste mit den **beschrifteten Beispielen** eine andere Datei aus.
3. Wiederholen Sie im Viewer die Schritte 1 und 2, und wiederholen Sie den Vorgang, bis Sie die Beschriftung in allen fünf Dateien gespeichert haben.

    ![Erweiterte Einstellungen](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a>Hinzufügen eines negativen Beispiels

Ähnlich wie beim Erstellen einer Klassifizierung eine negative Beispieldatei hinzugefügt wird, müssen Sie ein negatives Beispiel für den Extraktor hinzufügen. Es sollte sich um eine Datei handeln, die keinen Date-Wert vom "Dienst Start" enthält.

1. Wählen Sie in der Liste mit den **beschrifteten Beispielen** ein negatives Beispiel aus.
2. Wählen Sie im Viewer oben im Artikel **keine Beschriftung vorhanden**aus.
3. Klicken Sie auf **Speichern**.
 
Nachdem Sie fünf Dateien markiert haben, wird ein Benachrichtigungs Banner angezeigt, in dem Sie informiert werden, dass Sie zur Schulung übergehen möchten. Sie können mehr Dokumente auswählen oder zur Schulung wechseln. 

## <a name="add-an-explanation"></a>Hinzufügen einer Erklärung

Für das Beispiel erstellen Sie eine Erläuterung, die einen Hinweis auf das Entitäts Format selbst und Variationen in den Beispiel Dokumenten bereitstellt. Beispielsweise kann ein Date-Wert in einer Reihe von unterschiedlichen Formaten vorliegen, beispielsweise:
- 10/14/2019
- 14. Oktober 2019
- Montag, Oktober 14, 2019
 

Um den *Start Termin des Diensts* zu identifizieren, erstellen Sie eine Mustererklärung.

1. Wählen Sie im Abschnitt Erklärung die Option **neu** aus, und geben Sie einen Namen ein (beispielsweise *Date*).
2. Wählen Sie unter Typ die Option **Musterliste**aus.
3. Geben Sie als Wert die Datums Variation so an, wie Sie in den Beispieldateien angezeigt werden. Wenn beispielsweise Datumsformate als 0/00/0000 angezeigt werden, geben Sie alle Variationen ein, die in Ihren Dokumenten angezeigt werden, beispielsweise:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Klicken Sie auf **Speichern**.

### <a name="use-the-explanation-library"></a>Verwenden der Erklärungs Bibliothek

Zum Erstellen von Erläuterungen für Elemente wie Datumsangaben ist es einfacher, die Erklärungs Bibliothek zu verwenden, als alle Variationen manuell einzugeben. Die Erklärungs Bibliothek ist ein Satz von vordefinierten Phrasen-und Muster Erläuterungen. Die Bibliothek bietet alle Formate für allgemeine Phrasen-oder Muster Listen wie Datumsangaben, Telefonnummern, Postleitzahlen usw. 

Für das Beispiel für den *Start Termin des Diensts* ist es effizienter, die vordefinierte Erläuterung für *Date* in der Erklärungs Bibliothek zu verwenden:

1. Wählen Sie im **Abschnitt Erklärung**die Option **neu**aus, und wählen Sie dann **aus Erklärungs Bibliothek aus**.
2. Wählen Sie in der Erklärungs Bibliothek **Datum**aus. Sie können alle erkannten Datums Variationen anzeigen.
3. Klicken Sie auf **Hinzufügen**.</br>

    ![Erklärungs Bibliothek](../media/content-understanding/explanation-library.png) 

4. Auf der Seite **Erklärung erstellen** werden die Felder in den *Datums* Angaben aus der Erklärungs Bibliothek automatisch ausgefüllt. Klicken Sie auf **Speichern**.</br>

    ![Datum](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a>Trainieren des Modells 

Speichern Ihrer Erklärung beginnen Sie das Training. Wenn Ihr Modell über genügend Informationen verfügt, um die Daten aus ihren beschrifteten Beispieldateien zu extrahieren, wird jede Datei mit der Bezeichnung **Match**angezeigt.  

![Vergleich](../media/content-understanding/match2.png) 

Wenn die Erklärung nicht über genügend Informationen verfügt, um die Daten zu finden, die Sie extrahieren möchten, wird jede Datei mit einem **Missverhältnis**versehen. Sie können auf die nicht **übereinstimmenden** Dateien klicken, um weitere Informationen dazu zu erhalten, warum ein Konflikt aufgetreten ist.


## <a name="add-another-explanation"></a>Hinzufügen einer weiteren Erläuterung

Häufig ist die Übereinstimmung ein Hinweis darauf, dass die von uns angegebene Erklärung nicht genügend Informationen bereitgestellt hat, um den Wert für das Startdatum des Diensts zu extrahieren und mit unseren beschrifteten Dateien übereinstimmen. Möglicherweise müssen Sie es bearbeiten oder eine weitere Erklärung hinzufügen.

Beachten Sie für das Beispiel, dass der *anfangs Dienst Datum* der Textzeichenfolge immer dem tatsächlichen Wert vorangestellt ist. Um den Start Termin des Diensts zu identifizieren, müssen Sie eine Phrasen Erklärung erstellen.

1. Wählen Sie im Abschnitt Erklärung die Option **neu**aus, und geben Sie dann einen Namen ein (beispielsweise *Präfixzeichenfolge*).
2. Wählen Sie für den Typ die Option **Phrase List**aus.
3. Verwenden Sie das *Start Datum des Diensts* als Wert.
4. Klicken Sie auf **Speichern**.

    ![Präfixzeichenfolge](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a>Modell erneut trainieren

Wenn Sie die Erläuterung speichern, wird das Training erneut gestartet, wobei beide Erläuterungen im Beispiel verwendet werden. Wenn Ihr Modell über genügend Informationen verfügt, um die Daten aus den beschrifteten Beispieldateien zu extrahieren, sehen Sie jede Datei mit der Bezeichnung **Match**. 

Wenn Sie erneut eine **Übereinstimmung** bei ihren beschrifteten Dateien erhalten, müssen Sie wahrscheinlich eine weitere Erklärung erstellen, um das Modell mit weiteren Informationen zum Identifizieren des Dokumenttyps zu versehen oder Änderungen am Beispielmodell vorzunehmen.

## <a name="test-your-model"></a>Testen des Modells

Wenn Sie eine Übereinstimmung mit den beschrifteten Beispieldateien erhalten, können Sie Ihr Modell nun auf den verbleibenden unbeschrifteten Beispieldateien testen.

1. Klicken Sie auf der Modell Startseite auf die Registerkarte **Test** .  Dadurch wird das Modell für Ihre unbeschrifteten Beispieldateien ausgeführt.
2. In der Liste **Test Dateien** werden Ihre Beispieldateien angezeigt, um anzuzeigen, ob das Modell die benötigten Informationen extrahieren kann. Anhand dieser Informationen können Sie die Effektivität ihrer Klassifizierung bei der Identifizierung Ihrer Dokumente ermitteln.

    ![Testen der Dateien](../media/content-understanding/test-filies-extractor.png) 
