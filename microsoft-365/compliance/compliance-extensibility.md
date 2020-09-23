---
title: Microsoft 365-Compliance-Erweiterbarkeit
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
description: Erfahren Sie mehr über das Erweitern von Microsoft 365-Kompatibilitätslösungen mithilfe von Drittanbieter-Daten-Konnektoren und Microsoft Graph-APIs.
ms.openlocfilehash: 284125db8243b10f5c8de7e0a37c1b7284709c28
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204400"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365-Compliance-Erweiterbarkeit

Microsoft 365 Compliance-Lösungen helfen Organisationen, Ihre Compliance-Risiken intelligent zu bewerten, vertrauliche Daten zu steuern und zu schützen und effektiv auf regulatorische Anforderungen zu reagieren. Die Kompatibilität mit Microsoft 365 ist reich an Erweiterungs Szenarien und ermöglicht es Organisationen, Ihre Compliance-Lösungen anzupassen, zu erweitern, zu integrieren, zu beschleunigen und zu unterstützen.

Für die Erweiterbarkeit der Kompatibilität gibt es zwei wichtige Bausteine:

- **Daten-Konnektoren**. Verwenden Sie zum Importieren und Archivieren von nicht-Microsoft-Daten, damit Sie Microsoft 365-Schutz-und-Steuerungsfunktionen auf drittanbieterdaten anwenden können.

- **APIs**. Ermöglicht den programmgesteuerten Zugriff auf die Microsoft 365-Konformitäts Funktionen.

## <a name="data-connectors"></a>Datenconnectors

Microsoft stellt Daten-Konnektoren von Drittanbietern bereit, die im Microsoft 365 Compliance Center konfiguriert werden können. Eine Liste der von Microsoft bereitgestellten Daten-Konnektoren finden Sie in der Tabelle " [Drittanbieter-Daten Konnektoren](archiving-third-party-data.md#third-party-data-connectors) ". In der Tabelle mit Drittanbieter-Daten Konnektoren werden auch die Kompatibilitätslösungen zusammengefasst, die Sie nach dem Importieren und Archivieren von Daten in Microsoft 365 auf drittanbieterdaten anwenden können, sowie Links zu den schrittweisen Anleitungen für jeden Connector.

Weitere Informationen zu Microsoft 365-Daten Konnektoren finden Sie unter [Archivieren von drittanbieterdaten](archiving-third-party-data.md). Wenn ein Drittanbieter Datentyp nicht von den im Microsoft 365 Compliance Center verfügbaren Daten Konnektoren unterstützt wird, können Sie mit einem Partner zusammenarbeiten, der Ihnen einen benutzerdefinierten Connector zur Verfügung stellen kann. Eine Liste der Partner, mit denen Sie zusammenarbeiten können, und der schrittweise Prozess für diese Methode finden Sie unter [Arbeiten mit einem Partner zum Archivieren von drittanbieterdaten](work-with-partner-to-archive-third-party-data.md).

### <a name="prerequisites-for-data-connectors"></a>Voraussetzungen für Daten-Konnektoren

Viele der im Microsoft 365 Compliance Center verfügbaren Daten Konnektoren zum Importieren und Archivieren von drittanbieterdaten erfordern die Vorbereitung und Ausführung von Konfigurationsaufgaben in der Drittanbieter-Datenquelle. Diese Voraussetzungen werden für jeden Daten Konnektor eines Drittanbieters ausführlich dokumentiert.

Für Daten-Konnektoren im Microsoft 365 Compliance Center, die von einem der Partner von Microsoft bereitgestellt werden, benötigt Ihre Organisation eine Geschäftsbeziehung mit dem Partner, bevor Sie einen Connector bereitstellen können.

Lizenzierungsanforderungen für Drittanbieter-Daten-Konnektoren finden Sie im [Microsoft 365 Compliance Licensing Comparison](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) Document.

## <a name="apis"></a>APIs

Microsoft 365-Kompatibilitäts-APIs stehen im Microsoft Information Protection-SDK, in der Microsoft Graph-API und in der API für die Office 365-Verwaltungsaktivität zur Verfügung. Einige Kompatibilitäts-APIs sind Teil eines neuen Satzes an Sicherheits-und Kompatibilitäts-APIs, mit denen Entwickler von Microsoft 365-Kunden, unabhängigen Softwareanbietern, Systemintegratoren und verwalteten Sicherheitsdienst Anbietern hochwertige Sicherheits-und Compliance-Lösungen erstellen können.

Weitere Informationen zum Zugreifen auf Graph-APIs finden Sie unter [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview).

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP)-SDK

Das MIP-SDK macht die Bezeichnungs-und Schutzdienste von Microsoft 365 Security and Compliance Center für Anwendungen und Dienste von Drittanbietern verfügbar. Entwickler können das SDK verwenden, um systemeigene Unterstützung für das Anwenden von Bezeichnungen und Schutz auf Dateien zu erstellen. Entwickler können bestimmen, welche Aktionen ausgeführt werden sollen, wenn bestimmte Bezeichnungen erkannt werden, und begründen über MIP-verschlüsselte Informationen.

