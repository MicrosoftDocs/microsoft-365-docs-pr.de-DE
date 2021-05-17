---
title: 'Schritt 2: Optimales Netzwerk für Microsoft 365 für Enterprise-Mandanten'
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
description: Optimieren Sie den Netzwerkzugriff auf Microsoft 365 Mandanten.
ms.openlocfilehash: 5eac0793d2afc924a919671ffa105362ea1866d9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407192"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a>Schritt 2. Optimales Netzwerk für Microsoft 365 für Enterprise-Mandanten

Microsoft 365 für Unternehmen umfasst Cloudproduktivitäts-Apps wie Teams und Exchange Online und Microsoft Intune sowie viele Identitäts- und Sicherheitsdienste von Microsoft Azure. Alle diese cloudbasierten Dienste basieren auf der Sicherheit, Leistung und Zuverlässigkeit von Verbindungen von Clientgeräten in Ihrem lokalen Netzwerk oder einem beliebigen Standort im Internet. 

Um den Netzwerkzugriff für Ihren Mandanten zu optimieren, müssen Sie:

- Optimieren Sie den Pfad zwischen Ihren lokalen Benutzern und dem nächstgelegenen Standort für das globale Microsoft-Netzwerk.
- Optimieren Sie den Zugriff auf das globale Microsoft-Netzwerk für Remotebenutzer, die eine Remotezugriffs-VPN-Lösung verwenden.
- Verwenden Sie Network Insights, um den Netzwerkperimeter für Ihre Bürostandorte zu entwerfen.
- Optimieren Sie den Zugriff auf bestimmte Objekte, die auf SharePoint gehostet werden, mit Office 365 CDN.
- Konfigurieren Sie Proxy- und Netzwerk-Edgegeräte, um die Verarbeitung für Microsoft 365 vertrauenswürdigen Datenverkehr mit der Liste der Endpunkte zu umgehen, und automatisieren Sie die Aktualisierung der Liste, sobald Änderungen vorgenommen werden.

## <a name="enterprise-on-premises-workers"></a>Enterprise lokalen Mitarbeitern

Für Unternehmensnetzwerke sollten Sie die Endbenutzererfahrung optimieren, indem Sie den leistungsstarken Netzwerkzugriff zwischen Clients und den Microsoft 365 ermöglichen. Die Qualität der Endbenutzererfahrung steht in direktem Zusammenhang mit der Leistung und Reaktionsfähigkeit der Anwendung, die der Benutzer verwendet. Beispielsweise basiert Microsoft Teams auf einer geringen Latenz, sodass Benutzertelefonanrufe, Konferenzen und zusammenarbeiten auf gemeinsamem Bildschirm ohne Fehler sind.

Das Hauptziel im Netzwerkentwurf sollte es sein, die Latenz zu minimieren, indem die Roundtripzeit (Roundtrip time, RTT) von Clientgeräten zum Microsoft Global Network reduziert wird, dem öffentlichen Netzwerk-Backbone von Microsoft, das alle Rechenzentren von Microsoft mit niedriger Latenz miteinander verbindet, und Die Einstiegspunkte für Cloudanwendung mit hoher Verfügbarkeit, die als Fronttüren bezeichnet werden, verteilen sich auf die ganze Welt.

Hier ist ein Beispiel für ein herkömmliches Unternehmensnetzwerk.

![Ein herkömmliches Unternehmensnetzwerk mit zentralem Zugriff auf das Internet](../media/tenant-management-overview/tenant-management-networking-traditional.png)

In dieser Abbildung stellen Zweigstellen eine Verbindung mit einer Zentralstelle über WAN-Geräte (Wide Area Network) und ein WAN-Backbone zur Verfügung. Der Internetzugriff wird über ein Sicherheits- oder Proxygerät am Netzwerkrand der Zentralstelle und über einen Internetdienstanbieter (Internet Service Provider, ISP) ausgeführt. Im Internet verfügt das Globale Netzwerk von Microsoft über eine Reihe von Fronttüren in Regionen auf der ganzen Welt. Organisationen können auch Zwischenstandorte für zusätzliche Paketverarbeitung und Sicherheit für Datenverkehr verwenden. Der mandanten einer Organisation Microsoft 365 sich innerhalb des globalen Netzwerks von Microsoft.

Die Probleme mit dieser Konfiguration für Microsoft 365 cloud services sind:

