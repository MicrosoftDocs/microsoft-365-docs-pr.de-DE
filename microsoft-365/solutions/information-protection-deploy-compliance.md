---
title: Verwenden des Compliance-Managers zum Verwalten von Verbesserungs Aktionen
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
description: In diesem Artikel erfahren Sie, wie Sie mit der Kompatibilitätsbewertung und dem Compliance-Manager ihr Schutzniveau für personenbezogene Daten verbessern.
ms.openlocfilehash: 5b41fa9fc52253d415a22aaa3422a87c4f1bda7c
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377099"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Verwenden des Compliance-Managers zum Verwalten von Verbesserungs Aktionen

Microsoft Compliance Manager unterstützt Sie bei der Verwaltung von Verbesserungen im Zusammenhang mit Datenschutzbestimmungen wie der [allgemeinen Datenschutzverordnung (dsgvo)](../compliance/gdpr.md), dem [California Consumer Protection Act CCPA)](../compliance/ccpa-faq.md), dem HIPAA-HITECH (US Health Care Privacy Act) und dem Brazil Data Protection Act (LGPD).

In diesem Artikel werden Anleitungen zur Verwendung dieses Tools für Datenschutzzwecke erläutert.

>[!Note]
>Empfehlungen des Compliance-Managers sollten nicht als eine Garantie für Compliance interpretiert werden. Es liegt an Ihnen, die Effektivität von Kunden Kontrollen pro ihrer regulatorischen Umgebung zu bewerten und zu validieren. Diese Dienste unterliegen den allgemeinen Geschäftsbedingungen in den [Online Dienstbedingungen](https://go.microsoft.com/fwlink/?linkid=2108910). Siehe auch [Leitfaden zur Lizenzierung von Microsoft 365 für Sicherheit und Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)
>

## <a name="getting-started-with-compliance-manager"></a>Erste Schritte mit Compliance-Manager

#### <a name="what-is-compliance-manager"></a>Was ist Compliance-Manager?

[Compliance-Manager](../compliance/compliance-manager.md) ist ein Workflow basiertes Risiko Bewertungstool im Microsoft 365 Compliance Center zum Verwalten von behördlichen Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud Services. Im Rahmen Ihres Microsoft 365-oder Azure Active Directory (Azure AD)-Abonnements unterstützt Sie Compliance-Manager beim Verwalten der behördlichen Compliance im Rahmen des Modells für die gemeinsame Verantwortung für Microsoft Cloud Services.

**Gebrauchsfertige Bewertungen**

Compliance-Manager stellt vorgefertigte Vorlagen zum [Erstellen von Assessments](../compliance/compliance-manager-assessments.md) bereit, die an datenschutzbezogenen Vorschriften wie dsgvo und HIPAA/HITECH ausgerichtet sind. Die Vorlagen verfügen über integrierte Steuerungs Zuordnungen, die Sie bei der Durchführung von Verbesserungs Aktionen zur Erfüllung der Anforderungen der Verordnung unterstützen. Jede Bewertung enthält Informationen zu den Steuerelementen, die jede Verordnung spezifisch für den Zieldienst aufruft, aufgeschlüsselt nach Steuerelementen, die Sie verwalten, und steuert, welche Microsoft verwaltet. 

Mithilfe einer vordefinierten Vorlage können Sie schnell mit Risikobewertungen beginnen. Wenn Sie mit Compliance-Manager besser vertraut sind, können Sie eine vordefinierte Vorlage anpassen, indem Sie eigene Steuerelemente und Verbesserungs Aktionen hinzufügen, oder Sie können eigene benutzerdefinierte Bewertungen erstellen, die den Anforderungen Ihrer Organisation entsprechen.

Zeigen Sie die [vollständige Liste der](../compliance/compliance-manager-templates-list.md) vom Compliance-Manager bereitgestellten Bewertungs Vorlagen an.

**Echt Zeit Kompatibilitätsbewertung**

Compliance-Manager bietet Ihnen außerdem eine Konformitätsbewertung, die Ihren Fortschritt beim Abschließen empfohlener Verbesserungs Aktionen innerhalb von Steuerelementen misst. Sie können diese Bewertung zum Überwachen des Fortschritts und zum Priorisieren von Aktionen basierend auf Ihrem Potenzial zur Verringerung des Risikos verwenden.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>Verwenden des Compliance-Manager-schnellstarthandbuchs

Das [Compliance-Manager-Schnellstart](../compliance/compliance-manager-quickstart.md) Handbuch enthält graduierte Schritte und Links zu wichtigen Ressourcen, die Sie bei der Arbeit mit Compliance-Manager unterstützen:

- [Erster Besuch: sich mit Compliance-Manager vertraut machen](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Arbeiten mit Ihrem Compliance-Manager-Dashboard
    - Grundlegendes zur Konformitätsbewertung
    - Kennenlernen von Verbesserungs Aktionen
    - Grundlegendes zu Bewertungen und Vorlagen
- [Hochfahren: Configure Compliance Manager to manage your Compliance Activities](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Erstellen und Verwalten Ihrer ersten Bewertung
    - Durchführen von Implementierungs-und Test arbeiten an Verbesserungs Aktionen zum Abschließen von Steuerelementen in ihren Bewertungen
    - Grundlegendes zur Auswirkung unterschiedlicher Aktionen auf das Konformitäts Ergebnis
- [Aufwärtsskalierung: Verwenden Sie erweiterte Funktionen, um Ihre benutzerdefinierten Anforderungen zu erfüllen.](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Erstellen Ihrer benutzerdefinierten Bewertungen zum Nachverfolgen von nicht von Microsoft 365 Produkten
    - Ändern vorhandener Vorlagen zum Hinzufügen oder Entfernen von Steuerelementen
    - Einrichten automatischer Tests von Verbesserungs Aktionen

## <a name="how-your-compliance-score-is-calculated"></a>Berechnung des Konformitätswerts

Das Kompatibilitäts Ergebnis wird basierend auf einer Kombination aus Microsoft-und Kunden verwalteten Steuerelement Implementierungen berechnet. Eine detaillierte Erläuterung finden Sie unter [Compliance Score calculation](../compliance/compliance-score-calculation.md) .

Steuerelementen wird ein Bewertungs Wert zugewiesen, je nachdem, ob Sie obligatorisch oder diskretionäre sind und ob Sie vorbeugend, detektivisch oder Korrektiv sind. Diese stellen gemeinsam das Risiko dar, es nicht im Verhältnis zu anderen Steuerelementen zu implementieren.

Wie im Artikel "Compliance Score Calculation" dargestellt, erhalten vorbeugende Steuerelemente eine höhere Punktzahl als Detektive und korrigierende, und obligatorische Steuerelemente erhalten eine höhere Punktzahl als Ermessens Werte.

Die Administrator-Benutzeroberfläche der Kompatibilitätsbewertung listet diese Parameter weder auf noch bietet Sie die Möglichkeit, nach diesen Parametern zu filtern. Wenn Sie jedoch die zugeordnete Vorlage aus dem Compliance-Manager herunterladen, werden diese Parameter in dem resultierenden Dataset für die meisten Verordnungen aufgelistet.

Für technische Steuerelemente aktualisiert Compliance Manager automatisch das Ergebnis der Verbesserungs Aktion, nachdem die Aktion erfolgreich implementiert und getestet wurde. Andere, nicht technische Kontrollaktionen wie &mdash; die, die betriebsbereit sind oder mit der Dokumentation in Zusammenhangstehen, &mdash; müssen manuell aufgezeichnet werden, bevor die Punkte auf Ihre Punktzahl angerechnet werden.

Sie implementieren auch viele Verbesserungs Aktionen für andere Zwecke &mdash; , beispielsweise die Verwendung von Aufbewahrungs Bezeichnungen aus anderen Gründen als die Einhaltung von Datenschutzbestimmungen &mdash; , sodass Sie eine Gutschrift für die Verwendung einer solchen Funktion erhalten, auch wenn Sie für andere Zwecke verwendet wird und nicht Teil einer vorsätzlichen Compliance-Aktion ist.

Ihre Konformitätsbewertung sollte als relative Maßnahme betrachtet werden, um die Verbesserung im großen Maßstab zu verfolgen. Sie sollten keine perfekte Punktzahl verfolgen.

## <a name="additional-guidance"></a>Zusätzliche Anleitung

Im folgenden finden Sie einige wichtige Tipps für die Verwendung des Compliance-Managers, um die Einhaltung der Datenschutzbestimmungen zu gewährleisten:

- Jede Datenschutzverordnung verfügt über eine Kombination aus technischen Kontrollen, Dokumentations Spezifikationen sowie Betriebs-, Prozess-und Berichtsanforderungen. Alle diese werden in den Verbesserungs Aktionen angezeigt.

- Wenn Sie die Ansicht von Verbesserungs Aktionen auf Ihren Interessenbereich konzentrieren möchten, können Sie auf der Registerkarte **Lösungen** im Compliance-Manager-Administrator nach Aktionstyp filtern. Erfahren Sie mehr über [das Filtern der Compliance-Manager-Dashboardansicht](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).

- Die relative Wichtigkeit und Priorität der im Compliance-Manager identifizierten Verbesserungs Aktionen sollten als Teil einer umfassenderen Risikoüberprüfung zusammen mit dem Datenschutzrisiko betrachtet werden, das Sie in Ihrer Organisation für die Verwaltung bestimmt haben.

- Selbst bei der Aggregation von Verbesserungs Aktionen über mehrere regulatorische Anforderungen hinweg werden, wenn die Regel Bewertungs Vorlagen für dsgvo, LGPD, CCPA und HIPAA-HITECH ausgewählt werden, beispielsweise fast 400 Verbesserungs Aktionen im Compliance-Manager aufgeführt. Um diese lange Liste besser in Angriff zu nehmen, verwenden Sie den Filter zur Verbesserung der Aktion, um die Ergebnismenge auf eine besser verwaltbare Liste zu reduzieren.

- Der categories-Filter bietet eine Möglichkeit zum Filtern von Verbesserungs Aktionen durch logische Gruppierung, die die nachverfolgen, verhindern, schützen, beibehalten und untersuchen von Artikeln in dieser Gesamtlösung an ausrichten.

- Einige der Steuerelemente, die in den Verbesserungs Aktionen aufgeführt sind, sind möglicherweise direkter an einen bestimmten Regelungs Artikel gebunden, während andere Steuerelemente indirekt mit dem Geist einer Verordnung in Verbindung gebracht werden können, und viele Male handelt es sich um einfach Empfohlene Aktivitäten oder bewährte Methoden.