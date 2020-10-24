---
title: Netzwerkfunktionen für die Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Grundlegendes zur Contoso-Netzwerkinfrastruktur und dazu, wie das Unternehmen seine SD-WAN-Technologie für eine optimale Netzwerkleistung für Microsoft 365 für Enterprise-Cloud-Dienste verwendet.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754014"
---
# <a name="networking-for-the-contoso-corporation"></a>Netzwerkfunktionen für die Contoso Corporation

Um eine Cloud-inclusive-Infrastruktur einzusetzen, hat Contoso eine grundlegende Verschiebung des Netzwerkdatenverkehrs zu Cloud-Diensten entwickelt. Anstelle eines internen Hub-and-Spoke-Modells, das die Netzwerkkonnektivität und den Datenverkehr für die nächste Ebene der Office-Hierarchie konzentriert, haben Sie Benutzer Standorte dem lokalen Internet Ausstieg und lokalen Verbindungen mit dem nächstgelegenen Microsoft 365-Netzwerkspeicherort im Internet zugeordnet.

## <a name="networking-infrastructure"></a>Netzwerkinfrastruktur

Dies sind die Netzwerkelemente, die Contoso-Niederlassungen auf der ganzen Welt verknüpfen:

- MPLS-WAN-Netzwerk (Multiprotocol Label Switching)

  Ein MPLS-WAN-Netzwerk verbindet das Pariser Hauptquartier mit regionalen Niederlassungen und regionalen Niederlassungen mit Satellitenbüros in einer Spoke-and-Hub-Konfiguration. Das Netzwerk ermöglicht Benutzern den Zugriff auf lokale Server, die Branchenanwendungen in der Pariser Hauptniederlassung bilden. Außerdem werden alle generischen Internetdatenverkehr an das Pariser Büro weitergeleitet, wo die Netzwerksicherheitsgeräte die Anforderungen Schrubben. In jedem Büro liefern Router Datenverkehr zu drahtgebundenen Hosts oder drahtlosen Zugriffspunkten in Subnetzen, die den privaten IP-Adressraum verwenden.

- Lokaler direkter Internetzugriff für Microsoft 365-Datenverkehr

  Jedes Büro verfügt über ein softwaredefiniertes WAN (SD-WAN)-Gerät, das über einen oder mehrere lokale Internetdienstanbieter-Netzwerk Schaltkreise mit eigener Internetverbindung über einen Proxy Server verfügt. Dies wird in der Regel als WAN-Link zu einem lokalen ISP implementiert, der auch öffentliche IP-Adressen und einen lokalen DNS-Server bereitstellt.

- Internetauftritt

  Contoso ist Besitzer des \. com-namens der öffentlichen Domäne von contoso. Bei der öffentlichen Contoso-Website für die Bestellung von Produkten handelt es sich um eine Reihe von Servern in einem mit dem Internet verbundenen Rechenzentrum im Pariser Campus. Contoso verwendet einen/24 öffentlichen IP-Adressbereich im Internet.

Abbildung 1 zeigt die Contoso-Netzwerkinfrastruktur und ihre Verbindungen mit dem Internet.

![Das Contoso-Netzwerk](../media/contoso-networking/contoso-networking-fig1.png)
 
**Abbildung 1: das Contoso-Netzwerk**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Verwenden des SD-WAN für eine optimale Netzwerkkonnektivität mit Microsoft

Contoso folgte den folgenden [Prinzipien von Microsoft 365-Netzwerkverbindungen](microsoft-365-network-connectivity-principles.md) bei folgende Aufgaben:

- Identifizieren und Unterscheiden von Microsoft 365-Netzwerkdatenverkehr
- Lokaler Ausgang von Netzwerkverbindungen
- Vermeiden von Spitzkehren für Netzwerke
- Umgehen von doppelten Netzwerksicherheitsgeräten

Für Microsoft 365 gibt es drei Kategorien von Netzwerkdatenverkehr: *optimieren*, *zulassen*und *Standard*. Optimieren und zulassen der Datenverkehr ist vertrauenswürdiger Netzwerkdatenverkehr, der an den Endpunkten verschlüsselt und gesichert ist und für das Microsoft 365-Netzwerk bestimmt ist.

Contoso hat Folgendes beschlossen:

- Verwenden Sie Direct Internet Ausstieg zum Optimieren und zulassen des Kategorie-Datenverkehrs sowie zum Weiterleiten aller standardmäßigen Kategorie-Datenverkehr an die in Paris ansässige zentrale Internetverbindung.

- Stellen Sie SD-WAN-Geräte in jedem Büro als einfache Möglichkeit zur Verfügung, um diese Prinzipien zu befolgen und eine optimale Netzwerkleistung für Microsoft 365 Cloud-basierte Dienste zu erzielen.

  Die SD-WAN-Geräte weisen einen LAN-Port für das lokale Netzwerk und mehrere WAN-Ports auf. Ein WAN-Port stellt eine Verbindung mit dem MPLS-Netzwerk her. Eine andere stellt eine Verbindung zu einer lokalen ISP-Schaltung her. Die SD-WAN-Geräte leiten Netzwerkdatenverkehr der Kategorie "Optimize" und "Allow" über die ISP-Verbindung.

