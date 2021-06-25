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
ms.openlocfilehash: c30be0888a2c92a23c4e5f323235eba671c5ab1d
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137724"
---
# <a name="archive-third-party-data-in-microsoft-365"></a>Archivieren von Drittanbieterdaten in Microsoft 365

mit Microsoft 365 können Administratoren Datenkonnektoren verwenden, um Daten von Drittanbietern von Social Media-Plattformen, Chatplattformen und Plattformen für die Zusammenarbeit an Dokumenten in Postfächern in Ihrer Microsoft 365 Organisation zu importieren und zu archivieren. Ein Hauptvorteil der Verwendung von Datenconnectors zum Importieren und Archivieren von Drittanbieterdaten in Microsoft 365 besteht darin, dass Sie nach dem Import verschiedene Microsoft 365 Compliancelösungen darauf anwenden können. Auf diese Weise können Sie sicherstellen, dass die Nicht-Microsoft-Daten Ihrer Organisation den Vorschriften und Standards entsprechen, die sich auf Ihre Organisation auswirken.

## <a name="third-party-data-connectors"></a>Daten-Connectoren von Drittanbietern

Das Microsoft 365 Compliance Center stellt systemeigene Drittanbieter-Datenconnectors von Microsoft zum Importieren von Daten aus verschiedenen Datenquellen bereit, z. B. LinkedIn, Instant Bloomberg und Twitter sowie Datenconnectors, die die Insider-Risikomanagementlösung unterstützen. Zusätzlich zu diesen Datenconnectors arbeitet Microsoft mit den folgenden Partnern zusammen, um im Microsoft 365 Compliance Center noch viel mehr Datenconnectors des dritten Teils bereitzustellen. Ihre Organisation arbeitet mit diesen Partnern zusammen, um ihren Archivierungsdienst einzurichten, bevor ein entsprechender Datenkonnektor im Microsoft 365 Compliance Center erstellt wird.

