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
description: In diesem Artikel erfahren Sie, wie Sie drittanbieterdaten aus Social Media-Plattformen, Instant Messaging-Plattformen und Dokument Zusammenarbeits Plattformen zu Microsoft 365-Postfächern importieren.
ms.openlocfilehash: 42835d103e027bd63687151554f811dc0945d46f
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682616"
---
# <a name="archive-third-party-data"></a>Archivieren von Drittanbieterdaten

Microsoft 365 ermöglicht Administratoren das Importieren und Archivieren von drittanbieterdaten aus Social Media-Plattformen, Instant Messaging-Plattformen und Dokument Zusammenarbeits Plattformen in Postfächern in Ihrer Microsoft 365-Organisation mithilfe von Daten-Konnektoren. Ein Hauptvorteil der Verwendung von Daten Konnektoren zum Importieren und Archivieren von drittanbieterdaten in Microsoft 365 besteht darin, dass Sie verschiedene Microsoft 365-Kompatibilitätslösungen auf diese anwenden können, nachdem Sie importiert wurde. Auf diese Weise können Sie sicherstellen, dass die nicht-Microsoft-Daten Ihrer Organisation mit den Vorschriften und Standards in Ihrer Organisation übereinstimmen.

## <a name="third-party-data-connectors"></a>Daten-Connectoren von Drittanbietern

