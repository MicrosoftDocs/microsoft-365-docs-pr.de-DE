---
title: Microsoft 365 Netzwerkbewertung
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Netzwerkbewertung
ms.openlocfilehash: c09e34b1bc3a8bf0f82a4a1e3c72e67f320abd43
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470474"
---
# <a name="microsoft-365-network-assessment"></a>Microsoft 365 Netzwerkbewertung

In der Microsoft 365 Admin Center werden durch  Netzwerkbewertungen viele Metriken für die Netzwerkleistung zu einer Momentaufnahme des Unternehmensnetzwerkperimeterzustands zusammengefasst. Bei einer Netzwerkbewertung erfahren Sie, wie stark sich der verantwortliche Netzwerkentwurf des Kunden auf die Office 365 aus wirkt. Netzwerkbewertungen sind sowohl auf den gesamten Mandanten als auch auf jeden geografischen Standort begrenzt, von dem aus Benutzer eine Verbindung mit Ihrem Mandanten herstellen. Die Bewertungen bieten Microsoft 365 Administratoren eine einfache Möglichkeit, sofort einen Einblick in den Netzwerkzustand des Unternehmens zu erhalten und schnell einen detaillierten Bericht für jeden globalen Bürostandort zu erstellen.

Der Wert der Netzwerkbewertungspunkte liegt zwischen 0 und 100 und ist ein Durchschnitt von TCP-Latenz, Downloadgeschwindigkeit und UdP-Verbindungsqualitätsmetriken. Diese Metriken werden einmal am Tag kompiliert. Leistungsmetriken für Microsoft-eigene Netzwerke werden von diesen Messungen ausgeschlossen, um sicherzustellen, dass die Bewertungsergebnisse eindeutig und für das Unternehmensnetzwerk spezifisch sind.

