---
title: Planen der Kommunikation Compliance
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
ms.openlocfilehash: 214c5376d4c074525253707e181eee69cefff85e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045850"
---
# <a name="plan-for-communication-compliance"></a>Planen der Kommunikation Compliance

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

Wählen Sie dedizierte Bearbeiter aus, um die Warnungen auf einer regulären Kadenz im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)zu überwachen und zu überprüfen. Denken Sie daran, Sie müssen [eine neue Rollengruppe erstellen](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) , um Berechtigungen für Bearbeiter mit dem **Aufsichts Überprüfungs Administrator**, der **Fallverwaltung**, dem **Kompatibilitäts Administrator**und den **Überprüfungs** Rollen zu aktivieren, um Nachrichten mit Richtlinien Übereinstimmungen zu untersuchen und zu beheben.

## <a name="plan-for-policies"></a>Planen von Richtlinien

Das Erstellen von Richtlinien für die Kommunikations Konformität ist schnell und einfach mit [vordefinierten Vorlagen](communication-compliance-feature-reference.md#policy-templates) für anstößige Sprache, vertrauliche Informationen und behördliche Compliance. Benutzerdefinierte Kommunikationsrichtlinien ermöglichen die Flexibilität bei der Erkennung und Untersuchung von Problemen, die für Ihre Organisation und Anforderungen spezifisch sind.

Berücksichtigen Sie bei der Planung von Kommunikations Konformitätsrichtlinien Folgendes:

- Sie sollten alle Benutzer in Ihrer Organisation als im Rahmen ihrer Kommunikationsrichtlinien Konformität hinzufügen. Das Identifizieren bestimmter Benutzer als in-Scope für einzelne Richtlinien ist unter bestimmten Umständen nützlich, allerdings sollten die meisten Organisationen alle Benutzer in Kommunikationsrichtlinien einbinden, die für die Erkennung von Belästigung oder Diskriminierung optimiert sind.
- Um das Setup zu vereinfachen, sollten Sie Gruppen für Personen erstellen, die Ihre Kommunikation überprüfen müssen. Wenn Sie mit Gruppen arbeiten; möglicherweise benötigen Sie mehrere. Wenn Sie beispielsweise die Kommunikation zwischen zwei unterschiedlichen Personengruppen überprüfen möchten oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht wird.
- Konfigurieren Sie den Prozentsatz der zu überprüfenden Kommunikation mit 100%, um sicherzustellen, dass Richtlinien alle Probleme in der Kommunikation für Ihre Organisation einfangen.
- Sie können die Kommunikation von [Drittanbieterquellen](communication-compliance-feature-reference.md#supported-communication-types) für Daten überprüfen, die in Postfächer in Ihrer Microsoft 365-Organisation importiert wurden. Um eine Überprüfung der Kommunikation in diesen Plattformen einzuschließen, müssen Sie einen Connector für diese Dienste konfigurieren, bevor die Richtlinienbedingungen für Nachrichten von der Kommunikationsrichtlinie überwacht werden.
- Richtlinien können andere Überwachungs Sprachen als Englisch in benutzerdefinierten Richtlinien für die Kommunikations Konformität unterstützen. Erstellen Sie ein [benutzerdefiniertes Keyword-Wörterbuch](communication-compliance-feature-reference.md#custom-keyword-dictionaries) mit anstößigen Wörtern in der Sprache Ihrer Wahl, oder erstellen Sie mithilfe von Lern baren [Klassifizierungen](classifier-getting-started-with.md) in Microsoft 365 ein eigenes Computer Lernmodell.
- Alle Organisationen haben unterschiedliche Kommunikationsstandards und Richtlinienanforderungen. Überwachen Sie nach bestimmten Schlüsselwörtern mithilfe von [Richtlinien für Kommunikationsrichtlinien Bedingungen](communication-compliance-feature-reference.md#conditional-settings) oder Monitor für bestimmte Arten von Informationen mit [benutzerdefinierten Typen vertraulicher Informationen](create-a-custom-sensitive-information-type.md).

## <a name="ready-to-get-started"></a>Sind Sie bereit zu beginnen?

Informationen zum Konfigurieren der Kommunikations Kompatibilität für Ihre Microsoft 365-Organisation finden Sie unter [configure Communication Compliance for Microsoft 365](communication-compliance-configure.md) oder in der [Fallstudie für Contoso](communication-compliance-case-study.md) und dazu, wie Sie eine Kommunikations Konformitätsrichtlinie für die Überwachung anstößiger Sprachen in Microsoft Teams, Exchange Online und Jammer Kommunikation schnell konfiguriert haben.
