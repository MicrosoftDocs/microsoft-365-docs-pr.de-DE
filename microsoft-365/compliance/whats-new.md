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
description: Unabhängig davon, ob neue Lösungen zum Compliance Center hinzugefügt werden, vorhandene Funktionen auf der Grundlage Ihres Feedbacks aktualisiert werden oder eine aktualisierte Dokumentation bereitgestellt wird, hilft Ihnen Microsoft 365, die ständig wechselnde Compliance-Landschaft zu überwachen. Finden Sie heraus, was wir diesen Monat vorhaben.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3688ee7390b7cadf701e8dbefd8b12c82cf6d89c
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751592"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Neuerungen in Microsoft 365 Compliance

Unabhängig davon, ob Sie dem [Microsoft 365 Compliance Center](microsoft-365-compliance-center.md)neue Lösungen hinzufügen, vorhandene Features auf der Grundlage Ihres Feedbacks aktualisieren oder eine aktualisierte und aktualisierte Dokumentation bereitstellen, hilft Ihnen Microsoft 365, die ständig wechselnde Compliance-Landschaft zu überwachen. Sehen Sie sich die folgenden Informationen an, um zu erfahren, was in der Microsoft 365-Compliance heute neu ist. 

> [!NOTE]
> Einige Compliance-Features werden mit unterschiedlichen Geschwindigkeiten für unsere Kunden bereit gesetzt. Wenn Sie noch kein Feature sehen, versuchen Sie, sich selbst zu [Gezieltes Release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365) hinzuzufügen.


