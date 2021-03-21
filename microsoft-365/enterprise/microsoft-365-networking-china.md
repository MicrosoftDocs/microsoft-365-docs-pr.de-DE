---
title: Microsoft 365– Optimierung der globalen Mandantenleistung für Benutzer in China
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
search.appverid: MET150
f1.keywords:
- NOCSH
description: Dieser Artikel enthält Anleitungen zur Optimierung der Netzwerkleistung für Chinesische Benutzer globaler Microsoft 365-Mandanten.
ms.openlocfilehash: 2ba0509425b60aec35d29b23b84e3b6346d2f5cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923194"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Microsoft 365– Optimierung der globalen Mandantenleistung für Benutzer in China

>[!IMPORTANT]
>Diese Anleitung gilt speziell für Verwendungsszenarien, in denen **Microsoft 365-Benutzer in China** eine Verbindung mit einem globalen Microsoft **365-Mandanten herstellen.** Diese Anleitung gilt **nicht** für Mandanten in Office 365, betrieben von 21Vianet.

Für Unternehmen mit globalen Microsoft 365-Mandanten und einer Unternehmenspräsenz in China kann die Leistung von Microsoft 365-Clients für chinabasierte Benutzer durch Faktoren kompliziert werden, die für die Internetarchitektur von China Telco einzigartig sind.

China ISPs verfügen über regulierte Verbindungen mit dem globalen öffentlichen Internet, die über Umkreisgeräte verfügen, die für eine hohe Überlastung des grenzübergreifenden Netzwerks anfällig sind. Diese Überlastung führt zu Paketverlusten und Wartezeiten für den ganzen Internetdatenverkehr, der nach China und aus China führt.

![Microsoft 365-Datenverkehr – nicht optimiert](../media/O365-networking/China-O365-unoptimized.png)

Paketverlust und Latenz beeinträchtigen die Leistung von Netzwerkdiensten, insbesondere Dienste, die einen großen Datenaustausch (z. B. große Dateiübertragungen) oder eine nahezu echtzeitnahe Leistung (Audio- und Videoanwendungen) erfordern.

Das Ziel dieses Themas besteht in der Bereitstellung bewährter Methoden für die Abmildung der Auswirkungen der grenzüberschreitenden Netzwerküberlastung chinas auf Microsoft 365-Dienste. In diesem Thema werden keine anderen häufigen Leistungsprobleme der letzten Meile, z. B. Probleme mit hoher Paketlatenz aufgrund komplexer Routings innerhalb von Chinesischen Netzbetreibern, beschrieben.

## <a name="corporate-network-best-practices"></a>Bewährte Methoden für Unternehmensnetzwerke

Viele Unternehmen mit globalen Microsoft 365-Mandanten und -Benutzern in China haben private Netzwerke implementiert, die Unternehmensnetzwerkdatenverkehr zwischen Chinesischen Bürostandorten und Standorten auf der ganzen Welt im Zusammenhang mit dem Unternehmensnetzwerk transportieren. Diese Unternehmen können diese Netzwerkinfrastruktur nutzen, um eine grenzüberschreitende Netzwerküberlastung zu vermeiden und ihre Microsoft 365-Dienstleistung in China zu optimieren.

>[!IMPORTANT]
>Wie bei allen privaten WAN-Implementierungen sollten Sie immer die gesetzlichen Anforderungen für Ihr Land und/oder Ihre Region konsultieren, um sicherzustellen, dass Ihre Netzwerkkonfiguration den Anforderungen entspricht.

Als ersten Schritt ist es wichtig, dass Sie unsere Benchmark-Netzwerkanleitungen unter Netzwerkplanung und Leistungsoptimierung [für Microsoft 365 befolgen.](./network-planning-and-performance.md) Das Hauptziel sollte sein, den Zugriff auf globale Microsoft 365-Dienste aus dem Internet in China möglichst zu vermeiden.

