---
title: Planen der Kommunikationscompliance
description: Erfahren Sie mehr über die Planung der Verwendung der Kommunikations Konformität in Ihrer Organisation.
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

Bevor Sie mit der [Kommunikation](communication-compliance.md) in Ihrer Organisation beginnen, gibt es wichtige Planungsaktivitäten und-Überlegungen, die von ihren Informationstechnologie-und Compliance-Verwaltungsteams überprüft werden sollten. Durch ein gründliches Verständnis und die Planung der Bereitstellung in den folgenden Bereichen können Sie sicherstellen, dass die Implementierung und Verwendung von Kommunikations Kompatibilitätsfeatures reibungslos verläuft und mit den bewährten Methoden für die Lösung abgeglichen wird.

## <a name="work-with-stakeholders-in-your-organization"></a>Arbeiten mit Beteiligten in Ihrer Organisation

Identifizieren Sie die geeigneten Beteiligten in Ihrer Organisation für die Zusammenarbeit bei der Durchführung von Maßnahmen zur Kommunikation Compliance Alerts. Einige empfohlene beteiligte, die in die anfängliche Planung einbezogen werden sollten, und der Workflow für die End-to-End- [Kommunikations Konformität](communication-compliance.md#workflow) sind Personen aus den folgenden Bereichen Ihrer Organisation:

- Informationstechnologie
- Compliance
- Datenschutz
- Sicherheit
- Personalabteilung
- Rechtliche Hinweise

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Planen des unter Such-und Korrektur Workflows

Wählen Sie dedizierte Beteiligte aus, um die Warnungen und Fälle auf einer regulären Kadenz im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)zu überwachen und zu überprüfen. Stellen Sie sicher, dass Sie verstehen, wie Sie Benutzern und Beteiligten unterschiedlichen Kommunikations Compliance-Rollengruppen in Ihrer Organisation zuweisen können.

Je nachdem, wie Sie Kommunikationsrichtlinien und Warnungen verwalten möchten, müssen Sie Benutzer einer oder mehreren Rollengruppen für Administratoren, Prüfer und Ermittler zuweisen. Sie haben die Möglichkeit, Benutzer bestimmten Rollengruppen zuzuweisen, um verschiedene Sätze von Kompatibilitätsfeatures für die Kommunikation zu verwalten. Oder Sie können beschließen, alle Benutzer der Kommunikations Konformität der Rollengruppe "Kommunikations Konformität" zuzuweisen. Verwenden Sie eine einzelne Rollengruppe oder mehrere Gruppen, um Ihre Anforderungen an die Compliance-Verwaltung am besten anzupassen.

Planen Sie beim Konfigurieren der Kommunikations Kompatibilität eine Auswahl aus diesen Rollengruppen Optionen:

|**Rolle**|**Rollenberechtigungen**|
|:-----|:-----|
| **Kommunikation Compliance** | Verwenden Sie diese Rollengruppe, um die Kommunikations Konformität für Ihre Organisation in einer einzigen Gruppe zu verwalten. Durch Hinzufügen aller Benutzerkonten für designierte Administratoren, Analysten, Ermittler und Betrachter können Sie die Berechtigungen für die Kommunikations Konformität in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für die Kommunikations Konformität. Diese Konfiguration ist die einfachste Möglichkeit, um schnell mit der Kommunikation zu beginnen, und Sie eignet sich gut für Organisationen, die keine separaten Berechtigungen benötigen, die für getrennte Benutzergruppen definiert sind. |
| **Communication Compliance-Administrator** | Verwenden Sie diese Rollengruppe, um die Kommunikationsrichtlinien Konfiguration zu konfigurieren und später Kommunikationsrichtlinien Administratoren in eine definierte Gruppe zu trennen. Benutzer, die dieser Rollengruppe zugewiesen sind, können Kommunikationsrichtlinien, globale Einstellungen und Rollengruppen Zuordnungen erstellen, lesen, aktualisieren und löschen. Benutzer, die dieser Rollengruppe zugewiesen sind, können keine Nachrichten Benachrichtigungen anzeigen. |
| **Communication Compliance Analyst** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Kommunikations Compliance-Analysten fungieren sollen. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien anzeigen, in denen Sie als Bearbeiter zugewiesen werden, Nachrichten Metadaten anzeigen (keine Nachrichteninhalte), an zusätzliche Bearbeiter eskalieren oder Benachrichtigungen an Benutzer senden. Ausstehende Warnungen können von Analysten nicht aufgelöst werden. |
| **Communication Compliance Investigator** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Kommunikations Compliance-Ermittler fungieren sollen. Benutzer, die dieser Rollengruppe zugewiesen sind, können Nachrichten Metadaten und-Inhalte anzeigen, an zusätzliche Bearbeiter eskalieren, zu einem erweiterten eDiscovery-Fall eskalieren, Benachrichtigungen an Benutzer senden und die Warnung lösen. |
| **Communication Compliance Viewer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen für die Verwaltung von Kommunikations Berichten zuzuweisen. Benutzer, die dieser Rollengruppe zugewiesen sind, können auf der Homepage der Communication Compliance auf alle Berichts-Widgets zugreifen und alle Kommunikations Konformitätsberichte anzeigen. |