- Für Benutzer in Zweigstellen wird Datenverkehr an nicht lokale Eingangstüren gesendet, was die Wartezeit erhöht.
- Das Senden von Datenverkehr an Zwischenstandorte erstellt Netzwerk-Hairpins, die doppelte Paketverarbeitung für vertrauenswürdigen Datenverkehr durchführen, was die Latenz erhöht.
- Netzwerk-Edgegeräte führen eine nicht mehr zu verwendende und doppelte Paketverarbeitung für vertrauenswürdigen Datenverkehr durch, was die Wartezeit erhöht.

Das Optimieren Microsoft 365 Netzwerkleistung muss nicht kompliziert sein. Sie können die bestmögliche Leistung erzielen, indem Sie einige wichtige Prinzipien folgen:

- Identifizieren Microsoft 365 Netzwerkdatenverkehr, bei dem es sich um vertrauenswürdigen Datenverkehr handelt, der an Microsoft Cloud Services bestimmt ist.
- Zulassen, dass der lokale Microsoft 365 von jedem Standort, an dem Benutzer eine Verbindung mit dem Netzwerk herstellen, in das Microsoft 365.
- Vermeiden Sie Netzwerk-Hairpins.
- Zulassen Microsoft 365 Datenverkehrs, um Proxys und Paketprüfungsgeräte zu umgehen.

Wenn Sie diese Prinzipien implementieren, erhalten Sie ein unternehmensweites Netzwerk, das für Microsoft 365.

![Ein unternehmensweites Netzwerk, das für Microsoft 365](../media/tenant-management-overview/tenant-management-networking-optimized.png)

In dieser Abbildung verfügen Zweigstellen über eine eigene Internetverbindung über ein softwaredefiniertes WAN-Gerät (SDWAN), das vertrauenswürdigen Microsoft 365-Datenverkehr an die regional nächstgelegene Eingangstür sendet. In der Zentralstelle werden vertrauenswürdige Microsoft 365 der Datenverkehr das Sicherheits- oder Proxygerät umgeht, und Zwischengeräte werden nicht mehr verwendet.

Hier sehen Sie, wie die optimierte Konfiguration die Latenzprobleme eines herkömmlichen Unternehmensnetzwerks löst:

- Vertrauenswürdiger Microsoft 365-Datenverkehr überspringt das WAN-Backbone und wird an lokale Fronttüren für alle Büros gesendet, was die Latenz verringert.
- Netzwerk-Hairpins, die doppelte Paketverarbeitung durchführen, werden für Microsoft 365 Datenverkehr übersprungen, was die Latenz verringert.
- Netzwerk-Edgegeräte, die nicht unnötigen und doppelten Paketverarbeitung durchführen, werden für Microsoft 365 vertrauenswürdigen Datenverkehr übersprungen, was die Latenz verringert.

Weitere Informationen finden Sie unter [Microsoft 365 Netzwerkverbindungsübersicht](../enterprise/microsoft-365-networking-overview.md).

## <a name="remote-workers"></a>Remotemitarbeiter

Wenn Ihre Remotemitarbeiter einen herkömmlichen VPN-Client für den Remotezugriff auf Ihr Organisationsnetzwerk verwenden, überprüfen Sie, ob der VPN-Client geteilte Tunnel unterstützt. Ohne geteilte Tunnel wird der gesamte Datenverkehr im Rahmend er Remotearbeit über die VPN-Verbindung gesendet, wo er an die Geräte am Rande Ihrer Organisation weitergeleitet, verarbeitet und dann im Internet gesendet werden muss. Hier ein Beispiel.

