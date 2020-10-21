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
description: Wie Contoso die Sicherheitsfunktionen von Microsoft 365 für Unternehmen verwendet.
ms.openlocfilehash: 635336b70318acdd4ed013a2705691d160926e84
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649701"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Zusammenfassung von Microsoft 365 für Enterprise-Sicherheit für die Contoso Corporation

Um die Genehmigung zur Bereitstellung von Microsoft 365 für Unternehmen zu erhalten, hat die IT-Sicherheitsabteilung von Contoso eine umfassende Sicherheitsüberprüfung durchgeführt. Sie haben die folgenden Sicherheitsanforderungen für die Cloud ermittelt:

- Verwenden Sie die stärksten Authentifizierungsmethoden für den Zugriff von Mitarbeitern auf Cloud-Ressourcen.
- Stellen Sie sicher, dass PCs und mobile Geräte auf sichere Weise eine Verbindung herstellen und auf Anwendungen zugreifen.
- Schützen Sie PCs und e-Mails vor Schadsoftware.
- Berechtigungen für Cloud-basierte digitale Objekte definieren, wer auf welche Aufgaben zugreifen kann und wie er für den Zugriff auf die geringsten Rechte ausgelegt ist.
- Vertrauliche und stark regulierte digitale Objekte werden in sicheren Speicherorten gekennzeichnet, verschlüsselt und gespeichert.
- Hochregulierte digitale Objekte werden mit zusätzlicher Verschlüsselung und Berechtigungen geschützt.
- IT-Sicherheitsmitarbeiter können die aktuelle Sicherheitslage über zentrale Dashboards überwachen und über Sicherheitsereignisse auf schnelle Reaktion und Minderung informieren.

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Der Contoso-Pfad zur Sicherheitsbereitschaft von Microsoft 365

Contoso hat die folgenden Schritte ausgeführt, um die Sicherheit für die Bereitstellung von Microsoft 365 für Unternehmen vorzubereiten:

1. Einschränken von Administratorkonten für die Cloud

   Contoso hat eine umfassende Überprüfung der vorhandenen Active Directory-Domänendienste (AD DS) Administratorkonten vorgenommen und eine Reihe dedizierter Cloud-Administratorkonten und-Gruppen eingerichtet.

2. Klassifizieren von Daten in drei Sicherheitsstufen

   Contoso hat eine sorgfältige Überprüfung vorgenommen und die drei Ebenen ermittelt, die verwendet wurden, um die Microsoft 365 für Enterprise-Features zum Schutz der wertvollsten Daten zu identifizieren.

3. Bestimmen von Zugriffs-, Aufbewahrungs- und Datensicherungsrichtlinien für Datenstufen

   Basierend auf den Datenebenen haben Contoso detaillierte Anforderungen zum qualifizieren zukünftiger IT-Arbeitslasten ermittelt, die in die Cloud verschoben werden.

Um Sicherheits bewährte Methoden und Microsoft 365 für Enterprise-Bereitstellungsanforderungen zu befolgen, haben Contoso-Sicherheitsadministratoren und die IT-Abteilung viele Sicherheitsfeatures und-Funktionen bereitgestellt, wie in den folgenden Abschnitten beschrieben.

## <a name="identity-and-access-management"></a>Identitäts- und Zugriffsverwaltung 

- Dedizierte globale Administratorkonten mit MFA und PIM

  Anstatt die globale Administratorrolle alltäglichen Benutzerkonten zuzuweisen, hat Contoso drei dedizierte globale Administratorkonten mit sicheren Kennwörtern erstellt. Die Konten sind durch Azure Multi-Factor Authentication (MFA) und Azure Active Directory (Azure AD) Privileged Identity Management (PIM) geschützt. *PIM ist nur mit Microsoft 365 E5 verfügbar.*

  Die Anmeldung mit einem globalen Administratorkonto erfolgt nur für bestimmte administrative Aufgaben. Die Kennwörter sind nur für designierte Mitarbeiter bekannt und können nur innerhalb eines Zeitraums verwendet werden, der in Azure AD PIM konfiguriert ist.

  Contoso-Sicherheitsadministratoren haben Konten, die für die Funktion des IT-Mitarbeiters geeignet sind, kleinere Administratorrollen zugewiesen.

  Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

- Mehrstufige Authentifizierung (MFA) für alle Benutzerkonten

  MFA fügt dem Anmeldevorgang eine zusätzliche Schutzschicht hinzu. Es erfordert, dass Benutzer nach der korrekten Eingabe Ihres Kennworts einen Telefonanruf, eine Textnachricht oder eine APP-Benachrichtigung auf dem Smartphone bestätigen. Bei MFA sind Azure AD Benutzerkonten gegen unberechtigte Anmeldung geschützt, auch wenn ein Kontokennwort kompromittiert wurde.

   - Um eine Gefährdung des Microsoft 365-Abonnements zu verhindern, benötigt Contoso für alle globalen Administratorkonten MFA.
   - Zum Schutz vor Phishingangriffen, bei denen die Anmeldeinformationen einer vertrauenswürdigen Person in der Organisation kompromittiert und böswillige E-Mails gesendet werden, wurde bei Contoso die mehrstufige Authentifizierung für alle Benutzerkonten aktiviert, einschließlich Manager und Führungskräfte.

