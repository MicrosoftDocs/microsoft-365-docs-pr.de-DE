---
title: 'Einführung von Microsoft SharePoint Syntex: Erste Schritte'
description: Erfahren Sie, wie Sie SharePoint Syntex in Ihrer Organisation verwenden und implementieren, um Sie bei der Lösung Ihrer Geschäftsprobleme zu unterstützen.
ms.author: samanro
author: samanro
manager: pamgreen
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
ms.openlocfilehash: 8a5442fcf8dd50cdee6be97ba7c9bbf5e21408a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288155"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Einführung von Microsoft SharePoint Syntex: Erste Schritte

Stellen Sie sich die in SharePoint Syntex verfügbaren intelligenten Inhaltsdienste in drei Teilen vor:

- **Inhaltsverständnis:** Erstellen Sie codelose KI-Modelle, um Informationen aus Inhalten zu klassifizieren und zu extrahieren, um Metadaten automatisch für die Ermittlung und Wiederverwendung von Wissen anzuwenden. Weitere Informationen zum [Inhaltsverständnis.](document-understanding-overview.md)
- **Inhaltsverarbeitung:** Automatisieren Sie die Erfassung, Aufnahme und Kategorisierung von Inhalten und optimieren Sie inhaltsorientierte Prozesse mit Power Automate. Weitere Informationen zur [Inhaltsverarbeitung.](form-processing-overview.md)
- **Inhaltscompliance:** Steuern und Verwalten von Inhalten zur Verbesserung der Sicherheit und Governance mit Integration in Microsoft Information Protection.

Mit neuen KI-Diensten und -Funktionen können Sie Apps zum Verstehen und Klassifizieren von Inhalten direkt in den Inhaltsverwaltungsfluss mit SharePoint Syntex integrieren. Es gibt zwei verschiedene Möglichkeiten, Ihre Inhalte zu verstehen. Der verwendete Modelltyp basiert auf dem Dateiformat und dem Anwendungsfall:

| Formularverarbeitung | Dokumentverständnis |
|:-------|:-------|
| Erstellt aus der Dokumentbibliothek. | Erstellt im Inhaltscenter, Teil von SharePoint Syntex. |
| Modell, das im KI-Generator erstellt wurde. | In der systemeigenen Schnittstelle erstelltes Modell. |
| Wird für halbstrukturierte Dateiformate verwendet. | Wird für unstrukturierte Dateiformate verwendet. |
| Klassifizierer für die Festlegung. | Trainierbarer Klassifizierer mit optionalen Extraktoren. |
| Beschränkt auf eine einzelne Bibliothek. | Kann auf mehrere Bibliotheken angewendet werden. |
| Train on PDF, JPG, PNG format, total 50 MB/500 pp. | Training auf 5–10 PDF-, Office- oder E-Mail-Dateien, einschließlich negativer Beispiele. |

Einen umfassenderen Vergleich der Funktionen finden Sie unter ["Unterschied zwischen Dokumentverständnis- und Formularverarbeitungsmodellen".](difference-between-document-understanding-and-form-processing-model.md)

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identifizieren von Pilot-Geschäftsszenarien zur Optimierung

Um sich auf die Verwendung von SharePoint Syntex in Ihrer Organisation vorzubereiten, müssen Sie zunächst die Szenarien verstehen, in denen dies nützlich ist. Das "Warum" hilft bei der Bestimmung, welches Modell benötigt wird und wie Sie Ihre Organisation basierend auf dem Anwendungsort des Modells strukturieren. Hier sind einige Szenarien, in denen Dokumentverständnis Ihrer Organisation helfen kann:

- **Inhaltsverarbeitung:** Verarbeiten von Verträgen, Arbeitsanweisungen und anderen formularähnlichen Dokumenten. Nehmen Sie die Formulare auf, schulen Sie das Modell, um die Felder zu verstehen und zuzuordnen, und führen Sie dann Ihre Formulare durch, um die Daten automatisch zu sammeln. Weitere Informationen finden Sie unter [Übersicht über die Formularverarbeitung.](form-processing-overview.md)
- **Rechnungsanalyse:** Ziehen Sie die relevanten Details aus Ihren Rechnungen heraus, und stellen Sie sicher, dass sie den Richtlinien entsprechen oder ordnungsgemäß verarbeitet werden.

Überlegen Sie, wie SharePoint Syntex Ihrer Organisation helfen können:

- Automatisieren von Geschäftsprozessen
- Verbessern der Suchgenauigkeit
- Verwalten von Compliancerisiken

Stellen Sie sich die folgenden Fragen, wenn Sie überlegen, welche Geschäftsszenarien Sie berücksichtigen sollten:

- Löst es ein echtes Problem?
- Wird sie häufig verwendet oder hat sie breite Auswirkungen?
- Ist sie erhältlich?
- Können Sie Erfolg messen?

Priorisieren Sie Szenarien basierend auf auswirkungen und einfacher Implementierung. Sorgen Sie dafür, dass Der anfängliche Fokusbereich Szenarien mit höheren Auswirkungen hat, die auch einfach implementiert werden können. Depriorisieren Sie Szenarien mit geringeren Auswirkungen, die schwer zu implementieren sind.

Verwenden Sie die [Beispielszenarien und Anwendungsfälle,](adoption-scenarios.md) um Ideen dazu zu geben, wie Sie SharePoint Syntex in Ihrer Organisation verwenden können.

## <a name="identify-roles--responsibilities"></a>Identifizieren von Rollen & Zuständigkeiten

