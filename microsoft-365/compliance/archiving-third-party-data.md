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
description: Erfahren Sie, wie Sie Daten von Drittanbietern von Social Media-Plattformen, Chatplattformen und Plattformen für die Zusammenarbeit bei Dokumenten in Microsoft 365 Postfächer importieren.
ms.openlocfilehash: 5e1eab67019184e337b7e5404bf96bdf26d0446d
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53061728"
---
# <a name="archive-third-party-data"></a>Archivieren von Drittanbieterdaten

mit Microsoft 365 können Administratoren Datenkonnektoren verwenden, um Daten von Drittanbietern von Social Media-Plattformen, Chatplattformen und Plattformen für die Zusammenarbeit an Dokumenten in Postfächern in Ihrer Microsoft 365 Organisation zu importieren und zu archivieren. Ein Hauptvorteil der Verwendung von Datenconnectors zum Importieren und Archivieren von Drittanbieterdaten in Microsoft 365 besteht darin, dass Sie nach dem Import verschiedene Microsoft 365 Compliancelösungen darauf anwenden können. Auf diese Weise können Sie sicherstellen, dass die Nicht-Microsoft-Daten Ihrer Organisation den Vorschriften und Standards entsprechen, die sich auf Ihre Organisation auswirken.

## <a name="third-party-data-connectors"></a>Daten-Connectoren von Drittanbietern

