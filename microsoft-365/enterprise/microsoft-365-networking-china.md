---
title: Microsoft 365 globale Mandantenleistungsoptimierung für Benutzer in China
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: Dieser Artikel enthält Anleitungen zum Optimieren der Netzwerkleistung für Benutzer globaler Microsoft 365 Mandanten in China.
ms.openlocfilehash: f48b552dec72d78e2429aedf6a3834dba6c7590a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844502"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Microsoft 365 globale Mandantenleistungsoptimierung für Benutzer in China

> [!IMPORTANT]
> Dieser Leitfaden ist spezifisch für Nutzungsszenarien, in denen **Unternehmen Microsoft 365 Benutzer in China** eine Verbindung mit einem globalen Microsoft 365 **Mandanten** herstellen. Dieser Leitfaden gilt **nicht** für Mandanten in Office 365 betrieben von 21Vianet.

Für Unternehmen mit globalen Microsoft 365-Mandanten und einer Unternehmenspräsenz in China kann Microsoft 365 Clientleistung für Benutzer mit Sitz in China durch faktoren kompliziert werden, die für die Internetarchitektur von China Telco einzigartig sind.

Die ISPs in China verfügen über regulierte Verbindungen mit dem globalen öffentlichen Internet, die Perimetergeräte durchlaufen, die für eine Überlastung des internationalen Netzwerks auf hoher Ebene anfällig sind. Diese Überlastung führt zu Paketverlust und Latenz für den gesamten Internetdatenverkehr, der in und aus China ausgeht.

![Microsoft 365 Datenverkehr – nicht optimiert](../media/O365-networking/China-O365-unoptimized.png)

Paketverluste und Latenz beeinträchtigen die Leistung von Netzwerkdiensten, insbesondere Dienste, die einen großen Datenaustausch (z. B. große Dateiübertragungen) oder nahezu Echtzeitleistung (Audio- und Videoanwendungen) erfordern.

Das Ziel dieses Themas besteht darin, bewährte Methoden bereitzustellen, um die Auswirkungen der Überlastung des grenzübergreifenden Chinesischen Netzwerks auf Microsoft 365 Dienste zu verringern. In diesem Thema werden keine anderen häufigen Leistungsprobleme im letzten Abschnitt behandelt, z. B. Probleme mit hoher Paketlatenz aufgrund des komplexen Routings innerhalb von China-Netzbetreibern.

## <a name="corporate-network-best-practices"></a>Bewährte Methoden für Unternehmensnetzwerke

Viele Unternehmen mit globaler Microsoft 365 Mandanten und Benutzern in China haben private Netzwerke implementiert, die unternehmensinternen Netzwerkdatenverkehr zwischen China-Bürostandorten und Standorten auf der ganzen Welt übertragen. Diese Unternehmen können diese Netzwerkinfrastruktur nutzen, um eine überlastung des grenzübergreifenden Netzwerks zu vermeiden und ihre Microsoft 365 Serviceleistung in China zu optimieren.

> [!IMPORTANT]
> Wie bei allen privaten WAN-Implementierungen sollten Sie sich immer an die gesetzlichen Anforderungen Ihres Landes und/oder Ihrer Region halten, um sicherzustellen, dass Ihre Netzwerkkonfiguration den Anforderungen entspricht.

Als ersten Schritt ist es wichtig, dass Sie unsere Benchmark-Netzwerkanleitungen bei der [Netzwerkplanung und Leistungsoptimierung für Microsoft 365](./network-planning-and-performance.md)befolgen. Das Primäre Ziel sollte sein, den Zugriff auf globale Microsoft 365-Dienste aus dem Internet in China nach Möglichkeit zu vermeiden.

