---
title: Verwendungsanalysen von Dokumentverständnismodellen
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
description: 'Informationen zum Anwenden einer Aufbewahrungsbezeichnung auf ein Dokumentverständnismodell '
ms.openlocfilehash: 92115d8b1985fa84cd72671442aca18f255355de
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080442"
---
# <a name="document-understanding-model-usage-analytics"></a>Verwendungsanalysen von Dokumentverständnismodellen

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhX]  

</br>


Im Microsoft SharePoint Syntex-Inhaltscenter finden Sie Modellverwendungsanalysen, um weitere Informationen zur Verwendung von Modellen bereitzustellen, die aus dem Inhaltscenter veröffentlicht wurden. Der Abschnitt des Inhaltscenters <b>Die Leistung Ihrer Modelle in den letzten 30 Tagen</b> umfasst ein 30-tägiges Rollup von Nutzungsanalysedaten, die in den folgenden Diagrammen und Listen bereitgestellt werden:

- Klassifizierung nach Modell
- Klassifizierung nach Bibliothek
- Modellnutzung 

 ![Modellanalyse](../media/content-understanding/model-analytics.png) </br>

### <a name="roll-up-of-model-usage-data-in-the-default-content-center"></a>Rollup von Modellnutzungsdaten im Standardinhaltscenter

In SharePoint Syntex wird das Standardinhaltscenter während des Setups erstellt. Bei Bedarf können auch zusätzliche Inhaltscenter erstellt werden. So können Abteilungen beispielsweise eigene Inhaltscenter erstellen, um ihre Modelle zu erstellen und zu verwalten. 

Im Hinblick auf Modellnutzungsanalysen beachten Sie:

- Ihr Standardinhaltscenter zeigt Modellnutzungsanalysen für alle Inhaltscenter und Modelle in Ihrer Organisation an, einschließlich der in zusätzlichen Inhaltscentern erstellten. Damit erhalten Inhaltsmanager und andere Projektbeteiligten ein zentrales Portal, um die Inhaltscenter und Modelle im gesamten Unternehmen zu verwalten und zu überwachen.  
- Andere Inhaltscenter zeigen nur Modellnutzungsanalysen für die Modelle an, die in ihnen erstellt wurden. Damit erhalten Inhaltsmanager nur Einblicke in die Verwendungsdaten für die Modelle, mit denen sie befasst sind.


## <a name="classification-by-model"></a>Klassifizierung nach Modell

   ![Prozentsatz des Gesamtmodells](../media/content-understanding/total-model-percentage.png) </br>

Im Kreisdiagramm **Klassifizierung nach Modell** wird angezeigt, welche Modelle die meisten Dateien klassifiziert haben. Es zeigt jedes veröffentlichte Modell als Prozentsatz der Gesamtzahl der Dateien an, die von allen veröffentlichten Modellen im Inhaltscenter verarbeitet wurden.

Außerdem zeigt jedes Modell die **Vollständigkeitsrate** an, der Prozentsatz der hochgeladenen Dateien, die vom Modell erfolgreich analysiert wurden. Eine niedrige Vollständigkeitsrate kann bedeuten, dass es Probleme mit dem Modell oder den zu analysierenden Dateien gibt.

## <a name="classification-by-library"></a>Klassifizierung nach Bibliothek

   ![Verarbeitete Dateien](../media/content-understanding/files-processed-over-time.png) </br>

Das Balkendiagramm **Klassifizierung nach Bibliothek** hilft Ihnen, die Effektivität des Inhaltsverständnisses in Ihrer Organisation zu bestimmen.  Es zeigt nicht nur die Anzahl der Dateien an, die mit der Zeit für jedes Modell verarbeitet wurden, sondern es zeigt durch Auswahl einer Spalte im Diagramm auch die Dokumentbibliotheken, auf die das Modell angewendet wurde.


## <a name="model-usage"></a>Modellnutzung

Die Liste „Modellnutzung“ zeigt Nutzungsanalysen für die Modelle an, die über das Inhaltscenter erstellt wurden.  

> [!NOTE]
> Wenn Sie sich im Standardinhaltscenter befinden und in Ihrer Organisation über weitere Inhaltscenter verfügen, wird die Modellnutzungsliste nach Inhaltscenter gruppiert.

Jedes Modell in der Modellnutzungsliste zeigt die Verwendungsdaten an:

- Anzahl der klassifizierten Elemente: Anzahl der vom Modell verarbeiteten Dateien.
- Durchschnittliche Konfidenzbewertung: Durchschnittliche Genauigkeitsbewertung des Modells, wenn es gegen Dateien ausgeführt wird.
- URL der Zielliste: Die SharePoint-Dokumentbibliothek, auf die das Modell angewendet wurde.



## <a name="see-also"></a>Siehe auch
[Erstellen einer Klassifizierung](create-a-classifier.md)

[Erstellen eines Extraktors](create-an-extractor.md)

[Übersicht über das Dokumentenverständnis](document-understanding-overview.md)

[Erstellen eines Formularverarbeitungsmodells](create-a-form-processing-model.md)  
