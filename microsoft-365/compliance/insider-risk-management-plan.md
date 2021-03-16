---
title: Planen des Insider-Risikomanagements
description: Erfahren Sie, wie Sie die Verwendung von Insider-Risikomanagementrichtlinien in Ihrer Organisation planen.
keywords: Microsoft 365, Insiderrisiko, Risikomanagement, Compliance
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
ms.openlocfilehash: 8cd9e9a72cd7643238d118fe0aed519db9159470
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820147"
---
# <a name="plan-for-insider-risk-management"></a>Planen des Insider-Risikomanagements

Bevor Sie mit insider [risk management](insider-risk-management.md) in Ihrer Organisation beginnen, gibt es wichtige Planungsaktivitäten und Überlegungen, die von Ihren Informationstechnologie- und Compliancemanagementteams überprüft werden sollten. Ein sorgfältiges Verständnis und eine sorgfältige Planung der Bereitstellung in den folgenden Bereichen tragen dazu bei, dass Ihre Implementierung und Verwendung von Insider-Risikomanagementfeatures reibungslos funktioniert und an die bewährten Methoden für die Lösung angepasst wird.

## <a name="work-with-stakeholders-in-your-organization"></a>Zusammenarbeit mit Interessengruppen in Ihrer Organisation

Identifizieren Sie die geeigneten Interessengruppen in Ihrer Organisation, um gemeinsam Aktionen zu Warnungen und Fällen des Insiderrisikomanagements zu ergreifen. Einige empfohlene Interessengruppen, die sie in die [](insider-risk-management.md#workflow) anfängliche Planung und den End-to-End-Insider-Risikomanagementworkflow integrieren sollten, sind Personen aus den folgenden Bereichen Ihrer Organisation:

- Informationstechnologie
- Compliance
- Datenschutz
- Sicherheit
- Personalwesen
- Rechtliche Hinweise

## <a name="determine-any-regional-compliance-requirements"></a>Ermitteln von regionalen Complianceanforderungen

Unterschiedliche geografische und organisatorische Bereiche können Compliance- und Datenschutzanforderungen haben, die sich von anderen Bereichen Ihrer Organisation unterscheiden. Arbeiten Sie mit den Interessengruppen in diesen Bereichen zusammen, um sicherzustellen, dass sie die Compliance- und Datenschutzkontrollen im Insider risk management verstehen und wie sie in verschiedenen Bereichen Ihrer Organisation verwendet werden sollten. In einigen Szenarien können Compliance- und Datenschutzanforderungen Richtlinien erfordern, mit denen bestimmte Beteiligte von Untersuchungen und Fällen basierend auf dem Fall für einen Benutzer oder behördliche oder richtlinienbezogene Anforderungen für den Bereich bestimmt oder eingeschränkt werden.

Wenn Sie Anforderungen haben, dass bestimmte Beteiligte an Falluntersuchungen beteiligt sind, an denen Benutzer in bestimmten Regionen, Rollen oder Abteilungen beteiligt sind, sollten Sie möglicherweise separate (auch wenn [identische)](insider-risk-management-policies.md) Insiderrisikomanagementrichtlinien für die verschiedenen Regionen und Populationen implementieren. Diese Konfiguration erleichtert es den richtigen Beteiligten, Fälle zu dreien und zu verwalten, die für ihre Rollen und Regionen relevant sind. Darüber hinaus sollten Sie die Erstellung von Prozessen und Richtlinien für Regionen in Betracht ziehen, in denen Ermittler und Prüfer die gleiche Sprache wie die Benutzer sprechen, um den Eskalationsprozess für Insider-Risikomanagementwarnungen und -fälle zu optimieren.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Planen des Überprüfungs- und Untersuchungsworkflows

Wählen Sie dedizierte Beteiligte aus, um die Warnungen und Fälle in regelmäßigen Abständen im [Microsoft 365 Compliance Center zu überwachen und zu überprüfen.](https://compliance.microsoft.com/) Stellen Sie sicher, dass Sie den verschiedenen Rollengruppen, die im Insider-Risikomanagement verfügbar sind, unterschiedliche Interessengruppen zuweisen.

Abhängig von der Struktur Ihres Compliance Management-Teams haben Sie Optionen, um Benutzern bestimmte Rollengruppen zuzuweisen, um unterschiedliche Gruppen von Funktionen zum Verwalten von Insiderrisiken zu verwalten. Wenn Sie  die Registerkarte Berechtigungen im Office 365 Security & Compliance Center anzeigen und  Rollengruppen verwalten möchten, müssen Sie der Rollengruppe Organisationsverwaltung zugewiesen sein oder der Rollenverwaltungsrolle *zugewiesen* werden. Wählen Sie bei der Konfiguration des Insiderrisikomanagements aus diesen Rollengruppenoptionen:

| **Rollengruppe** | **Rollenberechtigungen** |
| :------------- | :------------------- |
| **Insider Risk Management** | Verwenden Sie diese Rollengruppe zum Verwalten des Risikomanagements für Ihr Unternehmen in einer einzigen Gruppe. Durch Hinzufügen aller Benutzerkonten für designierte Administratoren, Analysten, Ermittler und Auditoren können Sie Berechtigungen für das Insiderrisikomanagement in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Insider-Risikomanagement-Berechtigungsrollen und zugehörige Berechtigungen. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit dem Insider-Risikomanagement zu beginnen, und ist gut geeignet für Organisationen, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind. |
| **Insider Risk Management Admin** | Verwenden Sie diese Rollengruppe, um zunächst das Insiderrisikomanagement zu konfigurieren und später Insiderrisikoadministratoren in eine definierte Gruppe zu trennen. Benutzer in dieser Rollengruppe können Analyseeinblicke aktivieren und anzeigen sowie Insider-Risikomanagementrichtlinien, globale Einstellungen und Rollengruppenzuweisungen erstellen, lesen, aktualisieren und löschen. |
| **Insider-Risikomanagement-Analysten** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Analysten im Falle eines Insiderrisikos fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungen, Fälle, Analyseeinblicke und Benachrichtigungsvorlagen für Insider-Risikomanagement zugreifen und diese anzeigen. Sie können nicht auf den Insider risk Content Explorer zugreifen. |
| **Insider-Risikomanagement-Prüfer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Datenprüfer für Insiderrisiken fungieren. Benutzer in dieser Rollengruppe können für alle Fälle auf alle Insider-Risikomanagementwarnungen, Fälle, Benachrichtigungsvorlagen und den Inhalts-Explorer zugreifen. |
| **Insider Risk Management Auditoren** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die Insider-Risikomanagementaktivitäten überwachen. Benutzer in dieser Rollengruppe können auf das Überwachungsprotokoll für Insiderrisiken zugreifen. |

## <a name="understand-requirements-and-dependencies"></a>Verstehen von Anforderungen und Abhängigkeiten

Je nachdem, wie Sie Insider-Risikomanagementrichtlinien implementieren möchten, müssen Sie über die richtigen Microsoft 365-Lizenzierungsabonnements verfügen und einige Lösungsvoraussetzungen verstehen und planen.

**Lizenzierung:** Insider-Risikomanagement ist im Rahmen einer breiten Auswahl von Microsoft 365-Lizenzierungsabonnements verfügbar. Weitere Informationen finden Sie im [Artikel Erste Schritte mit Insider-Risikomanagement.](insider-risk-management-configure.md#subscriptions-and-licensing)

Wenn Sie nicht über einen vorhandenen Microsoft 365 Enterprise E5-Plan verfügen und insider risk management ausprobieren [](https://www.microsoft.com/microsoft-365/enterprise) möchten, können Sie [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) zu Ihrem vorhandenen Abonnement hinzufügen oder sich für eine Testversion von Microsoft 365 Enterprise E5 registrieren.

**Richtlinienvorlagenanforderungen:** Je nach der von Ihnen verwendeten Richtlinienvorlage gibt es Anforderungen, die Sie verstehen und planen müssen, bevor Sie das Insiderrisikomanagement in Ihrer Organisation konfigurieren:

- Wenn Sie **die** Vorlage Datendiebstahl durch ausgehende Benutzer verwenden, müssen Sie einen Microsoft 365-Personalconnector konfigurieren, um regelmäßig Informationen zu Kündigungen und Beendigungsdatum für Benutzer in Ihrer Organisation zu importieren. Schrittweise [Anleitungen zum](import-hr-data.md) Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation finden Sie im Artikel Importieren von Daten mit dem Hr-Connector.
- Wenn Sie **Vorlagen** für Datenlecks verwenden, müssen Sie mindestens eine Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) konfigurieren, um vertrauliche Informationen in Ihrer Organisation zu definieren und Insiderrisikowarnungen für Warnungen mit hohem Schweregrad zu erhalten. Schrittweise [Anleitungen zum](create-test-tune-dlp-policy.md) Konfigurieren von DLP-Richtlinien für Ihre Organisation finden Sie im Artikel Erstellen, Testen und Optimieren eines DLP-Richtlinienartikels.
- Wenn Sie **Vorlagen für Sicherheitsrichtlinienverletzungen** verwenden, müssen Sie Microsoft Defender for Endpoint für die Integration von Insider-Risikomanagement im Defender Security Center aktivieren, um Sicherheitsverletzungswarnungen zu importieren. Im [Artikel Konfigurieren erweiterter Features in Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/advanced-features) finden Sie schrittweise Anleitungen zum Aktivieren der Integration von Defender for Endpoint in das Insider-Risikomanagement.
- Wenn  Sie unzufriedene Benutzervorlagen verwenden, müssen Sie einen Microsoft 365 HR-Connector so konfigurieren, dass regelmäßig Leistungs- oder Herabstufungsstatusinformationen für Benutzer in Ihrer Organisation importiert werden. Schrittweise [Anleitungen zum](import-hr-data.md) Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation finden Sie im Artikel Importieren von Daten mit dem Hr-Connector.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Testen mit einer kleinen Gruppe von Benutzern in einer Produktionsumgebung

Bevor Sie die Lösung allgemein in Ihrer Produktionsumgebung aktivieren, können Sie die Richtlinien mit einer kleinen Gruppe von Produktionsbenutzern testen und gleichzeitig die erforderlichen Compliance-, Datenschutz- und rechtlichen Überprüfungen in Ihrer Organisation durchführen. Die Auswertung des Insiderrisikomanagements in einer Testumgebung erfordert, dass Sie simulierte Benutzeraktionen und andere Signale generieren, um Warnungen für Triage und Fälle für die Verarbeitung zu erstellen. Dieser Ansatz ist für die meisten Organisationen nicht praktikabel, daher wird das Testen des Insiderrisikomanagements mit einer kleinen Gruppe von Benutzern in einer Produktionsumgebung bevorzugt.

Lassen Sie das Anonymisierungsfeature in Richtlinieneinstellungen aktiviert, um Benutzeranzeigenamen während dieser Tests in der Insider-Risikomanagementkonsole zu anonymisieren, um den Datenschutz innerhalb des Tools zu erhalten. Diese Einstellung trägt zum Schutz des Datenschutzes von Benutzern bei, die über Richtlinien übereinstimmungen verfügen, und kann zur Förderung der Objektivität bei datenuntersuchungen und Analyseüberprüfungen für Insiderrisikowarnungen beitragen.

Wenn unmittelbar nach der Konfiguration einer Insider-Risikomanagementrichtlinie keine Warnungen angezeigt werden, kann dies bedeuten, dass der Mindestrisikoschwellenwert noch nicht erreicht wurde. Eine gute Möglichkeit, um zu überprüfen, ob die Richtlinie ausgelöst wird und wie erwartet funktioniert, besteht in der Überprüfung, ob der Benutzer für die Richtlinie auf der Seite **Benutzer im** Bereich ist.

## <a name="resources-for-stakeholders"></a>Ressourcen für Beteiligte

Teilen Sie Insider-Risikomanagementdokumentation mit den Beteiligten in Ihrer Organisation, die in Ihrem Verwaltungs- und Korrekturworkflow enthalten sind:

- [Erstellen und Verwalten von Insider-Risikorichtlinien](insider-risk-management-policies.md)
- [Untersuchen von Insider-Risikowarnungen](insider-risk-management-alerts.md)
- [Maßnahmen bei Insider-Risikofällen ergreifen](insider-risk-management-cases.md)
- [Überprüfen von Falldaten mit dem Insider risk Content Explorer](insider-risk-management-content-explorer.md)
- [Erstellen von Vorlagen für Benachrichtigungen zu Insider-Risiken](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>Sind Sie bereit zu beginnen?

Sind Sie bereit, das Insider-Risikomanagement für Ihre Organisation zu konfigurieren? Lesen Sie die folgenden Artikel:

- [Beginnen Sie mit Insider-Risikomanagementeinstellungen,](insider-risk-management-settings.md) um globale Richtlinieneinstellungen zu konfigurieren.
- [Beginnen Sie mit insider risk management,](insider-risk-management-configure.md) um erforderliche Komponenten zu konfigurieren, Richtlinien zu erstellen und mit dem Empfang von Benachrichtigungen zu beginnen.
