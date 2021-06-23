---
title: Schritte zum Konfigurieren von Bedrohungsschutzfunktionen über Microsoft 365
description: Verwenden Sie diesen Artikel als Leitfaden für die Implementierung Ihrer Bedrohungsschutzlösung. Bereitstellen von Bedrohungsschutzdiensten und -funktionen über Microsoft 365 E5 hinweg.
keywords: Sicherheitslösung, Setup, Konfiguration, Microsoft 365 E5, erweiterter Bedrohungsschutz, Defender
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 48a51b8ec880726bdd2121f2eaf0d78f5cd6b3e0
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083464"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Konfigurieren von Bedrohungsschutzfunktionen über Microsoft 365

Führen Sie die folgenden Schritte aus, um den Bedrohungsschutz über Microsoft 365 hinweg zu konfigurieren.

## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Schritt 1: Einrichten der mehrstufigen Authentifizierung und Richtlinien für bedingten Zugriff

[Bei der mehrstufigen Authentifizierung (Multi-Factor Authentication,](/azure/active-directory/authentication/concept-mfa-howitworks) MFA) müssen Benutzer ihre Identität mit einem Telefonanruf oder einer Authentifikator-App überprüfen. Richtlinien für [bedingten Zugriff](/azure/active-directory/conditional-access/overview) definieren bestimmte Anforderungen, die erfüllt werden müssen, damit Benutzer in Microsoft 365 auf Apps und Daten zugreifen können. MFA- und Richtlinien für bedingten Zugriff arbeiten zusammen, um Ihre Organisation zu schützen. Wenn beispielsweise jemand versucht, sich von einem mobilen Gerät mit einem Konto anzumelden, das nicht für MFA aktiviert ist, und eine Richtlinie für bedingten Zugriff erfordert, dass MFA wirksam ist, wird dieser Benutzer daran gehindert, sich anzumelden.  

Microsoft hat einen bestimmten Satz bedingten Zugriff und verwandte Richtlinien zum Schutz des Zugriffs auf alle Ihre SaaS-Anwendungen getestet und empfiehlt, insbesondere Microsoft 365. Richtlinien werden für grundlegenden, vertraulichen und streng regulierten Schutz empfohlen. Beginnen Sie mit der Implementierung der Richtlinien für den grundlegenden Schutz.

