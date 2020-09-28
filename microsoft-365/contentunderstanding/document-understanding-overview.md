---
title: Dokument Verständnis Übersicht
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Erhalten Sie einen Überblick über das Dokument Verständnis in Microsoft SharePoint Syntex.
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294760"
---
# <a name="document-understanding-overview"></a>Dokument Verständnis Übersicht


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Document Understanding verwendet künstliche Intelligenz Modelle (AI), um die Klassifizierung von Dateien und die Extraktion von Informationen zu automatisieren. Es funktioniert am besten mit unstrukturierten Dokumenten wie Briefen oder Verträgen. Diese Dokumente müssen Text enthalten, der auf der Grundlage von Ausdrücken oder Mustern identifiziert werden kann. Der identifizierte Text bestimmt sowohl den Typ der Datei (seine Klassifizierung) als auch die Inhalte, die extrahiert werden sollen (Extraktionsprogramme).

Dokument Understanding Models werden in einer SharePoint-Website mit dem Namen " *inhaltscenter*" erstellt und verwaltet. Bei Anwendung auf eine SharePoint-Dokumentbibliothek wird das Modell einem Inhaltstyp zugeordnet hat Spalten zum Speichern der extrahierten Informationen. Der Inhaltstyp, den Sie erstellen, wird im Inhaltstypen Katalog von SharePoint gespeichert. Sie können auch die Verwendung vorhandener Inhaltstypen für die Verwendung Ihres Schemas auswählen.

Hinzufügen von *Klassifizierungen* und *Extraktionen* zu Ihrem Dokument Understanding Models to do the folgenden: 

- Klassifizierungen werden verwendet, um Dokumente zu identifizieren und zu klassifizieren, die in die Dokumentbibliothek hochgeladen werden. Beispielsweise kann eine Klassifizierung "geschult" werden, um alle *Vertrags Erneuerungs* Dokumente zu identifizieren, die in die Bibliothek hochgeladen werden. Der Inhaltstyp "Vertragserneuerung" wird von Ihnen beim Erstellen ihrer Klassifizierung definiert.

- Extraktions Module ziehen Informationen aus diesen Dokumenten. Beispielsweise werden für alle in Ihrer Dokumentbibliothek identifizierten Vertrags Erneuerungs Dokumente in der Ansicht Spalten angezeigt, die auch den *Start Termin* und den  *Client* des Diensts für jedes Vertrags Erneuerungs Dokument anzeigen. 

Mithilfe von Beispieldateien können Sie Ihre Klassifizierungen und Extraktoren in Ihrem Modell trainieren und testen. Beispieldateien bieten ihre Modellbeispiele, wonach Sie suchen müssen, wenn Sie versuchen, Daten aus Dateien zu identifizieren und daraus zu extrahieren. Sie möchten beispielsweise Ihre Klassifizierungen und Extraktionsprogramme für die Vertragserneuerung mit Beispielen von Vertrags Erneuerungs Dokumenten trainieren, mit denen Ihr Unternehmen zusammenarbeitet. Sie können auch Beispieldateien verwenden, um die Effektivität Ihres Modells zu testen.

Verwenden Sie nach der Veröffentlichung Ihres Modells das inhaltscenter, um es auf eine beliebige SharePoint-Dokumentbibliothek anzuwenden, auf die Sie Zugriff haben.  


## <a name="see-also"></a>Siehe auch
[Erstellen einer Klassifizierung](create-a-classifier.md)</br>
[Erstellen eines Extraktions Moduls](create-an-extractor.md)</br>
[Erstellen eines inhaltscenters](create-a-content-center.md) 
 [Erstellen eines Formular Verarbeitungsmodells](create-a-form-processing-model.md)</br>
[Anwenden eines Modells](apply-a-model.md)   
[Unterschied zwischen einem Dokument Verständnis und einem Formular Verarbeitungsmodell](difference-between-document-understanding-and-form-processing-model.md)  
[Übersicht über die Formularverarbeitung](form-processing-overview.md)
