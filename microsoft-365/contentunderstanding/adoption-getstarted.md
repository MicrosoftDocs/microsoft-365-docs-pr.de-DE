---
title: 'Microsoft SharePoint Syntex-Einführung: Erste Schritte'
description: Erfahren Sie, wie Sie SharePoint Syntex in Ihrer Organisation verwenden und implementieren, um Ihnen bei der Lösung Ihrer Geschäftsprobleme zu helfen.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: e88a7de1c81995b878dbf8a9308fbc774583289e
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597058"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Microsoft SharePoint Syntex-Einführung: Erste Schritte

Stellen Sie sich die intelligenten Inhaltsdienste in SharePoint Syntex als drei Teile vor:

- **Inhaltsverständnis: Erstellen** sie keine Code-KI-Modelle, um Informationen aus Inhalten zu klassifizieren und zu extrahieren, um Metadaten automatisch für die Wissenserkennung und -wiederverwendung anzuwenden. Erfahren Sie mehr über [das Verständnis von Inhalten.](document-understanding-overview.md)
- **Inhaltsverarbeitung:** Automatisieren Sie die Erfassung, Aufnahme und Kategorisierung von Inhalten, und optimieren Sie inhaltszentrierte Prozesse mithilfe von Power Automate. Erfahren Sie mehr über [die Inhaltsverarbeitung](form-processing-overview.md).
- **Inhaltskonformität:** Steuern und Verwalten von Inhalten zur Verbesserung der Sicherheit und Steuerung mit integration in Microsoft Information Protection.

Mit neuen AI-Diensten und -Funktionen können Sie Mithilfe von SharePoint Syntex Inhaltsverständnis- und Klassifizierungs-Apps direkt in den Inhaltsverwaltungsfluss aufnehmen. Es gibt zwei verschiedene Möglichkeiten, Ihre Inhalte zu verstehen. Der von Ihnen verwendete Modelltyp basiert auf dem Dateiformat und dem Verwendungsfall:

| Formularverarbeitung | Dokumentverständnis |
|:-------|:-------|
| Erstellt aus der Dokumentbibliothek. | Erstellt im Inhaltscenter, Teil von SharePoint Syntex. |
| Modell, das im KI-Generator erstellt wurde. | Modell, das in der systemeigenen Schnittstelle erstellt wurde. |
| Wird für semistrukturierte Dateiformate verwendet. | Wird für unstrukturierte Dateiformate verwendet. |
| Settable-Klassifikator. | Trainierbare Klassifizierung mit optionalen Extraktionen. |
| Auf eine einzelne Bibliothek beschränkt. | Kann auf mehrere Bibliotheken angewendet werden. |
| Train on PDF, JPG, PNG format, total 50 MB/500 pp. | Trainieren Sie mit 5-10 PDF-, Office- oder E-Mail-Dateien, einschließlich negativer Beispiele. |

Einen vollständigeren Vergleich der Funktionen finden Sie unter [Difference between document understanding and form processing models](difference-between-document-understanding-and-form-processing-model.md).

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identifizieren von Zu optimierende Pilotgeschäftsszenarien

Zur Vorbereitung auf die Verwendung von SharePoint Syntex in Ihrer Organisation müssen Sie zunächst die Szenarien verstehen, in denen sie nützlich sein wird. Das "Warum" hilft zu bestimmen, welches Modell benötigt wird, und wie Sie Ihre Organisation basierend auf dem Ort strukturieren, an dem das Modell angewendet wird. Im Folgenden finden Sie einige Szenarien, in denen Die Dokumentverständigung Ihrer Organisation helfen kann:

- **Inhaltsverarbeitung:** Verarbeiten von Verträgen, Arbeitsanweisungen und anderen formularverformten Dokumenten. Nehmen Sie die Formulare auf, schulen Sie das Modell, um die Felder zu verstehen und zu zuordnungen, und führen Sie dann Ihre Formulare durch, um die Daten automatisch zu erfassen. Weitere Informationen finden Sie unter [Übersicht über die Formularverarbeitung.](form-processing-overview.md)
- **Rechnungsanalyse:** Ziehen Sie die relevanten Details aus Ihren Rechnungen heraus, und stellen Sie sicher, dass sie den Richtlinien entsprechen oder entsprechend verarbeitet werden.

Überlegen Sie, wie SharePoint Syntex Ihrer Organisation helfen kann:

- Automatisieren von Geschäftsprozessen
- Verbessern der Suchgenauigkeit
- Verwalten des Compliancerisikos

Wenn Sie überlegen, welche Geschäftsszenarien sie berücksichtigen sollten, stellen Sie sich die folgenden Fragen:

- Löst sie ein echtes Problem?
- Wird sie weit verbreitet sein oder eine breite Wirkung haben?
- Ist sie erhältlich?
- Können Sie den Erfolg messen?

