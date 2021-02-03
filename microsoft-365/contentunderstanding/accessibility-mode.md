---
title: 'SharePoint -Syntex-Barrierefreiheitsmodus '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Erfahren Sie, wie Sie den Barrierefreiheitsmodus verwenden, wenn Sie ein Modell in SharePoint Syntex trainieren.
ms.openlocfilehash: 32e5bd132a7a0145f03e4620545d65d1d92ff223
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50081007"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>SharePoint -Syntex-Barrierefreiheitsmodus

In [SharePoint Syntex](index.md)können Benutzer den Barrierefreiheitsmodus in allen Phasen der Modellschulung (Bezeichnung, Schulung, Test) beim Arbeiten mit Beispieldokumenten aktivieren. Mithilfe des Barrierefreiheitsmodus können Benutzer mit geringer Anzeigezugriffshilfen leichter auf die Tastatur barrierefrei sein, wenn sie in der Dokumentanzeige navigieren und Elemente mit Bezeichnungen versehen.

Auf diese Weise können Benutzer mithilfe ihrer Tastaturen durch Text in der Dokumentanzeige navigieren und nicht nur die ausgewählten Werte, sondern auch Aktionen (z. B. Bezeichnungen oder Entfernen von Bezeichnungen aus markierten Texten) oder vorhergesagte Bezeichnungswerte hören, während Sie das Modell mit zusätzlichen Beispieldokumenten trainieren. 


![Barrierefreiheitsmodus](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>Anforderungen

Um die Audiowiedergabe der Sprachausgabe zu hören, müssen Sie die [Sprachausgabe-App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in den Sprachausgabeeinstellungen auf Ihrem Windows 10-System aktivieren.

![Sprachausgabe aktivieren](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>Bezeichnung für Tastaturbenutzer

Für Tastaturbenutzer, die den Barrierefreiheitsmodus verwenden, können Sie die folgenden Tasten verwenden, wenn Sie Text in einem Beispieldokument im Viewer beschriften:

- TAB: Verschiebt Sie vorwärts und wählt das nächste Wort aus.
- TAB+ UMSCHALT: Verschiebt Sie nach hinten und wählt das vorherige Wort aus.
- Enter: Label or removes a label from the selected word.
- Vorwärtspfeil: Verschiebt Sie durch einzelne Zeichen in einem ausgewählten Wort vorwärts.
- Abwärtspfeil: Verschiebt Sie in einem ausgewählten Wort rückwärts durch einzelne Zeichen.

> [!NOTE]
> Wenn Sie mehrere Wörter für eine einzelne Bezeichnung beschriften, müssen Sie jedes Wort beschriften.


## <a name="narration"></a>Kommentar

Verwenden Sie für Benutzer der Sprachausgabe, die den Barrierefreiheitsmodus verwenden, dieselbe Tastaturnavigation, die für Tastaturbenutzer beschrieben wird, um das Beispieldokument im Viewer zu durchgehen.

Während Sie durch die Beispieldokumente und Diebeschriftungswerte navigieren, gibt die Sprachausgabe dem Benutzer die folgenden Audioaufforderungen:

- Wenn Sie die Tastatur verwenden, um durch die Dokumentanzeige zu navigieren, wird die ausgewählte Zeichenfolge von Sprachausgabeaudio angezeigt.
- Innerhalb einer ausgewählten Zeichenfolge gibt die Sprachausgabe jedes Zeichen in der Zeichenfolge an, während Sie sie mithilfe des Vorwärts- oder Rückwärtspfeils auswählen.
- Wenn Sie eine Zeichenfolge auswählen, die mit bezeichnungen versehen wurde, gibt die Sprachausgabe den Wert und dann "mit Bezeichnung" an.  Wenn der Bezeichnungswert beispielsweise "Contoso" ist, wird "Costoso mit Bezeichnung" angegeben. 
- Wenn Sie auf der Registerkarte "Schulung" eine Zeichenfolge in der Dokumentanzeige auswählen, die nur vorhergesagt wurde, gibt die Sprachausgabe den Wert und dann "vorhergesagt" an. Dies tritt auf, wenn beim Training ein Wert in der Datei vorherzusagen ist, der nicht mit dem vom Benutzer bezeichneten Wert übereinstimmen kann.
- Wenn Sie auf der Registerkarte "Schulung" eine Zeichenfolge in der Dokumentanzeige auswählen, die mit Bezeichnungen versehen und vorhergesagt wurde, gibt die Sprachausgabe den Wert und dann "mit Bezeichnungen und Vorhersagen" an. Dies tritt auf, wenn die Schulung erfolgreich ist und eine Übereinstimmung zwischen einem vorhergesagten Wert und der Benutzerbezeichnung besteht.



Nachdem eine Zeichenfolge mit einer Bezeichnung versehen oder eine Bezeichnung im Viewer entfernt wurde, warnt die Sprachausgabe Sie, die Änderungen vor dem Beenden zu speichern.

## <a name="see-also"></a>Siehe auch

[Erstellen eines Extraktors](create-an-extractor.md)</br>

[Erstellen einer Klassifizierung](create-a-classifier.md)</br>










 


  
  



