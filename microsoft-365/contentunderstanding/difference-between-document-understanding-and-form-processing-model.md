---
title: Unterschied zwischen Dokumentverständnis- und Formularverarbeitungsmodellen
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
description: Beschreibung des Unterschieds zwischen Dokumentverständnis- und Formularverarbeitungsmodellen
ms.openlocfilehash: a50941ec117480be586ba828e7b49c4a88a310ab
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712294"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Unterschied zwischen Dokumentverständnis- und Formularverarbeitungsmodellen 


Das Inhaltsverständnis-Feature (Content Understanding) in Microsoft SharePoint Syntex ermöglicht es Ihnen, in SharePoint-Dokumentbibliotheken hochgeladene Dokumente zu identifizieren und zu klassifizieren sowie relevante Informationen aus jeder Datei zu extrahieren.  Wenn Dateien beispielsweise in eine SharePoint-Dokumentbibliothek hochgeladen werden, werden alle Dateien, die als *Aufträge* erkannt werden, als solche klassifiziert und anschließend in einer benutzerdefinierten Dokumentbibliotheksansicht angezeigt. Darüber hinaus können aus jeder Datei bestimmte Informationen (z. B. *Auftragsnummer* und *Gesamtbetrag*) abgerufen und als Spalte in Ihrer Dokumentbibliotheksansicht angezeigt werden. 

Das Inhaltsverständnis-Feature ermöglicht Ihnen das Erstellen von *Modellen*, um die benötigten Informationen zu finden und zu extrahieren. Modelle tragen dazu bei, geschäftliche Probleme bei der Suche, bei Geschäftsprozessen, Compliance und vielem mehr zu lösen.

Es gibt zwei Modelltypen, die Sie verwenden können:

- [Informationen zu Dokumentverständnismodellen](document-understanding-overview.md)
- [Formularverarbeitungsmodelle](form-processing-overview.md)

Beide Modelle werden in der Regel für den gleichen Zweck verwendet, doch die unten aufgeführten wesentlichen Unterschiede bedingen, welches Sie verwenden können.

> [!NOTE]
> Weitere Informationen zu Beispielszenarien für Formularverarbeitung und Dokumentverständnis finden Sie unter [SharePoint Syntex – Leitfaden für die ersten Schritte](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example).


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Strukturierte, unstrukturierte und teilstrukturierte Inhalte

Verwenden Sie Dokumentverständnismodelle, um Daten aus unstrukturierten Dokumenten (z. B. Briefen oder Verträgen) zu identifizieren und zu extrahieren, bei denen sich die Textentitäten, die Sie extrahieren möchten, in Sätzen oder bestimmten Bereichen des Dokuments befinden. So könnte beispielsweise ein unstrukturiertes Dokument ein Vertragsverlängerungsdokument sein, das auf unterschiedliche Weise verfasst sein kann. Allerdings enthält der Text jedes Vertragsverlängerungsdokuments übereinstimmende Informationen, z. B. die Textzeichenfolge *Startdatum Dienst* und dann ein bestimmtes Datum.

Verwenden Sie Formularverarbeitungsmodelle, um Dateien zu identifizieren und Daten aus strukturierten oder teilstrukturierten Dokumenten wie Formularen oder Rechnungen zu extrahieren. Formularverarbeitungsmodelle werden trainiert, den Aufbau eines Formulars anhand von Beispieldokumenten zu erkennen, und lernen, nach den Daten zu suchen, die aus ähnlichen Orten extrahiert werden sollen. Formulare weisen normalerweise einen strukturierteren Aufbau auf, in dem sich Entitäten an der selben Stelle befinden (beispielsweise eine Sozialversicherungsnummer in einem Steuerformular)

> [!NOTE]
> Um ein Dokumentverständnismodell erstellen oder ein solches auf eine SharePoint-Dokumentbibliothek anwenden zu können, benötigen Sie Zugang zu eine Inhaltscenter-Website. 


## <a name="where-models-are-created"></a>Wo die Modelle erstellt werden

Dokumentverständnismodelle werden auf einer SharePoint-Inhaltscenter-Site erstellt und verwaltet. 

