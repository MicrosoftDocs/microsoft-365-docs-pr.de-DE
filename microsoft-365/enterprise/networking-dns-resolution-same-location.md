---
title: 'Schritt 2: Konfigurieren von lokalen Internetverbindungen für jedes Büro'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Für eine bessere Leistung müssen Sie Ihre DNS-Auflösung nachvollziehen und konfigurieren können.
ms.openlocfilehash: b47131b9a5f854c630f5d54bd4d3b4738ed953b3
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370302"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a>Schritt 2: Konfigurieren von lokalen Internetverbindungen für jedes Büro

*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![Phase 1 – Netzwerken](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Stellen Sie in Schritt 2 sicher, dass jedes Ihrer Büros über eine lokale Internetverbindung verfügt und lokale DNS-Server verwendet. Beides ist erforderlich, um Verbindungslatenz zu reduzieren und sicherzustellen, dass lokale Clientcomputer Verbindungen zum nächsten Einstiegspunkt für cloudbasierte Microsoft 365-Dienste herstellen.

In herkömmlichen Netzwerken für große Organisationen wird der Internetdatenverkehr über das Netzwerkbackbone zu einer zentralen Internetverbindung geleitet. Dies eignet sich nicht gut zur Optimierung der Leistung für eine global verteilte SaaS-Infrastruktur (Software-as-a-Service), die die Office 365- und Intune-Produkte in Microsoft 365 umfasst.

Das globale Microsoft-Netzwerk umfasst eine *Distributed Service Frontdoor-Infrastruktur*, ein hochgradig verfügbares und skalierbares Netzwerk-Edge mit geografisch verteilten Standorten. Es beendet die Endbenutzerverbindungen auf einem Frontdoor-Server und leitet den Endbenutzerdatenverkehr innerhalb des globalen Microsoft-Netzwerks effizient weiter.

![Das Globale Microsoft-Netzwerk](./media/networking-dns-resolution-same-location/microsoft-global-network.png)

Die beste Leistung wird erzielt, wenn lokale Clients auf einen Frontdoor-Standort zugreifen, der ihnen geografisch am nächsten ist, statt Datenverkehr über ein Netzwerk-Backbone und zum Frontdoor-Server zu senden, der der zentralen Internetverbindung der Organisation am nächsten ist.

Hier ein Beispiel:

![Beispiel für das Globale Microsoft-Netzwerk](./media/networking-dns-resolution-same-location/microsoft-global-network-example.png)

Ein Benutzer in der Pariser Zweigniederlassung möchte auf eine SharePoint Online-Website zugreifen:

1. Er sendet eine DNS-Abfrage, um einen Namen aufzulösen, z. B. "contoso.sharepoint.com". 
2. Der vom Internetdienstanbieter bereitgestellte DNS-Server leitet diese Abfrage an einen Microsoft-DNS-Server weiter.
3. Die Microsoft-DNS-Server gleichen die Quell-IP-Adresse der weitergeleiteten DNS-Abfrage mit der Region der Welt ab, der diese Adresse zugewiesen ist. Der Microsoft-DNS-Server antwortet mit der IP-Adresse der nächstgelegenen Frontdoor des Microsoft-Netzwerks in Europa.
4. Der ISP-DNS-Server sendet diese IP-Adresse an den Benutzer.
5. Der Benutzer initiiert eine Verbindung mit dem SharePoint-Server über die Europa-Frontdoor.

Um eine Clientanforderung an den geografisch nächsten Frontdoor-Server zu leiten, verwenden die DNS-Server von Microsoft die DNS-Abfragen, die der anfänglichen Verbindungsanforderung des Clients entsprechen. Daher gilt für die niedrigste Netzwerklatenz Folgendes:

- Alle Büros Ihrer Organisation sollten eine lokale Internetverbindung für den Netzwerkdatenverkehr der Kategorie [Optimieren](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) haben.
- Jede lokale Internetverbindung sollte einen regionalen DNS-Server für ausgehenden Internetdatenverkehr von diesem Ort verwenden.

Weitere Informationen finden Sie unter [Lokaler Ausgang von Netzwerkverbindungen](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally). 

Als Zwischenprüfung können Sie die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step2) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![Schritt 3](./media/stepnumbers/Step3.png)|[Vermeiden von Spitzkehren für Netzwerke](networking-avoid-network-hairpins.md)|
