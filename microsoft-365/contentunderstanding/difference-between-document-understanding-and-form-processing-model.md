---
title: Unterschied zwischen Dokumentverständnis- und Formularverarbeitungsmodellen
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Beschreibung des Unterschieds zwischen Dokumentverständnis- und Formularverarbeitungsmodellen
ms.openlocfilehash: 98d5e9463dedda96c02ed7c3ed80576638941816
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464228"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Unterschied zwischen Dokumentverständnis- und Formularverarbeitungsmodellen 


Das Inhaltsverständnis-Feature in Microsoft SharePoint Syntex ermöglicht es Ihnen, in SharePoint-Dokumentbibliotheken hochgeladene Dokumente zu identifizieren und klassifizieren sowie relevante Informationen aus jeder Datei zu extrahieren.  Wenn Dateien beispielsweise in eine SharePoint-Dokumentbibliothek hochgeladen werden, werden alle Dateien, die als *Aufträge* erkannt werden, als solche klassifiziert und anschließend in einer benutzerdefinierten Dokumentbibliotheksansicht angezeigt. Darüber hinaus können aus jeder Datei bestimmte Informationen (z. B. *Auftragsnummer* und *Gesamtbetrag*) abgerufen und als Spalte in Ihrer Dokumentbibliotheksansicht angezeigt werden. 

Das Inhaltsverständnis-Feature ermöglicht Ihnen das Erstellen von *Modellen*, um die benötigten Informationen zu finden und zu extrahieren. Modelle tragen dazu bei, geschäftliche Probleme bei der Suche, bei Geschäftsprozessen, Compliance und vielem mehr zu lösen.

Es gibt zwei Modelltypen, die Sie verwenden können:

- [Informationen zu Dokumentverständnismodellen](document-understanding-overview.md)
- [Formularverarbeitungsmodelle](form-processing-overview.md)

Beide Modelle werden in der Regel für den gleichen Zweck verwendet, doch die unten aufgeführten wesentlichen Unterschiede bedingen, welches Sie verwenden können.

> [!NOTE]
> Weitere Informationen zu Beispielszenarien für Formularverarbeitung und Dokumentverständnis finden Sie unter [SharePoint Syntex – Leitfaden für die ersten Schritte](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example).


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Strukturierte, unstrukturierte und teilstrukturierte Inhalte

Verwenden Sie Dokumentverständnismodelle, um Daten aus unstrukturierten Dokumenten (z. B. Briefen oder Verträgen) zu identifizieren und zu extrahieren, bei denen sich die Textentitäten, die Sie extrahieren möchten, in Sätzen oder bestimmten Bereichen des Dokuments befinden. So könnte beispielsweise ein unstrukturiertes Dokument ein Vertragsverlängerungsdokument sein, das auf unterschiedliche Weise verfasst sein kann. Allerdings enthält der Text jedes Vertragsverlängerungsdokuments übereinstimmende Informationen, z. B. die Textzeichenfolge *Startdatum Dienst* und dann ein bestimmtes Datum.   

Verwenden Sie Formularverarbeitungsmodelle, um Dateien zu identifizieren und Daten aus strukturierten oder teilstrukturierten Dokumenten wie Formularen oder Rechnungen zu extrahieren. Formularverarbeitungsmodelle werden trainiert, den Aufbau eines Formulars anhand von Beispieldokumenten zu erkennen, und lernen, nach den Daten zu suchen, die aus ähnlichen Orten extrahiert werden sollen, da Formulare einen strukturierten Aufbau aufweisen, in dem sich Entitäten an der selben Stelle befinden (beispielsweise eine Sozialversicherungsnummer in einem Steuerformular). 

> [!NOTE]
> Um ein Dokumentverständnismodell erstellen oder ein solches auf eine SharePoint-Dokumentbibliothek anwenden zu können, benötigen Sie Zugang zu eine Inhaltscenter-Website. 


## <a name="where-they-are-created"></a>Wo die Modelle erstellt werden

Dokumentverständnismodelle werden auf einer SharePoint-Inhaltscenter-Site erstellt und verwaltet. 

> [!NOTE]
> Weitere Informationen zu Eingabedokumenten finden Sie unter [Formularverarbeitungsmodelle – Voraussetzungen und Einschränkungen](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

Formularverarbeitungsmodelle werden in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) erstellt, die Erstellung wird jedoch direkt aus einer SharePoint-Dokumentbibliothek heraus initiiert. Das Erstellen von Formularverarbeitungsmodellen muss in Ihrer Dokumentbibliothek aktiviert sein, damit ein Benutzer ein Formularverarbeitungsmodell dafür erstellen kann. Ein Administrator dies über die Administratoreinstellungen für das Inhaltsverständnis erledigen. Formularverarbeitungsmodelle verwenden PowerAutomate-Abläufe zum Verarbeiten von Dateien, wenn diese in die Dokumentbibliothek hochgeladen werden.

Bei der Erstellung eines Dokumentverständnismodells erstellen Sie einen neuen [SharePoint-Inhaltstyp](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), der im SharePoint-Inhaltstypenkatalog gespeichert wird. Bei Bedarf können Sie auch vorhandene Inhaltstypen verwenden, um das Modell zu definieren.

Formularverarbeitungsmodelle generieren ebenfalls neue [SharePoint-Inhaltstypen](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), die ebenfalls im SharePoint-Inhaltstypkatalog gespeichert werden.

## <a name="where-they-can-be-applied"></a>Wo die Modelle angewendet werden können

Sie können Dokumentverständnismodelle auf SharePoint-Dokumentbibliotheken anwenden, auf die Sie Zugriff haben. Verwenden Sie das Inhaltscenter, um ein Dokumentverständnismodell zu erstellen, und wenden Sie es auf verschiedene Dokumentbibliotheken an. Das Inhaltscenter ermöglicht eine zentralere Kontrolle darüber, wie Dokumentverständnismodelle verwendet und wo sie angewendet werden. Beachten Sie, dass diese Informationen auch bis zu einem Inhaltscenter reichen müssen.

Formularverarbeitungsmodelle können derzeit nur auf die SharePoint-Dokumentbibliothek angewendet werden, über die sie erstellt wurden. Auf diese Weise können lizenzierte Benutzer, die auf die Site zugreifen können, ein Formularverarbeitungsmodell erstellen. Bitte beachten Sie, dass Ihr Administrator die Formularverarbeitung in einer SharePoint-Dokumentbibliothek aktivieren muss, damit sie für lizenzierte Benutzer zur Verfügung steht.

 ## <a name="see-also"></a>Siehe auch
[Schulungen: Verbessern der Geschäftsergebnisse mit AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[Übersicht über das Dokumentenverständnis](document-understanding-overview.md)

[Übersicht über die Formularverarbeitung](form-processing-overview.md)

[Einführung in SharePoint Syntex](index.md)
