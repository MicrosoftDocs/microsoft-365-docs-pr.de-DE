---
title: Planen des Insider-Risikomanagements
description: Erfahren Sie, wie Sie die Verwendung von Richtlinien für das Insiderrisikomanagement in Ihrer Organisation planen.
keywords: Microsoft 365, Insider-Risiko, Risikomanagement, Compliance
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
ms.openlocfilehash: f2581c4756a57926ab4a4539be8c383b0479e567
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126624"
---
# <a name="plan-for-insider-risk-management"></a>Planen des Insider-Risikomanagements

Bevor Sie mit dem [Insiderrisikomanagement](insider-risk-management.md) in Ihrer Organisation beginnen, gibt es wichtige Planungsaktivitäten und Überlegungen, die von Ihren Teams für Informationstechnologie und Complianceverwaltung überprüft werden sollten. Sorgfältiges Verständnis und sorgfältige Planung der Bereitstellung in den folgenden Bereichen tragen dazu bei, dass Ihre Implementierung und Verwendung von Features für das Insider-Risikomanagement reibungslos funktioniert und mit den bewährten Methoden für die Lösung abgestimmt ist.

## <a name="work-with-stakeholders-in-your-organization"></a>Zusammenarbeit mit Beteiligten in Ihrer Organisation

Identifizieren Sie die entsprechenden Beteiligten in Ihrer Organisation, um gemeinsam Maßnahmen für Warnungen und Fälle des Insider-Risikomanagements zu ergreifen. Einige empfohlene Beteiligte, die in die anfängliche [](insider-risk-management.md#workflow) Planung und den End-to-End-Workflow für das Insiderrisikomanagement mit einplanen sollten, sind Personen aus den folgenden Bereichen Ihrer Organisation:

- Informationstechnologie
- Compliance
- Datenschutz
- Sicherheit
- Personalwesen
- Rechtliche Hinweise

## <a name="determine-any-regional-compliance-requirements"></a>Ermitteln von regionalen Complianceanforderungen

Unterschiedliche geografische und organisatorische Bereiche haben möglicherweise Compliance- und Datenschutzanforderungen, die sich von anderen Bereichen Ihrer Organisation unterscheiden. Arbeiten Sie mit den Beteiligten in diesen Bereichen zusammen, um sicherzustellen, dass sie die Compliance- und Datenschutzkontrollen im Insider-Risikomanagement verstehen und wie sie in verschiedenen Bereichen Ihrer Organisation verwendet werden sollten. In einigen Szenarien erfordern Compliance- und Datenschutzanforderungen möglicherweise Richtlinien, die bestimmte Beteiligte basierend auf dem Fall für einen Benutzer oder behördlichen oder richtlinienbezogenen Anforderungen für diesen Bereich für Untersuchungen und Fälle festlegen oder einschränken.

Wenn Sie Anforderungen haben, dass bestimmte Beteiligte an Falluntersuchungen beteiligt sind, an denen Benutzer in bestimmten Regionen, Rollen oder Abteilungen beteiligt sind, sollten Sie separate (auch wenn [identische)](insider-risk-management-policies.md) Richtlinien für das Insiderrisikomanagement für die verschiedenen Regionen und Populationen implementieren. Diese Konfiguration erleichtert den richtigen Beteiligten die Trikotierung und Verwaltung von Fällen, die für ihre Rollen und Regionen relevant sind. Darüber hinaus sollten Sie die Erstellung von Prozessen und Richtlinien für Regionen in Betracht ziehen, in denen Ermittler und Prüfer die gleiche Sprache sprechen wie die Benutzer, um den Eskalationsprozess für Warnungen und Fälle des Insider-Risikomanagements zu optimieren.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Planen des Überprüfungs- und Untersuchungsworkflows

Wählen Sie dedizierte Beteiligte aus, um die Warnungen und Fälle regelmäßig im [Microsoft 365 Compliance Center zu überwachen und zu überprüfen.](https://compliance.microsoft.com/) Stellen Sie sicher, dass Sie verstehen, wie Sie den verschiedenen Rollengruppen, die im Insider-Risikomanagement verfügbar sind, unterschiedliche Beteiligte zuweisen.

Abhängig von der Struktur Ihres Compliance Management-Teams haben Sie Optionen, um Benutzern bestimmte Rollengruppen zuzuweisen, um unterschiedliche Gruppen von Funktionen zum Verwalten von Insiderrisiken zu verwalten. Wählen Sie bei der Konfiguration des Insider-Risikomanagements aus diesen Rollengruppenoptionen:

| **Rollengruppe** | **Rollenberechtigungen** |
| :---- | :---------------- |
| **Insider Risk Management** | Verwenden Sie diese Rollengruppe zum Verwalten des Risikomanagements für Ihr Unternehmen in einer einzigen Gruppe. Wenn Sie alle Benutzerkonten für designierte Administratoren, Analytiker und Prüfer hinzufügen, können Sie Berechtigungen für das Insider-Risikomanagement in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für Insider-Risikomanagement. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit dem Insider-Risikomanagement zu beginnen, und ist gut geeignet für Organisationen, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind.|
| **Administrator des Insider-Risikomanagements** | Verwenden Sie diese Rollengruppe, um zunächst das Insiderrisikomanagement zu konfigurieren und später Insider-Risikoadministratoren in eine definierte Gruppe zu untergtrennen.  Benutzer in dieser Rollengruppe können Verwaltungsrichtlinien, globale Einstellungen und Rollengruppenzuweisungen für Insiderrisiken erstellen, lesen, aktualisieren und löschen. |
| **Insider-Risikomanagement-Analysten** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Analysten im Falle eines Insiderrisikos fungieren. Benutzer in dieser Rollengruppe können auf alle Vorlagen für Insider-Risikomanagement, -fälle und -benachrichtigungen zugreifen. Sie könne nicht auf den Inhalts-Explorer für Insider-Risiken zugreifen. |
| **Insider-Risikomanagement-Prüfer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Datenprüfer für Insiderrisiken fungieren. Benutzer in dieser Rollengruppe können für alle Fälle auf alle Insider-Risikomanagement-Warnungen, -Fälle, -Benachrichtigungsvorlagen und den Inhalts-Explorer zugreifen. |

## <a name="understand-requirements-and-dependencies"></a>Verstehen von Anforderungen und Abhängigkeiten

Je nachdem, wie Sie Insider-Risikomanagement-Richtlinien implementieren möchten, benötigen Sie die richtigen Microsoft 365-Lizenzierungsabonnements und verstehen und planen einige Lösungsvoraussetzungen.

**Lizenzierung:** Das Risikomanagement für Insider ist im Rahmen einer breiten Auswahl an Microsoft 365-Lizenzierungsabonnements verfügbar. Weitere Informationen finden Sie im Artikel ["Erste Schritte mit dem Insider-Risikomanagement".](insider-risk-management-configure.md#subscriptions-and-licensing)

Wenn Sie nicht über einen vorhandenen Microsoft 365 Enterprise E5-Plan verfügen und das Insiderrisikomanagement ausprobieren [](https://www.microsoft.com/microsoft-365/enterprise) möchten, können Sie [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) zu Ihrem vorhandenen Abonnement hinzufügen oder sich für eine Testversion von Microsoft 365 Enterprise E5 registrieren.

**Richtlinienvorlagenanforderungen:** Je nach der von Ihnen verwendeten Richtlinienvorlage müssen Sie die Anforderungen verstehen und planen, bevor Sie das Insiderrisikomanagement in Ihrer Organisation konfigurieren:

- Wenn Sie  den Datendiebstahl durch die Vorlage "Verlassene Benutzer" verwenden, müssen Sie einen Microsoft 365 -PERSONAL-Connector so konfigurieren, dass regelmäßig Informationen zum Datum der Kündigung für Benutzer in Ihrer Organisation importiert werden. Schrittweise [Anleitungen zum](import-hr-data.md) Konfigurieren des Microsoft 365 -PERSONAL-Connectors für Ihre Organisation finden Sie im Artikel zum Importieren von Daten mit dem HR-Connector.
- Wenn Sie Vorlagen für **Datenlecks** verwenden, müssen Sie mindestens eine Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) konfigurieren, um vertrauliche Informationen in Ihrer Organisation zu definieren und Benachrichtigungen über Insiderrisiken für Warnungen zu Richtlinien mit hohem Schweregrad zu erhalten. Schrittweise [Anleitungen zum Konfigurieren von DLP-Richtlinien](create-test-tune-dlp-policy.md) für Ihre Organisation finden Sie im Artikel zum Erstellen, Testen und Optimieren eines DLP-Richtlinienartikels.
- Wenn Sie **Vorlagen für Sicherheitsrichtlinienverletzungen** verwenden, müssen Sie Microsoft Defender for Endpoint für die Integration des Insider-Risikomanagements im Defender Security Center aktivieren, um Warnungen zu Sicherheitsverletzungen zu importieren. Schrittweise [Anleitungen zum](/windows/security/threat-protection/microsoft-defender-atp/advanced-features) Aktivieren der Integration von Defender for Endpoint in das Insider-Risikomanagement finden Sie im Artikel "Konfigurieren erweiterter Features in Microsoft Defender".
- Wenn Sie **unzufriedene** Benutzervorlagen verwenden, müssen Sie einen Microsoft 365 -PERSONAL-Connector so konfigurieren, dass regelmäßig Leistungs- oder Herabstufungsstatusinformationen für Benutzer in Ihrer Organisation importiert werden. Schrittweise [Anleitungen zum](import-hr-data.md) Konfigurieren des Microsoft 365 -HR-Connectors für Ihre Organisation finden Sie im Artikel zum Importieren von Daten mit dem HR-Connector.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Testen mit einer kleinen Gruppe von Benutzern in einer Produktionsumgebung

Bevor Sie die Lösung allgemein in Ihrer Produktionsumgebung aktivieren, sollten Sie die Richtlinien mit einer kleinen Gruppe von Produktionsbenutzern testen und gleichzeitig die erforderlichen Compliance-, Datenschutz- und rechtlichen Überprüfungen in Ihrer Organisation durchführen. Die Auswertung des Insiderrisikomanagements in einer Testumgebung erfordert, dass Sie simulierte Benutzeraktionen und andere Signale generieren, um Warnungen für die Triage und Fälle für die Verarbeitung zu erstellen. Dieser Ansatz ist für die meisten Organisationen nicht praktikabel, daher wird das Testen des Insiderrisikomanagements mit einer kleinen Gruppe von Benutzern in einer Produktionsumgebung bevorzugt.

Lassen Sie das Anonymisierungsfeature in den Richtlinieneinstellungen aktiviert, um Benutzeranzeigenamen während dieser Tests in der Verwaltungskonsole für Insider zu anonymisieren, um den Datenschutz innerhalb des Tools zu gewährleisten. Diese Einstellung trägt zum Schutz des Datenschutzes von Benutzern bei, die Richtlinien mit Übereinstimmungen haben, und kann die Objektivität bei Der Untersuchung von Daten und Analyseüberprüfungen für Insider-Risikowarnungen fördern.

Wenn unmittelbar nach der Konfiguration einer Richtlinie für das Insiderrisikomanagement keine Warnungen angezeigt werden, bedeutet dies möglicherweise, dass der Schwellenwert für das Mindestrisiko noch nicht erreicht wurde. Eine gute Möglichkeit, um zu überprüfen, ob die Richtlinie ausgelöst wird und wie erwartet funktioniert, besteht in der Überprüfung, ob sich der Benutzer im Bereich der Richtlinie auf der Seite **"Benutzer"** befindet.

## <a name="resources-for-stakeholders"></a>Ressourcen für Projektbeteiligten

Teilen Sie die Dokumentation zum Insider-Risikomanagement mit den Beteiligten in Ihrer Organisation, die in Ihrem Verwaltungs- und Wartungsworkflow enthalten sind:

- [Erstellen und Verwalten von Insider-Risikorichtlinien](insider-risk-management-policies.md)
- [Untersuchen von Insider-Risikowarnungen](insider-risk-management-alerts.md)
- [Maßnahmen bei Insider-Risikofällen ergreifen](insider-risk-management-cases.md)
- [Überprüfen von Falldaten mit dem Insider-Risiko-Inhalts-Explorer](insider-risk-management-content-explorer.md)
- [Erstellen von Vorlagen für Benachrichtigungen zu Insider-Risiken](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>Sind Sie bereit zu beginnen?

Sind Sie bereit, das Insider-Risikomanagement für Ihre Organisation zu konfigurieren? Lesen Sie die folgenden Artikel:

- [Beginnen Sie mit den Einstellungen für das Insider-Risikomanagement,](insider-risk-management-settings.md) um globale Richtlinieneinstellungen zu konfigurieren.
- [Beginnen Sie mit dem Insider-Risikomanagement,](insider-risk-management-configure.md) um die Voraussetzungen zu konfigurieren, Richtlinien zu erstellen und mit dem Empfangen von Warnungen zu beginnen.
