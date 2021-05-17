---
title: Microsoft 365 Security Roadmap – Die wichtigsten Prioritäten
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: Die besten Empfehlungen des Microsoft-Cybersicherheitsteams für die Implementierung von Sicherheitsfunktionen zum Schutz Microsoft 365 Umgebung.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd86262cd36d9482cd9a54e7fd7c336a6f0700dd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205639"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Security Roadmap – Die wichtigsten Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dieser Artikel enthält die besten Empfehlungen des Microsoft-Cybersicherheitsteams zum Implementieren von Sicherheitsfunktionen zum Schutz Microsoft 365 Umgebung. Dieser Artikel wurde von einer Microsoft Ignite-Sitzung angepasst – [Secure Microsoft 365 like a cybersecurity pro: Top priorities for the first 30 days, 90 days, and beyond](https://www.youtube.com/watch?v=luignzNyR-o). Diese Sitzung wurde von Mark Simos und Matt Kemelhar, Enterprise Cybersecurity Architects, entwickelt und präsentiert.

Inhalt dieses Artikels:

- [Roadmap-Ergebnisse](security-roadmap.md#Roadmap)
- [30 Tage – leistungsstarke schnelle Gewinne](security-roadmap.md#Thirdaydays)
- [90 Tage – erweiterte Schutzmaßnahmen](security-roadmap.md#Ninetydays)
- [Beyond](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Roadmap-Ergebnisse
<a name="Roadmap"> </a>

Diese Roadmapempfehlungen werden in drei Phasen in logischer Reihenfolge mit den folgenden Zielen verteilt.

****

|Zeitrahmen|Ergebnisse|
|---|---|
|30 Tage|Schnelle Konfiguration: <ul><li>Grundlegende Administratorschutzfunktionen.</li><li>Protokollierung und Analyse.</li><li>Grundlegende Identitätsschutzfunktionen.</li></ul> <p> Mandantenkonfiguration. <p> Bereiten Sie die Beteiligten vor.|
|90 Tage|Erweiterte Schutzmaßnahmen: <ul><li>Administratorkonten.</li><li>Daten und Benutzerkonten.</li></ul> <p> Sichtbarkeit der Compliance-, Bedrohungs- und Benutzeranforderungen. <p> Anpassen und Implementieren von Standardrichtlinien und -schutzmaßnahmen.|
|Beyond|Anpassen und Verfeinern von Schlüsselrichtlinien und -steuerelementen <p> Erweitern sie den Schutz auf lokale Abhängigkeiten. <p> Integration in Geschäfts- und Sicherheitsprozesse (rechtliche, Insiderbedrohungen usw.).|
|

## <a name="30-days--powerful-quick-wins"></a>30 Tage – leistungsstarke schnelle Gewinne
<a name="Thirdaydays"> </a>

Die folgenden Maßnahmen können schnell umgesetzt werden und führen lediglich zu geringen Beeinträchtigungen für die Benutzer.

****

|Bereich|Aufgaben|
|---|---|
|Sicherheitsverwaltung|<ul><li>Überprüfen Sie Secure Score, und notieren Sie sich Ihre aktuelle Bewertung ( <https://securescore.office.com> ).</li><li>Aktivieren der Überwachungsprotokollierung für Office 365. Weitere [Informationen finden Sie unter Durchsuchen des Überwachungsprotokolls.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</li><li>[Konfigurieren Microsoft 365 für erhöhte Sicherheit](tenant-wide-setup-for-increased-security.md).</li><li>Überprüfen Sie regelmäßig Dashboards und Berichte im Microsoft 365 Security Center und Cloud App Security.</li></ul>|
|Bedrohungsschutz|[Verbinden Microsoft 365 sie Microsoft Cloud App Security,](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) die Überwachung mithilfe der standardmäßigen Richtlinien für die Bedrohungserkennung auf anomale Verhaltensweisen zu starten. Es dauert sieben Tage, bis ein Basisplan für die Erkennung von Anomalien festgelegt ist. <p>  Implementieren des Schutzes für Administratorkonten:<ul><li>Verwenden Sie dedizierte Administratorkonten für Administratoraktivitäten.</li><li>Erzwingen der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) für Administratorkonten.</li><li>Verwenden Sie [ein hoch sicheres Windows 10 für](/windows-hardware/design/device-experiences/oem-highly-secure) Administratoraktivitäten.</li></ul>|
|Identitäts- und Zugriffsverwaltung|<ul><li>[Aktivieren Azure Active Directory Identity Protection](/azure/active-directory/active-directory-identityprotection-enable).</li><li>Erzwingen Sie für Verbundidentitätsumgebungen die Kontosicherheit (Kennwortlänge, Alter, Komplexität usw.).</li></ul>|
|Information Protection|Überprüfen Sie Beispielempfehlungen zum Informationsschutz. Der Informationsschutz erfordert eine Organisationskoordinierung. Finden Sie den Einstieg mit den folgenden Ressourcen:<ul><li>[Schutz von Informationen in Office 365 für die DSGVO](/compliance/regulatory/gdpr)</li><li>[Konfigurieren Teams drei](../../solutions/configure-teams-three-tiers-protection.md) Schutzebenen (einschließlich Freigabe, Klassifizierung, Verhinderung von Datenverlust und Azure Information Protection)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 Tage – erweiterte Schutzmaßnahmen
<a name="Ninetydays"> </a>

Die folgenden Maßnahmen erfordern etwas mehr Zeit für Planung und Implementierung, stärken die Sicherheit Ihres Unternehmens jedoch erheblich.

****

|Bereich|Aufgabe|
|---|---|
|Sicherheitsverwaltung|<ul><li>Überprüfen Sie Secure Score auf empfohlene Aktionen für Ihre Umgebung ( <https://securescore.office.com> ).</li><li>Lesen Sie weiterhin regelmäßig Dashboards und Berichte in den tools Microsoft 365 Security Center, Cloud App Security und SIEM.</li><li>Suchen und implementieren Sie Softwareupdates.</li><li>Durchführen von Angriffssimulationen für Speerphishing, Kennwort-Spray und Brute-Force-Kennwortangriffe mithilfe des Angriffssimulators (Office 365 [Threat Intelligence](office-365-ti.md)enthalten). [](attack-simulator.md)</li><li>Suchen Sie nach Freigaberisiken, indem Sie die integrierten Berichte in Cloud App Security (auf der Registerkarte Untersuchen) überprüfen.</li><li>Überprüfen [Sie den Compliance-Manager,](../../compliance/compliance-manager.md) um den Status für Vorschriften zu überprüfen, die für Ihre Organisation gelten (z. B. DSGVO, NIST 800-171).</li></ul>|
|Bedrohungsschutz|Implementieren sie erweiterte Schutzmaßnahmen für Administratorkonten: <ul><li>Konfigurieren [Sie Privileged Access Workstations](/security/compass/privileged-access-devices) (PAWs) für Administratoraktivitäten.</li><li>Konfigurieren [von Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Konfigurieren Sie ein Sicherheitsinformations- und Ereignisverwaltungstool (SIEM), um Protokollierungsdaten von Office 365, Cloud App Security und anderen Diensten, einschließlich AD FS, zu erfassen. Das Überwachungsprotokoll speichert Daten nur für 90 Tage. Wenn Sie diese Daten im SIEM-Tool erfassen, können Sie Daten für einen längeren Zeitraum speichern.</li></ul>|
|Identitäts- und Zugriffsverwaltung|<ul><li>Aktivieren und Erzwingen von MFA für alle Benutzer.</li><li>Implementieren Sie eine Reihe von [bedingten Zugriffen und zugehörigen Richtlinien.](microsoft-365-policies-configurations.md)</li></ul>|
|Information Protection| Anpassen und Implementieren von Informationsschutzrichtlinien. Diese Ressourcen enthalten Beispiele: <ul><li>[Schutz von Informationen in Office 365 für die DSGVO](/compliance/regulatory/gdpr)</li><li>[Konfigurieren von Teams mit drei Schutzebenen](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Verwenden Sie Richtlinien zur Verhinderung von Datenverlust und Überwachungstools in Microsoft 365 daten, die in Microsoft 365 gespeichert sind (anstelle Cloud App Security). <p> Verwenden Cloud App Security mit Microsoft 365 für erweiterte Benachrichtigungsfeatures (mit Anderen als Verhinderung von Datenverlust).|
|

## <a name="beyond"></a>Beyond
<a name="Beyond"> </a>

Dies sind wichtige Sicherheitsmaßnahmen, die auf vorherigen Arbeiten aufbauen.

****

|Bereich|Aufgabe|
|---|---|
|Sicherheitsverwaltung|<ul><li>Fahren Sie mit der Planung der nächsten Aktionen mit Secure Score ( <https://securescore.office.com> ) fort.</li><li>Lesen Sie weiterhin regelmäßig Dashboards und Berichte in den tools Microsoft 365 Security Center, Cloud App Security und SIEM.</li><li>Suchen und implementieren Sie weiterhin Softwareupdates.</li><li>Integrieren Sie eDiscovery in Ihre Prozesse zur Reaktion auf Rechtliche und Bedrohungen.</li></ul>|
|Bedrohungsschutz|<ul><li>Implementieren [von Secure Privileged Access](/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) für lokale Identitätskomponenten (AD, AD FS).</li><li>Verwenden Cloud App Security zum Überwachen von Insiderbedrohungen.</li><li>Ermitteln Sie die Verwendung von Shadow IT SaaS mithilfe Cloud App Security.</li></ul>|
|Identitäts- und Zugriffsverwaltung|<ul><li>Verfeinern von Richtlinien und betriebsbereiten Prozessen.</li><li>Verwenden Sie Azure AD Identity Protection, um Insiderbedrohungen zu identifizieren.</li></ul>|
|Information Protection|Einschränkung von Informationsschutzrichtlinien: <ul><li>Microsoft 365 und Office 365 Vertraulichkeitsbezeichnungen und Verhinderung von Datenverlust (Data Loss Prevention, DLP) oder Azure Information Protection.</li><li>Cloud App Security und Warnungen.</li></ul>|
|

Weitere Informationen finden Sie unter [How to mitigate rapid cyber attackcks such as Petya and WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).