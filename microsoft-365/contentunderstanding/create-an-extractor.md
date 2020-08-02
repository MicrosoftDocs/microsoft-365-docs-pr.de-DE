---
title: Erstellen eines Extraktors (Vorschau)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Informationen zum Erstellen eines Extraktions Moduls
ms.openlocfilehash: 76cb17df069c6905080baabb0b57d765fe5cc94c
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540106"
---
# <a name="create-an-extractor-preview"></a>Erstellen eines Extraktors (Vorschau)
> [!Note] 
> Der Inhalt dieses Artikels ist für Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Bevor oder nachdem Sie ein Klassifizierungsmodell erstellt haben, um die Identifizierung und Klassifizierung bestimmter Dokumenttypen zu automatisieren, können Sie dem Modell optional Extraktoren hinzufügen, um bestimmte Informationen aus diesen Dokumenten herauszuziehen. Möglicherweise möchten Sie, dass Ihr Modell nicht nur alle *Vertrags Erneuerungs* Dokumente identifiziert, die Ihrer Dokumentbibliothek hinzugefügt werden, sondern auch das *Start Datum des Diensts* für jedes Dokument als Spalte in der Dokumentbibliothek anzeigen.

Sie müssen für jede Entität im Dokument, die extrahiert werden soll, einen Extraktor erstellen. In unserem Beispiel möchten wir das *Start Datum des Diensts* für jedes *Vertrags Erneuerungs* Dokument extrahieren, das vom Modell identifiziert wird. Wir möchten in der Lage sein, eine Ansicht in der Dokumentbibliothek aller *Vertrags Erneuerungs* Dokumente mit einer Spalte anzuzeigen, in der der Wert des Dienst Anfangsdatums jedes Dokuments angezeigt wird.

> [!Note]
> Vor dem Erstellen eines Extraktors müssen Sie [Ihre Beispieldateien hinzufügen](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) , die Sie beim Trainieren des Modells unterstützen müssen, um die Informationen zu identifizieren, die extrahiert werden sollen. Verwenden Sie die gleichen Beispieldateien, die Sie zum Erstellen ihrer Klassifizierung verwendet haben.


## <a name="name-your-extractor"></a>Nennen Sie den Extraktor

1. Klicken Sie auf der Modell Startseite in der Kachel **Erstellen und trainieren von Extraktions** Modulen auf **Zug-Extraktor**.
2. Geben Sie auf dem Bildschirm **neuer Entitäts Extraktions** Modul den Namen Ihres Extraktors in das Feld **neuer Extraktions Name** ein. Beispielsweise können wir den **Starttermin** für den IT-Dienst benennen, wenn der Starttermin des Diensts aus jedem Vertrags Erneuerungs Dokument extrahiert werden soll.
3. Klicken Sie auf **Erstellen**.

## <a name="add-a-label"></a>Hinzufügen einer Bezeichnung

Im nächsten Schritt bezeichnen Sie die Informationen, die Sie extrahieren möchten, in ihren Übungsbeispiel Dateien.

Beim Erstellen des Extraktors wird die Extraktions Seite geöffnet, auf der Sie eine Liste mit den Beispieldateien sehen, wobei die erste Datei in der Liste im Viewer angezeigt wird.