In der folgenden Tabelle sind die datenkonnektoren von Drittanbietern aufgeführt, die im Microsoft 365 Compliance Center verfügbar sind. In der Tabelle sind auch die Compliancelösungen zusammengefasst, die Sie nach dem Importieren und Archivieren in Microsoft 365 auf Daten von Drittanbietern anwenden können. Im [nächsten Abschnitt](#overview-of-compliance-solutions-that-support-third-party-data) finden Sie eine detailliertere Beschreibung der einzelnen Compliance-Lösungen und wie sie von Drittanbieterdaten profitieren kann.

> [!TIP]
> Klicken Sie auf den Link in der **Datenspalte** des Drittanbieters, um die schrittweisen Anweisungen zum Erstellen eines Connectors für diesen Datentyp zu erhalten.

|Drittanbieterdaten  |Beweissicherungsverfahren|eDiscovery  |Aufbewahrungseinstellungen  |Datensatzverwaltung  |Kommunikationscompliance  |Insider-Risikomanagement  |
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
|[Physisches Ausweichen](import-physical-badging-data.md) ||||||![Häkchen](../media/checkmark.png)|
|[Pivot <sup>2</sup>](archive-pivot-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Redtail Speak <sup>2</sup>](archive-redtailspeak-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Reuters Dealing <sup>2</sup>](archive-reutersdealing-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Reuters E cod <sup>2</sup>](archive-reuterseikon-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Reuters FX <sup>2</sup>](archive-reutersfx-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Salesforce Chatter <sup>2</sup>](archive-salesforcechatter-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[ServiceNow <sup>2</sup>](archive-servicenow-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Signal <sup>1</sup>](archive-signal-archiver-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Skype for Business <sup>2</sup>](archive-skypeforbusiness-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Slack eDiscovery <sup>2</sup>](archive-slack-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Orchestra <sup>2</sup>](archive-symphony-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Kanal <sup>1</sup>](archive-telegram-archiver-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[TELUS Network <sup>1</sup>](archive-telus-network-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Text getrennt <sup>2</sup>](archive-text-delimited-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Verizon Network <sup>1</sup>](archive-verizon-network-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Webex Teams <sup>2</sup>](archive-webexteams-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Webseiten <sup>2</sup>](archive-webpagecapture-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[WeChat <sup>1</sup>](archive-wechat-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Workplace von Facebook <sup>2</sup>](archive-workplacefromfacebook-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Yieldbroker <sup>2</sup>](archive-yieldbroker-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Zoomen von Besprechungen <sup>2</sup>](archive-zoommeetings-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
||||||||

> [!NOTE]
> <sup>1</sup> Von TeleMessage bereitgestellter Datenkonnektor. Bevor Sie Daten in Microsoft 365 archivieren können, müssen Sie mit TeleMessage zusammenarbeiten, um deren Archivierungsdienst für Ihre Organisation einzurichten. Weitere Informationen finden Sie im Abschnitt "Voraussetzungen" in den schrittweisen Anweisungen für diesen Datentyp. TeleMessage-Datenconnectors sind auch in GCC Umgebungen in der Microsoft 365 US Government-Cloud verfügbar. Weitere Informationen finden Sie im Abschnitt ["Datenkonnektoren" im Abschnitt "US Government Cloud"](#data-connectors-in-the-us-government-cloud) in diesem Artikel. <br/><br/><sup>2</sup> Datenkonnektor, der von Dere bereitgestellt wird. Bevor Sie Daten in Microsoft 365 archivieren können, müssen Sie mit Csv zusammenarbeiten, um deren Archivierungsdienst für Ihre Organisation einzurichten. Weitere Informationen finden Sie im Abschnitt "Voraussetzungen" in den schrittweisen Anweisungen für diesen Datentyp.

Die in der vorherigen Tabelle aufgeführten Drittanbieterdaten (mit Ausnahme von PERSONAL-Daten und physischen Daten für Fehlerhafte) werden in Benutzerpostfächer importiert. Die entsprechenden Compliancelösungen, die Drittanbieterdaten unterstützen, werden auf das Benutzerpostfach angewendet, in dem die Daten gespeichert sind.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Übersicht über Compliancelösungen, die Drittanbieterdaten unterstützen

In den folgenden Abschnitten werden einige der Dinge beschrieben, die die Microsoft 365 Compliancelösungen Ihnen bei der Verwaltung der in der vorherigen Tabelle aufgeführten Drittanbieterdaten helfen können.

### <a name="litigation-hold"></a>Beweissicherungsverfahren

Sie legen ein [Beweissicherungsverfahren](create-a-litigation-hold.md) für ein Benutzerpostfach fest, um Daten von Drittanbietern aufzubewahren. Wenn Sie eine Aufbewahrung erstellen, können Sie eine Aufbewahrungsdauer (auch als *zeitbasierte* Aufbewahrung bezeichnet) angeben, damit gelöschte und geänderte Daten von Drittanbietern für einen bestimmten Zeitraum aufbewahrt und dann endgültig aus dem Postfach gelöscht werden. Oder Sie können Inhalte auf unbestimmte Zeit aufbewahren (als *unendliche Aufbewahrung)* oder bis das Beweissicherungsverfahren entfernt wird.

### <a name="ediscovery"></a>eDiscovery

Die drei wichtigsten eDiscovery-Tools in Microsoft 365 sind Inhaltssuche, Core eDiscovery und Advanced eDiscovery.

- **[Inhaltssuche](content-search.md).** Sie können das Tool für die Inhaltssuche verwenden, um Postfächer nach Daten von Drittanbietern zu durchsuchen, die Sie importiert haben. Sie können Suchabfragen und -bedingungen verwenden, um Ihre Suchergebnisse einzugrenzen und die Suchergebnisse zu exportieren.

- **[Core eDiscovery](get-started-core-ediscovery.md).** Dieses Tool baut auf der grundlegenden Such- und Exportfunktionalität auf, indem es Ihnen ermöglicht, Fälle zu erstellen, mit denen Sie steuern können, wer auf Falldaten zugreifen, Benutzerpostfächer oder Postfachinhalte sperren kann, die suchkriterien entsprechen. Das bedeutet, dass Sie eine eDiscovery-Aufbewahrung für die Daten von Drittanbietern festlegen können, die in Benutzerpostfächer importiert wurden.

- **[Advanced eDiscovery](overview-ediscovery-20.md).** Dieses leistungsstarke Tool erweitert die Fallfunktionalität von Core eDiscovery, indem Sie einem Fall Verwahrer hinzufügen, die Daten des Verwalters in die Sperre setzen und dann die Daten eines Verwahrers in eine Überprüfung laden, um weitere Analysen wie Designs und die Erkennung von Duplikaten durchzuführen. Nachdem Sie Daten von Drittanbietern in einen Prüfdateisatz geladen haben, können Sie sie abfragen und in ein schmales Resultset filtern.

   Sowohl Mit Core eDiscovery als auch Advanced eDiscovery können Sie Daten von Drittanbietern verwalten, die für die rechtlichen oder internen Untersuchungen Ihrer Organisation relevant sein können.

### <a name="retention-settings"></a>Aufbewahrungseinstellungen

Sie können eine [Aufbewahrungsrichtlinie](retention.md) auf Benutzerpostfächer anwenden, um Daten von Drittanbietern (und andere Postfachinhalte) nach Ablauf des Aufbewahrungszeitraums aufzubewahren und zu löschen. Sie können Aufbewahrungsrichtlinien auch verwenden, um Daten von Drittanbietern eines bestimmten Alters zu löschen, oder [Aufbewahrungsbezeichnungen verwenden, um eine Löschungsprüfung auszulösen,](disposition.md) wenn der Aufbewahrungszeitraum für Daten von Drittanbietern abläuft.

### <a name="records-management"></a>Datensatzverwaltung

Mit dem [Datensatzverwaltungsfeature](records-management.md) in Microsoft 365 können Sie Drittanbieterdaten als Datensatz deklarieren. Dies kann manuell von Benutzern durchgeführt werden, die eine Aufbewahrungsbezeichnung anwenden, die Daten von Drittanbietern in ihrem Postfach als Datensatz kennzeichnet. Oder Sie können Aufbewahrungsbezeichnungen automatisch anwenden, indem Sie vertrauliche Informationen, Schlüsselwörter oder Inhaltstypen in Daten von Drittanbietern identifizieren.

### <a name="communication-compliance"></a>Kommunikationscompliance

Sie können [die Kommunikationscompliance](communication-compliance.md) verwenden, um Daten von Drittanbietern zu überprüfen, um sicherzustellen, dass sie den Datenstandards Ihrer Organisation entsprechen. Dazu können Sie unangemessene Nachrichten in Ihrer Organisation erkennen, erfassen und beheben. Sie können beispielsweise die Drittanbieterdaten überwachen, die Sie für anstößige Sprache, vertrauliche Informationen und die Einhaltung gesetzlicher Vorschriften importieren.

### <a name="insider-risk-management"></a>Insider-Risikomanagement

Signale von Drittanbieterdaten, z. B. selektive PERSONALdaten, können von der [Insider-Risikomanagementlösung](insider-risk-management.md) verwendet werden, um interne Risiken zu minimieren, indem Sie riskante Aktivitäten in Ihrer Organisation erkennen, untersuchen und darauf reagieren können. Beispielsweise werden daten, die vom HR-Datenkonnektor importiert werden, als Risikoindikatoren verwendet, um den Diebstahl von Daten von mitarbeitern zu erkennen.

## <a name="data-connectors-in-the-us-government-cloud"></a>Datenkonnektoren in der CLOUD von US Government

Wie bereits erwähnt, sind datenkonnektoren, die von TeleMessage bereitgestellt werden, in der CLOUD der US-Regierung verfügbar. In der folgenden Tabelle sind die spezifischen Behördenumgebungen aufgeführt, die jeden TeleMessage-Datenconnector unterstützen. Weitere Informationen zu US Government-Clouds finden Sie unter [Microsoft 365 US Government](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy).

|TeleMessage-Datenconnector  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|Android-Archivierer | Ja | Nein | Nein |
|AT&T SMS/MMS Network Archiver | Ja | Nein | Nein |
|Klingel-SMS/MMS-Netzwerkarchivierer | Ja | Nein | Nein |
|Enterprise Zahlenarchivierer | Ja | Nein | Nein |
|O2-SMS und VoIP-Netzwerkarchivierer | Ja         | Nein | Nein |
|TELUS SMS Network Archiver | Ja | Nein | Nein |
|Verizon SMS/MMS Network Archiver | Ja | Nein | Nein |
|WhatsApp-Archivierer | Ja | Nein | Nein |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Zusammenarbeit mit einem Microsoft-Partner zum Archivieren von Drittanbieterdaten

Eine weitere Möglichkeit zum Importieren und Archivieren von Drittanbieterdaten besteht darin, dass Ihre Organisation mit einem Microsoft-Partner zusammenarbeiten kann. Wenn ein Datentyp eines Drittanbieters von den im Microsoft Compliance Center verfügbaren Datenconnectors nicht unterstützt wird, können Sie mit einem Partner zusammenarbeiten, der einen benutzerdefinierten Connector bereitstellen kann, der so konfiguriert wird, dass Elemente regelmäßig aus der Datenquelle des Drittanbieters extrahiert werden, und dann eine Verbindung mit der Microsoft-Cloud über eine DRITTANBIETER-API herstellen und diese Elemente in Microsoft 365 importieren. Der Partnerconnector konvertiert außerdem den Inhalt eines Elements aus der Datenquelle des Drittanbieters in eine E-Mail-Nachricht und importiert ihn dann in ein Postfach in Microsoft 365.

Eine Liste der Partner, mit denen Sie arbeiten können, und der schrittweise Prozess für diese Methode finden Sie unter Zusammenarbeit mit einem Partner zum Archivieren von [Drittanbieterdaten in Microsoft 365.](work-with-partner-to-archive-third-party-data.md)
