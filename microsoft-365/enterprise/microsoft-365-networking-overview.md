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
description: Erläutert, warum die Netzwerkoptimierung für SaaS-Dienste wichtig ist, das Ziel Microsoft 365 netzwerk und wie SaaS andere Netzwerke als andere Workloads erfordert.
ms.openlocfilehash: d1a2b79f6e4042b97ec5a31d0ff92175baa1218e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923182"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Microsoft 365 Netzwerkverbindungsübersicht

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft 365 ist eine verteilte Software-as-a-Service (SaaS)-Cloud, die Produktivitäts- und Zusammenarbeitsszenarien über eine Vielzahl von Mikrodiensten und Anwendungen bietet. Clientkomponenten von Microsoft 365 wie Outlook, Word und PowerPoint werden auf Benutzercomputern ausgeführt und stellen eine Verbindung mit anderen Komponenten von Microsoft 365, die in Microsoft-Rechenzentren ausgeführt werden. Der wichtigste Faktor, der die Qualität der Microsoft 365 der Endbenutzer bestimmt, ist die Netzwerkzuverlässigkeit und geringe Latenz zwischen Microsoft 365 Clients und Microsoft 365-Fronttüren.

In diesem Artikel erfahren Sie mehr über die Ziele Microsoft 365 Netzwerk und warum Microsoft 365 Netzwerk einen anderen Optimierungsansatz als generischen Internetdatenverkehr erfordert.

## <a name="microsoft-365-networking-goals"></a>Microsoft 365 Netzwerkziele

Das letztendliche Ziel Microsoft 365 Netzwerk besteht in der Optimierung der Endbenutzererfahrung, indem der geringste restriktivste Zugriff zwischen Clients und den Microsoft 365 ermöglicht wird. Die Qualität der Endbenutzererfahrung steht in direktem Zusammenhang mit der Leistung und Reaktionsfähigkeit der Anwendung, die der Benutzer verwendet. Beispielsweise basiert Microsoft Teams auf einer geringen Latenz, sodass Benutzertelefonanrufe, Konferenzen und Zusammenarbeiten auf gemeinsamem Bildschirm kostenlos sind und Outlook auf hervorragende Netzwerkkonnektivität für Sofortsuchfunktionen angewiesen ist, die serverseitige Indizierungs- und KI-Funktionen nutzen.

