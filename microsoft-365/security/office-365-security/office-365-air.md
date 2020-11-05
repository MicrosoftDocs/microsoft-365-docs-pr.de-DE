---
title: Erste Schritte mit der automatisierten Untersuchung und Antwort in Microsoft Defender für Office 365
keywords: Luft, autoIR, ATP, automatisiert, Untersuchung, Antwort, Behebung, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/04/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Erste Schritte mit automatisierten Ermittlungs-und Antwortfunktionen in Microsoft Defender für Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 7e9b786a9d00a34f5e2e88a8481e82fa8425a501
ms.sourcegitcommit: 751dc531f0410ee075c179efe409a01664483ee2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925604"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Erste Schritte mit der automatisierten Untersuchung und Antwort (Air) in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender für Office 365](office-365-atp.md) enthält leistungsstarke Funktionen für die automatische Untersuchung und Reaktion (Air), mit denen Sie Zeit und Aufwand für Sicherheitsvorgänge aufsparen können. Wenn Warnungen ausgelöst werden, liegt es an Ihrem Sicherheits Betriebsteam, diese Warnungen zu überprüfen, zu priorisieren und darauf zu reagieren. Das Einhalten des Umfangs eingehender Warnungen kann überwältigend sein. Das Automatisieren einiger dieser Aufgaben kann helfen. Mit Air kann sich Ihr Sicherheits Betriebsteam auf Aufgaben mit höherer Priorität konzentrieren, ohne wichtige ausgelöste Warnungen aus den Augen zu verlieren.

