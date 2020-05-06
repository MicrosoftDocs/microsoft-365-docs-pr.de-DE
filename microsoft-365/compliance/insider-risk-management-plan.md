---
title: Planen des Risikomanagements für Insider
description: Hier erfahren Sie, wie Sie die Verwendung von Richtlinien für Insider Risk Management in Ihrer Organisation planen.
keywords: Microsoft 365, Insider Risiko, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 2b2abd68d767f169ea8e20fc349e6314cc6400d5
ms.sourcegitcommit: e55e4747d3b838baacab8985aefc24aac245c431
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44043401"
---
# <a name="plan-for-insider-risk-management"></a>Planen des Risikomanagements für Insider

Bevor Sie mit dem [Insider Risk Management](insider-risk-management.md) in Ihrer Organisation beginnen, müssen Sie wichtige Planungsaktivitäten und-Überlegungen durch Ihre IT-und Compliance-Management Teams überprüfen. Durch ein gründliches Verständnis und die Planung der Bereitstellung in den folgenden Bereichen können Sie sicherstellen, dass die Implementierung und Verwendung von Insider Risikomanagement-Features reibungslos verläuft und mit den bewährten Methoden für die Lösung abgestimmt wird.

## <a name="work-with-stakeholders-in-your-organization"></a>Arbeiten mit Beteiligten in Ihrer Organisation

Identifizieren Sie die entsprechenden Beteiligten in Ihrer Organisation für die Zusammenarbeit bei der Durchführung von Aktionen in Warnungen und Fällen für Insider Risiken. Einige empfohlene beteiligte, die in die anfängliche Planung einbezogen werden sollten, und der End-to-End- [Workflow für Insider-Risikomanagement](insider-risk-management.md#workflow) sind Personen aus den folgenden Bereichen Ihrer Organisation:

- Informationstechnologie
- Compliance
- Datenschutz
- Sicherheit
- Personalabteilung
- Rechtliche Hinweise

## <a name="determine-any-regional-compliance-requirements"></a>Bestimmen der regionalen Compliance-Anforderungen

Unterschiedliche geographische und organisatorische Bereiche haben möglicherweise Compliance-und Datenschutzanforderungen, die sich erheblich von anderen Bereichen Ihrer Organisation unterscheiden. Arbeiten Sie mit den Beteiligten in diesen Bereichen zusammen, um sicherzustellen, dass Sie die Compliance-und Datenschutzkontrollen im Insider Risikomanagement verstehen und wie Sie in verschiedenen Bereichen Ihrer Organisation verwendet werden sollten. In einigen Szenarien erfordern Compliance-und Datenschutzanforderungen möglicherweise Richtlinien, mit denen einige Beteiligte anhand von Untersuchungen und Fällen basierend auf dem Fall eines Benutzers oder behördlicher oder Richtlinien mäßiger Anforderungen für den Bereich benannt oder eingeschränkt werden.

Wenn Sie Anforderungen an bestimmte Teilnehmer haben, die an Falluntersuchungen beteiligt sind, die Mitarbeiter in bestimmten Regionen, Rollen oder Abteilungen einbeziehen, sollten Sie möglicherweise separate (auch wenn identische) [Richtlinien für das Insider Risikomanagement](insider-risk-management-policies.md) implementieren, die auf die verschiedenen Regionen und Populationen abzielen. Dadurch wird es für die richtigen beteiligten einfacher, Fälle zu selektieren und zu verwalten, die für Ihre Rollen und Regionen relevant sind. Darüber hinaus sollten Sie in der Lage sein, Prozesse und Richtlinien für Regionen zu erstellen, in denen Prüfer und Prüfer dieselbe Sprache wie die Benutzer sprechen, um den Eskalationsprozess für Warnungen und Fälle beim Insider Risikomanagement zu rationalisieren.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Planen des Workflows für Überprüfung und Untersuchung

Wählen Sie dedizierte Beteiligte aus, um die Warnungen und Fälle auf einer regulären Kadenz im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)zu überwachen und zu überprüfen. Stellen Sie sicher, dass Sie verstehen, wie Sie verschiedenen Beteiligten die verschiedenen Rollengruppen zuordnen, die im Insider Risikomanagement verfügbar sind.