High-Level-MIP-SDK-Anwendungsfälle umfassen Folgendes:

- Eine Branchenanwendung, die Klassifizierungs Bezeichnungen auf Dateien im Export anwendet.

- Eine CAD/CAM-Design Anwendung, die systemeigene Unterstützung für MIP-Beschriftungen bereitstellt.

- Ein Cloud Access-Sicherheits Broker oder eine Lösung zur Verhinderung von Datenverlusten, die Daten mit Azure Information Protection verschlüsseln kann.

Weitere Informationen zum MIP-SDK, Voraussetzungen, zusätzlichen Szenarien und Beispielen finden Sie unter [MIP SDK Overview](https://docs.microsoft.com/information-protection/develop/overview).

### <a name="microsoft-graph-api-for-teams-dlp"></a>Microsoft Graph-API für Teams DLP

Die Funktionen zur [Verhinderung von Datenverlust (Data Loss Prevention, DLP)](dlp-microsoft-teams.md) werden in Microsoft Teams häufig verwendet, zumal sich Organisationen zu Remote Arbeit verschoben haben. Anfang dieses Jahres haben wir [die öffentliche Vorschau](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) der Microsoft Graph-Änderungs Benachrichtigungs-API für Nachrichten in Teams angekündigt. Mit dieser API können Entwickler apps erstellen, die Microsoft Teams-Nachrichten in nahezu Echtzeit abhören und dann DLP-Szenarien für Kunden und Partner implementieren. Darüber hinaus können Sie mit der Microsoft Graph-Patch-API DLP-Aktionen auf Teams-Nachrichten anwenden.

Diese beiden APIs bilden die Microsoft Graph-API für Teams DLP. Sie können zunächst die [Beispiel-App](https://github.com/microsoftgraph/csharp-webhook-with-resource-data)ausprobieren. Weitere Informationen zu Microsoft Teams-Messaging-webhooks finden Sie in der [Dokumentation](https://docs.microsoft.com/graph/api/subscription-post-subscriptions).

Die Lizenzierungsanforderungen für Teams DLP finden Sie unter [Microsoft 365-Lizenzierungsrichtlinien für Sicherheits & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>Microsoft Graph-API für eDiscovery (Vorschau)

Mit [Advanced eDiscovery](overview-ediscovery-20.md)können Organisationen Daten ermitteln, in denen Sie leben, und Verwalten von mehr End-to-End-eDiscovery-Workflows mit intelligenten Funktionen für Maschinelles Lernen und Analyse, um Daten auf den relevanten Datensatz zu reduzieren, während die Daten innerhalb der Microsoft 365-Sicherheits-und-Kompatibilitäts Grenze bleiben.

Graph-APIs für Advanced eDiscovery können zum Erstellen und Verwalten von Fällen, zum Überprüfen von Sätzen und zum Überprüfen von Set-Abfragen in skalierbarer und wiederholbarer Weise verwendet werden. So können Kunden und Partner apps und Workflows erstellen, um häufige und sich wiederholende Prozesse wie das Erstellen von Fällen und das Verwalten von Depotbanken und rechtlichen Aufbewahrungen zu automatisieren.

Die erste Gruppe von Graph-APIs für eDiscovery steht in der öffentlichen Vorschau zur Verfügung. Wir planen, bis zum Ende des Kalenderjahres weitere Funktionen hinzuzufügen. Weitere Informationen zu diesen APIs und anderen Updates für Advanced eDiscovery finden Sie in diesem [Blog](https://aka.ms/Ignite2020AeDAA).

Die Lizenzierungsanforderungen für Advanced eDiscovery und die API finden Sie im Abschnitt "eDiscovery" im [Microsoft 365-Lizenzierungs Handbuch für Sicherheits & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery).

### <a name="microsoft-graph-api-for-teams-export-preview"></a>Microsoft Graph-API für Teams-Export (Vorschau)

Enterprise Information Archiving (UVP) for Microsoft Teams ist ein wichtiges Szenario für unsere Kunden, da es Ihnen die Lösung für regulatorische Anforderungen ermöglicht. Zusätzlich zu den integrierten Funktionen für die Archivierung von Inhalten in Microsoft Teams können Kunden und Partner nun Teams-Export-APIs verwenden, um benutzerdefinierte Anwendungs-und Integrationsszenarien zu lösen. Die Teams-Export-APIs unterstützen den Massenexport (bis zu 200 Anforderungen pro Sekunde/pro App/pro Mandanten) von Microsoft Teams-Nachrichten und Nachrichtenanlagen. Auf gelöschte Nachrichten kann die API auch bis zu 30 Tage nach dem Löschen zugreifen. Weitere Informationen zu diesen Teams-Export-APIs und deren Verwendung in Ihren Anwendungen finden Sie unter [Exportieren von Inhalten mit Microsoft Teams Export-APIs](https://docs.microsoft.com/microsoftteams/export-teams-content).

Die Lizenzierungsanforderungen für die Verwendung der Teams-Export-APIs finden Sie unter [Microsoft 365 Licensing Guidance for Security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).
