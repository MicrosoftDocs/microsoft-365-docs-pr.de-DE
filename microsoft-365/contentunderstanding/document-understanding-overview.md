---
title: Dokument Verständnis Übersicht (Vorschau)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Erhalten Sie einen Überblick über das Dokument Verständnis in Project Cortex.
ms.openlocfilehash: 13b0aa3742c6cf1c0c1123996c683d13c6577876
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537135"
---
# <a name="document-understanding-overview-preview"></a>Dokument Verständnis Übersicht (Vorschau)
> [!Note] 
> Project Cortex befindet sich derzeit in der Vorschau. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Document Understanding verwendet AI-Modelle, um die Klassifizierung von Dateien und das Extrahieren von Informationen zu automatisieren. Es funktioniert am besten mit unstrukturierten Dokumenten wie Buchstaben oder Verträgen. Die Dokumente sollten Text enthalten, der anhand von Ausdrücken oder Mustern identifiziert werden kann. Der identifizierte Text kann sowohl den Typ der Datei (seine Klassifizierung) als auch die Inhalte bestimmen, die extrahiert werden sollen (Extraktoren).

Dokument Understanding Models werden in einer SharePoint-Website mit dem Namen "inhaltscenter" erstellt und verwaltet. Bei Anwendung auf eine SharePoint-Dokumentbibliothek wird das Modell einem Inhaltstyp zugeordnet, der Spalten zum Speichern der extrahierten Informationen enthält. Der Inhaltstyp, den Sie erstellen, wird im Inhaltstypen Katalog von SharePoint gespeichert. Sie können auch vorhandene Inhaltstypen verwenden, um Ihr Schema zu verwenden.

Sie können Ihrem Dokument *Klassifizierungen* und *Extraktions* Module hinzufügen, die die folgenden Schritte verstehen: 

- Klassifizierungen werden verwendet, um Dokumente zu identifizieren und zu klassifizieren, die in die Dokumentbibliothek hochgeladen werden. Beispielsweise kann eine Klassifizierung "geschult" werden, um alle *Vertrags Erneuerungs* Dokumente zu identifizieren, die in die Bibliothek hochgeladen werden. Der Inhaltstyp "Vertragserneuerung" wird von Ihnen beim Erstellen ihrer Klassifizierung definiert.

- Extraktions Module ziehen Informationen aus diesen Dokumenten. Beispielsweise werden für alle Vertrags Erneuerungs Dokumente, die in Ihrer Dokumentbibliothek identifiziert werden, in ihrer Ansicht Spalten angezeigt, in denen auch das *Start Datum* und der *Client* des Diensts für jedes Vertrags Erneuerungs Dokument angezeigt wird. 

Sie verwenden Beispieldateien, um Ihre Klassifizierungen und Extraktoren in Ihrem Modell zu trainieren und zu testen. Beispieldateien bieten ihre Modellbeispiele, wonach Sie suchen müssen, wenn Sie versuchen, Daten aus Dateien zu identifizieren und daraus zu extrahieren. Sie möchten beispielsweise Ihre Klassifizierungen und Extraktoren für die Vertragserneuerung mit Beispielen von Vertrags Erneuerungs Dokumenten trainieren, mit denen Ihr Unternehmen zusammenarbeitet. Sie können auch Beispieldateien verwenden, um die Effektivität Ihres Modells zu testen.

Verwenden Sie nach der Veröffentlichung Ihres Modells das inhaltscenter, um es auf eine beliebige SharePoint-Dokumentbibliothek anzuwenden, auf die Sie Zugriff haben.  


## <a name="see-also"></a>Siehe auch
[Erstellen einer Klassifizierung](create-a-classifier.md)</br>
[Erstellen eines Extraktions Moduls](create-an-extractor.md)</br>
[Erstellen eines inhaltscenters](create-a-content-center.md) 
 [Erstellen eines Formular Verarbeitungsmodells](create-a-form-processing-model.md)</br>
[Anwenden eines Modells](apply-a-model.md)   
[Unterschied zwischen einem Dokument Verständnis und einem Formular Verarbeitungsmodell](difference-between-document-understanding-and-form-processing-model.md)  
[Übersicht über die Formularverarbeitung](form-processing-overview.md)




