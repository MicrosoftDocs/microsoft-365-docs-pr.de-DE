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
description: Erfahren Sie, wie Sie Ihr Unternehmen von Microsoft 365 Business Premium Microsoft 365 E3.
ms.openlocfilehash: 10630671f3deb7eff0ad0f601d301b90743ee35f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164511"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migrieren von Microsoft 365 Business Premium zu Microsoft 365 E3

Microsoft 365 Business Premium bietet alles, was Sie für Ihr kleines Unternehmen benötigen, und kombiniert die erstklassigen cloudbasierten Produktivitäts-Apps mit einfacher Geräteverwaltung und Sicherheit, die Ihren Mitarbeitern die bestmögliche Arbeit ermöglichen. In einigen Fällen müssen Sie ihr Abonnement jedoch möglicherweise Microsoft 365 Business Premium zu Microsoft 365 E3. 

Ihr Unternehmen ist beispielsweise gewachsen und benötigt mehr als 300 Lizenzen (herzlichen Glückwunsch).

Oder Ihr Unternehmen benötigt Unternehmensfeatures, z. B. Microsoft 365 Apps for Enterprise, Windows 10 Enterprise E3 oder Enterprise Clientzugriffslizenzen (CaLs).

Das Upgrade ist einfach: Sie können das Upgrade [über das Admin Center starten.](../commerce/subscriptions/upgrade-to-different-plan.md) Alle Ihre Daten und Konfigurationen in Ihrem aktuellen Abonnement werden verwaltet. Es gibt nichts, was Sie tun müssen, um sich auf die Migration vorzubereiten, und es gibt nichts zu tun, außer die neuen Features zu nutzen.

>[!Note]
>Sie können auch ein Microsoft 365 Business Premium für bis zu 300 Plätze verwenden und ein Microsoft 365 E3 für mehr als 300 Plätze erhalten. Microsoft Defender for Office 365 ist jedoch nicht in der Microsoft 365 E3. Zum weiteren Schutz vor Bedrohungen sollten Sie zusätzliche Defender für Office 365-Lizenzen hinzufügen, damit alle Benutzer im Bereich Ihres Defender for Office 365-Polizei lizenziert sind.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Unterschiede zwischen Microsoft 365 Business Premium und Microsoft 365 Enterprise

Diese Tabelle zeigt die Unterschiede zwischen Microsoft 365 Business Premium und Microsoft 365 E3.

| Feature    | Support in Microsoft 365 Business Premium    | Support in Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **Lokal**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| Office Apps*    | [Microsoft 365 Apps for Business](#office-365-business)    | Microsoft 365 Apps for Enterprise | 
| **Cloud-Produktivitäts-Apps**        | | | 
| Exchange Online und Outlook    | Speichergrenzwert von 50 GB pro Postfach und unbegrenzte Exchange Online Archivierung    | Speichergrenzwert von 100 GB pro Postfach und unbegrenzte Exchange Online Archivierung | 
| Teams    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | Speichergrenzwert von 1 TB pro Benutzer    | Unbegrenzt | 
| Yammer, SharePoint Online, Planner, Stream    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| **Bedrohungsschutz**        | | | 
| Funktionen zur Reduzierung der Angriffsfläche    | [Siehe diese Liste](#threat-protection) | Enterprise verwaltung der hardwarebasierten Isolation für Microsoft Edge | 
| Microsoft Defender für Office 365 Plan 1 | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | Nicht enthalten, kann aber hinzugefügt werden | 
| **Identitätsverwaltung**        | | | 
| Self-Service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities|     ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| Cloud App Discovery, Azure AD Verbinden Health    |     | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Office 365 apps Single Sign-On (SSO): 10 Apps pro Benutzer (Gallery SaaS apps such as Salesforce)* | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: kein Grenzwert (lokale Apps über Azure AD-Anwendungsproxy und Nicht-Katalog-Apps mit Self-Service App-Integrationsvorlagen)    |     | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| **Verwaltung von Geräten und Apps**        | | | 
| Microsoft Intune, Windows Autopilot|     ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
|Virtual Desktop Access (VDA)    |  |     ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
|Windows Virtual Desktop (WVD)    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png) |     ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
|Aktivierung gemeinsam genutzter Computer (Shared Computer Activation, SCA)    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png) |     ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| Microsoft Desktop Optimization Package    | |     ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| **Schutz von Daten**        | | | 
| Office 365 Verhinderung von Datenverlust, Azure Information Protection Plan 1    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| Window Information Protection für Endpunkt-DLP    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| **Clientzugriffslizenz (CAL-Rechte)**    | | |     
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| **Compliance**        | | | 
| Unbegrenzte E-Mail-Archivierung    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| Compliance-Manager    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| eDiscovery    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| In-Place Hold und Litigation Hold    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
| Aufbewahrungstags und Aufbewahrungsrichtlinien für die Messaging-Datensatzverwaltung    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Im Lieferumfang Microsoft 365 E3](../media/check-mark.png) | 
||||

