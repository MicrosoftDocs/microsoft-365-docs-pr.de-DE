---
title: Microsoft 365 Netzwerkbewertung (Vorschau)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Netzwerkbewertung (Vorschau)
ms.openlocfilehash: 15eb514980bb53bd32380e44b6bfa174670f6b85
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948316"
---
# <a name="microsoft-365-network-assessment-preview"></a>Microsoft 365 Netzwerkbewertung (Vorschau)

In der Microsoft 365 Admin Center-Verbindung mit der Microsoft 365-Seite wird mithilfe von **Netzwerkbewertungen** ein Aggregat zahlreicher Netzwerk Leistungs Metriken in einer Momentaufnahme ihres Umkreis-Integritätsstatus des Unternehmensnetzwerks, dargestellt durch einen Points-Wert von 0-100, destilliert. Netzwerkbewertungen sind sowohl für den gesamten Mandanten als auch für jeden geografischen Standort ausgelegt, von dem aus Benutzer eine Verbindung mit Ihrem Mandanten herstellen, sodass Microsoft 365-Administratoren eine einfache Möglichkeit haben, eine Gestalt der Netzwerkintegrität des Unternehmens sofort zu erfassen und schnell einen detaillierten Bericht für einen beliebigen globalen Office-Standort aufzurufen.

Der Wert Netzwerk Bewertungspunkte ist eine durchschnittliche Messung der TCP-Wartezeit, der Downloadgeschwindigkeit und der Qualitäts Metriken für die UDP-Verbindung, die bei der Anzeige Live kompiliert wurden. Leistungs Metriken für in Microsoft befindliche Netzwerke werden von diesen Messungen ausgeschlossen, um sicherzustellen, dass die Bewertungsergebnisse eindeutig und für das Unternehmensnetzwerk spezifisch sind.

