---
title: Unterschied zwischen Dokument verstehen und Formular Verarbeitungs Modellen (Vorschau)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Beschreibt den wesentlichen Unterschied zwischen Dokument Verständnis und Formular Verarbeitungs Modellen.
ms.openlocfilehash: ceea3a6e7898d8971ea458222d6164b496fcb8b7
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950060"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a>Unterschied zwischen Dokument verstehen und Formular Verarbeitungs Modellen (Vorschau)

> [!Note] 
> Der Inhalt dieses Artikels ist für Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).

Mit dem Inhalts Verständnis in Project Cortex können Sie Dokumente, die in SharePoint-Dokumentbibliotheken hochgeladen werden, identifizieren und klassifizieren sowie relevante Informationen aus jeder Datei extrahieren.  Wenn beispielsweise Dateien in eine SharePoint-Dokumentbibliothek hochgeladen werden, werden alle Dateien, die als Bestel *Lungen* identifiziert werden, als solche klassifiziert und in einer benutzerdefinierten Dokumentbibliotheksansicht angezeigt, in der Sie angezeigt werden. Darüber hinaus können Sie bestimmte Informationen aus jeder Datei abrufen (beispielsweise *Bestellnummer* und *Summe*) und in einer Spalte in ihrer Dokumentbibliotheksansicht anzeigen. 


Mit dem Inhalts Verständnis können Sie *Modelle* erstellen, um die benötigten Informationen zu identifizieren und zu extrahieren.  Es gibt zwei Arten von Modellen, die verwendet werden können:

- [Dokument verstehen von Modellen](document-understanding-overview.md)
- [Formular Verarbeitungsmodelle](form-processing-overview.md)

Während beide Modelle für gewöhnlich denselben Zweck verwendet werden, gibt es wesentliche Unterschiede, die sich auf die zu verwendende Option auswirken.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Strukturierter Vergleich von unstrukturierten und semi-strukturierten Inhalten

Verwenden Sie Dokument Verständnis Modelle zum Identifizieren und Extrahieren von Daten aus unstrukturierten Dokumenten wie Briefen oder Verträgen, bei denen sich die Text Entitäten, die Sie extrahieren möchten, in Sätzen oder bestimmten Dokumentbereichen befinden. Beispielsweise kann ein unstrukturiertes Dokument ein Vertrags Erneuerungs schreiben sein, das auf unterschiedliche Weise geschrieben werden kann. Es gibt jedoch Informationen, die sich konsistent im Textkörper jedes Vertrags Erneuerungs Dokuments befinden, beispielsweise die Textzeichenfolge "Startdatum des Diensts", gefolgt von einem tatsächlichen Datum.   

Verwenden Sie Formular Verarbeitungsmodelle, um Dateien zu identifizieren und Daten aus strukturierten oder semi-strukturierten Dokumenten wie Formularen oder Rechnungen zu extrahieren, wobei Sie eindeutige Schlüssel/Wert-Paare (beispielsweise *Date: 10/1/2020*) * oder Tabellendaten haben. Als Beispiel wäre ein guter Kandidat für die Formularverarbeitung das Bestellformular eines Unternehmens, in dem die Clients ihre Informationen für bestimmte Felder angeben müssen, die sich im gleichen Bereich des Dokumentlayouts befinden, wie *Name*, *Telefonnummer*, *Gesamtkosten*usw.  Ein Steuerformular ist ein gutes Beispiel für ein strukturiertes Dokument. 

## <a name="where-they-are-created"></a>Wo Sie erstellt werden

Dokument Understanding Models werden in einer SharePoint-inhaltscenter-Website erstellt und verwaltet. Sie müssen Zugriff auf eine inhaltscenter-Website haben, um ein Dokument Verständnis Modell zu erstellen oder eine auf eine SharePoint-Dokumentbibliothek anzuwenden. 

Wenn Sie ein Dokument grundlegendes Modell erstellen, erstellen Sie einen neuen [SharePoint-Inhaltstyp](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) , der im Katalog der SharePoint-Inhaltstypen gespeichert wird. Sie können optional vorhandene Inhaltstypen verwenden, um Ihr Modell bei Bedarf zu definieren.

Formular Verarbeitungsmodelle werden im PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview)erstellt, die Erstellung wird jedoch direkt aus einer SharePoint-Dokumentbibliothek initiiert. Die Erstellung von Formular Verarbeitungs Modellen muss in Ihrer Dokumentbibliothek aktiviert sein, damit ein Benutzer ein Formular Verarbeitungsmodell für diese erstellen kann, und ein Administrator kann dies im Inhalt Understanding admin settings tun. Formular Verarbeitungsmodelle verwenden PowerAutomate-Flows, um Dateien zu verarbeiten, wenn Sie in die Dokumentbibliothek hochgeladen werden.

Formular Verarbeitungsmodelle erstellen auch neue [SharePoint-Inhaltstypen](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), die auch im SharePoint-Inhaltstypen Katalog gespeichert werden.

## <a name="where-they-can-be-applied"></a>Wo Sie angewendet werden können

Dokument Verständnis Modelle können auf verschiedene SharePoint-Dokumentbibliotheken angewendet werden, auf die Sie Zugriff haben. Sie können das inhaltscenter verwenden, um nicht nur ein Dokument grundlegendes Modell zu erstellen, sondern es auch auf verschiedene Dokumentbibliotheken anzuwenden. Das inhaltscenter bietet eine zentralere Kontrolle darüber, wie Dokument Verständnis Modelle verwendet werden und wo Sie angewendet werden, da diese Informationen in ein inhaltscenter aufrollen müssen.

Formular Verarbeitungsmodelle können derzeit nur auf die SharePoint-Dokumentbibliothek angewendet werden, aus der Sie erstellt wurden. Dadurch kann jeder lizenzierte Benutzer, der Zugriff auf die Website hat, ein Formular Verarbeitungsmodell erstellen.




 ## <a name="see-also"></a>Siehe auch
[Schulung: verbessern der Geschäftsleistung mit AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[Erstellen einer Klassifizierung](create-a-classifier.md)</br>
[Erstellen eines Extraktions Moduls](create-an-extractor.md)</br>
[Anwenden eines Dokument Verständnisses für das Modell](apply-a-model.md)</br>
[Erstellen eines Formular Verarbeitungsmodells](create-a-form-processing-model.md)</br>



  
  



