---
title: Automatische Untersuchung und Reaktion (Air) – erste Schritte
keywords: Luft, autoIR, ATP, automatisiert, Untersuchung, Antwort, Behebung, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 09/29/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Erste Schritte mit automatisierten Ermittlungs-und Antwortfunktionen in Microsoft Defender für Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: b844e4817bc77d7f6f4e99df53fc4b14c7e7110c
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308887"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a>Erste Schritte mit der automatisierten Untersuchung und Reaktion (Air) in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender für Office 365](office-365-atp.md) enthält leistungsstarke Funktionen für die automatische Untersuchung und Reaktion (Air), mit denen Sie Zeit und Aufwand für Sicherheitsvorgänge aufsparen können. Wenn Warnungen ausgelöst werden, liegt es an Ihrem Sicherheits Betriebsteam, diese Warnungen zu überprüfen, zu priorisieren und darauf zu reagieren. Das Einhalten des Umfangs eingehender Warnungen kann überwältigend sein. Die Automatisierung einiger dieser Informationen kann helfen. Mit Air kann sich Ihr Sicherheits Betriebsteam auf Aufgaben mit höherer Priorität konzentrieren, ohne die ausgelösten Warnungen aus den Augen zu verlieren.

Inhalt dieses Artikels:
- Der [gesamte Luftstrom](#the-overall-flow-of-air) ;
- [Gewusst wie: Abrufen von Luft](#how-to-get-air); und 
- Die [erforderlichen Berechtigungen](#required-permissions-to-use-air-capabilities) zum Konfigurieren oder Verwenden von Air-Funktionen. 

## <a name="the-overall-flow-of-air"></a>Der gesamte Luftstrom

Auf einer hohen Ebene wird eine Warnung ausgelöst, und ein Sicherheits Textbuch startet eine automatisierte Untersuchung, die Ergebnisse und Empfehlungen ergibt. Hier ist der Gesamtfluss der Luft, Schritt für Schritt:

1. Eine automatisierte Untersuchung wird auf eine der folgenden Arten eingeleitet:

   - Eine [Warnung](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) wird von einem Office-Ereignis ausgelöst, das einen Vorfall verursacht. Je nach Art des Vorfalls startet ein [Sicherheits](automated-investigation-response-office.md#security-playbooks) -Textbuch eine automatisierte Untersuchung. 

     --- oder ---
   
   - Ein Security Analyst [startet eine automatisierte Untersuchung](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) während der Verwendung von [Threat Explorer](threat-explorer.md).

2. Während eine automatisierte Untersuchung ausgeführt wird, sammelt Sie zusätzliche Daten über die fraglichen e-Mails und Entitäten im Zusammenhang mit dieser e-Mail. Solche Entitäten können Dateien, URLs und Empfänger umfassen.  Der Bereich der Untersuchung kann zunehmen, wenn neue und Verwandte Warnungen ausgelöst werden.

3. Während und nach einer automatisierten Untersuchung stehen [Details und Ergebnisse](air-view-investigation-results.md) zur Verfügung, die angezeigt werden können. Die Ergebnisse umfassen [Empfohlene Aktionen](air-remediation-actions.md) , die ergriffen werden können, um alle gefundenen Bedrohungen zu reagieren und zu beheben. Darüber hinaus steht ein Textbuch- [Protokoll](air-view-investigation-results.md#playbook-log) zur Verfügung, das alle Ermittlungsaktivitäten aufspürt.

    Wenn Ihre Organisation eine benutzerdefinierte Berichtslösung oder eine Drittanbieterlösung verwendet, können Sie [die API für die Office 365 Verwaltungsaktivität verwenden](air-custom-reporting.md) , um Informationen zu automatisierten Untersuchungen und Bedrohungen anzuzeigen.

4. Ihr Sicherheits Betriebsteam überprüft die [Ergebnisse und Empfehlungen der Untersuchung](air-view-investigation-results.md)und [genehmigt oder lehnt Korrekturaktionen](air-review-approve-pending-completed-actions.md)ab. 

    Wenn ausstehende Korrekturaktionen genehmigt (oder abgelehnt) werden, wird die automatische Untersuchung abgeschlossen.

> [!NOTE]
> In Office 365 ATP werden keine Korrekturaktionen automatisch durchgeführt. Abhilfemaßnahmen werden nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt. 

Während und nach einem automatisierten Ermittlungsprozess kann Ihr Sicherheitsteam folgende Aufgaben ausführen:

- [Anzeigen von Details zu einer Warnung im Zusammenhang mit einer Untersuchung](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Anzeigen der Ergebnisdetails einer Untersuchung](air-view-investigation-results.md#view-details-of-an-investigation)

- [Überprüfen und Genehmigen von Aktionen als Ergebnis einer Untersuchung](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Weitere Informationen finden Sie unter [Funktionsweise von Air](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>So erhalten Sie Luft

Air-Funktionen sind in [Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)enthalten. Ihre [Richtlinien müssen jedoch so konfiguriert werden](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) , dass die Luft wie erwartet funktioniert. Stellen Sie außerdem sicher, dass Sie die [Warnungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)Ihrer Organisation überprüfen und möglicherweise konfigurieren. 

Microsoft 365 bietet zahlreiche integrierte Warnungsrichtlinien, die die Identifizierung von Exchange-Administratorberechtigungen, Malwareaktivitäten, potenziellen externen und internen Bedrohungen sowie Risiken bei der Informationssteuerung ermöglichen. Mehrere der [standardmäßigen Warnungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) können automatisierte Untersuchungen auslösen. Hierzu gehören:

- Es wurde ein potenziell böswilliger URL-Klick erkannt

- Eine e-Mail-Nachricht wird von einem Benutzer als Phishing gemeldet.

- E-Mail-Nachrichten mit Schadsoftware werden nach der Zustellung entfernt

- E-Mail-Nachrichten mit Phishing-URLs werden nach der Zustellung entfernt

- Verdächtige e-Mail-Sende Muster werden erkannt

- Ein Benutzer wird vom Senden von e-Mails eingeschränkt.

[Erfahren Sie mehr über Alerts und Air](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="required-permissions-to-use-air-capabilities"></a>Erforderliche Berechtigungen für die Verwendung von Air-Funktionen

Berechtigungen werden über bestimmte Rollen erteilt, wie Sie in der folgenden Tabelle beschrieben werden: 

|Aufgabe |Erforderliche Rolle (n) |
|--|--|
|So richten Sie Air-Features ein |Eine der folgenden Rollen: <br/>-Globaler Administrator<br/>-Sicherheits Administrator <br/>Diese Rollen können in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) oder im [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)zugewiesen werden. |
|So genehmigen oder ablehnen Sie Empfohlene Aktionen|Eine der folgenden Rollen, die in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) oder im [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)zugewiesen ist):<br/>-Globaler Administrator <br/>-Sicherheits Administrator<br/>-Sicherheits Leser <br/>--- und ---<br/>-Suchen und löschen (diese Rolle wird nur im [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)zugewiesen. Möglicherweise müssen Sie dort eine neue Rollengruppe erstellen und die Such-und Lösch Rolle dieser neuen Rollengruppe hinzufügen.)

[Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) -Lizenzen sollte Folgendes zugewiesen werden:
- Sicherheitsadministratoren (einschließlich globaler Administratoren)
- Das Sicherheits Betriebsteam Ihrer Organisation (einschließlich Sicherheits Lesern und Benutzern mit der Rolle "suchen und löschen")
- Endbenutzer

Darüber hinaus müssen [Microsoft Defender für Office 365-Richtlinien](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) definiert und angewendet werden, damit der Schutz in Kraft tritt.

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Überprüfen und genehmigen ausstehender Aktionen](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Verwandte Artikel

- [Automatische Untersuchung und Korrektur in Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Automatische Untersuchung und Antwort in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
