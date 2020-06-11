---
title: Fördern von Remotemitarbeitern mit Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Konfigurieren Sie Sicherheit und Dienstinfrastruktur, die es Ihren Arbeitnehmern ermöglicht, von überall und jederzeit remote zu arbeiten.
ms.openlocfilehash: 763c8e745eb54897c1df88ecb5a9064987ed5a13
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560462"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>Fördern von Remotemitarbeitern mit Microsoft 365

Ihr Unternehmen muss möglicherweise Ihren Arbeitnehmern von zu Hause aus einen sicheren Zugang zu den Informationen, Tools und Ressourcen Ihres Unternehmens vor Ort und in der Cloud ermöglichen. Für viele Organisationen ist es wichtig, dass die Arbeitnehmer auch außerhalb des Büros nahtlos und sicher arbeiten können:

- Einsparen von Bürofläche.
- Einstellung und Bindung von Arbeitnehmern, die nicht bereit sind, umzuziehen.
- Verringern Sie das Pendeln von Arbeitnehmern, sodass ihnen mehr Zeit bleibt, produktiv zu sein und stressmindernde Tätigkeiten außerhalb der Arbeit zu verrichten.

Remotearbeit, auch als "Telearbeit" oder "Heimarbeit" bezeichnet, kann ein breites Spektrum umfassen:

- Arbeitnehmer, die sich gelegentlich für Konferenzen oder Kundenbesprechungen außerhalb des Büros befinden.
- Einige Arbeitnehmer, die Telearbeit in Vollzeit ausüben.
- Eine komplette Remoteorganisation, die kein eigenes Büro unterhält und deren Mitarbeiter alle remote arbeiten.

Remote-Mitarbeiter können von überall auf der Welt und jederzeit auf Folgendes zugreifen:

- Organisationsressourcen, wie sie z. B. in lokalen Anwendungsrechenzentren verfügbar sind.
- Cloudbasierte Dienste und Daten in Ihrem Microsoft 365-Abonnement, z. B. Microsoft Teams, Exchange Online, SharePoint und OneDrive.

Für einen flüssigen Anmeldevorgang sollten Ihre AD DS-Benutzerkonten (Active Directory Domain Services) mit Azure Active Directory (Azure AD) synchronisiert werden. Um Ihre Windows 10-Geräte zu schützen, sollten sie in Intune registriert werden. Hier ist eine allgemeine Übersicht über die Infrastruktur.

![Grundlegende Infrastruktur für Remotemitarbeiter mit Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)


Zur Unterstützung Ihrer Remotemitarbeiter, beispielsweise als Reaktion auf die COVID-19-Krise, bietet Microsoft 365 eine umfassende Kombination aus Features für die Zusammenarbeit, z. B.:

- Onlinebesprechungen und Chatsitzungen.
- Freigegebene Arbeitsbereiche für cloudbasierte Dateispeicherung mit globalem Zugriff und Zusammenarbeit in Echtzeit.
- Gemeinsame Aufgaben und Workflows, um die Arbeit aufzuteilen und Dinge zu erledigen.

Für eine starke Sicherheit bietet Microsoft 365 Folgendes:

- Anforderungen für eine erzwungene Authentifizierung, Erkennen von und Reagieren auf Anmeldungen mit hohem Risiko und Blockieren ausgewählter Apps und nicht kompatibler Geräte.
- Verschlüsselte Verbindungen und digitale Objekte in der Cloud.
- Berechtigungen, mit denen definiert werden kann, wer mit Dateien wie umgehen kann.
- Umfassende Sicherheitsfeatures zum Schutz von Windows 10-Geräten.

Verwenden Sie zur Erfüllung dieser Voraussetzungen für Remotemitarbeiter die folgenden Microsoft 365-Funktionen und -Features.

