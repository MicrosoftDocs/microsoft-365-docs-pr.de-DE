---
title: Verwalten von Verbesserungsmaßnahmen mithilfe des Compliance-Managers
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
description: Erfahren Sie, wie Sie Compliance Score und Compliance Manager verwenden, um Ihr Schutzniveau für personenbezogene Daten zu verbessern.
ms.openlocfilehash: 87131ea65661e8285fd7c3b36a87c79b618348d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918570"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Verwalten von Verbesserungsmaßnahmen mithilfe des Compliance-Managers

Microsoft Compliance Manager kann Ihnen dabei helfen, Verbesserungen im Zusammenhang mit Datenschutzbestimmungen wie der Allgemeinen Datenschutzverordnung [(DSGVO)](/compliance/regulatory/gdpr)der Europäischen Union, dem California [Consumer Protection Act CCPA)](/compliance/regulatory/ccpa-faq), HIPAA-HITECH (US Health Care Privacy Act) und dem Brazil Data Protection Act (LGPD) zu verwalten.

Dieser Artikel enthält Anleitungen zur Verwendung dieses Tools für Datenschutzzwecke.

>[!Note]
>Empfehlungen des Compliance-Managers sollten nicht als eine Garantie für Compliance interpretiert werden. Es liegt an Ihnen, die Effektivität von Kundenkontrollen nach Ihrer gesetzlichen Umgebung zu bewerten und zu überprüfen. Diese Dienste unterliegen den Allgemeinen Geschäftsbedingungen in den [Onlinedienstbedingungen](https://go.microsoft.com/fwlink/?linkid=2108910). Siehe auch [Microsoft 365 Lizenzierungsanleitung für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)
>

## <a name="getting-started-with-compliance-manager"></a>Erste Schritte mit Compliance Manager

#### <a name="what-is-compliance-manager"></a>Was ist Compliance Manager

[Compliance Manager](../compliance/compliance-manager.md) ist ein workflowbasiertes Risikobewertungstool im Microsoft 365 Compliance Center für die Verwaltung behördlicher Complianceaktivitäten im Zusammenhang mit Microsoft Cloud Services. Im Rahmen Ihres Microsoft 365 oder Azure Active Directory (Azure AD)-Abonnements hilft Ihnen der Compliance-Manager, die Einhaltung gesetzlicher Bestimmungen im Modell der gemeinsamen Verantwortung für Microsoft Cloud Services zu verwalten.

**Bereit zur Verwendung von Bewertungen**

Compliance Manager bietet vordefinierte [](../compliance/compliance-manager-assessments.md) Vorlagen für das Erstellen von Bewertungen, die an datenschutzbezogenen Bestimmungen wie DSGVO und HIPAA/HITECH ausgerichtet sind. Die Vorlagen verfügen über integrierte Steuerelementzuordnungen, mit deren Hilfe Sie Verbesserungsmaßnahmen ergreifen können, um die Anforderungen der Verordnung zu erfüllen. Jede Bewertung enthält Informationen zu den Steuerelementen, die von jeder Verordnung für den Zieldienst verlangt werden, aufgeschlüsselt nach Steuerelementen, die Sie verwalten und von Microsoft verwaltet werden. 

Die Verwendung einer vordefinierten Vorlage hilft Ihnen, schnell mit Risikobewertungen zu beginnen. Wenn Sie den Compliance Manager besser nutzen, können Sie eine vordefinierte Vorlage anpassen, indem Sie eigene Steuerelemente und Verbesserungsmaßnahmen hinzufügen oder eigene benutzerdefinierte Bewertungen erstellen, die den Anforderungen Ihrer Organisation entsprechen.

Zeigen Sie [die vollständige Liste der vom](../compliance/compliance-manager-templates-list.md) Compliance Manager bereitgestellten Bewertungsvorlagen an.

**Compliance-Bewertung in Echtzeit**

Der Compliance-Manager bietet Ihnen außerdem eine Compliance-Bewertung, die Ihren Fortschritt beim Abschließen empfohlener Verbesserungsmaßnahmen in Steuerelementen misst. Sie können diese Bewertung verwenden, um Ihren Fortschritt zu überwachen und Aktionen basierend auf ihrem Potenzial zur Risiko reduzieren zu priorisieren.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>Verwenden des Schnellstarthandbuchs für Compliance-Manager

Das [Schnellstarthandbuch für Compliance-Manager](../compliance/compliance-manager-quickstart.md) enthält abgestufte Schritte und Links zu wichtigen Ressourcen, die Ihnen bei der Arbeit mit dem Compliance-Manager helfen:

- [Erster Besuch: Machen Sie sich mit Compliance Manager vertraut](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Arbeiten mit Ihrem Compliance -Manager-Dashboard
    - Grundlegendes zu Ihrer Compliance-Bewertung
    - Informationen zu Verbesserungsmaßnahmen
    - Grundlegendes zu Bewertungen und Vorlagen
- [Hochfahren: Konfigurieren von Compliance Manager zum Verwalten Ihrer Complianceaktivitäten](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Erstellen und Verwalten Ihrer ersten Bewertung
    - Durchführen von Implementierungs- und Testarbeiten an Verbesserungsmaßnahmen zum Abschließen von Steuerelementen in Ihren Bewertungen
    - Verstehen, wie sich unterschiedliche Aktionen auf Ihre Compliance-Bewertung auswirken
- [Hochskalieren: Verwenden sie erweiterte Funktionen, um Ihre benutzerdefinierten Anforderungen zu erfüllen](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Erstellen ihrer benutzerdefinierten Bewertungen zum Nachverfolgen nicht Microsoft 365 Produkte
    - Ändern vorhandener Vorlagen zum Hinzufügen oder Entfernen von Steuerelementen
    - Einrichten automatisierter Tests von Verbesserungsmaßnahmen

## <a name="how-your-compliance-score-is-calculated"></a>Berechnung des Konformitätswerts

Ihre Compliance-Bewertung wird basierend auf einer Kombination aus Implementierungen von Microsoft und vom Kunden verwalteten Steuerelementen berechnet. Eine [ausführliche Erläuterung finden Sie unter Berechnung der Compliance-Bewertung.](../compliance/compliance-score-calculation.md)

Steuerelementen wird ein Bewertungswert zugewiesen, der darauf basiert, ob sie obligatorisch oder diskretionär sind und ob sie präventiv, detektivisch oder korrektiv sind. Diese stellen insgesamt das Risiko dar, dass sie im Vergleich zu anderen Steuerelementen nicht implementieren.

Wie im Artikel zur Berechnung der Compliance-Bewertung dargestellt, erhalten vorbeugende Steuerelemente eine höhere Bewertung als Detektiv- und Korrekturmaßnahmen, und obligatorische Steuerelemente erhalten eine höhere Bewertung als diskretionäre Steuerelemente.

Die Benutzeroberfläche des Compliance-Score-Admins listet diese Parameter nicht auf und bietet auch nicht die Möglichkeit, nach diesen zu filtern. Wenn Sie die zugeordnete Vorlage jedoch aus dem Compliance-Manager herunterladen, werden diese Parameter für die meisten Bestimmungen im resultierenden Datensatz aufgeführt.

Bei technischen Steuerelementen aktualisiert der Compliance-Manager automatisch die Bewertung der Verbesserungsaktion, sobald die Aktion erfolgreich implementiert und getestet wurde. Andere, nicht technische Kontrollaktionen, z. B. betriebsbereite oder dokumentationsbezogene Aktionen, müssen manuell als implementiert aufgezeichnet werden, bevor Punkte auf Ihre &mdash; &mdash; Punktzahl angezählt werden.

Sie viele implementieren auch bestimmte Verbesserungsmaßnahmen für andere Zwecke, z. B. die Verwendung von Aufbewahrungsbezeichnungen aus anderen Gründen als der Einhaltung der Datenschutzbestimmungen, damit Sie eine Anerkennung für die Verwendung eines solchen Features erhalten, auch wenn es für andere Zwecke verwendet wird, und nicht Teil einer absichtlichen &mdash; &mdash; Complianceaktion.

Ihre Compliance-Bewertung sollte als relative Maßnahme betrachtet werden, um verbesserungen auf einem breiten Maßstab nachverfolgt zu werden. Sie sollten keine perfekte Bewertung verfolgen.

## <a name="additional-guidance"></a>Zusätzliche Anleitung

Im Folgenden finden Sie einige wichtige Tipps für die Verwendung des Compliance-Managers, um Die Einhaltung der Datenschutzbestimmungen zu erreichen:

- Jede Datenschutzverordnung verfügt über eine Kombination aus technischen Kontrollen, Dokumentationsspezifikationen sowie Betriebs-, Prozess- und Berichtspflichten. All diese werden in den Verbesserungsmaßnahmen gezeigt.

- Um die Ansicht von Verbesserungsmaßnahmen auf Ihren Interessensbereich zu konzentrieren, können Sie auf der Registerkarte Lösungen im Compliance-Manager-Administrator nach Aktionstyp filtern.  Erfahren Sie mehr über [das Filtern Ihrer Compliance -Manager-Dashboardansicht](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).

- Die relative Wichtigkeit und Priorität von Verbesserungsmaßnahmen, die im Compliance Manager identifiziert werden, sollten als Teil einer umfassenderen Risikoüberprüfung zusammen mit dem Datenschutzrisiko betrachtet werden, das Sie für Ihre Organisation verwalten müssen.

- Selbst bei der Aggregation von Verbesserungsmaßnahmen über mehrere behördliche Anforderungen hinweg werden beispielsweise fast 400 Verbesserungsmaßnahmen im Compliance Manager aufgelistet, wenn die Vorlagen für die Regulierungsbewertung für DSGVO, LGPD, CCPA und HIPAA-HITECH ausgewählt sind. Um diese lange Liste besser zu bewältigen, verwenden Sie den Filter zur Verbesserungsaktion, um das Ergebnis auf eine verwaltbarere Liste zu reduzieren.

- Der Filter Categories bietet eine Möglichkeit zum Filtern von Verbesserungsmaßnahmen durch logische Gruppierung, an der sich die Artikel "Track", "Prevent", "Protect", "Retain" und "Investigate" in dieser Gesamtlösung ausrichten.

- Einige der in den Verbesserungsmaßnahmen aufgeführten Steuerelemente können als direkter an einen bestimmten Regulatorischen Artikel gebunden betrachtet werden, während andere Steuerelemente indirekter mit dem Geist einer Verordnung verknüpft sind und oft nur empfohlene Aktivitäten oder bewährte Methoden sind.