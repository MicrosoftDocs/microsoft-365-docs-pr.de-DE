---
title: Schritte zum Konfigurieren von Bedrohungsschutzfunktionen in Microsoft 365
description: Erfahren Sie, wie Sie Bedrohungsschutzdienste und -funktionen in Microsoft 365 E5 bereitstellen.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 492db78c9aea881ae05dbc66f5e84ad98629b923
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931986"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Konfigurieren von Bedrohungsschutzfunktionen in Microsoft 365

Führen Sie die folgenden Schritte aus, um den Bedrohungsschutz in Microsoft 365 zu konfigurieren.


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Schritt 1: Einrichten von mehrstufiger Authentifizierung und Richtlinien für bedingten Zugriff

[Bei der mehrstufigen Authentifizierung (Multi-Factor Authentication,](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) MFA) müssen Benutzer ihre Identität mit einem Telefonanruf oder einer Authentifizierungs-App überprüfen. [Richtlinien für bedingten](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) Zugriff definieren bestimmte Anforderungen, die erfüllt sein müssen, damit Benutzer auf Apps und Daten in Microsoft 365 zugreifen können. MFA und Richtlinien für bedingten Zugriff arbeiten zusammen, um Ihre Organisation zu schützen. Wenn beispielsweise jemand versucht, sich über ein mobiles Gerät mit einem Konto, das nicht für MFA aktiviert ist, anmeldet und eine Richtlinie für bedingten Zugriff MFA erfordert, wird dieser Benutzer daran gehindert, sich zu anmelden.  

Microsoft hat einen bestimmten Satz bedingter Zugriffe und zugehöriger Richtlinien zum Schutz des Zugriffs auf alle Ihre SaaS-Anwendungen, insbesondere Microsoft 365, getestet und empfohlen. Richtlinien werden für grundlegenden, vertraulichen und hochgradig regulierten Schutz empfohlen. Implementieren Sie zunächst die Richtlinien für den grundlegenden Schutz. 


