---
title: Anwenden einer Aufbewahrungsbezeichnung auf ein Modell
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
description: In diesem Artikel wird die Anwendung einer Aufbewahrungsbezeichnung auf ein Modell in SharePoint Syntex erläutert.
ms.openlocfilehash: 796130bfa967663b5696f49279154cfe9b16f703
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925368"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a>Anwenden einer Aufbewahrungsbezeichnung auf ein Modell in SharePoint Syntex

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


Sie können auf einfache Weise eine [Aufbewahrungsbezeichnung](../compliance/retention.md) auf ein Modell in Microsoft SharePoint Syntex anwenden. Sie können dies sowohl für Dokumentverständnis- als auch Formularverarbeitungsmodelle tun.

Aufbewahrungsbezeichnungen ermöglichen es Ihnen, Aufbewahrungseinstellungen auf die Dokumente anzuwenden, die von Ihrem Modell identifiziert werden.  Sie könnten beispielsweise wollen, dass Ihr Modell nicht nur sämtliche *Versicherungsbestätigungen* erkennt, die in Ihre Dokumentbibliothek hochgeladen werden, sondern auf diese auch eine *Geschäftlich*-Aufbewahrungsbezeichnung anwendet, damit diese Dokumente für den angegebenen Zeitraum (beispielsweise für die nächsten fünf Monate) nicht gelöscht werden können.

Über die Modelleinstellungen auf der Startseite Ihres Modells können Sie eine bereits vorhandene Aufbewahrungsbezeichnung auf Ihr Modell anwenden. 

> [!Important]
> Damit Aufbewahrungsbezeichnungen für die Anwendung auf Ihre Dokumentverständnismodelle verfügbar sind, müssen sie [im Microsoft 365 Compliance Center erstellt und veröffentlicht werden](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).

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

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a>So fügen Sie einem Formularverarbeitungsmodell eine Aufbewahrungsbezeichnung hinzu

> [!Important]
> Damit Aufbewahrungsbezeichnungen für die Anwendung auf Ihre Formularverarbeitungsmodelle verfügbar sind, müssen sie [im Microsoft 365 Compliance Center erstellt und veröffentlicht werden](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).

Sie können eine Aufbewahrungsbezeichnung entweder auf ein Formularverarbeitungsmodell anwenden, wenn Sie ein Modell erstellen, oder auf ein vorhandenes Modell anwenden.

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a>So fügen Sie eine Aufbewahrungsbezeichnung hinzu, wenn Sie ein Formularverarbeitungsmodell erstellen

1. Wenn Sie ein [Formularverarbeitungsmodell erstellen](./create-a-form-processing-model.md), wählen Sie <b>erweiterte Einstellungen</b> aus.
2. Wählen Sie unter <b>Erweiterte Einstellungen</b> im Abschnitt <b>Aufbewahrungsbezeichnung</b> das Menü aus, und wählen Sie dann die Aufbewahrungsbezeichnung aus, die Sie auf das Modell anwenden möchten.</b>

 
     ![Hinzufügen zu einem neuen Formularverarbeitungsmodell](../media/content-understanding/retention-label-forms.png)</br>

3.  Nachdem Sie die verbleibenden Modelleinstellungen abgeschlossen haben, wählen Sie <b>Erstellen</b> aus, um Ihr Modell zu erstellen.

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a>So fügen Sie einem bestehenden Formularverarbeitungsmodell eine Aufbewahrungsbezeichnung hinzu

Sie können einem bestehenden Formularverarbeitungsmodell auf verschiedene Arten eine Aufbewahrungsbezeichnung hinzufügen:
- Über das Menü „Automatisieren“ in der Dokumentbibliothek
- Über die Einstellungen der Aktiven Modelle in der Dokumentbibliothek 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a>So fügen Sie einem bestehenden Formularverarbeitungsmodell über das Menü „Automatisieren“ eine Aufbewahrungsbezeichnung hinzu

Sie können einem vorhandenen Formularverarbeitungsmodell, das Ihnen gehört, über das Menü „Automatisieren“ in der Dokumentbibliothek, auf die das Modell angewendet wird, eine Aufbewahrungsbezeichnung hinzufügen.


1. Wählen Sie in Ihrer Dokumentbibliothek, auf die das Formularverarbeitungsmodell angewendet wird, das Menü <b>Automatisieren</b>, anschließend <b>KI-Generator</b> und dann <b>Formularverarbeitungsmodelldetails anzeigen</b> aus.

   ![Menü „Automatisieren“](../media/content-understanding/automate-menu.png)</br>

2. Wählen Sie in den Modelldetails im Bereich <b>Aufbewahrungsbezeichnung</b> die Aufbewahrungsbezeichnung aus, die Sie anwenden möchten.  Klicken Sie dann auf <b>Speichern</b>.

     ![Hinzufügen zu einem bestehenden Formularverarbeitungsmodell](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a>So fügen Sie einem bestehenden Formularverarbeitungsmodell in Einstellungen der Aktiven Modelle eine Aufbewahrungsbezeichnung hinzu

Sie können einem vorhandenen Formularverarbeitungsmodell, das Ihnen gehört, über die Einstellungen der Aktiven Modelle in der Dokumentbibliothek, auf die das Modell angewendet wird, eine Aufbewahrungsbezeichnung hinzufügen.

1. Wählen Sie in der SharePoint-Dokumentbibliothek, auf die das Modell angewendet ist, das Symbol <b>Aktive Modelle anzeigen</b> und dann <b>Aktive Modelle anzeigen</b>.</b>

   ![Aktive Modelle anzeigen](../media/content-understanding/info-du.png)</br> 

2. Wählen Sie unter <b>Aktive Modelle</b>das Formularverarbeitungsmodell aus, auf das Sie die Aufbewahrungsbezeichnung anwenden möchten.

     ![Modelldetails](../media/content-understanding/retention-label-model-details.png)</br> 


3. Wählen Sie in den Modelldetails im Bereich <b>Aufbewahrungsbezeichnung</b> die Aufbewahrungsbezeichnung aus, die Sie anwenden möchten.  Klicken Sie dann auf <b>Speichern</b>.

> [!NOTE]
> Sie müssen der Modellbesitzer sein, damit der Bereich für Modelleinstellungen bearbeitet werden kann. 


## <a name="see-also"></a>Siehe auch
[Erstellen einer Klassifizierung](create-a-classifier.md)

[Erstellen eines Extraktors](create-an-extractor.md)

[Übersicht über das Dokumentenverständnis](document-understanding-overview.md)