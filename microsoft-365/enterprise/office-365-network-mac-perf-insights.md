---
title: Microsoft 365 Network Insights (Vorschau)
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
description: Microsoft 365 Network Insights (Vorschau)
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055473"
---
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 Network Insights (Vorschau)

**Netzwerkeinblicke** sind Leistungsmetriken, die von Ihrem Microsoft 365-Mandanten erfasst werden und nur von Administratorbenutzern in Ihrem Mandanten angezeigt werden können. Einblicke werden im Microsoft 365 Admin Center unter <https://portal.microsoft.com/adminportal/home#/networkperformance> angezeigt.

Einblicke sollen beim Entwerfen von Netzwerkperimetern für Ihre Bürostandorte helfen. Jeder Einblick bietet Livedetails zu den Leistungsmerkmalen für ein bestimmtes häufiges Problem für jeden geografischen Standort, an dem Benutzer auf Ihren Mandanten zugreifen.

Es gibt sechs spezifische Netzwerkeinblicke, die für jeden Bürostandort angezeigt werden können:

- [Backhauled network egress](#backhauled-network-egress)
- [Netzwerkvermittlergerät](#network-intermediary-device)
- [Bessere Leistung für Kunden in Ihrer Nähe erkannt](#better-performance-detected-for-customers-near-you)
- [Verwenden einer nicht optimalen Front-Door des Exchange Online-Diensts](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Verwenden einer nicht optimalen SharePoint Online-Dienst-Eingangstür](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Niedrige Downloadgeschwindigkeit von der SharePoint-Front-Door](#low-download-speed-from-sharepoint-front-door)
- [Optimaler Netzwerk-Ausgangs in China](#china-user-optimal-network-egress)

Es gibt zwei Netzwerkeinblicke auf Mandantenebene, die für den Mandanten angezeigt werden können. Diese werden auch auf den Produkvitivy-Bewertungsseiten angezeigt:

- [Exchange-Beispielverbindungen, die von Konnektivitätsproblemen betroffen sind](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [Von Konnektivitätsproblemen betroffene In-SharePoint-Beispielverbindungen](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Netzwerkeinblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und sind nur für Microsoft 365-Mandanten verfügbar, die für das Featurevorschauprogramm registriert wurden.

## <a name="backhauled-network-egress"></a>Backhauled network egress

Dieser Einblick wird angezeigt, wenn der Netzwerkinblickedienst erkennt, dass der Abstand zwischen einem bestimmten Benutzerstandort und dem Netzwerkeinsprung größer als 500 Meilen (800 Kilometer) ist, was bedeutet, dass microsoft 365-Datenverkehr zu einem gemeinsamen Internetedgegerät oder -proxy zurückgestürzt wird.

Dieser Einblick wird in einigen Zusammenfassungsansichten als "Egress" abgekürzt.

![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Szenario

Dies gibt an, dass der Abstand zwischen Bürostandort und Netzwerk aus dem Netzwerk mehr als 500 Meilen (800 Kilometer) beträgt. Der Bürostandort wird durch einen verschleierten Standort des Clientcomputers identifiziert, und der Netzwerk-Ausgangsstandort wird mithilfe der umgekehrten IP-Adresse für Standortdatenbanken identifiziert. Der Bürostandort ist möglicherweise ungenau, wenn die Windows Location Services auf Computern deaktiviert sind. Der Netzwerk-Ausgangsspeicherort ist möglicherweise ungenau, wenn die Informationen der Reverse-IP-Adressdatenbank ungenau sind.

Zu den Details für diesen Einblick gehören der Bürostandort, der geschätzte Prozentsatz des gesamten Mandantenbenutzers am Standort, der aktuelle Netzwerk-Ausgangsstandort, die Relevanz des Ausgangspunkts, der Abstand zwischen dem Standort und dem aktuellen Ausgangspunkt, das Datum, an dem die Bedingung zum ersten Mal erkannt wurde, und das Datum, an dem die Bedingung aufgelöst wurde.

### <a name="what-should-i-do"></a>Was soll ich machen?

Für diesen Einblick empfehlen wir, den Netzwerkeingang näher am Bürostandort zu verwenden, damit die Konnektivität optimal zum globalen Netzwerk von Microsoft und zur nächstgelegenen Microsoft 365-Dienst-Front-Door geroutet werden kann. Ein enger Netzwerkeinschluss zu den Bürostandorten der Benutzer ermöglicht auch in Zukunft eine bessere Leistung, da Microsoft in Zukunft sowohl netzwerkstandorte als auch Microsoft 365-Dienst-Front-Doors erweitert.

Weitere Informationen zur Behebung dieses Problems [](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) finden Sie unter "Prinzipien von Netzwerkverbindungen in [Office 365 Network Connectivity".](microsoft-365-network-connectivity-principles.md)

## <a name="network-intermediary-device"></a>Netzwerkvermittlergerät

Dieser Einblick wird angezeigt, wenn wir Geräte zwischen Ihren Benutzern und dem Netzwerk von Microsoft erkannt haben, die sich auf die Office 365-Benutzeroberfläche auswirken können. Es wird empfohlen, diese für bestimmten Microsoft 365-Netzwerkdatenverkehr zu umgehen, der für Microsoft-Rechenzentren bestimmt ist. Diese Empfehlung wird zusätzlich in den Prinzipien der [Microsoft 365-Netzwerkkonnektivität beschrieben.](microsoft-365-network-connectivity-principles.md)

### <a name="what-does-this-mean"></a>Szenario

Zwischengeschaltete Netzwerkgeräte wie Proxyserver, VPNs und Geräte zur Verhinderung von Datenverlusten können sich auf die Leistung und Stabilität von Microsoft 365-Clients auswirken, bei denen Datenverkehr zwischengeschaltet wird.

### <a name="what-should-i-do"></a>Was soll ich machen?

Konfigurieren Sie das Netzwerkvermittlergerät, das erkannt wurde, um die Verarbeitung für Microsoft 365-Netzwerkdatenverkehr zu umgehen.

## <a name="better-performance-detected-for-customers-near-you"></a>Bessere Leistung für Kunden in Ihrer Nähe erkannt

Dieser Einblick wird angezeigt, wenn der Netzwerkinblickedienst erkennt, dass eine erhebliche Anzahl von Kunden in Ihrer Region in Ihrer Region eine bessere Leistung hat als Benutzer in Ihrer Organisation an diesem Bürostandort.

Dieser Einblick wird in einigen Zusammenfassungsansichten als "Peers" abgekürzt.

![Relative Netzwerkleistung](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Szenario

Dieser Einblick untersucht die Gesamtleistung von Microsoft 365-Kunden in derselben Stadt wie dieser Bürostandort. Dieser Einblick wird angezeigt, wenn die durchschnittliche Wartezeit Ihrer Benutzer um 10 % über der durchschnittlichen Wartezeit benachbarter Mandanten liegt.

### <a name="what-should-i-do"></a>Was soll ich machen?

Es kann viele Gründe für diese Bedingung geben, z. B. Wartezeiten in Ihrem Unternehmensnetzwerk oder Internetdienstanbieter, Engpässe oder Architekturentwurfsprobleme. Überprüfen Sie die Wartezeit zwischen jedem Hop in der Route zwischen Ihrem Büronetzwerk und der aktuellen Microsoft 365-Eingangstür. Weitere Informationen finden Sie unter ["Prinzipien der Microsoft 365-Netzwerkkonnektivität".](microsoft-365-network-connectivity-principles.md)

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Verwenden eines nicht optimalen Front-Door-Diensts für den Exchange Online-Dienst

Dieser Einblick wird angezeigt, wenn der Netzwerkinblickedienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit einer optimalen Front-Door des Exchange Online-Diensts herstellen.

Dieser Einblick wird in einigen Zusammenfassungsansichten als "Routing" abgekürzt.

![Nicht optimale EXO-Front-Door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Szenario

Wir listen die Front-Doors des Exchange Online-Diensts auf, die sich für die Verwendung in der Stadt am Bürostandort mit guter Leistung eignen. Wenn der aktuelle Test die Verwendung einer Front-Door eines Exchange Online-Diensts zeigt, die nicht in dieser Liste enthalten ist, wird diese Empfehlung angezeigt.

### <a name="what-should-i-do"></a>Was soll ich machen?

Die Verwendung einer nicht optimalen Front-Door des Exchange Online-Diensts kann durch eine Netzwerk-Backhaul vor dem Auskommen des Unternehmensnetzwerks verursacht werden. In diesem Fall wird ein lokaler und direkter Netzwerkein-/-abgress empfohlen. Es kann auch durch die Verwendung eines DNS-Rekursiven Resolver-Remoteservers verursacht werden. In diesem Fall wird empfohlen, den DNS-Rekursiven Resolverserver an den Netzwerkentress auszurichten.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Verwenden einer nicht optimalen SharePoint Online-Dienst-Eingangstür

Dieser Einblick wird angezeigt, wenn der Netzwerkinblickedienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit der nächstgelegenen SharePoint Online -Dienst-Front-Door herstellen.

Dieser Einblick wird in einigen Zusammenfassungsansichten als "Afd" abgekürzt.

![Nicht optimaler SPO-Front-Door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Szenario

Wir identifizieren die Front-Door des SharePoint Online-Diensts, mit der der Testclient eine Verbindung herstellen soll. Für die Bürostandort-Stadt vergleichen wir dies dann mit dem erwarteten SharePoint Online-Service-Eingangstor für diese Stadt. Wenn sie nicht übereinstimmen, wird diese Empfehlung empfohlen.

### <a name="what-should-i-do"></a>Was soll ich machen?

Die Verwendung einer nicht optimalen SharePoint Online -Dienst-Front-Door kann durch eine Netzwerk-Backhaul vor dem Auskommen des Unternehmensnetzwerks verursacht werden. In diesem Fall empfehlen wir lokalen und direkten Netzwerkein- und -abgress. Es kann auch durch die Verwendung eines DNS-Rekursiven Resolver-Remoteservers verursacht werden. In diesem Fall wird empfohlen, den DNS-Rekursiven Resolverserver an den Netzwerkentress auszurichten.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Geringe Downloadgeschwindigkeit von der SharePoint-Front-Door

Dieser Einblick wird angezeigt, wenn der Netzwerkinblickedienst erkennt, dass die Bandbreite zwischen dem bestimmten Bürostandort und SharePoint Online weniger als 1 MBps beträgt.

Dieser Einblick wird in einigen Zusammenfassungsansichten als "Durchsatz" abgekürzt.

### <a name="what-does-this-mean"></a>Szenario

Die Downloadgeschwindigkeit, die ein Benutzer von SharePoint Online und OneDrive for #A0 erhalten kann, wird in Megabyte pro Sekunde (MBIT/s) gemessen. Wenn dieser Wert kleiner als 1 MBps ist, geben wir diesen Einblick.

### <a name="what-should-i-do"></a>Was soll ich machen?

Um die Downloadgeschwindigkeit zu verbessern, muss die Bandbreite möglicherweise erhöht werden. Alternativ kann es zu Netzwerküberlastungen zwischen Benutzergeräten am Bürostandort und der Fronttür des SharePoint Online-Diensts kommen. Dies wird manchmal als überlastet bezeichnet und schränkt die Downloadgeschwindigkeit ein, die Benutzern zur Verfügung steht, auch wenn ausreichend Bandbreite verfügbar ist.

## <a name="china-user-optimal-network-egress"></a>Optimaler Netzwerk-Ausgangs in China

Dieser Einblick wird angezeigt, wenn Ihre Organisation Benutzer in China hat, die sich mit Ihrem Microsoft 365-Mandanten an anderen geografischen Standorten verbinden. 

### <a name="what-does-this-mean"></a>Szenario

Wenn Ihre Organisation über private WAN-Verbindungen verfügt, wird empfohlen, eine Netzwerk-WAN-Leitung von Ihren Niederlassungen in China aus zu konfigurieren, die an einem der folgenden Standorte über einen Netzwerkentgang zum Internet verfügt:

- Hongkong
- Japan
- Taiwan
- Südkorea
- Singapur
- Malaysia

Der Internetaustritt von Benutzern als diese Standorte wird die Leistung beeinträchtigen, und ein Abgang in China kann aufgrund von überlastungsübergreifenden Verbindungen zu hohen Wartezeiten und Konnektivitätsproblemen führen.

### <a name="what-should-i-do"></a>Was soll ich machen?

Weitere Informationen zum Beheben von Leistungsproblemen im Zusammenhang mit diesem Einblick finden Sie unter [Microsoft 365 globale](microsoft-365-networking-china.md)Mandantenleistungsoptimierung für Benutzer in China.

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Exchange-Beispielverbindungen, die von Konnektivitätsproblemen betroffen sind

Dieser Einblick wird angezeigt, wenn 50 % oder mehr der in der Stichprobe verwendeten Verbindungen betroffen sind. Die Auswirkung wird durch die Exchange-Bewertung definiert, die für jede Stichprobe unter 60 % liegt.

### <a name="what-does-this-mean"></a>Szenario

Dies ist ein Hinweis darauf, dass bei der Mehrzahl der Benutzer wahrscheinlich Probleme mit der Benutzererfahrung auftreten, wenn Outlook eine Verbindung mit Exchange Online herstellen kann. Der Prozentsatz der Stichproben stellt wahrscheinlich den Prozentsatz der Benutzer dar, die weniger als 60 Punkte anzeigen.  

### <a name="what-should-i-do"></a>Was soll ich machen?

Aktivieren Sie die Sichtbarkeit der Netzwerkkonnektivität des Bürostandorts, wenn Sie dies noch nicht getan haben. Sie möchten ermitteln, welche Büros von einer schlechten Netzwerkkonnektivität betroffen sind, die Sich auf Exchange ausdingt, und nach Möglichkeiten suchen, den Netzwerkperimeter zu verbessern, der die Benutzer mit dem Netzwerk von Microsoft verbindet.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>Von Konnektivitätsproblemen betroffene In-SharePoint-Beispielverbindungen

Dieser Einblick wird angezeigt, wenn 50 % oder mehr der in der Stichprobe verwendeten Verbindungen betroffen sind. Die Auswirkung wird durch die SharePoint-Bewertung definiert, die für jede Stichprobe unter 40 % liegt.

### <a name="what-does-this-mean"></a>Szenario

Es ist ein Hinweis darauf, dass die Mehrzahl Ihrer Benutzer wahrscheinlich Probleme mit Der Benutzererfahrung mit SharePoint und OneDrive haben. Der Prozentsatz der Stichproben stellt wahrscheinlich den Prozentsatz der Benutzer dar, die weniger als 40 Punkte anzeigen.  

### <a name="what-should-i-do"></a>Was soll ich machen?

Aktivieren Sie die Sichtbarkeit der Netzwerkkonnektivität des Bürostandorts, wenn Sie dies noch nicht getan haben. Sie möchten ermitteln, welche Büros von einer schlechten Netzwerkkonnektivität betroffen sind, die Sich auf SharePoint auswirken, und nach Möglichkeiten suchen, den Netzwerkperimeter zu verbessern, der die Benutzer mit dem Netzwerk von Microsoft verbindet.

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)](office-365-network-mac-perf-overview.md)

[Microsoft 365-Netzwerkbewertung (Vorschau)](office-365-network-mac-perf-score.md)

[Microsoft 365-Tool zum Testen der Netzwerkkonnektivität (Vorschau)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (Vorschau)](office-365-network-mac-location-services.md)