## <a name="plan-for-policies"></a>Planen von Richtlinien

Das Erstellen von Richtlinien für die Kommunikations Konformität ist schnell und einfach mit [vordefinierten Vorlagen](communication-compliance-feature-reference.md#policy-templates) für anstößige Sprache, vertrauliche Informationen und behördliche Compliance. Benutzerdefinierte Kommunikationsrichtlinien ermöglichen die Flexibilität bei der Erkennung und Untersuchung von Problemen, die für Ihre Organisation und Anforderungen spezifisch sind.

Berücksichtigen Sie bei der Planung von Kommunikations Konformitätsrichtlinien die folgenden Bereiche:

- Sie sollten alle Benutzer in Ihrer Organisation als im Rahmen ihrer Kommunikationsrichtlinien Konformität hinzufügen. Das Identifizieren bestimmter Benutzer als in-Scope für einzelne Richtlinien ist unter bestimmten Umständen nützlich, allerdings sollten die meisten Organisationen alle Benutzer in Kommunikationsrichtlinien einbinden, die für die Erkennung von Belästigung oder Diskriminierung optimiert sind.
- Um das Setup zu vereinfachen, sollten Sie Gruppen für Personen erstellen, die Ihre Kommunikation überprüfen müssen. Wenn Sie mit Gruppen arbeiten; möglicherweise benötigen Sie mehrere. Zum Beispiel, wenn Sie die Kommunikation zwischen zwei verschiedenen Personengruppen überprüfen möchten oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht wird.
- Konfigurieren Sie den Prozentsatz der zu überprüfenden Kommunikation mit 100%, um sicherzustellen, dass Richtlinien alle Probleme in der Kommunikation für Ihre Organisation einfangen.
- Sie können die Kommunikation von [Drittanbieterquellen](communication-compliance-feature-reference.md#supported-communication-types) für Daten überprüfen, die in Postfächer in Ihrer Microsoft 365-Organisation importiert wurden. Um eine Überprüfung der Kommunikation in diesen Plattformen einzuschließen, müssen Sie einen Connector für diese Dienste konfigurieren, bevor die Richtlinienbedingungen für Nachrichten von der Kommunikationsrichtlinie überwacht werden.
- Richtlinien können andere Überwachungs Sprachen als Englisch in benutzerdefinierten Richtlinien für die Kommunikations Konformität unterstützen. Erstellen Sie ein [benutzerdefiniertes Keyword-Wörterbuch](communication-compliance-feature-reference.md#custom-keyword-dictionaries) mit anstößigen Wörtern in der Sprache Ihrer Wahl, oder erstellen Sie mithilfe von Lern baren [Klassifizierungen](classifier-get-started-with.md) in Microsoft 365 ein eigenes Computer Lernmodell.
- Alle Organisationen haben unterschiedliche Kommunikationsstandards und Richtlinienanforderungen. Überwachen Sie nach bestimmten Schlüsselwörtern mithilfe von [Richtlinien für Kommunikationsrichtlinien Bedingungen](communication-compliance-feature-reference.md#conditional-settings) oder Monitor für bestimmte Arten von Informationen mit [benutzerdefinierten Typen vertraulicher Informationen](create-a-custom-sensitive-information-type.md).

## <a name="ready-to-get-started"></a>Sind Sie bereit loszulegen?

Informationen zum Konfigurieren der Kommunikations Kompatibilität für Ihre Microsoft 365-Organisation finden Sie unter [configure Communication Compliance for Microsoft 365](communication-compliance-configure.md) oder in der [Fallstudie für Contoso](communication-compliance-case-study.md) und dazu, wie Sie eine Kommunikations Konformitätsrichtlinie für die Überwachung anstößiger Sprachen in Microsoft Teams, Exchange Online und Jammer Kommunikation schnell konfiguriert haben.
