---
title: Microsoft 365 – Überblick über die Netzwerkkonnektivität
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Erläutert, warum die Netzwerkoptimierung für SaaS-Dienste wichtig ist, das Ziel von Microsoft 365-Netzwerken und wie SaaS andere Netzwerke als andere Workloads erfordert.
ms.openlocfilehash: d1a2b79f6e4042b97ec5a31d0ff92175baa1218e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923182"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Übersicht über die Microsoft 365-Netzwerkkonnektivität

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft 365 ist eine verteilte Software-as-a-Service (SaaS)-Cloud, die Produktivitäts- und Zusammenarbeitsszenarien über eine Vielzahl von Mikrodiensten und Anwendungen bietet. Clientkomponenten von Microsoft 365 wie Outlook, Word und PowerPoint werden auf Benutzercomputern ausgeführt und stellen eine Verbindung mit anderen Komponenten von Microsoft 365 sicher, die in Microsoft-Rechenzentren ausgeführt werden. Der wichtigste Faktor, der die Qualität der Microsoft 365-Endbenutzererfahrung bestimmt, ist die Netzwerkzuverlässigkeit und geringe Latenz zwischen Microsoft 365-Clients und Microsoft 365-Dienst-Fronttüren.

In diesem Artikel erfahren Sie mehr über die Ziele von Microsoft 365-Netzwerken und warum microsoft 365-Netzwerke einen anderen Optimierungsansatz als generischen Internetdatenverkehr erfordern.

## <a name="microsoft-365-networking-goals"></a>Microsoft 365-Netzwerkziele

Das letztendliche Ziel des Microsoft 365-Netzwerks besteht in der Optimierung der Endbenutzererfahrung, indem der am wenigsten restriktive Zugriff zwischen Clients und den nächstgelegenen Microsoft 365-Endpunkten ermöglicht wird. Die Qualität der Endbenutzererfahrung steht in direktem Zusammenhang mit der Leistung und Reaktionsfähigkeit der Anwendung, die der Benutzer verwendet. Microsoft Teams basiert z. B. auf einer geringen Latenz, sodass Benutzertelefonanrufe, Konferenzen und Zusammenarbeiten auf gemeinsamem Bildschirm kostenlos sind und Outlook auf hervorragende Netzwerkkonnektivität für Sofortsuchfeatures angewiesen ist, die serverseitige Indizierung und KI-Funktionen nutzen.