- Nutzen Sie Ihr vorhandenes privates Netzwerk, um Microsoft 365 Netzwerkdatenverkehr zwischen chinesischen Büronetzwerken und Standorten zu übertragen, die aus dem öffentlichen Internet außerhalb Chinas ausgehend werden. Fast jeder Standort außerhalb Chinas bietet einen klaren Vorteil. Netzwerkadministratoren können die Optimierung weiter optimieren, indem sie in Bereichen mit geringer Latenz eine Verbindung mit dem [globalen Microsoft-Netzwerk](/azure/networking/microsoft-global-network)herstellen. Beispiele sind Hongkong, Japan und Südkorea.
- Konfigurieren Sie Benutzergeräte für den Zugriff auf das Unternehmensnetzwerk über eine VPN-Verbindung, damit Microsoft 365 Datenverkehr die private Verbindung des Unternehmensnetzwerks übertragen kann. Stellen Sie sicher, dass VPN-Clients entweder nicht für die Verwendung von geteilten Tunneln konfiguriert sind oder dass Benutzergeräte so konfiguriert sind, dass geteiltes Tunneling für Microsoft 365 Datenverkehr ignoriert wird. Weitere Informationen zum Optimieren der VPN-Konnektivität für Teams und Echtzeitmediendatenverkehr finden Sie in [diesem Abschnitt.](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china)
- Konfigurieren Sie Ihr Netzwerk so, dass es den gesamten Microsoft 365 Datenverkehr über Ihre private Verbindung leitet. Wenn Sie das Datenverkehrsvolumen auf Ihrem privaten Link minimieren müssen, können Sie nur Endpunkte in der Kategorie **"Optimieren"** weiterleiten und Anforderungen an **Allow-** und **Default-Endpunkte** für die Übertragung des Internets zulassen. Dadurch wird die Leistung verbessert und der Bandbreitenverbrauch minimiert, indem der optimierte Datenverkehr auf kritische Dienste beschränkt wird, die besonders anfällig für hohe Latenz und Paketverluste sind.
- Verwenden Sie nach Möglichkeit UDP anstelle von TCP für Livemedienstreamingdatenverkehr, z. B. für Teams. UDP bietet eine bessere Leistung beim Live-Medienstreaming als TCP.

Informationen zum selektiven Weiterleiten Microsoft 365 Datenverkehrs finden Sie unter [Verwalten Office 365 Endpunkte.](managing-office-365-endpoints.md) Eine Liste aller urls und IP-Adressen weltweit Office 365 finden Sie unter [Office 365 URLs und IP-Adressbereiche.](urls-and-ip-address-ranges.md)

