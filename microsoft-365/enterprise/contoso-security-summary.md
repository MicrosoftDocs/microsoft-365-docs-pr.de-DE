---
title: Zusammenfassung der Microsoft 365 unternehmenssicherheit für die Contoso Corporation
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
description: Wie Contoso die Sicherheitsfeatures von Microsoft 365 Enterprise verwendet.
ms.openlocfilehash: 59eed0b7e08aae8397bb037e6d1b515bf6aa0ba8
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113450"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Zusammenfassung der Microsoft 365 unternehmenssicherheit für die Contoso Corporation

Um die Genehmigung für die Bereitstellung Microsoft 365 Unternehmens zu erhalten, hat die Contoso-IT-Sicherheitsabteilung eine sorgfältige Sicherheitsüberprüfung durchgeführt. Sie haben die folgenden Sicherheitsanforderungen für die Cloud identifiziert:

- Verwenden Sie die stärksten Authentifizierungsmethoden für den Mitarbeiterzugriff auf Cloudressourcen.
- Stellen Sie sicher, dass PCs und mobile Geräte anwendungen auf sichere Weise verbinden und darauf zugreifen.
- Schützen Sie PCs und E-Mails vor Schadsoftware.
- Berechtigungen für cloudbasierte digitale Objekte definieren, wer auf was und was sie tun können, und sind für den Zugriff mit den geringsten Rechten konzipiert.
- Vertrauliche und streng regulierte digitale Objekte werden gekennzeichnet, verschlüsselt und an sicheren Orten gespeichert.
- Streng regulierte digitale Objekte sind durch zusätzliche Verschlüsselung und Berechtigungen geschützt.
- IT-Sicherheitsmitarbeiter können die aktuelle Sicherheitslage über zentrale Dashboards überwachen und sich über Sicherheitsereignisse für schnelle Reaktionen und Gegenmaßnahmen informiert machen.

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Der Contoso-Pfad Microsoft 365 Sicherheitsbereitschaft

Contoso hat die folgenden Schritte befolgt, um die Sicherheit für die Bereitstellung von Microsoft 365 Unternehmen vorzubereiten:

1. Einschränken von Administratorkonten für die Cloud

   Contoso hat eine umfassende Überprüfung der vorhandenen Active Directory Domain Services (AD DS)-Administratorkonten erstellt und eine Reihe dedizierter Cloudadministratorkonten und -gruppen eingerichtet.

2. Klassifizieren von Daten in drei Sicherheitsstufen

   Contoso hat die drei Ebenen sorgfältig überprüft und ermittelt, mit denen die Microsoft 365 für Unternehmensfeatures identifiziert wurden, um die wertvollsten Daten zu schützen.

3. Bestimmen von Zugriffs-, Aufbewahrungs- und Datensicherungsrichtlinien für Datenstufen

   Basierend auf den Datenebenen hat Contoso detaillierte Anforderungen zur Qualifizierung zukünftiger IT-Workloads ermittelt, die in die Cloud verschoben werden.

Um bewährte Sicherheitsmethoden und Microsoft 365 anforderungen für die Unternehmensbereitstellung zu befolgen, haben Contoso-Sicherheitsadministratoren und ihre IT-Abteilung viele Sicherheitsfeatures und -funktionen bereitgestellt, wie in den folgenden Abschnitten beschrieben.

## <a name="identity-and-access-management"></a>Identitäts- und Zugriffsverwaltung 

- Dedizierte globale Administratorkonten mit MFA und PIM

  Anstatt die globale Administratorrolle alltäglichen Benutzerkonten zuzuordnen, hat Contoso drei dedizierte globale Administratorkonten mit starken Kennwörtern erstellt. Die Konten sind durch azure AD Multi-Factor Authentication (MFA) und Azure Active Directory (Azure AD) Privileged Identity Management (PIM) geschützt. *PIM ist nur mit Microsoft 365 E5 verfügbar.*

  Die Anmeldung mit einem globalen Administratorkonto erfolgt nur für bestimmte Administrative Aufgaben. Die Kennwörter sind nur bestimmten Mitarbeitern bekannt und können nur innerhalb eines Zeitraums verwendet werden, der in Azure AD PIM konfiguriert ist.

  Contoso-Sicherheitsadministratoren haben Konten, die für die Auftragsfunktion dieses IT-Mitarbeiters geeignet sind, kleinere Administratorrollen zugewiesen.

  Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](/office365/admin/add-users/about-admin-roles).

