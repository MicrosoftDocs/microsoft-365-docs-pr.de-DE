---
title: Microsoft 365-Sicherheits-Roadmap – Die wichtigsten Prioritäten
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
description: Die empfehlungen des Microsoft Cybersecurity Teams für die Implementierung von Sicherheitsfunktionen zum Schutz Ihrer Microsoft 365-Umgebung.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a7d376eb7266975dc7582b83bfd4fa5e930ccea4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288169"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Sicherheitsplan – Die wichtigsten Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dieser Artikel enthält die besten Empfehlungen des Microsoft-Cybersicherheitsteams für die Implementierung von Sicherheitsfunktionen zum Schutz Ihrer Microsoft 365-Umgebung. Dieser Artikel wurde von einer Microsoft -Ignite-Sitzung angepasst – Sichern von Microsoft 365 wie ein Cybersicherheits-Pro: Die wichtigsten Prioritäten für die ersten [30 Tage, 90](https://www.youtube.com/watch?v=luignzNyR-o)Tage und darüber hinaus. Diese Sitzung wurde von Mark Simos und Matt Kemelhar, Enterprise Cybersecurity Architects, entwickelt und präsentiert.

Inhalt dieses Artikels:

- [Ergebnisse der Roadmap](security-roadmap.md#Roadmap)
- [30 Tage – leistungsstarke Schnelleingewinne](security-roadmap.md#Thirdaydays)
- [90 Tage – erweiterter Schutz](security-roadmap.md#Ninetydays)
- [Beyond](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Ergebnisse der Roadmap
<a name="Roadmap"> </a>

Diese Roadmapempfehlungen sind in drei Phasen in logischer Reihenfolge mit den folgenden Zielen verteilt.

****

|Zeitrahmen|Ergebnisse|
|---|---|
|30 Tage|Schnelle Konfiguration: <ul><li>Grundlegende Administratorschutzfunktionen.</li><li>Protokollierung und Analyse.</li><li>Grundlegende Identitätsschutzfunktionen.</li></ul> <p> Mandantenkonfiguration. <p> Bereiten Sie die Beteiligten vor.|
|90 Tage|Erweiterte Schutzmaßnahmen: <ul><li>Administratorkonten.</li><li>Daten und Benutzerkonten.</li></ul> <p> Einblicke in Compliance, Bedrohungen und Benutzeranforderungen. <p> Anpassen und Implementieren von Standardrichtlinien und -schutzmaßnahmen.|
|Beyond|Passen Sie wichtige Richtlinien und Steuerelemente an, und verfeinern Sie diese. <p> Erweitern sie den Schutz auf lokale Abhängigkeiten. <p> Integration in Geschäfts- und Sicherheitsprozesse (rechts, Insiderbedrohung usw.).|
|

## <a name="30-days--powerful-quick-wins"></a>30 Tage – leistungsstarke Schnelleingewinne
<a name="Thirdaydays"> </a>

Die folgenden Maßnahmen können schnell umgesetzt werden und führen lediglich zu geringen Beeinträchtigungen für die Benutzer.

****

|Bereich|Aufgaben|
|---|---|
|Sicherheitsverwaltung|<ul><li>Überprüfen Sie die Sicherheitsnote, und notieren Sie sich Ihre aktuelle Bewertung ( <https://securescore.office.com> ).</li><li>Aktivieren Sie die Überwachungsprotokollierung für Office 365. Siehe ["Durchsuchen des Überwachungsprotokolls".](../../compliance/search-the-audit-log-in-security-and-compliance.md)</li><li>[Konfigurieren Sie Microsoft 365 für erhöhte Sicherheit.](tenant-wide-setup-for-increased-security.md)</li><li>Überprüfen Sie regelmäßig Dashboards und Berichte im Microsoft 365 Security Center und in Cloud App Security.</li></ul>|
|Bedrohungsschutz|[Verbinden Sie Microsoft 365 mit Microsoft Cloud App Security,](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) um die Überwachung mithilfe der standardmäßigen Richtlinien zur Bedrohungserkennung auf anomales Verhalten zu starten. Es dauert sieben Tage, um einen Basisplan für die Anomalieerkennung zu erstellen. <p>  Implementieren Des Schutzes für Administratorkonten:<ul><li>Verwenden Sie dedizierte Administratorkonten für Administratoraktivitäten.</li><li>Erzwingen der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) für Administratorkonten.</li><li>Verwenden Sie [ein äußerst sicheres Windows 10-Gerät für](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) Administratoraktivitäten.</li></ul>|
|Identitäts- und Zugriffsverwaltung|<ul><li>[Aktivieren Sie Azure Active Directory Identity Protection.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)</li><li>Erzwingen Sie für Verbundidentitätsumgebungen die Kontosicherheit (Kennwortlänge, Alter, Komplexität usw.).</li></ul>|
|Schutz von Daten|Sehen Sie sich Beispielempfehlungen zum Informationsschutz an. Der Informationsschutz erfordert eine Organisationskoordinierung. Finden Sie den Einstieg mit den folgenden Ressourcen:<ul><li>[Schutz von Informationen in Office 365 für die DSGVO](https://aka.ms/o365gdpr)</li><li>[Konfigurieren von Teams mit drei Schutzebenen](../../solutions/configure-teams-three-tiers-protection.md) (einschließlich Freigabe, Klassifizierung, Verhinderung von Datenverlust und Azure Information Protection)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 Tage – erweiterter Schutz
<a name="Ninetydays"> </a>

Die folgenden Maßnahmen erfordern etwas mehr Zeit für Planung und Implementierung, stärken die Sicherheit Ihres Unternehmens jedoch erheblich.

****

|Bereich|Aufgabe|
|---|---|
|Sicherheitsverwaltung|<ul><li>Überprüfen Sie die Sicherheitsnote auf empfohlene Aktionen für Ihre Umgebung ( <https://securescore.office.com> ).</li><li>Überprüfen Sie weiterhin regelmäßig Dashboards und Berichte im Microsoft 365 Security Center, in Cloud App Security und im SIEM-Tools.</li><li>Suchen sie nach Softwareupdates, und implementieren Sie sie.</li><li>Durchführen von Angriffssimulationen für Phishing, Kennwort-Spray und Brute-Force-Kennwortangriffe mithilfe des Angriffssimulators (im Lieferumfang von [Office 365 Threat Intelligence enthalten).](office-365-ti.md) [](attack-simulator.md)</li><li>Suchen Sie nach Freigaberisiken, indem Sie die integrierten Berichte in Cloud App Security (auf der Registerkarte "Untersuchen" ) überprüfen.</li><li>Überprüfen [Sie den Compliance-Manager,](../../compliance/compliance-manager.md) um den Status von Vorschriften zu überprüfen, die für Ihre Organisation gelten (z. B. DSGVO, NIST 800-171).</li></ul>|
|Bedrohungsschutz|Implementieren Sie erweiterten Schutz für Administratorkonten: <ul><li>Konfigurieren [Sie Privileged Access Workstations](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) für Administratoraktivitäten.</li><li>Konfigurieren [Sie Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Konfigurieren Sie ein Tool zur Sicherheitsinformations- und Ereignisverwaltung (SIEM), um Protokollierungsdaten von Office 365, Cloud App Security und anderen Diensten, einschließlich AD FS, zu erfassen. Im Überwachungsprotokoll werden Daten nur für 90 Tage gespeichert. Wenn Sie diese Daten im SIEM-Tool erfassen, können Sie Daten über einen längeren Zeitraum speichern.</li></ul>|
|Identitäts- und Zugriffsverwaltung|<ul><li>Aktivieren und erzwingen Sie MFA für alle Benutzer.</li><li>Implementieren Sie eine Reihe von [bedingten Zugriff und zugehörige Richtlinien.](microsoft-365-policies-configurations.md)</li></ul>|
|Schutz von Daten| Anpassung und Implementierung von Informationsschutzrichtlinien. Diese Ressourcen umfassen Beispiele: <ul><li>[Schutz von Informationen in Office 365 für die DSGVO](https://aka.ms/o365gdpr)</li><li>[Konfigurieren von Teams mit drei Schutzebenen](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Verwenden Sie Richtlinien zur Verhinderung von Datenverlust und Überwachungstools in Microsoft 365 für in Microsoft 365 gespeicherte Daten (anstelle von Cloud App Security). <p> Verwenden Sie Cloud App Security mit Microsoft 365 für erweiterte Benachrichtigungsfeatures (andere als Verhinderung von Datenverlust).|
|

## <a name="beyond"></a>Beyond
<a name="Beyond"> </a>

Dies sind wichtige Sicherheitsmaßnahmen, die auf vorherigen Arbeiten aufbauen.

****

|Bereich|Aufgabe|
|---|---|
|Sicherheitsverwaltung|<ul><li>Fahren Sie mit der Planung der nächsten Aktionen mithilfe von Secure Score ( ) fort. <https://securescore.office.com></li><li>Überprüfen Sie weiterhin regelmäßig Dashboards und Berichte im Microsoft 365 Security Center, in Cloud App Security und im SIEM-Tools.</li><li>Suchen und implementieren Sie weiterhin Softwareupdates.</li><li>Integrieren Sie eDiscovery in Ihre Prozesse zur Rechtlichen und Bedrohungsreaktion.</li></ul>|
|Bedrohungsschutz|<ul><li>Implementieren [Sie Secure Privileged Access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) für identitätskomponenten lokal (AD, AD FS).</li><li>Verwenden Sie Cloud App Security, um auf Insiderbedrohungen zu überwachen.</li><li>Entdecken Sie die Schatten-IT-SaaS-Nutzung mithilfe von Cloud App Security.</li></ul>|
|Identitäts- und Zugriffsverwaltung|<ul><li>Verfeinern von Richtlinien und Betriebsprozessen.</li><li>Verwenden Sie Azure AD Identity Protection, um Insiderbedrohungen zu identifizieren.</li></ul>|
|Schutz von Daten|Einschränkung von Informationsschutzrichtlinien: <ul><li>Microsoft 365- und Office 365-Vertraulichkeitsbezeichnungen und Verhinderung von Datenverlust (Data Loss Prevention, DLP) oder Azure Information Protection.</li><li>Cloud App Security–Richtlinien und -Warnungen.</li></ul>|
|

Weitere Informationen finden Sie [auch: So verringern Sie schnelle Cyberangriffe wie Petya und WannaCrypt.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)