![Netzwerkdatenverkehr von VPN-Clients ohne Tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

In dieser Abbildung Microsoft 365 datenverkehr eine indirekte Route durch Ihre Organisation, die an eine Microsoft Global Network-Fronttür weit weg vom physischen Standort des VPN-Clients weitergeleitet werden kann. Dieser indirekte Pfad erhöht die Latenz des Netzwerkverkehrs und verringert die Gesamtleistung. 

Mit geteilten Tunneln können Sie Ihren VPN-Client so konfigurieren, dass bestimmte Typen von Datenverkehr von der Übertragung über die VPN-Verbindung zum Unternehmensnetzwerk ausgeschlossen werden.

Um den Zugriff auf Microsoft 365-Cloudressourcen zu optimieren, konfigurieren Sie die VPN-Clients für geteilte Tunneln so, dass der Datenverkehr an die Endpunkte der **Optimieren**-Kategorie von Microsoft 365 über die VPN-Verbindung ausgeschlossen ist. Weitere Informationen finden Sie [unter Office 365 endpunktkategorien](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) und [den](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) Listen von Optimize category endpoints for split tunneling.

Hier ist der resultierende Datenverkehrsfluss für geteiltes Tunneln, bei dem der großteil des Datenverkehrs zu Microsoft 365-Cloud-Apps die VPN-Verbindung umgehen.

![Netzwerkdatenverkehr von VPN-Clients mit Tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

In dieser Abbildung sendet und empfängt der VPN-Client wichtige Microsoft 365 des Clouddienstdatenverkehrs direkt über das Internet und an die nächste Eingangstür in das globale Microsoft Netzwerk.

Weitere Informationen und eine Anleitung finden Sie unter[Optimieren der Office 365-Konnektivität für Remotebenutzer mithilfe von geteilten VPN-Tunneln](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="using-network-insights-preview"></a>Verwenden von Network Insights (Vorschau)

Netzwerkeinblicke sind Leistungsmetriken, die von Microsoft 365 Mandanten gesammelt werden, mit deren Hilfe Sie Netzwerkperimeter für Ihre Bürostandorte entwerfen können. Jeder Einblick enthält Livedetails zu den Leistungsmerkmalen eines bestimmten Problems für jeden geografischen Standort, an dem lokale Benutzer auf Ihren Mandanten zugreifen.

Es gibt zwei Netzwerkeinblicke auf Mandantenebene, die für den Mandanten angezeigt werden können:

- [Exchange verbindungen, die von Konnektivitätsproblemen betroffen sind](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [SharePoint von Konnektivitätsproblemen betroffener Beispielverbindungen](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

Dies sind die spezifischen Netzwerkeinblicke für jeden Bürostandort:

- [Backhauled network egress](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [Bessere Leistung für Kunden in Ihrer Nähe erkannt](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [Verwenden einer nicht optimalen Exchange Online-Service-Eingangstür](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [Verwenden einer nicht optimalen SharePoint Onlinedienst-Eingangstür](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Niedrige Downloadgeschwindigkeit SharePoint Eingangstür](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [Optimaler Netzwerk-Abgress für China-Benutzer](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
>Netzwerkeinblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befindet sich derzeit im Vorschaustatus. Sie ist nur für Microsoft 365 mandanten verfügbar, die im Featurevorschauprogramm registriert wurden.

Weitere Informationen finden Sie unter [Microsoft 365 Network Insights](../enterprise/office-365-network-mac-perf-insights.md).

## <a name="sharepoint-performance-with-the-office-365-cdn"></a>SharePoint leistung mit dem Office 365 CDN

Mit einem cloudbasierten Content Delivery Network (CDN) können Sie Ladezeiten reduzieren, Bandbreite sparen und die Reaktionsfähigkeit beschleunigen. Ein CDN verbessert die Leistung, indem statische Ressourcen wie Grafik- oder Videodateien näher an den Browsern zwischenspeichert werden, die sie anfordern, wodurch Downloads beschleunigt und die Wartezeit reduziert wird. Mithilfe der integrierten Office 365 Content Delivery Network (CDN), die in SharePoint in Microsoft 365 E3 und E5 enthalten ist, können Sie statische Objekte hosten, um eine bessere Leistung für Ihre SharePoint bieten.

Das Office 365-Netzwerk für die Inhaltsübermittlung besteht aus mehreren CDNs, über die Sie statische Objekte an mehreren Speicherorten hosten können, oder aus _Ursprüngen_, die aus globalen Hochgeschwindigkeitsnetzwerken bedient werden. Je nachdem, welche Art von Inhalt Sie in der Office 365 CDN  hosten möchten, können Sie öffentliche Ursprünge, **private** Ursprünge oder beides hinzufügen.

Bei der Bereitstellung und Konfiguration lädt Office 365 CDN Objekte von öffentlichen und privaten Ursprüngen hoch und stellt sie für den schnellen Zugriff auf Benutzer zur Verfügung, die sich über das Internet befinden.

![Office 365 CDN für Benutzer bereitgestellt](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN für Benutzer bereitgestellt")

Weitere Informationen finden Sie unter [Use the Office 365 CDN with SharePoint Online](../enterprise/use-microsoft-365-cdn-with-spo.md).

## <a name="automated-endpoint-listing"></a>Automatisierte Endpunktauflistung

Damit Ihre lokalen Clients, Edgegeräte und cloudbasierten Paketanalysedienste die Verarbeitung des vertrauenswürdigen Microsoft 365-Datenverkehrs überspringen, müssen Sie sie mit dem Satz von Endpunkten (IP-Adressbereiche und DNS-Namen) konfigurieren, der den Microsoft 365-Diensten entspricht. Diese Endpunkte können manuell in Firewalls und anderen Edgesicherheitsgeräten, PAC-Dateien für Clientcomputer zum Umgehen von Proxys oder SD-WAN-Geräten in Zweigstellen konfiguriert werden. Die Endpunkte ändern sich jedoch im Laufe der Zeit, was eine fortlaufende manuelle Wartung der Endpunktlisten an diesen Speicherorten erfordert.

Verwenden Sie zum Automatisieren der Listen- und Änderungsverwaltung für Microsoft 365-Endpunkte in Ihren Client-PAC-Dateien und Netzwerkgeräten den [Office 365-IP-Adresse- und URL-REST-basierten Webdienst](../enterprise/microsoft-365-ip-web-service.md). Dieser Dienst hilft Ihnen, Microsoft 365 Netzwerkdatenverkehr besser zu identifizieren und zu unterscheiden, wodurch Es ihnen einfacher wird, die neuesten Änderungen auszuwerten, zu konfigurieren und auf dem neuesten Stand zu bleiben.

Sie können PowerShell, Python oder andere Sprachen verwenden, um die Änderungen an Endpunkten im Laufe der Zeit zu bestimmen und Ihre PAC-Dateien und Edgenetzwerkgeräte zu konfigurieren.

Der grundlegende Prozess ist:

1. Verwenden Sie Office 365-IP-Adresse und -URL-Webdienst und den Konfigurationsmechanismus Ihrer Wahl, um Ihre PAC-Dateien und Netzwerkgeräte mit dem aktuellen Satz von Microsoft 365 konfigurieren.
2. Führen Sie eine tägliche Wiederholung aus, um nach Änderungen an den Endpunkten zu suchen oder eine Benachrichtigungsmethode zu verwenden.
3. Wenn Änderungen erkannt werden, regenerieren und verteilen Sie die PAC-Datei für Clientcomputer, und nehmen Sie die Änderungen an Ihren Netzwerkgeräten vor.

Weitere Informationen finden Sie unter [Office 365 IP-Adresse und URL-Webdienst](../enterprise/microsoft-365-ip-web-service.md).

## <a name="results-of-step-2"></a>Ergebnisse von Schritt 2

Für Microsoft 365 Mandanten mit optimalem Netzwerk haben Sie ermittelt:

- Optimieren der Netzwerkleistung für lokale Benutzer durch Hinzufügen von Internetverbindungen zu allen Zweigstellen und Eliminieren von Netzwerk-Hairpins.
- Implementieren der automatisierten Liste vertrauenswürdiger Endpunkte für Ihre clientbasierten PAC-Dateien und Ihre Netzwerkgeräte und -dienste, einschließlich laufender Updates (am besten geeignet für Unternehmensnetzwerke).
- So unterstützen Sie den Zugriff von Remotemitarbeitern auf lokale Ressourcen.
- Verwenden von Network Insights
- Bereitstellen der Office 365 CDN.

Hier ist ein Beispiel für eine Unternehmensorganisation und deren Mandant mit optimaler Netzwerkumgebung.

![Beispiel für einen Mandanten mit optimalem Netzwerk](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[Eine größere Version dieses Bilds sehen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

In dieser Abbildung verfügt der Mandant für diese Unternehmensorganisation über:

- Lokaler Internetzugriff für jede Zweigstelle mit einem SDWAN-Gerät, das vertrauenswürdigen Microsoft 365 an eine lokale Eingangstür weiter.
- Keine Netzwerk-Hairpins.
- Sicherheits- und Proxy-Edgegeräte der Zentralstelle, die Microsoft 365 vertrauenswürdigen Datenverkehr an eine lokale Eingangstür weiterleiten.

## <a name="ongoing-maintenance-for-optimal-networking"></a>Fortlaufende Wartung für optimale Netzwerke

Auf fortlaufender Basis müssen Sie möglicherweise:

- Aktualisieren Sie Ihre Edgegeräte und bereitgestellten PAC-Dateien für Änderungen an Endpunkten, oder überprüfen Sie, ob Ihr automatisierter Prozess ordnungsgemäß funktioniert.
- Verwalten Sie Ihre Ressourcen im Office 365 CDN.
- Aktualisieren Sie die Konfiguration des geteilten Tunnels in Ihren VPN-Clients für Änderungen an Endpunkten.

## <a name="next-step"></a>Nächster Schritt

[![Schritt 3. Synchronisieren Ihrer Identitäten und Erzwingen sicherer Anmeldungen](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)

Fahren Sie mit [der Identität](tenant-management-identity.md) fort, um Ihre lokalen Konten und Gruppen zu synchronisieren und sichere Benutzer-Anmeldungen zu erzwingen.
