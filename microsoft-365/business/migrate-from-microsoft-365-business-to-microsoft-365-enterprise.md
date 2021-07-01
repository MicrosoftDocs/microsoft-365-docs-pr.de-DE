---
title: Migrieren von Microsoft 365 Business zu Microsoft 365 E3
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Erfahren Sie, wie Sie Ihr Unternehmen von Microsoft 365 Business Premium zu Microsoft 365 E3 verschieben.
ms.openlocfilehash: 6502d79dbb283db37b00e4fccf89b15ab4291ce5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227617"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migrieren von Microsoft 365 Business Premium zu Microsoft 365 E3

Microsoft 365 Business Premium bietet alles, was Sie für Ihr kleines Unternehmen benötigen, und kombiniert die besten cloudbasierten Produktivitäts-Apps mit einfacher Geräteverwaltung und Sicherheit, die Es Ihren Mitarbeitern ermöglichen, ihre beste Arbeit zu leisten. In einigen Fällen müssen Sie ihr Microsoft 365 Business Premium-Abonnement jedoch möglicherweise zu Microsoft 365 E3 migrieren.

Beispielsweise ist Ihr Unternehmen ausgereift und benötigt mehr als 300 Lizenzen (herzlichen Glückwunsch).

Oder Ihr Unternehmen benötigt Unternehmensfeatures, z. B. Microsoft 365 Apps for Enterprise, Windows 10 Enterprise E3 oder Enterprise Clientzugriffslizenzen (CALs).

Das Upgrade ist einfach: Sie können das Upgrade [über das Admin Center](../commerce/subscriptions/upgrade-to-different-plan.md)starten. Alle Daten und Konfigurationen in Ihrem aktuellen Abonnement werden beibehalten. Es gibt nichts für Sie, um sich auf die Migration vorzubereiten, und nichts, was Sie danach tun müssen, außer die neuen Features zu nutzen.

> [!NOTE]
> Sie können auch ein Microsoft 365 Business Premium-Abonnement für bis zu 300 Arbeitsplätze verwenden und ein Microsoft 365 E3-Abonnement für mehr als 300 Arbeitsplätze erhalten. Microsoft Defender für Office 365 ist jedoch nicht in Microsoft 365 E3 enthalten. Für den fortgesetzten Bedrohungsschutz sollten Sie zusätzliche Defender für Office 365 Lizenzen hinzufügen, damit alle Benutzer im Bereich Ihres Defender für Office 365 Richtlinien lizenziert sind.

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Unterschiede zwischen Microsoft 365 Business Premium und Microsoft 365 Enterprise

Diese Tabelle zeigt die Unterschiede zwischen Microsoft 365 Business Premium und Microsoft 365 E3.

| Feature    | Unterstützung in Microsoft 365 Business Premium    | Unterstützung in Microsoft 365 E3 |
|:-------|:-----|:-----|
| **Lokal**        | | |
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3|
| Office-Apps*    | [Microsoft 365 Apps for Business](#office-365-business)    | Microsoft 365 Apps for Enterprise |
| **Cloud-Produktivitäts-Apps**        | | |
| Exchange Online und Outlook    | 50 GB Speicherlimit pro Postfach und unbegrenzte Exchange Online Archivierung    | Speicherlimit von 100 GB pro Postfach und unbegrenzte Exchange Online Archivierung |
| Teams    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| OneDrive for Business    | 1 TB Speicherlimit pro Benutzer    | Unbegrenzt |
| Yammer, SharePoint Online, Planner, Stream    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| **Bedrohungsschutz**        | | |
| Funktionen zur Verringerung der Angriffsfläche    | [Siehe diese Liste](#threat-protection) | Enterprise Verwaltung der hardwarebasierten Isolation für Microsoft Edge |
| Microsoft Defender für Office 365 Plan 1 | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | Nicht enthalten, kann aber hinzugefügt werden |
| **Identitätsverwaltung**        | | |
| Self-Service Password Reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| Cloud App Discovery, Azure AD Verbinden Health    |     | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| Azure AD Office 365 Apps Single Sign-On (SSO): 10 Apps pro Benutzer (Katalog SaaS-Apps wie Salesforce)* | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| Azure AD Premium 1 SSO: keine Beschränkung (lokale Apps über den Azure AD-Anwendungsproxy und Nicht-Katalog-Apps mit Self-Service App-Integrationsvorlagen)    |     | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| **Verwaltung von Geräten und Apps**        | | |
| Microsoft Intune, Windows Autopilot|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
|Virtual Desktop Access (VDA)    |  |     ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
|Windows Virtual Desktop (WVD)    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png) |     ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
|Aktivierung freigegebener Computer (Shared Computer Activation, SCA)    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png) |     ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| Microsoft Desktop Optimization Package    | |     ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| **Schutz von Daten**        | | |
| Office 365 Verhinderung von Datenverlust, Azure Information Protection Plan 1    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| Window Information Protection für Endpunkt-DLP    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| **Clientzugriffslizenz (CAL-Rechte)**    | | |
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| **Compliance**        | | |
| Unbegrenzte E-Mail-Archivierung    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| Compliance-Manager    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| eDiscovery    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| In-Situ-Aufbewahrung und Beweissicherungsverfahren    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
| Aufbewahrungstags und Aufbewahrungsrichtlinien für die Messaging-Datensatzverwaltung    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Microsoft 365 E3 enthalten](../media/check-mark.png) |
||||

