---
title: Microsoft 365 der globalen Mandantenleistungsoptimierung für Benutzer in China
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
description: Dieser Artikel enthält Anleitungen zur Optimierung der Netzwerkleistung für Chinesische Benutzer globaler Microsoft 365 Mandanten.
ms.openlocfilehash: e330e892b584c805bded2228381e74e6a4fa615a
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615195"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Microsoft 365 der globalen Mandantenleistungsoptimierung für Benutzer in China

>[!IMPORTANT]
>Diese Anleitung gilt speziell für Verwendungsszenarien, in denen **Microsoft 365 benutzer in China** eine Verbindung mit einem globalen mandanten Microsoft 365 **herstellen.** Diese Anleitung gilt **nicht** für Mandanten in Office 365 betrieben von 21Vianet.

Für Unternehmen mit globalen Microsoft 365 Mandanten und einer Unternehmenspräsenz in China kann die Microsoft 365-Clientleistung für chinabasierte Benutzer durch Faktoren kompliziert werden, die für die Internetarchitektur von China Telco einzigartig sind.

China-ISPs verfügen über regulierte Verbindungen mit dem globalen öffentlichen Internet, die über Umkreisgeräte verfügen, die für eine hohe Überlastung des grenzübergreifenden Netzwerks anfällig sind. Diese Überlastung führt zu Paketverlusten und Wartezeiten für den ganzen Internetdatenverkehr, der nach China und aus China führt.

![Microsoft 365 Datenverkehr – nicht optimiert](../media/O365-networking/China-O365-unoptimized.png)

Paketverluste und Wartezeiten beeinträchtigen die Leistung von Netzwerkdiensten, insbesondere Dienste, die einen großen Datenaustausch (z. B. große Dateiübertragungen) oder eine nahezu echtzeitnahe Leistung (Audio- und Videoanwendungen) erfordern.

Das Ziel dieses Themas besteht in der Bereitstellung bewährter Methoden zur Minderung der Auswirkungen der grenzüberschreitenden Netzwerküberlastung chinas auf Microsoft 365 Dienste. In diesem Thema werden keine anderen häufigen Leistungsprobleme der letzten Meile, z. B. Probleme mit hoher Paketlatenz aufgrund komplexer Routings innerhalb von Chinesischen Netzbetreibern, beschrieben.

## <a name="corporate-network-best-practices"></a>Bewährte Methoden für Unternehmensnetzwerke

Viele Unternehmen mit globalen Microsoft 365 und Benutzern in China haben private Netzwerke implementiert, die den Unternehmensnetzwerkverkehr zwischen Chinesischen Bürostandorten und Standorten auf der ganzen Welt im Ausland transportieren. Diese Unternehmen können diese Netzwerkinfrastruktur nutzen, um grenzübergreifende Netzwerküberlastungen zu vermeiden und Microsoft 365 leistung in China zu optimieren.

>[!IMPORTANT]
>Wie bei allen privaten WAN-Implementierungen sollten Sie immer die gesetzlichen Anforderungen für Ihr Land und/oder Ihre Region konsultieren, um sicherzustellen, dass Ihre Netzwerkkonfiguration den Anforderungen entspricht.

Als ersten Schritt ist es wichtig, dass Sie unsere Benchmark-Netzwerkanleitungen unter Netzwerkplanung und [Leistungsoptimierung](./network-planning-and-performance.md)für Microsoft 365. Das Hauptziel sollte sein, den Zugriff auf globale Microsoft 365 über das Internet in China möglichst zu vermeiden.

