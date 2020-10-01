---
title: Microsoft 365 globale Mandanten Leistungsoptimierung für Benutzer in China
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
- M365initiative-CoreDeploy
search.appverid: MET150
f1.keywords:
- NOCSH
description: Dieser Artikel enthält Anleitungen für die Optimierung der Netzwerkleistung für China-Benutzer globaler Microsoft 365-Mandanten.
ms.openlocfilehash: 1f5f51991c5950d46c9d835a98bea86bcb354366
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327509"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Microsoft 365 globale Mandanten Leistungsoptimierung für Benutzer in China

>[!IMPORTANT]
>Dieser Leitfaden richtet sich an Verwendungsszenarien, in denen **sich Microsoft 365-Benutzer in China** mit einem **globalen Microsoft 365-Mandanten**verbinden. Diese Anleitung gilt **nicht** für Mandanten in Office 365, die von 21Vianet betrieben werden.

Für Unternehmen mit globalen Microsoft 365-Mandanten und einer Unternehmenspräsenz in China kann die Leistung von Microsoft 365-Clients für in China ansässige Benutzer durch Faktoren, die für die Internet Architektur von China Telco einzigartig sind, erschwert werden.

China-ISPs haben Offshore-Verbindungen mit dem globalen öffentlichen Internet reguliert, die Umkreisgeräte durchlaufen, die anfällig für eine hohe grenzüberschreitende Netzwerküberlastung sind. Diese Überlastung verursacht Paketverlust und Latenz für den gesamten Internet Datenverkehr, der in und aus China kommt.

![Microsoft 365-Datenverkehr-nicht optimiert](../media/O365-networking/China-O365-unoptimized.png)

Paketverlust und-Wartezeit sind schädlich für die Leistung von Netzwerkdiensten, insbesondere für Dienste, die großen Datenaustausch erfordern (beispielsweise große Dateiübertragungen) oder in der Nähe von Echtzeitleistung (Audio-und Videoanwendungen) erforderlich sind.

Das Ziel dieses Themas ist es, bewährte Methoden zur Milderung der Auswirkungen von grenzüberschreitenden Netzwerkengpässen in China auf Microsoft 365-Dienste bereitzustellen. In diesem Thema werden nicht andere häufige Probleme mit der Last-Mile-Leistung behandelt, beispielsweise Probleme mit hoher Paket Wartezeit aufgrund komplexer Weiterleitung innerhalb von China Carriers.

## <a name="corporate-network-best-practices"></a>Bewährte Methoden für das Unternehmensnetzwerk

Viele Unternehmen mit globalen Microsoft 365-Mandanten und-Benutzern in China haben private Netzwerke implementiert, die den Unternehmensnetzwerk Datenverkehr zwischen chinesischen Bürostandorten und Offshore-Standorten auf der ganzen Welt transportieren. Diese Unternehmen können diese Netzwerkinfrastruktur nutzen, um grenzüberschreitende Netzwerküberlastung zu vermeiden und Ihre Microsoft 365-Dienstleistung in China zu optimieren.

>[!IMPORTANT]
>Wie bei allen privaten WAN-Implementierungen sollten Sie immer regulatorische Anforderungen für Ihr Land und/oder Ihre Region konsultieren, um sicherzustellen, dass Ihre Netzwerkkonfiguration eingehaltenwird.