Das Hauptziel im Netzwerkentwurf sollte es sein, die Latenz zu minimieren, indem die Roundtripzeit (Roundtrip time, RTT) von Clientcomputern zum Globalen Netzwerk von Microsoft reduziert wird, dem öffentlichen Netzwerk-Backbone von Microsoft, das alle Rechenzentren von Microsoft mit niedriger Latenz verbindet, und Die Einstiegspunkte für Cloudanwendung mit hoher Verfügbarkeit, die auf der ganzen Welt verteilt sind. Erfahren Sie mehr über das globale Microsoft-Netzwerk unter [So erstellt Microsoft sein schnelles und zuverlässiges globales Netzwerk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Das Optimieren Microsoft 365 Netzwerkleistung muss nicht kompliziert sein. Sie können die bestmögliche Leistung erzielen, indem Sie einige wichtige Prinzipien folgen:

- Identifizieren Microsoft 365 Netzwerkdatenverkehrs
- Zulassen, dass lokale Zweigstellen Microsoft 365 Netzwerkdatenverkehr an das Internet von jedem Ort aus, an dem Benutzer eine Verbindung mit Microsoft 365
- Zulassen Microsoft 365 Datenverkehrs zum Umgehen von Proxys und Paketprüfungsgeräten

Weitere Informationen zu Microsoft 365 Netzwerkkonnektivitätsprinzipien finden Sie [unter Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="traditional-network-architectures-and-saas"></a>Herkömmliche Netzwerkarchitekturen und SaaS

Herkömmliche Prinzipien der Netzwerkarchitektur für Client-/Server-Arbeitsauslastungen sind so konzipiert, dass der Datenverkehr zwischen Clients und Endpunkten nicht außerhalb des Unternehmensnetzwerkperimeters liegt. Außerdem durchlaufen in vielen Unternehmensnetzwerken alle ausgehenden Internetverbindungen das Unternehmensnetzwerk und fangen von einem zentralen Standort ab.

In herkömmlichen Netzwerkarchitekturen ist eine höhere Latenz für generischen Internetdatenverkehr ein notwendiger Tradeoff, um die Sicherheit des Netzwerkperimeters zu gewährleisten, und die Leistungsoptimierung für den Internetdatenverkehr umfasst in der Regel ein Upgrade oder skalieren der Geräte an Netzwerkaussprungspunkten. Dieser Ansatz erfüllt jedoch nicht die Anforderungen für eine optimale Netzwerkleistung von SaaS-Diensten wie Microsoft 365.

## <a name="identifying-microsoft-365-network-traffic"></a>Identifizieren Microsoft 365 Netzwerkdatenverkehrs

Wir vereinfachen die Identifizierung Microsoft 365 Netzwerkdatenverkehrs und vereinfachen die Verwaltung der Netzwerkidentifikation.

- Neue Kategorien von Netzwerkendpunkten, um hochgradig kritischen Netzwerkdatenverkehr vom Netzwerkdatenverkehr zu unterscheiden, der nicht von Internetlatenz betroffen ist. Es gibt nur eine Handvoll URLs und unterstützende IP-Adressen in der kritischsten Kategorie "Optimieren".
- Webdienste für die Skriptverwendung oder direkte Gerätekonfiguration und Änderungsverwaltung Microsoft 365 Netzwerkidentifikation. Änderungen sind über den Webdienst oder im RSS-Format oder per E-Mail mithilfe einer Microsoft Flow verfügbar.
- [Office 365 Netzwerkpartnerprogramm](./microsoft-365-networking-partner-program.md) mit Microsoft-Partnern, die Geräte oder Dienste bereitstellen, die Microsoft 365 prinzipien der Netzwerkkonnektivität folgen und über eine einfache Konfiguration verfügen.

## <a name="securing-microsoft-365-connections"></a>Sichern Microsoft 365 Verbindungen

Das Ziel der herkömmlichen Netzwerksicherheit ist die Absicherung des Unternehmensnetzwerkperimeters gegen Eindringversuche und böswillige Angriffe. Die meisten Unternehmensnetzwerke erzwingen die Netzwerksicherheit für den Internetdatenverkehr mithilfe von Technologien wie Proxyservern, Firewalls, SSL-Unterbrechung und -Überprüfung, Tiefenpaketprüfung und Systemen zur Verhinderung von Datenverlust. Diese Technologien mindern die Risiken für allgemeine Internetanforderungen, können aber die Leistung, Skalierbarkeit und die Qualität der Endbenutzererfahrung erheblich verringern, wenn sie auf Microsoft 365-Endpunkte angewendet werden.

Microsoft 365 trägt dazu bei, die Anforderungen Ihrer Organisation an inhaltssicherheit und Datennutzungskonformität mit integrierten Sicherheits- und Governancefeatures zu erfüllen, die speziell für features und workloads Microsoft 365 wurden. Weitere Informationen zu Microsoft 365 und Compliance finden Sie in [der Office 365 Security Roadmap](/office365/securitycompliance/security-roadmap). Weitere Informationen zu Den Empfehlungen und der Supportposition von Microsoft für erweiterte Netzwerklösungen, die eine verarbeitung auf erweiterter Ebene für Microsoft 365-Datenverkehr durchführen, finden Sie unter [Using third-party network devices](https://support.microsoft.com/help/2690045)or solutions on Office 365 traffic .

## <a name="why-is-microsoft-365-networking-different"></a>Warum unterscheiden Microsoft 365 Netzwerk?

Microsoft 365 ist für eine optimale Leistung mithilfe von Endpunktsicherheit und verschlüsselten Netzwerkverbindungen ausgelegt, wodurch die Notwendigkeit einer Durchsetzung der Umkreissicherheit reduziert wird. Microsoft 365 Rechenzentren befinden sich auf der ganzen Welt, und der Dienst ist so konzipiert, dass verschiedene Methoden zum Verbinden von Clients mit den besten verfügbaren Dienstendpunkten verwendet werden. Da Benutzerdaten und -verarbeitung auf viele Microsoft-Rechenzentren verteilt sind, gibt es keinen einzelnen Netzwerkendpunkt, mit dem Clientcomputer eine Verbindung herstellen können. Daten und Dienste in Ihrem mandanten Microsoft 365 werden vom globalen Microsoft Network dynamisch optimiert, um sich an die geografischen Standorte anzupassen, von denen aus endbenutzer auf sie zugreifen.

Bestimmte häufige Leistungsprobleme werden erstellt, Microsoft 365 Datenverkehr einer Paketprüfung und einem zentralisierten Ausgangsverkehr unterliegt:

- Hohe Latenz kann zu einer extrem schlechten Leistung von Video- und Audiodatenströmen und zu einer langsamen Reaktion auf Datenabrufe, Suchen, Zusammenarbeit in Echtzeit, Frei/Gebucht-Kalenderinformationen, Produktinhalten und anderen Diensten führen.
- Durch das Ausziehen von Verbindungen von einem zentralen Standort werden die dynamischen Routingfunktionen des Microsoft 365 globalen Netzwerks nicht mehr unterstützt, und es werden Wartezeit und Roundtripzeit hinzugefügt.
- Das Entschlüsseln von SSL Microsoft 365 netzwerkdatenverkehr und die erneute Verschlüsselung kann Protokollfehler verursachen und ein Sicherheitsrisiko haben

Das Kürzen des Netzwerkpfads auf Microsoft 365 Einstiegspunkte, indem der Clientdatenverkehr so nah wie möglich an den geografischen Standort abfing, kann die Konnektivitätsleistung und die Endbenutzererfahrung in Microsoft 365. Sie kann auch dazu beitragen, die Auswirkungen zukünftiger Änderungen an der Netzwerkarchitektur auf Microsoft 365 und Zuverlässigkeit zu reduzieren. Das optimale Konnektivitätsmodell besteht immer in der Bereitstellung des Netzwerkausflugs am Standort des Benutzers, unabhängig davon, ob es sich um das Unternehmensnetzwerk oder Remotestandorte wie Heim, Hotels, Cafés und Flughäfen handelt. Generischer Internetdatenverkehr und WAN-basierter Unternehmensnetzwerkdatenverkehr würden getrennt geroutet und verwenden nicht das lokale direkte Ausgangsmodell. Dieses Modell mit lokalem direkten Ausgang ist in der nachstehenden Abbildung dargestellt.

![Netzwerkarchitektur mit lokalem Ausgang](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

Die lokale Ausgangsarchitektur bietet die folgenden Vorteile für Microsoft 365 Netzwerkdatenverkehr über das herkömmliche Modell:
  
- Bietet optimale Microsoft 365-Leistung durch optimale Routenlänge. Endbenutzerverbindungen werden dynamisch über die Front-Door-Infrastruktur des verteilten Diensts  des Microsoft Global Network an den nächstgelegenen Microsoft 365-Einstiegspunkt geleitet, und der Datenverkehr wird dann intern über die Hochverfügbarkeits-Hochverfügbarkeits-Fiber von Microsoft an Daten- und Dienstendpunkte geleitet.
- Reduziert die Auslastung der Unternehmensnetzwerkinfrastruktur, indem lokales Ausfahren für Microsoft 365 datenverkehr ermöglicht und Proxys und Datenverkehrsprüfgeräte umgangen werden.
- Sichert Verbindungen an beiden Enden, indem Clientendpunktsicherheits- und Cloudsicherheitsfeatures verwendet werden, um die Anwendung redundanter Netzwerksicherheitstechnologien zu vermeiden.

> [!NOTE]
> Die _Infrastruktur für den verteilten_ Dienst vor der Tür ist der hochgradig verfügbare und skalierbare Netzwerk edge des Microsoft Global Network mit geografisch verteilten Standorten. Es beendet Endbenutzerverbindungen und leitet diese effizient innerhalb des globalen Netzwerks von Microsoft. Erfahren Sie mehr über das globale Microsoft-Netzwerk unter [So erstellt Microsoft sein schnelles und zuverlässiges globales Netzwerk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Weitere Informationen zum Verständnis und zum Anwenden Microsoft 365 Netzwerkkonnektivitätsprinzipien finden Sie [unter Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="conclusion"></a>Zusammenfassung

Die Optimierung Microsoft 365 Netzwerkleistung hat tatsächlich zur Beseitigung unnötiger Hindernisse bei. Indem Sie Microsoft 365 Verbindungen als vertrauenswürdigen Datenverkehr behandeln, können Sie verhindern, dass die Latenz durch Paketprüfung und Konkurrenz um Proxybandbreite eingeführt wird. Durch das Zulassen lokaler Verbindungen zwischen Clientcomputern und Office 365 Endpunkten kann Datenverkehr dynamisch über das globale Microsoft Network geleitet werden.

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