Priorisieren Sie Szenarien basierend auf auswirkungen und einfacher Implementierung. Machen Sie Ihren anfänglichen Fokusbereich zu szenarien mit höheren Auswirkungen, die auch einfach implementiert werden können. De priorisieren Sie Szenarien mit geringeren Auswirkungen, die schwer zu implementieren sind.

Verwenden Sie die folgenden Beispielszenarien, um Ideen zur Verwendung von SharePoint Syntex in Ihrer Organisation einzubringen.

### <a name="scenario-track-data-from-invoices-with-form-processing"></a>Szenario: Nachverfolgen von Daten aus Rechnungen mit Formularverarbeitung

Beispielsweise können Sie einen Prozess mit SharePoint Syntex- und Power Automate-Funktionen einrichten, um Rechnungen nachverfolgt und zu überwachen.

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

### <a name="scenario-track-information-from-contracts-with-document-understanding"></a>Szenario: Nachverfolgen von Informationen aus Verträgen mit Dokumentverständnis

Als weiteres Beispiel können Sie einen Prozess einrichten, um Verträge zu identifizieren, die Ihr Unternehmen mit anderen Unternehmen oder Einzelpersonen hat. Richten Sie ein Modell ein, um wichtige Informationen aus diesen Verträgen zu extrahieren, z. B. den Clientnamen, Gebühren, Datumsangaben oder andere wichtige Informationen, und fügen Sie die Informationen der Bibliothek als Felder hinzu, die Sie schnell anzeigen können. Wenden Sie eine Aufbewahrungsbezeichnung auf die Dokumentbibliothek an, um sicherzustellen, dass Verträge nicht vor einem bestimmten Zeitraum gelöscht werden können, um ihre Geschäftsbestimmungen entsprechend einzuhalten.

1. Beginnen Sie im Inhaltscenter, und erstellen Sie ein neues Dokumentverständnismodell für Verträge.
1. Laden Sie Beispieldokumente für positive und negative Beispiele hoch, führen Sie die Schulung aus, um Vertragsdokumente zu identifizieren und die Ergebnisse zu überprüfen.
1. Schulen Sie den Extractor, um Felder in den Verträgen zu identifizieren, z. B. den Clientnamen, die Gebühr und das Datum, und testen Sie dann die Extraktion.
1. Wenn das Modell abgeschlossen ist, wenden Sie das Modell auf eine Bibliothek an, in der Sie Verträge hochladen können.
1. Wenden Sie eine Aufbewahrungsbezeichnung auf das Datumsfeld an, damit Verträge für den erforderlichen Zeitraum in der Bibliothek aufbewahrt werden.

![Nachverfolgen und Überwachen von Verträgen mit SharePoint Syntex und Aufbewahrungsbezeichnungen](../media/content-understanding/process-contracts-flow.png)

Wenn Sie dieses Szenario automatisieren, können Sie:

- Sparen Sie Zeit und Geld, indem Sie Daten automatisch aus den Verträgen extrahieren, anstatt dies manuell zu tun.
- Stellen Sie mithilfe von Aufbewahrungsbezeichnungen eine bessere Compliance sicher, um sicherzustellen, dass die Verträge angemessen aufbewahrt werden.

### <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>Szenario: Vermeiden von Risiken mit Datensatzverwaltungs-, Dokument-Governance- und Complianceprozessen basierend auf SharePoint Syntex

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

### <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>Szenario: Erfassen von Informationen aus zuvor nicht zugänglichen Dokumenten

Die meisten Organisationen verfügen über umfangreiche Repositorys von Rechtsdokumenten, Richtlinien, Verträgen, Personaldokumenten und Steuerungsrichtlinien. Verwenden Sie diese Datenspeicher, um wertvolle Informationen zu extrahieren, z. B.: Projekte, Sektoren, Designs, Personen, geografische Regionen und so weiter.

Beispielsweise muss ein Personalleiter schnell auf alle Personaldokumente zugreifen – einschließlich Lebenslauf, Personalrichtlinien und anderen Formularen. Und sie möchten die erforderlichen Informationen aus Lebenslauf und anderen personalbezogenen Dokumenten schnell identifizieren, ohne die Dokumente manuell zu durchsingen. Sie suchen nach einer Lösung, mit der sie schnell die benötigten Informationen finden können, ohne tausende von Lebensläufen, Personalrichtlinien und andere Dokumentationen manuell durchschauen zu müssen, die möglicherweise auf mehrere Websites verteilt sind.

Wenn Sie dieses Szenario automatisieren, können Sie:

- Entsperrung von Wissen aus digitalen Inhalten.
- Klassifizieren Von Personalrichtlinien, Fortsetzungen, Verkaufsdokumenten, technischen Blaupausen, Kontoplänen und Extrahieren von Informationen.
- Finden Sie schnell die richtigen Informationen oder Dokumente, die Sie suchen.
- Erhalten Sie sofortigen Zugriff auf die neuesten Informationen.
- Reduzieren Sie die Suchzeiten.

### <a name="scenario-improve-data-processing-to-provide-insights--analytics"></a>Szenario: Verbessern der Datenverarbeitung, um Einblicke in & bieten

Beispielsweise könnte ein Pharmaunternehmen SharePoint Syntex verwenden, um Informationen aus DEN -DOKUMENTEN zu extrahieren, um Fragen zu beantworten, die ihre Führungskräfte haben. Die einfachere Erreichbarkeit der Antworten kann den Zeitaufwand für die Erstellung dieser Antworten reduzieren und die Verfügbarkeit von Daten erhöhen, um genauere Antworten auf Führungsfragen zu erhalten.

Beispielsweise muss ein Projektmanager schnell Antworten auf produktbezogene Fragen von meinem Führungsteam geben. Sie müssen Informationen und Metriken im Zusammenhang mit Abfragen in einem konsolidierten Dashboard finden. Sie suchen nach einer Lösung, die die benötigten Informationen aus Produktbezeichnungen, Produkt pamphlets und anderen Materialien extrahiert und einen konsolidierten Bericht generiert, den sie bei der Berichterstellung an ihr Führungsteam verwenden können.

Wenn Sie dieses Szenario automatisieren, können Sie:

- Reduzieren Sie die Zeit, um Antworten zu erhalten.
- Erhöhen Sie die Verfügbarkeit von Daten.
- Geben Sie genauere Antworten.

### <a name="scenario-automate-order-processing"></a>Szenario: Automatisieren der Auftragsverarbeitung

Mit SharePoint Syntex können Sie die Zeit für die manuelle Verarbeitung von Kundenbestellungen reduzieren. Beispielsweise können Sie Bestellungen aus Fax, E-Mail oder Papier mithilfe der OCR-Verarbeitung in SharePoint hochladen und dann die Metadaten aus diesen Bestellungen extrahieren, sodass Sie sie mithilfe automatisierter Prozesse erfüllen können.

Beispielsweise möchte ein Supply Chain Manager Fehler reduzieren, die durch die manuelle Dateneingabe verursacht werden. Sie möchten eine manuelle Überprüfung und Dateneingabe eingehender Kundenbestellungen (Papier, Fax oder E-Mail) vermeiden, um Fehler in ihre Geschäftssysteme zu reduzieren. Sie möchten eine Lösung, die KI- und maschinelle Lerntechniken verwendet, um eingehende Auftragsinformationen zu überprüfen, Kerndaten zu extrahieren und automatisch in ihr ERP-System zu übertragen, um Auftragserfüllung und -abstimmung zu erhalten.

Wenn Sie dieses Szenario automatisieren, können Sie sicherstellen, dass:

- Die Bestell- und Liefergenauigkeit wird erhöht.
- Gebühren oder Strafen im Zusammenhang mit Bestell- oder Lieferfehlern werden reduziert.
- Verzögerungen bei der Rechnungsstellung oder bei Zahlungen werden verringert.
- Die Personalkosten werden reduziert.

### <a name="scenario-simplify-visa-renewal-process"></a>Szenario: Vereinfachung des Visaerneuerungsprozesses

SharePoint Syntex kann Ihnen helfen, Erinnerungen und Verlängerungen für wichtige Vertragsinformationen zu automatisieren. Beispielsweise muss ein Personalleiter sicherstellen, dass die Visa der Mitarbeiter auf dem neuesten Stand sind und/oder zeitgemäß verlängert werden. Sie möchten den Personen einen einfachen und intuitiven Prozess für die Aktualisierung ihrer Visa bieten. Sie benötigen eine Lösung, die Verlängerungstermine aus Verträgen extrahiert und mitarbeiter automatisch Erinnerungen sendet, wenn ihre Verlängerungstermine näher kommen.

Wenn Sie dieses Szenario automatisieren, können Sie sicherstellen, dass:

- Die Einhaltungsstufen werden reduziert.
- Die Anzahl manueller Erinnerungen wird reduziert.
- Die Anzahl der Bußgelder für Verstöße wird reduziert.

## <a name="identify-roles--responsibilities"></a>Identifizieren von Rollen & Verantwortlichkeiten

Bestimmen Sie, wer in Ihrer Organisation die Modelle erstellen und verwalten soll? Die folgenden Rollen können beteiligt sein:

| SharePoint/Knowledge Admin | Power Platform Admin | Knowledge Manager | Modellbesitzer |
|:-------|:-------|:-------|:-------|
| AAD-Rolle| AAD-Rolle | AAD-Rolle | Experten |
| Konfigurieren der Formularverarbeitung | Konfigurieren der allgemeinen Datendienstumgebung für die Formularverarbeitung | Sammeln von Verwendungsfällen | Erfassen von Geschäftsnutzungsfällen |
| Verwalten von Inhaltscentern und -berechtigungen| Kaufen und Zuordnen von AIB-Guthaben | Einrichten bewährter Methoden und Überprüfen der Modellanalyse | Erstellen und Anwenden von Modellen |

Knowledge Manager, Geschäftsprozessbesitzer und Besitzer des Inhaltsmodells erstellen Beispielmodelle und unterstützen die Einführung in die Organisation.
Andere, die beteiligt sein können: Compliance-Administrator, Taxonomie-Manager.

Wo werden sie die Modelle erstellen und anwenden? Gibt es vorhandene Prozesse oder Repositorys, die erweitert werden könnten?

- Formularverarbeitung: Entscheiden Sie, welche Websites Die Formularverarbeitungsaktion erhalten soll.
- Dokumentverständnis: Sie können mehrere Inhaltscenter für verschiedene Geschäftsbereiche erstellen.

## <a name="strategic-positioning"></a>Strategische Positionierung

Arbeiten Sie mit den Beteiligten zusammen, um sicherzustellen, dass sie an der Strategie für die Verwendung von SharePoint Syntex ausgerichtet sind. Recherchiert und stellt die folgenden Ressourcen zur Verfügung, um bei dieser Positionierung zu helfen:

- Geschäftsergebnisse:
  - Mögliche geschäftspolitische Ergebnisse
  - Mögliche Agilitätsergebnisse
  - Vorlage für Geschäftsergebnis
- Stakeholders/Exec sponsor buy-in/alignment
  - Business Case Decks
  - Finanzmodelle
  - Unternehmensbereitschaft – Kultur

## <a name="identify-stakeholders"></a>Bestimmen der Beteiligten

Identifizieren Sie die Projektbeteiligten.

|Rolle |Responsibilities |Abteilung |
|:-------|:-------|:--------|
| Executive Sponsor(s)   | Kommunizieren von Visionen und Werten auf hoher Ebene für das Unternehmen   |  Führungsspitze   |
| Projektleiter | Überwachen des gesamten Startausführungs- und Rolloutprozesses | Projektmanagement |
| Wissensadministratoren| Erstellen und Verwalten der Inhaltscenter | IT oder andere Abteilung|
| Inhaltsmanager und Modellbesitzer| Erfassen von Verwendungsfällen und Erstellen und Anwenden von Modellen | Jede Abteilung|
| Experten | Hilfe bei der Evangelisierung und Verwaltung der Behandlung von Einwand | Jede Abteilung (Mitarbeiter) |
| Mandantenadministrator | Konfigurieren von Einstellungen auf Mandantenebene | IT-Abteilung|
| Power Platform-Administrator| Konfigurieren einer allgemeinen Data Services-Umgebung | IT-Abteilung|

> [!Note]
> Obwohl wir empfehlen, dass jede dieser Rollen während ihres Rollouts erfüllt wird, müssen Sie möglicherweise nicht alle rollen, um mit Ihrer identifizierten Lösung zu beginnen.

## <a name="readiness-checklist"></a>Prüfliste zur Bereitschaft

Um die Implementierung von SharePoint Syntex zu implementieren, müssen Sie:

![Bereitschaft zum Verständnis von Inhalten](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Planen des Endzustands
    - Dokumentverständnismodelle sind die Mittel und nicht das Ende.
    - Planen der Nutzung des Werts extrahierter Metadaten mit:
      - Suche
      - Filtern und Anzeigen von Formatierungen
      - Compliance
      - Automatisierung
2. Identifizieren
    - Verstehen der vorhandenen Informationsarchitektur und der Verwendung von Inhaltsverwaltungsfeatures.
    - Sind vorhandene Inhaltstypen gute Kandidaten für Modelle?
    - Welche vorhandenen Prozesse würden durch Metadaten verbessert?
3. Entwerfen
    - Entwerfen Ihres Ansatzes für Informationsarchitektur, verwaltete Metadaten und Inhaltstypen
    - Entwerfen sie den Prozess für Definition, Erstellung, Verwaltung.

## <a name="engage-your-organization"></a>Engagement Ihrer Organisation

1. Identifizieren von Beteiligungsinhabern, Bestätigen von Szenarien und Entwickeln eines Projektplans
1. Konfigurieren Sie Einstellungen, und wenden Sie Lizenzen an.
1. Sensibilisierung und Schulung – Rekrutieren von Champions.
1. Einführung in Phasen.  
1. Sammeln Sie Feedback und iterieren.
1. Wenn die Nutzung bei Bedarf anwächst, werden alle Guthaben des AI Builders geplant.
