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
ms.openlocfilehash: 9bdddbbfbb20900a4645d2e17cf298ed018f4c6d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197429"
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
|30 Tage|Schnelle Konfiguration:  <br/> * Grundlegende Administrator Schutz  <br/> * Protokollierung und Analyse  <br/> * Grundlegende Identitätsschutz  <br/> Mandanten Konfiguration  <br/>  Vorbereiten von Beteiligten|
|90 Tage|Erweiterte Schutzfunktionen:  <br/> * Administratorkonten  <br/>  * Daten &amp; Benutzerkonten  <br/>  Sichtbarkeit in Compliance, Bedrohung und Benutzeranforderungen  <br/>  Anpassen und Implementieren von Standardrichtlinien und-Schutz|
|Über|Anpassen und verfeinern wichtiger Richtlinien und Steuerelemente  <br/> Erweitern von Schutzeinrichtungen zu lokalen Abhängigkeiten  <br/> Integration in Geschäfts-und Sicherheitsprozesse (rechtliche, Insider-Bedrohungen usw.)|
|

## <a name="30-days--powerful-quick-wins"></a>30 Tage – leistungsstarke schnell Gewinne
<a name="Thirdaydays"> </a>

Die folgenden Maßnahmen können schnell umgesetzt werden und führen lediglich zu geringen Beeinträchtigungen für die Benutzer.

****

