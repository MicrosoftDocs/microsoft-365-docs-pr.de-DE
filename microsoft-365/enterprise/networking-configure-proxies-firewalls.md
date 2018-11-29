---
title: 'Schritt 4: Konfigurieren von Datenverkehrumgehungen'
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
description: Verstehen und Konfigurieren von Webbrowsern und Edge-Geräten für Datenverkehrumgehungen zu vertrauenswürdigen Office 365-Speicherorten.
ms.openlocfilehash: f52921fdc0a5329e3fffae687855a653f7026df6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867956"
---
# <a name="step-4-configure-traffic-bypass"></a>Schritt 4: Konfigurieren von Datenverkehrumgehungen

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Da allgemeiner Internetdatenverkehr riskant sein kann, erzwingen typische Organisationsnetzwerke Sicherheit über Edge-Geräte wie Proxyserver, SSL Break and Inspect und Paketüberprüfungsgeräte sowie Systeme zur Verhinderung von Datenverlust. Unter „Verwenden von Netzwerkgeräten oder -lösungen von Drittanbietern für Office 365-Datenverkehr“ finden Sie einige Probleme mit Netzwerk-Abfanggeräten.

Die DNS-Domänennamen und IP-Adressen, die von cloudbasierten Microsoft 365-Diensten verwendet werden, sind bekannt. Zudem sind Datenverkehr und Dienste selbst durch viele Sicherheitsfeatures geschützt. Durch diese Sicherheit und diesen Schutz müssen Ihre Edge-Geräte dies nicht duplizieren. Zwischenziele und doppelte Sicherheitsverarbeitung für Microsoft 365-Datenverkehr können die Leistung erheblich senken.

Der erste Schritt zur Eliminierung von Zwischenzielen und doppelter Sicherheitsverarbeitung ist die Identifizierung von Microsoft 365-Datenverkehr. Microsoft hat die folgenden Typen von DNS-Domänennamen und IP-Adressbereichen, bekannt als Endpunkte, definiert:

- Optimieren – erforderlich für Verbindungen zu jedem Office 365-Dienst, repräsentiert mehr als 75 % der Microsoft 365-Bandbreite, -Verbindungen und -Datenmenge. Diese Endpunkte bilden Microsoft 365-Szenarien ab, die am sensibelsten in Bezug auf Leistung, Latenz und Verfügbarkeit im Netzwerk sind.
- Zulassen – erforderlich für Konnektivität zu speziellen Microsoft 365-Diensten und -Features, die jedoch in Bezug auf Leistung und Latenz im Netzwerk nicht so sensibel sind wie die in der Kategorie „Optimieren“.
 - Standard – repräsentiert Microsoft 365-Dienste und -Abhängigkeiten, für die keine Optimierung erforderlich ist. Sie können standardmäßige Kategorie-Endpunkte als normalen Internetdatenverkehr behandeln.

Sie finden die DNS-Domänennamen und IP-Adressbereiche unter [ https://aka.ms/o365endpoints ](https://aka.ms/o365endpoints).

Microsoft empfiehlt Folgendes:

- Verwenden Sie Proxy Automatic Configuration(PAC)-Skripts für die Internetbrowser Ihrer lokalen Computer, um Ihre Proxyserver für die DNS-Domänennamen cloudbasierter Microsoft 365-Dienste zu umgehen. Das aktuelle Microsoft 365-PAC-Skript finden Sie im Get-Pacfile-PowerShell-Skript.
- Analysieren Sie Ihre Edge-Geräte, um die doppelte Verarbeitung zu bestimmen, und konfigurieren Sie sie dann zum Weiterleiten von Datenverkehr an Optimieren- und Zulassen-Endpunkte ohne Verarbeitung. Dies wird als Umgehung des Datenverkehrs bezeichnet. 
- 
Edge-Geräte umfassen Firewalls, SSL Break and Inspect, Paketüberprüfungsgeräte und Systeme zur Verhinderung von Datenverlust. Um die Konfiguration der Edge-Geräte zu konfigurieren und zu aktualisieren, können Sie ein Skript oder einen REST-Aufruf verwenden, um eine strukturierte Liste von Endpunkten aus dem Office 365-Endpunkt-Webdienst zu nutzen. Weitere Informationen finden Sie unter [Office 365 – IP-Adress- und URL-Webdienst](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).

Sie umgehen nur die normale Proxy- und Netzwerksicherheitsverarbeitung für Datenverkehr zu Microsoft 365-Endpunkten der Kategorie „Optimieren“ und „Zulassen“. Der andere allgemeine Internetdatenverkehr wird weitergeleitet und unterliegt Ihrer vorhandenen Netzwerksicherheitsverarbeitung.


Als Zwischenprüfung können Sie die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step4) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Optimieren der Leistung des Clients und des Office 365-Diensts](networking-optimize-tcp-performance.md) |



