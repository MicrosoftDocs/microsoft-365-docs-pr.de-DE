---
title: Office 365 automatisierte Untersuchung und Antwort
keywords: Luft, autoIR, ATP, automatisiert, Untersuchung, Antwort, Behebung, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Erste Schritte mit automatisierten Ermittlungs-und Antwortfunktionen in Office 365 Advanced Threat Protection-Plan 2.
ms.openlocfilehash: 7bfa07880a302f77769ee15e9108db21dac2519c
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228567"
---
# <a name="office-365-automated-investigation-and-response"></a>Office 365 automatisierte Untersuchung und Antwort

[Office 365 Advanced Threat Protection](office-365-atp.md) Plan 2 enthält leistungsstarke Funktionen für die automatische Untersuchung und Reaktion (Air), mit denen Sie Zeit und Aufwand für Sicherheitsvorgänge speichern können. Wenn bestimmte Warnungen ausgelöst werden, werden ein oder mehrere Sicherheits-Textbuch initiiert, und der automatische Ermittlungsprozess wird gestartet. Dadurch können sich Ihre Sicherheits Betriebsteams auf Aufgaben mit hoher Priorität konzentrieren, ohne ausgelöste Warnungen aus den Augen zu verlieren. 

Auf hohem Niveau funktioniert der Luftstrom wie folgt:

|Schritt  |Aktionen  |
|---------|---------|
|1     |Eine Warnung wird von einem Office-Ereignis ausgelöst, und ein [Sicherheits](automated-investigation-response-office.md#security-playbooks) -Textbuch initiiert eine automatisierte Untersuchung für ausgewählte Warnungen. <br/><br/>Alternativ kann ein Sicherheitsanalyst [eine automatisierte Untersuchung](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) bei Verwendung von [Threat Explorer](threat-explorer.md)auslösen.        |
|2     |Während eine automatisierte Untersuchung ausgeführt wird, sammelt Sie zusätzliche Daten über die e-Mail und die Entitäten im Zusammenhang mit dieser e-Mail – Dateien, URLs und Empfänger.  Der Bereich der Untersuchung kann zunehmen, wenn neue zugehörige Warnungen ausgelöst werden.         |
|3     |Während und nach einer automatisierten Untersuchung stehen [Details und Ergebnisse](air-view-investigation-results.md) zur Verfügung, die angezeigt werden können. Die Ergebnisse umfassen [Empfohlene Aktionen](air-remediation-actions.md) , die ergriffen werden können, um alle gefundenen Bedrohungen zu reagieren und zu beheben. Darüber hinaus steht ein Textbuch- [Protokoll](air-view-investigation-results.md#playbook-log) zur Verfügung, das alle Ermittlungsaktivitäten aufspürt.<br/><br/>Wenn Ihre Organisation eine benutzerdefinierte Berichtslösung oder eine Drittanbieterlösung verwendet, können Sie [die API für die Office 365 Verwaltungsaktivität verwenden](air-custom-reporting.md) , um Informationen zu automatisierten Untersuchungen und Bedrohungen anzuzeigen.         |
|4     |Ihr Security Operations-Team überprüft die [Untersuchungsergebnisse und Empfehlungen](air-view-investigation-results.md)und [genehmigt Korrekturaktionen](air-remediation-actions.md#approve-or-reject-pending-actions). In Office 365 werden keine Aktionen automatisch durchgeführt. Korrekturaktionen werden nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt.         |

Während und nach einem automatisierten Ermittlungsprozess kann Ihr Sicherheitsteam folgende Aufgaben ausführen:

- [Anzeigen von Details zu einer Warnung im Zusammenhang mit einer Untersuchung](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Anzeigen der Ergebnisdetails einer Untersuchung](air-view-investigation-results.md#view-details-of-an-investigation)
- [Überprüfen und Genehmigen von Aktionen als Ergebnis einer Untersuchung](air-remediation-actions.md#approve-or-reject-pending-actions)

Weitere Informationen finden Sie unter [Funktionsweise von Air](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>So erhalten Sie Luft

Office 365 AIR ist in den folgenden Abonnements enthalten:

- Microsoft 365 E5
- Office 365 E5
- Microsoft Threat Protection
- Office 365 Advanced Threat Protection Plan 2

Wenn Sie keines dieser Abonnements haben, [Starten Sie eine ﻿kostenlose Testversion](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US).

Weitere Informationen zur Verfügbarkeit von Features finden Sie unter [Verfügbarkeit von Features über erweiterte Threat Protection (ATP)-Pläne](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="required-permissions-to-use-air-capabilities"></a>Erforderliche Berechtigungen für die Verwendung von Air-Funktionen

Berechtigungen werden über bestimmte Rollen erteilt, wie Sie in der folgenden Tabelle beschrieben werden: 

|Aufgabe |Erforderliche Rolle (n) |
|--|--|
|So richten Sie Air-Features ein |Eine der folgenden Rollen: <br/>- **Globaler Administrator**<br/>- **Sicherheits Administrator** <br/>Diese Rollen können in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) oder im [Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)zugewiesen werden. |
|So genehmigen oder ablehnen Sie Empfohlene Aktionen|Eine der folgenden Rollen, die in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) oder im [Compliance Center von Office 365 Security &](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)) zugewiesen ist:<br/>- **Globaler Administrator** <br/>- **Sicherheits Administrator**<br/>- **Sicherheits Leser** <br/>--- und ---<br/>- **Suchen und löschen** (diese Rolle wird nur im [Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)zugewiesen. Möglicherweise müssen Sie dort eine neue Rollengruppe erstellen und die Such-und Lösch Rolle dieser neuen Rollengruppe hinzufügen.)

## <a name="related-articles"></a>Verwandte Artikel

- [Automatische Untersuchung und Reaktion in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

- [Automatische Untersuchung und Korrektur in Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)