| Funktion oder Feature | Beschreibung | Lizenzierung |
|:-------|:-----|:-------|
| Mehrstufige Authentifizierung (MFA, Multi-Factor Authentication) mit Sicherheitsstandards erzwingen   | Schützen Sie sich vor kompromittierten Identitäten und Geräten, indem Sie eine zweite Authentifizierungsmethode für die Anmeldung vorsehen. Sicherheitsstandards schreiben MFA für alle Benutzerkonten vor.   | Microsoft 365 E3 und E5 |
| Mehrstufige Authentifizierung (MFA, Multi-Factor Authentication) mit bedingtem Zugriff erzwingen| Erfordert MFA basierend auf den Anmeldungseigenschaften mit Richtlinien für bedingten Zugriff.    | Microsoft 365 E3 und E5 | 
| Mehrstufige Authentifizierung (MFA, Multi-Factor Authentication) mit risikoabhängig bedingtem Zugriff erzwingen   | Erfordert MFA basierend auf dem Risiko der Benutzeranmeldung mit Azure Advanced Threat Protection. | Microsoft 365 E5 oder E3 mit Azure AD Premium P2-Lizenzen | 
| Zurücksetzen von Kennwörtern durch den Benutzer (Self-Service Password Reset, SSPR)    | Ermöglichen Sie Ihren Benutzern das Zurücksetzen oder Entsperren ihrer Kennwörter oder Konten.  | Microsoft 365 E3 und E5 |
| Azure AD-Anwendungsproxy    | Sorgen Sie für sicheren Remotezugriff für webbasierte Anwendungen, die auf Intranet-Servern gehostet sind.   | Erfordert separates kostenpflichtiges Azure-Abonnement |
| Azure Punkt-zu-Site-VPN   | Erstellen Sie über ein virtuelles Azure-Netzwerk eine sichere Verbindung vom Gerät eines Remotemitarbeiters zu Ihrem Intranet.   | Erfordert separates kostenpflichtiges Azure-Abonnement |
| Windows Virtual Desktop   | Unterstützen Sie Mitarbeiter, die nur ihre persönlichen und nicht verwalteten Geräte verwenden können, mit virtuellen Desktops, die in Azure ausgeführt werden. | Erfordert separates kostenpflichtiges Azure-Abonnement |
| Remotedesktopdienste (RDS) | Ermöglichen Sie Mitarbeitern die Verbindung mit Windows-basierten Computern in Ihrem Intranet. | Microsoft 365 E3 und E5 | 
| Remotedesktopdienste-Gateway   | Sorgen Sie für verschlüsselte Kommunikationen und verhindern Sie, dass RDS-Hosts direkt über das Internet erreichbar sind. | Erfordert separate Windows Server-Lizenzen |
| Microsoft Intune | Verwalten Sie Geräte und Anwendungen.   | Microsoft 365 E3 und E5 | 
| Configuration Manager | Verwalten Sie Softwareinstallationen, Updates und Einstellungen auf Ihren Geräten. | Erfordert separate Configuration Manager-Lizenzen |
| Desktop Analytics | Ermitteln Sie die Update-Bereitschaft Ihrer Windows-Clients.   | Erfordert separate Configuration Manager-Lizenzen |
| Windows Autopilot | Richten Sie neue Windows 10-Geräte ein, und konfigurieren Sie sie für eine produktive Nutzung.   | Microsoft 365 E3 und E5 |
| Microsoft Teams, Exchange Online, SharePoint Online und OneDrive, Microsoft 365 Apps, Microsoft Power Platform, Yammer, Power Apps | Planen, kommunizieren und zusammenarbeiten. | Microsoft 365 E3 und E5 |
||||

Nutzen Sie diese Schritte, um den Zugriff auf die Server, Daten und Cloud-Dienste Ihres Unternehmens zu sichern und zu optimieren und eine maximale Mitarbeiterproduktivität zu ermöglichen.

1. [Erhöhung der Anmeldesicherheit durch MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Bereitstellung des Remotezugriffs auf lokale Apps und Dienste](empower-people-to-work-remotely-remote-access.md)
3. [Bereitstellen der Endpunktverwaltung für Ihre Geräte, PCs und andere Endpunkte](empower-people-to-work-remotely-manage-endpoints.md)
4. [Bereitstellen von Produktivitätsanwendungen und -diensten für Remotemitarbeiter](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [Erstellen von Kommunikationsveranstaltungsorten](empower-people-to-work-remotely-communication-venues.md)
6. [Schulung von Remotemitarbeitern und Ansprechen von Nutzungsrückmeldungen](empower-people-to-work-remotely-train-monitor-usage.md)

![Die Schritte zum Fördern von Remotemitarbeitern mit Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

Die neuesten Informationen von Microsoft zur Unterstützung von Remotemitarbeitern finden Sie auf der [Tech Community-Website über das Fördern von Remotearbeit](https://resources.techcommunity.microsoft.com/enabling-remote-work/).