[ ![ Allgemeine Richtlinien zum Konfigurieren des Identitäts- und Gerätezugriffs](../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png) 
 [Siehe eine größere Version dieses Images.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>So implementieren Sie grundlegenden Schutz für Microsoft 365

![Prozess für die Bereitstellung des grundlegenden Schutzes](../media/deploy-threat-protection/deploy-threat-protection-identity-access-steps.png) 

1. [Konfigurieren Sie die erforderlichen Komponenten, einschließlich Azure AD Identity Protection.](../security/office-365-security/identity-access-prerequisites.md)
2. [Konfigurieren sie allgemeine Identitäts- und Gerätezugriffsrichtlinien](../security/office-365-security/identity-access-policies.md) für grundlegenden Schutz.
3. Konfigurieren von Richtlinien für [Gastbenutzer,](../security/office-365-security/identity-access-policies-guest-access.md) [Microsoft Teams,](../security/office-365-security/teams-access-policies.md) [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)und [SharePoint Online und OneDrive](../security/office-365-security/sharepoint-file-access-policies.md).

### <a name="more-information-about-protecting-identities"></a>Weitere Informationen zum Schutz von Identitäten

- [Konfigurationen für den Identitäts- und Gerätezugriff](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Sicherheitsleitfaden für Azure MFA](/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>Schritt 2: Konfigurieren von Microsoft Defender for Identity

[Microsoft Defender for Identity](/defender-for-identity/what-is) ist eine cloudbasierte Sicherheitslösung, die mit Ihren lokalen Active Directory Domain Services (AD DS)-Signalen zusammenarbeitet, um erweiterte Bedrohungen, kompromittierte Identitäten und bösartige Insideraktionen, die gegen Ihre Organisation gerichtet sind, zu identifizieren, zu erkennen und zu untersuchen.

Microsoft Defender for Identity ermöglicht Analysten und Sicherheitsexperten von Sicherheitsvorgängen (SecOps), die fortgeschrittene Angriffe in Hybridumgebungen erkennen möchten, Folgendes:

- Überwachen Sie Benutzer, Entitätsverhalten und Aktivitäten mit lernbasierten Analysen.
- Schützt Benutzeridentitäten und Anmeldeinformationen, die in Active Directory gespeichert sind.
- Identifizieren und untersuchen Sie verdächtige Benutzeraktivitäten und fortgeschrittene Angriffe in der gesamten Abwehrkette.
- Bereitstellen klarer Vorfallinformationen auf einer einfachen Zeitachse für eine schnelle Sichtung.

### <a name="to-set-up-microsoft-defender-for-identity"></a>So richten Sie Microsoft Defender for Identity ein

![Prozess für die Bereitstellung von Microsoft Defender for Identity](../media/deploy-threat-protection/deploy-azure-atp-steps.png) 

1. [Richten Sie Microsoft Defender for Identity](/azure-advanced-threat-protection/install-atp-step1) ein, um Ihre primären Umgebungen zu schützen.
2. Schützen Sie alle [Domänencontroller](/azure-advanced-threat-protection/atp-sensor-monitoring) und [Gesamtstrukturen.](/azure-advanced-threat-protection/atp-multi-forest)
3. Integrieren Sie [Microsoft Defender for Identity-Warnungen](/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) in Ihren Security Operations (SecOps)-Workflow.

### <a name="more-information-about-microsoft-defender-for-identity"></a>Weitere Informationen zu Microsoft Defender for Identity

- [Was ist Microsoft Defender for Identity?](/azure-advanced-threat-protection/what-is-atp)
- [Video: Einführung in Microsoft Defender for Identity](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Microsoft Defender for Identity-Bereitstellung](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>Schritt 3: Aktivieren Microsoft 365 Defender

[Microsoft 365 Defender](../security/defender/microsoft-365-defender.md) kombiniert Signale und Orchestrierungsfunktionen in einer einzigen Lösung. Mit der integrierten Microsoft 365 Defender Lösung können Sicherheitsexperten die Bedrohungssignale zusammenfügen, die jedes dieser Produkte erhält, und den vollständigen Umfang und die Auswirkungen der Bedrohung ermitteln. wie sie in die Umgebung gelangt ist, welche Auswirkungen sie hat und wie sie sich derzeit auf die Organisation auswirkt. Microsoft 365 Defender führt automatische Maßnahmen aus, um den Angriff zu verhindern oder zu beenden und die betroffenen Postfächer, Endpunkte und Benutzeridentitäten selbst zu verwunden.

Microsoft 365 Defender vereinheitlicht Warnungen, Vorfälle, automatisierte Untersuchung und Reaktion sowie die erweiterte Suche über Workloads (Microsoft Defender for Identity, Microsoft Defender für Office 365, Microsoft Defender für Endpunkt und Microsoft Cloud App Security) in einem einzigen Bereich. Microsoft 365 Defender werden ständig neue Features hinzugefügt. Erwägen Sie, sich für den Empfang von Vorschaufeatures zu entscheiden.

### <a name="to-set-up-microsoft-365-defender"></a>So richten Sie Microsoft 365 Defender

![Prozess für die Bereitstellung von Microsoft 365 Defender](../media/deploy-threat-protection/deploy-mtp-steps.png) 

1. [Überprüfen Sie die Voraussetzungen.](../security/defender/prerequisites.md)
2. [Aktivieren Sie Microsoft 365 Defender](../security/defender/m365d-enable.md).
3. [Melden Sie sich für Vorschaufeatures an.](../security/defender/preview.md)

### <a name="more-information-about-microsoft-365-defender"></a>Weitere Informationen zu Microsoft 365 Defender

- [Was ist Microsoft 365 Defender?](../security/defender/microsoft-365-defender.md)
- [Neuerungen in Microsoft 365 Defender](../security/defender/whats-new.md)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>Schritt 4: Konfigurieren von Microsoft Defender für Office 365

[Microsoft Defender für Office 365](../security/office-365-security/defender-for-office-365.md) schützt Ihre Organisation vor bösartigen Bedrohungen in E-Mail-Nachrichten (Anlagen und URLs), Office Dokumenten und Tools für die Zusammenarbeit. Die folgende Tabelle enthält Microsoft Defender für Office 365 Features und Funktionen, die in Microsoft 365 E5 enthalten sind:

<br>

****

|Konfigurations-, Schutz- und Erkennungsfunktionen|Automatisierungs-, Untersuchungs-, Korrektur- und Schulungsfunktionen|
|---|---|
|[Sichere Anlagen](../security/office-365-security/safe-attachments.md) <p> [Sichere Links](../security/office-365-security/safe-links.md) <p> [Sichere Dokumente](../security/office-365-security/safe-docs.md) <p> [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md) <p> [Antiphishingschutz in Microsoft 365](../security/office-365-security/anti-phishing-protection.md)|[Bedrohungs-Tracker](../security/office-365-security/threat-trackers.md) <p> [Sicherheitsrisiken-Explorer](../security/office-365-security/threat-explorer.md) <p> [Automatische Untersuchung und Reaktion](../security/office-365-security/office-365-air.md) <p> [Angriffssimulationstraining](../security/office-365-security/attack-simulation-training.md)|
|

Mit Microsoft Defender für Office 365 können Personen in Ihrer organisationweiten Organisation sicherer kommunizieren und zusammenarbeiten, mit Bedrohungsschutz für ihre E-Mail-Inhalte und Office Dokumente.

### <a name="to-set-up-microsoft-defender-for-office-365"></a>So richten Sie Microsoft Defender für Office 365

![Prozess für die Bereitstellung von Microsoft Defender für Office 365](../media/deploy-threat-protection/deploy-office365-atp-steps.png) 

1. [Richten Sie Microsoft Defender für Office 365 Richtlinien ein und konfigurieren Sie es.](../security/office-365-security/protect-against-threats.md)
2. [Anzeigen und Verwenden von Microsoft Defender für Office 365 Berichte.](../security/office-365-security/view-reports-for-mdo.md)
3. [Verwenden Sie die Funktionen zur Bedrohungsuntersuchung und -reaktion.](../security/office-365-security/office-365-ti.md)

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Weitere Informationen zu Microsoft Defender für Office 365

- [Übersicht über Microsoft Defender für Office 365](../security/office-365-security/defender-for-office-365.md)
- [Neuigkeiten in Microsoft Defender für Office 365](../security/office-365-security/whats-new-in-defender-for-office-365.md)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>Schritt 5: Konfigurieren von Microsoft Defender für Endpunkt

[Microsoft Defender für Endpunkt](/windows/security/threat-protection) schützt Ihre Geräte Ihrer Organisation (auch als Endpunkte bezeichnet) vor Cyberbedrohungen, fortgeschrittenen Angriffen und Datenschutzverletzungen. Sicherheitsteams können die Sicherheit ihrer Endpunkte effizienter verwalten. Robuste Tools helfen Organisationen, mithilfe der Sicherheitsrisikoerkennung mit [dem Bedrohungs- und Sicherheitsrisikomanagement](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)mit nicht gepatchten Systemen Schritt zu halten. Automatisierte Erkennungs- und Korrekturfunktionen wie [Attack Surface Reduction,](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)Schutz der [nächsten Generation,](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) [EDR](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)und automatisierte Untersuchung [und Behebung](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) tragen dazu bei, Ihre Geräte vor Schadsoftware zu schützen. Zusätzlich zu diesen Funktionen können Kunden proaktive Benachrichtigungen erhalten und sich bei Bedarf an Microsoft-Bedrohungsexperten wenden, als Teil des Diensts für die verwaltete Suche bei der Anmeldung.

### <a name="set-up-microsoft-defender-for-endpoint"></a>Einrichten von Microsoft Defender für Endpunkt

![Prozess für die Bereitstellung von Microsoft Defender für Endpunkt](../media/deploy-threat-protection/deploy-mdatp-steps.png) 

1. [Bereiten Sie Ihre Umgebung für Microsoft Defender für Endpunkt](../security/defender-endpoint/deployment-phases.md)vor.
2. [Bereitstellen von Microsoft Defender für Endpunkt](../security/defender-endpoint/production-deployment.md).
3. [Onboarding in den Microsoft Defender für Endpunktdienst.](../security/defender-endpoint/onboarding.md)
4. [Führen Sie Die wichtigsten Verwaltungsaufgaben für die Sicherheit aus.](../security/defender-endpoint/tvm-security-recommendation.md)

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Weitere Informationen zu Microsoft Defender für Endpunkt

- [Erfahren Sie mehr über Microsoft Defender für Endpunkt.](../security/defender-endpoint/microsoft-defender-endpoint.md)
- [Testen Sie das Evaluierungslabor von Microsoft Defender für Endpunkt.](../security/defender-endpoint/evaluation-lab.md)

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Schritt 6: Konfigurieren Microsoft Cloud App Security

[Microsoft Cloud App Security](/cloud-app-security) ist ein Cloud Access Security Broker, der Protokollsammlung, API-Connectors und Reverseproxy unterstützt. Microsoft Cloud App Security bietet umfassende Sichtbarkeit, Kontrolle über datenbasierte Reisen und komplexe Analysen, um Cyberbedrohungen in allen Ihren Clouddiensten zu erkennen und zu bekämpfen. Mit Microsoft Cloud App Security können Ihre Sicherheitsvorgänge die vertraulichen Informationen Ihrer Organisation schützen, sich vor Cyberbedrohungen und Anomalien schützen, Apps ermitteln und überwachen, die auf die Daten Ihrer Organisation zugreifen, und sicherstellen, dass die Cloud-Apps Ihrer Organisation die Complianceanforderungen erfüllen.

### <a name="set-up-microsoft-cloud-app-security"></a>Einrichten Microsoft Cloud App Security

![Prozess für die Bereitstellung von Microsoft Cloud App Security](../media/deploy-threat-protection/deploy-mcas-steps.png) 

1. [Richten Sie das Portal und andere grundlegende Anforderungen ein.](/cloud-app-security/general-setup)
2. [Einrichten der Cloudermittlung](/cloud-app-security/set-up-cloud-discovery) und [Verbinden von Apps.](/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)
3. [Bereitstellen der App-Steuerung für bedingten Zugriff für ausgewählte Apps.](/cloud-app-security/proxy-deployment-aad)
4. [Verwenden Sie die Untersuchungstools und Dashboards.](/cloud-app-security/investigate)

### <a name="more-information-about-microsoft-cloud-app-security"></a>Weitere Informationen zu Microsoft Cloud App Security

- [Überprüfen Sie die neuen Features und Funktionen.](/cloud-app-security/release-notes)
- [Weitere Informationen zu Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security).

## <a name="step-7-monitor-status-and-take-actions"></a>Schritt 7: Überwachen des Status und Ausführen von Aktionen

Nachdem Sie Ihre Bedrohungsschutzdienste und -funktionen eingerichtet und bereitgestellt haben, besteht der nächste Schritt darin, die Bedrohungserkennung zu überwachen und entsprechende Maßnahmen zu ergreifen. Der beste Ausgangspunkt ist das Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ), in dem Sie die Sicherheit über Ihre Microsoft-Identitäten, Daten, Geräte, Apps und Infrastruktur hinweg überwachen und verwalten können.

![Microsoft 365 Security Center](../media/solutions-architecture-center/m365-security-center.png)

Das Microsoft 365 Security Center ist für Sicherheitsadministratoren und Sicherheitsteams vorgesehen. Im Microsoft 365 Security Center haben Sie folgende Möglichkeiten:

- Zeigen Sie den Gesamtsicherheitsstatus Ihrer Organisation mit [der Sicherheitsbewertung an.](/microsoft-365/security/defender/microsoft-secure-score)
- [Überwachen und Anzeigen](../security/defender-endpoint/threat-protection-reports.md) von Berichten über den Status Ihrer Identitäten, Daten, Geräte, Apps und Infrastruktur.
- Verbinden die Punkte für Warnungen durch [Vorfälle.](/microsoft-365/security/defender/incident-queue)
- Verwenden Sie [automatisierte Untersuchungen und Korrekturen,](../security/defender/m365d-autoir.md) um Bedrohungen zu beheben.
- [Proaktive Suche nach Bedrohungen,](/microsoft-365/security/defender/advanced-hunting-overview)z. B. Angriffsversuche oder Aktivitäten, die Sich auf Ihre E-Mails, Daten, Geräte und Identitäten auswirken.
- [Verstehen Sie die neuesten Angriffskampagnen](/microsoft-365/security/defender/latest-attack-campaigns) und -techniken mit bedrohungsanalysen.
- ... und mehr!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Weitere Informationen zum Microsoft 365 Security Center

- [Erste Schritte mit dem Microsoft 365 Security Center.](../security/defender/overview-security-center.md)
- [Überwachen und Anzeigen von Berichten.](../security/defender/overview-security-center.md)
- [Sehen Sie sich die Sicherheitsportale in Microsoft 365 an.](../security/defender/portals.md)

## <a name="step-8-train-users"></a>Schritt 8: Schulen von Benutzern

Schulungen für Benutzer können Ihren Benutzern und dem Sicherheitsteam viel Zeit und Frustration ersparen. Erfahrene Benutzer öffnen weniger Anlagen oder klicken auf Links in fraglichen E-Mail-Nachrichten, und sie vermeiden eher verdächtige Websites. 

Das [Cybersicherheitskampagnenhandbuch](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) der Schule Stellt hervorragende Anleitungen zum Aufbau einer starken Kultur des Sicherheitsbewusstseins in Ihrer Organisation bereit, einschließlich der Schulung von Benutzern zur Identifizierung von Phishingangriffen. 

Microsoft 365 bietet die folgenden Ressourcen, um Die Benutzer in Ihrer Organisation zu informieren:

<br>

****

|Konzept|Ressourcen|
|---|---|
|Microsoft 365|[Anpassbare Lernpfade](/office365/customlearning/) <p> Diese Ressourcen können Ihnen helfen, Schulungen für Endbenutzer in Ihrer Organisation zusammenzustellen.|
|Microsoft 365 Security|[Learning Modul: Sichern Ihrer Organisation mit integrierter, intelligenter Sicherheit vor Microsoft 365](/learn/modules/security-with-microsoft-365) <p> In diesem Modul können Sie beschreiben, wie Microsoft 365 Sicherheitsfeatures zusammenarbeiten und die Vorteile dieser Sicherheitsfeatures erläutern.|
|Mehrstufige Authentifizierung|[Zweistufige Überprüfung: Was ist die zusätzliche Überprüfungsseite?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p> Dieser Artikel hilft Endbenutzern zu verstehen, was die mehrstufige Authentifizierung ist und warum sie in Ihrer Organisation verwendet wird.|
|

Zusätzlich zu diesem Leitfaden empfiehlt Microsoft Ihren Benutzern, die in diesem Artikel beschriebenen Maßnahmen zu ergreifen: [Schützen Ihres Kontos und Ihrer Geräte vor Hackern und Schadsoftware.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) Diese setzen sich wie folgt zusammen:

- Verwenden sicherer Kennwörter
- Schützen von Geräten
- Aktivieren von Sicherheitsfeatures auf Windows 10 und Mac-PCs (für nicht verwaltete Geräte)

Microsoft empfiehlt außerdem, dass Benutzer ihre persönlichen E-Mail-Konten schützen, indem sie die in den folgenden Artikeln empfohlenen Maßnahmen ergreifen:

- [Schützen Ihres Outlook.com-E-Mail-Kontos](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Schützen Ihres Gmail-Kontos mit zweistufiger Überprüfung](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
