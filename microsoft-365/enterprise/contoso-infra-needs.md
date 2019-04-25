---
title: IT-Infrastruktur und geschäftliche Anforderungen von Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen zur grundlegenden Struktur der lokalen IT-Infrastruktur von Contoso und wie die Unternehmensanforderungen mithilfe von Microsoft 365 Enterprise erfüllt werden können.
ms.openlocfilehash: bd259f367cdf3417e32671457f248029c853b6f8
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283677"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a>IT-Infrastruktur und geschäftliche Anforderungen von Contoso

**Zusammenfassung:** Informationen zur grundlegenden Struktur der lokalen IT-Infrastruktur von Contoso und wie die Unternehmensanforderungen mithilfe von Microsoft 365 Enterprise erfüllt werden können.


Contoso ist dabei, von der lokalen zentralen IT-Infrastruktur auf eine cloudeinschließende Infrastruktur umzustellen, die aus cloudbasierten persönlichen Produktivitätsarbeitslasten und Anwendungen besteht.

## <a name="contosos-existing-it-infrastructure"></a>Contosos vorhandene IT-Infrastruktur

Contoso nutzt eine weitestgehend zentrale lokale IT-Infrastruktur mit Anwendungsrechenzentren in der Pariser Zentrale.

Abbildung 1 zeigt eine Unternehmenszentrale mit Anwendungsrechenzentren, einer DMZ und Internet.