\* Benutzer, denen Zugriff auf SaaS-Apps zugewiesen wurde, können SSO-Zugriff auf bis zu 10 Apps erhalten. Administratoren können SSO konfigurieren und den Benutzerzugriff auf verschiedene SaaS-Apps ändern, der SSO-Zugriff ist jedoch nur für 10 Apps pro Benutzer gleichzeitig zulässig. Alle Office 365 werden als einzelne App gezählt.

## <a name="migration"></a>Migration

Um zu migrieren, arbeiten Sie mit Ihrem Partner zusammen, um Ihr Microsoft 365 Business Premium und Lizenzen in ein geeignetes Microsoft 365 E3 mit seinen Lizenzen zu verschieben.

In den folgenden Abschnitten wird beschrieben, welche Änderungen Sie gegebenenfalls vornehmen müssen und was Sie nach der Migration tun können.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 Konfiguration und Daten des Abonnements

Sie müssen vor der Migration keine Änderungen an Ihrem aktuellen Abonnement oder Ihren Daten vornehmen. Dazu gehören:

- Abonnementkonfiguration, z. B. DNS-Domänennamen.
- Benutzer- und Gruppenkonten und Authentifizierungseinstellungen, z. B. mehrstufige Authentifizierung oder Richtlinien für bedingten Zugriff.
- Produktivitätsdienstkonfigurationen und ihre Daten, z. B. Teams, Exchange Online Postfächer, SharePoint Onlinewebsites, OneDrive for Business Ordner und OneNote Notizbücher.

Ihre Benutzer können jetzt unbegrenzten Speicherplatz in den Exchange Online und ordnern OneDrive for Business nutzen.

Sie können mit der Verwendung von Cloud App Discovery, Azure AD Verbinden Health und SSO für mehr als 10 Apps beginnen.

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Bedrohungsschutz

Windows 10 Business umfasst die folgenden Schutzbestimmungen:

- Erzwingung der Integrität des Startvorgangs des Betriebssystems
- Erzwingung der Integrität vertraulicher Betriebskomponenten
- Erweiterte Sicherheitslücken und Zero-Day-Exploit-Gegenmaßnahmen
- Reputationsbasierter Netzwerkschutz für Microsoft Edge, Internet Explorer und Chrome
- Hostbasierte Firewall
- Ransomware-Gegenmaßnahmen
- Hardwarebasierte Isolation für Microsoft Edge
- Anwendungssteuerung, die von der intelligenten Sicherheitssteuerung Graph
- Gerätesteuerung (USB)
- Netzwerkschutz für webbasierte Bedrohungen
- Regeln zur Verhinderung von Hostangriffen

Windows 10 Enterprise E3 umfasst auch die Unternehmensverwaltung der hardwarebasierten Isolation für Microsoft Edge.

>[!Note]
>Benutzer, die zu Microsoft 365 E3 migriert wurden, benötigen jeweils eine Microsoft Defender for Office 365 für den fortgesetzten Bedrohungsschutz. Achten Sie darauf, zusätzliche Defender für Office 365 zu erwerben, damit alle Benutzer im Bereich Ihres Defender for Office 365 lizenziert sind. 
>

### <a name="device-management-with-intune"></a>Geräteverwaltung mit Intune

Sie müssen vor der Migration keine Änderungen an Ihrer aktuellen Intune-Konfiguration vornehmen, die registrierte Geräte sowie Geräte- und App-Einstellungen umfasst.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium enthält Windows 10 Business, die Sie mit Windows AutoPilot installieren können. Wenn Sie zu Microsoft 365 E3 migrieren, enthält jede Benutzerlizenz Windows 10 Enterprise E3, die Sie auch mit Windows Autopilot installieren können.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps for Business

Ihr Microsoft 365 Apps for Business, der auf Ihren Geräten installiert ist, beginnt automatisch mit der Verwendung der Features Microsoft 365 Apps for Enterprise. Nach der Migration können Sie nun verwenden:

 - Unterstützung der Gruppenrichtlinie
 - Tabellenkalkulation vergleichen und abfragen
 - Business intelligence

