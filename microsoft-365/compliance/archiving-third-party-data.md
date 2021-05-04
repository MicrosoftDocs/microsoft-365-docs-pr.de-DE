---
title: Archivieren von Drittanbieterdaten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Daten von Drittanbietern von Plattformen für soziale Medien, Chatplattformen und Plattformen für die Dokumentzusammenarbeit in Microsoft 365 importieren.
ms.openlocfilehash: 22a2e6dbadc3c259896348fc89754882db85cfb4
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764110"
---
# <a name="archive-third-party-data"></a>Archivieren von Drittanbieterdaten

Microsoft 365 können Administratoren Datenconnectors verwenden, um Daten von Drittanbietern von Plattformen für soziale Medien, Chatplattformen und Plattformen für die Dokumentzusammenarbeit in Postfächer in Ihrer Organisation Microsoft 365 archivieren. Ein Hauptvorteil der Verwendung von Datenconnectors zum Importieren und Archivieren von Drittanbieterdaten in Microsoft 365 besteht in der Anwendung verschiedener Microsoft 365-Compliancelösungen auf diese, nachdem sie importiert wurden. Auf diese Weise stellen Sie sicher, dass die Nicht-Microsoft-Daten Ihrer Organisation den Vorschriften und Standards entsprechen, die sich auf Ihre Organisation auswirken.

## <a name="third-party-data-connectors"></a>Daten-Connectoren von Drittanbietern