> [!NOTE]
> Weitere Informationen zu Eingabedokumenten finden Sie unter [Formularverarbeitungsmodelle – Voraussetzungen und Einschränkungen](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

Formularverarbeitungsmodelle werden in PowerApps [KI-Generator](https://docs.microsoft.com/ai-builder/overview) erstellt, aber die Erstellung wird direkt aus einer SharePoint-Dokumentbibliothek heraus gestartet. Für eine Dokumentbibliothek muss das Erstellen von Formularverarbeitungsmodellen aktiviert sein, damit ein Benutzer ein Formularverarbeitungsmodell dafür erstellen kann. Administratoren können die Erstellung eines Formularverarbeitungsmodells in den Administratoreinstellungen für das Inhaltsverständnis aktivieren. Formularverarbeitungsmodelle verwenden PowerAutomate-Flows zum Verarbeiten von Dateien, wenn diese in die Dokumentbibliothek hochgeladen werden.

Bei der Erstellung eines Dokumentverständnismodells erstellen Sie einen neuen [SharePoint-Inhaltstyp](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), der im SharePoint-Inhaltstypenkatalog gespeichert wird. Bei Bedarf können Sie auch vorhandene Inhaltstypen verwenden, um das Modell zu definieren.

Formularverarbeitungsmodelle generieren ebenfalls neue [SharePoint-Inhaltstypen](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), die ebenfalls im SharePoint-Inhaltstypkatalog gespeichert werden.

## <a name="where-they-can-be-applied"></a>Wo die Modelle angewendet werden können

Sie können Dokumentverständnismodelle auf SharePoint-Dokumentbibliotheken anwenden, auf die Sie Zugriff haben. Verwenden Sie das Inhaltscenter, um ein Dokumentverständnismodell zu erstellen, und wenden Sie es auf verschiedene Dokumentbibliotheken an. Das Inhaltscenter ermöglicht eine zentralere Kontrolle darüber, wie Dokumentverständnismodelle verwendet und wo sie angewendet werden. Beachten Sie, dass diese Informationen auch bis zu einem Inhaltscenter reichen müssen.

Formularverarbeitungsmodelle können derzeit nur auf die SharePoint-Dokumentbibliothek angewendet werden, über die sie erstellt wurden. Auf diese Weise können lizenzierte Benutzer, die auf die Site zugreifen können, ein Formularverarbeitungsmodell erstellen. Beachten Sie, dass ein Administrator die Formularverarbeitung für eine SharePoint-Dokumentbibliothek aktivieren muss, damit sie für lizenzierte Benutzer zur Verfügung steht.

## <a name="comparison-of-forms-processing-and-document-understanding"></a>Vergleich von Formularverarbeitung und Dokumentenverständnis

Verwenden Sie die folgende Tabelle, um zu verstehen, wann Sie die Formularverarbeitung und wann Sie das Dokumentenverständnis verwenden sollten:

| Feature | Formularverarbeitung | Dokumentverständnis |
| ------- | ------- | ------- |
| Modelltyp – wann ist welcher zu verwenden | Wird für semistrukturierte Dateiformate verwendet, beispielsweise PDFs für Formularinhalte wie Rechnungen oder Bestellungen, bei denen das Layout und die Formatierung ähnlich sind.  | Wird für halbstrukturierte Dateiformate verwendet, beispielsweise für Office-Dokumente, bei denen es Unterschiede im Layout gibt, aber dennoch ähnliche Informationen extrahiert werden sollen. |
| Modellbildung | Im KI-Generator erstelltes Modell mit nahtlosem Zugriff aus der SharePoint-Dokumentenbibliothek.| In SharePoint erstelltes Modell auf einer neuen Website – dem Inhaltscenter. |
| Klassifizierungstyp| Einstellbarer Klassifizierer, der verwendet wird, um dem System Hinweise zu geben, welche Daten zu extrahieren sind.| Trainierbarer Klassifizierer mit optionalen Extraktoren, der mit Hilfe von maschinellem Lernen festlegt, an welcher Stelle des Dokuments welche Daten zu extrahieren sind.|
| Speicherorte | Für eine einzige Dokumentbibliothek trainiert.| Kann auf mehrere Bibliotheken angewendet werden.|
| Unterstützte Dateitypen| Training im Format PDF, JPG, PNG, insgesamt 50 MB und 500 Seiten.| Training auf 5–10 PDF-, Office- oder E-Mail-Dateien, einschließlich negativer Beispiele.<br>Office-Dateien werden bei 64k Zeichen abgeschnitten. OCR-gescannte Dateien sind auf 20 Seiten begrenzt.|
| Integrieren mit verwalteten Metadaten | Nein | Ja, durch das Training der Entitätsextraktionsfunktion, die sich auf ein konfiguriertes verwaltetes Metadatenfeld bezieht.|
| Integration von Compliance-Features, wenn Microsoft Information Protection aktiviert ist | Veröffentlichte Aufbewahrungsbezeichnungen festlegen.<br>Vertraulichkeitsbezeichnungen können bald eingestellt werden. | Veröffentlichte Aufbewahrungsbezeichnungen festlegen.<br>Vertraulichkeitsbezeichnungen können bald eingestellt werden. |
| Unterstützte Regionen| Die Formularverarbeitung basiert auf der Power-Platform. Informationen zur globalen Verfügbarkeit von Power-Platform und AI Builder finden Sie unter [Verfügbarkeit von Power-Platform](https://dynamics.microsoft.com/geographic-availability/). | In allen Regionen verfügbar.|
| Transaktionskosten | Verwendet AI Builder-Kreditpunkte.<br>Kreditpunkte können in Stapeln von 1 Mio. gekauft werden.<br>Beim Kauf von 300+ SharePoint Syntex Lizenzen sind 1 Mio. Kreditpunkte enthalten.<br>1 Mio. Kreditpunkte ermöglichen die Verarbeitung von 2000 Dateiseiten.<br>| Nicht zutreffend |
| Kapazität | Verwendet die Standard-Power Platform-Umgebung (benutzerdefinierte Umgebungen mit unterstützter Datenverse-Datenbank). | Hat keine Kapazitätsbeschränkungen.|
| Unterstützte Sprachen| Englisch <br>Später in 2021: Sprachen des lateinischen Alphabets | Die Modelle arbeiten mit allen Sprachen des lateinischen Alphabets. Zusätzlich zu Englisch: Deutsch, Schwedisch, Französisch, Spanisch, Italienisch und Portugiesisch.|

## <a name="see-also"></a>Siehe auch
[Schulungen: Verbessern der Geschäftsergebnisse mit AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[Übersicht über das Dokumentenverständnis](document-understanding-overview.md)

[Übersicht über die Formularverarbeitung](form-processing-overview.md)

[Einführung in SharePoint Syntex](index.md)
