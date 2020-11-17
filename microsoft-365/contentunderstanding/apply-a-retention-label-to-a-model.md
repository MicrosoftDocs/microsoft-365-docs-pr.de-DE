---
title: Anwenden einer Aufbewahrungsbezeichnung auf ein Dokumentverständnismodell
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: In diesem Artikel wird die Anwendung einer Aufbewahrungsbezeichnung auf ein Dokumentverständnismodell erläutert.
ms.openlocfilehash: 2e6d300b63a173d01488406485cffa44fab4278e
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087475"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>Anwenden einer Aufbewahrungsbezeichnung auf ein Dokumentverständnismodell

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


Sie können auf einfache Weise eine [Aufbewahrungsbezeichnung](https://docs.microsoft.com/microsoft-365/compliance/retention) auf ein Dokumentverständnismodell in Microsoft SharePoint Syntex anwenden.

Aufbewahrungsbezeichnungen ermöglichen es Ihnen, Aufbewahrungseinstellungen auf die Dokumente anzuwenden, die von Ihrem Dokumentverständnismodell identifiziert werden.  Sie könnten beispielsweise wollen, dass Ihr Modell nicht nur sämtliche *Versicherungsbestätigungen* erkennt, die in Ihre Dokumentbibliothek hochgeladen werden, sondern auf diese auch eine *Geschäftlich*-Aufbewahrungsbezeichnung anwendet, damit diese Dokumente für den angegebenen Zeitraum (beispielsweise für die nächsten fünf Monate) nicht gelöscht werden können.

Über die Modelleinstellungen auf der Startseite Ihres Modells können Sie eine bereits vorhandene Aufbewahrungsbezeichnung auf Ihr Dokumentverständnismodell anwenden. 

> [!Important]
> Damit Aufbewahrungsbezeichnungen für die Anwendung auf Ihre Inhaltsverständnismodelle verfügbar sind, müssen sie [im Microsoft 365 Compliance Center erstellt und veröffentlicht werden](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>So fügen Sie einem Dokumentverständnismodell eine Aufbewahrungsbezeichnung hinzu

1. Wählen Sie auf der Modell-Startseite **Modelleinstellungen** aus.</br>
2. Wählen Sie in den **Modelleinstellungen** im Abschnitt **Sicherheit und Compliance** das Menü **Aufbewahrungsbezeichnung** aus, um eine Liste der Aufbewahrungsbezeichnungen anzuzeigen, die auf das Modell angewendet werden können.</br>
 ![Menü "Aufbewahrungsbezeichnung"](../media/content-understanding/retention-labels-menu.png)</br> 
3. Wählen Sie die Aufbewahrungsbezeichnung aus, die auf das Modell angewendet werden soll, und wählen Sie **Speichern** aus.</br>

Nachdem Sie die Aufbewahrungsbezeichnung auf das Modell angewendet haben, kann sie auf Folgendes angewendet werden:
- Neue Dokumentbibliothek
- Dokumentbibliothek, auf die das Modell bereits angewendet wird
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Anwenden der Aufbewahrungsbezeichnung auf eine Dokumentbibliothek, auf die das Modell bereits angewendet wird

Wenn Ihr Dokumentverständnismodell bereits auf eine Dokumentbibliothek angewendet wurde, können Sie die folgenden Schritte ausführen, um das Aufbewahrungsbezeichnungsupdate mit Ihrem Modell zu synchronisieren, so dass es auf Ihre Dokumentbibliothek angewendet wird:</br>

1. Wählen Sie auf der Startseite Ihres Modells im Abschnitt **Bibliotheken mit diesem Modell** die Dokumentbibliothek aus, auf die das Aufbewahrungsbezeichnungsupdate angewendet werden soll. </br> 
2. Wählen Sie **Synchronisieren** aus. </br>
 ![Synchronisierungsmodell](../media/content-understanding/sync-model.png)</br> 


Nachdem das Update angewendet und mit Ihrem Modell synchronisiert wurde, können Sie folgendermaßen vorgehen, um zu überprüfen, ob es angewendet wurde:

1. Klicken Sie im Inhaltscenter im Abschnitt **Bibliotheken mit diesem Modell** auf die Bibliothek, auf die das aktualisierte Modell angewendet wurde. </br>
2. Wählen Sie in der Dokumentbibliotheksansicht das Symbol "Informationen" aus, um die Modelleigenschaften zu überprüfen.</br>  
3. Wählen Sie in der Liste **Aktive Modelle** das aktualisierte Modell aus.</br>
4. Im Abschnitt **Aufbewahrungsbezeichnung** wird der Name der angewendeten Aufbewahrungsbezeichnung angezeigt.</br>


Auf der Ansichtsseite Ihres Modells in Ihrer Dokumentbibliothek wird eine neue Spalte **Aufbewahrungsbezeichnung** angezeigt.  Wenn Ihr Modell ermittelte Dateien als seinem Inhaltstyp zugeordnet klassifiziert und sie in der Bibliotheksansicht auflistet, wird in der Spalte "Aufbewahrungsbezeichnung" auch der Name der Aufbewahrungsbezeichnung angezeigt, das auf sie über das Modell angewendet wurde.


So wird beispielsweise auf alle *Versicherungsbestätigungen*, die von Ihrem Modell identifiziert wurden, auch die *Geschäftlich*-Aufbewahrungsbezeichnung angewendet, wodurch sie für fünf Monate nicht aus der Dokumentbibliothek gelöscht werden können. Wenn versucht wird, eine solche Datei aus der Dokumentbibliothek zu löschen, wird eine Fehlermeldung angezeigt mit dem Hinweis, dass dies aufgrund der angewendeten Aufbewahrungsbezeichnung nicht zulässig ist.

## <a name="see-also"></a>Siehe auch
[Erstellen einer Klassifizierung](create-a-classifier.md)

[Erstellen eines Extraktors](create-an-extractor.md)

[Übersicht über das Dokumentenverständnis](document-understanding-overview.md)