|Bereich|Aufgaben|
|---|---|
|Sicherheitsverwaltung|* Check Secure Score und notieren Sie sich Ihre aktuelle Punktzahl ( <https://securescore.office.com> ).  <br/>  * Aktivieren Sie die Überwachungsprotokollierung für Office 365. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls](../../compliance/search-the-audit-log-in-security-and-compliance.md).  <br/> * [Konfigurieren Sie Microsoft 365 für mehr Sicherheit](tenant-wide-setup-for-increased-security.md).  <br/>  * Regelmäßige Überprüfung von Dashboards und Berichten im Microsoft 365 Security Center und in der Cloud-App-Sicherheit.|
|Bedrohungsschutz|[Verbinden Sie Microsoft 365 mit der Microsoft Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) , um die Überwachung mithilfe der standardmäßigen Bedrohungs Erkennungsrichtlinien für anomale Verhaltensweisen zu starten. Es dauert sieben Tage, um einen Basisplan für die Anomalie-Erkennung zu erstellen.  <br><br/>  Implementieren des Schutzes für Administratorkonten:  <br/> * Verwenden Sie dedizierte Administratorkonten für Administratoraktivitäten.  <br/>  * Erzwingen Sie die mehrstufige Authentifizierung (MFA) für Administratorkonten.  <br/>  * Verwenden Sie ein [hochsicheres Windows 10-Gerät](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) für Administratoraktivitäten.|
|Identitäts- und Zugriffsverwaltung|* [Aktivieren Sie Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).  <br/> * Erzwingen Sie für Verbund Identitäts Umgebungen die Kontosicherheit (Kennwortlänge, Alter, Komplexität usw.).|
|Information Protection|Lesen Sie die Empfehlungen zum Beispiel für Informationsschutz. Informationsschutz erfordert eine Koordination in Ihrer Organisation. Finden Sie den Einstieg mit den folgenden Ressourcen:  <br/> * [Office 365 Informationsschutz für dsgvo](https://aka.ms/o365gdpr) <br/> * [Konfigurieren von Teams mit drei Schutzebenen](../../solutions/configure-teams-three-tiers-protection.md) (einschließlich Freigabe, Klassifizierung, Verhinderung von Datenverlust und Azure Information Protection)|
|

## <a name="90-days--enhanced-protections"></a>90 Tage – erweiterter Schutz
<a name="Ninetydays"> </a>

Die folgenden Maßnahmen erfordern etwas mehr Zeit für Planung und Implementierung, stärken die Sicherheit Ihres Unternehmens jedoch erheblich.

****

|Bereich|Aufgabe|
|---|---|
|Sicherheitsverwaltung|* Check Secure Score für empfohlene Aktionen für Ihre Umgebung ( [https://securescore.office.com](https://securescore.office.com) ).  <br/>  * Weiterhin regelmäßige Überprüfung von Dashboards und Berichten im Microsoft 365 Security Center, in der Cloud-App-Sicherheit und in Siem-Tools. <br/> * Suchen und Implementieren von Softwareupdates <br/> * Durchführen von Angriffssimulationen für Spear-Phishing, Kenn Wort Spray und Brute-Force-Kennwortangriffe mithilfe von [Attack Simulator](attack-simulator.md) (im Lieferumfang von [Office 365 Threat Intelligence](office-365-ti.md)enthalten).  <br/> * Suchen Sie nach Freigabe Risiko, indem Sie die integrierten Berichte in Cloud App Security (auf der Registerkarte untersuchen) überprüfen. <br/> * Überprüfen Sie den Status von [Compliance-Manager](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager) auf Vorschriften, die für Ihre Organisation gelten (beispielsweise dsgvo, NIST 800-171).|
|Bedrohungsschutz| Implementieren Sie erweiterte Schutzbestimmungen für Administratorkonten: <br/> * Konfigurieren von [rechten Zugriffs Arbeitsstationen](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) für Administratoraktivitäten. <br/> * Konfigurieren [Azure AD privilegierten Identitätsverwaltung](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure). <br/> * Konfigurieren Sie ein Siem-Tool (Security Information and Event Management) zum Erfassen von Protokollierungsdaten aus Office 365, Cloud-App-Sicherheit und anderen Diensten, einschließlich AD FS. Im Überwachungsprotokoll werden Daten für nur 90 Tage gespeichert. Durch das Erfassen dieser Daten im Siem-Tool können Sie Daten für einen längeren Zeitraum speichern.|
|Identitäts- und Zugriffsverwaltung|* Aktivieren und Erzwingen von MFA für alle Benutzer. <br/> * Implementieren Sie eine Reihe von [bedingten Zugriff und verwandte Richtlinien](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations). |
|Information Protection| Anpassen und Implementieren von Richtlinien für den Informationsschutz Diese Ressourcen umfassen Beispiele: <br/> * [Office 365 Informationsschutz für dsgvo](https://aka.ms/o365gdpr) <br/> * [Konfigurieren von Microsoft Teams mit drei Schutzebenen](../../solutions/configure-teams-three-tiers-protection.md) <br/> <br> Verwenden Sie Richtlinien zur Verhinderung von Datenverlust und Überwachungstools in Microsoft 365 für Daten, die in Microsoft 365 (anstelle von Cloud-App-Sicherheit) gespeichert sind. <br><br>Verwenden Sie die Cloud-App-Sicherheit mit Microsoft 365 für erweiterte Warnungsfunktionen (außer Verhinderung von Datenverlust).|
|

## <a name="beyond"></a>Über
<a name="Beyond"> </a>

Dies sind wichtige Sicherheitsmaßnahmen, die auf früheren Arbeiten aufbauen.

****

|Bereich|Aufgabe|
|---|---|
|Sicherheitsverwaltung|* Fahren Sie mit der Planung der nächsten Aktionen mit Secure Score ( [https://securescore.office.com](https://securescore.office.com) ) fort. <br/> * Weiterhin regelmäßige Überprüfung von Dashboards und Berichten im Microsoft 365 Security Center, in der Cloud-App-Sicherheit und in Siem-Tools. <br/> * Suchen und implementieren Sie weiterhin Softwareupdates. <br/> * Integrieren Sie eDiscovery in ihre rechtlichen und Bedrohungs Reaktionsprozesse.|
|Bedrohungsschutz|* Implementieren Sie den [Secure privileged Access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (Spa) für Identitäts Komponenten lokal (AD, AD FS). <br/> * Verwenden Sie die Cloud-App-Sicherheit, um Insiderbedrohungen zu überwachen. <br/> * Entdecken Sie Shadow IT Saas-Nutzung mithilfe der Cloud-App-Sicherheit.|
|Identitäts- und Zugriffsverwaltung|* Optimieren von Richtlinien und Betriebsprozessen <br/> * Verwenden Sie Azure AD Identitätsschutz, um Insiderbedrohungen zu identifizieren.|
|Information Protection|Verfeinern von Richtlinien für den Informationsschutz: <br/> * Microsoft 365 und Office 365 Sensitivitäts Bezeichnungen und Verhinderung von Datenverlust (DLP) oder Azure Information Protection. <br/> * Cloud-App-Sicherheitsrichtlinien und-Warnungen.|
|

Siehe auch: [Vorgehensweise zum minimieren schneller Cyberangriffe wie Petja und WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