> [!div class="mx-imgBorder"]
> ![Netzwerkbewertungswert](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Ein sehr niedriger Netzwerkbewertungswert legt nahe, Microsoft 365 Clients erhebliche Probleme haben, eine Verbindung mit dem Mandanten zu herstellen oder eine reaktionsfähige Benutzererfahrung zu erhalten. Ein hoher Wert weist auf ein ordnungsgemäß konfiguriertes Netzwerk mit wenigen laufenden Leistungsproblemen hin. Ein Wert von 80 % stellt eine fehlerfreie Basislinie dar, über der Sie aufgrund der Netzwerkleistung keine regelmäßigen Benutzerbeschwerden über Microsoft 365 oder Reaktionsfähigkeit erwarten sollten. Wenn iterative Netzwerkkonnektivität verbessert wird, wird dieser Wert zusammen mit der Benutzeroberfläche zunehmen.

| Netzwerkbewertung | Erwartete Benutzererfahrung |
| :----------------- | :----------------------- |
| 100                | Optimal                     |
| 80                 | Erfüllt Empfehlungen    |
| 60                 | Annehmbar               |
| 40                 | Bei Benutzern können Probleme auftreten |
| 20                 | Benutzer können sich beschweren       |
| 0                  | Netzwerkprobleme ein häufiges Diskussionsthema |

>[!IMPORTANT]
>Netzwerkeinblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und sind nur für Microsoft 365-Mandanten verfügbar, die im Featurevorschauprogramm registriert wurden.

## <a name="network-assessment-panel"></a>Netzwerkbewertungspanel

Jede Netzwerkbewertung, unabhängig davon, ob sie auf den Mandanten oder einen bestimmten Bürostandort begrenzt ist, zeigt ein Panel mit Details zur Bewertung an. Dieses Panel zeigt ein Balkendiagramm der Bewertung sowohl als Prozentsatz als auch als Gesamtpunkte für jede Komponentenarbeitsauslastung, einschließlich nur Arbeitsauslastungen, bei denen Messdaten empfangen wurden. Für eine Bewertung des Office-Standortnetzwerks zeigen wir auch einen Vergleich mit dem Prozent der Microsoft 365-Kunden in jedem von fünf Fünftilen, die Daten in derselben Stadt wie Ihren Bürostandort gemeldet haben.

> [!div class="mx-imgBorder"]
> ![Beispielwert für die Netzwerkbewertung](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

Die **Bewertungsaufschlüsselung** im Panel zeigt die Bewertung für die einzelnen Komponentenworkloads an.

Der **Bewertungsverlauf** zeigt die letzten 30 Tage der Bewertung und den Benchmark an. Sie können auch den Metrikverlauf für jeden Beliebigen Bürostandort für bis zu zwei Jahre mithilfe der Registerkarte Verlauf melden. Auf der Registerkarte Verlauf können Sie die Attribute auswählen, für die Bericht angezeigt werden soll. Wenn Sie einen Berichtzeitrahmen auswählen, können Sie die Auswirkungen eines Netzwerkupdateprojekts hervorheben und die Verbesserung Ihrer Netzwerkbewertung sehen.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Mandantennetzwerkbewertungen und Office Location Network Assessments

Eine Netzwerkbewertung misst den Entwurf des Netzwerkperimeters eines Bürostandorts für das Netzwerk von Microsoft. Verbesserungen am Netzwerkperimeter sind am besten an jedem Bürostandort möglich.

Wir zeigen auf der Seite Netzwerkleistungsübersicht einen Netzwerkbewertungswert für den Microsoft 365 Mandanten an. Dieser Wert ist ein gewichteter Durchschnitt der Netzwerkbewertungen für alle Bürostandorte. Es gibt auch einen bestimmten Netzwerkbewertungswert für jeden erkannten Bürostandort auf der Zusammenfassungsseite dieses Standorts.

## <a name="exchange-online"></a>Exchange Online

Bei Exchange Online wird die TCP-Latenz vom Clientcomputer zum Exchange-Fronttür gemessen. Diese Wartezeit kann durch den Abstand des Netzwerks über das LAN und wan der Kunden betroffen sein. Dies kann auch von netzwerkvermittlern Geräten oder Diensten betroffen sein, die die Konnektivität verzögern oder das Senden von Paketen verursachen. Und dies ist davon betroffen, wie weit sich die nächste Exchange der Eingangstür befindet. Der Median (auch bekannt als 50. Perzentil oder P50-Maß) wird für alle Messungen in den vorherigen drei Tagen verwendet.

Die Exchange Online wird mithilfe der folgenden Tabelle vorgenommen. Jeder TCP-Latenznummer zwischen den Schwellenwerten werden Lineare Punkte innerhalb des Bandes zugewiesen.

| TCP-Latenz   | Points |
| :------------ | :----- |
| 10 ms oder weniger  | 100    |
| 25 ms          | 80     |
| 100 ms         | 60     |
| 200 ms         | 40     |
| 300 ms         | 20     |
| 350 ms oder mehr | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

Für SharePoint Online wird die Downloadgeschwindigkeit gemessen, mit der ein Benutzer auf ein Dokument SharePoint oder OneDrive kann. Dies kann von der Bandbreite betroffen sein, die auf Netzwerkschaltungen zwischen dem Clientcomputer und dem Netzwerk von Microsoft verfügbar ist. Dies wird auch häufig durch Netzwerküberlastungen verursacht, die in Engpässen in komplexen Netzwerkgeräten oder bei schlechter Abdeckung in Wi-Fi sind. Die Downloadgeschwindigkeit wird in Megabyte pro Sekunde gemessen, was ungefähr einem Zehntel einer Schaltung entspricht, die als Megabit pro Sekunde bewertet wird. Das MegaByte pro Sekunde ist hilfreich, da Sie direkt sehen können, welche Dateigröße in 1 Sekunde heruntergeladen werden kann. Das 25. Perzentil (auch als P25-Maß bezeichnet) wird für alle Messungen in den letzten drei Tagen verwendet. Dieses 25. Perzentil trägt dazu bei, die Auswirkungen unterschiedlicher Überlastungen im Laufe der Zeit zu reduzieren.

Die SharePoint Online-Bewertung erfolgt mithilfe der folgenden Tabelle. Jeder Downloadgeschwindigkeitsnummer zwischen den Schwellenwerten werden Lineare Punkte innerhalb des Bandes zugewiesen.

| Downloadgeschwindigkeit | Points |
| :------------- | :----- |
| 20 MBps oder mehr | 100    |
| 14 MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 20     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Für Microsoft Teams wird die Netzwerkqualität als UDP-Latenz, UDP-Jitter und UDP-Paketverlust gemessen. UDP wird für die Audio- und Videomedienkonnektivität von Anrufen und Konferenzen für Microsoft Teams. Dies kann durch dieselben Faktoren wie für Wartezeit und Downloadgeschwindigkeit zusätzlich zu Verbindungslücken in der UDP-Unterstützung eines Netzwerks beeinflusst werden, da UDP separat für das gängigere TCP-Protokoll konfiguriert ist. Der Median (auch bekannt als 50. Perzentil oder P50-Maß) wird für alle Messungen in den vorherigen drei Tagen verwendet. 

Aus diesen UDP-Messungen wird für eine Skala von 1 bis 5 eine mittlere Meinungswertung berechnet. Anschließend ordnen wir dies der Skalierung von 0 bis 100 Punkt für die Microsoft Teams zu.  Insgesamt gut ist über 87,5 Punkte und insgesamt schlecht ist unter 50 Punkt.

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Einblicke in die Netzwerkleistung (Vorschau)](office-365-network-mac-perf-insights.md)

[Microsoft 365 Netzwerkverbindungstesttool (Vorschau)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (Vorschau)](office-365-network-mac-location-services.md)