![](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

**Abbildung 1: Contosos vorhandene IT-Infrastruktur**
 
In den lokalen Anwendungsrechenzentren wird Folgendes gehostet: 

- Benutzerdefinierte Branchenanwendungen, die SQL Server und andere Linux-Datenbanken verwenden.
- Eine Reihe von älteren SharePoint-Servern.
- Server auf Organisations- und Teamebene für das Speichern von Dateien.

Darüber hinaus jedes regionales Hub-Büro, das eine Reihe von Servern mit einer ähnlichen Gruppe von Anwendungen unterstützt. Diese Server werden von regionalen IT-Abteilungen gesteuert.

Die Durchsuchbarkeit über die Anwendungen und Daten dieser separaten Rechenzentren an mehreren geografischen Standorten hinweg bleibt eine Herausforderung.

In der DMZ am Hauptsitz von Contoso bieten verschiedene Servergruppen Folgendes:

- VPN-basierter Remotezugriff auf das Contoso-Intranet und Webproxyfunktion für Mitarbeiter in der Pariser Zentrale.
- Hosting der öffentlichen Contoso-Website, über die Kunden Produkte, Teile, Zubehör oder Dienstleistungen bestellen können.
- Hosting für das Contoso-Partnerextranet für die Kommunikation und Zusammenarbeit mit Partnern.

## <a name="contosos-business-needs"></a>Contosos Geschäftsanforderungen

Die Geschäftsanforderungen von Contoso können in fünf Hauptkategorien unterteilt werden.

Produktivität:

- Vereinfachen der Zusammenarbeit

  Ersetzen Sie die auf E-Mails und Dateifreigaben basierte Zusammenarbeit durch ein Onlinemodell, das Echtzeitänderungen an Dokumenten, einfachere Onlinebesprechungen und erfasste Unterhaltungsthreads ermöglicht.
- Mehr Produktivität für Telearbeiter und Mobilmitarbeiter

  Viele Mitarbeiter arbeiten von zu Hause aus oder unterwegs – ersetzen Sie daher die zu Engpässen führende VPN-Lösung durch leistungsstarken Zugriff auf Contoso-Daten und -Ressourcen in der Cloud.
- Mehr Kreativität und Innovation

  Nutzen Sie die Vorteile der neuesten visuellen Lern- und Ideenfindungsmethoden, einschließlich Freihand und 3D-Visualisierung.

Sicherheit:

- Identitäts- und Zugriffsverwaltung

  Erzwingen Sie die mehrstufige Authentifizierung und andere Formen der Authentifizierung, und schützen Sie Anmeldeinformationen von Benutzer- und Administratorkonten.

- Bedrohungsschutz

  Schutz vor externen Sicherheitsrisiken, einschließlich Schadsoftware, die auf E-Mails oder dem Betriebssystem basiert.

- Schutz von Daten

  Sperren Sie den Zugriff auf wichtige digitale Ressourcen, und verschlüsseln Sie diese (z. B. Kundendaten, Entwurfsspezifikationen und Mitarbeiterinformationen).

- Sicherheitsverwaltung

  Überwachen des Sicherheitszustands und Ermitteln von sowie Reagieren auf Bedrohungen in Echtzeit.

Remote- und Mobilzugriff und Geschäftspartner:

- Mehr Sicherheit für Telearbeiter und Mobilmitarbeiter

  Führen Sie BYOD (Bring Your Own Device) und die Verwaltung von firmeneigenen Geräten ein, um einen sicheren Zugriff, ein korrektes Anwendungsverhalten sowie den Schutz von Unternehmensdaten zu gewährleisten.

- Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter

  Senken Sie die Wartungs- und Supportkosten, und verbessern Sie die Leistung für Remotezugriffslösungen, indem Sie Ressourcen, auf die häufig zugegriffen wird, in die Cloud verschieben.

- Bessere Konnektivität und weniger Aufwand für Business-to-Business-Transaktionen (B2B)

  Ersetzen Sie das in die Jahre gekommene Partnerextranet durch eine cloudbasierte Lösung, für die Verbundauthentifizierung verwendet wird.

Compliance:

- Einhalten von regionalen gesetzlichen Vorschriften

  Halten Sie branchenübliche und regionale Vorschriften für Datenspeicherung, Verschlüsselung und Datenschutz sowie Vorschriften für personenbezogene Daten ein, z. B. die DSGVO für die Europäische Union.

Verwaltung:

- Reduzieren des IT-Aufwands für die Verwaltung von Software, die auf Clientcomputern und -geräten ausgeführt wird

  Automatisieren Sie die Installation von Updates auf dem Windows-Betriebssystem und in Microsoft Office in der gesamten Organisation.

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a>Zuordnen der Geschäftsanforderungen von Contoso zu Microsoft 365 Enterprise

Von der IT-Abteilung von Contoso wurde vor der Bereitstellung die folgende Zuordnung von Geschäftsanforderungen zu den Features von Microsoft 365 Enterprise E5 vorgenommen:

||||
|:-------|:-----|:-----|
| **Kategorie** | **Geschäftsanforderung** | **Produkte oder Features von Microsoft 365 Enterprise** |
| Produktivität |  |  |
|  | Vereinfachen der Zusammenarbeit | Teams, SharePoint Online, Skype for Business Online |
|  | Mehr Produktivität für Telearbeiter und Mobilmitarbeiter | Office 365-Arbeitslasten und cloudbasierte Daten |
|  | Mehr Kreativität und Innovation | Windows Ink, Cortana at Work, PowerPoint |
| Sicherheit |  |  |
|  | Identitäts- und Zugriffsverwaltung | Dedizierte globale Administratorkonten mit mehrstufiger Authentifizierung (MFA) und Azure AD Privileged Identity Management (PIM) <BR> Mehrstufige Authentifizierung für alle Benutzerkonten <BR> Bedingter Zugriff <BR> Windows Hello <BR> Windows Credential Guard |
|  | Bedrohungsschutz | Advanced Threat Analytics <BR> Windows Defender <BR> Advanced Threat Protection <BR> Office 365 Advanced Threat Protection <BR> Untersuchung von und Antwort auf Bedrohungen in Office 365 <BR> |
|  | Schutz von Daten | Azure Information Protection <BR> Verhinderung von Datenverlust in Office 365 <BR> Windows Information Protection <BR> Microsoft Cloud App Security <BR> Office 365 Cloud App Security (CAS) <BR> Microsoft Intune |
|  | Sicherheitsverwaltung | Azure Security Center  <BR> Windows Defender Security Center |
| Remote- und Mobilzugriff und Geschäftspartner |  |  |
|  | Mehr Sicherheit für Telearbeiter und Mobilmitarbeiter | Microsoft Intune |
|  | Verkleinern der Remotezugriffsinfrastruktur für Mitarbeiter | Office 365-Arbeitslasten und cloudbasierte Daten |
|  | Bessere Konnektivität und weniger Aufwand für B2B-Transaktionen | Verbundauthentifizierung und cloudbasierte Ressourcen |
| Compliance |  |  |
|  | Einhalten von regionalen gesetzlichen Vorschriften | DSGVO-Features in Office 365 |
| Verwaltung |  |  |
|  | Reduzieren des IT-Aufwands für die Installation von Clientupdates | Bereitstellungsringe <BR> Vorhandenes Upgrade auf Windows 10 und Autopilot <BR> Office 365 ProPlus |
||||

## <a name="next-step"></a>Nächster Schritt

[Erfahren Sie mehr](contoso-networking.md) über das lokale Netzwerk von Contoso und wie dieses im Hinblick auf Zugriff und Latenz für cloudbasierte Microsoft 365-Ressourcen in der gesamten Organisation optimiert wurde.

## <a name="see-also"></a>Siehe auch

[Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)