1. Wählen Sie im Viewer die Daten aus, die Sie aus den Dateien extrahieren möchten. Wenn Sie beispielsweise das *Datum des Start Diensts*extrahieren möchten, markieren Sie den Datumswert in der ersten Datei (*Montag, Oktober 14, 2019*). Klicken Sie dann auf **Speichern**.  Der Wert für die Datei wird in der Liste mit den beschrifteten Beispielen unter der Spalte **Label** angezeigt.
2. Wählen Sie **nächste Datei** zum automatischen Speichern aus, und öffnen Sie die nächste Datei in der Liste im Viewer, oder wählen Sie **Speichern** aus, und wählen Sie in der Liste mit den **beschrifteten Beispielen** eine andere Datei aus.
3. Wiederholen Sie im Viewer die Schritte 1 und 2, und gehen Sie so vor, bis Sie die Beschriftung in fünf Dateien gespeichert haben.

    ![Erweiterte Einstellungen](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a>Hinzufügen eines negativen Beispiels

Ähnlich wie beim Erstellen einer Klassifizierung eine negative Beispieldatei hinzugefügt werden soll, müssen Sie ein negatives Beispiel für den Extraktor hinzufügen. Für unser Beispiel sollte es eine Datei sein, die keinen Start Datumswert des Diensts enthält.

1. Wählen Sie in der Liste mit den **beschrifteten Beispielen** ein negatives Beispiel aus.
2. Wählen Sie im Viewer oben im Artikel **keine Beschriftung vorhanden**aus.
3. Klicken Sie auf **Speichern**.
 
Nachdem Sie fünf Dateien markiert haben, wird ein Benachrichtigungs Banner angezeigt, in dem Sie informiert werden, dass Sie zur Schulung übergehen möchten. Sie können mehr Dokumente auswählen oder zur Schulung wechseln. 

## <a name="add-an-explanation"></a>Hinzufügen einer Erklärung

Für unser Beispiel werden wir eine Erklärung erstellen, die einen Hinweis auf das Entitäts Format selbst und in den Beispiel Dokumenten möglicherweise Variationen enthält. Beispielsweise kann ein Date-Wert in einer Reihe von unterschiedlichen Formaten vorliegen, beispielsweise:
- 10/14/2019
- 14. Oktober 2019
- Montag, Oktober 14, 2019
 

Um den *Start Termin des Diensts* zu ermitteln, können Sie eine Mustererklärung erstellen.

1. Wählen Sie im Abschnitt Erklärung die Option **neu**aus, und geben Sie dann einen Namen ein (beispielsweise *Date*).
2. Wählen Sie für den Typ die Option **Musterliste**aus.
3. Für den Wert müssen Sie die Datums Variation angeben, die in den Beispieldateien angezeigt wird. Wenn beispielsweise Datumsformate als 0/00/0000 angezeigt werden, geben Sie alle Variationen ein, die in Ihren Dokumenten angezeigt werden können, beispielsweise:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Wählen Sie **Speichern** aus.


### <a name="use-the-explanation-library"></a>Verwenden der Erklärungs Bibliothek

Für das Erstellen von Erläuterungen zu Dingen wie Datumsangaben ist es wesentlich einfacher, die Erklärungs Bibliothek zu verwenden, als alle Variationen manuell einzugeben. Die Erklärungs Bibliothek ist ein Satz von vordefinierten Phrasen-und Muster Erläuterungen. Die Bibliothek versucht, alle Formate für allgemeine Phrasen-oder Muster Listen bereitzustellen, wie Datumsangaben, Telefonnummern, Postleitzahlen und viele andere. 

Für unser Beispiel zum *Start Datum von Diensten* ist es effizienter, die vordefinierte Erläuterung für *Date* in der Erklärungs Bibliothek zu verwenden:

1. Wählen Sie im **Abschnitt Erläuterung**die Option **neu**aus, und wählen Sie dann **aus Erklärungs Bibliothek**.
2. Wählen Sie in der Erklärungs Bibliothek **Datum**aus. Sie können alle Datums Variationen anzeigen, die erkannt werden.
3. Klicken Sie auf **Hinzufügen**.</br>

    ![Erklärungs Bibliothek](../media/content-understanding/explanation-library.png) 

4. Auf der Seite **eine Erklärung erstellen** werden die *Datums* Angaben aus der Erklärungs Bibliothek die Felder automatisch ausfüllen. Wählen Sie **Speichern** aus.</br>

    ![Erklärungs Bibliothek](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a>Trainieren des Modells 

Wenn Sie Ihre Erklärung speichern, wird die Schulung gestartet. Wenn Ihr Modell über genügend Informationen verfügt, um die Daten aus ihren beschrifteten Beispieldateien zu extrahieren, wird jede Datei mit der Bezeichnung **Match**angezeigt.  

![Erklärungs Bibliothek](../media/content-understanding/match2.png) 

Wenn die Erklärung nicht über genügend Informationen verfügt, um die Daten zu finden, die Sie extrahieren möchten, wird jede Datei mit einem **Missverhältnis**versehen. Sie können auf die nicht übereinstimmenden Dateien klicken, um weitere Informationen dazu zu erhalten, warum ein Konflikt aufgetreten ist.


## <a name="add-another-explanation"></a>Hinzufügen einer weiteren Erläuterung

Häufig ist die Übereinstimmung ein Hinweis darauf, dass die von uns angegebene Erklärung nicht genügend Informationen bereitgestellt hat, um den Wert für das Startdatum des Diensts zu extrahieren und mit unseren beschrifteten Dateien übereinstimmen. Möglicherweise müssen Sie es bearbeiten oder eine weitere Erklärung hinzufügen.

Für unser Beispiel stellen wir fest, dass der *anfangs Dienst Datum* der Textzeichenfolge immer dem tatsächlichen Wert vorangestellt ist. Um den Start Termin des Diensts zu identifizieren, können wir eine Phrasen Erklärung erstellen.

1. Wählen Sie im Abschnitt Erklärung die Option **neu**aus, und geben Sie dann einen Namen ein (beispielsweise *Präfixzeichenfolge*).
2. Wählen Sie für den Typ die Option **Phrase List**aus.
3. Verwenden Sie das *Start Datum des Diensts* als Wert.
4. Wählen Sie **Speichern** aus.

    ![Erklärungs Bibliothek](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a>Trainieren des Modells

Wenn Sie Ihre Erklärung speichern, wird das Training erneut gestartet, wobei beide Erläuterungen in unserem Beispiel verwendet werden. Wenn Ihr Modell über genügend Informationen verfügt, um die Daten aus ihren beschrifteten Beispieldateien zu extrahieren, wird jede Datei mit der Bezeichnung **Match**angezeigt. 

Wenn Sie erneut eine **Übereinstimmung** bei ihren beschrifteten Dateien erhalten, müssen Sie möglicherweise eine weitere Erklärung erstellen, um das Modell mit weiteren Informationen zum Identifizieren des Dokumenttyps zu versehen oder um Änderungen an Ihren vorhandenen vorzunehmen.

## <a name="test-your-model"></a>Testen des Modells

Wenn Sie eine Übereinstimmung mit den beschrifteten Beispieldateien erhalten haben, können Sie Ihr Modell nun auf ihren restlichen unbeschrifteten Beispieldateien testen.

1. Klicken Sie auf der Modell Startseite auf die Registerkarte **Test** .  Dadurch wird das Modell für Ihre unbeschrifteten Beispieldateien ausgeführt.
2. In der Liste **Test Dateien** werden Ihre Beispieldateien angezeigt, und es wird angezeigt, ob das Modell die benötigten Informationen extrahieren kann. Anhand dieser Informationen können Sie die Effektivität ihrer Klassifizierung bei der Identifizierung Ihrer Dokumente ermitteln.

    ![Testen der Dateien](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a>Siehe auch
  




