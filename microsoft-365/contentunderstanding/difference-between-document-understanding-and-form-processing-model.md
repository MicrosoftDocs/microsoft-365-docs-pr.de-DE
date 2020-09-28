---
title: Unterschied zwischen Dokument verstehen und Formular Verarbeitungs Modellen
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Beschreibung des Haupt Unterschieds zwischen Dokument Verständnis und Formular Verarbeitungs Modellen
ms.openlocfilehash: 268a2fa4a0381e5822c17e5df22566c931d37f3c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294748"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Unterschied zwischen Dokument verstehen und Formular Verarbeitungs Modellen 

Der Inhalt in diesem Artikel ist für die Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).

Mit dem Inhalts Verständnis in Project Cortex können Sie Dokumente, die in SharePoint-Dokumentbibliotheken hochgeladen werden, identifizieren und klassifizieren sowie relevante Informationen aus jeder Datei extrahieren.  Wenn beispielsweise Dateien in eine SharePoint-Dokumentbibliothek hochgeladen werden, werden alle Dateien, die als Bestel *Lungen* identifiziert werden, als solche klassifiziert und dann in einer benutzerdefinierten Dokumentbibliotheksansicht angezeigt. Darüber hinaus können Sie bestimmte Informationen aus jeder Datei abrufen (beispielsweise *Bestellnummer* und *Gesamtsumme*) und als Spalte in ihrer Dokumentbibliotheksansicht anzeigen. 

Mit dem Inhalts Verständnis können Sie *Modelle* erstellen, um die benötigten Informationen zu identifizieren und zu extrahieren. Hierbei handelt es sich um zwei Modelltypen, die Sie verwenden können:

- [Dokument verstehen von Modellen](document-understanding-overview.md)
- [Formular Verarbeitungsmodelle](form-processing-overview.md)

Während beide Modelle im Allgemeinen für denselben Zweck verwendet werden, wirken sich die unten aufgelisteten Hauptunterschiede darauf aus, welche Sie verwenden können.

## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Strukturierter Vergleich von unstrukturierten und semi-strukturierten Inhalten

Verwenden Sie Dokument Verständnis Modelle zum Identifizieren und Extrahieren von Daten aus unstrukturierten Dokumenten wie Briefen oder Verträgen, bei denen sich die Text Entitäten, die Sie extrahieren möchten, in Sätzen oder bestimmten Dokumentbereichen befinden. Beispielsweise kann ein unstrukturiertes Dokument ein Vertrags Erneuerungs schreiben sein, das auf unterschiedliche Weise geschrieben werden kann. Die Informationen sind jedoch konsistent im Textkörper jedes Vertrags Erneuerungs Dokuments vorhanden, beispielsweise in der Textzeichenfolge "Startdatum des Diensts", gefolgt von einem tatsächlichen Datum.   

Verwenden Sie Formular Verarbeitungsmodelle, um Dateien zu identifizieren und Daten aus strukturierten oder semi-strukturierten Dokumenten wie Formularen oder Rechnungen zu extrahieren. Diese Dokumente müssen eindeutige Schlüssel/Wert-Paare aufweisen (beispielsweise *Date: 10/1/2020*) * oder Tabellendaten. Ein guter Kandidat für die Formularverarbeitung ist beispielsweise das Bestellformular eines Unternehmens, mit dem die Clients Informationen für bestimmte Felder bereitstellen müssen, die sich im gleichen Bereich des Dokumentlayouts befinden, beispielsweise *Name*, *Telefonnummer*, *Gesamtkosten*usw.  Ein Steuerformular ist ein gutes Beispiel für ein strukturiertes Dokument. 

## <a name="where-they-are-created"></a>Wo Sie erstellt werden

Dokument Understanding Models werden in einer SharePoint-inhaltscenter-Website erstellt und verwaltet. 

> [!NOTE]
> Sie müssen Zugriff auf eine inhaltscenter-Website haben, um ein Dokument Verständnis Modell zu erstellen oder eine auf eine SharePoint-Dokumentbibliothek anzuwenden. 

Formular Verarbeitungsmodelle werden im PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview)erstellt, die Erstellung wird jedoch direkt aus einer SharePoint-Dokumentbibliothek initiiert. Die Erstellung von Formular Verarbeitungs Modellen muss in Ihrer Dokumentbibliothek aktiviert sein, damit ein Benutzer ein Formular Verarbeitungsmodell für diese erstellen kann, und ein Administrator kann dies im Inhalt Understanding admin settings tun. Formular Verarbeitungsmodelle verwenden PowerAutomate-Flows, um Dateien zu verarbeiten, wenn Sie in die Dokumentbibliothek hochgeladen werden.

Wenn Sie ein Dokument grundlegendes Modell erstellen, erstellen Sie einen neuen [SharePoint-Inhaltstyp](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) , der im Katalog der SharePoint-Inhaltstypen gespeichert wird. Sie können auch vorhandene Inhaltstypen verwenden, um Ihr Modell bei Bedarf zu definieren.

Formular Verarbeitungsmodelle werden im PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview)erstellt, die Erstellung wird jedoch direkt aus einer SharePoint-Dokumentbibliothek initiiert. Die Erstellung von Formular Verarbeitungs Modellen muss in Ihrer Dokumentbibliothek aktiviert sein, damit ein Benutzer ein Formular Verarbeitungsmodell dafür erstellen kann. Oder ein Administrator kann dies im Inhalt Understanding admin settings tun. Formular Verarbeitungsmodelle verwenden PowerAutomate-Flows, um Dateien zu verarbeiten, wenn Sie in die Dokumentbibliothek hochgeladen werden.

Formular Verarbeitungsmodelle erstellen auch neue [SharePoint-Inhaltstypen](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)und werden auch im SharePoint-Inhaltstypen Katalog gespeichert.

## <a name="where-they-can-be-applied"></a>Wo Sie angewendet werden können

Sie können Dokument Verständnis Modelle auf SharePoint-Dokumentbibliotheken anwenden, auf die Sie Zugriff haben. Verwenden Sie das inhaltscenter, um ein Dokument grundlegendes Modell zu erstellen und es auf verschiedene Dokumentbibliotheken anzuwenden. Das inhaltscenter bietet Ihnen eine zentralere Kontrolle darüber, wie Dokument Verständnis Modelle verwendet werden und wo Sie angewendet werden. Hinweis Diese Informationen müssen auch in einem inhaltscenter aufrollen.

Formular Verarbeitungsmodelle können derzeit nur auf die SharePoint-Dokumentbibliothek angewendet werden, aus der Sie Sie erstellt haben. Auf diese Weise können lizenzierte Benutzer mit Zugriff auf die Website ein Formular Verarbeitungsmodell erstellen.

 ## <a name="see-also"></a>Siehe auch
[Schulung: verbessern der Geschäftsleistung mit AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[Erstellen einer Klassifizierung](create-a-classifier.md)</br>
[Erstellen eines Extraktions Moduls](create-an-extractor.md)</br>
[Anwenden eines Dokument Verständnisses für das Modell](apply-a-model.md)</br>
[Erstellen eines Formular Verarbeitungsmodells](create-a-form-processing-model.md)</br>