In der folgenden Tabelle sind die Datenconnectors von Drittanbietern aufgeführt, die im Microsoft 365 Compliance Center verfügbar sind. In der Tabelle werden auch die Compliancelösungen zusammengefasst, die Sie auf Drittanbieterdaten anwenden können, nachdem Sie daten importiert und Microsoft 365. Im nächsten [Abschnitt finden](#overview-of-compliance-solutions-that-support-third-party-data) Sie eine ausführlichere Beschreibung der einzelnen Compliancelösungen und deren Vorteile für Drittanbieterdaten.

> [!TIP]
> Klicken Sie auf  den Link in der Datenspalte Drittanbieter, um die schrittweisen Anweisungen zum Erstellen eines Connectors für diesen Datentyp zu erhalten.

|Drittanbieterdaten  |Prozesssicherungsverfahren|eDiscovery  |Aufbewahrungseinstellungen  |Datensatzverwaltung  |Kommunikationscompliance  |Insider-Risikomanagement  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[AT&T Network <sup>1</sup>](archive-att-network-archiver-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Bell Network <sup>1</sup>](archive-bell-network-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Bloomberg Message](archive-bloomberg-message-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[CellTrust <sup>2</sup>](archive-celltrust-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Cisco Jabber auf MS SQL <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Cisco Jabber auf Oracle <sup>2</sup>](archive-ciscojabberonoracle-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Cisco Jabber auf PostgreSQL <sup>2</sup>](archive-ciscojabberonpostgresql-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Enterprise Zahl <sup>1</sup>](archive-enterprise-number-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[FX Verbinden <sup>2</sup>](archive-fxconnect-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Personalwesen (HR)](import-hr-data.md) ||||||![Häkchen](../media/checkmark.png)
|[ICE Chat](archive-icechat-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[MS SQL-Datenbank <sup>2</sup>](archive-mssqldatabaseimporter-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[O2 Network <sup>1</sup>](archive-o2-network-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Physisches Badging](import-physical-badging-data.md) ||||||![Häkchen](../media/checkmark.png)|
|[Pivot <sup>2</sup>](archive-pivot-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Redtail Speak <sup>2</sup>](archive-redtailspeak-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Reuters Dealing <sup>2</sup>](archive-reutersdealing-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Reuters Eikon <sup>2</sup>](archive-reuterseikon-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Reuters FX <sup>2</sup>](archive-reutersfx-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Salesforce Chatter <sup>2</sup>](archive-salesforcechatter-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[ServiceNow <sup>2</sup>](archive-servicenow-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Slack eDiscovery <sup>2</sup>](archive-slack-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[<sup>Symphonie 2</sup>](archive-symphony-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[TELUS Network <sup>1</sup>](archive-telus-network-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Texttrennzeichen <sup>2</sup>](archive-text-delimited-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Verizon Network <sup>1</sup>](archive-verizon-network-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Webex Teams <sup>2</sup>](archive-webexteams-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Webseiten <sup>2</sup>](archive-webpagecapture-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Workplace von Facebook <sup>2</sup>](archive-workplacefromfacebook-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Yieldbroker <sup>2</sup>](archive-yieldbroker-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Zoomen von <sup>Besprechungen 2</sup>](archive-zoommeetings-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
||||||||

> [!NOTE]
> <sup>1</sup> Von TeleMessage bereitgestellter Datenconnector. Bevor Sie Daten in Microsoft 365 archivieren können, müssen Sie mit TeleMessage zusammenarbeiten, um den Archivierungsdienst für Ihre Organisation einrichten zu können. Weitere Informationen finden Sie im Abschnitt Voraussetzungen in den schrittweisen Anweisungen für diesen Datentyp.<br/><br/><sup>2</sup> Datenconnector, der von "Veritas" bereitgestellt wird. Bevor Sie Daten in Microsoft 365 archivieren können, müssen Sie mit Demeni zusammenarbeiten, um den Archivierungsdienst für Ihre Organisation einrichten zu können. Weitere Informationen finden Sie im Abschnitt Voraussetzungen in den schrittweisen Anweisungen für diesen Datentyp.

Die in der vorherigen Tabelle aufgeführten Drittanbieterdaten (mit Ausnahme von Hr-Daten und physischen Daten zur Verletzung) werden in Benutzerpostfächer importiert. Die entsprechenden Compliancelösungen, die Drittanbieterdaten unterstützen, werden auf das Benutzerpostfach angewendet, in dem die Daten gespeichert werden.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Übersicht über Compliancelösungen, die Drittanbieterdaten unterstützen

In den folgenden Abschnitten werden einige dinge beschrieben, die Microsoft 365 Compliancelösungen Ihnen bei der Verwaltung der in der vorherigen Tabelle aufgeführten Drittanbieterdaten helfen können.

### <a name="litigation-hold"></a>Prozesssicherungsverfahren

Sie setzen ein [Verfahrensverfahren für](create-a-litigation-hold.md) ein Benutzerpostfach ein, um Daten von Drittanbietern zu speichern. Wenn Sie einen Haltezustand erstellen, können Sie eine Haltedauer (auch als zeitbasierter Haltezustand *bezeichnet)* angeben, sodass gelöschte und geänderte Drittanbieterdaten für einen bestimmten Zeitraum aufbewahrt und dann endgültig aus dem Postfach gelöscht werden. Oder Sie können Inhalte einfach auf unbestimmte Zeit beibehalten (als *unendliches* Halterecht bezeichnet) oder bis das Verfahrensverfahren aufgehoben wurde.

### <a name="ediscovery"></a>eDiscovery

Die drei primären eDiscovery-Tools in Microsoft 365 sind Inhaltssuche, Core eDiscovery und Advanced eDiscovery.

- **[Inhaltssuche](content-search.md).** Sie können das Inhaltssuchtool verwenden, um Postfächer nach importierten Drittanbieterdaten zu durchsuchen. Sie können Suchabfragen und -bedingungen verwenden, um Ihre Suchergebnisse zu einenten und die Suchergebnisse zu exportieren.

- **[Core eDiscovery](get-started-core-ediscovery.md).** Dieses Tool baut auf den grundlegenden Such- und Exportfunktionen auf, indem Sie Fälle erstellen können, mit denen Sie steuern können, wer auf Falldaten zugreifen kann, benutzerpostfächern oder Postfachinhalten, die den Suchkriterien entsprechen, einen Halteschutz setzen können. Dies bedeutet, dass Sie eDiscovery-Daten, die in Benutzerpostfächer importiert wurden, in einem eDiscovery-Archiv speichern können.

- **[Advanced eDiscovery](overview-ediscovery-20.md).** Mit diesem leistungsstarken Tool wird die Fallfunktionalität von Core eDiscovery erweitert, indem Sie einem Fall Custodians hinzufügen, die Daten des Custodians in der Warteschleife platzieren und dann die Drittanbieterdaten eines Verwahrers in eine Überprüfung laden, um weitere Analysen wie Designs und Duplikaterkennung durchzuführen. Nachdem Sie Daten von Drittanbietern in einen Überprüfungssatz geladen haben, können Sie diese abfragen und in ein schmales Ergebnisset filtern.

   Sowohl core eDiscovery als auch Advanced eDiscovery können Sie Daten von Drittanbietern verwalten, die für die rechtlichen oder internen Untersuchungen Ihrer Organisation relevant sein können.

### <a name="retention-settings"></a>Aufbewahrungseinstellungen

Sie können eine [Aufbewahrungsrichtlinie](retention.md) auf Benutzerpostfächer anwenden, um Daten von Drittanbietern (und andere Postfachinhalte) nach Ablauf des Aufbewahrungszeitraums zu speichern und zu löschen. Sie können aufbewahrungsrichtlinien auch verwenden, um Drittanbieterdaten [](disposition.md) eines bestimmten Alters zu löschen oder Aufbewahrungsbezeichnungen zu verwenden, um eine Dispositionsüberprüfung auszulösen, wenn der Aufbewahrungszeitraum für Drittanbieterdaten abläuft.

### <a name="records-management"></a>Datensatzverwaltung

Mit [dem Datensatzverwaltungsfeature](records-management.md) in Microsoft 365 Können Sie Drittanbieterdaten als Datensatz deklarieren. Dies kann manuell von Benutzern erfolgen, die eine Aufbewahrungsbezeichnung anwenden, die Daten von Drittanbietern in ihrem Postfach als Datensatz kennzeichnet. Oder Sie können Aufbewahrungsbezeichnungen automatisch anwenden, indem Sie vertrauliche Informationen, Schlüsselwörter oder Inhaltstypen in Drittanbieterdaten identifizieren.

### <a name="communication-compliance"></a>Kommunikationscompliance

Mithilfe der [Kommunikationskonformität](communication-compliance.md) können Sie Daten von Drittanbietern untersuchen, um sicherzustellen, dass sie mit den Datenstandards Ihrer Organisation kompatibel sind. Sie können dies tun, indem Sie Korrekturaktionen für unangemessene Nachrichten in Ihrer Organisation erkennen, erfassen und durchführen. Sie können z. B. die Daten von Drittanbietern überwachen, die Sie für anstößige Sprache, vertrauliche Informationen und die Einhaltung gesetzlicher Vorschriften importieren.

### <a name="insider-risk-management"></a>Insider-Risikomanagement

Signale von Drittanbieterdaten, z. B. selektive [](insider-risk-management.md) Personaldaten, können von der Insider-Risikomanagementlösung verwendet werden, um interne Risiken zu minimieren, indem Sie riskante Aktivitäten in Ihrer Organisation erkennen, untersuchen und darauf reagieren können. Daten, die vom Personaldatenconnector importiert werden, werden beispielsweise als Risikoindikatoren verwendet, um den Diebstahl von Ausgehenden Mitarbeiterdaten zu erkennen.

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Arbeiten mit einem Microsoft-Partner zum Archivieren von Drittanbieterdaten

Eine weitere Möglichkeit zum Importieren und Archivieren von Drittanbieterdaten besteht in der Zusammenarbeit Ihrer Organisation mit einem Microsoft-Partner. Wenn ein Drittanbieterdatentyp von den im Microsoft Compliance Center verfügbaren Datenconnectors nicht unterstützt wird, können Sie mit einem Partner zusammenarbeiten, der einen benutzerdefinierten Connector bereitstellen kann, der so konfiguriert wird, dass Elemente regelmäßig aus der Datenquelle eines Drittanbieters extrahiert werden, und anschließend eine Verbindung mit der Microsoft Cloud über eine Drittanbieter-API hergestellt wird, und diese Elemente in Microsoft 365 importieren. Der Partnerconnector konvertiert auch den Inhalt eines Elements aus der Datenquelle eines Drittanbieters in eine E-Mail-Nachricht und importiert es dann in ein Postfach in Microsoft 365.

Eine Liste der Partner, mit der Sie zusammenarbeiten können, und den schrittweisen Prozess für diese Methode finden Sie unter Arbeiten mit einem Partner zum Archivieren von Drittanbieterdaten [in Microsoft 365](work-with-partner-to-archive-third-party-data.md).
