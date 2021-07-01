---
title: Verwenden des Compliance-Managers zum Verwalten von Verbesserungsmaßnahmen
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Erfahren Sie, wie Sie die Compliancebewertung und den Compliance-Manager verwenden, um Ihren Schutz für personenbezogene Daten zu verbessern.
ms.openlocfilehash: 26e9f54ce77869f4f6ef07c18147483628ddc223
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229299"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Verwenden des Compliance-Managers zum Verwalten von Verbesserungsmaßnahmen

Microsoft Compliance Manager kann Ihnen bei der Verwaltung von Verbesserungen im Zusammenhang mit Datenschutzbestimmungen helfen, z. B. der [Datenschutz-Grundverordnung der](/compliance/regulatory/gdpr)Europäischen Union (DSGVO), dem [California Consumer Protection Act CCPA),](/compliance/regulatory/ccpa-faq)HIPAA-HITECH (US Health Care Privacy Act) und dem Brazil Data Protection Act (LGPD).

Dieser Artikel enthält Anleitungen zur Verwendung dieses Tools für Datenschutzzwecke.

> [!NOTE]
> Empfehlungen des Compliance-Managers sollten nicht als eine Garantie für Compliance interpretiert werden. Es liegt an Ihnen, die Effektivität von Kundenkontrollen gemäß Ihrer regulatorischen Umgebung zu bewerten und zu überprüfen. Diese Dienste unterliegen den Geschäftsbedingungen in den Nutzungsbedingungen für [Onlinedienste.](https://go.microsoft.com/fwlink/?linkid=2108910) Siehe auch [Microsoft 365 Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

## <a name="getting-started-with-compliance-manager"></a>Erste Schritte mit Compliance-Manager

#### <a name="what-is-compliance-manager"></a>Was ist Compliance-Manager?

[Compliance-Manager](../compliance/compliance-manager.md) ist ein workflowbasiertes Tool zur Risikobewertung im Microsoft 365 Compliance Center für die Verwaltung gesetzlicher Complianceaktivitäten im Zusammenhang mit Microsoft-Clouddiensten. Im Rahmen Ihres Microsoft 365- oder Azure Active Directory (Azure AD)-Abonnements hilft Ihnen Compliance-Manager bei der Verwaltung der einhaltung gesetzlicher Vorschriften im Rahmen des Modells der gemeinsamen Verantwortung für Microsoft-Clouddienste.

**Bereit für die Verwendung von Bewertungen**

Compliance-Manager bietet vordefinierte Vorlagen zum [Erstellen von Bewertungen,](../compliance/compliance-manager-assessments.md) die an Datenschutzbestimmungen wie DSGVO und HIPAA/HITECH ausgerichtet sind. Die Vorlagen verfügen über eine integrierte Steuerelementzuordnung, mit der Sie Verbesserungsmaßnahmen ergreifen können, um die Anforderungen der Verordnung zu erfüllen. Jede Bewertung enthält Informationen zu den Steuerelementen, die jede Verordnung speziell für den Zieldienst aufruft, aufgeschlüsselt nach den von Ihnen verwalteten Steuerelementen und den von Microsoft verwalteten Steuerelementen.

Die Verwendung einer vordefinierten Vorlage hilft Ihnen bei den ersten Schritten mit Risikobewertungen. Sobald Sie mit der Verwendung des Compliance-Managers vertraut sind, können Sie eine vordefinierte Vorlage anpassen, indem Sie Ihre eigenen Steuerelemente und Verbesserungsmaßnahmen hinzufügen, oder Sie können Ihre eigenen benutzerdefinierten Bewertungen für die Anforderungen Ihrer Organisation erstellen.

Zeigen Sie die vollständige Liste der vom Compliance-Manager bereitgestellten [Bewertungsvorlagen](../compliance/compliance-manager-templates-list.md) an.

**Compliancebewertung in Echtzeit**

Der Compliance-Manager bietet Ihnen auch eine Compliancebewertung, die Ihren Fortschritt bei der Durchführung empfohlener Verbesserungsmaßnahmen innerhalb von Steuerelementen misst. Sie können diese Bewertung verwenden, um Ihren Fortschritt zu überwachen und Aktionen basierend auf ihrem Risiko zu priorisieren.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>Verwenden der Compliance-Manager-Schnellstartanleitung

Der [Compliance-Manager-Schnellstartanleitung](../compliance/compliance-manager-quickstart.md) enthält schrittweise Schritte und Links zu wichtigen Ressourcen, die Ihnen bei der Arbeit mit Compliance-Manager helfen:

- [Erster Besuch: Machen Sie sich mit compliance-Manager vertraut](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Arbeiten mit Ihrem Compliance-Manager-Dashboard
    - Grundlegendes zur Compliancebewertung
    - Learning zu Verbesserungsmaßnahmen
    - Grundlegendes zu Bewertungen und Vorlagen
- [Hochfahren: Konfigurieren des Compliance-Managers zum Verwalten Ihrer Complianceaktivitäten](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Erstellen und Verwalten Ihrer ersten Bewertung
    - Durchführen von Implementierungs- und Testarbeiten zu Verbesserungsmaßnahmen, um die Kontrollen in Ihren Bewertungen abzuschließen
    - Verstehen, wie sich unterschiedliche Aktionen auf Ihre Compliancebewertung auswirken
- [Hochskalieren: Verwenden sie erweiterte Funktionen, um Ihre benutzerdefinierten Anforderungen zu erfüllen](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Erstellen ihrer benutzerdefinierten Bewertungen zum Nachverfolgen von Nicht-Microsoft 365-Produkten
    - Ändern vorhandener Vorlagen zum Hinzufügen oder Entfernen von Steuerelementen
    - Einrichten des automatisierten Testens von Verbesserungsmaßnahmen

## <a name="how-your-compliance-score-is-calculated"></a>Berechnung des Konformitätswerts

Ihre Compliancebewertung wird basierend auf einer Kombination aus Microsoft- und vom Kunden verwalteten Steuerelementimplementierungen berechnet. Eine ausführliche Erläuterung finden Sie in der [Berechnung der Compliancebewertung.](../compliance/compliance-score-calculation.md)

Steuerelementen wird ein Bewertungswert zugewiesen, der davon abhängt, ob sie obligatorisch oder diskretionär sind und ob sie vorbeugend, erkennend oder korrigierend sind. Diese stellen zusammen das Risiko dar, dass sie nicht im Verhältnis zu anderen Steuerelementen implementiert werden.

Wie im Artikel zur Berechnung der Compliancebewertung dargestellt, erhalten präventive Steuerelemente eine höhere Bewertung als Erkennungs- und Korrekturmaßnahmen, und obligatorische Steuerelemente erhalten eine höhere Bewertung als diskretionäre.

Die Administrator-Benutzeroberfläche der Compliancebewertung listet diese Parameter nicht auf und bietet auch nicht die Möglichkeit, nach diesen zu filtern. Wenn Sie die zugeordnete Vorlage jedoch vom Compliance-Manager herunterladen, listet der resultierende Datensatz diese Parameter für die meisten Vorschriften auf.

Bei technischen Kontrollen aktualisiert der Compliance-Manager automatisch die Bewertung der Verbesserungsmaßnahmen, sobald die Aktion erfolgreich implementiert und getestet wurde. Andere, nicht technische &mdash; Kontrollaktionen, z. B. solche, die betriebsbereit sind oder sich auf Die Dokumentation &mdash; beziehen, müssen manuell als implementiert aufgezeichnet werden, bevor Punkte in Richtung Ihres Punktestands zählen.

Viele implementieren auch bestimmte Verbesserungsmaßnahmen für andere Zwecke, &mdash; z. B. die Verwendung von Aufbewahrungsbezeichnungen aus anderen Gründen als der Einhaltung &mdash; von Datenschutzbestimmungen, sodass Sie eine Gutschrift für die Verwendung eines solchen Features erhalten, auch wenn es für andere Zwecke verwendet wird und nicht Teil einer absichtlichen Compliance-Aktion ist.

Ihre Compliancebewertung sollte als relative Maßnahme betrachtet werden, um Verbesserungen in großem Umfang nachzuverfolgen. Sie sollten keine perfekte Punktzahl verfolgen.

## <a name="additional-guidance"></a>Zusätzliche Anleitung

Hier sind einige wichtige Tipps für die Verwendung des Compliance-Managers, um die Einhaltung der Datenschutzbestimmungen zu erreichen:

- Jede Datenschutz-Verordnung verfügt über eine Kombination aus technischen Kontrollen, Dokumentationsspezifikationen sowie betrieblichen, Prozess- und Berichtsanforderungen. Alle diese werden in den Verbesserungsmaßnahmen angezeigt.

- Um die Ansicht von Verbesserungsmaßnahmen auf Ihren Interessenbereich zu konzentrieren, können Sie auf der Registerkarte **"Lösungen"** im Compliance-Manager-Administrator nach Aktionstyp filtern. Erfahren Sie mehr über [das Filtern ihrer Compliance-Manager-Dashboardansicht.](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)

- Die relative Bedeutung und Priorität von Verbesserungsmaßnahmen, die im Compliance-Manager identifiziert werden, sollten als Teil einer umfassenderen Risikoüberprüfung zusammen mit dem Datenschutzrisiko betrachtet werden, das Sie für Ihre Organisation festgelegt haben.

- Selbst bei der Aggregation von Verbesserungsmaßnahmen über mehrere gesetzliche Anforderungen hinweg, wenn die Vorlagen für die Regulierungsbewertung für DSGVO, LGPD, CCPA und HIPAA-HITECH ausgewählt sind, werden beispielsweise fast 400 Verbesserungsmaßnahmen im Compliance-Manager aufgeführt. Um diese lange Liste besser zu bewältigen, verwenden Sie den Filter für Verbesserungsmaßnahmen, um das Resultset auf eine besser verwaltbare Liste zu reduzieren.

- Der Filter "Kategorien" bietet eine Möglichkeit, Verbesserungsmaßnahmen nach logischer Gruppierung zu filtern, an der die Artikel "Nachverfolgen", "Verhindern", "Schützen", "Aufbewahren" und "Untersuchen" in dieser Gesamtlösung ausgerichtet sind.

- Einige der in den Verbesserungsmaßnahmen aufgeführten Kontrollen werden möglicherweise als direkter an einen bestimmten regulatorischen Artikel gebunden betrachtet, während andere Steuerelemente indirekter mit der Einführung einer Verordnung verknüpft sind und oft einfach empfohlene Aktivitäten oder bewährte Methoden sind.