\* Benutzer, denen der Zugriff auf SaaS-Apps zugewiesen wurde, können SSO-Zugriff auf bis zu 10 Apps erhalten. Administratoren können SSO konfigurieren und den Benutzerzugriff auf verschiedene SaaS-Apps ändern, aber SSO-Zugriff ist nur für 10 Apps pro Benutzer gleichzeitig zulässig. Alle Office 365-Apps werden als einzelne App gezählt.

## <a name="migration"></a>Migration

Um zu migrieren, arbeiten Sie mit Ihrem Partner zusammen, um Ihr Microsoft 365 Business Premium Abonnement und Die Lizenzen in ein geeignetes Microsoft 365 E3 Abonnement mit seinen Lizenzen zu verschieben.

In den folgenden Abschnitten wird beschrieben, welche Änderungen Sie vornehmen müssen, falls vorhanden, und was Sie nach der Migration tun können.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 Abonnementkonfiguration und -daten

Sie müssen vor der Migration keine Änderungen an Ihrem aktuellen Abonnement oder Ihren aktuellen Daten vornehmen, was Folgendes umfasst:

- Abonnementkonfiguration, z. B. DNS-Domänennamen.
- Benutzer- und Gruppenkonten und Authentifizierungseinstellungen, z. B. mehrstufige Authentifizierung oder Richtlinien für bedingten Zugriff.
- Produktivitätsdienstkonfigurationen und deren Daten, z. B. Teams, Exchange Online Postfächer, SharePoint Onlinewebsites, OneDrive for Business Ordner und OneNote Notizbücher.

Ihre Benutzer können jetzt unbegrenzten Speicherplatz in den Exchange Online Postfächern und OneDrive for Business Ordnern nutzen.

Sie können mit der Verwendung von Cloud App Discovery, Azure AD Verbinden Health und SSO für mehr als 10 Apps beginnen.

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Bedrohungsschutz

Windows 10 Business umfasst die folgenden Schutzmaßnahmen:

- Integritätserzwingung des Betriebssystemstartprozesses
- Integritätserzwingung vertraulicher Betriebskomponenten
- Erweiterte Sicherheitsrisiken und Zero-Day-Exploit-Gegenmaßnahmen
- Reputationsbasierter Netzwerkschutz für Microsoft Edge, Internet Explorer und Chrome
- Hostbasierte Firewall
- Ransomware-Gegenmaßnahmen
- Hardwarebasierte Isolation für Microsoft Edge
- Anwendungssteuerung, die von der intelligenten Sicherheits-Graph unterstützt wird
- Gerätesteuerung (USB)
- Netzwerkschutz für webbasierte Bedrohungen
- Regeln zur Verhinderung von Hostangriffen

Windows 10 Enterprise E3 umfasst auch die Unternehmensverwaltung der hardwarebasierten Isolation für Microsoft Edge.

> [!NOTE]
> Benutzer, die zu Microsoft 365 E3 migriert wurden, benötigen jeweils eine Microsoft Defender für Office 365-Lizenz für den fortgesetzten Bedrohungsschutz. Achten Sie darauf, zusätzliche Defender für Office 365 Lizenzen zu erwerben, damit alle Benutzer im Bereich Ihres Defender für Office 365 Richtlinien lizenziert sind.

### <a name="device-management-with-intune"></a>Geräteverwaltung mit Intune

Sie müssen vor der Migration keine Änderungen an Ihrer aktuellen Intune-Konfiguration vornehmen, die registrierte Geräte sowie Geräte- und App-Einstellungen umfasst.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium enthält Windows 10 Business, die Sie mit Windows AutoPilot installieren können. Wenn Sie zu Microsoft 365 E3 migrieren, enthält jede Benutzerlizenz Windows 10 Enterprise E3, die Sie auch mit Windows Autopilot installieren können.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps for Business

Der auf Ihren Geräten installierte Microsoft 365 Apps for Business-Client beginnt automatisch mit der Verwendung der Features von Microsoft 365 Apps for Enterprise. Nach der Migration können Sie jetzt Folgendes verwenden:

- Unterstützung der Gruppenrichtlinie
- Vergleich und Untersuchung von Tabellenkalkulationen
- Business intelligence