> [!TIP]
> Interessieren Sie sich dafür, was in anderen Admin Centers geschieht? Dann lesen Sie die folgenden Artikel:<br>[Neuerungen im Microsoft 365 Admin Center](https://docs.microsoft.com/office365/admin/whats-new-in-preview)<br>[Aktive Websites im SharePoint Online Admin Center](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Neuerungen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
Besuchen Sie die [Microsoft 365-Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap), um sich über Features von Microsoft 365 zu informieren, die eingeführt wurden, bereitgestellt werden, sich in der Entwicklung befinden, eingestellt oder zuvor veröffentlicht wurden.

## <a name="november--december-2020"></a>November & Dezember 2020
Nur eine Erinnerung daran, dass wir häufig neue und aktualisierte Features in einem Vorschaustatus veröffentlichen, um zu erfahren, wie Sie verwendet werden, damit wir Sie verfeinern und verbessern können, bevor Sie zur allgemeinen Verfügbarkeit freigeben. Ihr Feedback ist kritisch während der Vorschau (und darüber hinaus), so stellen Sie sicher, dass Sie uns Ihre Meinung mitteilen, indem Sie die Feedback Karte unten rechts im Compliance Center öffnen.

![Feedback](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>Spotlight: Endpunkt-Datenverlust Verhinderung (DLP) veröffentlicht

[EndPoint DLP](endpoint-dlp-learn-about.md) erweitert die Funktionen für die Aktivitätsüberwachung und den Schutz von DLP auf vertrauliche Informationen auf Windows 10-Geräten. Nach dem [Onboarding](dlp-configure-endpoints.md) von Geräten im Microsoft 365 Compliance Center können Sie DLP-Richtlinien einrichten, um die vertraulichen Informationen auf diesen Geräten zu schützen.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

Um die Verwaltung verschlüsselter Inhalte im eDiscovery-Workflow zu vereinfachen, integrieren Microsoft 365 eDiscovery-Tools jetzt die [Entschlüsselung von verschlüsselten Dateien](ediscovery-decryption.md) , die an e-Mail-Nachrichten angehängt und in Exchange gesendet werden. Außerdem werden verschlüsselte Dokumente, die in SharePoint und OneDrive gespeichert sind, in Advanced eDiscovery entschlüsselt.

### <a name="compliance-manager"></a>Compliance-Manager

- [Unterstützung für Microsoft 365 Government-Abonnements](compliance-manager.md). Compliance-Manager steht jetzt für moderate und hohe Kunden von US Government Community (gcc) zur Verfügung.
- [Microsoft Compliance Configuration Analyzer für Compliance-Manager](compliance-manager-mcca.md). Neues PowerShell-basiertes Tool, mit dem Sie die ersten Schritte mit Compliance-Manager durchsuchen können, indem Sie die aktuellen Konfigurationen Ihrer Organisation überprüfen und diese anhand der empfohlenen Best Practices von Microsoft 365 validieren.
- [Neue Vorlagen](compliance-manager-templates-list.md). 56 neue Vorlagen hinzugefügt, und insgesamt Compliance-Manager-Vorlagen wurden auf über 230 gebracht.

### <a name="data-connectors"></a>Datenconnectors

[Fünf neue Globanet-Konnektoren in der Vorschau](archiving-third-party-data.md#third-party-data-connectors). Zu den neuen Connectors gehören Reuters-Geschäfte, Reuters FX, CellTrust, XIP, generische MS SQL-Datenbankdaten.

### <a name="retention-labels-disposition-review"></a>Aufbewahrungs Bezeichnungen (Dispositions Überprüfung)

Um Elemente während einer Dispositions Überprüfung anzuzeigen, müssen Benutzer jetzt Mitglieder der [Rollengruppen Inhalts-Explorer-Inhaltsanzeige und Inhalts-Explorer-Listenanzeige](disposition.md#permissions-for-disposition)sein. Obwohl zum Überprüfen von Elementen erforderlich, sind diese Rollengruppen nicht erforderlich, um die Dispositions Überprüfung abzuschließen.

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

- [(Vorschau) externe Freigabeeinstellungen für SharePoint-Websites](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings). Beim Erstellen einer Bezeichnung, die für Gruppen und Websites verwendet wird, wird eine Option zum Steuern der externen Freigabe für SharePoint-Websites mit Anwendung der Bezeichnung angezeigt. Sie können angeben, dass die Freigabe für alle, neuen und vorhandenen Gäste, nur für vorhandene Gäste oder nur für Benutzer in Ihrer Organisation zulässig ist. Wenn die Bezeichnung angewendet wird, ersetzen die Bezeichnungs Einstellungen alle [im SharePoint Admin Center konfigurierten](https://docs.microsoft.com/sharepoint/change-external-sharing-site)externen Freigabeeinstellungen.
- [Entfernen Sie Label und Encryption aus einem beschrifteten Dokument](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document). Um sowohl eine Bezeichnung als auch die Verschlüsselung zu entfernen, die von einem beschrifteten Dokument in SharePoint erzwungen wird, können globale Administratoren und SharePoint-Administratoren das neue `Unlock-SPOSensitivityLabelEncryptedFile` Cmdlet ausführen. Dieses Cmdlet wird auch dann ausgeführt, wenn der Administrator nicht über Zugriffsberechtigungen für die Website oder Datei verfügt oder wenn der Azure Rights Management-Dienst nicht verfügbar ist.

## <a name="october-2020"></a>Oktober 2020

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

[Unterstützung für CJK-Sprachen](ediscovery-cjk-support.md). Advanced eDiscovery unterstützt jetzt Doppelbyte-Zeichensatz Sprachen, die als CJK-Sprachen bezeichnet werden (umfasst vereinfachtes Chinesisch, traditionelles Chinesisch, Japanisch und Koreanisch). Diese können in mehreren Szenarien für erweiterte Überprüfungs Sätze verwendet werden.

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

- [Bezeichnungsbereich](sensitivity-labels.md#label-scopes). Beim Erstellen einer Sensitivitäts Bezeichnung wird eine neue Option zum Definieren des Bereichs für die Bezeichnung angezeigt. Mit dieser Option können Sie Bezeichnungen nur für Dateien und e-Mails, Container (wie SharePoint-Websites und-Teams) oder beides konfigurieren.
- [Dynamische Inhalts Markierung](sensitivity-labels-office-apps.md#dynamic-markings-with-variables). Wenn Sie die Inhalts Markierung für eine Vertraulichkeits Bezeichnung konfigurieren, können Sie nun die dynamischen Variablen wie `${Item.Label}` und `${Item.Location}` in der Textzeichenfolge für die Kopfzeile, die Fußzeile oder das Wasserzeichen verwenden.

## <a name="september-2020"></a>September 2020

### <a name="spotlight-compliance-manager"></a>Spotlight: Compliance-Manager

Bei Ignite in diesem Jahr angekündigt, wird das Compliance-Ergebnis als [Compliance-Manager](compliance-manager.md)umbenannt. In dieser Version wird der Übergang von der vorherigen Startseite des Compliance Managers im Dienst Vertrauensstellungs Portal abgeschlossen und eine End-to-End-Compliance-Verwaltungslösung im Microsoft 365 Compliance Center eingeführt.

Sehen Sie sich das Video unten an, um zu erfahren, wie Compliance-Manager die Compliance-Verwaltung in Ihrer Organisation erleichtert.
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>Erweiterte Überwachung

- Die neue 10-jährige Aufbewahrung von Überwachungsprotokollen hilft bei der Unterstützung lang andauernder Untersuchungen und der Reaktion auf regulatorische, rechtliche und interne Verpflichtungen.
- [Drei neue wichtige Ereignisse](advanced-audit.md#access-to-crucial-events-for-investigations). Die folgenden neuen Ereignisse können Ihnen dabei helfen, mögliche Verstöße zu untersuchen und den Umfang des Kompromisses zu bestimmen: Send, SearchQueryInitiatedExchange und SearchQueryInitiatedSharePoint.

### <a name="communication-compliance"></a>Kommunikationsbezogene Compliance

- [Aktualisierte Rollengruppen](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance). Rollengruppen für die Kommunikations Konformität entsprechen nun der Rollengruppen Struktur, die für die Lösung für das Insider Risikomanagement verfügbar ist.
- [Berichts Dashboard](communication-compliance-feature-reference.md#reports-preview). Ihr zentraler Standort für die Anzeige aller Kommunikations Kompatibilitätsberichte. Berichts-Widgets bieten eine schnelle Übersicht über die am häufigsten benötigten Einblicke für eine Gesamtbewertung des Status von Kommunikations Compliance-Aktivitäten.
- [Power automatisiert Flows](communication-compliance-feature-reference.md#power-automate-flows-preview). Einrichten von Flows zum Automatisieren von Aufgaben für Warnungen und Benutzer, Benachrichtigen von Managern, wenn Benutzer eine Warnung auslösen, und vieles mehr.
- [Korrekturaktion "Klassifizierung verbessern"](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action). Benachrichtigungen mit Elementen, die Schulungs klassifizierten entsprechen, können von Feedback profitieren, um falsch positive Ergebnisse in Ihrer Organisation zu minimieren. Mit der Option " **Klassifizierung verbessern** " können Sie Feedback geben, ob erkannte Elemente mit der in der zugehörigen Kommunikations Konformitätsrichtlinie konfigurierten Klassifizierung übereinstimmen. Sie können sogar andere Klassifizierungen vorschlagen, die dem Element zugeordnet werden sollen, um die Übereinstimmungs Genauigkeit für zukünftige Warnungen zu verbessern.

### <a name="data-connectors"></a>Datenconnectors

- [Neue Drittanbieter-Daten-Konnektoren](archiving-third-party-data.md#third-party-data-connectors). 25 neue Daten-Konnektoren, darunter 14 Konnektoren von Globanet und 8 von TeleMessage.
- [Physischer Badges-Connector](import-physical-badging-data.md). Importieren Sie physische Badges-Daten, wie beispielsweise unformatierte physische Zugriffsereignisse des Mitarbeiters oder physische Zugriffs Warnungen, die vom Badges-System Ihrer Organisation generiert werden. Beispiele hierfür sind Einträge zu Gebäuden, Serverräumen oder Rechenzentren. Physische Badges-Daten können von der Insider Risk Management-Lösung verwendet werden, um Ihre Organisation vor böswilligen Aktivitäten oder Datendiebstahl in Ihrer Organisation zu schützen.

### <a name="insider-risk-management"></a>Insider-Risikomanagement

- [Microsoft Teams-Integration](insider-risk-management-settings.md#microsoft-teams-preview). Wenn die Integration von Microsoft Teams in den Einstellungen für Insider Risiken aktiviert ist, können Sie Koordination und Zusammenarbeit mit anderen Beteiligten in Microsoft Teams für Aufgaben wie die sichere Freigabe und Speicherung von Daten im Zusammenhang mit einzelnen Fällen, das Nachverfolgen und Überprüfen von Reaktions Aktivitäten von Analysten und Ermittlern und vieles mehr.
- [Power automatisiert Flows](insider-risk-management-settings.md#power-automate-flows-preview). Einrichten von Flows zur Automatisierung wichtiger Aufgaben für Fälle und Benutzer, wie das Abrufen von Benutzer-, Benachrichtigungs-und Fall Informationen für die Freigabe für beteiligte und andere apps, das Automatisieren von Aktionen wie das Veröffentlichen von fallnotizen und vieles mehr.
- [Aktivitäten-Explorer](insider-risk-management-alerts.md#activity-explorer-preview): Verfügbar bei der Überprüfung von Benachrichtigungen bietet der Aktivitäts-Explorer den Ermittlern und Analysten ein umfassendes Analyse Tool zum Drilldown in jede Warnung. Überprüfen Sie schnell eine Zeitachse der erkannten riskanten Aktivität, identifizieren und Filtern Sie alle Risiko Aktivitäten, die mit Warnungen verbunden sind.

### <a name="retention-policies-and-retention-labels"></a>Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

- [Unterstützung für jammern](retention-policies-yammer.md). Sie können jetzt Aufbewahrungsrichtlinien verwenden, um jammern von Community-Nachrichten und privaten Nachrichten beizubehalten und zu löschen.
- [Anwenden von Bezeichnungen auf Besprechungen in Microsoft Teams](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings). Verwenden Sie beim Erstellen einer autolabeling-Richtlinie den Keyword-Abfrage-Editor, um Microsoft Teams-Besprechungsaufzeichnungen zu identifizieren, die in OneDrive-Konten der Benutzer oder in SharePoint gespeichert sind.

### <a name="records-management"></a>Datensatzverwaltung

[Unterstützung für regulatorische Datensätze](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record). Durch das Klassifizieren einer Bezeichnung als Regulierungsdaten Satz werden die Einschränkungen für Inhalte erhöht, auf die die Bezeichnung angewendet wird, und die verfügbaren Verwaltungsaktionen für die Bezeichnung selbst werden eingeschränkt. Nachdem er beispielsweise auf Inhalte angewendet wurde, kann niemand, nicht einmal ein globaler Administrator, die Bezeichnung entfernen. [Erfahren Sie mehr](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) darüber, welche Aktionen für regulatorische Datensätze zulässig und blockiert sind.

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

[Unterstützung für Kunden der US-Regierung](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description). Vertraulichkeits Bezeichnungen werden jetzt für gcc-, gcc High-und DoD-Kunden unterstützt, nur für den Azure Information Protection Unified Labeling-Client und-Scanner.

### <a name="trainable-classifiers"></a>Trainierbare Klassifizierungsmerkmale

Neue Umschulungs-und Feedbackfunktionen helfen, die Genauigkeit zu verbessern und falsch positive Übereinstimmungen für alle benutzerdefinierten Klassifizierungen und einige vorab geschulte Klassifizierungen zu minimieren. Mit diesem Fluss können Sie Feedback darüber geben, ob Elemente mit bestimmten Klassifizierungen übereinstimmen, andere Klassifizierungen vorschlagen, um Elemente zuzuordnen, und Klassifizierungen neu auszubilden, um die Übereinstimmungs Genauigkeit zu verfeinern und zu verbessern.

Diese neue Funktion ist in den folgenden Features enthalten:

> [!NOTE]
> Wenn Sie mindestens 30 Feedback Antworten bereitstellen, erstellen wir für alle Features eine Umschulungs Version dieser Klassifizierung, die Sie überprüfen können. Wenn es eine Verbesserung gibt, können Sie die Klassifizierung erneut veröffentlichen.

- [Trainierbare Klassifizierungen](classifier-learn-about.md#retraining-classifiers): Um die Genauigkeit Ihrer veröffentlichten Klassifizierungen zu verbessern, können Sie Feedback darüber geben, ob die erkannten Elemente mit der Klassifizierung übereinstimmen.
- [Kommunikations Kompatibilität](classifier-how-to-retrain-comms-compliance.md). Mit der neuen Aktion zur **Optimierung der Klassifizierung optimieren** können Sie Feedback geben, ob ein Element aus einer Benachrichtigung über die Konformität mit der in der Kommunikations Konformitätsrichtlinie konfigurierten Klassifizierung übereinstimmt.
- [Inhalts-Explorer](classifier-how-to-retrain-content-explorer.md): Wenn Sie eine automatische Bezeichnungsrichtlinie für die Aufbewahrung einrichten, um automatisch Bezeichnungen auf e-Mail-Nachrichten anzuwenden, die Schulungs Klassifizierer entsprechen, können Sie den Inhalts-Explorer verwenden, um die beschrifteten Elemente zu überprüfen und Feedback darüber zu geben, ob die Elemente mit der Klassifizierung übereinstimmen.

## <a name="august-2020"></a>August 2020

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>Spotlight: Compliance-Updates für Insider Risiken und-Kommunikation

Einige neue und verbesserte Features haben die öffentliche Vorschau in diesem Monat erreicht:

**Insider-Risikomanagement**

- Schauen Sie sich unsere sechs neuen [Richtlinienvorlagen](insider-risk-management-policies.md#policy-templates)an:
    - Datenverluste nach Prioritäts Benutzern
    - Datenverluste durch verärgerte Benutzer
    - Allgemeine Sicherheitsrichtlinienverletzungen
    - Sicherheitsrichtlinienverletzungen durch Benutzer, die abgemeldet werden
    - Sicherheitsrichtlinienverletzungen nach Prioritäts Benutzern
    - Sicherheitsrichtlinienverletzungen durch verärgerte Benutzer

- Die Integration mit [Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) ermöglicht das Importieren und Filtern von Microsoft Defender für Endpunkt Warnungen für Aktivitäten, die durch Richtlinien erkannt werden, die aus den neuen Richtlinienvorlagen für Sicherheitsverstöße ermittelt wurden. Es gibt auch eine zugehörige [Einstellung für Insider Risiken](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview) , in der Sie Sicherheitswarnungen in das Insider Risikomanagement basierend auf dem Status "Microsoft Defender for Endpoint Alert Triage" importieren können.

    > [!NOTE]
    > Um die Vorteile von Microsoft Defender für die Endpunkt Integration (einschließlich der neuen Vorlagen für Sicherheitsrichtlinienverletzungen) nutzen zu können, müssen Sie Microsoft Defender for Endpoint in Ihrer Organisation konfigurieren lassen. Sie müssen auch Microsoft Defender für Endpoint for Insider Risk Management Integration aktivieren, indem Sie [Erweiterte Features in Microsoft Defender für Endpoint konfigurieren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).
 
- Passen Sie Indikator Schwellenwerte beim [Erstellen einer Richtlinie](insider-risk-management-policies.md#create-a-new-policy)an.
- Einrichten von [Prioritäts Benutzergruppen](insider-risk-management-settings.md#priority-user-groups-preview) zum Definieren von Benutzern in Ihrer Organisation, deren Aktivität anhand von Faktoren wie Position, Zugriffsebene auf vertrauliche Informationen oder Risikoverlauf genauer zu Untersuchung erforderlich ist.
- Verwenden Sie Office 365 Verwaltungs Aktivitäts-APIs, um [Insider Risiko-Warnungsdetails](insider-risk-management-settings.md#export-alerts-preview) in andere Anwendungen zu exportieren, die Ihre Organisation zum Verwalten oder Aggregieren von Insider Risikodaten verwenden kann.
- Mithilfe neuer [Domäneneinstellungen](insider-risk-management-settings.md#domains-preview) können Sie Risikoebenen für Aktivitäten in bestimmten Domänen definieren und steuern.

**Kommunikationscompliance**

- Wenn Sie [Nachrichten in einer Warnung überprüfen](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action), können Sie jetzt unangemessene Nachrichten in Microsoft Teams-Kanälen, 1:1 und Gruppenchats entfernen. Entfernte Nachrichten und Inhalte werden durch einen richtlinientipp ersetzt, der erklärt, dass er aufgrund von vertraulichen Inhalten entfernt wurde.
- Neue [Kommunikationsrollen](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) (diese werden auch in den neuen Kommunikationsrichtlinien-Rollengruppen enthalten sein, die im September veröffentlicht werden).
- Neue Kompatibilitätseinstellungen für Kommunikation mit Einstellungen für [Datenschutz](communication-compliance-feature-reference.md#privacy-preview) -und [Benachrichtigungsvorlagen](communication-compliance-feature-reference.md#notice-templates).
- Neue [Klassifizierungen](communication-compliance-feature-reference.md#classifiers) zur Unterstützung der Erkennung von Erwachsenen, rassigen und blutigen Bildern.
- Die neue Meldung "Pattern detected", die beim über [Prüfen von Nachrichten in einer Warnung](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details) angezeigt wird, informiert Sie über wiederkehrende Instanzen desselben Verhaltens durch einen Benutzer.

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

- Für US Government-Mandanten (GCC, GCC-HC, und DoD) werden Vertraulichkeitsbezeichnungen derzeit nur für den Azure Information Protection-Client für einheitliche Bezeichnungen und den Scanner unterstützt. Weitere Informationen finden Sie in der [Dienstbeschreibung des Azure Information Protection Premium Government ](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description).
- Sie können nun [Security & Compliance Center PowerShell verwenden](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) , um alle Einstellungen zu erstellen und zu konfigurieren, die in Ihrem Bezeichnungs-Admin Center angezeigt werden. Dies bedeutet, dass Sie zusätzlich zur Verwendung von PowerShell für Einstellungen, die in den Bezeichnungs-Admin Center nicht verfügbar sind, jetzt die Erstellung und Verwaltung von Vertraulichkeits Bezeichnungen und Richtlinien für die Sensitivitäts Kennzeichnung vollständig Skriptieren können.

### <a name="records-management-content-overhaul"></a>Datensatzverwaltung: Überarbeitung der Inhalte

Neue Dokumente für Bereitstellungsschritte, kennzeichnen von Inhalten als Datensätzen und Aufzeichnen der Versionsverwaltung:

- [Erste Schritte mit der Datensatzverwaltung](get-started-with-records-management.md)
- [Datensätze mithilfe von Aufbewahrungsbezeichnungen deklarieren](declare-records.md)
- [Versionsverwaltung zur Aktualisierung von Datensätzen verwenden, die in Microsoft Office SharePoint Online oder OneDrive gespeichert sind](record-versioning.md)

### <a name="retention-labels--policies"></a>Aufbewahrungs Bezeichnungen & Richtlinien

Aufbewahrungs bezogene Administratoraktivitäten werden jetzt aufgezeichnet und können im Überwachungsprotokoll überprüft werden. Die vollständige Liste finden Sie unter [ Aufbewahrungsrichtlinie und Aufbewahrungsbezeichnungsaktivitäten](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- Wenn Sie einer [Überprüfungsgruppe eine Sammlung hinzufügen](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review), können Sie jetzt moderne Anlagen (auch "Cloud Attachments" genannt) und SharePoint-Dokumentversionen einschließen.
- Neue [direkte Download Exporterfahrung](export-documents-from-review-set.md), wodurch die Verwendung des Azure Storage Explorers zum Herunterladen von Groß-/Kleinschreibung nicht mehr erforderlich ist.


## <a name="july-2020"></a>Juli 2020

### <a name="spotlight-on-help-docs"></a>Hilfedokumente im Rampenlicht

Damit Sie besser verstehen, welche Compliance-Lösungen zum Schutz und zur Steuerung vertraulicher Daten Ihrer Organisation verwendet werden, haben wir zwei neue Zielseiten mit Übersichten darüber erstellt, wie die Lösungen zusammenarbeiten, um diese Ziele zu erreichen, einschließlich Links zu verwandten Dokumenten, damit Sie weiter eintauchen können.

[Microsoft Information Protection in Microsoft 365](information-protection.md)<br>
[Microsoft-Informationsgovernance in Microsoft 365](manage-Information-governance.md)

### <a name="advanced-ediscovery-add-non-custodial-data-sources-to-your-cases"></a>Erweiterte eDiscovery: Hinzufügen von Datenquellen ohne Freiheitsentzug zu ihren Fällen

Hinzufügen von Daten zu einem Fall, ohne ihn einer Depotbank zuzuordnen (als [Datenquellen ohne Freiheitsentzug](non-custodial-data-sources.md)bezeichnet). Wenn Sie diese Daten ohne Freiheitsentzug in die Warteschleife stellen müssen, können Sie dies mit unserem neuen Feature für erweiterte Indizierung tun.

### <a name="data-connectors-hr-connector-enhancements"></a>Daten Konnektoren: Verbesserungen des HR-Connectors

(In der Vorschau) Mit einer neuen Version des [HR-Konnektors](import-hr-data.md) können Sie Daten im Zusammenhang mit Änderungen auf Auftragsebene, Leistungsbewertungen und Pläne zur Leistungsverbesserung importieren. Diese Daten können dann in mehreren [Insider Risikorichtlinien](insider-risk-management-policies.md) verwendet werden, um verwandte Aktivitäten zu erkennen.

### <a name="retention-labels-new-support-for-email"></a>Aufbewahrungs Bezeichnungen: neue Unterstützung für e-Mail

Sie können jetzt eine [Aufbewahrungs Bezeichnung](retention.md#retention-labels) erstellen, um e-Mails basierend auf der Bezeichnung der Nachrichten beizubehalten. Dies gilt nicht für Kalenderelemente, die basierend auf dem Senden des Elements beibehalten werden.

### <a name="sensitivity-labels-new-feature-and-an-improvement"></a>Vertraulichkeits Bezeichnungen: neues Feature und eine Verbesserung

- (In der Vorschau) Wenn Sie Verschlüsselungseinstellungen für eine Bezeichnung konfigurieren, suchen Sie nach der neuen Option, um die [Doppelschlüssel Verschlüsselung](encryption-sensitivity-labels.md#double-key-encryption) zu verwenden, um die beschrifteten Dateien und e-Mails weiter zu schützen.
- Beim Erstellen oder Löschen von Vertraulichkeits Bezeichnungen oder beim Erstellen, bearbeiten oder Löschen Ihrer Bezeichnungsrichtlinien werden Änderungen jetzt innerhalb einer Stunde für alle Benutzer, Apps und Dienste synchronisiert.

## <a name="june-2020"></a>Juni 2020

### <a name="spotlight-new-data-connectors-hit-preview"></a>Spotlight: neue Daten Konnektor-Treffer Vorschau

Auf der Grundlage unserer Zusage, Ihnen beim Importieren von Daten aus weiteren Drittanbieterquellen in Microsoft 365 zu helfen, freuen wir uns, die Preview-Version von zwei weiteren Data Connectors anzukündigen:

- [Bloomberg-Nachricht](archive-bloomberg-message-data.md). Importieren und archivieren Sie e-Mail-Daten von Finanzdienstleistungen aus dem Bloomberg-Nachrichten Zusammenarbeits Tool. Nachdem die Daten in Postfächern gespeichert wurden, können Sie auf die Daten in Compliance-Features wie Beweissicherungsverfahren, Inhaltssuche, in-situ-Archivierung, Überwachung, Kommunikations Konformität und Aufbewahrungsrichtlinien zugreifen und diese verwenden.
- [Ice-Chat](archive-icechat-data.md). Importieren und Archivieren von Finanz Dienstleistungs-Chatdaten aus dem ICE Chat-Zusammenarbeits Tool. Nachdem die Daten in Postfächern gespeichert wurden, können Sie auf die Daten in Compliance-Features wie Beweissicherungsverfahren, eDiscovery, Archivierung, Überwachung, Kommunikations Konformität und Aufbewahrungsrichtlinien zugreifen und diese verwenden.

### <a name="compliance-score--compliance-manager-the-hits-keep-coming"></a>Kompatibilitätsbewertung & Compliance-Manager: die Treffer kommen immer wieder

Juni-Updates enthalten eine neue Bewertungs Drilldown-Ansicht in [Compliance Score](compliance-score.md). Überwachen Sie den Status der Steuerung, fügen Sie Bewertungen direkt aus dem Kompatibilitäts Bewertungsergebnis hinzu, und löschen Sie Sie.

Möchten Sie über die neuesten Updates für Compliance-Score und Compliance-Manager informiert werden? Bookmarken Sie die [Versionshinweise für das Konformitäts Bewertungs](compliance-score-release-notes.md) System, und schauen Sie häufig zurück.

## <a name="may-2020"></a>Mai 2020

### <a name="spotlight-data-classification-is-officially-released"></a>Spotlight: die Datenklassifizierung wurde offiziell veröffentlicht.

Die Datenklassifizierung, aka "[Wissen Ihrer Daten](data-classification-overview.md)", Funktionen (Analyse, Inhalts-Explorer und Aktivitäts-Explorer) haben die Vorschauphase abgeschlossen und stehen allen Organisationen zur Verfügung. Leistungsstarke Einblicke und Tools helfen Ihnen dabei, zu ermitteln und zu bewerten, wie vertrauliche Informationen und Beschriftungen (Aufbewahrung und Vertraulichkeit) in Ihrem gesamten Unternehmen verwendet werden. Überprüfen Sie Inhalte, die vertrauliche Informationen enthalten oder Bezeichnungen angewendet haben, untersuchen Sie die Beschriftungs Aktivität in Microsoft 365-Speicherorten, erstellen Sie benutzerdefinierte vertrauliche Informationstypen und vieles mehr.

Video Tour durchführen...

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

### <a name="trainable-classifiers-a-fix-and-a-feature"></a>Schulungsable Klassifizierer: eine Korrektur und ein Feature

Bietet möglicherweise weitere Verbesserungen für Schulungs Klassifizierer:

- Eine Korrektur basierend auf Ihrem Feedback: Wenn Sie eine benutzerdefinierte Klassifizierung Aussaaten und trainieren, müssen Sie die SharePoint-Website-URLs und Ordnerpfade nicht mehr manuell eingeben. Sie können nun eine Liste mit Websites und Ordnern aus einer vorab Auffüllung auswählen.
- Neues Feature: Wenn Sie eine Vertraulichkeits Bezeichnung erstellen und Einstellungen für die automatische Kennzeichnung für Office-Apps konfigurieren, können Sie nun automatisch die Bezeichnung auf Inhalte anwenden (oder diesen Benutzern empfehlen, diese anzuwenden), die mit Schulungs Klassifizierern übereinstimmen. [Weitere Informationen](apply-sensitivity-label-automatically.md#configuring-trainable-classifiers-for-a-label)

### <a name="communication-compliance-yammer-support-is-here"></a>Kommunikation Compliance: jammern Unterstützung ist hier

Private Nachrichten und öffentliche Community-Unterhaltungen in jammern werden in Kommunikationsrichtlinien unterstützt. Yammer ist ein optionaler Kanal und muss sich im [nativen Modus](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) befinden, um die Überprüfung von Nachrichten und Anlagen zu unterstützen.

### <a name="data-loss-prevention-new-sharing-restriction"></a>Verhinderung von Datenverlust: neue Freigabe Einschränkung

Beim Einrichten einer DLP-Richtlinie zum Schutz von Inhalten in SharePoint oder OneDrive können Sie nun die Aktion "Zugriff auf Inhalte einschränken" so konfigurieren, dass Personen, die Zugriff auf die Inhalte erhalten haben, über die Option "[jeder, der den Link](https://support.microsoft.com/office/share-files-outside-your-organization-with-anyone-links-53e91027-fb8e-4a6e-a3e4-5df4be32e38a)aktiviert hat" blockiert werden.

### <a name="insider-risk-management-tailor-your-alert-volume"></a>Insider Risikomanagement: Anpassen des Warnungs Volumens

Benutzeraktivitäten, die von Insider Risikorichtlinien erkannt werden, werden mit einem bestimmten Risikoergebnis versehen, das wiederum den Warnungsschweregrad (niedrig, Mittel, hoch) bestimmt. Standardmäßig generiert Microsoft 365 eine bestimmte Anzahl von Warnungen mit niedrigem, mittlerem und hohem Schweregrad, aber mit der neuen Einstellung für das [Benachrichtigungs Volume](insider-risk-management-settings.md#alert-volume)können Sie die Lautstärke entsprechend Ihren Anforderungen erweitern oder verringern.

### <a name="pst-import-new-region-supported"></a>PST-Import: neue Region unterstützt

Netzwerk Upload ist jetzt in den Vereinigten Arabischen Emiraten verfügbar.

### <a name="sensitivity-labels-new-privacy-option"></a>Vertraulichkeits Bezeichnungen: neue Datenschutzoption

Wenn Sie [Standort-und Gruppeneinstellungen](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) für eine Bezeichnung konfigurieren, können Sie nun die Option Datenschutz auf **None festlegen – Benutzer auswählen, wer auf die Website zugreifen kann**. Dies ist hilfreich, wenn Sie Inhalte im Container mithilfe einer Vertraulichkeits Bezeichnung schützen möchten, aber Benutzer weiterhin die Datenschutzeinstellung selbst konfigurieren können.

## <a name="april-2020"></a>April 2020

### <a name="records-management-overhauland-a-new-addition"></a>Datensatzverwaltung: Überholung... und eine neue Ergänzung

April enthält ein paar wichtige Updates für unsere Datensatzverwaltungslösung:

- Der Abschnitt "Datensatzverwaltung" ist jetzt vollständig im Compliance Center verfügbar. Nutzen Sie aktualisierte Benutzeroberflächen und Funktionen für Dateiplan, Aufbewahrungs Bezeichnungen und Bezeichnungsrichtlinien, Ereignisse und Disposition.
- Apropos Disposition: Wir haben auch einen [Nachweis über die Disposition](disposition.md#disposition-of-records) für Datensätze in SharePoint und OneDrive ausgeführt. Sie können jetzt eine Liste der Elemente an diesen Orten sehen, die automatisch oder nach einer Dispositions Überprüfung verworfen wurden.

### <a name="sensitivity-labels-preview-auto-labeling-policies"></a>Vertraulichkeits Bezeichnungen: Vorschau Richtlinien für die automatische Kennzeichnung

Mit automatisch bezeichnenden Richtlinien können Sie jetzt automatisch Vertraulichkeits Bezeichnungen auf SharePoint-und OneDrive-Dokumente anwenden, die bereits gespeichert sind (aka "Daten im Ruhezustand") und e-Mails, die bereits gesendet oder empfangen werden (aka "e-Mail bei der Übertragung"). Da diese Kennzeichnung von Diensten anstelle von apps angewendet wird, müssen Sie sich keine Gedanken darüber machen, was apps-Benutzer haben und welche Version.

Diese Funktion erweitert die vorhandene clientseitige Beschriftung, die bereits in den Einstellungen für die automatische Beschriftung für Office-Apps enthalten ist, wenn Sie eine Vertraulichkeits Bezeichnung erstellen. Wenn Sie die Unterschiede und Vorteile beider Optionen für die automatische Bezeichnungs Funktion beschleunigen möchten, lesen Sie den [aktualisierten Artikel](apply-sensitivity-label-automatically.md).

## <a name="march-2020"></a>März 2020

### <a name="introducing-advanced-audit"></a>Einführung in die erweiterte Überwachung

Mit der [erweiterten Überwachung in Microsoft 365](advanced-audit.md) werden neue Überwachungsfunktionen eingeführt, die Ihrer Organisation bei forensischen und Compliance-Untersuchungen helfen können. Zu den Highlights gehören die langfristige Aufbewahrung von Überwachungsprotokollen, benutzerdefinierte Überwachungsprotokoll-Aufbewahrungsrichtlinien, neue *MailItemsAccessed* -Post Fach Überwachungsaktionen und die Einführung eines neuen Einschränkungs Grenzwerts auf Mandantenebene, der Ihrer Organisation ein eigenes Kontingent für die Bandbreite für den Zugriff auf Ihre Überwachungsdaten bietet.

### <a name="compliance-score--compliance-manager-preview-the-latest-enhancements"></a>Kompatibilitätsbewertung & Compliance-Manager: Vorschau der neuesten Verbesserungen

Zu den wichtigsten Updates für diese Preview-Version gehören:

- Vereinfachter Prozess zum Erstellen und Ändern von Vorlagen
- Versions Verwaltungs Hinweis und-Steuerung für Vorlagen und Aktionen
- Synchronisieren allgemeiner Aktionen über Gruppen hinweg
- Sprachunterstützung jetzt erweitert auf Chinesisch (vereinfacht), Chinesisch (traditionell), Französisch, Deutsch, Italienisch, Japanisch, Koreanisch, Portugiesisch (Brasilien), Russisch und Spanisch

Weitere Informationen zur [Kompatibilitätsbewertung](compliance-score.md) und zum [Compliance-Manager](compliance-manager-overview.md)

### <a name="sensitivity-labels-support-for-labeling-office-files-in-sharepoint-and-onedrive-preview"></a>Vertraulichkeits Bezeichnungen: Unterstützung für das bezeichnen von Office-Dateien in SharePoint und OneDrive (Vorschau)

Das Aktivieren der Vorschau ermöglicht Benutzern das Anwenden von Sensitivitäts Bezeichnungen in Office im Internet. Sie können die Schaltfläche " **Empfindlichkeit** " im Menüband und den angewendeten Beschriftungsnamen in der Statusleiste sehen. Wenn Sie Desktop-Apps verwenden, um Ihre Dateien auf SharePoint oder OneDrive zu beschriften und dann zu speichern, kann Microsoft 365 nun auch den Inhalt dieser Dateien verarbeiten, wenn auf der Bezeichnung Verschlüsselungseinstellungen angewendet wurden. Die gemeinsame Dokumenterstellung, eDiscovery, Verhinderung von Datenverlust, die Suche und andere kollaborative Features werden in diesen Fällen ebenfalls unterstützt.

[Informationen zum Aktivieren der Vorschau](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="february-2020"></a>Februar 2020

### <a name="insider-risk-management-is-officially-released"></a>Insider-Risikomanagement wird offiziell veröffentlicht

Trommelwirbel, bitte ...<br>Das Insider-Risikomanagement steht jetzt Organisationen mit den folgenden Abonnements zur Verfügung:

- [Microsoft 365 E5](https://go.microsoft.com/fwlink/?linkid=2120431) (bezahlt oder Testversion)
- Microsoft 365 Enterprise E3-Abonnement mit dem [Microsoft E5-Compliance-Add-On](https://go.microsoft.com/fwlink/?linkid=2120432)

Wir möchten Sie darüber informieren, dass wir seit der Vorschauversion einige Verbesserungen vorgenommen haben, darunter [neue Rollengruppen](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) und [lösungsweite Einstellungen](insider-risk-management-configure.md#step-4-configure-insider-risk-settings).

Wie immer, geben Sie bitte Feedback zur Lösung ab, damit wir weiterhin Verbesserungen vornehmen können.

### <a name="records-management"></a>Datensatzverwaltung

Diese neue Lösung bietet alle Funktionen für die Datensatzverwaltung unter einem Dach. Zu den Highlights gehören die Einführung der Datensatz-Versionsverwaltung für Microsoft Office SharePoint Online und OneDrive sowie der Nachweis über die Beseitigung von Datensätzen.

![Seite "Datensatzverwaltung" im Microsoft 365 Compliance Center](../media/mcc-records-management-page.png)

[Weitere Informationen zur Datensatzverwaltung](records-management.md)

### <a name="solution-spotlight-data-connectors-for-facebook-and-twitter"></a>Lösung im Blickpunkt: Datenconnectors für Facebook und Twitter

[Letzten Monat wurden Datenconnectors veröffentlicht](#just-launched), und wir erbitten Ihre Hilfe beim Testen der folgenden Connectors.

- [Facebook-Unternehmensseite](archive-facebook-data-with-sample-connector.md). Importiert und archiviert Daten von Facebook-Unternehmensseiten in Microsoft 365. Nutzbringend für Compliancelösungen wie Datensatzverwaltung und eDiscovery.
- [Twitter](archive-twitter-data-with-sample-connector.md). Importiert und archiviert Daten aus Twitter in Microsoft 365. Nutzbringend für Compliancelösungen wie Datensatzverwaltung und eDiscovery.

Wenn Sie diese Connectors einrichten und überprüfen, geben Sie uns bitte Feedback, was gut gelaufen ist, was nicht funktioniert hat und was wir tun können, um die Benutzerfreundlichkeit zu verbessern.

## <a name="january-2020"></a>Januar 2020

Die Wartezeit ist vorbei. Wir freuen uns, Ihnen mitzuteilen, dass das Microsoft 365 Compliance Center für alle Kunden mit Microsoft 365, Office 365, Enterprise Mobility + Security (EMS) und Windows 10 Enterprise-Plänen verfügbar ist. Alle Daten oder Richtlinien, die Sie im Security & Compliance Center verwaltet haben, stehen im Compliance Center zur Verfügung, daher müssen Sie nicht mehr hin-und herspringen.

Setzen Sie jetzt ein Lesezeichen, und wechseln Sie zu [https://compliance.microsoft.com](https://compliance.microsoft.com), um Ihre zentrale Anlaufstelle für die Verwaltung der Compliance in Ihrer gesamten Organisation zu besuchen..., oder [lesen Sie diesen Artikel](microsoft-365-compliance-center.md), um ein bisschen tiefer einzutauchen.

![Startseite des Microsoft 365 Compliance Centers](../media/mcc-home-ga.png)

In diesem Monat haben wir auch neue und aktualisierte Lösungen veröffentlicht. Hier erhalten Sie einen schnellen Blick auf die Highlights.

### <a name="now-in-preview"></a>Jetzt in der Vorschau

**Insider-Risikomanagement (Vorschau)**

Wir freuen uns, Ihnen mitteilen zu können, dass unsere Lösung zum Insider-Risikomanagement jetzt in der öffentlichen Vorschau angezeigt wird. Kurz gesagt, hilft das Insider-Risikomanagement Ihrer Organisation, Insider-Risiken intelligent zu erkennen und dagegen Maßnahmen zu ergreifen, indem es Folgendes bereitstellt:

- Anonymitäts-Steuerelemente zur Sicherstellung des Datenschutzes von Benutzern.
- intelligente Richtlinienvorlagen mit systemeigenen und Drittanbieter-Indikatoren, die Insiderbedrohungen wie Datenlecks erkennen.
- integrierte End-to-End-Untersuchungs-Workflows, die sich über die IT-, Personal- und Rechtsabteilung erstrecken.

Wir würden uns freuen, Ihre Meinung zu hören. Wenn Sie die Lösung verwenden, senden Sie uns Ihr Feedback, damit wir sicherstellen können, dass wir Ihre Anforderungen erfüllen, während wir uns in Richtung allgemeine Verfügbarkeit bewegen.

[Weitere Informationen zum Insider-Risikomanagement](insider-risk-management.md)

### <a name="just-launched"></a>Soeben eingeführt

**Kommunikationscompliance**

Beim Übergang von der Vorschauphase zur vollständigen Verfügbarkeit ist die Kommunikationscompliance ein wichtiger Bestandteil unseres neuen Lösungssatzes zum Insider-Risiko. Diese robuste Lösung trägt dazu bei, die Kommunikationsrisiken mithilfe von Workflows zu minimieren, um Nachrichten, die nicht den Standards Ihrer Organisation entsprechen, zu erkennen, zu untersuchen und um Abhilfemaßnahmen zu treffen.

Das Kundenfeedback während der Vorschau war fantastisch. Es führte zu mehreren Verbesserungen, darunter der Eindruck beim ersten Ausführen, um Ihnen den Einstieg zu erleichtern, Verbesserungen der Untersuchung und Abhilfemaßnahmen sowie vieles mehr.

[Weitere Informationen zur Kommunikationscompliance](communication-compliance.md)

![Seite "Kommunikationscompliance" im Microsoft 365 Compliance Center mit der ersten Karte der Willkommensseite](../media/mcc-communication-compliance-page-with-fre.png)

**Datenconnectors**

Früher haben Datenconnectors sich Speicherplatz mit anderen "Import"-Features im Office 365 Security & Compliance Center geteilt, nun verfügen sie über einen eigenen Bereich im Microsoft 365 Compliance Center. Verwenden Sie die neue Seite "Datenconnectors", um Daten aus den Dateien aus der Personalabteilung (HR) Ihrer Organisation und von verschiedenen Plattformen von Drittanbietern (z. B. Facebook, LinkedIn, Twitter und Instant Bloomberg) in Postfächer in Ihrer Microsoft 365-Organisation zu importieren und archivieren. Nach dem Importieren können diese Daten in mehreren Compliancelösungen verwaltet werden, darunter eDiscovery, Insider-Risikomanagement, Kommunikationscompliance, Überwachung, Aufbewahrungsrichtlinien und vieles mehr.

[Weitere Informationen zu Datenconnectors](archiving-third-party-data.md)

![Seite „Datenconnectors“ im Microsoft 365 Compliance Center](../media/mcc-data-connectors-page.png)

### <a name="noteworthy-updates"></a>Beachtenswerte Updates

**Neue Beurteilungsvorlagen für Compliancebewertung (Vorschau)**

Stets bemüht, Ihnen zu helfen, in der sich ständig weiterentwickelnden Compliancelandschaft voranzukommen, hat unser Team für Compliancebewertungen einen neuen Satz von Vorlagen bereitgestellt, um Ihnen dabei helfen, die Complianceausrichtung Ihrer Organisation in Hinblick auf die neuesten Bestimmungen zu bewerten und Anleitungen zur Implementierung effektiverer Steuerelemente zu erhalten. Sie können neue Vorlagen anzeigen für:

- ISO/IEC 27701:2019
- California Consumer Privacy Act (CCPA)
- das brasilianische allgemeine Datenschutzrecht (Lei Geral de Proteção de Dados – LGPD)
- SOC 1 Typ 2 und SOC 2 Typ 2

[Weitere Informationen zu Vorlagen für Compliancebewertungen](compliance-score.md#templates)