Inhalt dieses Artikels
- Der [gesamte Luftstrom](#the-overall-flow-of-air);
- [Gewusst wie: Abrufen von Luft](#how-to-get-air); und 
- Die [erforderlichen Berechtigungen](#required-permissions-to-use-air-capabilities) zum Konfigurieren oder Verwenden von Air-Funktionen. 

## <a name="the-overall-flow-of-air"></a>Der gesamte Luftstrom

Eine Warnung wird ausgelöst, und ein Sicherheits-Textbuch startet eine automatisierte Untersuchung, die Ergebnisse und empfohlene Aktionen zur Folge hat. Hier ist der Gesamtfluss der Luft, Schritt für Schritt:

1. Eine automatisierte Untersuchung wird auf eine der folgenden Arten eingeleitet:

   - Eine [Warnung](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) wird durch etwas Verdächtiges in e-Mails ausgelöst (beispielsweise eine Nachricht, Anlage oder URL). Ein Vorfall wird erstellt. Je nach Art des Vorfalls wird ein [Sicherheits](automated-investigation-response-office.md#security-playbooks) Textbuch ausgeführt, und eine automatische Untersuchung wird gestartet. 

     --- oder ---
   
   - Ein Security Analyst [startet eine automatisierte Untersuchung](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) während der Verwendung von [Threat Explorer](threat-explorer.md).

2. Während eine automatisierte Untersuchung ausgeführt wird, sammelt Sie zusätzliche Daten über die fraglichen e-Mails und Entitäten im Zusammenhang mit dieser e-Mail. Solche Entitäten können Dateien, URLs und Empfänger umfassen.  Der Bereich der Untersuchung kann zunehmen, wenn neue und Verwandte Warnungen ausgelöst werden.

3. Während und nach einer automatisierten Untersuchung stehen [Details und Ergebnisse](air-view-investigation-results.md) zur Verfügung, die angezeigt werden können. Die Ergebnisse umfassen [Empfohlene Aktionen](air-remediation-actions.md) , die ergriffen werden können, um auf gefundene Bedrohungen zu reagieren und diese zu beheben. Darüber hinaus steht ein Textbuch- [Protokoll](air-view-investigation-results.md#playbook-log) zur Verfügung, das alle Ermittlungsaktivitäten aufspürt.


4. Ihr Sicherheits Betriebsteam überprüft die [Ergebnisse und Empfehlungen der Untersuchung](air-view-investigation-results.md)und [genehmigt oder lehnt Korrekturaktionen](air-review-approve-pending-completed-actions.md)ab. 

5. Wenn ausstehende Korrekturaktionen genehmigt (oder abgelehnt) werden, wird die automatische Untersuchung abgeschlossen.

> [!IMPORTANT]
> In Microsoft Defender für Office 365 werden keine Korrekturaktionen automatisch durchgeführt. Abhilfemaßnahmen werden nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt. Air-Funktionen speichern jedoch die Team Zeit für Sicherheitsvorgänge, indem Sie Korrekturaktionen identifizieren und die erforderlichen Details für eine fundierte Entscheidung bereitstellen.

Während und nach jeder automatischen Untersuchung kann Ihr Sicherheits Betriebsteam folgende Aufgaben ausführen:

- [Anzeigen von Details zu einer Warnung im Zusammenhang mit einer Untersuchung](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Anzeigen der Ergebnisdetails einer Untersuchung](air-view-investigation-results.md#view-details-of-an-investigation)

- [Überprüfen und Genehmigen von Aktionen als Ergebnis einer Untersuchung](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Eine ausführlichere Übersicht finden Sie unter [How Air Works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>So erhalten Sie Luft

Air-Funktionen sind in [Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)enthalten, vorausgesetzt, Ihre Richtlinien und Warnungen sind konfiguriert. Wenn Sie Hilfe bei dieser Vorgehensweise wünschen, befolgen Sie die Anweisungen unter [Protect Against Threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) , um die folgenden Schutzeinstellungen einzurichten oder zu konfigurieren: 

1. [Überwachungsprotokollierung](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (sollte aktiviert sein)

2. [Richtlinien für Antischadsoftware](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-1---anti-malware-protection)

3. [Schutz vor Phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
   
4. [Antispam-Schutz](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection).
   
5. [Sichere Links und sichere Anlagen](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).
   
6. [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).
   
7. [Automatische Bereinigung ohne Stunden für e-Mail](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop).

Stellen Sie außerdem sicher, dass Sie die [Warnungsrichtlinien Ihrer Organisation](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), insbesondere die [Standardrichtlinien in der Kategorie "Threat Management](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)", überprüfen. 

## <a name="which-alert-policies-trigger-automated-investigations"></a>Welche Warnungsrichtlinien lösen automatisierte Untersuchungen aus?

Microsoft 365 bietet zahlreiche integrierte Warnungsrichtlinien, die die Identifizierung von Exchange-Administratorberechtigungen, Malwareaktivitäten, potenziellen externen und internen Bedrohungen sowie Risiken bei der Informationssteuerung ermöglichen. Mehrere der [standardmäßigen Warnungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) können automatisierte Untersuchungen auslösen. Hierzu gehören:

- Es wurde ein potenziell böswilliger URL-Klick erkannt
- Eine e-Mail-Nachricht wird von einem Benutzer als Phishing gemeldet.
- E-Mail-Nachrichten mit Schadsoftware werden nach der Zustellung entfernt
- E-Mail-Nachrichten mit Phishing-URLs werden nach der Zustellung entfernt
- Verdächtige e-Mail-Sende Muster werden erkannt
- Ein Benutzer wird vom Senden von e-Mails eingeschränkt.

## <a name="required-permissions-to-use-air-capabilities"></a>Erforderliche Berechtigungen für die Verwendung von Air-Funktionen

Berechtigungen werden über bestimmte Rollen erteilt, wie Sie in der folgenden Tabelle beschrieben werden: 

|Aufgabe |Erforderliche Rolle (n) |
|--|--|
|So richten Sie Air-Features ein |Eine der folgenden Rollen: <br/>-Globaler Administrator<br/>-Sicherheits Administrator <br/>Diese Rollen können in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) oder im [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)zugewiesen werden. |
|So genehmigen oder ablehnen Sie Empfohlene Aktionen|Eine der folgenden Rollen, die in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) oder im [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)zugewiesen ist):<br/>-Globaler Administrator <br/>-Sicherheits Administrator<br/>-Sicherheits Leser <br/>--- und ---<br/>-Suchen und löschen (diese Rolle wird nur im [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)zugewiesen. Möglicherweise müssen Sie dort eine neue Rollengruppe erstellen und die Such-und Lösch Rolle dieser neuen Rollengruppe hinzufügen.)

## <a name="required-licenses"></a>Erforderliche Lizenzen

[Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) -Lizenzen sollte Folgendes zugewiesen werden:
- Sicherheitsadministratoren (einschließlich globaler Administratoren)
- Das Sicherheits Betriebsteam Ihrer Organisation (einschließlich Sicherheits Lesern und Benutzern mit der Rolle "suchen und löschen")
- Endbenutzer


## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Überprüfen und genehmigen ausstehender Aktionen](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Verwandte Artikel

- [Automatische Untersuchung und Korrektur in Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Automatische Untersuchung und Antwort in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
