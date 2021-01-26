---
title: 'Einführung von Microsoft SharePoint Syntex: Erste Schritte'
description: Erfahren Sie, wie Sie SharePoint Syntex in Ihrer Organisation verwenden und implementieren, um Ihre Geschäftlichen Probleme zu lösen.
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
ms.openlocfilehash: 7a0bd04121d7400cced22e43a539bd21c45a7fc3
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976572"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Einführung von Microsoft SharePoint Syntex: Erste Schritte

Stellen Sie sich die intelligenten Inhaltsdienste vor, die in SharePoint Syntex verfügbar sind, und haben drei Teile:

- **Inhaltserkenntnisse: Erstellen** Sie keine Code-KI-Modelle, um Informationen aus Inhalten zu klassifizieren und zu extrahieren, um Metadaten automatisch für die Ermittlung und Wiederverwendung von Wissen anzuwenden. Erfahren Sie mehr über [das Verständnis von Inhalten.](document-understanding-overview.md)
- **Inhaltsverarbeitung:** Automatisieren Sie die Erfassung, Aufnahme und Kategorisierung von Inhalten, und optimieren Sie inhaltsorientierte Prozesse mithilfe von Power Automate. Erfahren Sie mehr über [die Inhaltsverarbeitung.](form-processing-overview.md)
- **Inhaltskonformität:** Steuern und Verwalten von Inhalten zur Verbesserung der Sicherheit und Governance mit der Integration in Microsoft Information Protection.

Mit neuen AI-Diensten und -Funktionen können Sie Apps zum Verständnis und zur Klassifizierung von Inhalten direkt in den Inhaltsverwaltungsfluss mit SharePoint Syntex erstellen. Es gibt zwei verschiedene Möglichkeiten, Ihre Inhalte zu verstehen. Der von Ihnen verwendeten Modelltyp basiert auf dem Dateiformat und dem Verwendungsfall:

| Formularverarbeitung | Grundlegendes zu Dokumenten |
|:-------|:-------|
| Erstellt aus Dokumentbibliothek. | Erstellt im Inhaltscenter, Teil von SharePoint Syntex. |
| Modell, das im Generator für künstliche Intelligenz erstellt wurde. | Modell, das in der systemeigenen Schnittstelle erstellt wurde. |
| Wird für halbstrukturierte Dateiformate verwendet. | Wird für unstrukturierte Dateiformate verwendet. |
| Settable-Klassifikator. | Trainierbare Klassifizierung mit optionalen Extraktionen. |
| Auf eine einzelne Bibliothek beschränkt. | Kann auf mehrere Bibliotheken angewendet werden. |
| Schulen Sie das PDF-, JPG-, PNG-Format, insgesamt 50 MB/500 S.. | Schulen Sie 5-10 PDF-, Office- oder E-Mail-Dateien, einschließlich negativer Beispiele. |

In der folgenden Tabelle werden Verfügbarkeit und Lizenzierung für SharePoint Syntex erläutert:

| Formularverarbeitung | Grundlegendes zu Dokumenten |
|:-------|:-------|
| Die Formularverarbeitung basiert auf Power Platform. <br>Informationen zur globalen Verfügbarkeit für Power Platform und AI Builder finden Sie unter [Power Platform Availability](https://dynamics.microsoft.com/geographic-availability/). | In allen Regionen verfügbar. |
| Verwendet AI Builder-Guthaben.<br>Guthaben können in Batches von 1M erworben werden.<br>1M-Guthaben ist enthalten, wenn mehr als 300 SharePoint -Syntex-Lizenzen erworben werden.<br>1M-Guthaben ermöglicht die Verarbeitung von 2.000 Dateiseiten. | Modelle funktionieren in allen Sprachen des lateinischen Alphabets. Zusätzlich zu Englisch: Deutsch, Schwedisch, Französisch, Spanisch, Italienisch und Portugiesisch. |
| Wird für die standardmäßige allgemeine Datendienstumgebung bereitgestellt. | Es gelten keine Kapazitätseinschränkungen. |

Weitere Informationen zu Guthaben und Einheiten des AI Builders finden Sie unter [AI Builder-Lizenzierung.](https://docs.microsoft.com/ai-builder/administer-licensing)

SharePoint Syntex ist in Microsoft 365-Compliancefeatures integriert, wie:

- Aufbewahrungsbezeichnungen, die Datensatzrichtlinien basierend auf dem Dokumentalter oder externen Ereignissen definieren.
- Vertraulichkeitsbezeichnungen, die DLP-, Verschlüsselungs-, Freigabe- und Richtlinien für bedingten Zugriff festlegen.

Benutzer können Bezeichnungen anwenden, oder sie können automatisch von SharePoint Syntex-AI-Modellen angewendet werden. Analyse- und Dateipläne bieten eine skalierte Verwaltung der Bezeichnungsverwendung und -richtlinien.

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identifizieren von Zu optimierende Pilotgeschäftsszenarien

Um sich auf die Verwendung von SharePoint Syntex in Ihrer Organisation vorzubereiten, müssen Sie zunächst die Szenarien verstehen, in denen es nützlich sein wird. Die Gründe hierfür sind hilfreich, um zu bestimmen, welches Modell benötigt wird und wie Sie Ihre Organisation basierend darauf strukturieren, wo das Modell angewendet wird. Im Folgenden finden Sie einige Szenarien, in denen Dokumentverständnissen Ihrer Organisation helfen können:

- Inhaltsverarbeitung: Verarbeiten von Verträgen, Arbeitsanweisungen und anderen formular like-Dokumenten. Nehmen Sie die Formulare auf, schulen Sie das Modell, um die Felder zu verstehen und zu zuordnungieren, und führen Sie dann Die Formulare aus, um die Daten automatisch zu erfassen. Weitere Informationen finden Sie in der [Übersicht über die Formularverarbeitung.](form-processing-overview.md)
- Rechnungsanalyse: Ziehen Sie die relevanten Details aus Ihren Rechnungen heraus, und stellen Sie sicher, dass sie den Richtlinien entsprechen oder entsprechend verarbeitet werden.

Überlegen Sie, wie SharePoint Syntex Ihrer Organisation helfen kann:

- Automatisieren von Geschäftsprozessen
- Verbessern der Suchgenauigkeit
- Verwalten von Compliancerisiken

### <a name="form-processing-scenario-example"></a>Beispiel für ein Formularverarbeitungsszenario

Sie können z. B. einen Prozess mit SharePoint Syntex- und Power Automate-Features einrichten, um Rechnungen nachverfolgt und zu überwachen.

1. Richten Sie eine Bibliothek zum Speichern der Rechnungsdokumente ein.
1. Schulen Sie das Modell, um Felder in den Dokumenten zu erkennen.
1. Extrahieren Sie die Felder, die Sie nachverfolgen möchten, in eine Liste.
1. Richten Sie einen Fluss ein, um Sie bei bestimmten Ereignissen zu benachrichtigen, z. B.:
    - Eine neue Rechnung wird hinzugefügt.
    - Eine Rechnung liegt nach ihrem Fälligkeitsdatum.
    - Eine Rechnung ist für einen Betrag, der größer als Der Betrag für die automatische Genehmigung ist.

![Nachverfolgen und Überwachen von Rechnungen mit SharePoint Syntex und Power Automate](../media/content-understanding/process-invoices-flow.png)

Wenn Sie dieses Szenario automatisieren, können Sie:

- Sparen Sie Zeit und Geld, indem Sie Daten automatisch aus den Rechnungen extrahieren, anstatt dies manuell zu tun.
- Reduzieren Sie potenzielle Fehler, und stellen Sie eine bessere Compliance sicher, indem Sie Workflows verwenden, um auf Rechnungen zu handeln und Sie über Probleme zu informieren.

### <a name="document-understanding-scenario-example"></a>Beispiel für ein Szenario zum Verstehen von Dokumenten

Als weiteres Beispiel können Sie einen Prozess einrichten, um Verträge zu identifizieren, die Ihr Unternehmen mit anderen Unternehmen oder Einzelpersonen abgeschlossen hat. Sie können ein Modell einrichten, um wichtige Informationen aus diesen Verträgen zu extrahieren, z. B. den Clientnamen, Gebühren, Datumsangaben oder andere wichtige Informationen, und diese Informationen der Bibliothek als Felder hinzufügen, die Sie schnell anzeigen können. Und Sie können eine Aufbewahrungsbezeichnung auf die Dokumentbibliothek anwenden, um sicherzustellen, dass Verträge nicht vor einem bestimmten Zeitraum gelöscht werden können, um Ihre geschäftsspezifischen Bestimmungen zu erfüllen.

1. Beginnen Sie im Inhaltscenter, und erstellen Sie ein neues Dokument-Grundlegendes-Modell für Verträge.
1. Laden Sie Beispieldokumente für positive und negative Beispiele hoch, führen Sie dann die Schulung aus, um Vertragsdokumente zu identifizieren und die Ergebnisse zu überprüfen.
1. Schulen Sie die Extraktion, um Felder in den Verträgen zu identifizieren, z. B. client name, fee, and date, and then test the extractor.
1. Wenn das Modell abgeschlossen ist, wenden Sie das Modell auf eine Bibliothek an, in der Sie Verträge hochladen können.
1. Wenden Sie eine Aufbewahrungsbezeichnung auf das Datumsfeld an, damit Verträge für die Dauer, die Ihre Organisation für Verträge benötigt, in der Bibliothek aufbewahrt werden.

![Nachverfolgen und Überwachen von Verträgen mit SharePoint Syntex und Aufbewahrungsbezeichnungen](../media/content-understanding/process-contracts-flow.png)

Wenn Sie dieses Szenario automatisieren, können Sie:

- Sparen Sie Zeit und Geld, indem Sie Daten automatisch aus den Verträgen extrahieren, anstatt dies manuell zu tun.
- Sicherstellen einer besseren Einhaltung durch Die Verwendung von Aufbewahrungsbezeichnungen, um sicherzustellen, dass die Verträge angemessen aufbewahrt werden.

### <a name="tips-for-identifying-scenarios"></a>Tipps zum Identifizieren von Szenarien

Wenn Sie überlegen, welche Geschäftsszenarien Sie berücksichtigen sollten, stellen Sie sich die folgenden Fragen:

- Wird damit ein echtes Problem gelöst?
- Wird sie weit verbreitet sein oder große Auswirkungen haben?
- Ist sie erhältlich?
- Können Sie den Erfolg messen?

Priorisieren Sie Szenarien basierend auf auswirkungen und einfacher Implementierung. Machen Sie Ihre anfänglichen Fokusszenarien mit höheren Auswirkungen, die auch einfach implementiert werden können. De priorisieren Sie Szenarien mit geringeren Auswirkungen, die schwer zu implementieren sind.

## <a name="identify-roles--responsibilities"></a>Identifizieren von Rollen & Zuständigkeiten

Bestimmen Sie, wer in Ihrer Organisation die Modelle erstellen und verwalten wird? Die folgenden Rollen können beteiligt sein:

| SharePoint/Knowledge Admin | Power Platform Admin | Knowledge Manager | Modellbesitzer |
|:-------|:-------|:-------|:-------|
| Rolle "AAD"| Rolle "ADD" | Rolle "AAD" | Experten |
| Konfigurieren der Formularverarbeitung | Konfigurieren einer allgemeinen Datendienstumgebung für die Formularverarbeitung | Sammeln von Verwendungsfällen | Sammeln von Geschäftsnutzungsfällen |
| Verwalten von Inhaltscentern und Berechtigungen| Erwerben und Zuordnen von AIB-Guthaben | Einrichten bewährter Methoden und Überprüfen der Modellanalyse | Erstellen und Anwenden von Modellen |

Knowledge Manager, Geschäftsprozessbesitzer und Besitzer des Inhaltsmodells erstellen Beispielmodelle und verteidigern die Einführung in der Organisation.
Andere, die möglicherweise beteiligt sind: Complianceadministrator, Taxonomiemanager.

Wo werden die Modelle erstellen und angewendet? Gibt es vorhandene Prozesse oder Repositorys, die erweitert werden können?

- Formularverarbeitung: Entscheiden Sie, auf welchen Websites eine Formularverarbeitungsaktion angezeigt wird.
- Dokumentverständnis: Sie können mehrere Inhaltscenter für verschiedene Geschäftsbereiche erstellen.

## <a name="strategic-positioning"></a>Strategische Positionierung

Arbeiten Sie mit den Beteiligten zusammen, um sicherzustellen, dass sie an der Strategie für die Verwendung von SharePoint Syntex ausgerichtet sind. Recherchiert und stellt die folgenden Ressourcen zur Unterstützung dieser Positionierung zur Verfügung:

- Geschäftsergebnisse:
  - Mögliche Geschäftsergebnisse
  - Mögliche Agilitätsergebnisse
  - Geschäftsergebnisvorlage
- Projektbeteiligten/Exec Sponsor Buy-In/Ausrichtung
  - Geschäftsfall decks
  - Finanzmodelle
  - Unternehmensbereitschaft – Kultur

## <a name="identify-stakeholders"></a>Bestimmen der Beteiligten

Identifizieren Sie die Projektbeteiligten.

|Rolle |Responsibilities |Abteilung |
|:-------|:-------|:--------|
| Geschäftsleitungssponsor(en)   | Kommunizieren von visionären Und Werten auf hoher Ebene für das Unternehmen   |  Führungskräfte   |
| Projektleiter | Überwachen des gesamten Startausführungs- und Rolloutprozesses | Projektmanagement |
| Wissensadministratoren| Erstellen und Verwalten der Inhaltscenter | IT oder andere Abteilung|
| Inhaltsmanager und Modellbesitzer| Sammeln von Verwendungsfällen und Erstellen und Anwenden von Modellen | Jede Abteilung|
| Experten | Unterstützung bei der Verankündigung und Verwaltung der Behandlung von Ablehnungen | Jede Abteilung (Mitarbeiter) |
| Mandantenadministrator | Konfigurieren von Einstellungen auf Mandantenebene | IT-Abteilung|
| Power Platform-Administrator| Konfigurieren einer allgemeinen Datendiensteumgebung | IT-Abteilung|

> [!Note]
> Obwohl wir empfehlen, jede dieser Rollen während des Rollouts zu erfüllen, stellen Sie möglicherweise fest, dass Sie nicht alle für die ersten Schritte mit Ihrer identifizierten Lösung benötigen.

## <a name="readiness-checklist"></a>Prüfliste zur Bereitschaft

Um sich auf die Implementierung von SharePoint Syntex zu bereiten, müssen Sie:

![Bereitschaft zum Verständnis von Inhalten](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Planen des Endzustands
    - Dokumentergnungsmodelle sind die Mittel, nicht das Ende.
    - Planen Sie die Nutzung des Werts extrahierter Metadaten mit:
      - Suche
      - Filtern und Anzeigen von Formatierungen
      - Compliance
      - Automatisierung
2. Identifizieren
    - Verstehen der vorhandenen Verwendung von Informationsarchitektur und Inhaltsverwaltungsfeatures.
    - Sind vorhandene Inhaltstypen gut für Modelle geeignet?
    - Welche vorhandenen Prozesse würden durch Metadaten verbessert?
3. Entwurf
    - Entwerfen Des Ansatzes für Informationsarchitektur, verwaltete Metadaten und Inhaltstypen
    - Entwerfen sie den Prozess für Definition, Erstellung, Verwaltung.

## <a name="engage-your-organization"></a>Engagement Ihrer Organisation

1. Identifizieren Sie Projektinhaber, bestätigen Sie Szenarien, und entwickeln Sie einen Projektplan.
1. Konfigurieren Sie Einstellungen, und wenden Sie Lizenzen an.
1. Sensibilisierung und Schulung – Rekrutieren von Champions.
1. Einführung in Phasen.  
1. Sammeln von Feedback und Iterieren.
1. Mit der Nutzung wächst der Plan für alle AI Builder-Guthaben nach Bedarf.