- Mehrstufige Authentifizierung (MFA) für alle Benutzerkonten

  MFA fügt dem Anmeldevorgang eine zusätzliche Schutzebene hinzu. Es erfordert, dass Benutzer einen Anruf, eine SMS oder eine App-Benachrichtigung auf ihrem Smartphone bestätigen, nachdem sie ihr Kennwort richtig eingegeben haben. Mit MFA sind Azure AD-Benutzerkonten vor nicht autorisierter Anmeldung geschützt, auch wenn ein Kontokennwort gefährdet ist.

   - Zum Schutz vor der Microsoft 365 des Abonnements erfordert Contoso MFA für alle globalen Administratorkonten.
   - Zum Schutz vor Phishingangriffen, bei denen die Anmeldeinformationen einer vertrauenswürdigen Person in der Organisation kompromittiert und böswillige E-Mails gesendet werden, wurde bei Contoso die mehrstufige Authentifizierung für alle Benutzerkonten aktiviert, einschließlich Manager und Führungskräfte.

- Sicherer Zugriff auf Geräte und Anwendungen durch bedingte Zugriffsrichtlinien

  Contoso verwendet [bedingte Zugriffsrichtlinien](../security/office-365-security/microsoft-365-policies-configurations.md) für Identität, Geräte, Exchange Online und SharePoint. Bedingte Zugriffsrichtlinien für die Identität erfordern unter anderem die Änderung des Kennworts für Benutzer mit hohem Risiko und das Blockieren der Verwendung von Apps, die keine moderne Authentifizierung unterstützten, durch Clients. Geräterichtlinien umfassen die Definition von genehmigten Apps und erfordern kompatible PCs und mobile Geräte. Bedingte Zugriffsrichtlinien für Exchange Online umfassen das Blockieren von ActiveSync-Clients und das Einrichten der Nachrichtenverschlüsselung in Office 365. Bedingte Zugriffsrichtlinien für SharePoint umfassen zusätzlichen Schutz für vertrauliche und hochgradig regulierte Websites.

- Windows Hello for Business

  Contoso hat [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification) bereitgestellt, um die Notwendigkeit von Kennwörtern durch eine starke zweistufige Authentifizierung auf PCs und mobilen Geräten, auf Windows 10 Enterprise.

- Windows Defender Credential Guard

  Um gezielte Angriffe und Schadsoftware zu blockieren, die [](/windows/security/identity-protection/credential-guard/credential-guard) im Betriebssystem mit Administratorrechten ausgeführt werden, aktivierte Contoso Windows Defender Credential Guard AD DS-Gruppenrichtlinie.

## <a name="threat-protection"></a>Bedrohungsschutz

- Schutz vor Schadsoftware mit Windows Defender Antivirus

  Contoso verwendet [Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) zum Schutz vor Schadsoftware und für die Verwaltung von Antischadsoftware für PCs und Geräte mit Windows 10 Enterprise.

- Sichere E-Mail-Fluss- und Postfach-Überwachungsprotokollierung mit Microsoft Defender für Office 365 

  Contoso verwendet Exchange Online Protection [und Defender für Office 365,](/office365/securitycompliance/office-365-atp) um sich vor unbekannter Schadsoftware, Viren und schädlichen URLs zu schützen, die über E-Mails übertragen werden.

  Contoso aktivierte außerdem die Postfach-Überwachungsprotokollierung, um zu ermitteln, wer sich bei Benutzerpostfächern anmeldet, Nachrichten sendet und andere Aktivitäten des Postfachbesitzers, eines delegierten Benutzers oder eines Administrators ausgeführt.

