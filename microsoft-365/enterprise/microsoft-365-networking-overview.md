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
- M365initiative-CoreDeploy
f1.keywords:
- NOCSH
description: Erläutert, warum die Netzwerkoptimierung für SaaS-Dienste wichtig ist, das Ziel von Microsoft 365-Netzwerk und wie Saas unterschiedliche Netzwerke aus anderen Arbeitslasten benötigt.
ms.openlocfilehash: acc55868e47ea89cd2357487838a88032dc8538d
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327485"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Microsoft 365-Netzwerkkonnektivität (Übersicht)

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft 365 ist eine verteilte Software-as-a-Service-Cloud (SaaS), die Produktivitäts-und Zusammenarbeitsszenarien mithilfe einer Vielzahl von Mikro Diensten und Anwendungen bereitstellt. Client Komponenten von Microsoft 365 wie Outlook, Word und PowerPoint werden auf Benutzercomputern ausgeführt und stellen eine Verbindung mit anderen Microsoft 365-Komponenten her, die in Microsoft-Rechenzentren ausgeführt werden. Der wichtigste Faktor, der die Qualität der Microsoft 365-Endbenutzererfahrung bestimmt, sind Netzwerkzuverlässigkeit und niedrige Latenz zwischen Microsoft 365-Clients und Microsoft 365-Dienst-Front-Doors.

In diesem Artikel erfahren Sie mehr über die Ziele von Microsoft 365 Networking und warum für Microsoft 365-Netzwerke ein anderer Ansatz zur Optimierung erforderlich ist als allgemeiner Internet Datenverkehr.

## <a name="microsoft-365-networking-goals"></a>Microsoft 365-Netzwerk Ziele

Das ultimative Ziel von Microsoft 365 Networking besteht darin, die Endbenutzerfreundlichkeit zu optimieren, indem Sie den geringsten restriktiven Zugriff zwischen Clients und den nächstgelegenen Microsoft 365-Endpunkten ermöglichen. Die Qualität der Endbenutzererfahrung steht in direktem Zusammenhang mit der Leistung und Reaktionsfähigkeit der Anwendung, die der Benutzer verwendet. Beispielsweise stützt sich Microsoft Teams auf eine geringe Wartezeit, sodass Benutzer Anrufe, Konferenzen und gemeinsame Bildschirm zusammenarbeiten glitch-frei sind, und Outlook basiert auf einer großen Netzwerkkonnektivität für sofort Suchfunktionen, die serverseitige Indizierungs-und AI-Funktionen nutzen.