- [Veritas](#veritas-data-connectors)

- [TeleMessage](#telemessage-data-connectors)

- [17a-4 LLC](#17a-4-data-connectors)

- [CellTrust](#celltrust-data-connectors)

Die in den nächsten Abschnitten aufgeführten Drittanbieterdaten (mit Ausnahme von PERSONAL-Daten und physischen Daten, die für die Microsoft 365 Insider-Risikomanagementlösung verwendet werden) werden in Benutzerpostfächer importiert. Die Microsoft 365 Compliancelösungen, die Drittanbieterdaten unterstützen, werden auf das Benutzerpostfach angewendet, in dem die Daten gespeichert sind.

### <a name="microsoft-data-connectors"></a>Microsoft-Datenkonnektoren

In der folgenden Tabelle sind die systemeigenen Datenkonnektoren von Drittanbietern aufgeführt, die im Microsoft 365 Compliance Center verfügbar sind. Die Tabelle enthält außerdem eine Zusammenfassung der Compliancelösungen, die Sie anwenden können, nachdem Sie Drittanbieterdaten in Microsoft 365 importiert und archiviert haben. Im Abschnitt ["Übersicht über Compliancelösungen, die Daten](#overview-of-compliance-solutions-that-support-third-party-data) von Drittanbietern unterstützen" finden Sie eine detailliertere Beschreibung der einzelnen Compliancelösungen und der Unterstützung von Drittanbieterdaten.

Klicken Sie auf den Link in der **Datenspalte** des Drittanbieters, um die schrittweisen Anweisungen zum Erstellen eines Connectors für diesen Datentyp zu erhalten.

|Drittanbieterdaten  |Beweissicherungsverfahren|eDiscovery  |Aufbewahrungseinstellungen  |Datensatzverwaltung  |Kommunikationscompliance  |Insider-Risikomanagement  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Bloomberg Message](archive-bloomberg-message-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Personalwesen (HR)](import-hr-data.md) ||||||![Häkchen](../media/checkmark.png)
|[ICE Chat](archive-icechat-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Physisches Ausweichen](import-physical-badging-data.md) ||||||![Häkchen](../media/checkmark.png)|
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
||||||||

### <a name="veritas-data-connectors"></a>Veritas-Datenkonnektoren

In der Tabelle in diesem Abschnitt sind die datenkonnektoren von Drittanbietern aufgeführt, die in Zusammenarbeit mit Csv verfügbar sind. In der Tabelle sind auch die Compliancelösungen zusammengefasst, die Sie nach dem Importieren und Archivieren in Microsoft 365 auf Drittanbieterdaten anwenden können. Im Abschnitt ["Übersicht über Compliancelösungen, die Daten](#overview-of-compliance-solutions-that-support-third-party-data) von Drittanbietern unterstützen" finden Sie eine detailliertere Beschreibung der einzelnen Compliancelösungen und der Unterstützung von Drittanbieterdaten.

Bevor Sie Daten von Drittanbietern in Microsoft 365 archivieren können, müssen Sie mit Deren Archivierungsdienst *(merge1* genannt) für Ihre Organisation zusammenarbeiten. Klicken Sie für weitere Informationen auf den Link in der **Datenspalte** des Drittanbieters, um die schrittweisen Anweisungen zum Erstellen eines Connectors für diesen Datentyp zu erhalten.

|Drittanbieterdaten  |Beweissicherungsverfahren|eDiscovery  |Aufbewahrungseinstellungen  |Datensatzverwaltung  |Kommunikationscompliance  |Insider-Risikomanagement  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust](archive-celltrust-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Cisco-Jabber auf MS SQL](archive-ciscojabberonmssql-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Cisco-Jabber auf Oracle](archive-ciscojabberonoracle-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Cisco-Jabber auf PostgreSQL](archive-ciscojabberonpostgresql-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[EML](archive-eml-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[FX Connect](archive-fxconnect-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Jive](archive-jive-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[MS SQL-Datenbank](archive-mssqldatabaseimporter-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Pivot](archive-pivot-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Redtail Speak](archive-redtailspeak-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Reuters Dealing](archive-reutersdealing-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Reuters Eikon](archive-reuterseikon-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Reuters FX](archive-reutersfx-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Salesforce Chatter](archive-salesforcechatter-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[ServiceNow](archive-servicenow-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Slack eDiscovery](archive-slack-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Symphony](archive-symphony-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Texttrennzeichen](archive-text-delimited-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Webex Teams](archive-webexteams-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Webseiten](archive-webpagecapture-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Workplace von Facebook](archive-workplacefromfacebook-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[XIP](archive-xip-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[XSLT/XML](archive-xslt-xml-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Yieldbroker](archive-yieldbroker-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Zoom Besprechungen](archive-zoommeetings-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
||||||||

### <a name="telemessage-data-connectors"></a>TeleMessage Datenconnectors

In der Tabelle in diesem Abschnitt sind die datenkonnektoren von Drittanbietern aufgeführt, die in Zusammenarbeit mit TeleMessage verfügbar sind. Die Tabelle enthält außerdem eine Zusammenfassung der Compliancelösungen, die Sie nach dem Importieren und Archivieren in Microsoft 365 auf Drittanbieterdaten anwenden können. Im Abschnitt ["Übersicht über Compliancelösungen, die Daten](#overview-of-compliance-solutions-that-support-third-party-data) von Drittanbietern unterstützen" finden Sie eine detailliertere Beschreibung der einzelnen Compliancelösungen und der Unterstützung von Drittanbieterdaten.

Bevor Sie Daten von Drittanbietern in Microsoft 365 archivieren können, müssen Sie mit TeleMessage zusammenarbeiten, um deren Archivierungsdienst für Ihre Organisation einzurichten. Klicken Sie für weitere Informationen auf den Link in der **Datenspalte** des Drittanbieters, um die schrittweisen Anweisungen zum Erstellen eines Connectors für diesen Datentyp zu erhalten.

TeleMessage-Datenconnectors sind auch in GCC Umgebungen in der Microsoft 365 US Government-Cloud verfügbar. Weitere Informationen finden Sie im Abschnitt "Datenkonnektoren" im Abschnitt "US Government Cloud" in diesem Artikel.

|Drittanbieterdaten  |Beweissicherungsverfahren|eDiscovery  |Aufbewahrungseinstellungen  |Datensatzverwaltung  |Kommunikationscompliance  |Insider-Risikomanagement  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android ](archive-android-archiver-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[AT&T Network ](archive-att-network-archiver-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Bell Network ](archive-bell-network-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Enterprise Anzahl](archive-enterprise-number-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[O2-Netzwerk ](archive-o2-network-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[TELUS-Netzwerk ](archive-telus-network-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Verizon Network ](archive-verizon-network-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[WeChat ](archive-wechat-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Whatsapp ](archive-whatsapp-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
||||||||

### <a name="17a-4-data-connectors"></a>17a-4-Datenconnectors

In der Tabelle in diesem Abschnitt sind die Datenkonnektoren von Drittanbietern aufgeführt, die in Zusammenarbeit mit 17a-4 LLC verfügbar sind. Die Tabelle enthält außerdem eine Zusammenfassung der Compliancelösungen, die Sie nach dem Importieren und Archivieren in Microsoft 365 auf Drittanbieterdaten anwenden können. Im Abschnitt ["Übersicht über Compliancelösungen, die Daten](#overview-of-compliance-solutions-that-support-third-party-data) von Drittanbietern unterstützen" finden Sie eine detailliertere Beschreibung der einzelnen Compliancelösungen und der Unterstützung von Drittanbieterdaten.

Bevor Sie Daten von Drittanbietern in Microsoft 365 archivieren können, müssen Sie mit Deren Archivierungsdienst *(dataparser* genannt) für Ihre Organisation zusammenarbeiten. Klicken Sie für weitere Informationen auf den Link in der **Datenspalte** des Drittanbieters, um die schrittweisen Anweisungen zum Erstellen eines Connectors für diesen Datentyp zu erhalten.

|Drittanbieterdaten  |Beweissicherungsverfahren|eDiscovery  |Aufbewahrungseinstellungen  |Datensatzverwaltung  |Kommunikationscompliance  |Insider-Risikomanagement  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[BlackBerry](archive-17a-4-blackberry-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Bloomberg ](archive-17a-4-bloomberg-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Cisco Jabber ](archive-17a-4-cisco-jabber-data.md)   |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Cisco Webex ](archive-17a-4-webex-teams-data.md)   |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[FactSet ](archive-17a-4-factset-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Fuze ](archive-17a-4-fuze-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[FX Verbinden](archive-17a-4-fxconnect-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[ICE Chat](archive-17a-4-ice-im-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[InvestEdge ](archive-17a-4-investedge-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[LivePerson Conversational Cloud ](archive-17a-4-liveperson-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Quip ](archive-17a-4-quip-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Refinitiv Ediscovery Messenger](archive-17a-4-refinitiv-messenger-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Servicenow ](archive-17a-4-servicenow-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Slack ](archive-17a-4-slack-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[SQL](archive-17a-4-sql-database-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Symphonie ](archive-17a-4-symphony-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Zoom ](archive-17a-4-zoom-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
||||||||

### <a name="celltrust-data-connectors"></a>CellTrust-Datenkonnektoren

In der Tabelle in diesem Abschnitt ist der Datenkonnektor eines Drittanbieters aufgeführt, der in Zusammenarbeit mit CellTrust verfügbar ist. In der Tabelle sind auch die Compliancelösungen zusammengefasst, die Sie nach dem Importieren und Archivieren in Microsoft 365 auf Drittanbieterdaten anwenden können. Im Abschnitt ["Übersicht über Compliancelösungen, die Daten](#overview-of-compliance-solutions-that-support-third-party-data) von Drittanbietern unterstützen" finden Sie eine detailliertere Beschreibung der einzelnen Compliancelösungen und der Unterstützung von Drittanbieterdaten.

Bevor Sie Daten von Drittanbietern in Microsoft 365 archivieren können, müssen Sie mit CellTrust zusammenarbeiten, um deren Archivierungsdienst *(celltrust SL2)* für Ihre Organisation einzurichten. Klicken Sie für weitere Informationen auf den Link in der **Datenspalte** des Drittanbieters, um die schrittweisen Anweisungen zum Erstellen eines CellTrust SL2-Connectors zu erhalten.

|Drittanbieterdaten  |Beweissicherungsverfahren|eDiscovery  |Aufbewahrungseinstellungen  |Datensatzverwaltung  |Kommunikationscompliance  |Insider-Risikomanagement  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust SL2](archive-data-from-celltrustsl2.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
||||||||

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
|Android-Archivierung | Ja | Nein | Nein |
|AT&T SMS/MMS-Netzwerkarchivierung | Ja | Nein | Nein |
|Bell SMS/MMS-Netzwerkarchivierung | Ja | Nein | Nein |
|Enterprise-Zahlenarchivierung | Ja | Nein | Nein |
|O2-SMS und VoIP-Netzwerkarchivierer | Ja         | Nein | Nein |
|TELUS SMS Network Archiver | Ja | Nein | Nein |
|Verizon SMS/MMS-Netzwerkarchivierung | Ja | Nein | Nein |
|WhatsApp-Archivierung | Ja | Nein | Nein |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Zusammenarbeit mit einem Microsoft-Partner zum Archivieren von Drittanbieterdaten

Eine weitere Möglichkeit zum Importieren und Archivieren von Drittanbieterdaten besteht darin, dass Ihre Organisation mit einem Microsoft-Partner zusammenarbeiten kann. Wenn ein Datentyp eines Drittanbieters von den im Microsoft Compliance Center verfügbaren Datenconnectors nicht unterstützt wird, können Sie mit einem Partner zusammenarbeiten, der einen benutzerdefinierten Connector bereitstellen kann, der so konfiguriert wird, dass Elemente regelmäßig aus der Datenquelle des Drittanbieters extrahiert werden, und dann eine Verbindung mit der Microsoft-Cloud über eine DRITTANBIETER-API herstellen und diese Elemente in Microsoft 365 importieren. Der Partnerconnector konvertiert außerdem den Inhalt eines Elements aus der Datenquelle des Drittanbieters in eine E-Mail-Nachricht und importiert es dann in ein Postfach in Microsoft 365.

Eine Liste der Partner, mit denen Sie arbeiten können, und der schrittweise Prozess für diese Methode finden Sie unter Zusammenarbeit mit einem Partner zum Archivieren von [Drittanbieterdaten in Microsoft 365.](work-with-partner-to-archive-third-party-data.md)