Bestimmen Sie, wer in Ihrer Organisation die Modelle erstellen und verwalten wird? Die folgenden Rollen können beteiligt sein:

| SharePoint/Wissensadministrator | Power Plattform-Administrator | Wissensmanager | Modellbesitzer |
|:-------|:-------|:-------|:-------|
| AAD-Rolle| AAD-Rolle | AAD-Rolle | Experten |
| Konfigurieren der Formularverarbeitung | Konfigurieren der allgemeinen Datendienstumgebung für die Formularverarbeitung | Erfassen von Anwendungsfällen | Sammeln von Geschäftsverwendungsfällen |
| Verwalten von Inhaltscentern und Berechtigungen| Erwerben und Zuordnen von AIB-Guthaben | Einrichten bewährter Methoden und Überprüfen von Modellanalysen | Erstellen und Anwenden von Modellen |

Wissensmanager, Besitzer von Geschäftsprozessen und Besitzer des Inhaltsmodells erstellen Beispielmodelle und setzen sich für die Einführung in der Organisation ein.
Andere Personen, die möglicherweise beteiligt sind: Compliance-Administrator, Taxonomie-Manager.

Wo werden die Modelle erstellt und angewendet? Gibt es vorhandene Prozesse oder Repositorys, die verbessert werden könnten?

- Formularverarbeitung: Entscheiden Sie, welche Websites eine Formularverarbeitungsaktion erhalten.
- Dokumentverständnis: Sie können mehrere Inhaltscenter für unterschiedliche Geschäftsbereiche erstellen.

## <a name="strategic-positioning"></a>Strategische Positionierung

Arbeiten Sie mit den Beteiligten zusammen, um sicherzustellen, dass sie an der Strategie für die Verwendung von SharePoint Syntex ausgerichtet sind. Recherchieren Sie und stellen Sie die folgenden Ressourcen bereit, um bei dieser Positionierung zu helfen:

- Geschäftsergebnisse:
  - Potenzielle Finanzergebnisse
  - Potenzielle Flexibilitätsergebnisse
  - Vorlage für Geschäftsergebnisse
- Stakeholder/Exec-Sponsor – Buy-In/Ausrichtung
  - Geschäftsfall-Decks
  - Finanzmodelle
  - Unternehmensbereitschaft – Kultur

## <a name="identify-stakeholders"></a>Bestimmen der Beteiligten

Identifizieren Sie die Beteiligten für Ihr Projekt.

|Rolle |Responsibilities |Abteilung |
|:-------|:-------|:--------|
| Leitender Sponsor   | Kommunizieren Sie die übergeordnete Vision und die Werte des Unternehmens   |  Führungskräfte   |
| Project Lead | Überwachen Sie die gesamte Durchführung der Markteinführung und den Rollout-Prozess | Projektmanagement |
| Wissensadministratoren| Erstellen und Verwalten der Inhaltscenter | IT oder andere Abteilungen|
| Inhaltsmanager und Modellbesitzer| Erfassen von Anwendungsfällen und Erstellen und Anwenden von Modellen | Jede Abteilung|
| Experten | Helfen Sie bei der Evangelisierung und bei der Behandlung von Einwänden | Jede Abteilung (Personal) |
| Mandantenadministrator | Konfigurieren von Einstellungen auf Mandantenebene | IT-Abteilung|
| Power Platform-Administrator| Gemeinsame Datendienstumgebung konfigurieren | IT-Abteilung|

> [!Note]
> Obwohl wir empfehlen, jede dieser Rollen während ihres Rollouts zu erfüllen, stellen Sie möglicherweise fest, dass Sie nicht alle benötigen, um mit Ihrer identifizierten Lösung zu beginnen.

## <a name="readiness-checklist"></a>Prüfliste zur Bereitschaft

Um sich auf die Implementierung von SharePoint Syntex vorzubereiten, müssen Sie Folgendes ausführen:

![Bereitschaft zum Verständnis von Inhalten](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Planen des Endzustands
    - Dokumentverständnismodelle sind die Mittel, nicht das Ende.
    - Planen Sie die Nutzung des Werts extrahierter Metadaten mit:
      - Suche
      - Filtern und Anzeigen der Formatierung
      - Compliance
      - Automatisierung
2. Identifizieren
    - Grundlegendes zur Verwendung der vorhandenen Informationsarchitektur und des Inhaltsverwaltungsfeatures.
    - Sind vorhandene Inhaltstypen gute Kandidaten für Modelle?
    - Welche vorhandenen Prozesse würden durch Metadaten verbessert?
3. Entwurf
    - Entwerfen Sie Ihren Ansatz für informationsarchitektur, verwaltete Metadaten und Inhaltstypen.
    - Entwerfen Sie den Prozess für Definition, Erstellung, Verwaltung.

## <a name="engage-your-organization"></a>Binden Sie Ihre Organisation ein

1. Identifizieren Sie Dienser, bestätigen Sie Szenarien und entwickeln Sie einen Projektplan.
1. Konfigurieren Sie Einstellungen, und wenden Sie Lizenzen an.
1. Beginnen Sie mit Sensibilisierung und Schulung – Werben von Champions.
1. Schrittweises Rollout.  
1. Sammeln Sie Feedback, und durchlaufen Sie.
1. Mit der zunehmenden Nutzung wächst der Plan für alle AI Builder-Gutschriften nach Bedarf.

## <a name="see-also"></a>Weitere Informationen:

[Szenarien und Anwendungsfälle für SharePoint Syntex](adoption-scenarios.md)