- Angriffsüberwachung und -vermeidung mit der Bedrohungssuche und -reaktion von Office 365 

  Contoso verwendet [Office 365 Bedrohungsuntersuchung und -reaktion,](/office365/securitycompliance/office-365-ti) um Benutzer zu schützen, indem es einfacher wird, Angriffe zu identifizieren und zu adressiert und zukünftige Angriffe zu verhindern.

- Schutz vor raffinierten Angriffen mit Advanced Threat Analytics

  Contoso verwendet [Advanced Threat Analytics (ATA](/advanced-threat-analytics/what-is-ata), um sich vor fortschrittlichen gezielten Angriffen zu schützen. ATA analysiert normales und ungewöhnliches Verhalten von Entitäten (Benutzer, Geräte und Ressourcen), lernt daraus und kann es identifizieren.

## <a name="information-protection"></a>Schutz von Daten

- Schützen von vertraulichen und hochgradig regulierten digitalen Objekten mit Azure Information Protection-Bezeichnungen

  Contoso hat drei Ebenen des Datenschutzes festgelegt und Microsoft 365 Vertraulichkeitsbezeichnungen [bereitgestellt,](../compliance/sensitivity-labels.md) die Benutzer auf digitale Objekte anwenden. Für seine Geschäftsgeheimnisse und andere geistiges Eigentum verwendet Contoso Vertraulichkeitsunterlabels für streng regulierte Daten. Dieser Prozess verschlüsselt Inhalte und schränkt den Zugriff auf bestimmte Benutzerkonten und Gruppen ein.

- Verhindern von Datenlecks mit Data Loss Prevention (DLP)

  Contoso hat [Richtlinien](../compliance/dlp-learn-about-dlp.md) zur Verhinderung von Datenverlust für Exchange Online, SharePoint und OneDrive for Business konfiguriert, um zu verhindern, dass Benutzer versehentlich oder absichtlich vertrauliche Daten freigeben.

- Verhindern von Geräte-Datenlecks mit Windows Information Protection

  Contoso verwendet [Windows Information Protection (WIP)](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) zum Schutz vor Datenlecks durch internetbasierte Apps und Dienste sowie Unternehmens-Apps und Daten auf Unternehmensgeräten und persönlichen Geräten, die Mitarbeiter zur Arbeit bringen.

- Cloudüberwachung mit Microsoft Cloud App Security

  Contoso verwendet [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security), um seine Cloudumgebung zu strukturieren, die Nutzung zu überwachen und Sicherheitsereignisse und -vorfälle zu erkennen. *Microsoft Cloud App Security ist nur mit Microsoft 365 E5 verfügbar.*

- Geräteverwaltung mit Microsoft Intune

  Contoso verwendet [Microsoft Intune](/intune/introduction-intune) zum Registrieren und Verwalten von mobilen Geräten und zum Konfigurieren des Zugriffs darauf, ebenso wie zum Konfigurieren der Apps, die auf den Geräten ausgeführt werden können. Gerätebasierte bedingte Zugriffsrichtlinien erfordern ebenfalls genehmigte Apps und kompatible PCs bzw. mobile Geräte.

## <a name="security-management"></a>Sicherheitsverwaltung

- Zentrales Sicherheitsdashboard für DIE IT mit Azure Defender

  Contoso verwendet [Azure Defender,](https://azure.microsoft.com/services/security-center/) um eine einheitliche Ansicht des Sicherheits- und Bedrohungsschutzes zu präsentieren, Sicherheitsrichtlinien über alle Arbeitsauslastungen hinweg zu verwalten und auf Cyberangriffe zu reagieren.

- Zentrales Sicherheits-Dashboard für Benutzer mit Windows Defender Security Center

  Contoso hat die [Windows-Sicherheit-App](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) auf seinen PCs und Geräten mit Windows 10 Enterprise bereitgestellt, damit Benutzer ihre Sicherheitslage auf einen Blick sehen und Maßnahmen ergreifen können.