---
title: Neuerungen in Microsoft 365 Compliance
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Ob es darum geht, dem Compliance Center neue Lösungen zu hinzufügen, vorhandene Features basierend auf Ihrem Feedback zu aktualisieren oder eine aktuelle und aktualisierte Dokumentation zu erstellen– Microsoft 365 hilft Ihnen, auf dem neuesten Stand der sich ständig ändernden Compliancelandschaft zu bleiben. Finden Sie heraus, was wir diesen Monat vorhaben.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ed29ad5186972f56609a596d88a48c7c460f295f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905857"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Neuerungen in Microsoft 365 Compliance

Ob es darum geht, dem [Microsoft 365 Compliance Center](microsoft-365-compliance-center.md)neue Lösungen zu hinzufügen, vorhandene Features basierend auf Ihrem Feedback zu aktualisieren oder eine aktuelle und aktualisierte Dokumentation zu erstellen– Microsoft 365 hilft Ihnen, die sich ständig ändernde Compliancelandschaft auf dem neuesten Stand zu halten. Sehen Sie sich unten an, was in Der Microsoft 365-Compliance heute neu ist.

> [!NOTE]
> Einige Compliancefeatures werden für unsere Kunden mit unterschiedlichen Geschwindigkeiten ausgeführt. Wenn Sie noch kein Feature sehen, versuchen Sie, sich selbst zu [Gezieltes Release](/office365/admin/manage/release-options-in-office-365) hinzuzufügen.

> [!TIP]
> Interessieren Sie sich dafür, was in anderen Admin Centers geschieht? Dann lesen Sie die folgenden Artikel:<br>[Neuerungen im Microsoft 365 Admin Center](/office365/admin/whats-new-in-preview)<br>[Aktive Websites im SharePoint Online Admin Center](/sharepoint/what-s-new-in-admin-center)<br>[Neuerungen in Microsoft 365 Defender](../security/mtp/whats-new.md)<br><br>
Besuchen Sie die [Microsoft 365-Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap), um sich über Features von Microsoft 365 zu informieren, die eingeführt wurden, bereitgestellt werden, sich in der Entwicklung befinden, eingestellt oder zuvor veröffentlicht wurden.

## <a name="january-2021"></a>Januar 2021

### <a name="support-for-card-content-in-teams"></a>Unterstützung für Karteninhalte in Teams

Die folgenden Microsoft 365-Compliancelösungen [](/microsoftteams/platform/task-modules-and-cards/what-are-cards) unterstützen nun die Erkennung von Karteninhalten, die über Apps in Teams-Nachrichten generiert werden:

