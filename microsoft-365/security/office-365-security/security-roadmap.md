---
title: Microsoft 365-Sicherheits-Roadmap – Hauptprioritäten
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Die wichtigsten Empfehlungen aus dem Cyber-Team von Microsoft für die Implementierung von Sicherheitsfunktionen zum Schutz Ihrer Microsoft 365-Umgebung. '
ms.openlocfilehash: 452ce2a303f02cadfcdcbe12310f2538d33a24e7
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615804"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Security Roadmap – die wichtigsten Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dieser Artikel enthält die wichtigsten Empfehlungen des Cyber-Teams von Microsoft für die Implementierung von Sicherheitsfunktionen zum Schutz Ihrer Microsoft 365-Umgebung. Dieser Artikel wird von einer Microsoft Ignite-Sitzung angepasst – [Sichern Sie Microsoft 365 wie ein Cyber pro: die wichtigsten Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](https://www.youtube.com/watch?v=luignzNyR-o). Diese Sitzung wurde von Mark Simos und Matt Kemelhar, Enterprise Cyber Architects, entwickelt und präsentiert.

Inhalt dieses Artikels:

- [Roadmap-Ergebnisse](security-roadmap.md#Roadmap)
- [30 Tage – leistungsstarke schnell Gewinne](security-roadmap.md#Thirdaydays)
- [90 Tage – erweiterter Schutz](security-roadmap.md#Ninetydays)
- [Über](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Roadmap-Ergebnisse
<a name="Roadmap"> </a>

Diese Empfehlungen für die Roadmap werden in einer logischen Reihenfolge in drei Phasen mit den folgenden Zielen bereitgestellt.

****

|Zeitrahmen|Ergebnisse|
|---|---|
|30 Tage|Schnelle Konfiguration: <ul><li>Grundlegende Administrator Schutz.</li><li>Protokollierung und Analyse.</li><li>Grundlegende Identitätsschutz.</li></ul> <p> Mandanten Konfiguration. <p> Vorbereiten von Beteiligten.|
|90 Tage|Erweiterte Schutzfunktionen: <ul><li>Administratorkonten.</li><li>Daten-und Benutzerkonten.</li></ul> <p> Sichtbarkeit in Compliance, Bedrohung und Benutzeranforderungen. <p> Anpassen und Implementieren von Standardrichtlinien und-Schutz.|
|Über|Anpassen und verfeinern wichtiger Richtlinien und Steuerelemente <p> Erweitern Sie den Schutz auf lokale Abhängigkeiten. <p> Integration in Geschäfts-und Sicherheitsprozesse (Legal, Insider Threat, etc.).|
|

## <a name="30-days--powerful-quick-wins"></a>30 Tage – leistungsstarke schnell Gewinne
<a name="Thirdaydays"> </a>

Die folgenden Maßnahmen können schnell umgesetzt werden und führen lediglich zu geringen Beeinträchtigungen für die Benutzer.

****

|Bereich|Aufgaben|
|---|---|
|Sicherheitsverwaltung|<ul><li>Überprüfen Sie Secure Score, und notieren Sie sich das aktuelle Ergebnis ( <https://securescore.office.com> ).</li><li>Aktivieren Sie die Überwachungsprotokollierung für Office 365. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls](../../compliance/search-the-audit-log-in-security-and-compliance.md).</li><li>[Konfigurieren Sie Microsoft 365 für mehr Sicherheit](tenant-wide-setup-for-increased-security.md).</li><li>Überprüfen Sie Dashboards und Berichte regelmäßig im Microsoft 365 Security Center und in der Cloud-App-Sicherheit.</li></ul>|
|Bedrohungsschutz|[Verbinden Sie Microsoft 365 mit der Microsoft Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) , um die Überwachung mithilfe der standardmäßigen Bedrohungs Erkennungsrichtlinien für anomale Verhaltensweisen zu starten. Es dauert sieben Tage, um einen Basisplan für die Anomalie-Erkennung zu erstellen. <p>  Implementieren des Schutzes für Administratorkonten:<ul><li>Verwenden Sie dedizierte Administratorkonten für Administratoraktivitäten.</li><li>Erzwingen Sie die mehrstufige Authentifizierung (MFA) für Administratorkonten.</li><li>Verwenden Sie ein [hochsicheres Windows 10-Gerät](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) für Administratoraktivitäten.</li></ul>|
|Identitäts- und Zugriffsverwaltung|<ul><li>[Aktivieren Sie Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</li><li>Erzwingen Sie für Verbund Identitäts Umgebungen die Kontosicherheit (Kennwortlänge, Alter, Komplexität usw.).</li></ul>|
|Information Protection|Lesen Sie die Empfehlungen zum Beispiel für Informationsschutz. Informationsschutz erfordert eine Koordination in Ihrer Organisation. Finden Sie den Einstieg mit den folgenden Ressourcen:<ul><li>[Schutz von Informationen in Office 365 für die DSGVO](https://aka.ms/o365gdpr)</li><li>[Konfigurieren von Teams mit drei Schutzebenen](../../solutions/configure-teams-three-tiers-protection.md) (einschließlich Freigabe, Klassifizierung, Verhinderung von Datenverlust und Azure Information Protection)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 Tage – erweiterter Schutz
<a name="Ninetydays"> </a>

Die folgenden Maßnahmen erfordern etwas mehr Zeit für Planung und Implementierung, stärken die Sicherheit Ihres Unternehmens jedoch erheblich.

****

|Bereich|Aufgabe|
|---|---|
|Sicherheitsverwaltung|<ul><li>Überprüfen Sie die sichere Bewertung auf Empfohlene Aktionen für Ihre Umgebung ( <https://securescore.office.com> ).</li><li>Überprüfen Sie weiterhin regelmäßig Dashboards und Berichte im Microsoft 365 Security Center, in der Cloud-App-Sicherheit und in Siem-Tools.</li><li>Suchen und Implementieren von Softwareupdates</li><li>Durchführen von Angriffssimulationen für Spear-Phishing-, Password-Spray-und Brute-Force-Kennwortangriffe mithilfe von [Attack Simulator](attack-simulator.md) (im Lieferumfang von [Office 365 Threat Intelligence](office-365-ti.md)enthalten).</li><li>Suchen Sie nach Freigabe Risiko, indem Sie die integrierten Berichte in der Cloud-App-Sicherheit (auf der Registerkarte untersuchen) überprüfen.</li><li>Überprüfen Sie [Compliance-Manager](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager) , um den Status für Vorschriften zu prüfen, die für Ihre Organisation gelten (beispielsweise dsgvo, NIST 800-171).</li></ul>|
|Bedrohungsschutz|Implementieren Sie erweiterte Schutzbestimmungen für Administratorkonten: <ul><li>Konfigurieren von "PAWs" für Administratoraktivitäten für [privilegierte Zugriffs Arbeitsplätze](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) .</li><li>Konfigurieren Sie [Azure AD privilegierte Identitätsverwaltung](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Konfigurieren Sie ein Siem-Tool (Security Information and Event Management) zum Erfassen von Protokollierungsdaten aus Office 365, Cloud-App-Sicherheit und anderen Diensten, einschließlich AD FS. Im Überwachungsprotokoll werden Daten für nur 90 Tage gespeichert. Durch das Erfassen dieser Daten im Siem-Tool können Sie Daten für einen längeren Zeitraum speichern.</li></ul>|
|Identitäts- und Zugriffsverwaltung|<ul><li>Aktivieren und Erzwingen von MFA für alle Benutzer.</li><li>Implementieren Sie eine Reihe von [bedingten Zugriff und zugehöriger Richtlinien](microsoft-365-policies-configurations.md).</li></ul>|
|Information Protection| Anpassen und Implementieren von Richtlinien für den Informationsschutz Diese Ressourcen umfassen Beispiele: <ul><li>[Schutz von Informationen in Office 365 für die DSGVO](https://aka.ms/o365gdpr)</li><li>[Konfigurieren von Teams mit drei Schutzebenen](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Verwenden Sie Richtlinien zur Verhinderung von Datenverlust und Überwachungstools in Microsoft 365 für Daten, die in Microsoft 365 (anstelle von Cloud-App-Sicherheit) gespeichert sind. <p> Verwenden Sie die Cloud-App-Sicherheit mit Microsoft 365 für erweiterte Warnungsfunktionen (außer Verhinderung von Datenverlust).|
|

## <a name="beyond"></a>Über
<a name="Beyond"> </a>

Dies sind wichtige Sicherheitsmaßnahmen, die auf früheren Arbeiten aufbauen.

****

|Bereich|Aufgabe|
|---|---|
|Sicherheitsverwaltung|<ul><li>Fahren Sie mit der Planung der nächsten Aktionen mit Secure Score ( <https://securescore.office.com> ) fort.</li><li>Überprüfen Sie weiterhin regelmäßig Dashboards und Berichte im Microsoft 365 Security Center, in der Cloud-App-Sicherheit und in Siem-Tools.</li><li>Suchen und implementieren Sie weiterhin Softwareupdates.</li><li>Integrieren Sie eDiscovery in ihre rechtlichen und Bedrohungs Reaktionsprozesse.</li></ul>|
|Bedrohungsschutz|<ul><li>Implementieren Sie den [Secure privileged Access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (Spa) für Identitäts Komponenten lokal (AD, AD FS).</li><li>Verwenden Sie die Cloud-App-Sicherheit, um Insiderbedrohungen zu überwachen.</li><li>Entdecken Sie Shadow IT Saas-Nutzung mithilfe der Cloud-App-Sicherheit.</li></ul>|
|Identitäts- und Zugriffsverwaltung|<ul><li>Optimieren von Richtlinien und Betriebsprozessen</li><li>Verwenden Sie Azure AD Identitätsschutz, um Insiderbedrohungen zu identifizieren.</li></ul>|
|Information Protection|Verfeinern von Richtlinien für den Informationsschutz: <ul><li>Microsoft 365 und Office 365 Vertraulichkeits Bezeichnungen und Datenverlust Verhinderung (DLP) oder Azure Information Protection.</li><li>Cloud-App-Sicherheitsrichtlinien und-Warnungen.</li></ul>|
|

Siehe auch: [Vorgehensweise zum minimieren schneller Cyberangriffe wie Petja und WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
