---
title: Neuerungen in Microsoft 365 Compliance
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: Ganz gleich, ob sie dem Compliance Center neue Lösungen hinzufügen, vorhandene Features basierend auf Ihrem Feedback aktualisieren oder eine neue und aktualisierte Dokumentation bereitstellen– Microsoft 365 hilft Ihnen, die sich ständig ändernde Compliance-Landschaft zu überblicken. Finden Sie heraus, was wir diesen Monat vorhaben.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1884989abba56a7da68a2a1372132015a81f5e03
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985012"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Neuerungen in Microsoft 365 Compliance

Ganz gleich, ob sie neue Lösungen zum [Microsoft 365 Compliance Center](microsoft-365-compliance-center.md)hinzufügen, vorhandene Features basierend auf Ihrem Feedback aktualisieren oder eine neue und aktualisierte Dokumentation bereitstellen– Microsoft 365 hilft Ihnen, die sich ständig ändernde Compliance-Landschaft zu überblicken. Sehen Sie sich die Neuerungen in Microsoft 365 Compliance an.

> [!NOTE]
> Einige Compliance-Features werden für unsere Kunden mit unterschiedlicher Geschwindigkeit eingeführt. Wenn Sie noch kein Feature sehen, versuchen Sie, sich selbst zu [Gezieltes Release](/office365/admin/manage/release-options-in-office-365) hinzuzufügen.

> [!TIP]
> Interessieren Sie sich dafür, was in anderen Admin Centers geschieht? Dann lesen Sie die folgenden Artikel:<br>[Neuerungen im Microsoft 365 Admin Center](/office365/admin/whats-new-in-preview)<br>[Aktive Websites im SharePoint Online Admin Center](/sharepoint/what-s-new-in-admin-center)<br>[Neuerungen in Microsoft 365 Defender](../security/defender/whats-new.md)<br><br>
Besuchen Sie die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap), um sich über Features von Microsoft 365 zu informieren, die eingeführt wurden, bereitgestellt werden, sich in der Entwicklung befinden, eingestellt oder zuvor veröffentlicht wurden.

## <a name="may-2021"></a>Mai 2021

### <a name="data-loss-prevention"></a>Verhinderung von Datenverlust

- Neue Anleitungen für die Planung Ihrer Strategie [zur Verhinderung von Datenverlust.](dlp-overview-plan-for-dlp.md)

### <a name="retention-and-records-management"></a>Aufbewahrung und Datensatzverwaltung

- Wenn Sie eine Aufbewahrungsrichtlinie von einem SharePoint Standort oder OneDrive Konto freigeben, müssen Sie die 30-tägige Nachfrist nicht mehr warten, bevor Sie die Website oder das Konto löschen können. Eine beliebte Anforderung von Kunden, diese Änderung ist jetzt für alle Mandanten abgeschlossen.
- In der Vorschau, **mehrstufige Löschungsprüfung:** Ein Administrator kann jetzt bis zu fünf aufeinander folgende Stufen der [Löschungsprüfung](disposition.md) für eine Aufbewahrungsbezeichnung hinzufügen, und Prüfer können andere Benutzer zu ihrer Löschungsprüfungsphase hinzufügen. Sie können auch die E-Mail-Benachrichtigungen und -Erinnerungen anpassen.

### <a name="sensitive-information-types"></a>Typen vertraulicher Informationen

- Neue Informationen hinzugefügt, die Ihnen beim [Ändern eines Schlüsselwortwörterbuchs](sit-modify-keyword-dictionary.md)helfen sollen.

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