Das Hauptziel im Netzwerkentwurf sollte es sein, die Latenz zu minimieren, indem die Roundtripzeit (Roundtrip time, RTT) von Clientcomputern zum Globalen Netzwerk von Microsoft reduziert wird, dem öffentlichen Netzwerk-Backbone von Microsoft, das alle Rechenzentren von Microsoft mit niedriger Latenz verbindet, und Die Einstiegspunkte für Cloudanwendung mit hoher Verfügbarkeit, die auf der ganzen Welt verteilt sind. Erfahren Sie mehr über das globale Microsoft-Netzwerk unter [So erstellt Microsoft sein schnelles und zuverlässiges globales Netzwerk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Die Optimierung der Microsoft 365-Netzwerkleistung muss nicht kompliziert sein. Sie können die bestmögliche Leistung erzielen, indem Sie einige wichtige Prinzipien folgen:

- Identifizieren des Microsoft 365-Netzwerkdatenverkehrs
- Zulassen, dass lokale Zweigstellen den Microsoft 365-Netzwerkdatenverkehr von jedem Standort aus in das Internet übertragen, an dem Benutzer eine Verbindung mit Microsoft 365 herstellen
- Zulassen des Microsoft 365-Datenverkehrs zum Umgehen von Proxys und Paketprüfungsgeräten

Weitere Informationen zu Microsoft 365-Netzwerkkonnektivitätsprinzipien finden Sie unter [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="traditional-network-architectures-and-saas"></a>Herkömmliche Netzwerkarchitekturen und SaaS

Herkömmliche Prinzipien der Netzwerkarchitektur für Client-/Server-Arbeitsauslastungen sind so konzipiert, dass der Datenverkehr zwischen Clients und Endpunkten nicht außerhalb des Unternehmensnetzwerkperimeters liegt. Außerdem durchlaufen in vielen Unternehmensnetzwerken alle ausgehenden Internetverbindungen das Unternehmensnetzwerk und fangen von einem zentralen Standort ab.

In herkömmlichen Netzwerkarchitekturen ist eine höhere Latenz für generischen Internetdatenverkehr ein notwendiger Tradeoff, um die Sicherheit des Netzwerkperimeters zu gewährleisten, und die Leistungsoptimierung für den Internetdatenverkehr umfasst in der Regel ein Upgrade oder skalieren der Geräte an Netzwerkaussprungspunkten. Dieser Ansatz erfüllt jedoch nicht die Anforderungen für eine optimale Netzwerkleistung von SaaS-Diensten wie Microsoft 365.

## <a name="identifying-microsoft-365-network-traffic"></a>Identifizieren des Microsoft 365-Netzwerkdatenverkehrs

Wir vereinfachen die Identifizierung des Microsoft 365-Netzwerkdatenverkehrs und die Verwaltung der Netzwerkidentifikation.

- Neue Kategorien von Netzwerkendpunkten, um hochgradig kritischen Netzwerkdatenverkehr vom Netzwerkdatenverkehr zu unterscheiden, der nicht von Internetlatenz betroffen ist. Es gibt nur eine Handvoll URLs und unterstützende IP-Adressen in der kritischsten Kategorie "Optimieren".
- Webdienste für die Skriptverwendung oder direkte Gerätekonfiguration und Änderungsverwaltung der Microsoft 365-Netzwerkidentifikation. Änderungen sind im Webdienst, im RSS-Format oder in E-Mails mit einer Microsoft Flow-Vorlage verfügbar.
- [Office 365-Netzwerkpartnerprogramm](./microsoft-365-networking-partner-program.md) mit Microsoft-Partnern, die Geräte oder Dienste bereitstellen, die den Prinzipien von Microsoft 365-Netzwerkkonnektivität entsprechen und über eine einfache Konfiguration verfügen.

## <a name="securing-microsoft-365-connections"></a>Sichern von Microsoft 365-Verbindungen

Das Ziel der herkömmlichen Netzwerksicherheit ist die Absicherung des Unternehmensnetzwerkperimeters gegen Eindringversuche und böswillige Angriffe. Die meisten Unternehmensnetzwerke erzwingen die Netzwerksicherheit für den Internetdatenverkehr mithilfe von Technologien wie Proxyservern, Firewalls, SSL-Unterbrechung und -Überprüfung, Tiefenpaketprüfung und Systemen zur Verhinderung von Datenverlust. Diese Technologien mindern die Risiken für allgemeine Internetanforderungen, können aber die Leistung, Skalierbarkeit und die Qualität der Endbenutzererfahrung erheblich verringern, wenn sie auf Microsoft 365-Endpunkte angewendet werden.

Microsoft 365 trägt dazu bei, die Anforderungen Ihrer Organisation an die Inhaltssicherheit und datennutzungskonformität mit integrierten Sicherheits- und Steuerungsfeatures zu erfüllen, die speziell für Microsoft 365-Features und -Workloads entwickelt wurden. Weitere Informationen zur Sicherheit und Compliance von Microsoft 365 finden Sie unter [Office 365 Security Roadmap](/office365/securitycompliance/security-roadmap). Weitere Informationen zu Den Empfehlungen und der Supportposition von Microsoft zu erweiterten Netzwerklösungen, die eine verarbeitung auf erweiterter Ebene für Microsoft 365-Datenverkehr durchführen, finden Sie unter Verwenden von Netzwerkgeräten oder Lösungen von Drittanbietern für [Office 365-Datenverkehr.](https://support.microsoft.com/help/2690045)

## <a name="why-is-microsoft-365-networking-different"></a>Warum unterscheiden sich Microsoft 365-Netzwerke?

Microsoft 365 ist für eine optimale Leistung mit Endpunktsicherheit und verschlüsselten Netzwerkverbindungen konzipiert, wodurch die Notwendigkeit der Durchsetzung der Umkreissicherheit reduziert wird. Microsoft 365-Rechenzentren befinden sich auf der ganzen Welt, und der Dienst ist so konzipiert, dass verschiedene Methoden zum Verbinden von Clients mit den besten verfügbaren Dienstendpunkten verwendet werden. Da Benutzerdaten und -verarbeitung auf viele Microsoft-Rechenzentren verteilt sind, gibt es keinen einzelnen Netzwerkendpunkt, mit dem Clientcomputer eine Verbindung herstellen können. Tatsächlich werden Daten und Dienste in Ihrem Microsoft 365-Mandanten vom globalen Microsoft Network dynamisch optimiert, um sich an die geografischen Standorte anzupassen, von denen aus endbenutzer auf sie zugreifen.

Bestimmte häufige Leistungsprobleme werden erstellt, wenn Microsoft 365-Datenverkehr einer Paketprüfung und einem zentralisierten Ausgangs unterliegt:

- Hohe Latenz kann zu einer extrem schlechten Leistung von Video- und Audiodatenströmen und zu einer langsamen Reaktion auf Datenabrufe, Suchen, Zusammenarbeit in Echtzeit, Frei/Gebucht-Kalenderinformationen, Produktinhalten und anderen Diensten führen.
- Das Ausziehen von Verbindungen von einem zentralen Standort zwingt die dynamischen Routingfunktionen des globalen Microsoft 365-Netzwerks und fügt Wartezeit und Roundtripzeit hinzu.
- Entschlüsselung von SSL gesicherten Microsoft 365-Netzwerkdatenverkehr und erneute Verschlüsselung kann Protokollfehler verursachen und sicherheitsrisikot

Das Kürzen des Netzwerkpfads zu Microsoft 365-Einstiegspunkten, indem Clientdatenverkehr so nah wie möglich an den geografischen Standort abfing, kann die Konnektivitätsleistung und die Endbenutzererfahrung in Microsoft 365 verbessern. Es kann auch dazu beitragen, die Auswirkungen zukünftiger Änderungen an der Netzwerkarchitektur auf die Leistung und Zuverlässigkeit von Microsoft 365 zu reduzieren. Das optimale Konnektivitätsmodell besteht immer in der Bereitstellung des Netzwerkausflugs am Standort des Benutzers, unabhängig davon, ob es sich um das Unternehmensnetzwerk oder Remotestandorte wie Heim, Hotels, Cafés und Flughäfen handelt. Generischer Internetdatenverkehr und WAN-basierter Unternehmensnetzwerkdatenverkehr würden getrennt geroutet und verwenden nicht das lokale direkte Ausgangsmodell. Dieses Modell mit lokalem direkten Ausgang ist in der nachstehenden Abbildung dargestellt.

![Netzwerkarchitektur mit lokalem Ausgang](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

Die lokale Ausgangsarchitektur hat die folgenden Vorteile für den Microsoft 365-Netzwerkdatenverkehr gegenüber dem herkömmlichen Modell:
  
- Bietet optimale Microsoft 365-Leistung durch optimale Routenlänge. Endbenutzerverbindungen werden von der Verteilten Front-Door-Infrastruktur für den verteilten Dienst  des globalen Netzwerks dynamisch an den nächstgelegenen Microsoft 365-Einstiegspunkt geleitet, und der Datenverkehr wird dann intern an Daten- und Dienstendpunkte über die Hochverfügbarkeits-Fiber mit extrem niedriger Latenz von Microsoft geleitet.
- Reduziert die Auslastung der Unternehmensnetzwerkinfrastruktur, indem der lokale Ausfahrverkehr für Microsoft 365-Datenverkehr ermöglicht wird und Proxys und Datenverkehrsprüfgeräte umgangen werden.
- Sichert Verbindungen an beiden Enden, indem Clientendpunktsicherheits- und Cloudsicherheitsfeatures verwendet werden, um die Anwendung redundanter Netzwerksicherheitstechnologien zu vermeiden.

> [!NOTE]
> Die _Infrastruktur für den verteilten_ Dienst vor der Tür ist der hochgradig verfügbare und skalierbare Netzwerk edge des Microsoft Global Network mit geografisch verteilten Standorten. Es beendet Endbenutzerverbindungen und leitet diese effizient innerhalb des globalen Netzwerks von Microsoft. Erfahren Sie mehr über das globale Microsoft-Netzwerk unter [So erstellt Microsoft sein schnelles und zuverlässiges globales Netzwerk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Weitere Informationen zum Verstehen und Anwenden von Microsoft 365-Prinzipien für Netzwerkkonnektivität finden Sie unter [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="conclusion"></a>Schlussbemerkung

Die Optimierung der Microsoft 365-Netzwerkleistung hat tatsächlich zur Beseitigung unnötiger Hindernisse bei. Durch die Behandlung von Microsoft 365-Verbindungen als vertrauenswürdiger Datenverkehr können Sie verhindern, dass die Latenz durch Paketprüfung und Konkurrenz um Proxybandbreite eingeführt wird. Durch das Zulassen lokaler Verbindungen zwischen Clientcomputern und Office 365-Endpunkten kann Datenverkehr dynamisch über das globale Microsoft Network geleitet werden.

## <a name="related-topics"></a>Verwandte Themen

[Prinzipien von Microsoft 365-Netzwerkverbindungen](microsoft-365-network-connectivity-principles.md)

[Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md)

[URLs und IP-Adressbereiche für Office 365](urls-and-ip-address-ranges.md)

[Office 365 – IP-Adress- und URL-Webdienst](microsoft-365-ip-web-service.md)

[Bewerten der Microsoft 365-Netzwerkkonnektivität](assessing-network-connectivity.md)

[Netzwerkplanung und Leistungsoptimierung für Microsoft 365](network-planning-and-performance.md)

[Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf](performance-tuning-using-baselines-and-history.md)

[Plan zur Problembehandlung für Office 365](performance-troubleshooting-plan.md)

[Netzwerke für die Inhaltsübermittlung](content-delivery-networks.md)

[Microsoft 365-Konnektivitätstest](https://aka.ms/netonboard)

[So erstellt Microsoft sein schnelles und zuverlässiges globales Netzwerk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365-Networking-Blog](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)