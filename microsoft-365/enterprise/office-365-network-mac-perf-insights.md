---
title: Microsoft 365 Network Insights
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
description: Microsoft 365 Network Insights
ms.openlocfilehash: 10b1c66a8f9aae555c2841b2b290f341bec3c7ec
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470556"
---
# <a name="microsoft-365-network-insights"></a>Microsoft 365 Network Insights

**Netzwerkeinblicke** sind Leistungsmetriken, die von Ihrem mandanten Microsoft 365 erfasst werden und nur von administrativen Benutzern in Ihrem Mandanten angezeigt werden können. Einblicke werden im Microsoft 365 Admin Center unter <https://portal.microsoft.com/adminportal/home#/networkperformance> angezeigt.

Einblicke sollen beim Entwerfen von Netzwerkperimetern für Ihre Bürostandorte helfen. Jeder Einblick enthält Livedetails zu den Leistungsmerkmalen für ein bestimmtes häufiges Problem für jeden geografischen Standort, an dem Benutzer auf Ihren Mandanten zugreifen.

Es gibt sechs spezifische Netzwerkeinblicke, die für jeden Bürostandort angezeigt werden können:

- [Backhauled network egress](#backhauled-network-egress)
- [Netzwerkvermittlergerät](#network-intermediary-device)
- [Bessere Leistung für Kunden in Ihrer Nähe erkannt](#better-performance-detected-for-customers-near-you)
- [Verwenden einer nicht optimalen Exchange Online-Service-Eingangstür](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Verwenden einer nicht optimalen SharePoint Onlinedienst-Eingangstür](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Niedrige Downloadgeschwindigkeit SharePoint Eingangstür](#low-download-speed-from-sharepoint-front-door)
- [Optimaler Netzwerk-Abgress für China-Benutzer](#china-user-optimal-network-egress)

Es gibt zwei Netzwerkeinblicke auf Mandantenebene, die für den Mandanten angezeigt werden können. Diese werden auch auf den Seiten für Produktivitätsergebnis angezeigt:

- [Exchange verbindungen, die von Konnektivitätsproblemen betroffen sind](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [SharePoint von Konnektivitätsproblemen betroffener Beispielverbindungen](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Netzwerkeinblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und sind nur für Microsoft 365-Mandanten verfügbar, die im Featurevorschauprogramm registriert wurden.

## <a name="backhauled-network-egress"></a>Backhauled network egress

Diese Einsicht wird angezeigt, wenn der Netzwerkeinblickdienst erkennt, dass der Abstand zwischen einem bestimmten Benutzerstandort und dem Netzwerkeinsprung größer als 800 Kilometer ist, was darauf hinweist, dass Microsoft 365-Datenverkehr zu einem gängigen Internet-Edgegerät oder -proxy zurückgehauen wird.

Diese Einsicht wird in einigen Zusammenfassungsansichten Egress als "Egress" abgekürzt.

> [!div class="mx-imgBorder"]
> ![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Szenario

Dies gibt an, dass der Abstand zwischen dem Bürostandort und dem Netzwerkress mehr als 800 Kilometer beträgt. Der Bürostandort wird durch einen verschleierten Clientcomputerspeicherort identifiziert, und der Netzwerk-Ausgangsspeicherort wird mithilfe der Reverse-IP-Adresse für Standortdatenbanken identifiziert. Der Bürostandort kann ungenau sein, Windows Standortdienste auf Computern deaktiviert sind. Der Standort des Netzwerk-Ausgangs kann ungenau sein, wenn die Reverse-IP-Adressdatenbankinformationen ungenau sind.

Details für diese Einblicke umfassen den Standort des Büros, den geschätzten Prozentsatz des gesamten Mandantenbenutzers am Standort, den aktuellen Standort für den Netzwerkbezug, die Relevanz des Ausgangsstandorts, den Abstand zwischen dem Standort und dem aktuellen Ausgangspunkt, das Datum, an dem die Bedingung zum ersten Mal erkannt wurde, und das Datum, an dem die Bedingung aufgelöst wurde.

### <a name="what-should-i-do"></a>Was soll ich machen?

Für diesen Einblick empfehlen wir, dass das Netzwerk näher an den Bürostandort rückt, damit die Konnektivität optimal zum globalen Netzwerk von Microsoft und zur nächsten Microsoft 365-Service-Eingangstüre geroutet werden kann. Die Enge des Netzwerkeinschlusses zu den Bürostandorten der Benutzer ermöglicht auch in Zukunft eine verbesserte Leistung, da Microsoft sowohl Netzwerkstandorte als auch Microsoft 365-Fronttüren erweitert.

Weitere Informationen zum Beheben dieses Problems finden Sie unter [Egress netzwerkverbindungen lokal](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="network-intermediary-device"></a>Netzwerkvermittlergerät

Diese Einsicht wird angezeigt, wenn wir Geräte zwischen Ihren Benutzern und dem Netzwerk von Microsoft erkannt haben, die sich auf die Office 365 auswirken können. Es wird empfohlen, diese für bestimmte Netzwerkdatenverkehr Microsoft 365, der für Microsoft-Rechenzentren bestimmt ist, zu umgehen. Diese Empfehlung wird zusätzlich unter Microsoft 365 [Network Connectivity Principles beschrieben.](microsoft-365-network-connectivity-principles.md) 

Eine der Erkenntnisse des Netzwerkvermittlers ist die SSL-Unterbrechung und -Überprüfung, wenn kritische Office 365 Netzwerkendpunkte für Exchange, SharePoint und Teams von netzwerkvermittlern Geräten abgefangen und entschlüsselt werden.

### <a name="what-does-this-mean"></a>Szenario

Netzwerkvermittlergeräte wie Proxyserver, VPNs und Verhinderung von Datenverlust können sich auf die Leistung und Stabilität Microsoft 365 Clients auswirken, auf denen Datenverkehr zwischengeschaltet wird.

### <a name="what-should-i-do"></a>Was soll ich machen?

Konfigurieren Sie das netzwerkvermittlere Gerät, das erkannt wurde, um die Verarbeitung für Microsoft 365 zu umgehen.

## <a name="better-performance-detected-for-customers-near-you"></a>Bessere Leistung für Kunden in Ihrer Nähe erkannt

Diese Einsicht wird angezeigt, wenn der Netzwerk-Einblicke-Dienst erkennt, dass eine erhebliche Anzahl von Kunden in Ihrem U-Bahn-Bereich eine bessere Leistung als Benutzer in Ihrer Organisation an diesem Bürostandort hat.

Diese Einsicht wird in einigen Zusammenfassungsansichten als "Peers" abgekürzt.

> [!div class="mx-imgBorder"]
> ![Relative Netzwerkleistung](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Szenario

Dieser Einblick untersucht die Gesamtleistung Microsoft 365 Kunden in derselben Stadt wie dieser Bürostandort. Diese Einsicht wird angezeigt, wenn die durchschnittliche Wartezeit Ihrer Benutzer um 10 % größer ist als die durchschnittliche Latenz der benachbarten Mandanten.

### <a name="what-should-i-do"></a>Was soll ich machen?

Es kann viele Gründe für diese Bedingung geben, z. B. Wartezeiten in Ihrem Unternehmensnetzwerk oder Internetdienstanbieter, Engpässe oder Architekturdesignprobleme. Untersuchen Sie die Wartezeit zwischen jedem Hop in der Route zwischen Ihrem Büronetzwerk und dem Microsoft 365 Eingangstür. Weitere Informationen finden Sie unter [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Verwenden einer nicht optimalen Exchange Online-Service-Eingangstür

Diese Einsicht wird angezeigt, wenn der Netzwerk-Einblicke-Dienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit einer optimalen Exchange Online herstellen.

Diese Einsicht wird in einigen Zusammenfassungsansichten als "Routing" abgekürzt.

> [!div class="mx-imgBorder"]
> ![Nicht optimale EXO-Fronttür](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Szenario

Wir listet Exchange Online,die für die Verwendung aus der Bürostandortstadt mit guter Leistung geeignet sind. Wenn der aktuelle Test die Verwendung eines Exchange Online, der nicht in dieser Liste enthalten ist, wird diese Empfehlung angezeigt.

### <a name="what-should-i-do"></a>Was soll ich machen?

Die Verwendung einer nicht optimalen Exchange Online-Fronttür des Diensts kann durch netzwerk backhaul verursacht werden, bevor das Unternehmensnetzwerk abfresst. In diesem Fall wird der lokale und direkte Netzwerkeinschwung empfohlen. Dies kann auch durch die Verwendung eines Remote-DNS-Recursive Resolver-Servers verursacht werden. In diesem Fall wird empfohlen, den DNS-Rekursiven Resolver-Server am Netzwerkress auszurichten.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Verwenden einer nicht optimalen SharePoint Onlinedienst-Eingangstür

Diese Einsicht wird angezeigt, wenn der Netzwerkeinblickdienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit der SharePoint Onlinedienst-Eingangstür herstellen.

Diese Einsicht wird in einigen Zusammenfassungsansichten als "Afd" abgekürzt.

> [!div class="mx-imgBorder"]
> ![Nicht optimale SPO-Eingangstür](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Szenario

Wir identifizieren die SharePoint Onlinedienst-Eingangstür, mit der der Testclient eine Verbindung herstellen soll. Anschließend vergleichen wir dies für die Bürostandortstadt mit der erwarteten SharePoint Online-Service-Eingangstür für diese Stadt. Wenn sie nicht übereinstimmen, wird diese Empfehlung empfohlen.

### <a name="what-should-i-do"></a>Was soll ich machen?

Die Verwendung einer nicht optimalen SharePoint Online-Dienst-Eingangstür könnte durch Netzwerkhull vor dem Unternehmensnetzwerkeinziehen verursacht werden. In diesem Fall wird der lokale und direkte Netzwerkeinschwung empfohlen. Dies kann auch durch die Verwendung eines Remote-DNS-Recursive Resolver-Servers verursacht werden. In diesem Fall wird empfohlen, den DNS-Rekursiven Resolver-Server am Netzwerkress auszurichten.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Niedrige Downloadgeschwindigkeit SharePoint Eingangstür

Diese Einsicht wird angezeigt, wenn der Netzwerkeinblickdienst erkennt, dass die Bandbreite zwischen dem jeweiligen Bürostandort und SharePoint Online kleiner als 1 MBps ist.

Diese Einsicht wird in einigen Zusammenfassungsansichten als "Durchsatz" abgekürzt.

### <a name="what-does-this-mean"></a>Szenario

Die Downloadgeschwindigkeit, die ein Benutzer von SharePoint Online- und OneDrive for Business-Service-Eingangstüren erhalten kann, wird in Megabyte pro Sekunde (MBps) gemessen. Wenn dieser Wert kleiner als 1 MBps ist, geben wir diese Einsicht.

### <a name="what-should-i-do"></a>Was soll ich machen?

Um die Downloadgeschwindigkeit zu verbessern, muss möglicherweise die Bandbreite erhöht werden. Alternativ kann es zu Netzwerküberlastungen zwischen Denkautomaten am Bürostandort und der SharePoint Onlinedienst-Eingangstür kommen. Dies wird manchmal als verlustreich bezeichnet und schränkt die Downloadgeschwindigkeit ein, die Benutzern zur Verfügung steht, auch wenn genügend Bandbreite verfügbar ist.

## <a name="china-user-optimal-network-egress"></a>Optimaler Netzwerk-Abgress für China-Benutzer

Dieser Einblick wird angezeigt, wenn Ihre Organisation Benutzer in China hat, die eine Verbindung zu Microsoft 365 an anderen geografischen Standorten herstellen. 

### <a name="what-does-this-mean"></a>Szenario

Wenn Ihre Organisation über private WAN-Verbindungen verfügt, wird empfohlen, eine Netzwerk-WAN-Schaltung von Ihren Bürostandorten in China aus zu konfigurieren, die an einem der folgenden Speicherorte über eine Netzwerkverbindung zum Internet verfügen:

- Hongkong
- Japan
- Taiwan
- Südkorea
- Singapur
- Malaysia

Der Internetaustritt von Benutzern als diese Standorte führt zu leistungsbehinderndern, und ein Austritt in China kann aufgrund der grenzüberschreitenden Überlastung zu hohen Wartezeiten und Konnektivitätsproblemen führen.

### <a name="what-should-i-do"></a>Was soll ich machen?

Weitere Informationen zum Beheben von Leistungsproblemen im Zusammenhang mit dieser Einsicht finden Sie unter Microsoft 365 optimierung der globalen Mandantenleistung [für Chinesische Benutzer](microsoft-365-networking-china.md).

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Exchange verbindungen, die von Konnektivitätsproblemen betroffen sind

Diese Einsicht zeigt, wann 50 % oder mehr der in der Stichprobe verwendeten Verbindungen betroffen sind. Die Auswirkung wird durch die Exchange, die für jede Stichprobe unter 60 % liegt.

### <a name="what-does-this-mean"></a>Szenario

Dies ist ein Hinweis darauf, dass bei der Mehrzahl der Benutzer Probleme mit der Benutzererfahrung auftreten, wenn Outlook Verbindung mit Exchange Online. Der Prozentsatz der Stichproben stellt wahrscheinlich den Prozentsatz der Benutzer dar, die unter 60 Punkt angezeigt werden.  

### <a name="what-should-i-do"></a>Was soll ich machen?

Aktivieren Sie die Sichtbarkeit der Netzwerkkonnektivität für Office-Standorte, wenn Sie dies noch nicht getan haben. Sie möchten ermitteln, welche Büros von einer schlechten Netzwerkkonnektivität betroffen sind, die sich auf Exchange auswirken, und nach Möglichkeiten suchen, um den Netzwerkperimeter zu verbessern, der die Benutzer mit dem Netzwerk von Microsoft verbindet.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>SharePoint von Konnektivitätsproblemen betroffener Beispielverbindungen

Diese Einsicht zeigt, wann 50 % oder mehr der in der Stichprobe verwendeten Verbindungen betroffen sind. Die Auswirkung wird durch die SharePoint, die für jede Stichprobe unter 40 % liegt.

### <a name="what-does-this-mean"></a>Szenario

Dies ist ein Hinweis darauf, dass bei der Mehrzahl Ihrer Benutzer wahrscheinlich Probleme mit der Benutzererfahrung SharePoint und OneDrive. Der Prozentsatz der Stichproben stellt wahrscheinlich den Prozentsatz der Benutzer dar, die unter 40 Punkt angezeigt werden.  

### <a name="what-should-i-do"></a>Was soll ich machen?

Aktivieren Sie die Sichtbarkeit der Netzwerkkonnektivität für Office-Standorte, wenn Sie dies noch nicht getan haben. Sie möchten ermitteln, welche Büros von einer schlechten Netzwerkkonnektivität betroffen sind, die sich auf SharePoint auswirken, und nach Möglichkeiten suchen, um den Netzwerkperimeter zu verbessern, der die Benutzer mit dem Netzwerk von Microsoft verbindet.

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Netzwerkbewertung (Vorschau)](office-365-network-mac-perf-score.md)

[Microsoft 365 Netzwerkverbindungstesttool (Vorschau)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (Vorschau)](office-365-network-mac-location-services.md)
