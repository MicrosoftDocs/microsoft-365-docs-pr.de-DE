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
description: Erfahren Sie, wie Sie Ihr Unternehmen von Microsoft 365 Business Premium auf Microsoft 365 E3 umziehen.
ms.openlocfilehash: 019a422bb879389f42a32cf30f9a8094f776078a
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126199"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migrieren von Microsoft 365 Business Premium zu Microsoft 365 E3

Microsoft 365 Business Premium bietet alles, was Sie für Ihr kleines Unternehmen benötigen, und kombiniert die erstklassigen cloudbasierten Produktivitäts-Apps mit einfacher Geräteverwaltung und Sicherheit, mit denen Ihre Mitarbeiter ihre beste Arbeit machen können. In einigen Fällen müssen Sie Jedoch möglicherweise Ihr Microsoft 365 Business Premium-Abonnement zu Microsoft 365 E3 migrieren. 

Ihr Unternehmen ist beispielsweise größer geworden und benötigt mehr als 300 Lizenzen (herzlichen Glückwunsch).

Oder Ihr Unternehmen benötigt Unternehmensfeatures wie Microsoft 365 Apps for Enterprise, Windows 10 Enterprise E3 oder Enterprise Client Access Licenses (CALs).

Das Upgrade ist einfach: Sie können das Upgrade [über das Admin Center starten.](../commerce/subscriptions/upgrade-to-different-plan.md) Alle Ihre Daten und Konfigurationen in Ihrem aktuellen Abonnement werden verwaltet. Es gibt nichts, was Sie zur Vorbereitung der Migration tun müssen, und nichts, was Sie später tun müssen, außer die neuen Features zu nutzen.

>[!Note]
>Sie können auch ein Microsoft 365 Business Premium-Abonnement für bis zu 300 Plätze verwenden und ein Microsoft 365 E3-Abonnement für mehr als 300 Plätze erhalten. Microsoft Defender für Office 365 ist jedoch nicht in Microsoft 365 E3 enthalten. Für den weiteren Bedrohungsschutz sollten Sie zusätzliche Defender für Office 365-Lizenzen hinzufügen, damit alle Benutzer im Bereich Ihrer Defender für Office 365-Polizeien lizenziert sind.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Unterschiede zwischen Microsoft 365 Business Premium und Microsoft 365 Enterprise

Diese Tabelle zeigt die Unterschiede zwischen Microsoft 365 Business Premium und Microsoft 365 E3.

| Feature    | Support in Microsoft 365 Business Premium    | Support in Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **Lokal**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| Office-Apps*    | [Microsoft 365 Apps for Business](#office-365-business)    | Microsoft 365 Apps for Enterprise | 
| **Cloudproduktivitäts-Apps**        | | | 
| Exchange Online und Outlook    | Speichergrenzwert von 50 GB pro Postfach und unbegrenzte Exchange Online-Archivierung    | Speichergrenzwert von 100 GB pro Postfach und unbegrenzte Exchange Online-Archivierung | 
| Teams    | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | Speichergrenzwert von 1 TB pro Benutzer    | Unbegrenzt | 
| Yammer, SharePoint Online, Planner, Stream    | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| MileIQ    | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Bedrohungsschutz**        | | | 
| Funktionen zur Reduzierung der Angriffsfläche    | [Siehe diese Liste](#threat-protection) | Unternehmensverwaltung der hardwarebasierten Isolation für Microsoft Edge | 
| Defender für Office 365 Plan 1 | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | Nicht enthalten, kann aber hinzugefügt werden | 
| **Identitätsverwaltung**        | | | 
| Self-Service-Kennwortzurücksetzung für Azure Active Directory (Azure AD)-Hybridkonten, Azure AD Multi-Factor Authentication (MFA), bedingter Zugriff, Kennwortrückschreiben für lokale Identitäten|     ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| Cloud App Discovery, Azure AD Connect Health    |     | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Office 365 apps Single Sign-On (SSO): 10 Apps pro Benutzer (Gallery SaaS apps such as Salesforce)* | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: keine Beschränkung (lokale Apps über Azure AD-Anwendungsproxy und Nicht-Katalog-Apps, die Self-Service App-Integrationsvorlagen verwenden)    |     | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| **Verwaltung von Geräten und Apps**        | | | 
| Microsoft Intune, Windows Autopilot|     ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
|Virtual Desktop Access (VDA)    |  |     ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
|Windows Virtual Desktop (WVD)    | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png) |     ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
|Aktivierung gemeinsam genutzter Computer (Shared Computer Activation, SCA)    | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png) |     ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| Microsoft Desktop Optimization Package    | |     ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| **Schutz von Daten**        | | | 
| Office 365 Data Loss Prevention, Azure Information Protection Plan 1    | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| Window Information Protection für Endpunkt-DLP    | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| **Clientzugriffslizenz (CAL-Rechte)**    | | |     
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| **Compliance**        | | | 
| Unbegrenzte E-Mail-Archivierung    | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| Compliance-Manager    | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| eDiscovery    | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| In-Place-Hold und Litigation Hold    | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
| Aufbewahrungstags und Aufbewahrungsrichtlinien für die Messaging-Datensatzverwaltung    | ![Enthalten in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Microsoft 365 E3](../media/check-mark.png) | 
||||

