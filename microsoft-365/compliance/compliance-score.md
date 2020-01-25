---
title: Microsoft-Konformitätsbewertung
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Score unterstützt Organisationen bei der Vereinfachung und Automatisierung von Risikobewertungen und schlägt Empfohlene Aktionen zum Beheben von Risiken vor.
ms.openlocfilehash: 8a523878cb003e1cc676ea65d69f402ddf056e84
ms.sourcegitcommit: e872676ec98036a50d3a0cb5071109ea5f5a7ae5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "41515676"
---
# <a name="microsoft-compliance-score-preview"></a>Microsoft-Konformitätsbewertung (Vorschau)

Das Microsoft-Kompatibilitäts Ergebnis hilft Ihnen, die Verwaltung der Compliance zu vereinfachen und Compliance-Risiken durch eine benutzerfreundliche Erfahrung zu verringern. Das Kompatibilitäts Ergebnis steht nun für die öffentliche Vorschau im [Microsoft 365 Compliance Center](microsoft-365-compliance-center.md)zur Verfügung.

**In diesem Artikel:** Lesen Sie diesen Artikel, um zu verstehen, welche Kompatibilitätsbewertung vorliegt und wie Sie Sie für Ihre Organisation einrichten.

Informationen **zu Updates:** Informationen zu den neuen und bekannten Problemen mit der Vorschauversion des Kompatibilitäts Bewertungsergebnisses finden Sie in den Versionshinweisen zur [Kompatibilitätsbewertung](compliance-score-release-notes.md) .

## <a name="what-is-compliance-score"></a>Was ist Konformitätsbewertung

Microsoft Compliance Score ist eine Vorschaufunktion im Microsoft 365 Compliance Center, die Ihnen hilft, die Compliance-Haltung ihrer Organisation zu verstehen. Es wird eine risikobasierte Bewertung berechnet, die Ihren Fortschritt bei der Durchführung von Aktionen misst, um Risiken hinsichtlich des Datenschutzes und der regulatorischen Standards zu verringern.

Sie können die Kompatibilitätsbewertung als Tool verwenden, um alle ihre Risikobewertungen nachzuverfolgen. Es bietet Workflowfunktionen, die Sie bei der effizienten Durchführung ihrer Risikobewertungen mithilfe eines allgemeinen Tools unterstützen.

Wenn Sie den [Compliance-Manager](compliance-manager-overview.md)derzeit verwenden, werden Sie feststellen, dass das Kompatibilitäts Ergebnis nun ein eigenständiges Feature mit einem einfacheren, benutzerfreundlicheren Design ist, mit dem Sie die Compliance einfacher verwalten können. 

Die Hauptseite der Kompatibilitätsbewertung ist Ihr benutzerdefiniertes Dashboard. Es zeigt Ihre aktuelle Punktzahl, hilft Ihnen zu sehen, was Aufmerksamkeit benötigt, und führt Sie zu Aktionen zur Verbesserung ihrer Gäste. Das Dashboard für die Konformitätsbewertung sieht wie folgt aus:

![Compliance Score-Dashboard](media/compliance-score-dashboard.png "Konformitäts Bewertungs Dashboard")

### <a name="simplified-compliance-management"></a>Vereinfachte Compliance-Verwaltung

Compliance-Score hilft bei der Vereinfachung der Compliance-Verwaltung durch folgende Bereitstellung:

- **Kontinuierliche Bewertungen**: scannt automatisch Ihre Microsoft 365-Umgebungen, um die Effektivität von Datenschutz-Steuerelementen in Ihrem System zu erkennen und zu überwachen.
- **Empfohlene Aktionen**: enthält Empfehlungen und Schritt-für-Schritt-Anleitungen zum Implementieren von Steuerelementen zur Maximierung der Punktzahl
-  **Integrierte Steuerungs Zuordnung**: hilft Ihnen, mit der sich entwickelnden Compliance-Landschaft auf dem Laufenden zu bleiben, indem ein integriertes einheitliches Steuerelement Framework bereitgestellt wird