![Netzwerk Bewertungs Wert](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Ein sehr niedriger Netzwerk Bewertungs Wert deutet darauf hin, dass Microsoft 365-Clients erhebliche Probleme beim Herstellen einer Verbindung mit dem Mandanten oder beim aufrecht erhalten einer reaktionsfähigen Benutzeroberfläche haben, während ein hoher Wert ein ordnungsgemäß konfiguriertes Netzwerk mit einigen fortlaufenden Leistungsproblemen angibt. Ein Wert von 80% stellt eine gesunde Basislinie dar, bei der nicht erwartet werden soll, dass reguläre Benutzer Beschwerden über die Microsoft 365-Konnektivität oder die Reaktionsfähigkeit aufgrund der Netzwerkleistung empfangen werden. Wenn die Verbesserungen für eine iterative Netzwerkkonnektivität vorgenommen werden, steigt dieser Wert zusammen mit der Benutzeroberfläche.

>[!IMPORTANT]
>Netzwerk Einblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und stehen nur für Microsoft 365-Mandanten zur Verfügung, die im Feature Preview-Programm registriert wurden.

## <a name="network-assessment-panel"></a>Netzwerk Bewertungsbereich

Bei jeder Netzwerkbewertung, unabhängig davon, ob Sie auf den Mandanten oder einen bestimmten Standort beschränkt ist, wird ein Bereich mit Details zur Bewertung angezeigt. Dieses Panel zeigt ein Balkendiagramm der Bewertung sowohl als Prozentsatz als auch als Gesamtpunktzahl für jede Arbeitsauslastung der Komponente einschließlich der Arbeitslasten, bei denen Messdaten empfangen wurden. Für eine Bewertung des Office-Standortnetzwerks zeigen wir auch einen Benchmark an, bei dem es sich um den Median aller Microsoft 365-Clients handelt, von denen Daten in derselben Stadt wie Ihr Bürostandort gemeldet wurden.

![Beispiel für einen Netzwerk Bewertungs Wert](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

Der **Bewertungs Aufschlüsselung** im Bereich zeigt die Bewertung für jede der Komponenten Arbeitsauslastungen.

Der **Bewertungsverlauf** zeigt die letzten 30 Tage der Bewertung und die Benchmark an. Sie können auch über die Registerkarte Verlauf bis zu zwei Jahre über den Metriken-Verlauf für alle Office-Standorte Berichten.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Assessments für Mandanten Netzwerke und Netzwerkbewertungen für Office-Standorte

Eine Netzwerkbewertung misst den Entwurf des Netzwerkperimeters eines Office-Standorts für das Microsoft-Netzwerk. Verbesserungen am Netzwerkperimeter werden am besten an jedem Office-Standort vorgenommen, oder wenn die Netzwerkkonnektivität aggregiert ist, können Verbesserungen auftreten, die sich auf mehrere Standorte auswirken.

Wir zeigen einen Wert für die Netzwerkbewertung für den gesamten Microsoft 365-Mandanten auf der Seite "Netzwerk Leistungsübersicht" und einen bestimmten Wert für jeden erkannten Office-Standort auf der Zusammenfassungsseite dieses Speicherorts an.

## <a name="exchange-online"></a>Exchange Online

Für Exchange Online wird die TCP-Wartezeit vom Clientcomputer auf den Exchange-Front-End-Server gemessen. Dies kann durch die Entfernung beeinträchtigt werden, über die das Netzwerk über die Kunden LAN und WAN reist. Es kann auch durch Netzwerk-zwischengeschaltete Geräte oder Dienste beeinträchtigt werden, die die Konnektivität verzögern oder dazu führen, dass Pakete erneut gesendet werden. Der Median (auch als 50-Perzentil-oder P50-Measure bezeichnet) wird für alle Messungen in den vorherigen drei Tagen verwendet.

Die Exchange Online Bewertung erfolgt anhand der folgenden Tabelle. Alle TCP-Latenz Nummern zwischen den Schwellenwerten werden linear innerhalb des Bands zugewiesen.

| TCP-Wartezeit   | Points |
| :------------ | :----- |
| 10ms oder niedriger  | 100    |
| 25ms          | 80     |
| 100 MS         | 60     |
| 200ms         | 40     |
| 300ms         | 20     |
| 350ms oder mehr | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

Für SharePoint Online wird die Downloadgeschwindigkeit gemessen, die ein Benutzer für den Zugriff auf ein Dokument über SharePoint Online oder OneDrive zur Verfügung stellt. Dies kann durch die verfügbare Bandbreite zwischen dem Clientcomputer und dem Netzwerk von Microsoft auf Netzwerk Schaltkreisen beeinträchtigt werden. Es wird auch häufig von Netzwerküberlastung beeinflusst, die in Engpässen bei komplexen Netzwerkgeräten oder in schlechten WLAN-Abdeckungsbereichen vorhanden ist. Die Downloadgeschwindigkeit wird in Megabyte pro Sekunde gemessen, bei dem es sich um etwa einen Zehntel einer Schaltung mit Megabit pro Sekunde handelt. Das 25. Perzentil (auch als P25-Measure bezeichnet) wird für alle Messungen in den vorherigen drei Tagen übernommen.

Die SharePoint Online Bewertung erfolgt anhand der folgenden Tabelle. Jede Download Geschwindigkeits Nummer zwischen den Schwellenwerten wird linear innerhalb des Bands zugewiesen.

| Download Geschwindigkeit | Points |
| :------------- | :----- |
| 20Mbps oder mehr | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2Mbps          | 20     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Für Microsoft Teams wird die Netzwerkqualität als UDP-Wartezeit, UDP-Jitter und UDP-Paketverlust gemessen. UDP wird für die Audio-und Video Medien Konnektivität für Anrufe und Konferenzen für Microsoft Teams verwendet. Dies kann durch die gleichen Faktoren wie Wartezeit und Downloadgeschwindigkeit sowie Verbindungs Lücken in der UDP-Unterstützung eines Netzwerks beeinträchtigt werden, da UDP separat mit dem häufigeren TCP-Protokoll konfiguriert wird. Der Median (auch als 50-Perzentil-oder P50-Measure bezeichnet) wird für alle Messungen in den vorherigen drei Tagen verwendet. 

Die Microsoft Teams-Bewertung erfolgt anhand der folgenden Tabelle. Alle drei UDP-Messungen müssen über dem angegebenen Schwellenwert liegen, um die angezeigten Punkte zu erreichen. Es gibt keine Bewertungen für einen einzelnen Standort innerhalb eines Bands.

| UDP-Paketverlust | UDP-Wartezeit | UDP-Jitter | Points |
| :-------------- | :---------- | :--------- | :----- |
| 0,25%           | 60ms        | 15ms       | 100    |
| 1,00%           | 120ms       | 40ms       | 80     |
| 1,50%           | 240ms       | 65ms       | 60     |
| 3,00%           | 275ms       | 80ms       | 40     |
| 5,00%           | 350ms       | 150ms      | 20     |
| Höher      | Höher  | Höher | 0      |

## <a name="related-topics"></a>Verwandte Themen

[Empfehlungen zur Netzwerkleistung im Microsoft 365 Admin Center (Vorschau)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Performance Insights (Vorschau)](office-365-network-mac-perf-insights.md)

[Microsoft 365 Connectivity Test im M365 Admin Center (Vorschau)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (Vorschau)](office-365-network-mac-location-services.md)
