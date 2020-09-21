---
title: Microsoft 365 Netzwerkbewertung (Vorschau)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
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
ms.openlocfilehash: 21fb9515ea1621225cffbe23fe87d0daeb5265de
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104546"
---
# <a name="microsoft-365-network-assessment-preview"></a>Microsoft 365 Netzwerkbewertung (Vorschau)

In der Netzwerkkonnektivität des Microsoft 365 admin Centers destillieren **Netzwerkbewertungen** ein Aggregat zahlreicher Netzwerk Leistungs Metriken in einer Momentaufnahme ihrer Umkreis Integrität des Unternehmensnetzwerks, dargestellt durch einen Points-Wert von 0-100. Bei einer Netzwerkbewertung erfahren Sie, wie stark sich der Netzwerkentwurf des Kunden auf Office 365 Benutzererfahrung auswirkt. Netzwerkbewertungen sind sowohl für den gesamten Mandanten als auch für jeden geografischen Standort ausgelegt, von dem aus Benutzer eine Verbindung mit Ihrem Mandanten herstellen, sodass Microsoft 365-Administratoren eine einfache Möglichkeit haben, eine Gestalt der Netzwerkintegrität des Unternehmens sofort zu erfassen und schnell einen detaillierten Bericht für einen beliebigen globalen Office-Standort aufzurufen.

Der Wert "Netzwerk Bewertungspunkte" ist ein Durchschnitt der TCP-Wartezeit, der Downloadgeschwindigkeit und der Qualitäts Metriken für die UDP-Verbindung, die einmal pro Tag kompiliert wurden. Leistungs Metriken für in Microsoft befindliche Netzwerke werden von diesen Messungen ausgeschlossen, um sicherzustellen, dass die Bewertungsergebnisse eindeutig und für das Unternehmensnetzwerk spezifisch sind.