In einem ersten Schritt ist es wichtig, dass Sie unsere Benchmark-Netzwerk Anleitung bei der [Netzwerkplanung und Leistungsoptimierung für Microsoft 365](https://aka.ms/tune)beachten. Das primäre Ziel sollte sein, den Zugriff auf globale Microsoft 365-Dienste aus dem Internet in China möglichst zu vermeiden.

- Nutzen Sie Ihr vorhandenes privates Netzwerk, um den Netzwerkdatenverkehr von Microsoft 365 zwischen chinesischen Office-Netzwerken und Offshore-Standorten zu übertragen, die sich im öffentlichen Internet außerhalb Chinas befinden. Fast alle Standorte außerhalb Chinas werden einen klaren Vorteil bieten. Netzwerkadministratoren können die Optimierung durch egressing in Bereichen mit geringer Latenz Verbindung mit dem [globalen Microsoft-Netzwerk](https://docs.microsoft.com/azure/networking/microsoft-global-network)weiter optimieren. Hong Kong, Japan und Südkorea sind Beispiele.
- Konfigurieren Sie Benutzer Geräte für den Zugriff auf das Unternehmensnetzwerk über eine VPN-Verbindung, damit Microsoft 365-Datenverkehr den privaten Offshore-Link des Unternehmensnetzwerks übertragen kann. Stellen Sie sicher, dass VPN-Clients entweder nicht für die Verwendung des geteilten Tunnels konfiguriert sind oder dass Benutzer Geräte so konfiguriert sind, dass der geteilte Tunnel für den Microsoft 365-Datenverkehr ignoriert wird.
- Konfigurieren Sie Ihr Netzwerk so, dass alle Microsoft 365-Datenströme über Ihren privaten Offshore-Link weitergeleitet werden. Wenn Sie das Volumen des Datenverkehrs auf Ihrem privaten Link minimieren müssen, können Sie festlegen, dass nur Endpunkte in der Kategorie **optimize** weitergeleitet **werden sollen,** und Anforderungen zulassen und **Standard** Endpunkte für den Transit im Internet erlauben. Dadurch wird die Leistung verbessert und die Bandbreitenauslastung minimiert, indem der optimierte Datenverkehr auf kritische Dienste eingeschränkt wird, die für hohe Latenzzeiten und Paketverluste am sensibelsten sind.
- Verwenden Sie, wenn möglich, UDP anstelle von TCP für Live Media-Streaming-Datenverkehr, beispielsweise für Teams. UDP bietet eine bessere Live-Medienstreaming-Leistung als TCP.

Informationen zum selektiven Weiterleiten von Microsoft 365-Datenverkehr finden Sie unter [Managing Office 365 Endpoints](managing-office-365-endpoints.md). Eine Liste aller weltweiten Office 365-URLs und IP-Adressen finden Sie unter [Office 365-URLs und IP-Adressbereiche](urls-and-ip-address-ranges.md).

![Microsoft 365 Traffic-optimiert](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Bewährte Methoden für den Benutzer

Benutzer in China, die eine Verbindung zu globalen Microsoft 365-Mandanten von Remotestandorten wie Homes, Coffee Shops, Hotels und Zweigstellen ohne Verbindung zu Unternehmensnetzwerken herstellen, können eine schlechte Netzwerkleistung erfahren, da der Datenverkehr zwischen ihren Geräten und Microsoft 365 die überlasteten grenzüberschreitenden Netzwerkleitungen in China durchlaufen muss.

Wenn grenzüberschreitende private Netzwerke und/oder VPN-Zugriff in das Unternehmensnetzwerk keine Option sind, können benutzerspezifische Leistungsprobleme weiterhin durch Schulung ihrer in China ansässigen Benutzer verringert werden, um diese bewährten Methoden zu befolgen.

- Verwenden Sie Rich-Office-Clients, die Zwischenspeicherung (beispielsweise Outlook, Teams, OneDrive usw.) unterstützen, und vermeiden Sie webbasierte Clients. Die Office-Clientzwischenspeicherung und die Offlinezugriffs Funktionen können die Auswirkungen von Netzwerküberlastung und-Latenz drastisch reduzieren.
- Wenn Ihr Microsoft 365-Mandant mit dem Feature " _Audiokonferenz_ " konfiguriert wurde, können Teams-Benutzer über das Telefon Festnetz (Public Switched Telephone Network, PSTN) an Besprechungen teilnehmen. Weitere Informationen finden Sie unter [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).
- Wenn Benutzer Probleme mit der Netzwerkleistung auftreten, sollten Sie Ihrer IT-Abteilung zur Problembehandlung Berichten und an den Microsoft-Support eskalieren, wenn ein Problem mit den Microsoft 365-Diensten vermutet wird. Nicht alle Probleme werden durch die Leistung grenzüberschreitender Netzwerke verursacht.

Microsoft arbeitet kontinuierlich an der Verbesserung der Benutzerfreundlichkeit von Microsoft 365 und der Leistung von Clients in einer möglichst breiten Palette von Netzwerkarchitekturen und-Merkmalen. Besuchen Sie die [Office 365-Tech-Community](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) , um eine Unterhaltung zu starten oder an einem Unternehmen teilzunehmen, Ressourcen zu finden und Feature-Anfragen und Vorschläge zu senden

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkplanung und Leistungsoptimierung für Microsoft 365](https://aka.ms/tune)

[Prinzipien der Microsoft 365-Netzwerkkonnektivität](microsoft-365-network-connectivity-principles.md)

[Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md)

[URLs und IP-Adressbereiche für Office 365](urls-and-ip-address-ranges.md)

[Globales Microsoft-Netzwerk](https://docs.microsoft.com/azure/networking/microsoft-global-network)
