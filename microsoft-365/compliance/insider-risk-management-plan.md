---
title: Planen des Insider-Risikomanagements
description: Erfahren Sie, wie Sie die Verwendung von Insider-Risikomanagementrichtlinien in Ihrer Organisation planen.
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
ms.openlocfilehash: 6884ec3b2bc7c24e4f7f6e62d9b24add3aeee2c0
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007345"
---
# <a name="plan-for-insider-risk-management"></a>Planen des Insider-Risikomanagements

Bevor Sie mit dem [Insider-Risikomanagement](insider-risk-management.md) in Ihrer Organisation beginnen, gibt es wichtige Planungsaktivitäten und Überlegungen, die von Ihren It-Technologie- und Compliance-Management-Teams überprüft werden sollten. Wenn Sie die Bereitstellung in den folgenden Bereichen sorgfältig verstehen und planen, können Sie sicherstellen, dass Ihre Implementierung und Verwendung von Insider-Risikomanagementfeatures reibungslos verläuft und den bewährten Methoden für die Lösung entspricht.

## <a name="work-with-stakeholders-in-your-organization"></a>Zusammenarbeit mit Projektbeteiligten in Ihrer Organisation

Identifizieren Sie die entsprechenden Interessengruppen in Ihrer Organisation, um zusammen Maßnahmen für Warnungen und Fälle des Insider-Risikomanagements zu ergreifen. Einige empfohlene Interessengruppen, die sie bei der anfänglichen Planung und dem End-to-End-Workflow für [Insider-Risikomanagement](insider-risk-management.md#workflow) berücksichtigen sollten, sind Personen aus den folgenden Bereichen Ihrer Organisation:

- Informationstechnologie
- Compliance
- Datenschutz
- Sicherheit
- Personalwesen
- Rechtliche Hinweise

## <a name="determine-any-regional-compliance-requirements"></a>Ermitteln von regionalen Complianceanforderungen

Unterschiedliche geografische und organisatorische Bereiche können Compliance- und Datenschutzanforderungen haben, die sich von anderen Bereichen Ihrer Organisation unterscheiden. Arbeiten Sie mit den Beteiligten in diesen Bereichen zusammen, um sicherzustellen, dass sie die Compliance- und Datenschutzkontrollen im Insider-Risikomanagement verstehen und wie sie in verschiedenen Bereichen Ihrer Organisation verwendet werden sollten. In einigen Szenarien erfordern Compliance- und Datenschutzanforderungen möglicherweise Richtlinien, die einige Interessengruppen von Untersuchungen und Fällen abhängig vom Fall für einen Benutzer oder behördlichen oder Richtlinienanforderungen für den Bereich bestimmen oder einschränken.

Wenn Sie Anforderungen haben, dass bestimmte Projektbeteiligten an Falluntersuchungen beteiligt sind, an denen Benutzer in bestimmten Regionen, Rollen oder Abteilungen beteiligt sind, sollten Sie separate (auch wenn identische) [Insider-Risikomanagementrichtlinien](insider-risk-management-policies.md) für die verschiedenen Regionen und Populationen implementieren. Diese Konfiguration erleichtert es den richtigen Beteiligten, Fälle zu selektieren und zu verwalten, die für ihre Rollen und Regionen relevant sind. Darüber hinaus empfiehlt es sich, Prozesse und Richtlinien für Regionen zu erstellen, in denen Ermittler und Prüfer dieselbe Sprache wie die Benutzer sprechen, um den Eskalationsprozess für Warnungen und Fälle des Insider-Risikomanagements zu optimieren.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Planen des Prüf- und Untersuchungsworkflows

Wählen Sie dedizierte Projektbeteiligten aus, um warnungen und Fälle regelmäßig im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)zu überwachen und zu überprüfen. Stellen Sie sicher, dass Sie wissen, wie Sie den verschiedenen Rollengruppen, die im Insider-Risikomanagement verfügbar sind, unterschiedliche Projektbeteiligten zuweisen.

Abhängig von der Struktur Ihres Compliance Management-Teams haben Sie Optionen, um Benutzern bestimmte Rollengruppen zuzuweisen, um unterschiedliche Gruppen von Funktionen zum Verwalten von Insiderrisiken zu verwalten. Um die Registerkarte **"Berechtigungen"** im Office 365 Security & Compliance Center anzuzeigen und Rollengruppen zu verwalten, müssen Sie der Rollengruppe *"Organisationsverwaltung"* oder der *Rollenverwaltungsrolle* zugewiesen werden. Wählen Sie bei der Konfiguration des Insider-Risikomanagements aus den folgenden Rollengruppenoptionen:

| **Rollengruppe** | **Rollenberechtigungen** |
| :------------- | :------------------- |
| **Insider-Risikomanagement** | Verwenden Sie diese Rollengruppe zum Verwalten des Risikomanagements für Ihr Unternehmen in einer einzigen Gruppe. Durch Hinzufügen aller Benutzerkonten für bestimmte Administratoren, Analysten, Ermittler und Auditoren können Sie Berechtigungen für das Insider-Risikomanagement in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für das Insider-Risikomanagement und zugehörige Berechtigungen. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit dem Insider-Risikomanagement zu beginnen, und eignet sich gut für Organisationen, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind. Wenn Sie diese Konfiguration verwenden, sollten Sie sicherstellen, dass dieser Rollengruppe immer mindestens ein Benutzer zugewiesen ist, um sicherzustellen, dass Ihre Richtlinien wie erwartet funktionieren, damit der Benutzer Richtlinien erstellen und bearbeiten, Lösungseinstellungen konfigurieren und Warnungen zur Richtlinienintegrität überprüfen kann. |
| **Administrator für Insider-Risikomanagement** | Verwenden Sie diese Rollengruppe, um zunächst das Insider-Risikomanagement zu konfigurieren und später Insider-Risikoadministratoren in eine definierte Gruppe zu untergliedern. Benutzer in dieser Rollengruppe können Analyseerkenntnisse aktivieren und anzeigen sowie Richtlinien für das Insider-Risikomanagement, globale Einstellungen und Rollengruppenzuweisungen erstellen, lesen, aktualisieren und löschen. Wenn Sie diese Konfiguration verwenden, sollten Sie sicherstellen, dass dieser Rollengruppe immer mindestens ein Benutzer zugewiesen ist, um sicherzustellen, dass Ihre Richtlinien wie erwartet funktionieren, damit der Benutzer Richtlinien erstellen und bearbeiten, Lösungseinstellungen konfigurieren und Warnungen zur Richtlinienintegrität überprüfen kann. |
| **Insider-Risikomanagement-Analysten** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Analysten im Falle eines Insiderrisikos fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungen, Fälle, Analyseerkenntnisse und Benachrichtigungsvorlagen des Insider-Risikomanagements zugreifen und diese anzeigen. Sie können nicht auf den Inhalts-Explorer für Insider-Risiken zugreifen. |
| **Insider-Risikomanagement-Prüfer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Datenprüfer für Insiderrisiken fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungen, Fälle, Benachrichtigungsvorlagen und den Inhalts-Explorer für alle Fälle zugreifen. |
| **Auditoren des Insider-Risikomanagements** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die Aktivitäten des Insider-Risikomanagements überwachen. Benutzer in dieser Rollengruppe können auf das Überwachungsprotokoll für Insider-Risiken zugreifen. |

## <a name="understand-requirements-and-dependencies"></a>Grundlegendes zu Anforderungen und Abhängigkeiten

Je nachdem, wie Sie Insider-Risikomanagementrichtlinien implementieren möchten, müssen Sie über die richtigen Microsoft 365-Lizenzierungsabonnements verfügen und einige Lösungsvoraussetzungen verstehen und planen.

