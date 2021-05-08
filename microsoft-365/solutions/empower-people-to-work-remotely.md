---
title: Einrichten der Infrastruktur für Remotearbeit mit Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
- M365initiative-coredeploy
ms.custom: seo-marvel-jun2020
keywords: von Zuhause arbeiten, Heimarbeit, hybrid, Remotearbeitskraft, hybride Arbeit, Remote-Angestellte, hybride Verbindung, Remotezugriff, Fernarbeit, Telearbeit, Telearbeiten, Mobilarbeit, Remote-Job, arbeiten von überall, flexibler Arbeitsplatz
description: Gehen Sie durch die Schichten der Infrastruktur hindurch, damit Ihre Remote-Mitarbeiter sicher auf lokale und Microsoft 365-Ressourcen zugreifen können.
ms.openlocfilehash: 1a8cf471cf92e1301c231f395ed0238bb35359cb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246320"
---
# <a name="set-up-your-infrastructure-for-remote-work-with-microsoft-365"></a>Einrichten der Infrastruktur für Remotearbeit mit Microsoft 365

Um die Produktivität und Zusammenarbeit Ihrer Remote-Mitarbeiter zu sichern und zu optimieren, müssen Sie Ihre IT- und Cloud-Infrastruktur so konfigurieren, dass sie Remotearbeit ermöglicht und den Zugriff auf die lokalen und Cloud-basierten Informationen, Tools und Ressourcen Ihres Unternehmens ermöglicht. Diese Lösung führt Sie schrittweise durch die Bereitstellung wichtiger Schichten der Infrastruktur, die Ihre Mitarbeiter in die Lage versetzen, ihre beste Arbeit zu leisten, egal wo sie sind.

Es ist für viele Organisationen wichtig, den Mitarbeitern das Arbeiten außerhalb des Büros zu ermöglichen:

- Einsparen von Bürofläche.
- Einstellung und Bindung von Arbeitnehmern, die nicht bereit sind, umzuziehen.
- Verringern Sie das Pendeln von Arbeitnehmern, sodass ihnen mehr Zeit bleibt, produktiv zu sein und stressmindernde Tätigkeiten außerhalb der Arbeit zu verrichten.

Microsoft 365 bietet die Möglichkeit, Ihre Mitarbeiter zu befähigen, Remote zu arbeiten.