- Sicherer Zugriff auf Geräte und Anwendungen durch bedingte Zugriffsrichtlinien

  Contoso verwendet [bedingte Zugriffsrichtlinien](../security/office-365-security/microsoft-365-policies-configurations.md) für Identität, Geräte, Exchange Online und SharePoint. Bedingte Zugriffsrichtlinien für die Identität erfordern unter anderem die Änderung des Kennworts für Benutzer mit hohem Risiko und das Blockieren der Verwendung von Apps, die keine moderne Authentifizierung unterstützten, durch Clients. Geräterichtlinien umfassen die Definition von genehmigten Apps und erfordern kompatible PCs und mobile Geräte. Bedingte Zugriffsrichtlinien für Exchange Online umfassen das Blockieren von ActiveSync-Clients und das Einrichten der Nachrichtenverschlüsselung in Office 365. Bedingte Zugriffsrichtlinien für SharePoint umfassen zusätzlichen Schutz für vertrauliche und hochgradig regulierte Websites.

- Windows Hello for Business

  Contoso hat [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) bereitgestellt, um die Notwendigkeit von Kennwörtern durch starke zweistufige Authentifizierung auf PCs und mobilen Geräten mit Windows 10 Enterprise zu eliminieren.

- Windows Defender Credential Guard

  Um gezielte Angriffe und Schadsoftware, die im Betriebssystem ausgeführt wird, mit Administratorrechten zu blockieren, aktivierte Contoso die [Windows Defender-Anmeldeinformationen-Schutz](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) über AD DS Gruppenrichtlinie.

## <a name="threat-protection"></a>Bedrohungsschutz

- Schutz vor Schadsoftware mit Windows Defender Antivirus

  Contoso verwendet [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) zum Schutz vor Schadsoftware und für die Verwaltung von Antischadsoftware für PCs und Geräte mit Windows 10 Enterprise.

- Sicherer E-Mail-Fluss und Postfach-Prüfprotokollierung mit Office 365 Advanced Threat Protection 

  Zum Schutz vor unbekannter Schadsoftware, Viren und böswilligen URLs, die per E-Mail gesendet werden, verwendet Contoso Exchange Online Protection und [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).

  Contoso hat auch die postfachüberwachungsprotokollierung aktiviert, um zu identifizieren, wer sich bei Benutzerpostfächern anmeldet, Nachrichten sendet und andere Aktivitäten ausführt, die vom Postfachbesitzer, einem Delegierten Benutzer oder einem Administrator ausgeführt werden.

- Angriffsüberwachung und -vermeidung mit der Bedrohungssuche und -reaktion von Office 365 

  Contoso verwendet [Office 365 Bedrohungs Ermittlung und-Antwort](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) , um Benutzer zu schützen, indem Sie Angriffe leicht erkennen und adressieren und zukünftige Angriffe verhindern.

- Schutz vor raffinierten Angriffen mit Advanced Threat Analytics

  Contoso verwendet [Advanced Threat Analytics (ATA](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata), um sich vor fortschrittlichen gezielten Angriffen zu schützen. ATA analysiert normales und ungewöhnliches Verhalten von Entitäten (Benutzer, Geräte und Ressourcen), lernt daraus und kann es identifizieren.

## <a name="information-protection"></a>Schutz von Daten

- Schützen von vertraulichen und hochgradig regulierten digitalen Objekten mit Azure Information Protection-Bezeichnungen

  Contoso hat drei Datenschutzstufen festgelegt und [Microsoft 365-Vertraulichkeits Bezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) bereitgestellt, die Benutzer auf digitale Objekte anwenden. Für Geschäftsgeheimnisse und andere geistiges Eigentum verwendet Contoso Sensitivitäts-Sublabels für hochregulierte Daten. Durch diesen Vorgang werden Inhalte verschlüsselt und der Zugriff auf bestimmte Benutzerkonten und Gruppen eingeschränkt.

- Verhindern von Datenlecks mit Data Loss Prevention (DLP)

  Contoso hat Richtlinien zur [Verhinderung von Datenverlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) für Exchange Online, SharePoint und OneDrive für Unternehmen konfiguriert, um zu verhindern, dass Benutzer vertrauliche Daten versehentlich oder absichtlich freigeben.

- Verhindern von Geräte-Datenlecks mit Windows Information Protection

  Contoso verwendet [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) zum Schutz vor Datenverlusten über internetbasierte apps und Dienste sowie Enterprise-apps und-Daten auf unternehmenseigenen Geräten und persönlichen Geräten, die Mitarbeiter zur Arbeit bringen.

- Cloudüberwachung mit Microsoft Cloud App Security

  Contoso verwendet [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security), um seine Cloudumgebung zu strukturieren, die Nutzung zu überwachen und Sicherheitsereignisse und -vorfälle zu erkennen. *Microsoft Cloud App Security ist nur mit Microsoft 365 E5 verfügbar.*

- Geräteverwaltung mit Microsoft Intune

  Contoso verwendet [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) zum Registrieren und Verwalten von mobilen Geräten und zum Konfigurieren des Zugriffs darauf, ebenso wie zum Konfigurieren der Apps, die auf den Geräten ausgeführt werden können. Gerätebasierte bedingte Zugriffsrichtlinien erfordern ebenfalls genehmigte Apps und kompatible PCs bzw. mobile Geräte.

## <a name="security-management"></a>Sicherheitsverwaltung

- Zentrales Sicherheits-Dashboard für die IT mit Azure Security Center

  Contoso verwendet das [Azure Security Center](https://azure.microsoft.com/services/security-center/) , um eine einheitliche Ansicht der Sicherheit und des Bedrohungsschutzes zu präsentieren, Sicherheitsrichtlinien für die Arbeitslasten zu verwalten und auf Cyberangriffe zu reagieren.

- Zentrales Sicherheits-Dashboard für Benutzer mit Windows Defender Security Center

  Contoso hat die [Windows-Sicherheits-App](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) auf ihren PCs und Geräten mit Windows 10 Enterprise bereitgestellt, damit Benutzer ihre Sicherheitslage auf einen Blick sehen und Maßnahmen ergreifen können.