Je nach Struktur Ihres Compliance-Verwaltungsteams haben Sie die Möglichkeit, Benutzer bestimmten Rollengruppen zuzuweisen, um verschiedene Gruppen von Insider Risikomanagement-Features zu verwalten. Wählen Sie unter diese Rollengruppen Optionen beim Konfigurieren des Insider Risikomanagements:

| **Rollengruppe** | **Rollenberechtigungen** |
| :---- | :---------------- |
| **Insider Risiko Management** | Verwenden Sie diese Rollengruppe, um das Insider Risikomanagement für Ihre Organisation in einer einzigen Gruppe zu verwalten. Durch Hinzufügen aller Benutzerkonten für designierte Administratoren, Analysten und Ermittler können Sie die Berechtigungen für das Insider-Risikomanagement in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungen für das Insider Risk Management. Diese Konfiguration ist die einfachste Möglichkeit, um schnell mit dem Insider Risiko-Management zu beginnen, und eignet sich gut für Organisationen, die keine separaten Berechtigungen benötigen, die für getrennte Benutzergruppen definiert werden.|
| **Insider Risk Management-Administrator** | Verwenden Sie diese Rollengruppe, um zunächst das Insider Risikomanagement zu konfigurieren und später Insider Risiko Administratoren in eine definierte Gruppe zu unter trennen.  Benutzer in dieser Rollengruppe können Richtlinien für die Verwaltung von Insider Risiken, globale Einstellungen und Rollengruppen Zuordnungen erstellen, lesen, aktualisieren und löschen. |
| **Insider Risk Management Analysten** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Risikoanalysten für Insider Risiken fungieren sollen. Benutzer in dieser Rollengruppe können auf alle Alerts-, Cases-und Notices-Vorlagen für Insider-Risikomanagement zugreifen. Sie können nicht auf den Insider Risiko-Inhalts-Explorer zugreifen. |
| **Insider Risk Management Investigators** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Insider Risiko-Daten Ermittler fungieren sollen. Benutzer in dieser Rollengruppe können in allen Fällen auf alle Alerts für Insider-Risikomanagement,-Fälle,-Benachrichtigungsvorlagen und den Inhalts-Explorer zugreifen. |

## <a name="understand-requirements-and-dependencies"></a>Grundlegendes zu Anforderungen und Abhängigkeiten

Je nachdem, wie Sie Richtlinien für die Verwaltung von Insider Risiken implementieren möchten, müssen Sie über die entsprechenden Microsoft 365-Lizenzierungs Abonnements verfügen und einige Lösungs Voraussetzungen verstehen und planen.