> [!IMPORTANT] 
> Compliance Score ist kein absolutes Maß für die organisatorische Einhaltung einer bestimmten Norm oder Regulierung. Sie drückt das Ausmaß aus, in dem Sie Steuerelemente eingeführt haben, die die Risiken für personenbezogene Daten und den Schutz der Privatsphäre reduzieren können. Empfehlungen aus dem Compliance Score und dem Compliance-Manager sollten nicht als Garantie für die Compliance interpretiert werden. Dieser Dienst befindet sich derzeit in der Vorschau und unterliegt den allgemeinen Geschäftsbedingungen in den [Online Dienstbedingungen](https://go.microsoft.com/fwlink/?linkid=2108910).

## <a name="relationship-to-compliance-manager"></a>Beziehung zum Compliance-Manager

Denken Sie an die Konformitätsbewertung als vereinfachte Version von Compliance-Manager. Während die beiden als eindeutige, aber integrierte Tools vorhanden sind, erleichtert Compliance Score die Überwachung ihrer allgemeinen Compliance-Haltung und die Schritte zur Verbesserung dieser.

Das Kompatibilitäts Ergebnis teilt dasselbe Back-End mit dem Compliance-Manager, sodass alle Daten, die Sie möglicherweise bereits im Compliance-Manager haben, in der Kompatibilitätsbewertung angezeigt werden.

Während der öffentlichen Vorschau verbleiben einige Funktionen nur im Compliance-Manager, beispielsweise bei der Verwaltung von Bewertungen und dem Erstellen von Vorlagen. Es wird empfohlen, alle Compliance-Verwaltungsaktivitäten im Kompatibilitäts Bewertungsergebnis zu beginnen. Wenn Sie mit den von Compliance Manager behandelten Funktionen kommen, werden Sie zu diesem Tool geführt. Aus diesem Grund werden Sie in einigen dieser Dokumentationen zu Compliance-Manager-Themen geleitet.

Weitere Informationen zur Beziehung zwischen Compliance Score und Compliance-Manager finden Sie in den Versionshinweisen zur [Kompatibilitätsbewertung](compliance-score-release-notes.md).

## <a name="understanding-your-score"></a>Grundlegendes zur Partitur

Mit der Kompatibilitätsbewertung erhalten Sie eine erste Bewertung basierend auf der Microsoft 365-Datenschutz Basis. Dieser Basisplan umfasst eine Reihe von Steuerelementen, die allgemeine Branchenvorschriften und-Standards umfassen. Diese Bewertung ist zwar ein guter Ausgangspunkt für die Bewertung Ihrer Compliance-Position, aber die Konformitätsbewertung wird leistungsfähiger, wenn Sie Bewertungen hinzufügen, die für Ihre Organisation relevanter sind.

Wenn Ihre Organisation beispielsweise zur Finanzdienstleistungsbranche gehört, möchten Sie möglicherweise die FFIEC-Bewertung hinzufügen. Wenn Ihre Organisation der Healthcare-Branche angehört, können Sie die HIPAA/HITECH-Bewertung hinzufügen. Hier erfahren Sie, wie [Sie Assessments im Compliance-Manager hinzufügen](working-with-compliance-manager.md#assessments).

Erfahren Sie mehr darüber [, wie Ihr Konformitäts Bewertungspunkt berechnet und kontinuierlich überwacht wird](compliance-score-methodology.md).


## <a name="key-components-controls-assessments-templates-groups"></a>Wichtige Komponenten: Steuerelemente, Bewertungen, Vorlagen, Gruppen

Compliance Score verwendet mehrere Komponenten, die Sie bei der Verwaltung Ihrer Compliance-Aktivitäten unterstützen. Wenn Sie die Konformitätsbewertung verwenden, um Compliance-Aktivitäten zuzuweisen, zu testen und zu überwachen, ist es hilfreich, ein grundlegendes Verständnis dieser wichtigen Komponenten zu haben. Dieses Diagramm zeigt die Beziehungen zwischen diesen:

![Beziehungen in Compliance-Manager, Version 3](media/compliance-manager-relationships.png "Kompatibilitäts Bewertungspunkte – Komponenten")

### <a name="controls"></a>Steuerelemente

Ein Steuerelement definiert, wie Sie die Systemkonfiguration, den Organisationsprozess und die Verantwortlichkeiten der Personen bewerten und verwalten, um eine bestimmte Anforderung einer Richtlinie, einer Standardrichtlinie oder einer internen Richtlinie zu erfüllen.

Das Kompatibilitäts Ergebnis verfolgt zwei Arten von Steuerelementen:

1. Von **Microsoft verwaltete Steuer**Elemente: Steuerelemente für Microsoft Cloud-Dienste, die von Microsoft für die Implementierung zuständig sind
2. Vom **Kunden verwaltete**Steuerelemente: von Ihrer Organisation verwaltete Steuerelemente, die Sie für die Implementierung zuständig sind
 
### <a name="assessments"></a>Bewertungen

Bei einer Bewertung handelt es sich um eine Bewertung einer Vorlage, die den Bewertungsprozess für Ihre Organisation initiiert. Assessments Group die Maßnahmen, die erforderlich sind, um die Anforderungen eines Standards, einer Verordnung oder eines Gesetzes zu erfüllen. Sie haben beispielsweise eine Einschätzung, dass, wenn Sie alle darin enthaltenen Aktionen durchführen, Ihre Office 365-Einstellungen entsprechend den Anforderungen von ISO 27001 angepasst werden.

Standardmäßig bietet Compliance Score Ihrer Organisation eine Bewertung basierend auf der Microsoft 365-Datenschutz Basis, eine Empfehlung zur Verringerung ihrer Datenschutz-und Konformitätsrisiken ([Weitere Informationen](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).

Die Bewertungen umfassen mehrere Komponenten:

- **Im Bereich Dienste**: die spezifische Gruppe von Microsoft-Diensten, die für die Bewertung gelten.
- Von Microsoft **verwaltete Steuer**Elemente: von Microsoft implementierte und getestete Steuerelemente
- Von **Kunden verwaltete Steuer**Elemente: Steuerelemente, die Sie verwalten
- **Bewertungsergebnis**: der Prozentsatz der Punkte, die durch das Ausführen von Aktionen innerhalb dieser Bewertung erzielt wurden

> [!NOTE]
> Das Kompatibilitäts Ergebnis zeigt Ihre Bewertungen an und wie Sie in Ihre Gesamtpunktzahl eingehen. Während der öffentlichen Vorschau werden Sie jedoch an den Compliance-Manager weitergeleitet, um Ihre Bewertungen zu verwalten.

Hier erhalten Sie detaillierte Anweisungen zum [Arbeiten mit Assessments im Compliance-Manager](working-with-compliance-manager.md#assessments).

### <a name="templates"></a>Vorlagen

Compliance Score stellt vorkonfigurierte Vorlagen für Bewertungen bereit. Mit Compliance Score können Sie auch Vorlagen für eigene Bewertungen erstellen, die Ihren Anforderungen entsprechen. Sie können beispielsweise eine Vorlage für Ihr Geschäftsprozess-Steuerelement oder eine Vorlage für einen regionalen Datenschutz-oder Kompatibilitätsstandard erstellen, der nicht von einer der vorkonfigurierten Vorlagen abgedeckt wird.  Wenn Sie eigene Vorlagen erstellen, können Sie benutzerdefinierte Bewertungen erstellen, um sicherzustellen, dass die Konformitätsbewertung nicht nur Microsoft-Cloud-Bewertungen, sondern auch alle anderen Risikobewertungen im Bereich Ihrer Organisation verfolgt.

Sie können neue Vorlagen erstellen, indem Sie eine vorhandene Vorlage kopieren oder Steuerelementinformationen aus einer Excel-Datei importieren. Hier erhalten Sie detaillierte Anweisungen zum [Erstellen von Vorlagen im Compliance-Manager](working-with-compliance-manager.md#templates).

Die vorkonfigurierten Vorlagen für die Konformitätsbewertung lauten wie folgt:

1. [Brasilien – allgemeine Datenschutz Gesetze (LGPD)](https://go.microsoft.com/fwlink/?linkid=2115387)
2. [California Consumer Privacy Act (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (Vorschau)
3. [Cloud Security Alliance (CSA) Cloud Controls Matrix (CCM) 3.0.1](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [Dsgvo der Europäischen Union](https://go.microsoft.com/fwlink/?linkid=2108870)
5. [Federal Financial Institutions Examination Council (FFIEC) Information Security Booklet](https://go.microsoft.com/fwlink/?linkid=2109077)
6. [FedRAMP moderat](https://go.microsoft.com/fwlink/?linkid=2108869)
7. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / -[HITECH](https://go.microsoft.com/fwlink/?linkid=2109079)
8. [IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [Australian Government ISM](https://go.microsoft.com/fwlink/?linkid=2113024) (Vorschau)
9. [ISO 27001:2013](https://go.microsoft.com/fwlink/?linkid=2109073)
10. [ISO 27018:2014](https://go.microsoft.com/fwlink/?linkid=2109074)
11. [ISO 27701:2019](https://go.microsoft.com/fwlink/?linkid=2113025)
12. [Microsoft 365-Datenschutz Basis](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
13. [NIST 800-53 Rev. 4](https://go.microsoft.com/fwlink/?linkid=2109075)
14. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
15. [NIST-Cyber-Framework (CSF)](https://go.microsoft.com/fwlink/?linkid=2108868)
16. [SOC 1](https://go.microsoft.com/fwlink/?linkid=2115184)
17. [SOC 2](https://go.microsoft.com/fwlink/?linkid=2115184)

> [!NOTE]
> Navigieren Sie während der öffentlichen Vorschau zum Compliance-Manager, um Ihre Vorlagen zu erstellen und zu verwalten.

### <a name="groups"></a>Gruppen

Mit Gruppen können Sie Bewertungen so organisieren, dass Sie logisch sind. Sie können beispielsweise nach Jahr, Kompatibilitätsstandard, Dienst, Teams in Ihrer Organisation oder auf andere Weise Gruppenbewertungen auswählen.

Wenn zwei unterschiedliche Bewertungen in derselben Gruppe von Kunden verwaltete Aktionen gemeinsam nutzen, werden der Abschluss der Implementierungsdetails, Tests und der Status der Aktion in einem Test automatisch mit derselben Aktion in einer anderen Bewertung in der Gruppe synchronisiert. Dadurch werden die zugewiesenen Verbesserungs Aktionen in der gesamten Gruppe vereinheitlicht und Arbeits Duplikate reduziert.

Informationen zum [Erstellen von Gruppen im Compliance-Manager](working-with-compliance-manager.md#groups). Nachdem Sie Gruppen erstellt haben, können Sie das Dashboard für die [Konformitätsbewertung Filtern](compliance-score-setup.md#filtering-your-dashboard-view) , um die Bewertung von einer oder mehreren Gruppen anzuzeigen.

## <a name="next-step-begin-setup"></a>Nächster Schritt: Setup starten

Hier erfahren Sie, wie Sie sich anmelden, Berechtigungen einrichten und Updates und Dashboard-Ansichten im [Setup der Kompatibilitätsbewertung](compliance-score-setup.md)konfigurieren.
