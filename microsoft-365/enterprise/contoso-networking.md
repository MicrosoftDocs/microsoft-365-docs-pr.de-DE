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
description: Erfahren Sie mehr über die Contoso-Netzwerkinfrastruktur und darüber, wie das Unternehmen seine SD-WAN-Technologie für eine optimale Netzwerkleistung verwendet, um Microsoft 365 Enterprise Cloud Services zu verbessern.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754014"
---
# <a name="networking-for-the-contoso-corporation"></a>Netzwerkfunktionen für die Contoso Corporation

Um eine cloud-inklusive Infrastruktur zu übernehmen, hat Contoso eine grundlegende Verschiebung in der Art und Weise des Datenverkehrs von Netzwerkdatenverkehr zu Clouddiensten entwickelt. Anstelle eines internen Hub- und Sprachmodells, das die Netzwerkkonnektivität und den Datenverkehr für die nächste Ebene der Bürohierarchie konzentriert, wurden Benutzerstandorte lokalen Internetanschlüssen und lokalen Verbindungen zum nächstgelegenen Microsoft 365-Netzwerkspeicherort im Internet zugeordnet.

## <a name="networking-infrastructure"></a>Netzwerkinfrastruktur

Dies sind die Netzwerkelemente, die Contoso-Niederlassungen auf der ganzen Welt verbinden:

- MPLS-WAN-Netzwerk (Multiprotocol Label Switching)

  Ein MPLS-WAN-Netzwerk verbindet die Pariser Zentrale mit Regionalbüros und Regionalbüros mit Satellitenbüros in einer Spoke-and-Hub-Konfiguration. Das Netzwerk ermöglicht Benutzern den Zugriff auf lokale Server, die In-Business-Anwendungen in der Pariser Zentrale sind. Außerdem werden alle generischen Internetdatenverkehre an das Pariser Büro weiter geroutet, in dem Netzwerksicherheitsgeräte die Anforderungen bereinigungen. In jedem Büro liefern Router Datenverkehr an verkabelte Hosts oder Funkzugriffspunkte in Subnetzen, die den privaten IP-Adressraum verwenden.

- Lokaler direkter Internetzugriff für Microsoft 365 Datenverkehr

  Jedes Büro verfügt über ein softwaredefiniertes WAN (SD-WAN)-Gerät, das über mindestens einen lokalen Internet-ISP-Netzwerkkreis mit eigener Internetverbindung über einen Proxyserver verfügt. Dies wird in der Regel als WAN-Verbindung zu einem lokalen ISP implementiert, der auch öffentliche IP-Adressen und einen lokalen DNS-Server bietet.

- Internetauftritt

  Contoso besitzt den öffentlichen Domänennamen contoso \. com. Die öffentliche Contoso-Website zum Bestellen von Produkten ist eine Reihe von Servern in einem mit dem Internet verbundenen Rechenzentrum auf dem Pariser Campus. Contoso verwendet einen öffentlichen /24-IP-Adressbereich im Internet.

Abbildung 1 zeigt die Contoso-Netzwerkinfrastruktur und ihre Verbindungen mit dem Internet.

![Das Contoso-Netzwerk](../media/contoso-networking/contoso-networking-fig1.png)
 
**Abbildung 1: Das Contoso-Netzwerk**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Verwenden des SD-WAN für eine optimale Netzwerkkonnektivität mit Microsoft

Contoso folgte den folgenden [Prinzipien von Microsoft 365-Netzwerkverbindungen](microsoft-365-network-connectivity-principles.md) bei folgende Aufgaben:

- Identifizieren und Unterscheiden von Microsoft 365-Netzwerkdatenverkehr
- Lokaler Ausgang von Netzwerkverbindungen
- Vermeiden von Spitzkehren für Netzwerke
- Umgehen von doppelten Netzwerksicherheitsgeräten

Es gibt drei Kategorien von Netzwerkdatenverkehr für Microsoft 365: *Optimize*, *Allow* und *Default*. Optimieren und Zulassen von Datenverkehr ist vertrauenswürdiger Netzwerkdatenverkehr, der an den Endpunkten verschlüsselt und gesichert ist und für das Netzwerk Microsoft 365 ist.

Contoso hat Folgendes beschlossen:

- Verwenden Sie den direkten Interneteinzug zum Optimieren und Zulassen von Kategoriedatenverkehr und zum Weiterleiten des Datenverkehrs der Standardkategorie an die zentrale Internetverbindung in Paris.

- Stellen Sie SD-WAN-Geräte in jedem Büro auf einfache Weise zur Verfügung, um diese Prinzipien zu befolgen und eine optimale Netzwerkleistung für Microsoft 365 cloudbasierte Dienste zu erzielen.

  Die SD-WAN-Geräte weisen einen LAN-Port für das lokale Netzwerk und mehrere WAN-Ports auf. Ein WAN-Port verbindet sich mit dem MPLS-Netzwerk. Ein anderer stellt eine Verbindung mit einer lokalen ISP-Schaltung ein. Die SD-WAN-Geräte leiten Netzwerkdatenverkehr der Kategorie "Optimize" und "Allow" über die ISP-Verbindung.