- In der Vorschau ist jetzt eine neue Einstellung für **den Authentifizierungskontext** verfügbar, wenn Sie eine [Vertraulichkeitsbezeichnung für Gruppen und Websites]( sensitivity-labels-teams-groups-sites.md)konfigurieren. Diese Option funktioniert in Verbindung mit Azure AD-Richtlinien für bedingten Zugriff, um strengere Bedingungen zu erzwingen, wenn Benutzer auf SharePoint Websites zugreifen, auf die die Bezeichnung angewendet wurde. Lesen Sie die [Abhängigkeiten und Einschränkungen,](sensitivity-labels-teams-groups-sites.md#more-information-about-the-dependencies-for-the-authentication-context-option) bevor Sie diese Einstellung konfigurieren.
- Richtlinien für automatische [Bezeichnungen,](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) die nur für Exchange konfiguriert sind, unterstützen jetzt Vertraulichkeitsbezeichnungen, die Verschlüsselung anwenden, indem Benutzer Berechtigungen für die Optionen "Nicht weiterleiten" oder **"Encrypt-Only" zuweisen** dürfen.
- [Obligatorische Bezeichnungen](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) sind jetzt allgemein für alle Office-Apps auf allen Plattformen verfügbar.

## <a name="april-2021"></a>April 2021

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- [Grenzwerte in Advanced eDiscovery](/microsoft-365/compliance/limits-ediscovery20#export-limits---final-export-out-of-review-set). Organisationen können jetzt bis zu 5 Millionen Elemente oder 500 MB (je nachdem, was kleiner ist) in einem einzigen Export von Elementen aus einem Prüfdateisatz exportieren.

### <a name="data-classification"></a>Datenklassifikation

- [Bezeichnungsaktivitäten, die im Aktivitäten-Explorer verfügbar sind](/microsoft-365/compliance/data-classification-activity-explorer-available-events)

### <a name="data-connectors"></a>Datenconnectors

- [Einrichten eines Connectors zum Archivieren von Cisco Jabber auf Oracle-Daten](/microsoft-365/compliance/archive-ciscojabberonoracle-data)
- [Einrichten eines Connectors zum Archivieren von Cisco Jabber auf PostgreSQL-Daten](/microsoft-365/compliance/archive-ciscojabberonpostgresql-data)

### <a name="data-loss-prevention"></a>Verhinderung von Datenverlust

- Neues Thema für [Richtlinientipps zur Verhinderung von Datenverlust](/microsoft-365/compliance/dlp-policy-tips-reference).
- Neues Thema für [Informationen zur Verhinderung von Datenverlust.](/microsoft-365/compliance/dlp-learn-about-dlp)
- Neues Thema für [die ersten Schritte mit dem Warnungsdashboard zur Verhinderung von Datenverlust.](/microsoft-365/compliance/dlp-alerts-dashboard-get-started)

### <a name="retention-policies-and-retention-label-policies"></a>Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien

- Der Speicherort Microsoft 365 Gruppen unterstützt jetzt das Anwenden der Aufbewahrungseinstellungen auf nur Microsoft 365 Postfächer oder nur die verbundenen SharePoint Websites mithilfe des [PowerShell-Cmdlets "Set-RetentionCompliancePolicy"](/powershell/module/exchange/set-retentioncompliancepolicy) mit dem Parameter *"Applications".*

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Outlook Versionen und Updates:
- [Unterschiedliche Einstellungen für die Standardbezeichnung und die obligatorische Bezeichnung](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling) werden jetzt für integrierte Bezeichnungen unterstützt. Bisher wurden diese Einstellungen nur vom AIP-Client für einheitliche Bezeichnungen unterstützt.
- ["Nur verschlüsseln"](encryption-sensitivity-labels.md#let-users-assign-permissions) wird jetzt von macOS, iOS und Android unterstützt.
- [Die obligatorische Bezeichnung](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) wird auf den verbleibenden Plattformen eingeführt.
- [Dynamische Markierungen mit allen Variablen](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) werden auf allen Outlook Clients unterstützt.

## <a name="march-2021"></a>März 2021

Hier sind einige änderungen an Microsoft 365 Compliancelösungen und Inhalten für den Monat März.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- **Advanced eDiscovery Sammlungen** unterstützt jetzt das [neue Sammlungstool und den Workflow.](/microsoft-365/compliance/collections-overview) Weitere neue Themen sind [das Erstellen einer Entwurfssammlung,](/microsoft-365/compliance/create-draft-collection) [das Übernehmen eines Commits einer Entwurfssammlung in einen Prüfdateisatz](/microsoft-365/compliance/commit-draft-collection)sowie [Sammlungsstatistiken und -berichte.](/microsoft-365/compliance/collection-statistics-reports)
- **Exportieren Sie Dokumente** in einem Prüfdateisatz auf ein [Azure Storage](/microsoft-365/compliance/download-export-jobs) Konto.
- **Modul für prädiktive Codierung für Advanced eDiscovery**. Sehen Sie sich zunächst die neue Funktion für [die Vorhersagecodierung](/microsoft-365/compliance/predictive-coding-overview) an, die das veraltete Relevanzmodul ersetzt.

### <a name="data-classification"></a>Datenklassifizierung

- **Datenklassifizierungs-Explorer**. [Erste Schritte](/microsoft-365/compliance/data-classification-activity-explorer) mit dem Datenklassifizierungs-Explorer.

### <a name="data-connectors"></a>Datenconnectors

- **Private Schlüssel**. Unterstützung für private Schlüssel wurde zu [Bloomberg-Nachrichtendaten,](/microsoft-365/compliance/archive-bloomberg-message-data#set-up-a-connector-using-public-keys) [ICE Chat-Daten](/microsoft-365/compliance/archive-icechat-data#set-up-a-connector-using-public-keys) und [Instant Bloomberg-Datenconnectors](/microsoft-365/compliance/archive-instant-bloomberg-data#set-up-a-connector-using-public-keys) hinzugefügt.

### <a name="data-loss-prevention"></a>Verhinderung von Datenverlust

- **Microsoft Teams Unterstützung.** Die Unterstützung zur Verhinderung von Datenverlust wurde auf [Microsoft Teams](/microsoft-365/compliance/dlp-teams-default-policy)erweitert.
- **Microsoft Compliance-Erweiterung**. Erste Schritte mit der [Microsoft Compliance-Erweiterung.](/microsoft-365/compliance/dlp-chrome-get-started)

### <a name="encryption"></a>Verschlüsselung

- **Kundenschlüssel für Microsoft 365**. [Übersicht über den Kundenschlüssel](/microsoft-365/compliance/customer-key-tenant-level) für Microsoft 365 auf Mandantenebene (öffentliche Vorschau).
- **Verschlüsselung mit Doppelschlüssel**. Erfahren Sie mehr über [das Aktivieren der Unterstützung für mit Bezeichnungen versehene und geschützte Dokumente](/microsoft-365/compliance/double-key-encryption) in SharePoint und OneDrive for Business.

### <a name="insider-risk-management"></a>Insider-Risikomanagement

Die folgenden Insider-Risikomanagement-Funktionsupdates wurden im März für die öffentliche Vorschau veröffentlicht:

- Neues Analysefeature zum Identifizieren von Risiken vor dem Erstellen von Insider-Risikorichtlinien
- Unterstützung und Verwaltung der Erkennung neuer Risikoaktivitätssequenzen
- Neue kumulative Exfiltrationserkennungsunterstützung
- Neue In-App-Richtlinien-Integritätsberichterstellung und Empfehlungsunterstützung
- Neue Überwachungsprotokollfunktion und Berichterstellung
- Verbesserungen am Assistenten zum Erstellen von Richtlinien
- Aktualisierungen des Inhalts-Explorers
- Neuer Benutzerverwaltungsprozess/-support (Hinzufügen/Entfernen von Benutzern aus Richtlinien)
- Neue Unterstützung für die AAD-Integration (Unterstützung für abweichende Benutzerrichtlinien)
- Aktualisierte Domänenunterstützung in Richtlinien (REGEX)
- Verbesserungen und Verbesserungen an Richtlinienvorlagen

Die folgenden Themen wurden aktualisiert oder hinzugefügt, um diese neuen Features zu unterstützen:

- [Informationen zum Insider-Risikomanagement](/microsoft-365/compliance/insider-risk-management)
- [Planen des Insider-Risikomanagements](/microsoft-365/compliance/insider-risk-management-plan)
- [Erste Schritte mit Einstellungen für das Insider-Risikomanagement](/microsoft-365/compliance/insider-risk-management-settings)
- [Erste Schritte mit dem Insider-Risikomanagement](/microsoft-365/compliance/insider-risk-management-configure)
- [Erstellen und Verwalten von Insider-Risikorichtlinien](/microsoft-365/compliance/insider-risk-management-policies)
- [Untersuchen von Insider-Risikowarnungen](/microsoft-365/compliance/insider-risk-management-alerts)
- [Maßnahmen bei Insider-Risikofällen ergreifen](/microsoft-365/compliance/insider-risk-management-cases)
- [Überprüfen von Aktivitäten mit dem Insider-Risiko-Überwachungsprotokoll](/microsoft-365/compliance/insider-risk-management-audit-log)
- [Überprüfen von Daten mit dem Inhalts-Explorer für Insider-Risiken](/microsoft-365/compliance/insider-risk-management-content-explorer)
- [Verwalten des Workflows mit dem Benutzerdashboard](/microsoft-365/compliance/insider-risk-management-users)

### <a name="records-management"></a>Datensatzverwaltung

- **Verbesserungen am Dateiplan.** Eine Aktualisierung des [Dateiplans](file-plan-manager.md) entfernt oder verbessert die vorherigen Längeneinschränkungen für den Import.
- **Löschen Sie Aufbewahrungsbezeichnungen für Datensätze.** Eine Vorschauversion unterstützt die Möglichkeit, [Aufbewahrungsbezeichnungen](create-apply-retention-labels.md#deleting-retention-labels) zu löschen, die Elemente als Datensätze markieren.

### <a name="sensitive-information-types"></a>Typen vertraulicher Informationen

Inhalte wurden in den folgenden Themen hinzugefügt oder aktualisiert:

- [Erste Schritte mit benutzerdefiniertem vertraulichen Informationstyp](/microsoft-365/compliance/create-a-custom-sensitive-information-type)
- [Informationen zu Typen vertraulicher Informationen](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Erstellen von benutzerdefinierten vertraulichen Informationstypen mit genauer Datenübereinstimmungsklassifizierung](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Erstellen von Benachrichtigungen für genaue Datenübersprechungsaktivitäten](/microsoft-365/compliance/sit-edm-notifications-activities)
- [Entitätsdefinitionen für Typen vertraulicher Informationen](/microsoft-365/compliance/sensitive-information-type-entity-definitions)
- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps mithilfe von PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Erstellen eines Schlüsselwörterbuchs](/microsoft-365/compliance/create-a-keyword-dictionary)

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

- **DoD-Unterstützung.** Unterstützung für Mandanten von US-Behörden mit DoD-Umgebungen.
- **Nur verschlüsseln für Outlook**. Verschlüsselungsoptionen für Outlook umfassen jetzt Encrypt-Only, wenn Sie ["Benutzer Berechtigungen zuweisen lassen"](encryption-sensitivity-labels.md#let-users-assign-permissions)auswählen.
- **Erzwingen integrierter Bezeichnungen in Office-Apps.** Aktualisierte [Anleitungen](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client) zum Erzwingen integrierter Bezeichnungen in Office-Apps, wenn Sie den Azure Information Protection-Client für einheitliche Bezeichnungen installiert haben.

## <a name="february-2021"></a>Februar 2021

Hier sind einige änderungen an Microsoft 365 Compliance-Lösungen und Inhalten für den Monat Februar.

### <a name="auditing"></a>Überwachung

- **Verwalten von Aufbewahrungsrichtlinien für Überwachungsprotokolle.** Erfahren Sie mehr über das neue Dashboard für [Überwachungsaufbewahrungsrichtlinien.](/microsoft-365/compliance/audit-log-retention-policies#manage-audit-log-retention-policies-1)
- **Durchsuchen Sie das Überwachungsprotokoll.** [Verwenden Sie das PowerShell-Skript, um das Überwachungsprotokoll zu durchsuchen.](/microsoft-365/compliance/audit-log-search-script)

### <a name="data-classification-content-explorer"></a>Datenklassifizierungs-Inhalts-Explorer

Inhalte wurden in den folgenden Themen hinzugefügt oder aktualisiert:

- [Erste Schritte mit dem Inhalts-Explorer](/microsoft-365/compliance/data-classification-content-explorer)
- [Veröffentlichungshinweise zur Datenklassifizierung](/microsoft-365/compliance/data-classification-pub-preview-relnotes)

### <a name="data-loss-prevention"></a>Verhinderung von Datenverlust

Inhalte wurden in den folgenden Themen hinzugefügt oder aktualisiert:

- [Informationen zu Endpunkt-DLP](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Senden von E-Mail-Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien](/microsoft-365/compliance/use-notifications-and-policy-tips)
- [Erfahren Sie mehr über den lokalen Microsoft 365-Scanner zur Verhinderung von Datenverlust](/microsoft-365/compliance/dlp-on-premises-scanner-learn)
- [Erste Schritte mit dem lokalen Scanner zur Verhinderung von Datenverlust](/microsoft-365/compliance/dlp-on-premises-scanner-get-started)
- [Erstellen einer DLP-Richtlinie zum Schützen von Dokumenten mit FCI- oder anderen Eigenschaften](/microsoft-365/compliance/protect-documents-that-have-fci-or-other-properties)
- [Nutzen der Verhinderung von Datenverlust am Endpunkt](/microsoft-365/compliance/endpoint-dlp-using)
- [Endpunkt-DLP – Erste Schritte](/microsoft-365/compliance/endpoint-dlp-getting-started)

### <a name="ediscovery"></a>eDiscovery

Inhalte wurden in den folgenden Themen hinzugefügt oder aktualisiert:

- [Entschlüsselung in Microsoft 365 eDiscovery-Tools](/microsoft-365/compliance/ediscovery-decryption)
- [Stichwortabfragen und Suchbedingungen](/microsoft-365/compliance/keyword-queries-and-search-conditions#limitations-for-searching-sensitive-data-types)
- [Einstellung des Relevanzmoduls in Advanced eDiscovery](/microsoft-365/compliance/relevance-module-retirement)
- [Verwenden eines Skripts zum Hinzufügen von Benutzern zu einem Haltebereich in einem Core eDiscovery-Fall](/microsoft-365/compliance/use-a-script-to-add-users-to-a-hold-in-ediscovery)

### <a name="encryption"></a>Verschlüsselung

Inhalte wurden in den folgenden Themen hinzugefügt oder aktualisiert:

#### <a name="azure-rights-management-service-rms"></a>Azure Rights Management Service (RMS)

- [Vom Kunden verwaltete Verschlüsselungsfunktionen](/microsoft-365/compliance/office-365-customer-managed-encryption-features)
- [Exchange Online-E-Mail-Verschlüsselung mit AD RMS.](/microsoft-365/compliance/information-rights-management-in-exchange-online) Der Support für diesen Dienst ist veraltet. Sie können AD RMS in einer Exchange-Hybridumgebung nicht mehr verwenden. Migrieren Sie stattdessen zu Azure RMS.

#### <a name="customer-key"></a>Kundenschlüssel

- [Kundenschlüssel für Microsoft 365 auf Mandantenebene](/microsoft-365/compliance/customer-key-tenant-level)
- [Übersicht über Sicherheit und Compliance](/microsoftteams/security-compliance-overview)

#### <a name="information-rights-management-irm"></a>Verwaltung von Informationsrechten (Information Rights Management, IRM)

- [Wenden Sie die Verwaltung von Informationsrechten (Information Rights Management, IRM) auf eine Liste oder Bibliothek an.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Diese nationalen Clouds unterstützen diese Einstellung nicht:
    - Microsoft Cloud for US Government
    - Microsoft Cloud Deutschland
    - Azure und Microsoft 365, betrieben von 21Vianet in China)
- [Konfigurieren Sie IRM für die Verwendung eines lokalen AD RMS-Servers.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Die Unterstützung für diesen Dienst in einer Exchange-Hybridumgebung ist veraltet.

### <a name="sensitive-information-types"></a>Typen vertraulicher Informationen

Inhalte wurden in den folgenden Themen hinzugefügt oder aktualisiert:

- [Informationen zu Typen vertraulicher Informationen](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps mit PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Erstellen einer benutzerdefinierten Typen vertraulicher Informationen mit genauer Datenübereinstimmungsklassifizierung](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Entitätsdefinitionen für Typen vertraulicher Informationen](/microsoft-365/compliance/sensitive-information-type-entity-definitions)


### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Inhalte wurden in den folgenden Themen hinzugefügt oder aktualisiert:

- **Externe SharePoint-Freigabe**. Für [Containerbeschriftungen](sensitivity-labels-teams-groups-sites.md) wird die Option für die externe Freigabe von SharePoint-Websites jetzt als allgemein verfügbar veröffentlicht. Darüber hinaus unterstützen das Microsoft 365 Admin Center und Planner jetzt die Anwendung dieser Vertraulichkeitsbezeichnungen. 
- **Gemeinsame Dokumenterstellung und automatisches Speichern.** Unterstützung für [die gemeinsame Dokumenterstellung und das automatische Speichern](sensitivity-labels-coauthoring.md) für verschlüsselte Dateien wird als Vorschau für Tests in Nicht-Produktionsmandanten veröffentlicht.

## <a name="january-2021"></a>Januar 2021

### <a name="support-for-card-content-in-teams"></a>Unterstützung für Karteninhalte in Teams

Die folgenden Microsoft 365 Compliance-Lösungen unterstützen jetzt die Erkennung von [Karteninhalten,](/microsoftteams/platform/task-modules-and-cards/what-are-cards) die über Apps in Teams-Nachrichten generiert werden:

- **Core und Advanced eDiscovery**. Karteninhalte können jetzt in [den Haltebereich gesetzt](create-ediscovery-holds.md#preserve-card-content) oder in [Suchvorgänge](/microsoftteams/ediscovery-investigation#search-for-card-content) einbezogen werden (gilt auch für die Inhaltssuche).
- **Überwachen**. Kartenaktivität wird nun [im Überwachungsprotokoll aufgezeichnet.](/microsoftteams/audit-log-events#teams-activities)
- **Aufbewahrungsrichtlinien**. Kann jetzt Aufbewahrungsrichtlinien verwenden, um [Karteninhalte aufzubewahren und](retention-policies-teams.md#whats-included-for-retention-and-deletion)zu löschen.

### <a name="information-governance-and-records-management"></a>Informationsgovernance und Datensatzverwaltung

[Neue Bewertung](retention-regulatory-requirements.md#new-zealand-public-records-act) zur Behandlung der Verwendung von Informationsgovernance und Datensatzverwaltung zur Erfüllung von Compliance-Verpflichtungen für das New Zealand Public Records Act.

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

- Vertraulichkeitsbezeichnungen werden jetzt für Mandanten der US-Regierung (GCC und GCC-H) unterstützt.
- Neue [automatische Bezeichnungsunterstützung](sensitivity-labels-office-apps.md) für macOS.

## <a name="december-2020"></a>Dezember 2020

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>Spotlight: Neue Inhalte für Insider-Risikolösungen

Das Microsoft 365 Compliance-Inhaltsteam arbeitet hart daran, "Inhaltslösungs"-Dokumente zu erstellen, um zu fördern, wie Compliance-Funktionen gemeinsam verwendet werden können, um Ihre Complianceziele zu erreichen.

Zunächst sind Inhalte, die unsere Insider-Risikolösungen miteinander verbindet: Kommunikationscompliance, Insider-Risikomanagement, Informationsbarrieren und privilegiertes Zugriffsmanagement. Hier sehen Sie einen Blick darauf, was Sie finden:

- [Neue Angebotsseite für Insider-Risikolösungen.](insider-risk-solution-overview.md) Enthält Details zu Risiken, die die Lösungen mindern können, Lizenzierungsanforderungen, Bereitstellungssequenz, Architekturillustrationen, Schulungsressourcen und vieles mehr.
- Neue Übersichtsartikel für jede Insider-Risikolösung. Anleitungen und Links zu Artikeln, die Ihnen helfen, jede Lösung zu erfahren, zu planen, bereitzustellen und zu verwalten:
  - [Kommunikationscompliance](communication-compliance-solution-overview.md)
  - [Insider-Risikomanagement](insider-risk-management-solution-overview.md)
  - [Informationsbarrieren](information-barriers-solution-overview.md)
  - [Privileged Access Management](privileged-access-management-solution-overview.md)
  
Weitere Dokumentationen zu Inhaltslösungen werden in Kürze verfügbar sein!

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

Verbesserte Workflows und Funktionen zum [Hinzufügen von Verwahrern](add-custodians-to-case.md) und [Nicht-Verwahrer-Datenquellen](non-custodial-data-sources.md) zu einem Advanced eDiscovery Fall.

### <a name="data-connectors"></a>Datenconnectors

[Vier neue Connectors wurden veröffentlicht:](archiving-third-party-data.md#third-party-data-connectors)Redtail Speak, Salesforce Chatter, ServiceNow und Yieldbroker.

### <a name="encryption"></a>Verschlüsselung

Einführung in [den Kundenschlüssel für Microsoft 365 auf Mandantenebene.](customer-key-tenant-level.md) Mithilfe der von Ihnen bereitgestellten Schlüssel können Sie eine Datenverschlüsselungsrichtlinie (Data Encryption Policy, DEP) erstellen und dem Mandanten zuweisen. Die Datenverschlüsselungsrichtlinie (DEP) verschlüsselt Daten für diese Workloads mandantenübergreifend:

- Teams Chatnachrichten (1:1-Chats, Gruppenchats, Besprechungschats und Kanalunterhaltungen)
- Teams Mediennachrichten (Bilder, Codeausschnitte, Videos, Wiki-Bilder)
- Teams in Teams Speicher gespeicherte Anruf- und Besprechungsaufzeichnungen
- Teams Chatbenachrichtigungen
- Teams von Chatvorschlägen nach Cortana
- Teams Statusmeldungen
- Benutzer- und Signalinformationen für Exchange Online

### <a name="records-management"></a>Datensatzverwaltung

Die [Rollengruppe "Datensatzverwaltungsadministrator"](get-started-with-records-management.md#permissions-required-for-records-management) gewährt jetzt Berechtigungen für alle Datensatzverwaltungsfunktionen, einschließlich der Löschungsprüfung.

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

- [Automatisches Bezeichnen von Daten in Azure Purview (Vorschau)](/azure/purview/create-sensitivity-label). Sie können jetzt Vertraulichkeitsbezeichnungen erstellen und automatisch auf Ressourcen in Azure Purview anwenden, z. B. Dateien in Azure Blob Storage und Datenbankspalten in SQL Server.
- [Benutzer müssen eine Bezeichnung auf Elemente anwenden.](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) Diese neue Option wird auch als "obligatorische Bezeichnung" bezeichnet und erfordert, dass Benutzer in den spezifischen Szenarien eine Vertraulichkeitsbezeichnung auswählen und anwenden.
