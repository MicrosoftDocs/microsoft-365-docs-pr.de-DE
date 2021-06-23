---
title: Microsoft 365-Sicherheits-Roadmap – Wichtigste Prioritäten
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
description: Die wichtigsten Empfehlungen des Cybersicherheitsteams von Microsoft für die Implementierung von Sicherheitsfunktionen zum Schutz Ihrer Microsoft 365 Umgebung.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 05ea4103abecb10d4eedddf8d5043e339b58804c
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083152"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Sicherheits-Roadmap – Die wichtigsten Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dieser Artikel enthält die wichtigsten Empfehlungen des Microsoft-Cybersicherheitsteams für die Implementierung von Sicherheitsfunktionen zum Schutz Ihrer Microsoft 365 Umgebung. Dieser Artikel basiert auf einer Microsoft Ignite-Sitzung – [Sichere Microsoft 365 wie ein Cybersicherheitsprofi: Die wichtigsten Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus.](https://www.youtube.com/watch?v=luignzNyR-o) Diese Sitzung wurde von Mark Simos und Matt Kemelhar, Enterprise Cybersecurity Architects, entwickelt und präsentiert.

Inhalt dieses Artikels:

- [Roadmap-Ergebnisse](security-roadmap.md#Roadmap)
- [30 Tage – leistungsstarke Schnellstarts](security-roadmap.md#Thirdaydays)
- [90 Tage – erweiterte Schutzmaßnahmen](security-roadmap.md#Ninetydays)
- [Über etwas hinaus](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Roadmap-Ergebnisse
<a name="Roadmap"> </a>

Diese Roadmap-Empfehlungen werden in drei Phasen in einer logischen Reihenfolge mit den folgenden Zielen unterteilt.

****

|Zeitrahmen|Ergebnisse|
|---|---|
|30 Tage|Schnelle Konfiguration: <ul><li>Grundlegende Administratorschutzmechanismen.</li><li>Protokollierung und Analyse.</li><li>Grundlegende Identitätsschutzmechanismen.</li></ul> <p> Mandantenkonfiguration. <p> Bereiten Sie Projektbeteiligten vor.|
|90 Tage|Erweiterte Schutzmaßnahmen: <ul><li>Administratorkonten.</li><li>Daten und Benutzerkonten.</li></ul> <p> Sichtbarkeit der Compliance-, Bedrohungs- und Benutzeranforderungen. <p> Anpassen und Implementieren von Standardrichtlinien und -schutzmaßnahmen.|
|Über etwas hinaus|Anpassen und Verfeinern wichtiger Richtlinien und Steuerelemente. <p> Erweitert den Schutz auf lokale Abhängigkeiten. <p> Integration in Geschäfts- und Sicherheitsprozesse (Recht, Insider-Bedrohung usw.).|
|

## <a name="30-days--powerful-quick-wins"></a>30 Tage – leistungsstarke Schnellstarts
<a name="Thirdaydays"> </a>

Die folgenden Maßnahmen können schnell umgesetzt werden und führen lediglich zu geringen Beeinträchtigungen für die Benutzer.

****

|Bereich|Aufgaben|
|---|---|
|Sicherheitsverwaltung|<ul><li>Überprüfen Sie die Sicherheitsbewertung, und notieren Sie sich Ihre aktuelle Bewertung ( <https://securescore.office.com> ).</li><li>Aktivieren Sie die Überwachungsprotokollierung für Office 365. Siehe ["Durchsuchen des Überwachungsprotokolls".](../../compliance/search-the-audit-log-in-security-and-compliance.md)</li><li>[Konfigurieren sie Microsoft 365 für erhöhte Sicherheit.](tenant-wide-setup-for-increased-security.md)</li><li>Überprüfen Sie regelmäßig Dashboards und Berichte im Microsoft 365 Defender-Portal und Cloud App Security.</li></ul>|
|Bedrohungsschutz|[Verbinden Microsoft 365 Microsoft Cloud App Security,](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) um die Überwachung mithilfe der standardmäßigen Bedrohungserkennungsrichtlinien für anomales Verhalten zu starten. Es dauert sieben Tage, bis eine Basislinie für die Anomalieerkennung erstellt wird. <p>  Implementieren des Schutzes für Administratorkonten:<ul><li>Verwenden Sie dedizierte Administratorkonten für Administratoraktivitäten.</li><li>Erzwingen der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) für Administratorkonten.</li><li>Verwenden Sie ein [hochsicheres Windows 10 Gerät](/windows-hardware/design/device-experiences/oem-highly-secure) für Administratoraktivitäten.</li></ul>|
|Identitäts- und Zugriffsverwaltung|<ul><li>[Aktivieren Sie Azure Active Directory Identity Protection.](/azure/active-directory/active-directory-identityprotection-enable)</li><li>Erzwingen Sie für Verbundidentitätsumgebungen die Kontosicherheit (Kennwortlänge, Alter, Komplexität usw.).</li></ul>|
|Schutz von Daten|Überprüfen Sie Beispielempfehlungen für den Informationsschutz. Der Informationsschutz erfordert eine Organisationsübergreifende Koordination. Finden Sie den Einstieg mit den folgenden Ressourcen:<ul><li>[Schutz von Informationen in Office 365 für die DSGVO](/compliance/regulatory/gdpr)</li><li>[Konfigurieren Teams mit drei Schutzebenen](../../solutions/configure-teams-three-tiers-protection.md) (einschließlich Freigabe, Klassifizierung, Verhinderung von Datenverlust und Azure Information Protection)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 Tage – erweiterte Schutzmaßnahmen
<a name="Ninetydays"> </a>

Die folgenden Maßnahmen erfordern etwas mehr Zeit für Planung und Implementierung, stärken die Sicherheit Ihres Unternehmens jedoch erheblich.

****

|Bereich|Aufgabe|
|---|---|
|Sicherheitsverwaltung|<ul><li>Überprüfen Sie die Sicherheitsbewertung auf empfohlene Aktionen für Ihre Umgebung ( <https://securescore.office.com> ).</li><li>Überprüfen Sie regelmäßig Dashboards und Berichte im Microsoft 365 Defender Portal, Cloud App Security und SIEM-Tools.</li><li>Suchen und implementieren Sie Softwareupdates.</li><li>Durchführen von Angriffssimulationen für Spear-Phishing-, Kennwort-Spray- und Brute-Force-Kennwortangriffe mithilfe von [Angriffssimulationsschulungen](attack-simulation-training.md) (enthalten in [Office 365 Threat Intelligence).](office-365-ti.md)</li><li>Suchen Sie nach Freigaberisiken, indem Sie die integrierten Berichte in Cloud App Security überprüfen (auf der Registerkarte "Untersuchen").</li><li>Überprüfen Sie [den Compliance-Manager,](../../compliance/compliance-manager.md) um den Status von Vorschriften zu überprüfen, die für Ihre Organisation gelten (z. B. DSGVO, NIST 800-171).</li></ul>|
|Bedrohungsschutz|Implementieren sie erweiterte Schutzmaßnahmen für Administratorkonten: <ul><li>Konfigurieren Sie Arbeitsstationen mit [privilegiertem Zugriff (PaWs)](/security/compass/privileged-access-devices) für Administratoraktivitäten.</li><li>Konfigurieren Sie [Azure AD Privileged Identity Management.](/azure/active-directory/active-directory-privileged-identity-management-configure)</li><li>Konfigurieren Sie ein SIEM-Tool (Security Information and Event Management), um Protokollierungsdaten von Office 365, Cloud App Security und anderen Diensten, einschließlich AD FS, zu sammeln. Das Überwachungsprotokoll speichert Daten nur 90 Tage lang. Wenn Sie diese Daten im SIEM-Tool erfassen, können Sie Daten für einen längeren Zeitraum speichern.</li></ul>|
|Identitäts- und Zugriffsverwaltung|<ul><li>Aktivieren und Erzwingen der MFA für alle Benutzer.</li><li>Implementieren sie eine Reihe von [bedingten Zugriff und zugehörigen Richtlinien.](microsoft-365-policies-configurations.md)</li></ul>|
|Schutz von Daten| Anpassen und Implementieren von Informationsschutzrichtlinien. Zu diesen Ressourcen gehören Beispiele: <ul><li>[Schutz von Informationen in Office 365 für die DSGVO](/compliance/regulatory/gdpr)</li><li>[Konfigurieren von Microsoft Teams mit drei Schutzebenen](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Verwenden Sie Richtlinien zur Verhinderung von Datenverlust und Überwachungstools in Microsoft 365 für Daten, die in Microsoft 365 gespeichert sind (anstelle von Cloud App Security). <p> Verwenden Sie Cloud App Security mit Microsoft 365 für erweiterte Benachrichtigungsfunktionen (außer der Verhinderung von Datenverlust).|
|

## <a name="beyond"></a>Über etwas hinaus
<a name="Beyond"> </a>

Dies sind wichtige Sicherheitsmaßnahmen, die auf früheren Arbeiten aufbauen.

****

|Bereich|Aufgabe|
|---|---|
|Sicherheitsverwaltung|<ul><li>Setzen Sie die Planung der nächsten Aktionen mithilfe der Sicherheitsbewertung ( <https://securescore.office.com> ) fort.</li><li>Überprüfen Sie regelmäßig Dashboards und Berichte im Microsoft 365 Defender Portal, Cloud App Security und SIEM-Tools.</li><li>Suchen Und implementieren Sie weiterhin Softwareupdates.</li><li>Integrieren Sie eDiscovery in Ihre Prozesse zur rechtlichen und Bedrohungsantwort.</li></ul>|
|Bedrohungsschutz|<ul><li>Implementieren von [Secure Privileged Access](/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) für lokale Identitätskomponenten (AD, AD FS).</li><li>Verwenden Sie Cloud App Security, um Insider-Bedrohungen zu überwachen.</li><li>Entdecken Sie die SaaS-Verwendung von Schatten-IT mithilfe von Cloud App Security.</li></ul>|
|Identitäts- und Zugriffsverwaltung|<ul><li>Verfeinern von Richtlinien und betrieblichen Prozessen.</li><li>Verwenden Sie Azure AD Identity Protection, um Insider-Bedrohungen zu identifizieren.</li></ul>|
|Schutz von Daten|Verfeinern von Informationsschutzrichtlinien: <ul><li>Microsoft 365 und Office 365 Vertraulichkeitsbezeichnungen und Verhinderung von Datenverlust (Data Loss Prevention, DLP) oder Azure Information Protection.</li><li>Cloud App Security Richtlinien und Warnungen.</li></ul>|
|

Siehe auch: So können Sie [schnelle Cyberangriffe wie Petya und WannaCrypt abschwächen.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)