**Lizenzierung:** Das Insider-Risikomanagement ist im Rahmen einer breiten Auswahl von Microsoft 365-Lizenzierungsabonnements verfügbar. Ausführliche Informationen finden Sie im Artikel ["Erste Schritte mit dem Insider-Risikomanagement".](insider-risk-management-configure.md#subscriptions-and-licensing)

Wenn Sie keinen vorhandenen Microsoft 365 Enterprise E5-Plan haben und das Insider-Risikomanagement ausprobieren möchten, können Sie [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) zu Ihrem vorhandenen Abonnement hinzufügen oder sich für eine Testversion von Microsoft 365 Enterprise E5 [registrieren.](https://www.microsoft.com/microsoft-365/enterprise)

**Anforderungen an Richtlinienvorlagen:** Je nach der von Ihnen gewählten Richtlinienvorlage gibt es Anforderungen, die Sie verstehen und planen müssen, bevor Sie das Insider-Risikomanagement in Ihrer Organisation konfigurieren:

- Wenn Sie die Vorlage **"Datendiebstahl durch verlassende Benutzer"** verwenden, müssen Sie einen Microsoft 365 HR-Connector konfigurieren, um in regelmäßigen Abständen Termin- und Termininformationen für Benutzer in Ihrer Organisation zu importieren. Eine schrittweise Anleitung zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation finden Sie in dem Artikel [Importieren von Daten mit dem HR-Connector](import-hr-data.md).
- Wenn Sie Vorlagen für **Datenlecks** verwenden, müssen Sie mindestens eine DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust) konfigurieren, um vertrauliche Informationen in Ihrer Organisation zu definieren und Insider-Risikowarnungen für DLP-Richtlinienwarnungen mit hohem Schweregrad zu erhalten. Eine schrittweise Anleitung zum Konfigurieren von DLP-Richtlinien für Ihre Organisation finden Sie in dem Artikel [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md).
- Wenn Sie Vorlagen für **Sicherheitsrichtlinienverletzungen** verwenden, müssen Sie Microsoft Defender für Endpunkt für die Integration des Insider-Risikomanagements im Defender Security Center aktivieren, um Warnungen zu Sicherheitsverstößen zu importieren. Eine schrittweise Anleitung zum Aktivieren der Defender für Endpunkt-Integration in das Insider-Risikomanagement finden Sie im Artikel ["Konfigurieren erweiterter Features in Microsoft Defender".](/windows/security/threat-protection/microsoft-defender-atp/advanced-features)
- Bei Verwendung **von Unmut-Benutzervorlagen** müssen Sie einen Microsoft 365 HR-Connector konfigurieren, um regelmäßig Leistungs- oder Herabstufungsstatusinformationen für Benutzer in Ihrer Organisation zu importieren. Eine schrittweise Anleitung zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation finden Sie in dem Artikel [Importieren von Daten mit dem HR-Connector](import-hr-data.md).

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Testen mit einer kleinen Gruppe von Benutzern in einer Produktionsumgebung

Bevor Sie die Lösung in Ihrer Produktionsumgebung allgemein aktivieren, können Sie die Richtlinien mit einer kleinen Gruppe von Produktionsbenutzern testen und gleichzeitig die erforderlichen Compliance-, Datenschutz- und rechtlichen Überprüfungen in Ihrer Organisation durchführen. Die Auswertung des Insider-Risikomanagements in einer Testumgebung erfordert, dass Sie simulierte Benutzeraktionen und andere Signale generieren, um Warnungen für triage und Fälle für die Verarbeitung zu erstellen. Dieser Ansatz ist für die meisten Organisationen nicht praktisch. Daher wird das Testen des Insider-Risikomanagements mit einer kleinen Gruppe von Benutzern in einer Produktionsumgebung bevorzugt.

Lassen Sie das Anonymisierungsfeature in den Richtlinieneinstellungen aktiviert, um die Anzeigenamen von Benutzern in der Insider-Risikomanagementkonsole während dieser Tests zu anonymisieren, um den Datenschutz innerhalb des Tools aufrechtzuerhalten. Diese Einstellung trägt zum Schutz der Privatsphäre von Benutzern bei, die Richtlinienübersprechungen haben, und kann dazu beitragen, die Objektivität bei der Untersuchung und Analyse von Daten für Insider-Risikowarnungen zu fördern.

Wenn unmittelbar nach dem Konfigurieren einer Insider-Risikomanagementrichtlinie keine Warnungen angezeigt werden, bedeutet dies möglicherweise, dass der Mindestrisikoschwellenwert noch nicht erreicht wurde. Eine gute Möglichkeit, um zu überprüfen, ob die Richtlinie ausgelöst wird und wie erwartet funktioniert, besteht darin, festzustellen, ob der Benutzer im Bereich für die Richtlinie auf der Seite **"Benutzer"** ist.

## <a name="resources-for-stakeholders"></a>Ressourcen für Projektbeteiligten

Teilen Sie die Dokumentation zum Insider-Risikomanagement mit den Beteiligten in Ihrer Organisation, die in Ihrem Verwaltungs- und Wartungsworkflow enthalten sind:

- [Erstellen und Verwalten von Insider-Risikorichtlinien](insider-risk-management-policies.md)
- [Untersuchen von Insider-Risikowarnungen](insider-risk-management-alerts.md)
- [Maßnahmen bei Insider-Risikofällen ergreifen](insider-risk-management-cases.md)
- [Überprüfen von Falldaten mit dem Inhalts-Explorer für Insider-Risiken](insider-risk-management-content-explorer.md)
- [Erstellen von Vorlagen für Benachrichtigungen zu Insider-Risiken](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>Sind Sie bereit loszulegen?

Sind Sie bereit, das Insider-Risikomanagement für Ihre Organisation zu konfigurieren? Lesen Sie die folgenden Artikel:

- [Erste Schritte mit Insider-Risikomanagementeinstellungen](insider-risk-management-settings.md) zum Konfigurieren globaler Richtlinieneinstellungen.
- [Beginnen Sie mit dem Insider-Risikomanagement,](insider-risk-management-configure.md) um Voraussetzungen zu konfigurieren, Richtlinien zu erstellen und mit dem Empfangen von Warnungen zu beginnen.