## <a name="the-contoso-line-of-business-app-infrastructure"></a>Die Contoso-Branchen-App-Infrastruktur

Contoso hat die Infrastruktur für Branchenanwendungen und Server Netzwerke für Folgendes entworfen:

- Zweigstellen verwenden lokale Cacheserver, um Dokumente und interne Websites zu speichern, auf die häufig zugegriffen wird.
- Regionalstellen verwenden regionale Anwendungsserver für die Regional- und Zweigstellenbüros. Diese Server werden mit den Servern in der Pariser Zentrale synchronisiert.
- Die Pariser Campus-Rechenzentren enthalten zentralisierte Anwendungsserver, die der gesamten Organisation dienen.

Abbildung 2 zeigt den Prozentsatz der Netzwerkdatenverkehr-Kapazität, die beim Zugriff auf Server im Intranet von Contoso verwendet wird.

![Die Contoso-Infrastruktur für interne Anwendungen](../media/contoso-networking/contoso-networking-fig2.png)
 
**Abbildung 2: die Contoso-Infrastruktur für interne Anwendungen**

Für die Satelliten-oder regionalen Hub-Büros können 60 Prozent der von Mitarbeitern benötigten Ressourcen über Satelliten-und regionale Hub-Office-Server bedient werden. Die zusätzlichen 40 Prozent der Ressourcenanforderungen müssen über die WAN-Verbindung mit dem Pariser Campus gehen.

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Netzwerkanalyse und Vorbereitung für Microsoft 365 für Unternehmen

Die erfolgreiche Einführung von Microsoft 365 für Enterprise-Dienste durch Contoso-Benutzer hängt von der hochgradig verfügbaren und leistungsfähigen Konnektivität mit dem Internet oder direkt mit Microsoft Cloud Services ab. Contoso hat diese Schritte zur Planung und Implementierung einer optimierten Konnektivität mit Microsoft 365 für Enterprise-Cloud-Dienste ausgeführt:

1. Erstellen eines WAN-Netzplandiagramms für Unternehmen zur Unterstützung bei der Planung

   Um Ihre Netzwerkplanung zu starten, hat Contoso ein Diagramm mit seinen Bürostandorten, vorhandenen Netzwerkverbindungen, vorhandenen Netzwerkperimeter-Geräten und Dienstklassen erstellt, die im Netzwerk verwaltet werden. Dieses Diagramm wurde für jeden nachfolgenden Schritt bei der Planung und Implementierung von Netzwerkkonnektivität verwendet.

2. Erstellen eines Plans für Microsoft 365 für die unternehmensweite Netzwerkkonnektivität

   Contoso hat die [Microsoft 365-Netzwerk Verbindungs Prinzipien](microsoft-365-network-connectivity-principles.md) und Beispielreferenz-Netzwerkarchitekturen verwendet, um SD-WAN als bevorzugte Topologie für die Microsoft 365-Konnektivität zu identifizieren.

3. Analysieren der Auslastung der Internetverbindung und der MPLS-WAN-Bandbreite in jedem Büro und erhöhte Bandbreite bei Bedarf

   Die aktuelle Auslastung jedes Büros wurde analysiert, und die Schaltkreise wurden erhöht, sodass der vorhergesagte Microsoft 365 Cloud-basierter Datenverkehr mit durchschnittlich 20 Prozent nicht genutzter Kapazität betrieben würde.

4. Optimieren der Leistung für Microsoft-Netzwerkdienste

   Contoso hat die Gruppe der Office 365-, InTune-und Azure-Endpunkte und konfigurierter Firewalls, Sicherheitsgeräte und anderer Systeme im Internetpfad für eine optimale Leistung bestimmt. Endpunkte für Office 365 optimieren und zulassen des Kategorie-Datenverkehrs wurden in die SD-WAN-Geräte für das Routing über die ISP-Schaltung konfiguriert.

5. Konfigurieren von internem DNS

   Das DNS muss betriebsbereit sein und für Microsoft 365-Datenverkehr lokal nachgeschlagen werden.

6. Überprüfen der Netzwerkendpunkt-und Port Konnektivität

   Contoso hat Microsoft Network Connectivity Test Tools zum Überprüfen der Konnektivität für Microsoft 365 für Enterprise-Cloud-Dienste ausgeführt.

7. Optimieren der Mitarbeiter Computer für die Netzwerkkonnektivität

   Einzelne Computer wurden überprüft, um sicherzustellen, dass die neuesten Betriebssystemupdates installiert wurden und dass die Endpunkt Sicherheitsüberwachung auf allen Clients aktiv war.

## <a name="next-step"></a>Nächster Schritt

Erfahren Sie, wie Contoso [seine lokalen Active Directory-Domänendienste in der Cloud](contoso-identity.md) für Mitarbeiter und Verbundauthentifizierung für Kunden und Geschäftspartner nutzt.

## <a name="see-also"></a>Siehe auch

[Roadmap für Netzwerke für Microsoft 365](networking-roadmap-microsoft-365.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)