\* Benutzer, denen Der Zugriff auf die SaaS-Apps zugewiesen wurde, können SSO-Zugriff auf bis zu 10 Apps erhalten. Administratoren können SSO konfigurieren und den Benutzerzugriff auf verschiedene SaaS-Apps ändern, aber der Zugriff auf einmaliges Einmaliges Konto ist nur für 10 Apps pro Benutzer gleichzeitig zulässig. Alle Office 365-Apps werden als einzelne App gezählt.

## <a name="migration"></a>Migration

Um zu migrieren, arbeiten Sie mit Ihrem Partner zusammen, um Ihr Microsoft 365 Business Premium-Abonnement und Lizenzen in ein geeignetes Microsoft 365 E3-Abonnement mit seinen Lizenzen zu verschieben.

In den folgenden Abschnitten wird beschrieben, welche Änderungen Sie gegebenenfalls vornehmen müssen und was Sie nach der Migration tun können.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Konfiguration und Daten des Microsoft 365-Abonnements

Sie müssen vor der Migration keine Änderungen an Ihrem aktuellen Abonnement oder ihren Daten vornehmen. Dazu gehören:

- Abonnementkonfiguration, z. B. DNS-Domänennamen.
- Benutzer- und Gruppenkonten und Authentifizierungseinstellungen, z. B. mehrstufige Authentifizierung oder Richtlinien für bedingten Zugriff.
- Konfigurationen des Produktivitätsdiensts und deren Daten, z. B. Teams, Exchange Online-Postfächer, SharePoint Online-Websites, OneDrive for #A0 und OneNote-Notizbücher.

Ihre Benutzer können jetzt unbegrenzten Speicherplatz in den Exchange #A0 und OneDrive for #A1 nutzen.

Sie können mit der Verwendung von Cloud App Discovery, Azure AD Connect Health und SSO für mehr als 10 Apps beginnen.

>[!Note]
>Benutzer, die zu Microsoft 365 E3 migriert wurden, können MilesIQ nicht mehr verwenden.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Bedrohungsschutz

Windows 10 Business umfasst die folgenden Schutzmaßnahmen:

- Erzwingung der Integrität des Betriebssystemstartvorgangs
- Erzwingung der Integrität vertraulicher Betriebskomponenten
- Erweiterte Sicherheitslücken und Zero-Day-Exploit-Gegenmaßnahmen
- Reputationsbasierter Netzwerkschutz für Microsoft Edge, Internet Explorer und Chrome
- Hostbasierte Firewall
- Gegenmaßnahmen gegen Ransomware
- Hardwarebasierte Isolierung für Microsoft Edge
- Von Intelligent Security Graph unterstütztes Anwendungssteuerelement
- Gerätesteuerung (USB)
- Netzwerkschutz für webbasierte Bedrohungen
- Regeln zur Verhinderung von Hostangriffen

Windows 10 Enterprise E3 umfasst auch die Unternehmensverwaltung der hardwarebasierten Isolation für Microsoft Edge.

>[!Note]
>Benutzer, die zu Microsoft 365 E3 migriert wurden, benötigen jeweils eine Microsoft Defender für Office 365-Lizenz für den fortgesetzten Bedrohungsschutz. Achten Sie darauf, zusätzliche Defender für Office 365-Lizenzen zu erwerben, damit alle Benutzer im Bereich Ihrer Defender für Office 365-Richtlinie lizenziert sind. 
>

### <a name="device-management-with-intune"></a>Geräteverwaltung mit Intune

Sie müssen vor der Migration keine Änderungen an Ihrer aktuellen Intune-Konfiguration vornehmen, die registrierte Geräte sowie Geräte- und App-Einstellungen umfasst.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium umfasst Windows 10 Business, das Sie mit Windows AutoPilot installieren können. Bei der Migration zu Microsoft 365 E3 umfasst jede Benutzerlizenz Windows 10 Enterprise E3, die Sie auch mit Windows Autopilot installieren können.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps for Business

Ihr auf Ihren Geräten installierter Microsoft 365 Apps for Business-Client verwendet automatisch die Features von Microsoft 365 Apps for Enterprise. Nach der Migration können Sie nun:

 - Unterstützung der Gruppenrichtlinie
 - Vergleichen und Abfragen von Tabellenkalkulationen
 - Business intelligence