- Nutzen Sie Ihr vorhandenes privates Netzwerk, um Microsoft 365 Netzwerkverkehr zwischen chinesischen Büronetzwerken und Off-Office-Standorten zu übertragen, die über das öffentliche Internet außerhalb Chinas abziehen. Fast jeder Standort außerhalb Chinas bietet einen eindeutigen Vorteil. Netzwerkadministratoren können die Optimierung weiter optimieren, indem sie sich in Bereichen mit niedriger Latenz mit dem globalen [Microsoft-Netzwerk verbinden.](https://docs.microsoft.com/azure/networking/microsoft-global-network) Hongkong, Japan und Südkorea sind Beispiele.
- Konfigurieren Sie Benutzergeräte so, dass sie über eine VPN-Verbindung auf das Unternehmensnetzwerk zugreifen, damit Microsoft 365 die private Off-Off -Verbindung des Unternehmensnetzwerks übertragen kann. Stellen Sie sicher, dass die VPN-Clients entweder nicht für die Verwendung von geteilten Tunneln konfiguriert sind oder dass Benutzergeräte so konfiguriert sind, dass sie den geteilten Tunneling für den Microsoft 365 ignorieren. Weitere Informationen zum Optimieren der VPN-Konnektivität für Teams und Echtzeitmedienverkehr finden Sie [in diesem Abschnitt](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china).
- Konfigurieren Sie Ihr Netzwerk so, dass Microsoft 365 datenverkehr über Ihre private Off-Off -Verbindung weiterverroutet wird. Wenn Sie das Datenverkehrsvolumen auf Ihrer privaten Verbindung minimieren müssen, können Sie auswählen, dass Endpunkte nur in der **Kategorie Optimieren** geleitet werden, und Anforderungen an **Allow-** und **Default-Endpunkte** die Übertragung des Internets erlauben. Dadurch wird die Leistung verbessert und die Bandbreitenauslastung minimiert, indem optimierter Datenverkehr auf kritische Dienste begrenzt wird, die besonders auf hohe Latenz und Paketverluste reagieren.
- Verwenden Sie nach Möglichkeit UDP anstelle von TCP für Livemedienstreamingverkehr, z. B. für Teams. UDP bietet eine bessere Livemedienstreamingleistung als TCP.

Informationen zum selektiven Routen von Datenverkehr Microsoft 365 finden Sie unter [Managing Office 365 endpoints](managing-office-365-endpoints.md). Eine Liste aller weltweiten Office 365 URLs und IP-Adressen finden Sie [unter Office 365 URLs und IP-Adressbereiche](urls-and-ip-address-ranges.md).

![Microsoft 365 Datenverkehr – optimiert](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Bewährte Methoden für Benutzer

Benutzer in China, die eine Verbindung mit globalen Microsoft 365-Mandanten von Remotestandorten wie Heimen, Cafés, Hotels und Zweigstellen ohne Verbindung zu Unternehmensnetzwerken herstellen, können eine schlechte Netzwerkleistung erleben, da der Datenverkehr zwischen ihren Geräten und Microsoft 365 chinas überlastete grenzübergreifende Netzwerkschaltungen durchqueren muss.

Wenn grenzüberschreitende private Netzwerke und/oder VPN-Zugriff auf das Unternehmensnetzwerk keine Option sind, können Leistungsprobleme pro Benutzer weiterhin durch Schulung Ihrer in China ansässigen Benutzer zur Anwendung dieser bewährten Methoden abgemildert werden.

- Nutzen Sie Office Clients, die zwischenspeichern (z. B. Outlook, Teams, OneDrive usw.), und vermeiden Sie webbasierte Clients. Office Client zwischenspeichern und Offlinezugriffsfeatures können die Auswirkungen von Netzwerküberlastung und Latenz erheblich reduzieren.
- Wenn Ihr Microsoft 365-Mandant mit der  Audiokonferenzfunktion konfiguriert wurde, können Teams Benutzer über das Festnetz (Public Switched Telephone Network, PSTN) an Besprechungen teilnehmen. Weitere Informationen finden Sie unter [Audiokonferenzen in Office 365](/microsoftteams/audio-conferencing-in-office-365).
- Wenn Benutzer Probleme mit der Netzwerkleistung haben, sollten sie sich zur Problembehandlung an ihre IT-Abteilung melden und an den Microsoft-Support eskalieren, wenn Probleme mit Microsoft 365 auftreten. Nicht alle Probleme werden durch die grenzüberschreitende Netzwerkleistung verursacht.

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>Optimieren Microsoft Teams Netzwerkleistung von Besprechungen für Benutzer in China  

Für Organisationen mit globalen Microsoft 365 mandanten und einer Anwesenheit in China kann die Microsoft 365 der Clientleistung für chinabasierte Benutzer durch Faktoren kompliziert werden, die für die Chinesische Internetarchitektur einzigartig sind. Viele Unternehmen und Schulen haben gute Ergebnisse gemeldet, indem sie diese Anleitungen folgen. Der Bereich ist jedoch auf Benutzernetzwerkstandorte beschränkt, die die Kontrolle über das Setup des IT-Netzwerks haben, z. B. Bürostandorte oder heim-/mobile Endpunkte mit VPN-Konnektivität. Microsoft Teams Anrufe und Besprechungen werden häufig von externen Standorten wie Home Offices, mobilen Standorten, unterwegs und Cafés verwendet. Da Anrufe und Besprechungen auf Dem Mediendatenverkehr in Echtzeit beruhen, Teams die Netzwerküberlastung besonders sensibel.

Aus diesem Grund hat Microsoft eine Partnerschaft mit Telekommunikationsanbietern hergestellt, um Teams- und Skype for Business Online-Mediendatenverkehr über einen qualitativ hochwertigen, bevorzugten Netzwerkpfad zwischen nationalen und öffentlichen Internetverbindungen in China und den Teams- und Skype-Diensten in der globalen Microsoft 365-Cloud zu übertragen. Diese Funktion hat zu einer mehr als zehnfachen Verbesserung des Paketverlusts und anderer wichtiger Metriken geführt, die sich auf die Benutzererfahrung auswirken.

>[!IMPORTANT]
>Derzeit werden diese Verbesserungen nicht auf die Teilnahme an Microsoft Live Events-Besprechungen wie großen Übertragungen oder "Rathaus"-Stilbesprechungen mit Teams oder Microsoft Stream adressiert. Um eine Live-Ereignis-Besprechung anzeigen zu können, müssen Benutzer in China ein privates Netzwerk oder eine SDWAN/VPN-Lösung verwenden. Die Netzwerkverbesserungen profitieren jedoch von Benutzern, die eine Live-Ereignis-Besprechung präsentieren oder herstellen, da diese Erfahrung als regelmäßige Teams des Produzenten oder Moderators dient.

### <a name="organization-network-best-practices-for-teams-meetings"></a>Bewährte Methoden des Organisationsnetzwerks für Teams Besprechungen

Sie müssen überlegen, wie Sie diese Netzwerkverbesserungen nutzen können, da in den vorherigen Anleitungen eine private Netzwerkerweiterung in Betracht zu ziehen ist, um grenzübergreifende Netzwerküberlastungen zu vermeiden. Es gibt zwei allgemeine Optionen für Organisationsbüronetzwerke:

1.  Nichts Neues tun. Befolgen Sie weiterhin die früheren Anleitungen zur Umgehung privater Netzwerke, um eine grenzüberschreitende Überlastung zu vermeiden. Teams Echtzeitmediendatenverkehr nutzt diese Einrichtung wie zuvor.
2.  Implementieren Eines geteilten/hybriden Musters. 

  - Verwenden Sie die vorherige Anleitung für den datenverkehr, der zur Optimierung gekennzeichnet ist, außer Teams Besprechungen und aufrufenden Mediendatenverkehr in Echtzeit.

  - Routen Teams Besprechung und Aufrufen von Echtzeitmediendatenverkehr über das öffentliche Internet. In den folgenden Informationen finden Sie Spezifisches zum Identifizieren des Echtzeitdatenverkehrs im Mediennetzwerk.

Das Senden Teams Audio- und Videodatenverkehr in Echtzeit über das öffentliche Internet, bei dem die Konnektivität mit höherer Qualität verwendet wird, kann zu erheblichen Kosteneinsparungen führen, da es kostenlos und nicht kostenpflichtig ist, diesen Datenverkehr über ein privates Netzwerk zu senden. Es kann ähnliche zusätzliche Vorteile geben, wenn Benutzer auch SDWAN- oder VPN-Clients verwenden. Einige Organisationen bevorzugen möglicherweise auch, dass mehr ihrer Daten öffentliche Internetverbindungen durchlaufen, wie allgemein üblich.

Die gleichen Optionen können für SDWAN- oder VPN-Konfigurationen gelten. Beispielsweise verwendet ein Benutzer einen SDWAN oder VPN, um Microsoft 365-Datenverkehr an das Unternehmensnetzwerk weiter zu routen und dann die private Erweiterung dieses Netzwerks zu nutzen, um eine grenzüberschreitende Überlastung zu vermeiden. SdWAN oder VPN des Benutzers können nun so konfiguriert werden, dass Teams besprechungs- und aufrufenden Echtzeitdatenverkehr vom VPN-Routing ausgeschlossen werden. Diese VPN-Konfiguration wird als geteiltes Tunneling bezeichnet. Weitere Informationen finden Sie unter [VPN split tunneling for Office 365.](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel)

Sie können Ihren SDWAN oder VPN auch weiterhin für den Microsoft 365 verwenden, einschließlich Microsoft Teams Echtzeitdatenverkehr. Microsoft hat keine Empfehlungen für die Verwendung von SDWAN- oder VPN-Lösungen.

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Bewährte Methoden für Heim-, Mobil- und Benutzernetzwerke für Teams Besprechungen

Benutzer in China können diese Verbesserungen nutzen, indem sie einfach eine Verbindung mit dem öffentlichen Internetdienst in China über eine Festnetz- oder mobile Verbindung herstellen. Teams Audio- und Videodatenverkehr in Echtzeit im öffentlichen Internet profitieren direkt von verbesserter Konnektivität und Qualität.

Daten von anderen Microsoft 365-Diensten – und anderer Datenverkehr in Teams, z. B. Chats oder Dateien – profitieren jedoch nicht direkt von diesen Verbesserungen. Benutzer außerhalb des Organisationsnetzwerks können weiterhin eine schlechte Netzwerkleistung für diesen Datenverkehr erleben. Wie in diesem Artikel erläutert, können Sie diese Auswirkungen mithilfe eines VPN oder SDWAN mindern. Sie können auch benutzerreiche Desktopclients über Webclients verwenden, die die In-App-Zwischenspeicherung unterstützen, um Netzwerkprobleme zu beheben.

### <a name="identifying-teams-real-time-media-network-traffic"></a>Identifizieren Teams Echtzeitmediennetzwerkdatenverkehrs

Zum Konfigurieren eines Netzwerkgeräts oder eines VPN/SDWAN-Setups müssen Sie nur den Teams Audio- und Videodatenverkehr in Echtzeit ausschließen. Die Datenverkehrsdetails finden Sie für ID 11 in der offiziellen Liste Office 365 [URLs und IP-Adressbereiche](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams). Alle anderen Netzwerkkonfigurationen sollten unverändert bleiben.

Microsoft arbeitet kontinuierlich daran, die Microsoft 365 benutzerfreundlichkeit und die Leistung von Clients über die breiteste Palette von Netzwerkarchitekturen und -merkmalen zu verbessern. Besuchen Sie [Office 365 Networking Tech Community,]( https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking) um eine Unterhaltung zu starten oder an einer Unterhaltung zu teilnehmen, Ressourcen zu finden und Featureanforderungen und Vorschläge zu übermitteln

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkplanung und Leistungsoptimierung für Microsoft 365](./network-planning-and-performance.md)

[Prinzipien der Microsoft 365-Netzwerkkonnektivität](microsoft-365-network-connectivity-principles.md)

[Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md)

[URLs und IP-Adressbereiche für Office 365](urls-and-ip-address-ranges.md)

[Globales Microsoft-Netzwerk](/azure/networking/microsoft-global-network)