![Fördern Ihrer Remotemitarbeiter mit Microsoft 365](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

>[!Note]
>Wenn Sie neu bei Microsoft 365 sind, sehen Sie sich [diese Ressourcen](https://www.microsoft.com/microsoft-365) an.
>

Schauen Sie sich dieses Video an, um einen Überblick über den Bereitstellungsprozess zu erhalten.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

Für IT-Experten, die Onsite- und cloudbasierte Infrastrukturen verwalten, um die Produktivität der Mitarbeiter zu steigern, bietet diese Lösung folgende wichtigen Funktionen:

- Verbunden

  Von überall auf der Welt und jederzeit können Remote-Mitarbeiter zugreifen: 

  - Cloud-basierte Dienste und Daten in Ihrem Microsoft 365-Abonnement. 

  - Organisationsressourcen, wie sie z. B. in lokalen Anwendungsrechenzentren verfügbar sind.

- Sicher

  Die Anmeldungen werden durch die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) und die integrierten Sicherheitsfeatures von Microsoft 365 und Windows 10 geschützt und schützen vor Schadsoftware, bösartigen Angriffen und Datenverlust.

- Verwaltet

  Die Geräte Ihrer aus der Ferne arbeitenden Mitarbeiter können mit Sicherheitseinstellungen, zulässigen Apps und zur Einhaltung der Systemintegrität aus der Cloud verwaltet werden.

- Kooperativ und produktiv

  Ihre aus der Ferne arbeitenden Mitarbeiter können so produktiv wie die lokal arbeitenden sein – und das auf sehr kooperative Weise mit:

  - Onlinebesprechungen und Chatsitzungen mit Teams. 

  - Freigegebene Arbeitsbereiche für cloudbasierte Dateispeicherung mit globalem Zugriff und Zusammenarbeit in Echtzeit mit SharePoint und OneDrive.

  - Gemeinsame Aufgaben und Workflows, um die Arbeit aufzuteilen und Dinge zu erledigen. 

Für einen flüssigen Anmeldevorgang sollten Ihre lokalen AD DS-Benutzerkonten (Active Directory Domain Services) mit Azure Active Directory (Azure AD) synchronisiert werden. Um Ihre Windows 10-Geräte zu schützen, sollten sie in Intune registriert werden. Hier ist eine allgemeine Übersicht über die Infrastruktur.

![Grundlegende Infrastruktur für Remotemitarbeiter mit Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

Verwenden Sie diese Microsoft 365-Features, um die Funktionen von Microsoft 365 für Ihre Remotemitarbeiter zu aktivieren.

| Funktion oder Feature | Beschreibung | Lizenzierung |
|:-------|:-----|:-------|
| Mehrstufige Authentifizierung (MFA, Multi-Factor Authentication) mit Sicherheitsstandards erzwingen   | Schützen Sie sich vor kompromittierten Identitäten und Geräten, indem Sie eine zweite Authentifizierungsmethode für die Anmeldung vorsehen. Sicherheitsstandards schreiben MFA für alle Benutzerkonten vor.   | Microsoft 365 E3 oder E5 |
| Mehrstufige Authentifizierung (MFA, Multi-Factor Authentication) mit bedingtem Zugriff erzwingen| Erfordert MFA basierend auf den Anmeldungseigenschaften mit Richtlinien für bedingten Zugriff.    | Microsoft 365 E3 oder E5 | 
| Mehrstufige Authentifizierung (MFA, Multi-Factor Authentication) mit risikoabhängig bedingtem Zugriff erzwingen   | Erfordert MFA basierend auf dem Risiko der Benutzeranmeldung mit Microsoft Defender for Identity. | Microsoft 365 E5 oder E3 mit Azure AD Premium P2-Lizenzen | 
| Zurücksetzen von Kennwörtern durch den Benutzer (Self-Service Password Reset, SSPR)    | Ermöglichen Sie Ihren Benutzern das Zurücksetzen oder Entsperren ihrer Kennwörter oder Konten.  | Microsoft 365 E3 oder E5 |
| Azure AD-Anwendungsproxy    | Sorgen Sie für sicheren Remotezugriff für webbasierte Anwendungen, die auf Intranet-Servern gehostet sind.   | Erfordert separates kostenpflichtiges Azure-Abonnement |
| Azure Punkt-zu-Site-VPN   | Erstellen Sie über ein virtuelles Azure-Netzwerk eine sichere Verbindung vom Gerät eines Remotemitarbeiters zu Ihrem Intranet.   | Erfordert separates kostenpflichtiges Azure-Abonnement |
| Windows Virtual Desktop   | Unterstützen Sie Mitarbeiter, die nur ihre persönlichen und nicht verwalteten Geräte verwenden können, mit virtuellen Desktops, die in Azure ausgeführt werden. | Erfordert separates kostenpflichtiges Azure-Abonnement |
| Remotedesktopdienste (RDS) | Ermöglichen Sie Mitarbeitern die Verbindung mit Windows-basierten Computern in Ihrem Intranet. | Microsoft 365 E3 oder E5 | 
| Remotedesktopdienste-Gateway   | Sorgen Sie für verschlüsselte Kommunikationen und verhindern Sie, dass RDS-Hosts direkt über das Internet erreichbar sind. | Erfordert separate Windows Server-Lizenzen |
| Microsoft Intune | Verwalten Sie Geräte und Anwendungen.   | Microsoft 365 E3 oder E5 | 
| Configuration Manager | Verwalten Sie Softwareinstallationen, Updates und Einstellungen auf Ihren Geräten. | Erfordert separate Configuration Manager-Lizenzen |
| Desktop Analytics | Ermitteln Sie die Update-Bereitschaft Ihrer Windows-Clients.   | Erfordert separate Configuration Manager-Lizenzen |
| Windows Autopilot | Richten Sie neue Windows 10-Geräte ein, und konfigurieren Sie sie für eine produktive Nutzung.   | Microsoft 365 E3 oder E5 |
| Microsoft Teams, Exchange Online, SharePoint Online und OneDrive, Microsoft 365 Apps, Microsoft Power Platform und Yammer | Planen, kommunizieren und zusammenarbeiten. | Microsoft 365 E3 oder E5 |
||||

Informationen zu den Sicherheits- und Compliance-Kriterien finden Sie unter [Bereitstellen von Sicherheit und Compliance für Remotemitarbeiter](empower-people-to-work-remotely-security-compliance.md).

<a name="poster"></a> Eine zweiseitige Zusammenfassung dieser Lösung finden Sie auf dem [Poster „Fördern von Remotemitarbeitern“](../downloads/empower-remote-workers.pdf).

[![Poster "Fördern von Remotemitarbeitern"](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)

Sie können dieses Poster auch im [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf)- oder [PowerPoint](https://download.microsoft.com/download/5/1/1/511b77a9-a34c-4ea7-af2a-32b07f20b780/empower-remote-workers.pptx)-Format herunterladen und in den Formaten „Brief“, „Legal“ oder „Tabloid“ (27,94 x 43,18 cm) ausdrucken.

## <a name="provide-remote-working-for-all-of-your-workers"></a>Ermöglichen Sie all Ihren Mitarbeitern Remotearbeit.

Mit diesen Geräten können Sie allen Ihren Mitarbeitern ermöglichen, überall produktiv zu sein:

- Modernes Gerät, wie z. B. Surface-Laptop mit Windows 10, das über die Features, Sicherheit und Leistung verfügt, um direkt über das Internet auf Microsoft 365 Cloud-Apps und -Dienste zuzugreifen.

- Alle Geräte, einschließlich älterer Laptops oder Desktops, die von zu Hause aus genutzt werden und indirekt über einen schnell bereitgestellten [virtuellen Desktop mit Windows 10](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices) auf Microsoft 365 Cloud-Apps und -Dienste zugreifen können. Diese Option bietet hohe Leistung, starke Sicherheit und vereinfachte IT-Verwaltung.

## <a name="next-steps"></a>Nächste Schritte

Nutzen Sie diese Schritte, um den Zugriff auf die Server und Clouddienste Ihres Unternehmens zu sichern und zu optimieren und eine maximale Mitarbeiterproduktivität zu ermöglichen.

1. [Erhöhung der Anmeldesicherheit durch MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Bereitstellung des Remotezugriffs auf lokale Apps und Dienste](empower-people-to-work-remotely-remote-access.md)
3. [Sicherheit und Compliance bereitstellen](empower-people-to-work-remotely-security-compliance.md)
4. [Bereitstellen der Endpunktverwaltung für Ihre Geräte, PCs und andere Endpunkte](empower-people-to-work-remotely-manage-endpoints.md)
5. [Bereitstellen von Produktivitätsanwendungen und -diensten für Remotemitarbeiter](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [Schulung von Remotemitarbeitern und Ansprechen von Nutzungsrückmeldungen](empower-people-to-work-remotely-train-monitor-usage.md)

[![Die Schritte zum Einrichten der Infrastruktur für Remotearbeit mit Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)

Sehen Sie sich hier an, wie eine fiktive aber repräsentative, multinationale Organisation ihre Infrastruktur für Remotearbeit einrichtete: [Die COVID-19-Reaktion von Contoso und seine Infrastruktur, die Remote- und Vor-Ort-Arbeit ermöglicht](contoso-remote-onsite-work.md).
