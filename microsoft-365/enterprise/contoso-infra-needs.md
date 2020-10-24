---
title: Contoso-IT-Infrastruktur und geschäftliche Anforderungen
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
description: Hier finden Sie Informationen zur grundlegenden Struktur der lokalen Contoso-IT-Infrastruktur und dazu, wie die geschäftlichen Anforderungen von Microsoft 365 für Unternehmen erfüllt werden.
ms.openlocfilehash: 767374097efa116f116cff6f6ddf96d075eb71ed
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754586"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>Contoso-IT-Infrastruktur und geschäftliche Anforderungen

Contoso wechselt von einer lokalen, zentralisierten IT-Infrastruktur zu einem Cloud-inclusive-Setup, das Cloud-basierte persönliche Produktivitäts Arbeitslasten und-Anwendungen enthält.

## <a name="existing-contoso-it-infrastructure"></a>Vorhandene Contoso-IT-Infrastruktur

Contoso nutzt eine weitestgehend zentrale lokale IT-Infrastruktur mit Anwendungsrechenzentren in der Pariser Zentrale.

Hier finden Sie die Hauptniederlassung mit Anwendungsdaten Centern, eine DMZ und das Internet.

![Vorhandene Contoso-IT-Infrastruktur](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

In den lokalen Anwendungsrechenzentren wird Folgendes gehostet: 

- Benutzerdefinierte Branchenanwendungen, die SQL Server und andere Linux-Datenbanken verwenden.
- Eine Reihe von älteren SharePoint-Servern.
- Server auf Organisations- und Teamebene für das Speichern von Dateien.

Darüber hinaus unterstützt jedes regionales Hub-Büro eine Reihe von Servern mit einer ähnlichen Gruppe von Anwendungen. Diese Server werden von regionalen IT-Abteilungen gesteuert.

Die Durchsuchbarkeit über die Anwendungen und Daten dieser separaten Rechenzentren an mehreren geografischen Standorten hinweg bleibt eine Herausforderung.

In der DMZ "Contoso Headquarters" bieten verschiedene Servergruppen Folgendes:

- Hosten für die öffentliche Contoso-Website, von der Kunden Produkte, Teile, Lieferungen und Dienste bestellen können.
- Hosting für das Contoso-Partnerextranet für die Kommunikation und Zusammenarbeit mit Partnern.
- VPN-basierter Remotezugriff (virtuelles privates Netzwerk) auf das Contoso-Intranet und Webproxyfunktion für Mitarbeiter in der Pariser Zentrale.

## <a name="contoso-business-needs"></a>Contoso-Geschäftsanforderungen

Die geschäftlichen Anforderungen von Contoso unterliegen fünf Hauptkategorien:

**Produktivität**

- Vereinfachen der Zusammenarbeit

  Ersetzen Sie die e-Mail-und Dateifreigabe basierte Zusammenarbeit durch ein Online Modell, das Echtzeitänderungen an Dokumenten, einfachere Onlinebesprechungen und aufgezeichnete Unterhaltungsthemen ermöglicht.
- Mehr Produktivität für Telearbeiter und Mobilmitarbeiter

  Wenn viele Mitarbeiter von zu Hause oder im Feld arbeiten, ersetzen Sie die Engpass-VPN-Lösung durch den leistungsfähigen Zugriff auf contoso-Daten und-Ressourcen in der Cloud.
- Mehr Kreativität und Innovation

  Nutzen Sie die Vorteile der neuesten visuellen Lern- und Ideenfindungsmethoden, einschließlich Freihand und 3D-Visualisierung.

**Sicherheit**

- Identitäts- und Zugriffsverwaltung

  Erzwingen Sie mehrstufige und andere Formen der Authentifizierung, und schützen Sie die Anmeldeinformationen von Benutzer-und Administratorkonten.

- Bedrohungsschutz

  Schutz vor externen Sicherheitsrisiken, einschließlich Schadsoftware, die auf E-Mails oder dem Betriebssystem basiert.

- Schutz von Daten

  Sperren Sie den Zugriff auf wichtige digitale Ressourcen, und verschlüsseln Sie diese (z. B. Kundendaten, Entwurfs- und Fertigungsspezifikationen und Mitarbeiterinformationen).

- Sicherheitsverwaltung

  Überwachen der Sicherheitsposition und erkennen und reagieren auf Bedrohungen in Echtzeit.

**Remote- und Mobilzugriff und Geschäftspartner**

- Verbessern der Sicherheit für Remote-und mobile Mitarbeiter

  Implementieren Sie Ihr eigenes Gerät (BYOD) und die unternehmenseigene Geräteverwaltung, um sicherzustellen, dass ein geschützter Zugriff, ein korrektes Anwendungsverhalten und Datenschutz für Unternehmen gewährleistet ist.

- Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter

  Reduzieren Sie Wartungs-und Supportkosten und verbessern Sie die Leistung für die Remotezugriffslösung durch Verschieben häufig abgerufener Ressourcen in der Cloud.

- Bereitstellen besserer Konnektivität und geringerer Overhead für Business-to-Susi-Transaktionen (B2B)

  Ersetzen Sie ein alterndes und kostspieliges Partner Extranet durch eine Cloud-basierte Lösung, die die Verbundauthentifizierung verwendet.

**Compliance**

- Einhalten von regionalen gesetzlichen Vorschriften

  Stellen Sie sicher, dass die Branchen-und regionalen Bestimmungen für Datenspeicherung, Verschlüsselung, Datenschutz und personenbezogene Daten, wie etwa die allgemeine Datenschutzverordnung (dsgvo) für die Europäische Union, eingehaltenwerden.

**Verwaltung**

- Weniger IT-Aufwand für die Verwaltung von Software, die auf Client-PCs und Geräten läuft

  Automatisieren der Installation von Updates für das Windows-Betriebssystem und Microsoft 365-Apps für Unternehmen in der gesamten Organisation.

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>Zuordnen von Contoso-Geschäftsanforderungen zu Microsoft 365 für Unternehmen

Die IT-Abteilung von Contoso hat vor der Bereitstellung die folgende Zuordnung der geschäftlichen Anforderungen zu Microsoft 365 E5-Funktionen ermittelt:


| Kategorie | Geschäftsanforderung | Microsoft 365 für Enterprise-Produkte oder-Features |
|:-------|:-----|:-----|
| Produktivität |  |  |
|  | Vereinfachen der Zusammenarbeit | Microsoft Teams, SharePoint, OneDrive |
|  | Mehr Produktivität für Telearbeiter und Mobilmitarbeiter | Microsoft 365-Arbeitslasten und cloudbasierte Daten |
|  | Mehr Kreativität und Innovation | Windows Ink, Cortana at Work, PowerPoint |
| Sicherheit |  |  |
|  | Identitäts- und Zugriffsverwaltung | Dedizierte globale Administratorkonten mit Azure Multi-Factor Authentication (MFA) und Azure Active Directory Privileged Identity Management (PIM) <BR> Mehrstufige Authentifizierung (MFA) für alle Benutzerkonten <BR> Bedingter Zugriff <BR> Windows Hello <BR> Windows Credential Guard |
|  | Bedrohungsschutz | Advanced Threat Analytics <BR> Windows Defender <BR> Advanced Threat Protection <BR> Office 365 Advanced Threat Protection <BR> Untersuchung und Antwort von Microsoft 365 Threat <BR> |
|  | Schutz von Daten | Azure Information Protection <BR> Verhinderung von Datenverlust (Data Loss Prevention, DLP) <BR> Windows Information Protection (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | Sicherheitsverwaltung | Azure Security Center  <BR> Windows Defender Security Center |
| Remote- und Mobilzugriff und Geschäftspartner |  |  |
|  | Mehr Sicherheit für Telearbeiter und Mobilmitarbeiter | Microsoft Intune |
|  | Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter | Microsoft 365-Arbeitslasten und cloudbasierte Daten |
|  | Verbessern der Konnektivität und des niedrigeren Overheads für B2B-Transaktionen | Verbundauthentifizierung und cloudbasierte Ressourcen |
| Compliance |  |  |
|  | Einhalten von regionalen gesetzlichen Vorschriften | Dsgvo-Features in Microsoft 365 |
| Verwaltung |  |  |
|  | Weniger IT-Aufwand für die Installation von Clientupdates | Windows 10 Enterprise-Updates <BR> Microsoft 365 Apps for Enterprise-Updates |
||||

## <a name="next-step"></a>Nächster Schritt

Erfahren Sie mehr über das [lokale](contoso-networking.md) Contoso Corporation-Netzwerk und wie es für den Zugriff und die Wartezeit auf Cloud-basierte Microsoft 365-Ressourcen optimiert wurde.

## <a name="see-also"></a>Siehe auch

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)