Das primäre Ziel im Netzwerkentwurf sollte die Minimierung der Wartezeit sein, indem die Roundtripzeit (Round-Trip Time, RTT) von Clientcomputern auf das globale Microsoft-Netzwerk, das Microsoft-Backbone für öffentliche Netzwerke, die alle Microsoft-Rechenzentren mit niedrigen Latenzzeiten und hoch Verfügbarkeits-Cloud-Anwendungseinstiegspunkten in der ganzen Welt vernetzen, reduziert wird. Erfahren Sie mehr über das globale Microsoft-Netzwerk unter [So erstellt Microsoft sein schnelles und zuverlässiges globales Netzwerk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Die Optimierung der Netzwerkleistung von Microsoft 365 muss nicht kompliziert sein. Sie können die bestmögliche Leistung erzielen, indem Sie ein paar wichtige Grundsätze befolgen:

- Identifizieren des Microsoft 365-Netzwerkdatenverkehrs
- Lokalen Zweigstellen Ausstieg aus dem Microsoft 365-Netzwerkdatenverkehr aus jedem Standort, an dem sich Benutzer mit Microsoft 365 verbinden, an das Internet zulassen
- Zulassen von Microsoft 365-Datenverkehr zum Umgehen von Proxys und Paket Prüfgeräten

Weitere Informationen zu den Grundsätzen der Microsoft 365-Netzwerkkonnektivität finden Sie unter [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="traditional-network-architectures-and-saas"></a>Herkömmliche Netzwerkarchitekturen und Saas

Die herkömmlichen Prinzipien der Netzwerkarchitektur für Client/Server-Arbeitsauslastungen sind auf die Annahme hin ausgelegt, dass sich der Datenverkehr zwischen Clients und Endpunkten nicht außerhalb des Umkreis Unternehmensnetzwerks erstreckt. Außerdem durchlaufen alle ausgehenden Internet Verbindungen in vielen Unternehmensnetzwerken das Unternehmensnetzwerk und gehen von einem zentralen Standort aus.

In herkömmlichen Netzwerkarchitekturen ist eine höhere Wartezeit für generischen Internetdatenverkehr ein notwendiger Kompromiss, um die Sicherheit des Netzwerkperimeters aufrechtzuerhalten, und die Leistungsoptimierung für den Internetdatenverkehr umfasst normalerweise ein Upgrade oder eine horizontale Skalierung der Geräte an Netzwerk Ausgangspunkten. Bei dieser Vorgehensweise werden jedoch nicht die Anforderungen für eine optimale Netzwerkleistung von Saas-Diensten wie Microsoft 365 behandelt.

## <a name="identifying-microsoft-365-network-traffic"></a>Identifizieren des Microsoft 365-Netzwerkdatenverkehrs

Wir vereinfachen die Identifizierung des Netzwerkdatenverkehrs von Microsoft 365 und vereinfachen die Verwaltung der Netzwerkidentifikation.

- Neue Kategorien von Netzwerkendpunkten zur Unterscheidung von stark kritischem Netzwerkdatenverkehr vom Netzwerkdatenverkehr, der nicht von Internet Wartezeiten betroffen ist. Es gibt nur eine Handvoll URLs und unterstützende IP-Adressen in der kritischsten Kategorie "optimieren".
- Webdienste für die Skriptverwendung oder direkte Gerätekonfiguration und Änderungsverwaltung der Microsoft 365-Netzwerkidentifikation. Änderungen sind über den Webdienst oder im RSS-Format oder per e-Mail mit einer Microsoft-Fluss Vorlage verfügbar.
- [Office 365 Netzwerkpartnerprogramm](https://aka.ms/Office365NPP) mit Microsoft-Partnern, die Geräte oder Dienste bereitstellen, die den Grundsätzen der Microsoft 365-Netzwerkkonnektivität entsprechen und eine einfache Konfiguration aufweisen.

## <a name="securing-microsoft-365-connections"></a>Sichern von Microsoft 365-Verbindungen

Das Ziel der herkömmlichen Netzwerksicherheit ist die Absicherung des Unternehmensnetzwerkperimeters gegen Eindringversuche und böswillige Angriffe. Die meisten Unternehmensnetzwerke erzwingen die Netzwerksicherheit für den Internet Datenverkehr mithilfe von Technologien wie Proxyservern, Firewalls, SSL-Unterbrechung und-Prüfung, Deep Packet Inspection und Verhinderung von Datenverlust. Diese Technologien mindern die Risiken für allgemeine Internetanforderungen, können aber die Leistung, Skalierbarkeit und die Qualität der Endbenutzererfahrung erheblich verringern, wenn sie auf Microsoft 365-Endpunkte angewendet werden.

Microsoft 365 hilft, die Anforderungen Ihrer Organisation an Inhaltssicherheit und Daten Nutzungs Konformität mit integrierten Sicherheits-und Steuerungsfeatures zu erfüllen, die speziell für Microsoft 365-Features und-Arbeitslasten entwickelt wurden. Weitere Informationen zur Sicherheit und Compliance von Microsoft 365 finden Sie unter [Office 365 Security Roadmap](https://docs.microsoft.com/office365/securitycompliance/security-roadmap). Weitere Informationen zu den Empfehlungen und der Unterstützung von Microsoft für erweiterte Netzwerklösungen, die eine fortgeschrittene Verarbeitung auf dem Microsoft 365-Datenverkehr ausführen, finden Sie unter [Verwenden von Drittanbieter-Netzwerkgeräten oder Lösungen für Office 365 Datenverkehr](https://support.microsoft.com/help/2690045).

## <a name="why-is-microsoft-365-networking-different"></a>Warum ist das Microsoft 365-Netzwerk unterschiedlich?

Microsoft 365 wurde für eine optimale Leistung mithilfe von Endpunktsicherheit und verschlüsselten Netzwerkverbindungen entwickelt, wodurch die Notwendigkeit der Durchsetzung der Umkreis Sicherheit reduziert wird. Microsoft 365-Rechenzentren befinden sich auf der ganzen Welt, und der Dienst ist für die Verwendung verschiedener Methoden zum Verbinden von Clients mit den besten verfügbaren Dienstendpunkten konzipiert. Da Benutzerdaten und-Verarbeitung zwischen vielen Microsoft-Rechenzentren verteilt werden, gibt es keinen einzelnen Netzwerkendpunkt, mit dem Clientcomputer eine Verbindung herstellen können. Tatsächlich werden Daten und Dienste in Ihrem Microsoft 365-Mandanten dynamisch von dem globalen Microsoft-Netzwerk optimiert, sodass Sie sich an die geografischen Standorte anpassen können, von denen Endbenutzer auf Sie zugreifen.

Bestimmte allgemeine Leistungsprobleme werden erstellt, wenn der Datenverkehr von Microsoft 365 der Paketüberprüfung und dem zentralisierten Ausstieg unterliegt:

- Hohe Latenz kann zu extrem schlechter Leistung von Video-und Audiostreams führen und eine langsame Antwort auf den Datenabruf, Suchvorgänge, Echtzeitzusammenarbeit, Kalender Frei/Gebucht-Informationen, produktbezogene Inhalte und andere Dienste verursachen.
- Egressing-Verbindungen von einem zentralen Standort aus besiegen die dynamischen Routingfunktionen des globalen Microsoft 365-Netzwerks, indem Wartezeit und Roundtripzeit hinzugefügt werden.
- Entschlüsseln von SSL-gesichertem Microsoft 365-Netzwerkdatenverkehr und erneuter Verschlüsselung es kann zu Protokollfehlern führen und weist ein Sicherheitsrisiko auf.

Wenn Sie den Netzwerkpfad zu den Einstiegspunkten von Microsoft 365 verkürzen, indem Sie den Client Datenverkehr so nah wie möglich an ihren geografischen Standort abgeben lassen, kann dies die Konnektivitäts-Performance und die Endbenutzererfahrung in Microsoft 365 verbessern. Sie kann auch dazu beitragen, die Auswirkungen künftiger Änderungen an der Netzwerkarchitektur auf die Leistung und Zuverlässigkeit von Microsoft 365 zu verringern. Das optimale Verbindungsmodell besteht darin, den Netzwerk Ausstieg immer am Standort des Benutzers bereitzustellen, unabhängig davon, ob sich dies im Unternehmensnetzwerk oder an Remotestandorten wie Home, Hotels, Cafés und Flughäfen befindet. Allgemeiner Internet Datenverkehr und WAN-basierter Unternehmensnetzwerk Datenverkehr werden separat weitergeleitet und verwenden nicht das lokale Direct-Ausstieg-Modell. Dieses Modell mit lokalem direkten Ausgang ist in der nachstehenden Abbildung dargestellt.

![Netzwerkarchitektur mit lokalem Ausgang](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

Die lokale Ausgangsarchitektur hat folgende Vorteile für den Microsoft 365-Netzwerkdatenverkehr über das herkömmliche Modell:
  
- Bietet optimale Microsoft 365-Leistung durch optimale Routenlänge. Endbenutzer Verbindungen werden dynamisch an den nächstgelegenen Microsoft 365-Einstiegspunkt durch die _verteilte Dienst-Front-Door_ -Infrastruktur des Microsoft Global-Netzwerks weitergeleitet, und der Datenverkehr wird dann intern an Daten-und Dienstendpunkte über die hoch Verfügbarkeits-Fiber von Microsoft mit hoher Verfügbarkeit weitergeleitet.
- Reduziert die Auslastung der Unternehmensnetzwerk Infrastruktur, indem lokale Ausgänge für Microsoft 365-Datenverkehr zugelassen werden und Proxys und Daten Verkehrsüberwachungs Geräte umgangen werden.
- Sichert Verbindungen an beiden Enden, indem Client-Endpunktsicherheit und Cloud-Sicherheitsfunktionen genutzt werden, wodurch die Anwendung redundanter Netzwerksicherheitstechnologien vermieden wird.

> [!NOTE]
> Die _verteilte Dienst-Front-Door_ -Infrastruktur ist die hoch verfügbare und skalierbare Netzwerk Kante des Microsoft Global Netzwerks mit geografisch verteilten Standorten. Sie beendet Endbenutzer Verbindungen und leitet Sie effizient innerhalb des globalen Netzwerks von Microsoft weiter. Erfahren Sie mehr über das globale Microsoft-Netzwerk unter [So erstellt Microsoft sein schnelles und zuverlässiges globales Netzwerk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Weitere Informationen zum Verständnis und zur Anwendung von Microsoft 365-Netzwerk Konnektivitäts Prinzipien finden Sie unter [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="conclusion"></a>Schlussbemerkung

Die Optimierung der Netzwerkleistung von Microsoft 365 ist wirklich auf das Entfernen unnötiger Hindernisse beschränkt. Durch die Behandlung von Microsoft 365-Verbindungen als vertrauenswürdiger Datenverkehr können Sie verhindern, dass die Wartezeit durch die Paketüberprüfung und den Wettbewerb um die Proxy Bandbreite eingeführt wird. Durch das zulassen lokaler Verbindungen zwischen Clientcomputern und Office 365 Endpunkten kann der Datenverkehr dynamisch über das globale Microsoft-Netzwerk weitergeleitet werden.

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