## <a name="the-contoso-line-of-business-app-infrastructure"></a>Die Contoso Line-of-Business-App-Infrastruktur

Contoso hat seine Anwendungs- und Serverintranetinfrastruktur für Folgendes entworfen:

- Zweigstellen verwenden lokale Cacheserver, um Dokumente und interne Websites zu speichern, auf die häufig zugegriffen wird.
- Regionalstellen verwenden regionale Anwendungsserver für die Regional- und Zweigstellenbüros. Diese Server werden mit den Servern in der Pariser Zentrale synchronisiert.
- Die Pariser Campus-Rechenzentren enthalten zentrale Anwendungsserver, die der gesamten Organisation dienen.

Abbildung 2 zeigt den Prozentsatz der Netzwerkdatenverkehrkapazität, die beim Zugriff auf Server über das Contoso-Intranet verwendet wird.

![Die Contoso-Infrastruktur für interne Anwendungen](../media/contoso-networking/contoso-networking-fig2.png)
 
**Abbildung 2: Die Contoso-Infrastruktur für interne Anwendungen**

Für die Büros für Satelliten- oder Regionale Hubs können 60 Prozent der von Mitarbeitern benötigten Ressourcen von Satelliten- und Regionalhubbüros bedient werden. Die zusätzlichen 40 Prozent der Ressourcenanforderungen müssen über die WAN-Verbindung zum Pariser Campus gehen.

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Netzwerkanalyse und Vorbereitung Microsoft 365 Unternehmens

Die erfolgreiche Einführung von Microsoft 365 für Unternehmensdienste durch Contoso-Benutzer hängt von einer hochverf nen verfügbaren und performanten Konnektivität mit dem Internet oder direkt mit Microsoft Cloud Services ab. Contoso hat die folgenden Schritte zum Planen und Implementieren einer optimierten Konnektivität Microsoft 365 Enterprise Cloud Services unternommen:

1. Erstellen eines Unternehmens-WAN-Netzwerkdiagramms zur Unterstützung der Planung

   Zum Starten der Netzwerkplanung hat Contoso ein Diagramm erstellt, in dem die Bürostandorte, die vorhandene Netzwerkkonnektivität, vorhandene Netzwerkperimetergeräte und Dienstklassen angezeigt werden, die im Netzwerk verwaltet werden. Dieses Diagramm wurde für jeden nachfolgenden Schritt bei der Planung und Implementierung der Netzwerkkonnektivität verwendet.

2. Erstellen eines Plans für Microsoft 365 unternehmensweite Netzwerkkonnektivität

   Contoso verwendete die [Microsoft 365 netzwerkkonnektivitätsprinzipien](microsoft-365-network-connectivity-principles.md) und Beispielreferenznetzwerkarchitekturen, um SD-WAN als bevorzugte Topologie für Microsoft 365 identifizieren.

3. Analysieren der Internetverbindungsauslastung und der MPLS-WAN-Bandbreite in jedem Büro und Erhöhen der Bandbreite nach Bedarf

   Die aktuelle Nutzung jedes Büros wurde analysiert, und die Schaltungen wurden erhöht, sodass der vorhergesagte Microsoft 365 cloudbasierten Datenverkehr mit einer durchschnittlichen nicht genutzten Kapazität von 20 Prozent funktionieren würde.

4. Optimieren der Leistung für Microsoft-Netzwerkdienste

   Contoso hat die Gruppe der Office 365, Intune und Azure-Endpunkte sowie konfigurierte Firewalls, Sicherheitsgeräte und andere Systeme im Internetpfad für eine optimale Leistung bestimmt. Endpunkte für Office 365 Optimize- und Allow-Kategoriedatenverkehr wurden für das Routing über die ISP-Schaltung in die SD-WAN-Geräte konfiguriert.

5. Konfigurieren von internem DNS

   Das DNS muss betriebsbereit sein und für Microsoft 365-Datenverkehr lokal nachgeschlagen werden.

6. Überprüfen der Netzwerkendpunkt- und Portkonnektivität

   Contoso hat Microsoft-Netzwerkverbindungstesttools zur Überprüfung der Konnektivität für Microsoft 365 Enterprise-Clouddienste verwendet.

7. Optimieren der Mitarbeitercomputer für die Netzwerkkonnektivität

   Einzelne Computer wurden überprüft, um sicherzustellen, dass die neuesten Betriebssystemupdates installiert wurden und dass die Überwachung der Endpunktsicherheit auf allen Clients aktiv war.

## <a name="next-step"></a>Nächster Schritt

Erfahren Sie, wie Contoso seine lokalen [Active Directory-Domänendienste in](contoso-identity.md) der Cloud für Mitarbeiter und die Verbundauthentifizierung für Kunden und Geschäftspartner nutzt.

## <a name="see-also"></a>Siehe auch

[Netzwerk-Roadmap für Microsoft 365](networking-roadmap-microsoft-365.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)
