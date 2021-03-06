---
title: 'Barrierefreiheitsmodus für SharePoint Syntex '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Erfahren Sie, wie Sie den Barrierefreiheitsmodus verwenden, wenn Sie ein Modell in SharePoint Syntex trainieren.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515148"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>Barrierefreiheitsmodus für SharePoint Syntex

In [SharePoint Syntex](index.md)können Benutzer den Barrierefreiheitsmodus in allen Phasen der Modellschulung (Bezeichnung, Schulung, Test) beim Arbeiten mit Beispieldokumenten aktivieren. Die Verwendung des Barrierefreiheitsmodus kann Benutzern mit niedriger Sicht bei der Navigation und Beschriftung von Elementen in der Dokumentanzeige helfen, die Barrierefreiheit auf der Tastatur zu vereinfachen.

Auf diese Weise können Benutzer ihre Tastaturen verwenden, um durch Text in der Dokumentanzeige zu navigieren und eine Erzählung nicht nur der ausgewählten Werte, sondern auch von Aktionen (z. B. Beschriftung oder Entfernen von Bezeichnungen aus markierten Texten) oder vorhergesagte Beschriftungswerte zu hören, während Sie das Modell mit zusätzlichen Beispieldokumenten trainieren. 


![Barrierefreiheitsmodus](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>Anforderungen

Um die Audiowiedergabe der Sprachausgabe zu hören, aktivieren Sie die [Sprachausgabe-App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in Den Sprachausgabeeinstellungen auf Ihrem Windows 10-System.

![Aktivieren der Sprachausgabe](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>Bezeichnung für Tastaturbenutzer

Bei Tastaturbenutzern, die den Barrierefreiheitsmodus verwenden, können Sie die folgenden Tasten verwenden, wenn Sie Text in einem Beispieldokument im Viewer beschriften:

- Tab: Verschiebt Sie vorwärts und wählt das nächste Wort aus.
- Tabulator + Umschalt: Verschiebt Sie nach hinten und wählt das vorherige Wort aus.
- Enter: Label or removes a label from the selected word.
- Pfeil nach rechts: Verschiebt Sie durch einzelne Zeichen in einem ausgewählten Wort.
- Pfeil nach links: Verschiebt Sie rückwärts durch einzelne Zeichen in einem ausgewählten Wort.

> [!NOTE]
> Wenn Sie mehrere Wörter für eine einzelne Bezeichnung beschriften, müssen Sie jedes Wort beschriften.


## <a name="narration"></a>Erzählung

Verwenden Sie für Sprachausgabebenutzer, die den Barrierefreiheitsmodus verwenden, dieselbe Tastaturnavigation, die für Tastaturbenutzer beschrieben wird, um das Beispieldokument im Viewer zu durchgehen.

Während Sie durch die Beispieldokumente und Beschriftungszeichenfolgenwerte navigieren, gibt die Sprachausgabe dem Benutzer die folgenden Audioaufforderungen:

- Wenn Sie die Tastatur verwenden, um durch die Dokumentanzeige zu navigieren, gibt Sprachausgabeaudio die ausgewählte Zeichenfolge an.
- Innerhalb einer ausgewählten Zeichenfolge wird jedes Zeichen in der Zeichenfolge durch Sprachausgabeaudio mit der linken oder rechten Pfeiltaste angezeigt, wenn Sie sie auswählen.
- Wenn Sie eine Zeichenfolge auswählen, die beschriftet wurde, gibt die Sprachausgabe den Wert an und dann "beschriftet".  Wenn der Bezeichnungswert beispielsweise "Contoso" ist, wird "Costoso labeled" angegeben. 
- Wenn Sie auf der Registerkarte Schulung eine Zeichenfolge in der Dokumentanzeige auswählen, die nur vorhergesagt wurde, wird der Wert von Sprachausgabeaudio und dann "vorhergesagt" angezeigt. Dies tritt auf, wenn die Schulung einen Wert in der Datei vorhersagt, der nicht mit dem vom Benutzer bezeichneten Wert übereinstimmen kann.
- Wenn Sie auf der Registerkarte Schulung eine Zeichenfolge in der Dokumentanzeige auswählen, die beschriftet und vorhergesagt wurde, gibt Sprachausgabeaudio den Wert an und dann "beschriftet und vorhergesagt". Dies tritt auf, wenn die Schulung erfolgreich ist und eine Übereinstimmung zwischen einem vorhergesagten Wert und der Benutzerbezeichnung besteht.



Nachdem eine Zeichenfolge beschriftet oder eine Bezeichnung im Viewer entfernt wurde, warnt Sprachausgabeaudio Sie, die Änderungen vor dem Beenden zu speichern.

## <a name="see-also"></a>Siehe auch

[Erstellen eines Extraktors](create-an-extractor.md)</br>

[Erstellen einer Klassifizierung](create-a-classifier.md)</br>










 


  
  