![Netzwerk Bewertungs Wert](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Ein sehr niedriger Netzwerk Bewertungs Wert deutet darauf hin, dass Microsoft 365-Clients erhebliche Probleme beim Herstellen einer Verbindung mit dem Mandanten oder beim aufrecht erhalten einer reaktionsfähigen Benutzeroberfläche haben, während ein hoher Wert ein ordnungsgemäß konfiguriertes Netzwerk mit einigen fortlaufenden Leistungsproblemen angibt. Ein Wert von 80% stellt eine gesunde Basislinie dar, bei der nicht erwartet werden soll, dass reguläre Benutzer Beschwerden über die Microsoft 365-Konnektivität oder die Reaktionsfähigkeit aufgrund der Netzwerkleistung empfangen werden. Wenn die Verbesserungen für eine iterative Netzwerkkonnektivität vorgenommen werden, steigt dieser Wert zusammen mit der Benutzeroberfläche.

| Netzwerkbewertung | Erwartete Benutzeroberfläche |
| :----------------- | :----------------------- |
| 100                | Optimal                     |
| 80                 | Erfüllt Empfehlungen    |
| 60                 | Annehmbar               |
| 40                 | Benutzer können Probleme auftreten |
| 20                 | Benutzer können sich beschweren       |
| 0                  | Netzwerkprobleme ein allgemeines Diskussionsthema |

>[!IMPORTANT]
>Netzwerk Einblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und stehen nur für Microsoft 365-Mandanten zur Verfügung, die im Feature Preview-Programm registriert wurden.

## <a name="network-assessment-panel"></a>Netzwerk Bewertungsbereich

Bei jeder Netzwerkbewertung, unabhängig davon, ob Sie auf den Mandanten oder einen bestimmten Standort beschränkt ist, wird ein Bereich mit Details zur Bewertung angezeigt. Dieses Panel zeigt ein Balkendiagramm der Bewertung sowohl als Prozentsatz als auch als Gesamtpunktzahl für jede Arbeitsauslastung der Komponente einschließlich der Arbeitslasten, bei denen Messdaten empfangen wurden. Für eine Bewertung des Office-Standortnetzwerks zeigen wir auch einen Vergleich mit dem Prozentsatz von Microsoft 365-Kunden in jedem der fünf Quintiles an, die Daten in derselben Stadt wie Ihr Bürostandort gemeldet haben.

![Beispiel für einen Netzwerk Bewertungs Wert](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

Der **Bewertungs Aufschlüsselung** im Bereich zeigt die Bewertung für jede der Komponenten Arbeitsauslastungen.

Der **Bewertungsverlauf** zeigt die letzten 30 Tage der Bewertung und die Benchmark an. Sie können auch über die Registerkarte Verlauf bis zu zwei Jahre über den Metriken-Verlauf für alle Office-Standorte Berichten. Auf der Registerkarte Verlauf können Sie Ihre Attribute auswählen und einen Berichtszeit Rahmen auswählen, um die Auswirkungen eines Netzwerk aktualisierungsprojekts hervorzuheben und die Verbesserung ihrer Netzwerkbewertung zu sehen.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Assessments für Mandanten Netzwerke und Netzwerkbewertungen für Office-Standorte

Eine Netzwerkbewertung misst den Entwurf des Netzwerkperimeters eines Office-Standorts für das Microsoft-Netzwerk. Verbesserungen am Netzwerkperimeter werden am besten an jedem Office-Standort vorgenommen.

Wir zeigen einen Netzwerk Bewertungs Wert für den gesamten Microsoft 365-Mandanten auf der Seite Netzwerk Leistungsübersicht an, bei der es sich um einen gewichteten Durchschnitt der Netzwerkbewertungen für alle Office-Standorte handelt. Es gibt auch einen bestimmten Netzwerk Bewertungs Wert für jeden erkannten Office-Standort auf der Zusammenfassungsseite dieses Standorts.

## <a name="exchange-online"></a>Exchange Online

Für Exchange Online wird die TCP-Wartezeit vom Clientcomputer zur Exchange-Dienst Haustür gemessen. Dies kann durch die Entfernung beeinträchtigt werden, über die das Netzwerk über die Kunden LAN und WAN reist. Es kann auch durch Netzwerk-zwischengeschaltete Geräte oder Dienste beeinträchtigt werden, die die Konnektivität verzögern oder dazu führen, dass Pakete erneut gesendet werden. Und es wird dadurch beeinflusst, wie weit entfernt die nächste Exchange-Dienst-Haustür ist. Der Median (auch als 50-Perzentil-oder P50-Measure bezeichnet) wird für alle Messungen in den vorherigen drei Tagen verwendet.

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

Für SharePoint Online wird die Downloadgeschwindigkeit gemessen, die ein Benutzer für den Zugriff auf ein Dokument von SharePoint oder OneDrive zur Verfügung stellt. Dies kann durch die verfügbare Bandbreite zwischen dem Clientcomputer und dem Netzwerk von Microsoft auf Netzwerk Schaltkreisen beeinträchtigt werden. Es wird auch häufig von Netzwerküberlastung beeinflusst, die in Engpässen bei komplexen Netzwerkgeräten oder in schlechten WLAN-Abdeckungsbereichen vorhanden ist. Die Downloadgeschwindigkeit wird in Megabyte pro Sekunde gemessen, bei dem es sich um etwa einen Zehntel einer Schaltung mit Megabit pro Sekunde handelt. Die Einheit Megabyte pro Sekunde ist hilfreich, da Sie direkt sehen können, welche Größe Datei in 1 Sekunde heruntergeladen werden kann. Das 25. Perzentil (auch als P25-Measure bezeichnet) wird für alle Messungen in den vorherigen drei Tagen übernommen. Dieses 25. Perzentil hilft, die Auswirkungen unterschiedlicher Überlastung im Laufe der Zeit zu verringern.

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

Wir berechnen eine mittlere Meinungs Bewertung aus diesen UDP-Messungen für eine Skala von 1 bis 5. Anschließend ordnen wir dies der 0-100 Points-Skala für die Microsoft Teams-Netzwerkbewertung zu.  Insgesamt gut ist über 87,5 Punkte und insgesamt schlecht liegt unter 50 Punkte.

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Performance Insights (Vorschau)](office-365-network-mac-perf-insights.md)

[Microsoft 365 Connectivity Test im M365 Admin Center (Vorschau)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (Vorschau)](office-365-network-mac-location-services.md)

[Microsoft 365 Network Connectivity Test Tool (Vorschau)](office-365-network-mac-perf-onboarding-tool.md)