In der folgenden Tabelle sind die Drittanbieter-Daten-Konnektoren aufgeführt, die im Microsoft 365 Compliance Center verfügbar sind. In der Tabelle sind auch die Kompatibilitätslösungen zusammengefasst, die Sie nach dem Importieren und Archivieren in Microsoft 365 auf drittanbieterdaten anwenden können. Im [nächsten Abschnitt](#overview-of-compliance-solutions-that-support-third-party-data) finden Sie eine ausführlichere Beschreibung der einzelnen Kompatibilitätslösungen sowie Informationen dazu, wie drittanbieterdaten genutzt werden können.

> [!TIP]
> Klicken Sie auf den Link in der Spalte **drittanbieterdaten** , um die schrittweisen Anweisungen zum Erstellen eines Connectors für diesen Datentyp zu öffnen.

|Drittanbieterdaten  |Beweissicherungsverfahren|eDiscovery  |Aufbewahrungseinstellungen  |Datensatzverwaltung  |Kommunikationscompliance  |Insider-Risikomanagement  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Bei&T Network <sup>1</sup>](archive-att-network-archiver-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Glocken Netz <sup>1</sup>](archive-bell-network-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Bloomberg Message](archive-bloomberg-message-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[CellTrust <sup>2</sup>](archive-celltrust-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Cisco Jabber <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Enterprise-Nummer <sup>1</sup>](archive-enterprise-number-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[FX Connect <sup>2</sup>](archive-fxconnect-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Personalwesen (HR)](import-hr-data.md) ||||||![Häkchen](../media/checkmark.png)
|[ICE Chat](archive-icechat-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[MS SQL-Datenbank <sup>2</sup>](archive-mssqldatabaseimporter-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[O2-Netzwerk <sup>1</sup>](archive-o2-network-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Physische Badges](import-physical-badging-data.md) ||||||![Häkchen](../media/checkmark.png)|
|[Pivot <sup>2</sup>](archive-pivot-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Reuters-Handel <sup>2</sup>](archive-reutersdealing-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Reuters EIKON <sup>2</sup>](archive-reuterseikon-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Reuters FX <sup>2</sup>](archive-reutersfx-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Slack eDiscovery <sup>2</sup>](archive-slack-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Symphonie <sup>2</sup>](archive-symphony-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Telus-Netzwerk <sup>1</sup>](archive-telus-network-data.md)    |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Text-Trennzeichen <sup>2</sup>](archive-text-delimited-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Verizon-Netzwerk <sup>1</sup>](archive-verizon-network-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[WebEx Teams <sup>2</sup>](archive-webexteams-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Webseiten <sup>2</sup>](archive-webpagecapture-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[Arbeitsplatz von Facebook <sup>2</sup>](archive-workplacefromfacebook-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|||
|[Vergrössern von Besprechungen <sup>2</sup>](archive-zoommeetings-data.md)     |![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
||||||||

> [!NOTE]
> <sup>1</sup> von TeleMessage bereitgestellter Datenanschluss. Bevor Sie Daten in Microsoft 365 archivieren können, müssen Sie mit TeleMessage zusammenarbeiten, um den Archivierungsdienst für Ihre Organisation einzurichten. Weitere Informationen finden Sie im Abschnitt Voraussetzungen in den schrittweisen Anleitungen für diesen Datentyp.<br/><br/><sup>2</sup> von Globanet bereitgestellter Datenanschluss. Bevor Sie Daten in Microsoft 365 archivieren können, müssen Sie mit Globanet zusammenarbeiten, um den Archivierungsdienst für Ihre Organisation einzurichten. Weitere Informationen finden Sie im Abschnitt Voraussetzungen in den schrittweisen Anleitungen für diesen Datentyp.

Die in der vorherigen Tabelle aufgeführten drittanbieterdaten (mit Ausnahme von HR-und physischen Badges-Daten) werden in Benutzerpostfächer importiert. Die entsprechenden Compliance-Lösungen, die drittanbieterdaten unterstützen, werden auf das Benutzerpostfach angewendet, in dem die Daten gespeichert sind.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Übersicht über Kompatibilitätslösungen zur Unterstützung von drittanbieterdaten

In den folgenden Abschnitten werden einige der Dinge beschrieben, die die Microsoft 365-Kompatibilitätslösungen bei der Verwaltung der in der vorherigen Tabelle aufgeführten drittanbieterdaten unterstützen können.

### <a name="litigation-hold"></a>Beweissicherungsverfahren

Sie legen ein [Beweissicherungsverfahren](create-a-litigation-hold.md) für ein Benutzerpostfach fest, um drittanbieterdaten beizubehalten. Wenn Sie einen Haltestatus erstellen, können Sie eine Aufbewahrungsdauer (auch als *zeitbasierter halte* Bereich bezeichnet) festlegen, damit gelöschte und geänderte drittanbieterdaten für einen bestimmten Zeitraum aufbewahrt und dann endgültig aus dem Postfach gelöscht werden. Oder Sie können Inhalte auf unbestimmte Zeit beibehalten (als *endlos Sperre* bezeichnet) oder bis das Beweissicherungsverfahren entfernt wird.

### <a name="ediscovery"></a>eDiscovery

Die drei primären eDiscovery-Tools in Microsoft 365 sind Inhaltssuche, zentrale eDiscovery und erweiterte eDiscovery.

- **[Inhaltssuche](content-search.md).** Sie können das Inhalts Such Tool verwenden, um Postfächer für Daten von Drittanbietern zu durchsuchen, die Sie importiert haben. Sie können Suchabfragen und-Bedingungen verwenden, um die Suchergebnisse einzuschränken, und die Suchergebnisse exportieren.

- **[Zentrale eDiscovery](get-started-core-ediscovery.md).** Dieses Tool baut auf den grundlegenden Such-und Exportfunktionen auf, indem es Ihnen ermöglicht, Fälle zu erstellen, mit denen Sie steuern können, wer auf Falldaten zugreifen kann, indem Sie Benutzerpostfächer oder Postfachinhalte, die Suchkriterien entsprechen, aufbewahren. Das bedeutet, dass Sie den drittanbieterdaten, die in Benutzerpostfächern importiert wurden, einen eDiscovery-Aufbewahrungsplatz geben können.

- **[Erweiterte eDiscovery](overview-ediscovery-20.md).** Dieses leistungsstarke Tool erweitert die Fall Funktionen von Core eDiscovery, indem Sie Verwalter zu einem Fall hinzufügen, die Aufbewahrungsdaten der Depotbank speichern und dann die drittanbieterdaten eines Depot Empfängers zur weiteren Analyse wie Designs und doppelter Erkennung in eine Überprüfung laden. Nachdem Sie Daten eines Drittanbieters in einen Überprüfungs importiert haben, können Sie ihn in einem engen Resultset Abfragen und filtern.

   Sowohl die Haupt-eDiscovery-als auch die Advanced-eDiscovery ermöglichen Ihnen die Verwaltung von drittanbieterdaten, die für die rechtlichen oder internen Untersuchungen Ihrer Organisation relevant sein können.

### <a name="retention-settings"></a>Aufbewahrungseinstellungen

Sie können eine [Aufbewahrungsrichtlinie](retention.md) auf Benutzerpostfächer anwenden, um drittanbieterdaten (und andere Postfachinhalte) nach Ablauf des Aufbewahrungszeitraums beizubehalten und anschließend zu löschen. Sie können auch mithilfe von Aufbewahrungsrichtlinien drittanbieterdaten eines bestimmten Alters löschen oder [Aufbewahrungs Bezeichnungen verwenden, um eine Dispositions Überprüfung auszulösen,](disposition.md) wenn der Aufbewahrungszeitraum für drittanbieterdaten abläuft.

### <a name="records-management"></a>Datensatzverwaltung

Mit dem Feature für die [Datensatzverwaltung](records-management.md) in Microsoft 365 können Sie drittanbieterdaten als Datensatz deklarieren. Dies kann manuell von Benutzern durchgeführt werden, die eine Aufbewahrungs Bezeichnung anwenden, die drittanbieterdaten in Ihrem Postfach als Datensatz kennzeichnet. Oder Sie können Aufbewahrungs Bezeichnungen automatisch anwenden, indem Sie vertrauliche Informationen, Stichwörter oder Inhaltstypen in drittanbieterdaten identifizieren.

### <a name="communication-compliance"></a>Kommunikationscompliance

Sie können die [Kommunikations Konformität](communication-compliance.md) verwenden, um drittanbieterdaten zu überprüfen, um sicherzustellen, dass Sie mit den Datenstandards Ihrer Organisation konform sind. Sie können dies tun, indem Sie Korrekturaktionen für ungeeignete Nachrichten in Ihrer Organisation erkennen, erfassen und ausführen. Beispielsweise können Sie die von Ihnen importierten drittanbieterdaten für anstößige Sprache, vertrauliche Informationen und behördliche Compliance überwachen.

### <a name="insider-risk-management"></a>Insider-Risikomanagement

Signale von drittanbieterdaten, wie beispielsweise selektive HR-Daten, können von der [Insider Risikomanagement](insider-risk-management.md) -Lösung verwendet werden, um interne Risiken zu minimieren, indem Sie riskante Aktivitäten in Ihrer Organisation erkennen, untersuchen und auf diese reagieren. Beispielsweise werden Daten, die vom HR Data Connector importiert werden, als Risikoindikatoren verwendet, um den Datendiebstahl beim Mitarbeiter zu ermitteln.

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Arbeiten mit einem Microsoft-Partner zum Archivieren von drittanbieterdaten

Eine weitere Option zum Importieren und Archivieren von drittanbieterdaten besteht darin, dass Ihre Organisation mit einem Microsoft-Partner zusammenarbeitet. Wenn ein Drittanbieter Datentyp nicht von den im Microsoft Compliance Center verfügbaren Daten Konnektoren unterstützt wird, können Sie mit einem Partner zusammenarbeiten, der einen benutzerdefinierten Connector bereitstellen kann, der so konfiguriert ist, dass er regelmäßig Elemente aus der Drittanbieter-Datenquelle extrahiert und dann über eine Drittanbieter-API eine Verbindung mit der Microsoft-Cloud hergestellt und diese Elemente in Microsoft 365 importiert Der Partner Connector konvertiert auch den Inhalt eines Elements aus der Drittanbieter-Datenquelle in eine e-Mail-Nachricht und importiert diese dann in ein Postfach in Microsoft 365.

Eine Liste der Partner, mit denen Sie zusammenarbeiten und den schrittweisen Prozess für diese Methode ausführen können, finden Sie unter [Arbeiten mit einem Partner zum Archivieren von drittanbieterdaten in Microsoft 365](work-with-partner-to-archive-third-party-data.md).
