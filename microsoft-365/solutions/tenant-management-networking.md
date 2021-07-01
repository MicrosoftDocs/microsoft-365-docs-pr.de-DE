---
title: 'Schritt 2: Optimales Netzwerk für Ihre Microsoft 365 für Unternehmensmandanten'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Optimieren Sie den Netzwerkzugriff auf Ihre Microsoft 365 Mandanten.
ms.openlocfilehash: cf9591d2ec027c42f5ef9e7abac6dc9b06744a81
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229179"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a>Schritt 2. Optimales Netzwerk für Ihre Microsoft 365 für Unternehmensmandanten

Microsoft 365 für Unternehmen umfasst Cloud-Produktivitäts-Apps wie Teams und Exchange Online sowie Microsoft Intune sowie viele Identitäts- und Sicherheitsdienste von Microsoft Azure. Alle diese cloudbasierten Dienste basieren auf der Sicherheit, Leistung und Zuverlässigkeit von Verbindungen von Clientgeräten in Ihrem lokalen Netzwerk oder einem beliebigen Standort im Internet. 

Um den Netzwerkzugriff für Ihren Mandanten zu optimieren, müssen Sie:

- Optimieren Sie den Pfad zwischen Ihren lokalen Benutzern und dem nächstgelegenen Standort des globalen Microsoft-Netzwerks.
- Optimieren Sie den Zugriff auf das globale Microsoft-Netzwerk für Ihre Remotebenutzer, die eine VPN-Lösung für den Remotezugriff verwenden.
- Verwenden Sie netzwerk Insights, um den Netzwerkperimeter für Ihre Bürostandorte zu entwerfen.
- Optimieren Sie den Zugriff auf bestimmte Ressourcen, die auf SharePoint Websites mit dem Office 365 CDN gehostet werden.
- Konfigurieren Sie Proxy- und Netzwerk-Edgegeräte, um die Verarbeitung für Microsoft 365 vertrauenswürdigen Datenverkehr mit der Liste der Endpunkte zu umgehen, und automatisieren Sie die Aktualisierung der Liste, wenn Änderungen vorgenommen werden.

## <a name="enterprise-on-premises-workers"></a>Enterprise lokale Mitarbeiter

Für Unternehmensnetzwerke sollten Sie die Endbenutzerumgebung optimieren, indem Sie den netzwerkbasierten Zugriff mit der höchsten Leistung zwischen Clients und den nächstgelegenen Microsoft 365 Endpunkten aktivieren. Die Qualität der Endbenutzererfahrung hängt direkt mit der Leistung und Reaktionsfähigkeit der Anwendung zusammen, die der Benutzer verwendet. Beispielsweise basiert Microsoft Teams auf einer geringen Latenz, sodass Benutzertelefonanrufe, Konferenzen und Zusammenarbeiten auf freigegebenen Bildschirmen nicht problemlos ausgeführt werden können.

Das Hauptziel beim Netzwerkdesign sollte die Minimierung der Latenz sein, indem die Roundtripzeit (RTT) von Clientgeräten zum globalen Microsoft-Netzwerk reduziert wird, dem öffentlichen Netzwerk-Backbone von Microsoft, der alle Microsoft-Rechenzentren mit geringer Latenz und hochverfügbarem Einstiegspunkten für Cloudanwendungen verbindet, die als Front-Doors bezeichnet werden und auf der ganzen Welt verteilt sind.

Nachfolgend sehen Sie ein Beispiel für ein herkömmliches Unternehmensnetzwerk.

![Ein herkömmliches Unternehmensnetzwerk mit zentralem Internetzugriff](../media/tenant-management-overview/tenant-management-networking-traditional.png)

In dieser Abbildung stellen Zweigstellen über WAN-Geräte (Wide Area Network) und einen WAN-Backbone eine Verbindung mit einer Zentralen Niederlassung her. Der Internetzugriff erfolgt über ein Sicherheits- oder Proxygerät am Netzwerkrand der Zentralstelle und über einen Internetdienstanbieter (Internet Service Provider, ISP). Im Internet verfügt das globale Microsoft-Netzwerk über eine Reihe von Eingangstüren in Regionen auf der ganzen Welt. Organisationen können auch Zwischenspeicherorte für zusätzliche Paketverarbeitung und Sicherheit für Datenverkehr verwenden. Der Microsoft 365 Mandant einer Organisation befindet sich im globalen Microsoft-Netzwerk.

Die Probleme mit dieser Konfiguration für Microsoft 365 Clouddienste sind:

