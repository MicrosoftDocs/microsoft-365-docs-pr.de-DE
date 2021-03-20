---
title: Übersicht über das Dokumentenverständnis
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
description: Hier erhalten Sie einen Überblick über das Dokumentverständnis-Feature in Microsoft SharePoint Syntex.
ms.openlocfilehash: e3b239260953837f70663bb6f7e2dba1676c49eb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911198"
---
# <a name="document-understanding-overview"></a>Übersicht über das Dokumentenverständnis


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Das Dokumentverständnis-Feature verwendet KI-Modelle (künstliche Intelligenz), um die Klassifizierung von Dateien und das Extrahieren von Informationen zu automatisieren. Es eignet sich am besten für unstrukturierte Dokumente, z. B. Briefe oder Verträge. Diese Dokumente müssen Text enthalten, der anhand von Phrasen oder Mustern erkannt werden kann. Der erkannte Text bestimmt sowohl den Dateityp (seine Klassifizierung) als auch das, was extrahiert werden soll (die Extraktoren).

> [!NOTE]
> Weitere Informationen zu Beispielszenarien für das Dokumentverständnis finden Sie unter [SharePoint Syntex – Leitfaden für die ersten Schritte](./adoption-getstarted.md#document-understanding-scenario-example).

Dokumentverständnismodelle werden auf einer Art von SharePoint-Site namens *Inhaltscenter* erstellt und verwaltet. Ein auf eine SharePoint-Dokumentbibliothek angewendetes Modell ist mit einem Inhaltstyp verknüpft und enthält Spalten zum Speichern der extrahierten Informationen. Der von Ihnen erstellte Inhaltstyp wird im SharePoint-Inhaltstypkatalog gespeichert. Sie können auch vorhandene Inhaltstypen verwenden, um deren Schema zu verwenden.

> [!NOTE]
> Schreibgeschützte oder versiegelte Inhaltstypen können nicht aktualisiert und somit nicht in einem Modell verwendet werden.

Sie können Ihren Dokumentverständnismodellen *Klassifizierungen* und *Extraktoren* für folgende Zwecke hinzufügen: 

- Klassifizierungen werden verwendet, um Dokumente zu identifizieren und zu klassifizieren, die in die Dokumentbibliothek hochgeladen werden. So kann beispielsweise eine Klassifizierung "trainiert" werden, alle *Vertragsverlängerungsdokumente* zu erkennen, die in die Bibliothek hochgeladen werden. Der Inhaltstyp der Vertragsverlängerung wird von Ihnen bei der Erstellung der Klassifizierung definiert.

- Extraktoren rufen Informationen aus diesen Dokumenten ab. Beispielsweise werden in Ihrer Ansicht für alle Vertragsverlängerungsdokumente, die in der Dokumentbibliothek erkannt wurden, Spalten angezeigt, die auch das *Dienst-Startdatum* und den *Kunden* für das jeweilige Vertragsverlängerungsdokument enthalten. 

Sie können Beispieldateien verwenden, um Ihre Klassifizierungen und Extraktoren im Modell zu trainieren und zu testen. Beispieldateien liefern Ihrem Modell Beispiele für das, wonach gesucht werden soll, wenn nach zu extrahierenden Daten in Dateien gesucht wird. So würden Sie beispielsweise Ihre Klassifizierungen und Extraktoren für Vertragsverlängerungen mit Beispielen für Vertragsverlängerungsdokumente trainieren, die in Ihrem Unternehmen verwendet werden. Sie können Beispieldateien auch dazu verwenden, die Effektivität Ihres Modells zu testen.

Nach dessen Veröffentlichung können Sie das Modell über das Inhaltscenter auf eine beliebige SharePoint-Dokumentbibliothek anwenden, auf die Sie Zugriff haben.  

### <a name="file-limitations"></a>Dateieinschränkungen

Dokumentverständnismodelle nutzen die Technik der optischen Zeichenerkennung (OCR), um PDF-, Bild- und TIFF-Dateien zu scannen, und zwar sowohl beim Trainieren eines Modells mit Beispieldateien als auch beim Ausführen des Modells mit Dateien einer Dokumentbibliothek.

Beachten Sie bitte die folgenden Unterschiede zwischen textbasierten Microsoft Office-Dateien und mit OCR gescannten Dateien (PDF, Bild oder TIFF):

- Office-Dateien: Bei einer Länge von 64K Zeichen werden diese abgeschnitten (beim Training und beim Ausführen mit Dateien einer Dokumentbibliothek)
- Mit OCR gescannte Dateien: Es besteht Limit von 20 Seiten.  

#### <a name="supported-file-types"></a>Unterstützte Dateitypen

Dokumentverständnismodelle unterstützen die folgenden Dateitypen:

- DOC
- DOCX
- EML
- HEIC
- HEIF
- HTM
- HTML
- JPEG
- JPG
- MARKDOWN
- MD
- MSG
- PDF
- PNG
- PPT
- PPTX
- RTF
- TIF
- TIFF
- TXT
- XLS
- XLSX



## <a name="see-also"></a>Siehe auch
[Erstellen einer Klassifizierung](create-a-classifier.md)

[Erstellen eines Extraktors](create-an-extractor.md)

[Erstellen eines Inhaltscenters](create-a-content-center.md)

[Erstellen eines Formularverarbeitungsmodells](create-a-form-processing-model.md)

[Anwenden eines Modells](apply-a-model.md)   

[Unterschied zwischen Dokumentverständnis- und Formularverarbeitungsmodellen](difference-between-document-understanding-and-form-processing-model.md)
  
[Übersicht über die Formularverarbeitung](form-processing-overview.md)

[Barrierefreiheitsmodus für SharePoint Syntex](accessibility-mode.md)