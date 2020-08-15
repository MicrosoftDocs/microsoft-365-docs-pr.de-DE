---
title: Zusammenfassung von Microsoft 365 für Enterprise-Sicherheit für die Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Wie Contoso die Sicherheitsfeatures in Microsoft 365 für Unternehmen verwendet.
ms.openlocfilehash: 2244f13f8e8f56edbadd40d1e85cb309d70f7744
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686440"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Zusammenfassung von Microsoft 365 für Enterprise-Sicherheit für die Contoso Corporation

Um die Registrierung der Bereitstellung von Microsoft 365 for Enterprise durch die IT-Sicherheitsabteilung zu erhalten, wurde eine gründliche Sicherheitsüberprüfung durchgeführt. Hier finden Sie die Sicherheitsanforderungen von Contoso für die Cloud:

- Verwenden der strengsten Authentifizierungsmethoden für den Mitarbeiterzugriff auf Cloudressourcen
- Sicherstellen, dass PCs und mobile Geräte auf sichere Weise eine Verbindung zu Anwendungen herstellen und auf sie zugreifen
- PCs und E-Mails sind vor Schadsoftware geschützt
- Berechtigungen für cloudbasierte digitale Objekte definieren, wer auf was zugreifen kann und was die Benutzer tun können, und sie sind stets für den minimal erforderlichen Zugriff ausgelegt
- Vertrauliche und hochgradig regulierte digitale Objekte sind mit Bezeichnungen versehen, verschlüsselt und an sicheren Orten gespeichert
- Hochgradig regulierte digitale Objekte sind durch zusätzliche Verschlüsselung und Berechtigungen geschützt
- Mitarbeiter der IT-Sicherheit können den aktuellen Sicherheitsstatus über zentrale Dashboards überwachen und erhalten Benachrichtigungen zu sicherheitsrelevanten Ereignissen, um schnell reagieren und Lösungen finden zu können

## <a name="contosos-path-to-microsoft-365-security-readiness"></a>Contosos Weg zur Sicherheit mit Microsoft 365

Contoso hat die folgenden Schritte verwendet, um die Sicherheit für die Bereitstellung von Microsoft 365 für Unternehmen vorzubereiten:

1. Beschränkte Administratorkonten für die Cloud

   Bei Contoso wurde eine umfassende Überprüfung der vorhandenen Active Directory Domain Services (AD DS)-Administratorkonten vorgenommen und eine Reihe von dedizierten Cloud-Administratorkonten und -gruppen eingerichtet.

2. Ausführen der Analyse für Datenklassifizierung in drei Stufen

   Contoso hat eine sorgfältige Überprüfung durchgeführt und die drei Ebenen ermittelt, mit denen die Microsoft 365 for Enterprise-Features zum Schutz der wertvollsten Daten von Contoso bestimmt wurden.

3. Festlegen des Zugriffs, der Aufbewahrung und der Informationsschutzrichtlinien für Datenstufen

   Auf Basis der Datenstufen hat Contoso ausführliche Anforderungen festgelegt, die dazu verwendet werden, zukünftige IT-Arbeitslasten zu qualifizieren, die in die Cloud verschoben werden.

In Übereinstimmung mit den bewährten Sicherheitsmethoden und den Bereitstellungsanforderungen von Microsoft 365 für Unternehmen haben die Sicherheitsadministratoren und die IT-Abteilung von Contoso viele Sicherheitsfeatures und-Funktionen bereitgestellt, wie in den folgenden Abschnitten beschrieben.

## <a name="identity--access-management"></a>Identitäts- und Zugriffsverwaltung 