- Nutzen Sie Ihr vorhandenes privates Netzwerk, um Microsoft 365-Netzwerkdatenverkehr zwischen chinesischen Büronetzwerken und Off-Office-Standorten zu übertragen, die über das öffentliche Internet außerhalb Chinas abziehen. Fast jeder Standort außerhalb Chinas bietet einen eindeutigen Vorteil. Netzwerkadministratoren können die Optimierung weiter optimieren, indem sie sich in Bereichen mit niedriger Latenz mit dem globalen [Microsoft-Netzwerk verbinden.](/azure/networking/microsoft-global-network) Hongkong, Japan und Südkorea sind Beispiele.
- Konfigurieren Sie Benutzergeräte so, dass sie über eine VPN-Verbindung auf das Unternehmensnetzwerk zugreifen, damit Microsoft 365-Datenverkehr die private Off-End-Verbindung des Unternehmensnetzwerks übertragen kann. Stellen Sie sicher, dass VPN-Clients entweder nicht für die Verwendung von geteilten Tunneln konfiguriert sind oder dass Benutzergeräte so konfiguriert sind, dass geteilter Tunneling für Microsoft 365-Datenverkehr ignoriert wird.
- Konfigurieren Sie Ihr Netzwerk so, dass der gesamte Microsoft 365-Datenverkehr über Ihre private Off-Off -Verbindung geroutet wird. Wenn Sie das Datenverkehrsvolumen auf Ihrer privaten Verbindung minimieren müssen, können Sie auswählen, dass Endpunkte nur in der **Kategorie Optimieren** geleitet werden, und Anforderungen an **Allow-** und **Default-Endpunkte** die Übertragung des Internets erlauben. Dadurch wird die Leistung verbessert und die Bandbreitenauslastung minimiert, indem optimierter Datenverkehr auf kritische Dienste begrenzt wird, die besonders auf hohe Latenz und Paketverluste reagieren.
- Verwenden Sie nach Möglichkeit UDP anstelle von TCP für Live-Medienstreaming-Datenverkehr, z. B. für Teams. UDP bietet eine bessere Livemedienstreamingleistung als TCP.

Informationen zum selektiven Routen von Microsoft 365-Datenverkehr finden Sie unter [Managing Office 365 endpoints](managing-office-365-endpoints.md). Eine Liste aller weltweiten Office 365-URLs und IP-Adressen finden Sie unter [Office 365-URLs und IP-Adressbereiche](urls-and-ip-address-ranges.md).

![Microsoft 365-Datenverkehr – optimiert](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Bewährte Methoden für Benutzer

Benutzer in China, die eine Verbindung mit globalen Microsoft 365-Mandanten von Remotestandorten wie Heimen, Cafés, Hotels und Zweigstellen ohne Verbindung zu Unternehmensnetzwerken herstellen, können eine schlechte Netzwerkleistung erleben, da der Datenverkehr zwischen ihren Geräten und Microsoft 365 chinas überlastete grenzübergreifende Netzwerkschaltungen durchqueren muss.

Wenn grenzüberschreitende private Netzwerke und/oder VPN-Zugriff auf das Unternehmensnetzwerk keine Option sind, können Leistungsprobleme pro Benutzer weiterhin durch Schulung Ihrer in China ansässigen Benutzer zur Anwendung dieser bewährten Methoden abgemildert werden.

- Nutzen Sie umfangreiche Office-Clients, die zwischenspeichern (z. B. Outlook, Teams, OneDrive usw.) unterstützen und webbasierte Clients vermeiden. Office-Client-Zwischenspeicherung und Offlinezugriffsfeatures können die Auswirkungen von Netzwerküberlastung und Latenz erheblich reduzieren.
- Wenn Ihr Microsoft 365-Mandant mit der _Audiokonferenzfunktion_ konfiguriert wurde, können Teams-Benutzer über das Festnetz (Public Switched Telephone Network, PSTN) an Besprechungen teilnehmen. Weitere Informationen finden Sie [unter Audiokonferenzen in Office 365](/microsoftteams/audio-conferencing-in-office-365).
- Wenn Benutzer Probleme mit der Netzwerkleistung haben, sollten sie sich zur Problembehandlung an ihre IT-Abteilung melden und an den Microsoft-Support eskalieren, wenn Probleme mit Microsoft 365-Diensten vermutet werden. Nicht alle Probleme werden durch die grenzüberschreitende Netzwerkleistung verursacht.

Microsoft arbeitet kontinuierlich daran, die Benutzerfreundlichkeit von Microsoft 365 und die Leistung von Clients über eine möglichst breite Palette von Netzwerkarchitekturen und -merkmalen zu verbessern. Besuchen Sie [die Office 365 Tech Community,](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) um eine Unterhaltung zu starten oder an einer Unterhaltung zu teilnehmen, Ressourcen zu finden und Featureanforderungen und Vorschläge zu übermitteln.

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkplanung und Leistungsoptimierung für Microsoft 365](./network-planning-and-performance.md)

[Prinzipien der Microsoft 365-Netzwerkkonnektivität](microsoft-365-network-connectivity-principles.md)

[Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md)

[URLs und IP-Adressbereiche für Office 365](urls-and-ip-address-ranges.md)

[Globales Microsoft-Netzwerk](/azure/networking/microsoft-global-network)