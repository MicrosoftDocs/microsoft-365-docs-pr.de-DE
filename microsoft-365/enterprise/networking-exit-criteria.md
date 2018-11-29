---
title: 'Phase 1: Beendigungskriterien für die Netzwerkinfrastruktur'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Stellen Sie sicher, dass Ihre Konfiguration die Kriterien von Microsoft 365 Enterprise für die Netzwerkinfrastruktur erfüllt.
ms.openlocfilehash: 8161fa2b92ffb4c7c4713e9356c0bc1bfec39d07
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867548"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a>Phase 1: Beendigungskriterien für die Netzwerkinfrastruktur

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Wenn Ihre Netzwerkinfrastruktur die folgenden Kriterien erfüllt, können Sie mit Phase 2 fortfahren.

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a>Erforderlich: Ihr Netzwerk ist bereit für Microsoft 365 Enterprise

- Ihre Büros verfügen über ausreichende Internetbandbreite für Microsoft 365-Datenverkehr, einschließlich Office 365, Microsoft Intune sowie Windows 10 Enterprise (Installation und Updates)
- Zentrale Büros für allgemeinen Internetdatenverkehr
- Zweigstellen für Endpunktdatenverkehr der Kategorie „Optimieren“
- Ihr Gesamtnetzwerk ist einer Office 365-Referenzarchitektur zugeordnet.

Gegebenenfalls hilft Ihnen [Schritt 1](networking-provide-bandwidth-cloud-services.md), diese Anforderung zu erfüllen.

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a>Erforderlich: Ihre lokalen Büros verfügen über lokale Internet-Verbindungen und -Namensauflösung.

Sie haben jedes lokale Büro mit Internetzugang über einen lokalen ISP konfiguriert, dessen DNS-Server eine lokale öffentliche IP-Adresse verwenden, die ihren Standort im Internet identifiziert. Dies gewährleistet die bestmögliche Leistung für Benutzer, die auf Office 365 und Intune zugreifen.

Wenn Sie nicht für jede Zweigstelle einen lokalen ISP verwenden, kann die Leistung beeinträchtigt werden, da der Netzwerkverkehr den Backbone einer Organisation passieren muss oder Datenanforderungen von entfernten Front-End-Servern bedient werden.

### <a name="how-to-test"></a>Testen
Verwenden Sie ein Tool oder eine Website von einem Gerät in diesem Büro, um die öffentliche IP-Adresse zu ermitteln, die der Proxy-Server verwendet. Verwenden Sie dazu beispielsweise die [Wie lautet meine IP-Adresse](https://www.whatismypublicip.com/)-Webseite. Diese von Ihrem ISP zugewiesene öffentliche IP-Adresse sollte geografisch lokal sein. Sie sollte nicht aus einem öffentlichen IP-Adressbereich für eine Zentrale oder von einem Anbieter von cloud-basierter Netzwerksicherheit stammen.

Gegebenenfalls hilft Ihnen [Schritt 2](networking-dns-resolution-same-location.md), diese Anforderung zu erfüllen.

<a name="crit-networking-step3"></a>
## <a name="optional-unneeded-network-hairpins-are-removed"></a>Optional: Nicht benötigte Spitzkehren für Netzwerke werden entfernt.

Sie haben Ihre Spitzkehren für Netzwerke untersucht und ihre Auswirkung auf die Leistung für alle Ihre Büros bestimmt. Sie haben Spitzkehren für Netzwerke (wo möglich) entfernt oder mit Ihrem Netzwerk- oder Sicherheitsanbieter zusammengearbeitet, um optimales Microsoft 365-Peering für das Netzwerk zu implementieren.

Gegebenenfalls hilft Ihnen [Schritt 3](networking-avoid-network-hairpins.md) bei dieser Option.


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a>Optional: Sie haben Datenverkehrumgehungen auf Ihren Internetbrowsern und Edge-Geräten konfiguriert.

Sie haben die neuesten PAC-Dateien auf Ihren lokalen Internetbrowsern bereitgestellt, damit der Datenverkehr zu Microsoft 365-DNS-Domänennamen Proxyserver umgeht.

Sie haben Ihre Netzwerkperimetergeräte, wie Firewalls, SSL Break and Inspect und Paketüberprüfungsgeräte, konfiguriert, um Datenverkehrumgehungen zu nutzen oder den Datenverkehr minimal zu den Kategorien „Optimieren“ und „Zulassen“ von Microsoft 365-Endpunkten zu verarbeiten.


### <a name="how-to-test"></a>Testen

Verwenden Sie die Protokollierungstools auf Ihren Netzwerkgeräten, um sicherzustellen, dass der Datenverkehr zu Microsoft 365-Zielen nicht überprüft, entschlüsselt oder anderweitig behindert wird.

Gegebenenfalls hilft Ihnen [Schritt 4](networking-configure-proxies-firewalls.md) bei dieser Option.


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a>Optional: Ihre Clients und Office 365-Anwendungen sind für eine optimale Performance konfiguriert.

Sie haben die Einstellungen für das Transmssion Control Protocol (TCP) auf Ihren Client-Geräten und für die Dienste Exchange Online, Skype for Business Online, SharePoint Online und Project Online optimiert.

Gegebenenfalls hilft Ihnen [Schritt 5](networking-optimize-tcp-performance.md) bei dieser Option.

## <a name="next-phase"></a>Nächste Phase

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)| Die nächste Phase im End-to-End-Bereitstellungsprozess für Microsoft 365 Enterprise ist [identity](identity-infrastructure.md). |