- Dedizierte globale Administratorkonten mit MFA und PIM

  Anstatt den normalen Benutzerkonten eine globale Administratorrolle zuzuweisen, erstellte Contoso drei dedizierte globale Administratorkonten mit sicheren Kennwörtern. Diese Konten wurden durch Azure Multi-Factor Authentication (MFA) und Azure Active Directory (Azure AD) Privileged Identity Management (PIM) geschützt. PIM ist nur mit Microsoft 365 E5 verfügbar.

  Das Anmelden mit einem globalen Administratorkonto wird nur für bestimmte Verwaltungsaufgaben ausgeführt, die Kennwörter sind nur festgelegten Mitarbeitern bekannt, und sie können nur in dem Zeitraum verwendet werden, der in Azure AD PIM definiert ist. 

  Den Contoso-Sicherheitsadministratoren sind Administratorrollen mit weniger Berechtigungen zugewiesen, die der Position und dem Verantwortungsbereich des IT-Mitarbeiters entsprechen.

  Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

- Mehrstufige Authentifizierung (MFA) für alle Benutzerkonten

  Bei der mehrstufigen Authentifizierung wird eine zusätzliche Sicherheitsstufe zum Anmeldevorgang hinzugefügt, indem Benutzer aufgefordert werden, Ihre Identität nach korrekter Eingabe des Kennworts per Telefonanruf, Textnachricht oder App-Benachrichtigung auf Ihrem Smartphone zu bestätigen. Mit der mehrstufigen Authentifizierung sind Azure AD-Benutzerkonten vor nicht autorisierter Anmeldung geschützt, selbst wenn ein Kontokennwort kompromittiert wird.

   - Zum Schutz vor einer Kompromittierung des Microsoft 365-Abonnements wird bei Contoso die mehrstufige Authentifizierung für alle globalen Administratorkonten durchgesetzt.
   - Zum Schutz vor Phishingangriffen, bei denen die Anmeldeinformationen einer vertrauenswürdigen Person in der Organisation kompromittiert und böswillige E-Mails gesendet werden, wurde bei Contoso die mehrstufige Authentifizierung für alle Benutzerkonten aktiviert, einschließlich Manager und Führungskräfte. 

- Sicherer Zugriff auf Geräte und Anwendungen durch bedingte Zugriffsrichtlinien

  Contoso verwendet [bedingte Zugriffsrichtlinien](microsoft-365-policies-configurations.md) für Identität, Geräte, Exchange Online und SharePoint. Bedingte Zugriffsrichtlinien für die Identität erfordern unter anderem die Änderung des Kennworts für Benutzer mit hohem Risiko und das Blockieren der Verwendung von Apps, die keine moderne Authentifizierung unterstützten, durch Clients. Geräterichtlinien umfassen die Definition von genehmigten Apps und erfordern kompatible PCs und mobile Geräte. Bedingte Zugriffsrichtlinien für Exchange Online umfassen das Blockieren von ActiveSync-Clients und das Einrichten der Nachrichtenverschlüsselung in Office 365. Bedingte Zugriffsrichtlinien für SharePoint umfassen zusätzlichen Schutz für vertrauliche und hochgradig regulierte Websites.

- Windows Hello for Business

  Contoso hat [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) bereitgestellt und macht dies erforderlich, sodass schließlich die Notwendigkeit von Kennwörtern mit starker zweistufiger Authentifizierung auf PCs und mobilen Geräten unter Windows 10 Enterprise entfällt.

- Windows Defender Credential Guard

  Um gezielte Angriffe und das Ausführen von Schadsoftware im Betriebssystem mit Administratorrechten zu blockieren, hat Contoso [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) über eine AD DS-Gruppenrichtlinie aktiviert.

## <a name="threat-protection"></a>Bedrohungsschutz

- Schutz vor Schadsoftware mit Windows Defender Antivirus

  Contoso verwendet [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) zum Schutz vor Schadsoftware und für die Verwaltung von Antischadsoftware für PCs und Geräte mit Windows 10 Enterprise.

- Sicherer E-Mail-Fluss und Postfach-Prüfprotokollierung mit Office 365 Advanced Threat Protection 

  Zum Schutz vor unbekannter Schadsoftware, Viren und böswilligen URLs, die per E-Mail gesendet werden, verwendet Contoso Exchange Online Protection und [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp). 

  Bei Contoso wurde außerdem die Postfachüberwachungsprotokollierung aktiviert, um zu bestimmen, wer sich bei Benutzerpostfächern angemeldet und Nachrichten gesendet hat, sowie andere Aktivitäten zu überwachen, die vom Benutzerpostfach, einem delegierten Benutzer oder einem Administrator durchgeführt wurden.

