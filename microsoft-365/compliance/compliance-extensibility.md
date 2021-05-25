---
title: Microsoft 365 Kompatibilitätsergehnbarkeit
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Informationen zum Erweitern Microsoft 365 Compliancelösungen mithilfe von Datenconnectors von Drittanbietern und Microsoft Graph APIs.
ms.openlocfilehash: 1fed5ac72c7dbfa4b1be370ec03678e1beecdcd2
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651056"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 Kompatibilitätsergehnbarkeit

Microsoft 365 Compliancelösungen helfen Organisationen dabei, ihre Compliancerisiken intelligent zu bewerten, vertrauliche Daten zu verwalten und zu schützen und effektiv auf behördliche Anforderungen zu reagieren. Microsoft 365 compliance ist reich an Erweiterbarkeitsszenarien und ermöglicht Es Organisationen, ihre Compliancelösungen anzupassen, zu erweitern, zu integrieren, zu beschleunigen und zu unterstützen.

Es gibt zwei wichtige Bausteine für die Kompatibilitätsergehnbarkeit:

- **Datenconnectors**. Verwenden Sie zum Importieren und Archivieren von Nicht-Microsoft-Daten, damit Sie Microsoft 365 Schutz- und Steuerungsfunktionen auf Drittanbieterdaten anwenden können.

- **APIs**. Ermöglicht programmgesteuerten Zugriff auf Microsoft 365 Compliancefunktionen.

## <a name="data-connectors"></a>Datenconnectors

Microsoft stellt Datenconnectors von Drittanbietern zur Verfügung, die im compliance center Microsoft 365 konfiguriert werden können. Eine Liste der von Microsoft bereitgestellten Datenconnectors finden Sie in der Tabelle [Datenconnectors von](archiving-third-party-data.md#third-party-data-connectors) Drittanbietern. Die Tabelle der Datenconnectors von Drittanbietern enthält außerdem eine Zusammenfassung der Compliancelösungen, die Sie auf Drittanbieterdaten anwenden können, nachdem Sie Daten in Microsoft 365 importiert und archiviert haben, sowie Links zu den schrittweisen Anweisungen für jeden Connector.

Weitere Informationen zum Microsoft 365 finden Sie unter [Archivierung von Drittanbieterdaten](archiving-third-party-data.md). Wenn ein Drittanbieterdatentyp von den im Microsoft 365 Compliance Center verfügbaren Datenconnectors nicht unterstützt wird, können Sie mit einem Partner zusammenarbeiten, der Ihnen einen benutzerdefinierten Connector bereitstellen kann. Eine Liste der Partner, mit der Sie zusammenarbeiten können, und den schrittweisen Prozess für diese Methode finden Sie unter Arbeiten mit einem Partner zum Archivieren von [Drittanbieterdaten](work-with-partner-to-archive-third-party-data.md).

### <a name="prerequisites-for-data-connectors"></a>Voraussetzungen für Datenconnectors

Viele der datenconnectors, die im Microsoft 365 Compliance Center zum Importieren und Archivieren von Drittanbieterdaten verfügbar sind, erfordern, dass Sie Konfigurationsaufgaben in der Datenquelle eines Drittanbieters vorbereiten und ausführen. Diese Voraussetzungen sind für jeden Datenconnector eines Drittanbieters detailliert dokumentiert.

Für Datenconnectors im Microsoft 365 Compliance Center, das von einem der Partner von Microsoft bereitgestellt wird, benötigt Ihre Organisation eine Geschäftsbeziehung mit dem Partner, bevor Sie einen Connector bereitstellen können.

Lizenzierungsanforderungen für Datenconnectors von Drittanbietern finden Sie im Dokument [Microsoft 365 Compliance Licensing Comparison.](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)

## <a name="apis"></a>APIs

Microsoft 365 Compliance-APIs sind im Microsoft Information Protection SDK, der Microsoft Graph-API und der Office 365-Verwaltungsaktivitäts-API verfügbar. Einige Compliance-APIs sind Teil einer neuen Gruppe von Sicherheits- und Compliance-APIs, mit denen Entwickler für Microsoft 365-Kunden, unabhängige Softwareanbieter, Systemintegratoren und anbieter für verwaltete Sicherheitsdienste hochwertige Sicherheits- und Compliancelösungen erstellen können.

Weitere Informationen zum Zugriff auf Graph-APIs finden Sie unter [Overview of Microsoft Graph](/graph/overview).

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP) SDK

Das MIP SDK macht die Bezeichnungs- und Schutzdienste von Microsoft 365 Sicherheits- und Compliancecentern für Anwendungen und Dienste von Drittanbietern verfügbar. Entwickler können das SDK verwenden, um systemeigene Unterstützung für das Anwenden von Bezeichnungen und Schutz auf Dateien zu erstellen. Entwickler können bestimmen, welche Aktionen beim Erkennen bestimmter Bezeichnungen ergriffen werden sollen, und einen Grund für MIP-verschlüsselte Informationen.

Zu den high-level MIP SDK-Verwendungsfällen gehören:

- Eine Geschäftsanwendung, die Klassifizierungsbezeichnungen auf Dateien beim Export angewendet.

- Eine CAD/CAM-Entwurfsanwendung, die systemeigene Unterstützung für die MIP-Bezeichnung bietet.

- Ein Cloudzugriffssicherheitsbroker oder eine Lösung zur Verhinderung von Datenverlust, die Daten mit Azure Information Protection verschlüsseln kann.