[ ![ Allgemeine Richtlinien zum Konfigurieren des Identitäts- und Gerätezugriffs](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [Siehe eine größere Version dieses Bilds](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>So implementieren Sie grundlegenden Schutz für Microsoft 365

![Prozess für die Bereitstellung des grundlegenden Schutzes](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Konfigurieren Sie die voraussetzungen, einschließlich Azure Identity Protection](../security/office-365-security/identity-access-prerequisites.md).
2. [Konfigurieren Sie allgemeine Identitäts- und Gerätezugriffsrichtlinien](../security/office-365-security/identity-access-policies.md) für grundlegenden Schutz.
3. Konfigurieren Sie Richtlinien [für Gastbenutzer,](../security/office-365-security/identity-access-policies-guest-access.md) [Microsoft Teams,](../security/office-365-security/teams-access-policies.md) [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)und [SharePoint Online und OneDrive.](../security/office-365-security/sharepoint-file-access-policies.md)

### <a name="more-information-about-protecting-identities"></a>Weitere Informationen zum Schützen von Identitäten

- [Konfigurationen für den Identitäts- und Gerätezugriff](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Sicherheitsanleitung für Azure MFA](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>Schritt 2: Konfigurieren von Microsoft Defender for Identity

[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ist eine cloudbasierte Sicherheitslösung, die mit Ihren lokalen [Azure Active](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) Directory-Signalen arbeitet, um fortgeschrittene Bedrohungen, gefährdete Identitäten und böswillige Insideraktionen zu identifizieren, zu erkennen und zu untersuchen, die gegen Ihre Organisation gerichtet sind.

Microsoft Defender for Identity ermöglicht (SecOps)-Analysten und Sicherheitsexperten, erweiterte Angriffe in Hybridumgebungen zu erkennen, um:
- Überwachen Sie Benutzer, Entitätsverhalten und Aktivitäten mit lernbasierten Analysen.
- Schützt Benutzeridentitäten und Anmeldeinformationen, die in Active Directory gespeichert sind.
- Identifizieren und untersuchen Sie verdächtige Benutzeraktivitäten und fortgeschrittene Angriffe in der gesamten Abwehrkette.
- Bereitstellen klarer Vorfallinformationen auf einer einfachen Zeitachse für eine schnelle Sichtung.

### <a name="to-set-up-microsoft-defender-for-identity"></a>So richten Sie Microsoft Defender for Identity ein

![Prozess für die Bereitstellung von Microsoft Defender for Identity](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [Richten Sie Microsoft Defender for Identity zum](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) Schutz Ihrer primären Umgebungen ein.
2. Schützen Sie alle [Domänencontroller und](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) [Gesamtstrukturen.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)
3. Integrieren [Sie Microsoft Defender for Identity-Warnungen](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) in Ihren Security Operations (SecOps)-Workflow.

### <a name="more-information-about-microsoft-defender-for-identity"></a>Weitere Informationen zu Microsoft Defender for Identity

- [Was ist Microsoft Defender for Identity?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Video: Einführung in Microsoft Defender for Identity](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Bereitstellung von Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>Schritt 3: Aktivieren von Microsoft 365 Defender

[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) kombiniert Signale und orchestriert Funktionen in einer einzigen Lösung. Mit der integrierten Microsoft 365 #A0 können Sicherheitsexperten die Bedrohungssignale zusammenbringen, die jedes dieser Produkte erhält, und den vollständigen Umfang und die Auswirkungen der Bedrohung bestimmen. wie es in die Umgebung eintrat, was davon betroffen ist und wie sich dies derzeit auf die Organisation ausdingt. Microsoft 365 Defender ergreift automatische Maßnahmen, um den Angriff zu verhindern oder zu stoppen und betroffene Postfächer, Endpunkte und Benutzeridentitäten selbst zu löschen.

Microsoft 365 Defender vereint Warnungen, Vorfälle, automatisierte Untersuchung und Reaktion sowie die erweiterte Suche über Workloads hinweg (Microsoft Defender for Identity, Microsoft Defender für Office 365, Microsoft Defender für Endpoint und Microsoft Cloud App Security) in einem einzigen Bereich. Nachdem Sie einen oder mehrere Ihrer Defender für Office 365-Dienste konfiguriert haben, aktivieren Sie Microsoft 365 Defender. Neue Features werden kontinuierlich zu Microsoft 365 Defender hinzugefügt. Erwägen Sie, sich für den Erhalt von Vorschaufeatures zu entscheiden.

### <a name="to-set-up-microsoft-365-defender"></a>So richten Sie Microsoft 365 Defender ein

![Prozess für die Bereitstellung von Microsoft 365 Defender](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [Überprüfen Sie die Voraussetzungen.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)
2. [Aktivieren Sie Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)
3. [Melden Sie sich für Vorschaufeatures an.](https://docs.microsoft.com/microsoft-365/security/mtp/preview)

### <a name="more-information-about-microsoft-365-defender"></a>Weitere Informationen zu Microsoft 365 Defender

- [Was ist Microsoft 365 Defender?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Neuerungen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>Schritt 4: Konfigurieren von Microsoft Defender für Office 365

[Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) schützt Ihre Organisation vor böswilligen Bedrohungen in E-Mail-Nachrichten (Anlagen und URLs), Office-Dokumenten und Tools für die Zusammenarbeit. In der folgenden Tabelle sind die Features und Funktionen von Microsoft Defender für Office 365 aufgeführt, die in Microsoft 365 E5 enthalten sind:

|Konfigurations-, Schutz- und Erkennungsfunktionen|Automatisierungs-, Untersuchungs-, Wartungs- und Bildungsfunktionen|
|---|---|
|[Sichere Anlagen](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[Sichere Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[Sichere Dokumente](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[ATP für SharePoint, OneDrive und Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[Anti-Phishing in Defender für Office 365-Schutz](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[Bedrohungs-Tracker](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[Sicherheitsrisiken-Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[Automatische Untersuchung und Reaktion](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[Angriffssimulator](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Mit Microsoft Defender für Office 365 können Personen in Ihrer Organisation sicherer kommunizieren und zusammenarbeiten, mit Bedrohungsschutz für ihre E-Mail-Inhalte und Office-Dokumente.

### <a name="to-set-up-microsoft-defender-for-office-365"></a>So richten Sie Microsoft Defender für Office 365 ein

![Prozess für die Bereitstellung von Microsoft Defender für Office 365](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [Richten Sie Ihre Microsoft Defender für Office 365-Richtlinien](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)ein und konfigurieren Sie sie.
2. [Anzeigen und Verwenden Ihrer Microsoft Defender für Office 365-Berichte.](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)
3. [Nutzen Sie Die Untersuchungs- und Reaktionsfunktionen für Bedrohungen.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Weitere Informationen zu Microsoft Defender für Office 365

- [Übersicht über Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Neues in Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>Schritt 5: Konfigurieren von Microsoft Defender für Endpunkt

[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) schützt Ihre Geräte (auch als Endpunkte bezeichnet) vor Cyberbedrohungen, erweiterten Angriffen und Datenschutzverletzungen. Sicherheitsteams können effizienter die Sicherheit ihrer Endpunkte verwalten. Robuste Tools helfen Organisationen, mit nicht gepatchten Systemen mit der Erkennung von Sicherheitslücken mit [der Bedrohungs- und Sicherheitsrisikoverwaltung mithalten zu können.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Automatisierte Erkennungs- und Wiederherstellungsfunktionen, z. B. Reduzierung der Angriffsfläche, Schutz der nächsten [Generation,](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)Endpunkterkennung und [-reaktion](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)sowie automatisierte Untersuchungs- und Wiederherstellungsfunktionen, helfen Ihnen, Ihre Geräte vor Schadsoftware zu schützen. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction) [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) Zusätzlich zu diesen Funktionen können Kunden proaktive Benachrichtigungen erhalten und sich bei Bedarf an Microsoft Threat Experts wenden, als Teil des opt-in managed Hunting-Diensts. 


### <a name="set-up-microsoft-defender-for-endpoint"></a>Einrichten von Microsoft Defender for Endpoint

![Prozess für die Bereitstellung von Microsoft Defender for Endpoint](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [Bereiten Sie Ihre Microsoft Defender für die Bereitstellung von Endpoint vor.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)
2. [Einrichten der Bereitstellung von Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Onboarding in den Microsoft Defender for Endpoint-Dienst.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding)
4. [Führen Sie Die hauptaufgaben bei der Sicherheitsverwaltung aus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Weitere Informationen zu Microsoft Defender for Endpoint

- [Erfahren Sie mehr über Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection)
- [Testen Sie das Microsoft Defender for Endpoint-Evaluierungslabor.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Schritt 6: Konfigurieren von Microsoft Cloud App Security

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) ist ein Cloud Access Security Broker, der protokollerfassung, API-Connectors und Reverseproxy unterstützt. Microsoft Cloud App Security bietet umfassende Transparenz, Kontrolle über den Datenverkehr und komplexe Analysen, um Cyberbedrohungen in allen Ihren Clouddiensten zu identifizieren und zu bekämpfen. Mit Microsoft Cloud App Security können Ihre Sicherheitsvorgänge die vertraulichen Informationen Ihrer Organisation schützen, vor Cyberbedrohungen und Anomalien schützen, Apps ermitteln und überwachen, die auf die Daten Ihrer Organisation zugreifen, und sicherstellen, dass die Cloud-Apps Ihrer Organisation die Complianceanforderungen erfüllen.

### <a name="set-up-microsoft-cloud-app-security"></a>Einrichten von Microsoft Cloud App Security

![Prozess für die Bereitstellung von Microsoft Cloud App Security](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [Richten Sie das Portal und andere grundlegende Anforderungen ein.](https://docs.microsoft.com/cloud-app-security/general-setup)
2. [Einrichten der Cloudermittlung und](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) Verbinden [von Apps.](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)
3. [Bereitstellen der App-Steuerung für bedingten Zugriff für ausgewählte Apps.](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)
4. [Verwenden Sie die Untersuchungstools und Dashboards.](https://docs.microsoft.com/cloud-app-security/investigate)

### <a name="more-information-about-microsoft-cloud-app-security"></a>Weitere Informationen zu Microsoft Cloud App Security

- [Überprüfen Sie die neuen Features und Funktionen.](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Erfahren Sie mehr über Microsoft Cloud App Security.](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

## <a name="step-7-monitor-status-and-take-actions"></a>Schritt 7: Überwachen des Status und Ergreifen von Aktionen

Nachdem Sie Ihre Dienste und Funktionen zum Schutz vor Bedrohungen eingerichtet und bereitgestellt haben, besteht der nächste Schritt in der Überwachung der Bedrohungserkennung und den entsprechenden Maßnahmen. Der beste Ausgangspunkt ist das Microsoft 365 Security Center ( ), in dem Sie die Sicherheit über Ihre Microsoft-Identitäten, -Daten, -Geräte, -Apps und -Infrastruktur hinweg überwachen und [https://security.microsoft.com](https://security.microsoft.com) verwalten können. 

![Microsoft 365 Security Center](../media/solutions-architecture-center/m365-security-center.png)

Das Microsoft 365 Security Center ist speziell für Sicherheitsadministratoren und Sicherheitsteams vorgesehen. Im Microsoft 365 Security Center können Sie:
- Zeigen Sie den allgemeinen Sicherheitszustand Ihrer Organisation mit [der Sicherheitsleistung an.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)
- [Überwachen und Anzeigen von Berichten](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) über den Status Ihrer Identitäten, Daten, Geräte, Apps und Infrastruktur.
- Verbinden Sie die Punkte bei Warnungen über [Vorfälle.](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- Verwenden [Sie automatisierte Untersuchungen und Korrekturen, um](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) Bedrohungen zu adressieren.
- [Proaktive Suche nach Bedrohungen,](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)z. B. Angriffsversuche oder Angriffsaktivitäten, die Ihre E-Mails, Daten, Geräte und Identitäten betreffen.
- [Verstehen Sie die neuesten Angriffskampagnen und](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) -techniken mit Bedrohungsanalysen.
- ... und vieles mehr!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Weitere Informationen zum Microsoft 365 Security Center

- [Erste Schritte mit dem Microsoft 365 Security Center](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).
- [Überwachen und Anzeigen von Berichten](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting).
- [Weitere Informationen finden Sie in den Sicherheitsportalen in Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="step-8-train-users"></a>Schritt 8: Schulen von Benutzern

Schulungsbenutzer können Ihre Benutzer und Ihr Sicherheitsteam viel Zeit und Frustration sparen. Versierte Benutzer sind weniger wahrscheinlich, Anlagen zu öffnen oder auf Links in fragwürdigen E-Mail-Nachrichten zu klicken, und sie vermeiden eher verdächtige Websites. 

Das Handbuch zur [Cybersicherheitskampagne](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) der "University University" bietet hervorragende Anleitungen zum Aufbau einer starken Kultur des Sicherheitsbewusstseins in Ihrer Organisation, einschließlich der Schulung von Benutzern zur Identifizierung von Phishingangriffen. 

Microsoft 365 bietet die folgenden Ressourcen, um Benutzer in Ihrer Organisation zu informieren:

|Konzept  |Ressourcen  |
|---------|---------|
|Microsoft 365     |[Anpassbare Lernpfade](https://docs.microsoft.com/office365/customlearning/) <p>Diese Ressourcen können Ihnen dabei helfen, Schulungen für Endbenutzer in Ihrer Organisation zusammen zu stellen.        |
|Microsoft 365 Security Center |[Lernmodul: Sichern Ihrer Organisation mit integrierter, intelligenter Sicherheit von Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>In diesem Modul können Sie beschreiben, wie Microsoft 365-Sicherheitsfeatures zusammenarbeiten und welche Vorteile diese Sicherheitsfeatures bieten. |
|Mehrstufige Authentifizierung     | [Überprüfung in zwei Schritten: Was ist die zusätzliche Überprüfungsseite?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Dieser Artikel hilft Endbenutzern zu verstehen, was die mehrstufige Authentifizierung ist und warum sie in Ihrer Organisation verwendet wird.    |

Zusätzlich zu dieser Anleitung empfiehlt Microsoft Ihren Benutzern, die in diesem Artikel beschriebenen Aktionen zu ergreifen: Schützen Ihres Kontos und Ihrer Geräte [vor Hackern und Schadsoftware.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) Diese setzen sich wie folgt zusammen:
- Verwenden von starken Kennwörtern
- Schützen von Geräten 
- Aktivieren von Sicherheitsfeatures auf Windows 10- und Mac-PCs (für nicht verwaltete Geräte)
    
Microsoft empfiehlt außerdem, dass Benutzer ihre persönlichen E-Mail-Konten schützen, indem sie die in den folgenden Artikeln empfohlenen Aktionen ausführen:
- [Schützen Ihres E Outlook.com-E-Mail-Kontos](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Schützen Ihres Gmail-Kontos mit der Überprüfung in zwei Schritten](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
