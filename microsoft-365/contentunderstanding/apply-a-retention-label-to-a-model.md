---
title: Anwenden einer Aufbewahrungs Bezeichnung auf ein Dokument grundlegendes Modell
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: In diesem Artikel wird erläutert, wie Sie eine Aufbewahrungs Bezeichnung auf ein Dokument Verständnis Modell anwenden.
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294923"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>Anwenden einer Aufbewahrungs Bezeichnung auf ein Dokument grundlegendes Modell

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Sie können eine [Aufbewahrungs Bezeichnung](https://docs.microsoft.com/microsoft-365/compliance/retention) ganz einfach auf ein Dokument grundlegendes Modell in Microsoft SharePoint Syntex anwenden.

Mit Aufbewahrungs Bezeichnungen können Sie Aufbewahrungseinstellungen auf die Dokumente anwenden, die Ihr Dokument als Verständnis für Modelle identifiziert.  Beispielsweise möchten Sie, dass Ihr Modell nicht nur *Versicherungs* Schutz Dokumente identifiziert, die in Ihre Dokumentbibliothek hochgeladen werden, sondern auch ein Aufbewahrungstags für die *Geschäfts* Aufbewahrung aufwendet, damit diese Dokumente für den angegebenen Zeitraum (beispielsweise die nächsten fünf Monate) nicht aus der Dokumentbibliothek gelöscht werden können.

Sie können eine bereits vorhandene Aufbewahrungs Bezeichnung auf Ihr Dokument Verständnis Modell über Ihre Modelleinstellungen auf der Startseite Ihres Modells anwenden. 

> [!Important]
> Damit Aufbewahrungs Bezeichnungen auf ihr Inhaltsmodell angewendet werden können, müssen Sie [im Microsoft 365 Compliance Center erstellt und veröffentlicht](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)werden.

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>So fügen Sie einem Dokument Understanding Model eine Aufbewahrungs Bezeichnung hinzu

1. Wählen Sie auf der Modell Startseite **Modelleinstellungen**aus.</br>
2. Wählen Sie unter **Modelleinstellungen**im Abschnitt **Sicherheit und Kompatibilität** das Menü **Aufbewahrungs Bezeichnung** aus, um eine Liste der Aufbewahrungs Bezeichnungen anzuzeigen, die für das Modell zur Verfügung stehen.</br>
 ![Menü "Aufbewahrungs Bezeichnung"](../media/content-understanding/retention-labels-menu.png)</br> 
3. Wählen Sie die Aufbewahrungs Bezeichnung aus, die Sie auf das Modell anwenden möchten, und wählen Sie dann **Speichern**aus.</br>

Nachdem Sie die Aufbewahrungs Bezeichnung auf Ihr Modell angewendet haben, können Sie Sie auf eine anwenden:
- Neue Dokumentbibliothek
- Dokumentbibliothek, auf die das Modell bereits angewendet wurde
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Anwenden der Aufbewahrungs Bezeichnung auf eine Dokumentbibliothek, auf die das Modell bereits angewendet wurde

Wenn Ihr Dokument grundlegendes Modell bereits auf eine Dokumentbibliothek angewendet wurde, können Sie die folgenden Schritte ausführen, um das Update für die Aufbewahrungs Bezeichnung zu synchronisieren und es auf die Dokumentbibliothek anzuwenden:</br>

1. Wählen Sie auf der Startseite des Modells im Abschnitt **Bibliotheken mit diesem Modell** die Dokumentbibliothek aus, auf die Sie das Update für die Aufbewahrungs Bezeichnung anwenden möchten. </br> 
2. Wählen Sie **Sync**aus. </br>
 ![Synchronisierungsmodell](../media/content-understanding/sync-model.png)</br> 


Nachdem Sie das Update angewendet und mit Ihrem Modell synchronisiert haben, können Sie bestätigen, dass es angewendet wurde, indem Sie die folgenden Schritte ausführen:

1. Klicken Sie im inhaltscenter im Abschnitt **Bibliotheken mit diesem Modell** auf die Bibliothek, auf die ihr aktualisiertes Modell angewendet wurde. </br>
2. Wählen Sie in der Ansicht Dokumentbibliothek das Informationssymbol aus, um die Modelleigenschaften zu überprüfen.</br>  
3. Wählen Sie in der Liste **aktive Modelle** das aktualisierte Modell aus.</br>
4. Im Abschnitt **Aufbewahrungs Bezeichnung** wird der Name der angewendeten Aufbewahrungs Bezeichnung angezeigt.</br>


Auf der Ansichtsseite Ihres Modells in Ihrer Dokumentbibliothek wird eine neue Spalte für die **Aufbewahrungs Bezeichnung** angezeigt.  Wenn Ihr Modell die Dateien klassifiziert, die es als Zugehörigkeit zum Inhaltstyp identifiziert und in der Bibliotheksansicht auflistet, wird in der Spalte Aufbewahrungs Bezeichnung auch der Name der Aufbewahrungs Bezeichnung angezeigt, die über das Modell auf Sie angewendet wurde.


Beispielsweise wird für alle *Versicherungs* Schutz Dokumente, die Ihr Modell identifiziert, auch die *Geschäfts* Aufbewahrungs Bezeichnung angewendet, wodurch verhindert wird, dass Sie fünf Monate lang aus der Dokumentbibliothek gelöscht werden. Wenn versucht wird, die Datei aus der Dokumentbibliothek zu löschen, wird eine Fehlermeldung angezeigt, die besagt, dass Sie aufgrund der angewendeten Aufbewahrungs Bezeichnung nicht zulässig ist.

## <a name="see-also"></a>Siehe auch
[Erstellen einer Klassifizierung](create-a-classifier.md)</br>
[Erstellen eines Extraktions Moduls](create-an-extractor.md)</br>
[Dokument Verständnis Übersicht](document-understanding-overview.md)</br>
[Erstellen eines Formular Verarbeitungsmodells](create-a-form-processing-model.md)  
