---
title: Planen der Kommunikationscompliance
description: Erfahren Sie mehr über die Planung der Verwendung von Kommunikationskonformität in Ihrer Organisation.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: d64edc9d80722080db18c45127bfc82110d1ea9e
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131537"
---
# <a name="plan-for-communication-compliance"></a>Planen der Kommunikationscompliance

Bevor Sie mit der [Kommunikationskonformität](communication-compliance.md) in Ihrer Organisation beginnen, gibt es wichtige Planungsaktivitäten und Überlegungen, die von Ihren Informationstechnologie- und Compliancemanagementteams überprüft werden sollten. Ein sorgfältiges Verständnis und eine sorgfältige Planung der Bereitstellung in den folgenden Bereichen tragen dazu bei, dass Ihre Implementierung und Verwendung von Kommunikations-Compliance-Features reibungslos funktioniert und an die bewährten Methoden für die Lösung angepasst wird.

## <a name="work-with-stakeholders-in-your-organization"></a>Zusammenarbeit mit Interessengruppen in Ihrer Organisation

Identifizieren Sie die geeigneten Beteiligten in Ihrer Organisation, die zusammenarbeiten sollen, um Aktionen zu Kommunikationskonformitätswarnungen zu ergreifen. Einige empfohlene Interessengruppen, die in die anfängliche [](communication-compliance.md#workflow) Planung und den Workflow für die End-to-End-Kommunikationskonformität integriert werden sollten, sind Personen aus den folgenden Bereichen Ihrer Organisation:

- Informationstechnologie
- Compliance
- Datenschutz
- Sicherheit
- Personalwesen
- Rechtliche Hinweise

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Planen des Untersuchungs- und Korrekturworkflows

Wählen Sie dedizierte Beteiligte aus, um die Warnungen und Fälle in regelmäßigen Abständen im Microsoft 365 [zu überwachen und zu überprüfen.](https://compliance.microsoft.com/) Verstehen Sie, wie Sie Benutzern und Beteiligten unterschiedliche Rollengruppen für die Kommunikationskonformität in Ihrer Organisation zuweisen.

Je nachdem, wie Sie Kommunikationsrichtlinien und Warnungen verwalten möchten, müssen Sie Benutzern eine oder mehrere Rollengruppen für Administratoren, Prüfer und Ermittler zuweisen. Sie haben die Möglichkeit, Benutzer bestimmten Rollengruppen zuzuordnen, um verschiedene Sätze von Kommunikationskonformitätsfeatures zu verwalten. Sie können auch festlegen, dass alle Benutzer der Kommunikationskonformität der Rollengruppe "Kommunikationskonformität" zugewiesen werden. Verwenden Sie eine einzelne Rollengruppe oder mehrere Gruppen, um Ihre Anforderungen an die Complianceverwaltung optimal zu erfüllen.

Planen Sie die Auswahl dieser Rollengruppenoptionen beim Konfigurieren der Kommunikationskonformität:

|**Rolle**|**Rollenberechtigungen**|
|:-----|:-----|
| **Kommunikationskonformität** | Verwenden Sie diese Rollengruppe, um die Kommunikationskonformität für Ihre Organisation in einer einzigen Gruppe zu verwalten. Durch Hinzufügen aller Benutzerkonten für designierte Administratoren, Analysten, Ermittler und Viewer können Sie Berechtigungen für die Kommunikationskonformität in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für die Kommunikationskonformität. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit der Kommunikationskonformität zu beginnen und ist für Organisationen geeignet, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind. |
| **Kommunikations-Compliance-Administrator** | Verwenden Sie diese Rollengruppe, um zunächst die Kommunikationskonformität zu konfigurieren und später Administratoren der Kommunikationskonformität in eine definierte Gruppe zu trennen. Benutzer, die dieser Rollengruppe zugewiesen sind, können Kommunikationskonformitätsrichtlinien, globale Einstellungen und Rollengruppenzuweisungen erstellen, lesen, aktualisieren und löschen. Benutzer, die dieser Rollengruppe zugewiesen sind, können keine Benachrichtigungen anzeigen. |
| **Communication Compliance Analyst** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die als Kommunikations-Compliance-Analysten fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien anzeigen, an denen sie als Prüfer zugewiesen sind, Nachrichtenmetadaten (nicht Nachrichteninhalte) anzeigen, an zusätzliche Prüfer eskalieren oder Benachrichtigungen an Benutzer senden. Analysten können ausstehende Warnungen nicht auflösen. |
| **Kommunikations-Compliance-Prüfer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die als Ermittler für die Kommunikationskonformität fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Nachrichtenmetadaten und -inhalte anzeigen, an zusätzliche Prüfer eskalieren, auf einen Advanced eDiscovery-Fall eskalieren, Benachrichtigungen an Benutzer senden und die Warnung auflösen. |
| **Communication Compliance Viewer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die Kommunikationsberichte verwalten. Benutzer, die dieser Rollengruppe zugewiesen sind, können auf der Homepage der Kommunikationskonformität auf alle Berichts-Widgets zugreifen und alle Berichte zur Kommunikationskonformität anzeigen. |

## <a name="plan-for-policies"></a>Planen von Richtlinien

Das Erstellen von Richtlinien zur [](communication-compliance-feature-reference.md#policy-templates) Kommunikationskonformität ist mit den vordefinierten Vorlagen für anstößige Sprache, vertrauliche Informationen und behördliche Compliance schnell und einfach. Benutzerdefinierte Richtlinien zur Kommunikationskonformität ermöglichen die Flexibilität beim Erkennen und Ermitteln von Problemen, die für Ihre Organisation und Anforderungen spezifisch sind.

Berücksichtigen Sie bei der Planung von Richtlinien zur Kommunikationskonformität die folgenden Bereiche:

- Erwägen Sie, alle Benutzer in Ihrer Organisation als In-Scope für Ihre Kommunikationskonformitätsrichtlinien zu verwenden. Die Identifizierung bestimmter Benutzer als in-Scope für einzelne Richtlinien ist unter bestimmten Umständen hilfreich, die meisten Organisationen sollten jedoch alle Benutzer in Kommunikationskonformitätsrichtlinien enthalten, die für die Erkennung von Belästigungen oder Benachteiligung optimiert sind.
- Um das Setup zu vereinfachen, sollten Sie Gruppen für Personen erstellen, die ihre Kommunikation überprüfen müssen. Wenn Sie Gruppen verwenden; Sie benötigen möglicherweise mehrere. Zum Beispiel, wenn Sie die Kommunikation zwischen zwei verschiedenen Personengruppen überprüfen möchten oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht wird.
- Konfigurieren Sie den Prozentsatz der Kommunikation, der zu 100 % überprüft werden soll, um sicherzustellen, dass Richtlinien alle Probleme lösen, die bei der Kommunikation für Ihre Organisation von Bedeutung sind.
- Sie können die Kommunikation aus [Drittanbieterquellen](communication-compliance-feature-reference.md#supported-communication-types) auf Daten überprüfen, die in Postfächer in Ihrer Organisation Microsoft 365 werden. Um die Kommunikation auf diesen Plattformen zu überprüfen, müssen Sie einen Connector für diese Dienste konfigurieren, bevor Nachrichten, die Richtlinienbedingungen erfüllen, von der Kommunikationsrichtlinie überwacht werden.
- Richtlinien können andere Überwachungssprachen als Englisch in benutzerdefinierten Kommunikationskonformitätsrichtlinien unterstützen. Erstellen Sie [ein benutzerdefiniertes](communication-compliance-feature-reference.md#custom-keyword-dictionaries) Schlüsselwortwörterbuch mit anstößigen Wörtern in der Sprache Ihrer Wahl, oder erstellen Sie ein eigenes Machine-Learning-Modell mit trainierbaren Klassifizierungen [in](classifier-get-started-with.md) Microsoft 365.
- Alle Organisationen haben unterschiedliche Kommunikationsstandards und Richtlinienanforderungen. Überwachen Sie mithilfe von [](communication-compliance-feature-reference.md#conditional-settings) Richtlinienbedingungen für die Kommunikationskonformität auf bestimmte Schlüsselwörter oder auf bestimmte Informationstypen mit [benutzerdefinierten Typen vertraulicher Informationen.](create-a-custom-sensitive-information-type.md)

## <a name="ready-to-get-started"></a>Sind Sie bereit zu beginnen?

Informationen zum Konfigurieren der Kommunikationskonformität für Ihre Microsoft 365-Organisation finden Sie unter Konfigurieren der Kommunikationskonformität für [Microsoft 365](communication-compliance-configure.md) oder in der Fallstudie für [Contoso](communication-compliance-case-study.md) und wie sie schnell eine Kommunikationskonformitätsrichtlinie zur Überwachung auf anstößige Sprache in Microsoft Teams, Exchange Online und Yammer konfiguriert haben.
