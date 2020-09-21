---
title: Microsoft 365 Network Insights (Vorschau)
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
description: Microsoft 365 Network Insights (Vorschau)
ms.openlocfilehash: e3730704b6672c931b7538659a38f218e769dd0a
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962371"
---
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 Network Insights (Vorschau)

**Netzwerk Einblicke** sind Leistungs Metriken, die von Ihrem Microsoft 365-Mandanten gesammelt werden und nur für administrative Benutzer in Ihrem Mandanten verfügbar sind. Einblicke werden im Microsoft 365 Admin Center unter angezeigt <https://portal.microsoft.com/adminportal/home#/networkperformance> .

Mithilfe von Insights sollen Netzwerkperimeter für Ihre Office-Standorte entworfen werden. Jede Insight enthält Live-Details zu den Leistungsmerkmalen eines bestimmten allgemeinen Problems für jeden geografischen Standort, auf den Benutzer auf ihren Mandanten zugreifen.

Es gibt sechs spezifische Netzwerk Einblicke, die für jeden Office-Standort angezeigt werden können:

- [Ausstieg aus dem backhauld-Netzwerk](#backhauled-network-egress)
- [Bessere Leistung für Kunden in Ihrer Nähe erkannt](#better-performance-detected-for-customers-near-you)
- [Verwenden eines nicht optimalen Exchange Online-Dienst-Front-Door](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Verwenden eines nicht optimalen SharePoint Online-Dienst-Front-Door](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Niedrige Downloadgeschwindigkeit von SharePoint-Haustür](#low-download-speed-from-sharepoint-front-door)
- [China-Benutzer optimales Netzwerk Austritt](#china-user-optimal-network-egress)

Es gibt zwei Netzwerk Einblicke auf Mandantenebene, die für den Mandanten angezeigt werden können. Diese werden auch auf den producvitivy-Ergebnisseiten angezeigt:

- [Auswirkungen von Verbindungsproblemen auf Exchange-Stichproben Verbindungen](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [Durch Verbindungsprobleme beeinträchtigte SharePoint-Stichproben Verbindungen](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Netzwerk Einblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und stehen nur für Microsoft 365-Mandanten zur Verfügung, die im Feature Preview-Programm registriert wurden.

## <a name="backhauled-network-egress"></a>Ausstieg aus dem backhauld-Netzwerk

Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass der Abstand zwischen einem bestimmten Benutzerstandort und dem Netzwerk Ausgang größer als 500 Meilen (800 Kilometer) ist und angibt, dass der Microsoft 365-Datenverkehr zu einem gemeinsamen Internet-Edge-Gerät oder-Proxy zurückgezogen wird.

Diese Einblicke wird in einigen zusammenfassungsansichten als "Ausstieg" abgekürzt.

![Ausstieg aus dem backhauld-Netzwerk](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Szenario

Dadurch wird feststellen, dass der Abstand zwischen dem Bürostandort und dem Netzwerk Ausstieg mehr als 500 Meilen (800 Kilometer) beträgt. Der Standort des Büros wird durch einen verborgenen Clientcomputer Speicherort identifiziert, und der Netzwerk Ausgangsspeicherort wird mithilfe von Reverse IP Address to Location Databases identifiziert. Der Office-Standort ist möglicherweise ungenau, wenn Windows-Ortungsdienste auf Computern deaktiviert sind. Der Netzwerk Ausgangsspeicherort ist möglicherweise ungenau, wenn die Datenbankinformationen der Reverse-IP-Adresse ungenau sind.

Details für diese Einblicke sind der Office-Standort, der geschätzte Prozentsatz des Gesamt Mandanten Benutzers am Standort, der aktuelle Netzwerk Ausgangsstandort, die Relevanz des Ausgangs Standorts, der Abstand zwischen dem Standort und dem aktuellen Ausgangspunkt, das Datum, an dem die Bedingung erstmals erkannt wurde, und das Datum, an dem die Bedingung aufgelöst wurde.

### <a name="what-should-i-do"></a>Was soll ich machen?

Für diese Einblicke empfehlen wir den Netzwerk Ausstieg näher am Office-Standort, damit die Konnektivität optimal zum globalen Microsoft-Netzwerk und zur nächsten Microsoft 365-Dienst Haustür weitergeleitet werden kann. Das Schließen des Netzwerk Ausstiegs für Benutzer in Office-Standorten ermöglicht auch in Zukunft eine verbesserte Leistung, da Microsoft in Zukunft sowohl Netzwerk Points of Presence als auch Microsoft 365 Service-Front-Doors erweitert.

Weitere Informationen zum Beheben dieses Problems finden Sie unter Ausgangs [Netzwerkverbindungen lokal](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Netzwerk Verbindungs Prinzipien](microsoft-365-network-connectivity-principles.md).

## <a name="better-performance-detected-for-customers-near-you"></a>Bessere Leistung für Kunden in Ihrer Nähe erkannt

Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass eine beträchtliche Anzahl von Kunden in Ihrem Metro-Bereich eine bessere Leistung hat als Benutzer in Ihrer Organisation an diesem Standort.

Diese Einblicke wird in einigen zusammenfassungsansichten als "Peers" abgekürzt.

![Relative Netzwerkleistung](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Szenario

In dieser Einblicke wird die Gesamtleistung von Microsoft 365-Kunden in derselben Stadt wie dieser Standort untersucht. Diese Einblicke wird angezeigt, wenn die durchschnittliche Wartezeit Ihrer Benutzer 10% über der durchschnittlichen Wartezeit von benachbarten Mandanten liegt.

### <a name="what-should-i-do"></a>Was soll ich machen?

Es kann viele Gründe für diese Bedingung geben, einschließlich Wartezeit in Ihrem Unternehmensnetzwerk oder ISP, Engpässe oder Architektur Designprobleme. Überprüfen Sie die Wartezeit zwischen den einzelnen Hops in der Route zwischen Ihrem Office-Netzwerk und der aktuellen Microsoft 365-Haustür. Weitere Informationen finden Sie unter [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Verwenden eines nicht optimalen Exchange Online-Dienst-Front-Door

Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit einer optimalen Exchange Online Dienst-Haustür herstellen.

Diese Einblicke wird in einigen zusammenfassungsansichten als "Routing" abgekürzt.

![Nicht optimale Exo-Haustür](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Szenario

Wir führen Exchange Online Service-Fronttüren auf, die für die Verwendung aus der Office-Standort Stadt mit guter Leistung geeignet sind. Wenn der aktuelle Test die Verwendung eines Exchange Online-Dienst-Front-Doors nicht in dieser Liste zeigt, wird diese Empfehlung aufgerufen.

### <a name="what-should-i-do"></a>Was soll ich machen?

Die Verwendung eines nicht optimalen Exchange Online Dienst-Front-Door könnte durch Netzwerk Backhaul vor dem Ausstieg des Unternehmensnetzwerks verursacht werden, in diesem Fall empfehlen wir den Ausstieg aus dem lokalen und direkten Netzwerk. Es kann auch durch die Verwendung eines Remote-DNS-rekursive Auflösungs Servers verursacht werden, in dem der Fall empfohlen wird, den DNS-rekursive Auflösungs Server mit dem Netzwerk Ausstieg auszurichten.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Verwenden eines nicht optimalen SharePoint Online-Dienst-Front-Door

Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit der nächstgelegenen SharePoint Online Dienst-Haustür herstellen.

Diese Einblicke wird in einigen zusammenfassungsansichten als "ausschließend" abgekürzt.

![Nicht optimale SPO-Haustür](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Szenario

Wir identifizieren die SharePoint Online-Dienst-Haustür, mit der der Testclient eine Verbindung herstellt. Für die Office-Standort Stadt vergleichen wir dies mit der erwarteten SharePoint Online-Service-Haustür für diese Stadt. Wenn er nicht übereinstimmt, machen wir diese Empfehlung.

### <a name="what-should-i-do"></a>Was soll ich machen?

Die Verwendung eines nicht optimalen SharePoint Online Dienst-Front-Door könnte durch Netzwerk Backhaul vor dem Ausstieg des Unternehmensnetzwerks verursacht werden, in diesem Fall empfehlen wir den Ausstieg aus dem lokalen und direkten Netzwerk. Es kann auch durch die Verwendung eines Remote-DNS-rekursive Auflösungs Servers verursacht werden, in dem der Fall empfohlen wird, den DNS-rekursive Auflösungs Server mit dem Netzwerk Ausstieg auszurichten.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Niedrige Downloadgeschwindigkeit von SharePoint-Haustür

Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass die Bandbreite zwischen dem jeweiligen Office-Standort und SharePoint Online kleiner als 1 Mbit/s ist.

Diese Einblicke wird in einigen zusammenfassungsansichten als "Durchsatz" abgekürzt.

### <a name="what-does-this-mean"></a>Szenario

Die Downloadgeschwindigkeit, die ein Benutzer von SharePoint Online-und OneDrive für Unternehmen-Dienst-Fronttüren erhalten kann, wird in Megabytes pro Sekunde (Mbps) gemessen. Wenn dieser Wert kleiner als 1 Mbit/s ist, stellen wir diese Einblicke bereit.

### <a name="what-should-i-do"></a>Was soll ich machen?

Um die Downloadgeschwindigkeit zu verbessern, muss die Bandbreite möglicherweise erhöht werden. Alternativ kann es zu Netzwerküberlastung zwischen Benutzercomputern am Office-Standort und der Front-Door-SharePoint Online Dienst geben. Dies wird manchmal als Überlastungs Verlust bezeichnet und schränkt die Downloadgeschwindigkeit ein, die Benutzern zur Verfügung steht, auch wenn genügend Bandbreite zur Verfügung steht.

## <a name="china-user-optimal-network-egress"></a>China-Benutzer optimales Netzwerk Austritt

Diese Einblicke werden angezeigt, wenn Ihre Organisation über Benutzer in China verfügt, die sich mit Ihrem Microsoft 365-Mandanten an anderen geografischen Standorten verbinden. 

### <a name="what-does-this-mean"></a>Szenario

Wenn Ihre Organisation über private WAN-Konnektivität verfügt, wird empfohlen, eine Netzwerk-WAN-Schaltung von Ihren Office-Standorten in China aus zu konfigurieren, die über einen Netzwerk Austritt mit dem Internet an einem der folgenden Standorte verfügt:

- Hongkong (SAR)
- Japan
- Taiwan
- Südkorea
- Singapur
- Malaysia

Internet Ausstieg weiter Weg von Benutzern als diese Standorte verringern die Leistung, und der Ausstieg in China kann aufgrund von grenzüberschreitender Überlastung zu hohen Latenz-und Verbindungsproblemen führen.

### <a name="what-should-i-do"></a>Was soll ich machen?

Weitere Informationen zum Minimieren von Leistungsproblemen im Zusammenhang mit dieser Einblicke finden Sie unter [Office 365 Global Tenant Performance Optimization for China users](microsoft-365-networking-china.md).

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Auswirkungen von Verbindungsproblemen auf Exchange-Stichproben Verbindungen

In dieser Erkenntnis wird angezeigt, wenn 50% oder mehr der Stichproben Verbindungen betroffen sind. Die Auswirkungen werden durch die Exchange-Bewertung für jedes Beispiel unter 60% definiert.

### <a name="what-does-this-mean"></a>Szenario

Dies deutet darauf hin, dass bei der Mehrzahl Ihrer Benutzer wahrscheinlich Probleme mit der Benutzerfreundlichkeit auftreten, wenn Outlook eine Verbindung mit Exchange Online herstellt. Der Prozentsatz der Beispiele stellt wahrscheinlich den Prozentsatz der Benutzer dar, die unter 60 Punkten angezeigt werden.  

### <a name="what-should-i-do"></a>Was soll ich machen?

Aktivieren Sie die Sichtbarkeit der Office-standortnetzwerk Konnektivität, falls noch nicht geschehen. Sie möchten ermitteln, welche Büros von einer schlechten Netzwerkverbindung betroffen sind, die sich auf Exchange auswirkt und Wege finden, um den impactred zu verbessern, der die Benutzer mit dem Netzwerk von Microsoft verbindet.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>Durch Verbindungsprobleme beeinträchtigte SharePoint-Stichproben Verbindungen

In dieser Erkenntnis wird angezeigt, wenn 50% oder mehr der Stichproben Verbindungen betroffen sind. Die Auswirkungen werden durch die SharePoint-Bewertung unter 40% für jedes Beispiel definiert.

### <a name="what-does-this-mean"></a>Szenario

Dies deutet darauf hin, dass die Mehrzahl der Benutzer wahrscheinlich Probleme mit der Benutzerfreundlichkeit bei SharePoint und OneDrive auftreten. Der Prozentsatz der Beispiele stellt wahrscheinlich den Prozentsatz der Benutzer dar, die unter 40 Punkten angezeigt werden.  

### <a name="what-should-i-do"></a>Was soll ich machen?

Aktivieren Sie die Sichtbarkeit der Office-standortnetzwerk Konnektivität, falls noch nicht geschehen. Sie möchten ermitteln, welche Büros von einer schlechten Netzwerkkonnektivität betroffen sind, die sich auf SharePoint auswirkt und Wege finden, um den impactred zu verbessern, der die Benutzer mit dem Netzwerk von Microsoft verbindet.

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Netzwerkbewertung (Vorschau)](office-365-network-mac-perf-score.md)

[Microsoft 365 Connectivity Test im M365 Admin Center (Vorschau)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (Vorschau)](office-365-network-mac-location-services.md)