- Für Benutzer in Zweigstellen wird Datenverkehr an nicht lokale Eingangstüren gesendet, wodurch sich die Latenz erhöht.
- Das Senden von Datenverkehr an zwischengeschaltete Standorte erstellt Netzwerkspitzen, die doppelte Paketverarbeitung für vertrauenswürdigen Datenverkehr ausführen, wodurch sich die Latenz erhöht.
- Netzwerk-Edgegeräte führen eine nicht benötigte und doppelte Paketverarbeitung für vertrauenswürdigen Datenverkehr durch, wodurch die Latenz erhöht wird.

Die Optimierung Microsoft 365 Netzwerkleistung muss nicht kompliziert sein. Sie können die bestmögliche Leistung erzielen, indem Sie einige wichtige Prinzipien befolgen:

- Identifizieren Sie Microsoft 365 Netzwerkdatenverkehr, bei dem es sich um vertrauenswürdigen Datenverkehr handelt, der an Microsoft-Clouddienste bestimmt ist.
- Zulassen des Lokalen Zweigstellenausgangs von Microsoft 365 Netzwerkdatenverkehr in das Internet von jedem Standort, an dem Benutzer eine Verbindung mit Microsoft 365 herstellen.
- Vermeiden Sie Spitzkehren im Netzwerk.
- Zulassen, dass Microsoft 365 Datenverkehr Proxys und Paketüberprüfungsgeräte umgeht.

Wenn Sie diese Prinzipien implementieren, erhalten Sie ein unternehmensoptimiertes Netzwerk für Microsoft 365.

![Ein für Microsoft 365 optimiertes Unternehmensnetzwerk](../media/tenant-management-overview/tenant-management-networking-optimized.png)

In dieser Abbildung verfügen Zweigstellen über eine eigene Internetverbindung über ein softwaredefiniertes WAN-Gerät (SDWAN), das vertrauenswürdige Microsoft 365 Datenverkehr an die regional nächstgelegene Eingangstür sendet. In der Zentrale werden vertrauenswürdige Microsoft 365 Datenverkehr das Sicherheits- oder Proxygerät umgeht, und Zwischengeräte werden nicht mehr verwendet.

Hier sehen Sie, wie die optimierte Konfiguration die Latenzprobleme eines herkömmlichen Unternehmensnetzwerks löst:

- Vertrauenswürdige Microsoft 365 Datenverkehr überspringt den WAN-Backbone und wird für alle Büros an lokale Front-Doors gesendet, wodurch die Latenz verringert wird.
- Netzwerkspitzen, die doppelte Paketverarbeitung durchführen, werden für Microsoft 365 vertrauenswürdigen Datenverkehr übersprungen, wodurch die Latenz verringert wird.
- Netzwerk-Edgegeräte, die nicht benötigte und doppelte Paketverarbeitung durchführen, werden für Microsoft 365 vertrauenswürdigen Datenverkehr übersprungen, wodurch die Latenz verringert wird.

Weitere Informationen finden Sie unter [Microsoft 365 Übersicht über die Netzwerkkonnektivität.](../enterprise/microsoft-365-networking-overview.md)

## <a name="remote-workers"></a>Remotemitarbeiter

Wenn Ihre Remotemitarbeiter einen herkömmlichen VPN-Client für den Remotezugriff auf Ihr Organisationsnetzwerk verwenden, überprüfen Sie, ob der VPN-Client geteilte Tunnel unterstützt. Ohne geteilte Tunnel wird der gesamte Datenverkehr im Rahmend er Remotearbeit über die VPN-Verbindung gesendet, wo er an die Geräte am Rande Ihrer Organisation weitergeleitet, verarbeitet und dann im Internet gesendet werden muss. Hier ein Beispiel.