- **Core und Advanced eDiscovery**. Karteninhalte können jetzt [in der Warteschleife](create-ediscovery-holds.md#preserve-card-content) platziert oder in Die Suche einbezogen [werden](/microsoftteams/ediscovery-investigation#search-for-card-content) (gilt auch für die Inhaltssuche).
- **Überwachung**. Die Kartenaktivität wird [nun im Überwachungsprotokoll aufgezeichnet.](/microsoftteams/audit-log-events#teams-activities)
- **Aufbewahrungsrichtlinien**. Kann jetzt Aufbewahrungsrichtlinien verwenden, [um Karteninhalte zu behalten und zu löschen.](retention-policies-teams.md#whats-included-for-retention-and-deletion)

### <a name="information-governance-and-records-management"></a>Informationsverwaltung und Datensatzverwaltung

[Neue Bewertung zur](retention-regulatory-requirements.md#new-zealand-public-records-act) Verwendung von Informations-Governance und Datensatzverwaltung zur Erfüllung der Complianceverpflichtungen für das New Zealand Public Records Act.

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

- Vertraulichkeitsbezeichnungen werden jetzt für Us Government Tenants (GCC und GCC-H) unterstützt.
- Neue [automatische Bezeichnungsunterstützung](sensitivity-labels-office-apps.md) für macOS.

## <a name="december-2020"></a>Dezember 2020

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>Spotlight: Neue Inhalte für Insider-Risikolösungen

Das Microsoft 365-Compliance-Inhaltsteam arbeitet hart daran, Dokumente zur Inhaltslösung zu erstellen, um zu fördern, wie Compliancefunktionen gemeinsam verwendet werden können, um Ihre Complianceziele zu erreichen.

Zunächst werden Inhalte verwendet, die unsere Insider-Risikolösungen verbinden: Kommunikations-Compliance, Insider-Risikomanagement, Informationsbarrieren und privilegierte Zugriffsverwaltung. Hier sehen Sie, was Sie finden:

- [Neue Angebotsseite für Insider-Risikolösungen](insider-risk-solution-overview.md). Enthält Details zu Risiken, die die Lösungen verringern können, Lizenzierungsanforderungen, Bereitstellungssequenzen, Architekturillustrationen, Schulungsressourcen und vieles mehr.
- Neue Übersichtsartikel für jede Insiderrisikolösung. Anleitungen und Links zu Artikeln, die Ihnen dabei helfen, die einzelnen Lösungen kennen zu lernen, zu planen, zu bereitstellen und zu verwalten:
  - [Kommunikationscompliance](communication-compliance-solution-overview.md)
  - [Insider-Risikomanagement](insider-risk-management-solution-overview.md)
  - [Informationsbarrieren](information-barriers-solution-overview.md)
  - [Privileged Access Management](privileged-access-management-solution-overview.md)
  
Weitere Inhaltslösungs-Dokumente werden in Kürze angezeigt!

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

Verbesserte Workflow- und Funktionalität zum Hinzufügen von [Custodians](add-custodians-to-case.md) und nicht [verwahrbaren](non-custodial-data-sources.md) Datenquellen zu einem Advanced eDiscovery-Fall.

### <a name="data-connectors"></a>Datenconnectors

[Vier neue "Globenet"-Connectors wurden veröffentlicht:](archiving-third-party-data.md#third-party-data-connectors)Redtail Speak, Salesforce Chatter, ServiceNow und Yieldbroker.

### <a name="encryption"></a>Verschlüsselung

Einführung [in den Kundenschlüssel für Microsoft 365 auf Mandantenebene.](customer-key-tenant-level.md) Mithilfe von schlüsseln, die Sie bereitstellen, können Sie eine Datenverschlüsselungsrichtlinie (Data Encryption Policy, DEP) erstellen und sie dem Mandanten zuweisen. Die DEP verschlüsselt Daten über den Mandanten für diese Workloads:

- Teams-Chatnachrichten (1:1-Chats, Gruppenchats, Besprechungschats und Kanalunterhaltungen)
- Teams-Mediennachrichten (Bilder, Codeausschnitte, Videos, Wiki-Bilder)
- Im Speicher von Teams gespeicherte Anruf- und Besprechungsaufzeichnungen von Teams
- Teams-Chatbenachrichtigungen
- Vorschläge für Teams-Chats von Cortana
- Teams-Statusmeldungen
- Benutzer- und Signalinformationen für Exchange Online

### <a name="records-management"></a>Datensatzverwaltung

Die [Rollengruppe Datensatzverwaltung gewährt](get-started-with-records-management.md#permissions-required-for-records-management) jetzt Berechtigungen für alle Datensatzverwaltungsfeatures, einschließlich der Dispositionsüberprüfung.

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

- [Automatische Bezeichnung von Daten in Azure Purview (Vorschau)](/azure/purview/create-sensitivity-label). Sie können jetzt Vertraulichkeitsbezeichnungen auf Ressourcen in Azure Purview erstellen und automatisch anwenden, z. B. Dateien in Azure Blob Storage und Datenbankspalten in SQL Server.
- [Benutzer müssen eine Bezeichnung auf Elemente anwenden.](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) Diese neue Option, die auch als "obligatorische Bezeichnung" bezeichnet wird, erfordert, dass Benutzer eine Vertraulichkeitsbezeichnung unter den jeweiligen Szenarien auswählen und anwenden.

## <a name="november-2020"></a>November 2020
Nur eine Erinnerung daran, dass wir häufig neue und aktualisierte Features in einem Vorschauzustand veröffentlichen, um zu erfahren, wie sie verwendet werden, damit wir sie optimieren und verbessern können, bevor wir sie für die allgemeine Verfügbarkeit freigeben. Ihr Feedback ist während der Vorschau (und darüber hinaus) wichtig. Teilen Sie uns daher unbedingt mit, was Sie denken, indem Sie die Feedbackkarte unten rechts im Compliance Center öffnen.

![Feedback](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>Spotlight: Endpoint Data Loss Prevention (DLP) veröffentlicht

[Endpoint DLP](endpoint-dlp-learn-about.md) erweitert die Aktivitätsüberwachungs- und Schutzfunktionen von DLP auf vertrauliche Informationen auf Windows 10-Geräten. Nachdem Geräte in [das](dlp-configure-endpoints.md) Microsoft 365 Compliance Center integrierte wurden, können Sie DLP-Richtlinien einrichten, um die vertraulichen Informationen auf diesen Geräten zu schützen.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

Um die Verwaltung verschlüsselter Inhalte im eDiscovery-Workflow zu vereinfachen, umfassen Microsoft [](ediscovery-decryption.md) 365 eDiscovery-Tools jetzt die Entschlüsselung verschlüsselter Dateien, die an E-Mail-Nachrichten angefügt und in Exchange gesendet werden. Darüber hinaus werden verschlüsselte Dokumente, die in SharePoint und OneDrive gespeichert sind, in Advanced eDiscovery entschlüsselt.

### <a name="compliance-manager"></a>Compliance-Manager

- [Support für Microsoft 365 Government-Abonnements](compliance-manager.md). Compliance Manager steht jetzt moderaten und hohen Kunden der US Government Community (GCC) zur Verfügung.
- [Microsoft Compliance Configuration Analyzer for Compliance Manager](compliance-manager-mcca.md). Neues PowerShell-basiertes Tool, mit dem Sie mit Compliance Manager beginnen können, indem Sie die aktuellen Konfigurationen Ihrer Organisation überprüfen und diese anhand der von Microsoft 365 empfohlenen bewährten Methoden überprüfen.
- [Neue Vorlagen](compliance-manager-templates-list.md). Es wurden 56 neue Vorlagen hinzugefügt, die insgesamt mehr als 230 Compliance-Manager-Vorlagen zur Verfügung stellen.

### <a name="data-connectors"></a>Datenconnectors

[Fünf neue Globanet-Connectors in der Vorschau](archiving-third-party-data.md#third-party-data-connectors). Neue Connectors sind Reuters Dealing, Reuters FX, CellTrust, XIP, generische MS SQL Datenbankdaten.

### <a name="retention-labels-disposition-review"></a>Aufbewahrungsbezeichnungen (Dispositionsüberprüfung)

Zum Anzeigen von Elementen während einer Dispositionsüberprüfung müssen Benutzer jetzt Mitglieder der Rollengruppen [Inhalts-Explorer-Inhaltsanzeige und Inhalts-Explorer-Listenanzeige sein.](disposition.md#permissions-for-disposition) Obwohl zum Überprüfen von Elementen erforderlich, sind diese Rollengruppen nicht erforderlich, um die Dispositionsüberprüfung abschließen zu können.

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

- [(Vorschau) Einstellungen für die externe Freigabe für SharePoint-Websites](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings). Beim Erstellen einer Bezeichnung, die für Gruppen und Websites verwendet wird, wird eine Option zum Steuern der externen Freigabe für SharePoint-Websites angezeigt, auf die die Bezeichnung angewendet wurde. Sie können angeben, dass die Freigabe für alle, neue und vorhandene Gäste, nur für vorhandene Gäste oder nur für Benutzer in Ihrer Organisation zulässig ist. Wenn die Bezeichnung angewendet wird, ersetzen die Bezeichnungseinstellungen alle externen Freigabeeinstellungen, die [im SharePoint Admin Center konfiguriert sind.](/sharepoint/change-external-sharing-site)
- [Entfernen von Bezeichnung und Verschlüsselung aus einem mit Bezeichnungen versehenen Dokument](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document). Zum Entfernen einer Bezeichnung und der Verschlüsselung, die sie aus einem mit Bezeichnungen versehenen Dokument in SharePoint erzwingt, können globale Administratoren und SharePoint-Administratoren das neue `Unlock-SPOSensitivityLabelEncryptedFile` Cmdlet ausführen. Dieses Cmdlet wird auch dann ausgeführt, wenn der Administrator nicht über Zugriffsberechtigungen für die Website oder Datei verfügt oder wenn der Azure Rights Management-Dienst nicht verfügbar ist.

## <a name="october-2020"></a>Oktober 2020

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

[CJK-Sprachunterstützung](ediscovery-cjk-support.md). Advanced eDiscovery unterstützt nun Doppel-Byte-Zeichensatzsprachen, die als #A0 (einschließlich vereinfachtes Chinesisch, traditionelles Chinesisch, Japanisch und Koreanisch) bekannt sind. Diese können in mehreren erweiterten Überprüfungssatzszenarien verwendet werden.

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

- [Bezeichnungsbereich](sensitivity-labels.md#label-scopes). Beim Erstellen einer Vertraulichkeitsbezeichnung wird eine neue Option zum Definieren des Bereichs für die Bezeichnung angezeigt. Mit dieser Option können Sie Bezeichnungen nur für Dateien und E-Mails, Container (wie SharePoint-Websites und Teams) oder beides konfigurieren.
- [Dynamische Inhaltsmarkierung](sensitivity-labels-office-apps.md#dynamic-markings-with-variables). Beim Konfigurieren der Inhaltskennzeichnung für eine Vertraulichkeitsbezeichnung können Sie jetzt die dynamischen Variablen wie und in der Textzeichenfolge für Die Kopfzeile, Fußzeile oder `${Item.Label}` `${Item.Location}` Wasserzeichen verwenden.

## <a name="september-2020"></a>September 2020

### <a name="spotlight-compliance-manager"></a>Spotlight: Compliance Manager

Bei Ignite in diesem Jahr angekündigt, wird die Compliance-Bewertung als [Compliance-Manager umfirmiert.](compliance-manager.md) Diese Version schließt den Übergang von der vorherigen Startseite des Compliance Managers im Service Trust Portal ab und führt eine End-to-End-Lösung für die Complianceverwaltung im Microsoft 365 Compliance Center ein.

Sehen Sie sich das folgende Video an, um zu erfahren, wie Der Compliance-Manager dazu beitragen kann, die Verwaltung der Compliance in Ihrer Organisation zu vereinfachen.
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>Erweiterte Überwachung

- Die neue 10-jahres-Aufbewahrung von Überwachungsprotokollen unterstützt lange laufende Untersuchungen und reagiert auf behördliche, rechtliche und interne Verpflichtungen.
- [Drei neue wichtige Ereignisse](advanced-audit.md#access-to-crucial-events-for-investigations). Die folgenden neuen Ereignisse können Ihnen dabei helfen, mögliche Verstöße zu untersuchen und den Umfang der Kompromisse zu ermitteln: Send, SearchQueryInitiatedExchange und SearchQueryInitiatedSharePoint.

### <a name="communication-compliance"></a>Kommunikationsbezogene Compliance

- [Aktualisierte Rollengruppen](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance). Rollengruppen für die Kommunikationskonformität entsprechen nun der Rollengruppenstruktur, die für die Insider-Risikomanagementlösung verfügbar ist.
- [Berichtedashboard](communication-compliance-feature-reference.md#reports). Ihr zentraler Ort zum Anzeigen aller Kommunikationskonformitätsberichte. Berichts-Widgets bieten eine schnelle Ansicht der Einblicke, die am häufigsten für eine allgemeine Bewertung des Status von Kommunikations-Compliance-Aktivitäten benötigt werden.
- [Power Automate-Flüsse](communication-compliance-feature-reference.md#power-automate-flows). Richten Sie Flüsse ein, um Aufgaben für Warnungen und Benutzer zu automatisieren, Manager zu benachrichtigen, wenn Benutzer Warnungen auslösen, und vieles mehr.
- [Korrekturaktion "Klassifizierung verbessern"](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action). Warnungen, die Elemente enthalten, die trainierbaren Klassifizierungen entsprechen, können von Feedback profitieren, um falsch positive Ergebnisse in Ihrer Organisation zu minimieren. Mit **der Option Klassifizierung verbessern** können Sie Feedback darüber geben, ob erkannte Elemente mit dem in der zugehörigen Kommunikationskonformitätsrichtlinie konfigurierten Klassifizierer übereinstimmen. Sie können sogar andere Klassifizierungen vorschlagen, die dem Element zugeordnet werden sollen, um die Übereinstimmungsgenauigkeit für zukünftige Warnungen zu verbessern.

### <a name="data-connectors"></a>Datenconnectors

- [Neue Datenconnectors von Drittanbietern](archiving-third-party-data.md#third-party-data-connectors). 25 neue Datenconnectors, darunter 14 Connectors von Globenet und 8 von Telemessage.
- [Physischer Badging Connector](import-physical-badging-data.md). Importieren von physischen Daten, z. B. unformatierte physische Zugriffsereignisse von Mitarbeitern oder physische Zugriffsalarme, die durch das Schlechtungssystem Ihrer Organisation generiert werden. Beispiele hierfür sind Einträge in Gebäude, Serverräume oder Rechenzentren. Physische Schaddaten können von der Risikomanagementlösung für Insider verwendet werden, um Ihre Organisation vor böswilligen Aktivitäten oder Datendiebstahl in Ihrer Organisation zu schützen.

### <a name="insider-risk-management"></a>Insider-Risikomanagement

- [Microsoft Teams-Integration](insider-risk-management-settings.md#microsoft-teams-preview). Wenn die Integration von Teams in Insiderrisikoeinstellungen aktiviert ist, können Sie mit anderen Beteiligten in Teams bei Aufgaben wie der sicheren Freigabe und Speicherung von Daten im Zusammenhang mit Einzelfällen, dem Nachverfolgen und Überprüfen von Reaktionsaktivitäten von Analysten und Ermittlern und vielem mehr zusammenarbeiten.
- [Power Automate-Flüsse](insider-risk-management-settings.md#power-automate-flows-preview). Richten Sie Flüsse ein, um wichtige Aufgaben für Fälle und Benutzer zu automatisieren, z. B. abrufen von Benutzer-, Warnungs- und Fallinformationen, die sie für Beteiligte und andere Apps freigeben möchten, das Automatisieren von Aktionen wie das Veröffentlichen von Fallnotizen und vieles mehr.
- [Aktivitäten-Explorer](insider-risk-management-alerts.md#activity-explorer-preview): Der Beim Überprüfen von Warnungen verfügbare Aktivitäts-Explorer bietet Ermittlern und Analysten ein umfassendes Analysetool zum Drillen der einzelnen Warnungen. Überprüfen Sie schnell eine Zeitachse erkannter riskanter Aktivitäten, und identifizieren und filtern Sie alle Risikoaktivitäten im Zusammenhang mit Warnungen.

### <a name="retention-policies-and-retention-labels"></a>Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

- [Unterstützung für Yammer](retention-policies-yammer.md). Sie können jetzt Aufbewahrungsrichtlinien verwenden, um Yammer und private Nachrichten zu behalten und zu löschen.
- [Wenden Sie Bezeichnungen auf Aufzeichnungen von Teams-Besprechungen an.](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings) Verwenden Sie beim Erstellen einer Richtlinie für automatische Bezeichnungen den Stichwortabfrage-Editor, um #A0 zu identifizieren, die in den #A1 oder in SharePoint gespeichert sind.

### <a name="records-management"></a>Datensatzverwaltung

[Unterstützung für behördliche Datensätze](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record). Durch das Klassifizieren einer Bezeichnung als behördlicher Datensatz werden die Einschränkungen für Inhalte erhöht, auf die die Bezeichnung angewendet wird, und die verfügbaren Verwaltungsaktionen für die Bezeichnung selbst werden eingeschränkt. Nachdem sie beispielsweise auf Inhalte angewendet wurde, kann niemand, nicht einmal ein globaler Administrator, die Bezeichnung entfernen. [Erfahren Sie](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) mehr darüber, welche Aktionen für behördliche Datensätze zulässig und blockiert sind.

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

[Support für Us Government-Kunden](/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description). Vertraulichkeitsbezeichnungen werden jetzt nur noch für den Azure Information Protection Unified Labeling Client und Scanner für GCC-, GCC High- und DoD-Kunden unterstützt.

### <a name="trainable-classifiers"></a>Trainierbare Klassifizierungsmerkmale

Neue Umschulungs- und Feedbackfunktionen verbessern die Genauigkeit und minimieren falsch positive Übereinstimmungen für alle benutzerdefinierten Klassifikatoren und einige vordefinierte Klassifizierungen. Mit diesem Fluss können Sie Feedback darüber bereitstellen, ob Elemente bestimmten Klassifizierungen entsprechen, andere Klassifizierungen vorschlagen, die Elementen zugeordnet werden, und Klassifikatoren umtrainieren, um die Übereinstimmungsgenauigkeit zu verfeinern und zu verbessern.

Diese neue Funktion ist in den folgenden Features enthalten:

> [!NOTE]
> Wenn Sie für alle Features mindestens 30 Feedbackantworten bereitstellen, erstellen wir eine umtrainierte Version dieser Klassifizierung, die Sie überprüfen können. Wenn eine Verbesserung vor sich geht, können Sie den Klassifikator erneut veröffentlichen.

- [Trainierbare Klassifizierungen](classifier-learn-about.md#retraining-classifiers): Um die Genauigkeit ihrer veröffentlichten Klassifizierungen zu verbessern, können Sie Feedback dazu geben, ob die erkannten Elemente mit dem Klassifizierungsfeeder übereinstimmen.
- [Kommunikationskonformität](classifier-how-to-retrain-comms-compliance.md). Mit der **neuen Aktion Zur** Verbesserung der Klassifizierungssanierung können Sie Feedback darüber geben, ob ein Element aus einer Warnung zur Kommunikationskonformität mit dem in der Kommunikationskonformitätsrichtlinie konfigurierten Klassifizierungselement entspricht.
- [Inhalts-Explorer](classifier-how-to-retrain-content-explorer.md): Wenn Sie eine Aufbewahrungsrichtlinie für automatische Bezeichnungen einrichten, um automatisch Bezeichnungen auf E-Mail-Nachrichten anzuwenden, die mit trainierbaren Klassifizierungen übereinstimmen, können Sie den Inhalts-Explorer verwenden, um die gekennzeichneten Elemente zu überprüfen und Feedback darüber zu geben, ob die Elemente mit dem Klassifizierungstyp übereinstimmen.

## <a name="august-2020"></a>August 2020

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>Spotlight: Updates zur Risiko- und Kommunikationskonformität von Insidern

Mehrere neue und verbesserte Features werden in diesem Monat in der öffentlichen Vorschau angezeigt:

**Insider-Risikomanagement**

- Sehen Sie sich unsere sechs neuen [Richtlinienvorlagen an:](insider-risk-management-policies.md#policy-templates)
    - Datenlecks nach Prioritätsbenutzern
    - Datenlecks durch unzufriedene Benutzer
    - Verstöße gegen allgemeine Sicherheitsrichtlinien
    - Sicherheitsrichtlinienverletzungen durch ausscheidende Benutzer
    - Sicherheitsrichtlinienverletzungen durch Prioritätsbenutzer
    - Sicherheitsrichtlinienverletzungen durch verärgerte Benutzer

- Mit der [Integration in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) können Sie Microsoft Defender for Endpoint-Warnungen nach Aktivitäten importieren und filtern, die von Richtlinien erkannt werden, die aus den neuen Richtlinienvorlagen für Sicherheitsverletzungen erstellt wurden. Es gibt auch [](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview) eine zugehörige Einstellung für Insiderrisiken, bei der Sie Sicherheitswarnungen basierend auf dem Microsoft Defender for Endpoint-Benachrichtigungstriagestatus in das Insiderrisikomanagement importieren können.

    > [!NOTE]
    > Um die Microsoft Defender for Endpoint-Integration (einschließlich der neuen Vorlagen für Sicherheitsrichtlinienverletzung) nutzen zu können, müssen Sie Microsoft Defender for Endpoint in Ihrer Organisation konfigurieren. Außerdem müssen Sie Microsoft Defender for Endpoint für die Integration von Insider-Risikomanagement aktivieren, indem Sie erweiterte Features [in Microsoft Defender for Endpoint konfigurieren.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)
 
- Anpassen von Schwellenwerten für Indikator beim [Erstellen einer Richtlinie](insider-risk-management-policies.md#create-a-new-policy).
- Richten Sie [Benutzergruppen mit](insider-risk-management-settings.md#priority-user-groups-preview) Priorität ein, um Benutzer in Ihrer Organisation zu definieren, deren Aktivität basierend auf Faktoren wie Position, Zugriffsebene auf vertrauliche Informationen oder Risikoverlauf genauer zu überwachen ist.
- Verwenden Sie Office 365-Verwaltungsaktivitäts-APIs, um Details zu Insiderrisikowarnungen in andere Anwendungen zu exportieren, die Ihre Organisation möglicherweise zum Verwalten oder Aggregieren von Insiderrisikodaten verwendet. [](insider-risk-management-settings.md#export-alerts-preview)
- Neue [Domäneneinstellungen helfen](insider-risk-management-settings.md#domains-preview) Ihnen beim Definieren und Steuern von Risikostufen für Aktivitäten in bestimmten Domänen.

**Kommunikationscompliance**

- Beim [Überprüfen von Nachrichten in einer](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)Warnung können Sie nun unangemessene Nachrichten in Microsoft Teams-Kanälen, 1:1- und Gruppenchats entfernen. Entfernte Nachrichten und Inhalte werden durch einen Richtlinientipp ersetzt, in dem erläutert wird, dass sie aufgrund vertraulicher Inhalte entfernt wurden.
- Neue [Kommunikationsrollen](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) (diese werden auch in neuen Rollengruppen zur Kommunikationskonformität aufgenommen, die im September veröffentlicht werden).
- Neue Kommunikationskonformitätseinstellungen, die Einstellungen für [Datenschutz-](communication-compliance-feature-reference.md#privacy) und [Benachrichtigungsvorlagen enthalten.](communication-compliance-feature-reference.md#notice-templates)
- Neue [Klassifizierungen,](communication-compliance-feature-reference.md#classifiers) mit deren Hilfe Bilder für Erwachsene, Rassivität und Gory erkannt werden können.
- Neue Benachrichtigung "Muster erkannt", die beim Überprüfen von Nachrichten [in](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details) einer Warnung angezeigt wird, informiert Sie über das erneute Auftreten von Instanzen desselben Verhaltens durch einen Benutzer.

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

- Für US Government-Mandanten (GCC, GCC-HC, und DoD) werden Vertraulichkeitsbezeichnungen derzeit nur für den Azure Information Protection-Client für einheitliche Bezeichnungen und den Scanner unterstützt. Weitere Informationen finden Sie in der [Dienstbeschreibung des Azure Information Protection Premium Government ](/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description).
- Sie können jetzt [Security & Compliance Center PowerShell](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) verwenden, um alle Einstellungen zu erstellen und zu konfigurieren, die im Labeling Admin Center angezeigt werden. Dies bedeutet, dass Sie nicht nur PowerShell für Einstellungen verwenden können, die in den Bezeichnungsverwaltungscentern nicht verfügbar sind, sondern jetzt auch die Erstellung und Wartung von Vertraulichkeitsbezeichnungen und Vertraulichkeitsbezeichnungsrichtlinien vollständig skripten können.

### <a name="records-management-content-overhaul"></a>Datensatzverwaltung: Überarbeitung von Inhalten

Neue Dokumente, die Bereitstellungsschritte, das Markieren von Inhalten als Datensätze und die Versionsierung von Datensätzen abdecken:

- [Erste Schritte mit der Datensatzverwaltung](get-started-with-records-management.md)
- [Datensätze mithilfe von Aufbewahrungsbezeichnungen deklarieren](declare-records.md)
- [Versionsverwaltung zur Aktualisierung von Datensätzen verwenden, die in Microsoft Office SharePoint Online oder OneDrive gespeichert sind](record-versioning.md)

### <a name="retention-labels--policies"></a>Aufbewahrungsbezeichnungen & Richtlinien

Aufbewahrungsbezogene Administratoraktivitäten werden nun aufgezeichnet und können im Überwachungsprotokoll überprüft werden. Die vollständige Liste finden Sie unter [ Aufbewahrungsrichtlinie und Aufbewahrungsbezeichnungsaktivitäten](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- Beim [Hinzufügen einer Auflistung zu](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)einem Überprüfungssatz können Sie nun moderne Anlagen (auch als "Cloudanlagen" bezeichnet) und SharePoint-Dokumentversionen hinzufügen.
- Neue [direkte Download-Exporterfahrung,](export-documents-from-review-set.md)sodass keine Azure Storage Explorer zum Herunterladen von Fallinhalten verwendet werden muss.