Weitere Informationen zum MIP SDK, den Voraussetzungen, zusätzlichen Szenarien und Beispielen finden Sie unter [MIP SDK Overview](/information-protection/develop/overview).

### <a name="microsoft-graph-api-for-teams-dlp"></a>Microsoft Graph-API für Teams DLP

Funktionen zur Verhinderung von Datenverlust (Data Loss Prevention, [DLP)](dlp-microsoft-teams.md) werden in Microsoft Teams insbesondere da Organisationen auf Remotearbeit umschichtet haben. Anfang dieses Jahres haben wir [die](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) öffentliche Vorschau der Microsoft Graph Change Notification API für Nachrichten in Teams. Diese API ermöglicht Entwicklern das Erstellen von Apps, die Microsoft Teams Nachrichten in nahezu Echtzeit abhören und dann DLP-Szenarien für Kunden und Partner implementieren können. Darüber hinaus können Sie mit Graph Patch-API DLP-Aktionen auf Teams anwenden.

Diese beiden APIs bilden die Microsoft Graph-API für Teams DLP. Sie können mit der Beispiel-App [beginnen.](https://github.com/microsoftgraph/csharp-webhook-with-resource-data) Weitere Informationen zu Microsoft Teams Messagingwebhooks finden Sie in der [Dokumentation](/graph/api/subscription-post-subscriptions).

Die Lizenzierungsanforderungen für Teams DLP finden Sie unter Microsoft 365 Lizenzierungsleitfade [für & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams).

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>Microsoft Graph-API für eDiscovery (Vorschau)

Mit [Advanced eDiscovery](overview-ediscovery-20.md)können Organisationen Daten dort ermitteln, wo sie sich befinden, und mehr End-to-End-eDiscovery-Workflows mit intelligenten Machine-Learning- und Analysefunktionen verwalten, um Daten auf den relevanten Satz zu reduzieren – und das alles, während die Daten Microsoft 365 der Sicherheits- und Compliancegrenze bleiben.

Graph APIs für Advanced eDiscovery können verwendet werden, um Fälle zu erstellen und zu verwalten, Sätze zu überprüfen und Satzabfragen skalierbar und wiederholbar zu überprüfen. Auf diese Weise können Kunden und Partner Apps und Workflows erstellen, um häufige und sich wiederholende Prozesse wie das Erstellen von Fällen und die Verwaltung von Verwahrern und rechtlichen Abläufen zu automatisieren.

Der erste Satz von Graph-APIs für eDiscovery ist in der öffentlichen Vorschau verfügbar. Wir planen, bis zum Ende des Kalenderjahres weitere Funktionen hinzuzufügen. Weitere Informationen zu diesen APIs und anderen Updates für Advanced eDiscovery finden Sie in diesem [Blog](https://aka.ms/Ignite2020AeDAA).

Die Lizenzierungsanforderungen für Advanced eDiscovery und die API finden Sie im Abschnitt "eDiscovery" im Microsoft 365-Lizenzierungsleitfas für & [Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery).

### <a name="microsoft-graph-api-for-teams-export-preview"></a>Microsoft Graph-API für Teams Export (Vorschau)

Enterprise Die Informationsarchivierung (EIA) für Microsoft Teams ist ein Schlüsselszenario für unsere Kunden, da sie es ihnen ermöglicht, gesetzliche Anforderungen zu erfüllen. Zusätzlich zu unseren integrierten Funktionen für die Archivierung von Inhalten in Microsoft Teams können Kunden und Partner jetzt Teams Export-APIs verwenden, um benutzerdefinierte Anwendungs- und Integrationsszenarien zu lösen. Die Teams Export-APIs unterstützen den Massenexport (bis zu 200 Anforderungen pro Sekunde/pro App/pro Mandant) von Teams Nachrichten und Nachrichtenanlagen. Auf gelöschte Nachrichten kann die API auch bis zu 30 Tage nach dem Löschen zugreifen. Weitere Informationen zu diesen Teams-APIs und deren Verwendung in Ihren Anwendungen finden Sie unter Exportieren von Inhalten mit den [Microsoft Teams-APIs](/microsoftteams/export-teams-content).

Die Lizenzierungsanforderungen für die Verwendung der Teams-Export-APIs finden Sie [unter Microsoft 365 Lizenzierungsanleitung für](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)& Compliance .

### <a name="microsoft-graph-connector-apis-preview"></a>Microsoft Graph Connector-APIs (Vorschau)

Mit [Microsoft Graph Connectors](/microsoftsearch/connectors-overview)können Organisationen Drittanbieterdaten indizieren, sodass sie in den Microsoft-Suchergebnissen angezeigt werden. Mit diesem Feature werden die Typen von Inhaltsquellen erweitert, die in Ihren Microsoft 365 und dem umfassenderen Microsoft-Ökosystem durchsucht werden können. Die Drittanbieterdaten können lokal oder in öffentlichen oder privaten Clouds gehostet werden. Beginnend mit Advanced eDiscovery ermöglichen wir entwicklervorschau des integrierten Compliancewerts von Microsoft 365 apps. Dies ermöglicht die Compliance für Apps, die in das Microsoft 365 integriert werden, um Benutzern eine nahtlose Complianceerfahrung zu ermöglichen. Weitere Informationen zum Integrieren von Microsoft Graph Connector-APIs in ihre Apps-Ansicht finden Sie unter [Create, update, and delete connections in the Microsoft Graph](/graph/search-index-manage-connections).