**Lizenzierung:** Das Insider Risk Management steht im Rahmen einer großen Auswahl von Microsoft 365-Lizenzierungs Abonnements zur Verfügung. Ausführliche Informationen finden Sie im Artikel [Erste Schritte mit Insider-Risikomanagement](insider-risk-management-configure.md#before-you-begin) .

Wenn Sie keinen vorhandenen Microsoft 365 Enterprise E5-Plan haben und das Insider Risk Management testen möchten, können Sie Microsoft 365 zu Ihrem vorhandenen Abonnement [Hinzufügen](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) oder [sich für eine Testversion](https://www.microsoft.com/microsoft-365/enterprise) von Microsoft 365 Enterprise E5 registrieren.

**Richtlinienvorlagen Anforderungen:** Je nach Richtlinienvorlage können Anforderungen erfüllt sein, die Sie vor dem Konfigurieren des Insider Risk Managements in Ihrer Organisation kennen und planen müssen:

- Wenn Sie die **Datendiebstahl Vorlage "departing Employee** " verwenden, müssen Sie einen Microsoft 365-HR-Connector konfigurieren, um regelmäßige Informationen zum Rücktritt und zum Abschlussdatum für Mitarbeiter in Ihrer Organisation zu importieren. Lesen Sie den Abschnitt [Importieren von Daten mit dem HR-Connector](import-hr-data.md) , um Schritt-für-Schritt-Anleitungen zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation zu erhalten.
- Bei Verwendung von **Datenlecks** -Vorlage müssen Sie mindestens eine DLP-Richtlinie (Data Loss Prevention) konfigurieren, um vertrauliche Informationen in Ihrer Organisation zu definieren und Insider Risikowarnungen für DLP-Richtlinienwarnungen mit hohem Schweregrad zu erhalten. Eine schrittweise Anleitung zum Konfigurieren von DLP-Richtlinien für Ihre Organisation finden Sie unter [erstellen, testen und Optimieren eines DLP-Richtlinien](create-test-tune-dlp-policy.md) Themas.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Testen mit einer kleinen Gruppe von Benutzern in einer Produktionsumgebung

Bevor Sie die Lösung weitgehend in Ihrer Produktionsumgebung aktivieren, können Sie die Richtlinien mit einer kleinen Gruppe von Produktionsbenutzern testen, während Sie die erforderlichen Compliance-, Datenschutz-und rechts Prüfungen in Ihrer Organisation durchführen. Für die Bewertung des Insider Risikomanagements in einer Testumgebung müssen Sie simulierte Benutzeraktionen und andere Signale generieren, um Warnungen für die Selektierung und für die Verarbeitung von Fällen zu erstellen. Häufig ist dies für die meisten Organisationen nicht praktikabel, daher wird in der Regel bevorzugt das Insider Risikomanagement mit einer kleinen Gruppe von Benutzern in einer Produktionsumgebung getestet.

Halten Sie das Anonymisierungs Feature unter Richtlinieneinstellungen aktiviert, um Benutzeranzeigenamen in der Insider Risk Management Console während dieser Tests zu pseudonymisieren, um den Datenschutz innerhalb des Tools beizubehalten. Dies trägt zum Schutz der Privatsphäre von Benutzern bei, die Richtlinien Übereinstimmungen aufweisen, und kann zur Förderung der Objektivität bei Daten Ermittlungs-und Analyse Überprüfungen für Insider Risikowarnungen beitragen.

Wenn Sie unmittelbar nach der Konfiguration einer Richtlinie für die Verwaltung von Insider Risiken keine Benachrichtigungen sehen, kann dies bedeuten, dass der minimale Risiko Grenzwert noch nicht erfüllt ist. Ein guter Weg, um zu überprüfen, ob die Richtlinie ausgelöst wird und wie erwartet funktioniert, ist, zu sehen, ob der Benutzer für die Richtlinie auf der Seite **Benutzer** im Bereich ist.

## <a name="resources-for-stakeholders"></a>Ressourcen für beteiligte

Teilen Sie die Insider Risk Management-Dokumentation den Beteiligten in Ihrer Organisation mit, die in Ihrem Verwaltungs-und Wartungs Workflow enthalten sind:

- [Erstellen und Verwalten von Insider-Risikorichtlinien](insider-risk-management-policies.md)
- [Untersuchen von Insider-Risikowarnungen](insider-risk-management-alerts.md)
- [Maßnahmen bei Insider-Risikofällen ergreifen](insider-risk-management-cases.md)
- [Überprüfen der Falldaten im Inhalts-Explorer für Insider Risiken](insider-risk-management-content-explorer.md)
- [Erstellen von Vorlagen für Benachrichtigungen zu Insider-Risiken](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>Sind Sie bereit zu beginnen?

Können Sie das Insider Risk Management für Ihre Organisation konfigurieren? Weitere Informationen finden Sie unter [Erste Schritte mit dem Insider Risikomanagement](insider-risk-management-configure.md) zum Konfigurieren von Voraussetzungen, Erstellen von Richtlinien und Starten des Empfangs von Benachrichtigungen.