![Netzwerkdatenverkehr von VPN-Clients ohne Tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

In dieser Abbildung muss Microsoft 365 Datenverkehr eine indirekte Route durch Ihre Organisation nehmen, die an eine Microsoft Global Network-Front-Door weit vom physischen Standort des VPN-Clients weitergeleitet werden kann. Dieser indirekte Pfad erhöht die Latenz des Netzwerkverkehrs und verringert die Gesamtleistung. 

Mit geteilten Tunneln können Sie Ihren VPN-Client so konfigurieren, dass bestimmte Typen von Datenverkehr von der Übertragung über die VPN-Verbindung zum Unternehmensnetzwerk ausgeschlossen werden.

Um den Zugriff auf Microsoft 365-Cloudressourcen zu optimieren, konfigurieren Sie die VPN-Clients für geteilte Tunneln so, dass der Datenverkehr an die Endpunkte der **Optimieren**-Kategorie von Microsoft 365 über die VPN-Verbindung ausgeschlossen ist. Weitere Informationen finden Sie unter [Office 365 Endpunktkategorien](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) und in den Listen der [Endpunkte](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) der Kategorie "Optimieren" für geteilte Tunnel.

Hier sehen Sie den resultierenden Datenverkehrsfluss für geteilte Tunnel, bei dem der Großteil des Datenverkehrs zu Microsoft 365 Cloud-Apps die VPN-Verbindung umgeht.

![Netzwerkdatenverkehr von VPN-Clients mit Tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

In dieser Abbildung sendet und empfängt der VPN-Client wichtigen Microsoft 365 Clouddienstdatenverkehr direkt über das Internet und an die nächste Front-Door in das globale Microsoft-Netzwerk.

Weitere Informationen und eine Anleitung finden Sie unter[Optimieren der Office 365-Konnektivität für Remotebenutzer mithilfe von geteilten VPN-Tunneln](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="using-network-insights-preview"></a>Verwenden von Netzwerk-Insights (Vorschau)

Bei Netzwerkerkenntnissen handelt es sich um Leistungsmetriken, die von Ihrem Microsoft 365 Mandanten gesammelt werden, die Ihnen beim Entwerfen von Netzwerkperimetern für Ihre Bürostandorte helfen. Jeder Einblick enthält Live-Details zu den Leistungsmerkmalen für ein bestimmtes Problem für jeden geografischen Standort, an dem lokale Benutzer auf Ihren Mandanten zugreifen.

Es gibt zwei Netzwerkerkenntnisse auf Mandantenebene, die für den Mandanten angezeigt werden können:

- [Exchange von Verbindungsproblemen betroffene Verbindungen](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [SharePoint von Verbindungsproblemen betroffene Verbindungen](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

Dies sind die spezifischen Netzwerkerkenntnisse für jeden Bürostandort:

- [Backhauled-Netzwerkausgang](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [Bessere Leistung für Kunden in Ihrer Nähe](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [Verwendung einer nicht optimalen Exchange Online Service-Front-Door](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [Verwendung einer nicht optimalen SharePoint-Onlinedienst-Eingangstür](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Niedrige Downloadgeschwindigkeit von SharePoint-Eingangstür](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [Optimaler Netzwerkausgang für Benutzer in China](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

> [!IMPORTANT]
> Netzwerkerkenntnisse, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus. Es ist nur für Microsoft 365 Mandanten verfügbar, die für das Featurevorschauprogramm registriert wurden.

Weitere Informationen finden Sie unter [Microsoft 365 Network Insights](../enterprise/office-365-network-mac-perf-insights.md).

## <a name="sharepoint-performance-with-the-office-365-cdn"></a>SharePoint Leistung mit dem Office 365 CDN

Mit einem cloudbasierten Content Delivery Network (CDN) können Sie Ladezeiten reduzieren, Bandbreite sparen und die Reaktionsfähigkeit beschleunigen. Ein CDN verbessert die Leistung, indem statische Objekte wie Grafik- oder Videodateien näher an den Browsern zwischengespeichert werden, die sie anfordern, was dazu beiträgt, Downloads zu beschleunigen und die Latenz zu verringern. Sie können die integrierten Office 365 Content Delivery Network (CDN) verwenden, die in SharePoint in Microsoft 365 E3 und E5 enthalten sind, um statische Objekte zu hosten, um eine bessere Leistung für Ihre SharePoint Seiten bereitzustellen.

Das Office 365-Netzwerk für die Inhaltsübermittlung besteht aus mehreren CDNs, über die Sie statische Objekte an mehreren Speicherorten hosten können, oder aus _Ursprüngen_, die aus globalen Hochgeschwindigkeitsnetzwerken bedient werden. Je nach Art des Inhalts, den Sie im Office 365 CDN hosten möchten, können Sie **öffentliche** Ursprünge, **private** Ursprünge oder beides hinzufügen.

Bei der Bereitstellung und Konfiguration lädt die Office 365 CDN Objekte aus öffentlichen und privaten Ursprüngen hoch und macht sie für den schnellen Zugriff für Benutzer über das Internet verfügbar.

![Office 365 CDN für Benutzer bereitgestellt](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN für Benutzer bereitgestellt")

Weitere Informationen finden Sie unter [Verwenden der Office 365 CDN mit SharePoint Online.](../enterprise/use-microsoft-365-cdn-with-spo.md)

## <a name="automated-endpoint-listing"></a>Automatisierte Endpunktauflistung

Damit Ihre lokalen Clients, Edgegeräte und cloudbasierten Paketanalysedienste die Verarbeitung von vertrauenswürdigem Microsoft 365-Datenverkehr überspringen können, müssen Sie diese mit dem Satz von Endpunkten (IP-Adressbereiche und DNS-Namen) konfigurieren, die Microsoft 365 Diensten entsprechen. Diese Endpunkte können in Firewalls und anderen Edgesicherheitsgeräten, PAC-Dateien für Clientcomputer zum Umgehen von Proxys oder SD-WAN-Geräten in Zweigstellen manuell konfiguriert werden. Die Endpunkte ändern sich jedoch im Laufe der Zeit, sodass die Endpunktlisten an diesen Speicherorten fortlaufend manuell gewartet werden müssen.

Um die Eintrags- und Änderungsverwaltung für Microsoft 365 Endpunkte in Ihren Client-PAC-Dateien und Netzwerkgeräten zu automatisieren, verwenden Sie den [Office 365 IP-Adresse und URL-REST-basierten Webdienst.](../enterprise/microsoft-365-ip-web-service.md) Dieser Dienst hilft Ihnen, Microsoft 365 Netzwerkdatenverkehr besser zu identifizieren und zu unterscheiden, sodass Sie die neuesten Änderungen leichter bewerten, konfigurieren und auf dem neuesten Stand halten können.

Sie können PowerShell, Python oder andere Sprachen verwenden, um die Änderungen an Endpunkten im Laufe der Zeit zu ermitteln und Ihre PAC-Dateien und Edgenetzwerkgeräte zu konfigurieren.

Der grundlegende Prozess ist:

1. Verwenden Sie den Office 365 IP-Adress- und URL-Webdienst sowie den Konfigurationsmechanismus Ihrer Wahl, um Ihre PAC-Dateien und Netzwerkgeräte mit dem aktuellen Satz von Microsoft 365 Endpunkten zu konfigurieren.
2. Führen Sie eine tägliche Terminserie aus, um nach Änderungen an den Endpunkten zu suchen oder eine Benachrichtigungsmethode zu verwenden.
3. Wenn Änderungen erkannt werden, generieren Und verteilen Sie die PAC-Datei für Clientcomputer neu, und nehmen Sie die Änderungen an Ihren Netzwerkgeräten vor.

Weitere Informationen finden Sie unter [Office 365 IP-Adresse und URL-Webdienst.](../enterprise/microsoft-365-ip-web-service.md)

## <a name="results-of-step-2"></a>Ergebnisse von Schritt 2

Für Ihren Microsoft 365 Mandanten mit optimalem Netzwerk haben Sie Folgendes festgelegt:

- So optimieren Sie die Netzwerkleistung für lokale Benutzer, indem Sie Internetverbindungen zu allen Zweigstellen hinzufügen und Netzwerkspitzen entfernen.
- Implementieren einer automatisierten Liste vertrauenswürdiger Endpunkte für Ihre clientbasierten PAC-Dateien und Ihre Netzwerkgeräte und -dienste, einschließlich fortlaufender Updates (am besten geeignet für Unternehmensnetzwerke).
- So unterstützen Sie den Zugriff von Remotemitarbeitern auf lokale Ressourcen.
- Verwenden von Netzwerk-Insights
- Bereitstellen der Office 365 CDN.

Hier ist ein Beispiel für eine Unternehmensorganisation und deren Mandant mit optimalem Netzwerk.

![Beispiel für einen Mandanten mit optimalem Netzwerk](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[Anzeigen einer größeren Version dieses Bilds](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

In dieser Abbildung weist der Mandant für diese Unternehmensorganisation Folgendes auf:

- Lokaler Internetzugriff für jede Zweigstelle mit einem SDWAN-Gerät, das vertrauenswürdigen Microsoft 365 Datenverkehr an eine lokale Eingangstür weiterleitet.
- Keine Netzwerk-Spitzkehren.
- Sicherheits- und Proxy-Edgegeräte in der Zentrale, die Microsoft 365 vertrauenswürdigen Datenverkehr an eine lokale Eingangstür weiterleiten.

## <a name="ongoing-maintenance-for-optimal-networking"></a>Fortlaufende Wartung für optimale Netzwerke

Unter Umständen müssen Sie fortlaufend Folgendes ausführen:

- Aktualisieren Sie Ihre Edgegeräte und bereitgestellten PAC-Dateien auf Änderungen an Endpunkten, oder stellen Sie sicher, dass Ihr automatisierter Prozess ordnungsgemäß funktioniert.
- Verwalten Sie Ihre Ressourcen im Office 365 CDN.
- Aktualisieren Sie die Konfiguration des geteilten Tunnels in Ihren VPN-Clients auf Änderungen an Endpunkten.

## <a name="next-step"></a>Nächster Schritt

[![Schritt 3. Synchronisieren Ihrer Identitäten und Erzwingen sicherer Anmeldungen](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)

Fahren Sie mit [der Identität](tenant-management-identity.md) fort, um Ihre lokalen Konten und Gruppen zu synchronisieren und sichere Benutzeranmeldungen zu erzwingen.