![Microsoft 365 Datenverkehr – optimiert](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Bewährte Methoden für Benutzer

Benutzer in China, die von Remotestandorten wie Heimen, Cafés, Cafés und Zweigstellen ohne Verbindung zu Unternehmensnetzwerken eine Verbindung mit globalen Microsoft 365 Mandanten herstellen, können eine schlechte Netzwerkleistung aufweisen, da der Datenverkehr zwischen ihren Geräten und Microsoft 365 die überlasteten länderübergreifenden Netzwerkverbindungen Chinas durchqueren muss.

Wenn grenzübergreifende private Netzwerke und/oder VPN-Zugriff auf das Unternehmensnetzwerk keine Option sind, können Leistungsprobleme pro Benutzer weiterhin behoben werden, indem Ihre in China ansässigen Benutzer entsprechend diesen bewährten Methoden geschult werden.

- Nutzen Sie umfangreiche Office Clients, die das Zwischenspeichern unterstützen (z. B. Outlook, Teams, OneDrive usw.), und vermeiden Sie webbasierte Clients. Office Clientzwischenspeicherung und Offlinezugriffsfeatures können die Auswirkungen von Netzwerküberlastung und Latenz erheblich reduzieren.
- Wenn Ihr Microsoft 365 Mandant mit der _Audiokonferenzfunktion_ konfiguriert wurde, können Teams Benutzer über das Telefonfestnetz (Public Switched Telephone Network, PSTN) an Besprechungen teilnehmen. Weitere Informationen finden Sie unter [Audiokonferenzen in Office 365](/microsoftteams/audio-conferencing-in-office-365).
- Wenn Bei Benutzern Probleme mit der Netzwerkleistung auftreten, sollten sie ihre IT-Abteilung zur Problembehandlung melden und an den Microsoft-Support eskalieren, wenn Probleme mit Microsoft 365 Diensten verdächtig sind. Nicht alle Probleme werden durch die grenzübergreifende Netzwerkleistung verursacht.

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>Optimieren der Netzwerkleistung von Microsoft Teams Besprechungen für Benutzer in China

Für Organisationen mit globalen Microsoft 365 Mandanten und einer Präsenz in China kann Microsoft 365 Clientleistung für Benutzer in China durch faktoren kompliziert werden, die für die Chinesische Internetarchitektur einzigartig sind. Viele Unternehmen und Schulen haben gute Ergebnisse gemeldet, indem sie diese Anleitung befolgen. Der Bereich ist jedoch auf Benutzernetzwerkstandorte beschränkt, die die Kontrolle über das IT-Netzwerksetup haben, z. B. Bürostandorte oder private/mobile Endpunkte mit VPN-Konnektivität. Microsoft Teams Anrufe und Besprechungen werden häufig von externen Standorten aus verwendet, wie z. B. Home Offices, mobile Standorte, unterwegs und Cafés. Da Anrufe und Besprechungen von Mediendatenverkehr in Echtzeit abhängen, sind diese Teams besonders anfällig für Netzwerküberlastung.

Daher hat Microsoft eine Partnerschaft mit Telekommunikationsanbietern eingegangen, um Teams und Skype for Business Online-Echtzeitmediendatenverkehr über einen qualitativ hochwertigeren, privilegierten Netzwerkpfad zwischen nationalen und öffentlichen Internetverbindungen in China und den Teams- und Skype-Diensten in der Microsoft 365 globalen Cloud durchzuführen. Diese Funktion hat zu einer mehr als zehnfachen Verbesserung bei Paketverlusten und anderen wichtigen Metriken geführt, die sich auf die Benutzererfahrung auswirken.

>[!IMPORTANT]
>Derzeit beziehen sich diese Verbesserungen nicht auf die Teilnahme an Microsoft Live Events-Besprechungen, z. B. große Livekonferenzen oder Besprechungen im Stil von "City Hall" mit Teams oder Microsoft Stream. Um eine Liveereignisbesprechung anzuzeigen, müssen Benutzer in China ein privates Netzwerk oder eine SDWAN/VPN-Lösung verwenden. Die Netzwerkverbesserungen profitieren jedoch von Benutzern, die eine Liveereignisbesprechung präsentieren oder erstellen, da diese Erfahrung als regelmäßige Teams Besprechung für den Produzenten oder Referenten fungiert.

### <a name="organization-network-best-practices-for-teams-meetings"></a>Bewährte Methoden des Organisationsnetzwerks für Teams Besprechungen

Sie müssen überlegen, wie Sie diese Netzwerkverbesserungen nutzen können, angesichts der vorherigen Anleitung, um eine private Netzwerkerweiterung in Betracht zu ziehen, um eine überlastung über das netzwerkübergreifende Netzwerk zu vermeiden. Es gibt zwei allgemeine Optionen für Organisations-Office-Netzwerke:

1. Nichts Neues tun. Folgen Sie weiterhin den früheren Anleitungen zur Umgehung des privaten Netzwerks, um eine überlastungsübergreifender Grenzen zu vermeiden. Teams Mediendatenverkehr in Echtzeit nutzt dieses Setup wie zuvor.
2. Implementieren sie ein Split/Hybrid-Muster.
   - Verwenden Sie die vorherige Anleitung für den gesamten Datenverkehr, der zur Optimierung gekennzeichnet ist, mit Ausnahme Teams Besprechungen und Anrufen von Echtzeitmediendatenverkehr.
   - Weiterleiten Teams Besprechung und Anrufen von Echtzeitmediendatenverkehr über das öffentliche Internet. In den folgenden Informationen finden Sie Einzelheiten zum Identifizieren des Echtzeit-Mediennetzwerkdatenverkehrs.

Das Senden Teams Medienaudio- und Videodatenverkehr in Echtzeit über das öffentliche Internet, das die höhere Qualität der Konnektivität verwendet, kann zu erheblichen Kosteneinsparungen führen, da der Datenverkehr kostenlos und nicht über ein privates Netzwerk gesendet werden muss. Es kann ähnliche zusätzliche Vorteile geben, wenn Benutzer auch SDWAN- oder VPN-Clients verwenden. Einige Organisationen bevorzugen möglicherweise auch, mehr ihrer Daten öffentliche Internetverbindungen als allgemeine Vorgehensweise zu durchlaufen.

Die gleichen Optionen können auch für SDWAN- oder VPN-Konfigurationen gelten. Beispielsweise verwendet ein Benutzer ein SDWAN oder VPN, um Microsoft 365 Datenverkehr an das Unternehmensnetzwerk weiterzuleiten und dann die private Erweiterung dieses Netzwerks zu nutzen, um eine länderübergreifende Überlastung zu vermeiden. Das SDWAN oder VPN des Benutzers kann jetzt so konfiguriert werden, dass Teams Besprechungs- und Anruf-Echtzeitdatenverkehr vom VPN-Routing ausgeschlossen wird. Diese VPN-Konfiguration wird als geteilter Tunnel bezeichnet. Weitere Informationen finden Sie unter ["Geteilter VPN-Tunneling" für Office 365.](/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel)

Sie können Ihre SDWAN oder Ihr VPN auch weiterhin für den gesamten Microsoft 365 Datenverkehr verwenden, einschließlich für Microsoft Teams Echtzeitdatenverkehr. Microsoft hat keine Empfehlungen zur Verwendung von SDWAN- oder VPN-Lösungen.

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Bewährte Methoden für private, mobile und Benutzernetzwerke für Teams Besprechungen

Benutzer in China können diese Verbesserungen nutzen, indem sie einfach eine Verbindung mit dem öffentlichen Internetdienst in China über eine Festnetz- oder Mobilverbindung herstellen. Teams Echtzeit-Medienaudio- und -videodatenverkehr im öffentlichen Internet profitieren direkt von verbesserter Konnektivität und Qualität.

Daten aus anderen Microsoft 365 Diensten – und anderer Datenverkehr in Teams, z. B. Chat oder Dateien – profitieren jedoch nicht direkt von diesen Verbesserungen. Für Benutzer außerhalb des Organisationsnetzwerks kann es weiterhin zu einer schlechten Netzwerkleistung für diesen Datenverkehr führen. Wie in diesem Artikel beschrieben, können Sie diese Auswirkungen mithilfe eines VPN oder SDWAN verringern. Sie können auch festlegen, dass Ihre Benutzer Rich-Desktopclients über Webclients verwenden, die in-App-Caching unterstützen, um Netzwerkprobleme zu beheben.

### <a name="identifying-teams-real-time-media-network-traffic"></a>Identifizieren von Teams Echtzeit-Mediennetzwerkdatenverkehr

Zum Konfigurieren eines Netzwerkgeräts oder eines VPN/SDWAN-Setups müssen Sie nur die Teams Medienaudio- und Videodatenverkehr in Echtzeit ausschließen. Die Datenverkehrsdetails finden Sie für ID 11 in der offiziellen Liste Office 365 [URLs und IP-Adressbereiche.](urls-and-ip-address-ranges.md#skype-for-business-online-and-microsoft-teams) Alle anderen Netzwerkkonfigurationen sollten unverändert bleiben.

Microsoft arbeitet kontinuierlich daran, die Microsoft 365 Benutzererfahrung und die Leistung von Clients über eine möglichst breite Palette von Netzwerkarchitekturen und -merkmalen zu verbessern. Besuchen Sie die [Office 365 Networking Tech Community,](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking) um eine Unterhaltung zu starten oder daran teilzunehmen, Ressourcen zu finden und Featureanforderungen und Vorschläge zu übermitteln.

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkplanung und Leistungsoptimierung für Microsoft 365](./network-planning-and-performance.md)

[Prinzipien der Microsoft 365-Netzwerkkonnektivität](microsoft-365-network-connectivity-principles.md)

[Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md)

[URLs und IP-Adressbereiche für Office 365](urls-and-ip-address-ranges.md)

[Globales Microsoft-Netzwerk](/azure/networking/microsoft-global-network)
