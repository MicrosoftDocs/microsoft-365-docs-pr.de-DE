---
title: Szenarien und Anwendungsfälle für Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: laurieellis
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: Hier finden Sie Szenarien zur Verwendung SharePoint Syntex in Ihrer Organisation.
ms.openlocfilehash: b28239a304c8fab209436c12e6cdbffe160b7981
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697061"
---
# <a name="scenarios-and-use-cases-for-microsoft-sharepoint-syntex"></a>Szenarien und Anwendungsfälle für Microsoft SharePoint Syntex

Verwenden Sie die folgenden Beispielszenarien, um Ideen zur Verwendung SharePoint Syntex in Ihrer Organisation einzubringen.

- [Szenario: Nachverfolgen von Daten aus Rechnungen mit Formularverarbeitung](adoption-scenarios.md#scenario-track-data-from-invoices-with-form-processing)
- [Szenario: Nachverfolgen von Informationen aus Verträgen mit Dokumentverständnis](adoption-scenarios.md#scenario-track-information-from-contracts-with-document-understanding)
- [Szenario: Vermeiden von Risiken durch Datensatzverwaltung, Dokumentverwaltung und Complianceprozesse basierend auf SharePoint Syntex](adoption-scenarios.md#scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex)
- [Szenario: Erfassen von Informationen aus zuvor nicht zugänglichen Dokumenten](adoption-scenarios.md#scenario-capture-information-from-previously-inaccessible-documents)
- [Szenario: Verbessern der Datenverarbeitung zur Bereitstellung von Einblicken und Analysen](adoption-scenarios.md#scenario-improve-data-processing-to-provide-insights-and-analytics)
- [Szenario: Automatisieren der Auftragsverarbeitung](adoption-scenarios.md#scenario-automate-order-processing)
- [Szenario: Vereinfachung des Visaerneuerungsprozesses](adoption-scenarios.md#scenario-simplify-visa-renewal-process)

## <a name="scenario-track-data-from-invoices-with-form-processing"></a>Szenario: Nachverfolgen von Daten aus Rechnungen mit Formularverarbeitung

Sie können z. B. einen Prozess mit SharePoint Syntex und Power Automate zum Nachverfolgen und Überwachen von Rechnungen einrichten.

1. Richten Sie eine Bibliothek zum Speichern der Rechnungsdokumente ein.
1. Schulen Sie das Modell, um Felder in den Dokumenten zu erkennen.
1. Extrahieren Sie die Felder, die Sie in einer Liste nachverfolgen möchten.
1. Richten Sie einen Fluss ein, um Sie bei bestimmten Ereignissen zu benachrichtigen, z. B.:
    - Eine neue Rechnung wird hinzugefügt.
    - Eine Rechnung liegt nach dem Fälligkeitsdatum.
    - Eine Rechnung ist für einen Betrag, der größer ist als Der betrag für die automatische Genehmigung.

![Nachverfolgen und Überwachen von Rechnungen mit SharePoint Syntex und Power Automate](../media/content-understanding/process-invoices-flow.png)

Wenn Sie dieses Szenario automatisieren, können Sie:

- Sparen Sie Zeit und Geld, indem Sie Daten automatisch aus den Rechnungen extrahieren, anstatt dies manuell zu tun.
- Reduzieren Sie potenzielle Fehler, und stellen Sie eine bessere Compliance sicher, indem Sie Mithilfe von Workflows Rechnungen überprüfen und Sie über probleme benachrichtigen.

## <a name="scenario-track-information-from-contracts-with-document-understanding"></a>Szenario: Nachverfolgen von Informationen aus Verträgen mit Dokumentverständnis

Als weiteres Beispiel können Sie einen Prozess einrichten, um Verträge zu identifizieren, die Ihr Unternehmen mit anderen Unternehmen oder Einzelpersonen hat. Richten Sie ein Modell ein, um wichtige Informationen aus diesen Verträgen zu extrahieren, z. B. den Clientnamen, Gebühren, Datumsangaben oder andere wichtige Informationen, und fügen Sie die Informationen der Bibliothek als Felder hinzu, die Sie schnell anzeigen können. Wenden Sie eine Aufbewahrungsbezeichnung auf die Dokumentbibliothek an, um sicherzustellen, dass Verträge nicht vor einem bestimmten Zeitraum gelöscht werden können, um ihre Geschäftsbestimmungen entsprechend einzuhalten.

1. Beginnen Sie im Inhaltscenter, und erstellen Sie ein neues Dokumentverständnismodell für Verträge.
1. Hochladen Sie Beispieldokumente für positive und negative Beispiele, führen Sie dann die Schulung aus, um Vertragsdokumente zu identifizieren und die Ergebnisse zu überprüfen.
1. Schulen Sie den Extractor, um Felder in den Verträgen zu identifizieren, z. B. den Clientnamen, die Gebühr und das Datum, und testen Sie dann die Extraktion.
1. Wenn das Modell abgeschlossen ist, wenden Sie das Modell auf eine Bibliothek an, in der Sie Verträge hochladen können.
1. Wenden Sie eine Aufbewahrungsbezeichnung auf das Datumsfeld an, damit Verträge für den erforderlichen Zeitraum in der Bibliothek aufbewahrt werden.

![Nachverfolgen und Überwachen von Verträgen mit SharePoint Syntex- und Aufbewahrungsbezeichnungen](../media/content-understanding/process-contracts-flow.png)

Wenn Sie dieses Szenario automatisieren, können Sie:

- Sparen Sie Zeit und Geld, indem Sie Daten automatisch aus den Verträgen extrahieren, anstatt dies manuell zu tun.
- Stellen Sie mithilfe von Aufbewahrungsbezeichnungen eine bessere Compliance sicher, um sicherzustellen, dass die Verträge angemessen aufbewahrt werden.

## <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>Szenario: Vermeiden von Risiken durch Datensatzverwaltung, Dokumentverwaltung und Complianceprozesse basierend auf SharePoint Syntex

Die Risikominderung ist für die meisten Unternehmen ein gemeinsames Ziel. Möglicherweise benötigen Sie:

- Eine bessere Möglichkeit zum Bereitstellen/Erzwingen der Informationsverwaltung in Ihrem Mandanten.
- Zur Verbesserung des Systems für die Klassifizierung von Dokumenten, E-Mails und anderen Kommunikationsformen, die als "Datensätze" für Projekte betrachtet werden.
- So überwachen Sie Quittungen, Verträge und so weiter, um die Einhaltung von Unternehmensrichtlinien sicherzustellen.
- So stellen Sie sicher, dass für Projekte alle für die Compliance erforderlichen Dokumentationen zur Verfügung sind.

Richten Sie einige Prozesse für die Einhaltung von SharePoint Syntex ein, um Dokumente und Formulare zu erfassen und entsprechend zu klassifizieren, zu überwachen und zu kennzeichnen, die eine bessere Steuerung benötigen. Sie können sich auf SharePoint Syntex verlassen, um Inhalte automatisch zu klassifizieren, anstatt sich darauf zu verlassen, dass Endbenutzer manuell taggen oder das Complianceteam Steuerungsregeln und Archivierung manuell anwenden kann. Und Sie können eine vereinfachte Suchfunktion aktivieren, Datenvolumes verwalten, Datensatzverwaltungs- und Aufbewahrungsrichtlinien anwenden, die Compliance sicherstellen und bewährte Archivierungs- und Bereinigungsmethoden sicherstellen.

Wenn Sie dieses Szenario automatisieren, können Sie sich sicher fühlen, dass:

- Die Compliance wird bestätigt, und das Risiko wird reduziert.
- Taxonomie und Datensatzverwaltung werden konsistent und präzise angewendet.
- Inhaltsvolumes werden gesteuert.
- Mitarbeiter können problemlos die richtigen Informationen im richtigen Kontext finden.

## <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>Szenario: Erfassen von Informationen aus zuvor nicht zugänglichen Dokumenten

Die meisten Organisationen verfügen über umfangreiche Repositorys von Rechtsdokumenten, Richtlinien, Verträgen, Personaldokumenten und Steuerungsrichtlinien. Verwenden Sie diese Datenspeicher, um wertvolle Informationen zu extrahieren, z. B.: Projekte, Sektoren, Designs, Personen, geografische Regionen und so weiter.

Beispielsweise muss ein Personalleiter schnell auf alle Personaldokumente zugreifen – einschließlich Lebenslauf, Personalrichtlinien und anderen Formularen. Und sie möchten die erforderlichen Informationen aus Lebenslauf und anderen personalbezogenen Dokumenten schnell identifizieren, ohne die Dokumente manuell zu durchsingen. Sie suchen nach einer Lösung, mit der sie schnell die benötigten Informationen finden können, ohne tausende von Lebensläufen, Personalrichtlinien und andere Dokumentationen manuell durchschauen zu müssen, die möglicherweise auf mehrere Websites verteilt sind.

Wenn Sie dieses Szenario automatisieren, können Sie:

- Entsperrung von Wissen aus digitalen Inhalten.
- Klassifizieren Von Personalrichtlinien, Fortsetzungen, Verkaufsdokumenten, technischen Blaupausen, Kontoplänen und Extrahieren von Informationen.
- Finden Sie schnell die richtigen Informationen oder Dokumente, die Sie suchen.
- Erhalten Sie sofortigen Zugriff auf die neuesten Informationen.
- Reduzieren Sie die Suchzeiten.

## <a name="scenario-improve-data-processing-to-provide-insights-and-analytics"></a>Szenario: Verbessern der Datenverarbeitung zur Bereitstellung von Einblicken und Analysen

Beispielsweise könnte ein Pharmazeutisches Unternehmen SharePoint Syntex verwenden, um Informationen aus DENA-Dokumenten zu extrahieren, um Fragen zu beantworten, die ihre Führungskräfte haben. Die einfachere Erreichbarkeit der Antworten kann den Zeitaufwand für die Erstellung dieser Antworten reduzieren und die Verfügbarkeit von Daten erhöhen, um genauere Antworten auf Führungsfragen zu erhalten.

Beispielsweise muss ein Projektmanager schnell Antworten auf produktbezogene Fragen von meinem Führungsteam geben. Sie müssen Informationen und Metriken im Zusammenhang mit Abfragen in einem konsolidierten Dashboard finden. Sie suchen nach einer Lösung, die die benötigten Informationen aus Produktbezeichnungen, Produkt pamphlets und anderen Materialien extrahiert und einen konsolidierten Bericht generiert, den sie bei der Berichterstellung an ihr Führungsteam verwenden können.

Wenn Sie dieses Szenario automatisieren, können Sie:

- Reduzieren Sie die Zeit, um Antworten zu erhalten.
- Erhöhen Sie die Verfügbarkeit von Daten.
- Geben Sie genauere Antworten.

## <a name="scenario-automate-order-processing"></a>Szenario: Automatisieren der Auftragsverarbeitung

Mit SharePoint Syntex können Sie die Zeit für die manuelle Verarbeitung von Kundenbestellungen reduzieren. Sie können z. B. Bestellungen aus Fax, E-Mail oder Papier mithilfe der OCR-Verarbeitung in SharePoint hochladen und dann die Metadaten aus diesen Bestellungen extrahieren, sodass Sie sie mithilfe automatisierter Prozesse erfüllen können.

Beispielsweise möchte ein Supply Chain Manager Fehler reduzieren, die durch die manuelle Dateneingabe verursacht werden. Sie möchten eine manuelle Überprüfung und Dateneingabe eingehender Kundenbestellungen (Papier, Fax oder E-Mail) vermeiden, um Fehler in ihre Geschäftssysteme zu reduzieren. Sie möchten eine Lösung, die KI- und maschinelle Lerntechniken verwendet, um eingehende Auftragsinformationen zu überprüfen, Kerndaten zu extrahieren und automatisch in ihr ERP-System zu übertragen, um Auftragserfüllung und -abstimmung zu erhalten.

Wenn Sie dieses Szenario automatisieren, können Sie sicherstellen, dass:

- Die Bestell- und Liefergenauigkeit wird erhöht.
- Gebühren oder Strafen im Zusammenhang mit Bestell- oder Lieferfehlern werden reduziert.
- Verzögerungen bei der Rechnungsstellung oder bei Zahlungen werden verringert.
- Die Personalkosten werden reduziert.

## <a name="scenario-simplify-visa-renewal-process"></a>Szenario: Vereinfachung des Visaerneuerungsprozesses

SharePoint Mit Syntex können Sie Erinnerungen und Verlängerungen für wichtige Vertragsinformationen automatisieren. Beispielsweise muss ein Personalleiter sicherstellen, dass die Visa der Mitarbeiter auf dem neuesten Stand sind und/oder zeitgemäß verlängert werden. Sie möchten den Personen einen einfachen und intuitiven Prozess für die Aktualisierung ihrer Visa bieten. Sie benötigen eine Lösung, die Verlängerungstermine aus Verträgen extrahiert und mitarbeiter automatisch Erinnerungen sendet, wenn ihre Verlängerungstermine näher kommen.

Wenn Sie dieses Szenario automatisieren, können Sie sicherstellen, dass:

- Die Einhaltungsstufen werden reduziert.
- Die Anzahl manueller Erinnerungen wird reduziert.
- Die Anzahl der Bußgelder für Verstöße wird reduziert.

## <a name="see-also"></a>Weitere Artikel

[Microsoft SharePoint Syntex-Einführung: Erste Schritte](adoption-getstarted.md)