- Angriffsüberwachung und -vermeidung mit der Bedrohungssuche und -reaktion von Office 365 

  Contoso verwendet die [Bedrohungssuche und -reaktion von Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-ti), um die Benutzer zu schützen, indem Angriffe auf einfache Weise erkannt werden und entsprechende Maßnahmen ergriffen werden können, damit so künftige Angriffe vermieden werden.

- Schutz vor raffinierten Angriffen mit Advanced Threat Analytics

  Contoso verwendet [Advanced Threat Analytics (ATA](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata), um sich vor fortschrittlichen gezielten Angriffen zu schützen. ATA analysiert normales und ungewöhnliches Verhalten von Entitäten (Benutzer, Geräte und Ressourcen), lernt daraus und kann es identifizieren. 

## <a name="information-protection"></a>Schutz von Daten

- Schützen von vertraulichen und hochgradig regulierten digitalen Objekten mit Azure Information Protection-Bezeichnungen

  Contoso ermittelte drei Stufen für den Schutz von Daten und stellte [Microsoft 365-Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) bereit, die Benutzer auf digitale Objekte anwenden konnten. Für Geschäftsgeheimnisse und anderes geistiges Eigentum verwendet Contoso Vertraulichkeitsunterbezeichnungen für stark regulierte Daten, die den Inhalt verschlüsseln und den Zugriff auf bestimmte Benutzerkonten und -gruppen beschränkt.

- Verhindern von Datenlecks mit Data Loss Prevention (DLP)

  Contoso hat [DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) für Exchange Online, SharePoint und OneDrive for Business konfiguriert, um zu verhindern, dass Benutzer versehentlich vertrauliche Daten weitergeben.

- Verhindern von Geräte-Datenlecks mit Windows Information Protection

  Contoso verwendet [Windows Informationen Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) zum Schutz vor Datenlecks durch Internet-basierte Apps und Dienste, durch Unternehmens-Apps und Daten auf Geräten im Besitz des Unternehmens und persönliche Geräte, die Mitarbeiter zur Arbeit bringen.

- Cloudüberwachung mit Microsoft Cloud App Security

  Contoso verwendet [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security), um seine Cloudumgebung zu strukturieren, die Nutzung zu überwachen und Sicherheitsereignisse und -vorfälle zu erkennen. Microsoft Cloud App Security ist nur mit Microsoft 365 E5 verfügbar.

- Geräteverwaltung mit Microsoft Intune

  Contoso verwendet [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) zum Registrieren und Verwalten von mobilen Geräten und zum Konfigurieren des Zugriffs darauf, ebenso wie zum Konfigurieren der Apps, die auf den Geräten ausgeführt werden können. Gerätebasierte bedingte Zugriffsrichtlinien erfordern ebenfalls genehmigte Apps und kompatible PCs bzw. mobile Geräte.

## <a name="security-management"></a>Sicherheitsverwaltung

- Zentrales Sicherheits-Dashboard für die IT mit Azure Security Center

  Contoso verwendet das [Azure Security Center](https://azure.microsoft.com/services/security-center/) für eine einheitliche Ansicht der Sicherheit und des Bedrohungsschutzes und um Sicherheitsrichtlinien über Workloads hinweg zu verwalten sowie auf Cyberangriffe zu reagieren.

- Zentrales Sicherheits-Dashboard für Benutzer mit Windows Defender Security Center

  Contoso hat auf PCs und auf Geräten, die Windows 10 Enterprise verwenden, die [Windows-Sicherheits-App](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) bereitgestellt, damit Benutzer ihren Sicherheitsstand auf einen Blick sehen und entsprechende Maßnahmen ergreifen können.

