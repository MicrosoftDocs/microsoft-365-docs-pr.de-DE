---
title: Übersicht über das Dokumentenverständnis
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Hier erhalten Sie einen Überblick über das Dokumentverständnis-Feature in Microsoft SharePoint Syntex.
ms.openlocfilehash: 1265dfa06db323e23d63a044a1a95a6b67c525cf
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333558"
---
# <a name="document-understanding-overview"></a>Übersicht über das Dokumentenverständnis


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Das Dokumentverständnis-Feature verwendet KI-Modelle (künstliche Intelligenz), um die Klassifizierung von Dateien und das Extrahieren von Informationen zu automatisieren. Es eignet sich am besten für unstrukturierte Dokumente, z. B. Briefe oder Verträge. Diese Dokumente müssen Text enthalten, der anhand von Phrasen oder Mustern erkannt werden kann. Der erkannte Text bestimmt sowohl den Dateityp (seine Klassifizierung) als auch das, was extrahiert werden soll (die Extraktoren).

> [!NOTE]
> Weitere Informationen zu Beispielszenarien für das Dokumentverständnis finden Sie unter [SharePoint Syntex – Leitfaden für die ersten Schritte](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example).

Dokumentverständnismodelle werden auf einer Art von SharePoint-Site namens *Inhaltscenter* erstellt und verwaltet. Ein auf eine SharePoint-Dokumentbibliothek angewendetes Modell ist mit einem Inhaltstyp verknüpft und enthält Spalten zum Speichern der extrahierten Informationen. Der von Ihnen erstellte Inhaltstyp wird im SharePoint-Inhaltstypkatalog gespeichert. Sie können auch vorhandene Inhaltstypen verwenden, um deren Schema zu verwenden.

Sie können Ihren Dokumentverständnismodellen *Klassifizierungen* und *Extraktoren* für folgende Zwecke hinzufügen: 

- Klassifizierungen werden verwendet, um Dokumente zu identifizieren und zu klassifizieren, die in die Dokumentbibliothek hochgeladen werden. So kann beispielsweise eine Klassifizierung "trainiert" werden, alle *Vertragsverlängerungsdokumente* zu erkennen, die in die Bibliothek hochgeladen werden. Der Inhaltstyp der Vertragsverlängerung wird von Ihnen bei der Erstellung der Klassifizierung definiert.

- Extraktoren rufen Informationen aus diesen Dokumenten ab. Beispielsweise werden in Ihrer Ansicht für alle Vertragsverlängerungsdokumente, die in der Dokumentbibliothek erkannt wurden, Spalten angezeigt, die auch das *Dienst-Startdatum* und den *Kunden* für das jeweilige Vertragsverlängerungsdokument enthalten. 

Sie können Beispieldateien verwenden, um Ihre Klassifizierungen und Extraktoren im Modell zu trainieren und zu testen. Beispieldateien liefern Ihrem Modell Beispiele für das, wonach gesucht werden soll, wenn nach zu extrahierenden Daten in Dateien gesucht wird. So würden Sie beispielsweise Ihre Klassifizierungen und Extraktoren für Vertragsverlängerungen mit Beispielen für Vertragsverlängerungsdokumente trainieren, die in Ihrem Unternehmen verwendet werden. Sie können Beispieldateien auch dazu verwenden, die Effektivität Ihres Modells zu testen.

Nach dessen Veröffentlichung können Sie das Modell über das Inhaltscenter auf eine beliebige SharePoint-Dokumentbibliothek anwenden, auf die Sie Zugriff haben.  



## <a name="see-also"></a>Siehe auch
[Erstellen einer Klassifizierung](create-a-classifier.md)

[Erstellen eines Extraktors](create-an-extractor.md)

[Erstellen eines Inhaltscenters](create-a-content-center.md)

[Erstellen eines Formularverarbeitungsmodells](create-a-form-processing-model.md)

[Anwenden eines Modells](apply-a-model.md)   

[Unterschied zwischen Dokumentverständnis- und Formularverarbeitungsmodellen](difference-between-document-understanding-and-form-processing-model.md)
  
[Übersicht über die Formularverarbeitung](form-processing-overview.md)
