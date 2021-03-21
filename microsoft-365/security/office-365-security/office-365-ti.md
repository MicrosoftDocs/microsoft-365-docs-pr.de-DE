---
title: Bedrohungsuntersuchung & Reaktionsfunktionen – Microsoft Defender für Office 365 Plan 2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie mehr über Die Untersuchungs- und Reaktionsfunktionen von Bedrohungen in Microsoft Defender for Office 365 Plan.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef8c445a5a234bdfaaae00824e7ab39dc3f51c26
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926772"
---
# <a name="threat-investigation-and-response"></a>Untersuchung von und Antwort auf Bedrohungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](office-365-atp.md)


Bedrohungsuntersuchungs- und Reaktionsfunktionen in [Microsoft Defender for Office 365](office-365-atp.md) helfen Sicherheitsanalysten und Administratoren beim Schutz der Microsoft 365 for Business-Benutzer ihrer Organisation durch:

- Einfaches Erkennen, Überwachen und Verstehen von Cyberangriffen
- Schnelles Reagieren auf Bedrohungen in Exchange Online, SharePoint Online, OneDrive for Business und Microsoft Teams
- Bereitstellen von Einblicken und Wissen, um Sicherheitsvorgängen zu helfen, Cyberangriffe auf ihre Organisation zu verhindern
- Verwenden einer [automatisierten Untersuchung und Reaktion in Office 365](automated-investigation-response-office.md) für kritische E-Mail-basierte Bedrohungen

Funktionen zur Untersuchung und Reaktion auf Bedrohungen bieten Einblicke in Bedrohungen und zugehörige Reaktionsaktionen, die im Security & Compliance Center verfügbar sind. Diese Erkenntnisse können dem Sicherheitsteam Ihrer Organisation helfen, Benutzer vor E-Mail- oder dateibasierten Angriffen zu schützen. Die Funktionen helfen dabei, Signale zu überwachen und Daten aus mehreren Quellen zu sammeln, z. B. Benutzeraktivitäten, Authentifizierung, E-Mails, gefährdete PCs und Sicherheitsvorfälle. Entscheidungsträger und Ihr Sicherheitsteam können diese Informationen verwenden, um Bedrohungen gegen Ihre Organisation zu verstehen und darauf zu reagieren und Ihr geistiges Eigentum zu schützen.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Machen Sie sich mit Tools zur Untersuchung und Reaktion auf Bedrohungen vertraut

Bedrohungsuntersuchungs- und Reaktionsfunktionen werden im Security & Compliance Center als eine Reihe von Tools und Reaktionsworkflows, einschließlich der folgenden, zur Verfügung stehen:

- [Bedrohungsdashboard](#threat-dashboard)
- [Explorer](#threat-explorer)
- [Vorfälle](#incidents)
- [Angriffssimulator](#attack-simulator)
- [Automatische Untersuchung und Reaktion](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a>Bedrohungsdashboard

Verwenden Sie das Bedrohungsdashboard (dies wird auch als Sicherheitsdashboard bezeichnet), um schnell zu sehen, welche Bedrohungen behoben wurden, und um Entscheidungsträgern in Unternehmen zu zeigen, wie Microsoft 365-Dienste Ihr Unternehmen schützen. [](security-dashboard.md)

![Bedrohungsdashboard](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

Um dieses Dashboard anzuzeigen und zu verwenden, wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Dashboard**.

### <a name="threat-explorer"></a>Sicherheitsrisiken-Explorer

Verwenden [Sie Den Bedrohungs-Explorer (und](threat-explorer.md) Echtzeiterkennungen), um Bedrohungen zu analysieren, die Anzahl der Angriffe im Laufe der Zeit zu sehen und Daten nach Bedrohungsfamilien, Angreiferinfrastrukturen und vielem mehr zu analysieren. Der Bedrohungs-Explorer (auch explorer genannt) ist der Ausgangspunkt für den Untersuchungsworkflow jedes Sicherheitsanalysten.

![Bedrohungs-Explorer](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

Wenn Sie diesen Bericht anzeigen und verwenden möchten, wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Explorer**.

### <a name="incidents"></a>Vorfälle

Verwenden Sie die Liste Vorfälle (dies wird auch als Untersuchungen bezeichnet), um eine Liste der Sicherheitsvorfälle in Flight zu sehen. Vorfälle werden verwendet, um Bedrohungen wie verdächtige E-Mail-Nachrichten nachverfolgt und weitere Untersuchungen und Korrekturen durchführen zu können.

![Liste der aktuellen Bedrohungsvorfälle in Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

Wenn Sie die Liste der aktuellen Vorfälle für Ihre Organisation anzeigen möchten, wechseln Sie im Security & Compliance Center zu Threat **Management** \> **Review** \> **Incidents**.

![Wählen Sie im Security & Compliance Center die Option Bedrohungsverwaltung \> überprüfen aus.](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a>Angriffssimulator

Verwenden Sie den Angriffssimulator, um realistische Cyberangriffe in Ihrer Organisation zu einrichten und ausführen und anfällige Personen zu identifizieren, bevor ein tatsächlicher Cyberangriff Ihr Unternehmen betrifft. Weitere Informationen finden Sie unter [Attack Simulator in Office 365](attack-simulator.md).

### <a name="automated-investigation-and-response"></a>Automatische Untersuchung und Reaktion

Verwenden Sie automatisierte Untersuchungs- und Reaktionsfunktionen (AIR), um Zeit und Aufwand für die Korrelierung von Inhalten, Geräten und Personen zu sparen, die durch Bedrohungen in Ihrer Organisation gefährdet sind. AIR-Prozesse können beginnen, wenn bestimmte Warnungen ausgelöst werden oder wenn sie vom Sicherheitsbetriebsteam gestartet werden. Weitere Informationen finden Sie unter [automatisierte Untersuchung und Reaktion in Office 365](automated-investigation-response-office.md).

## <a name="threat-intelligence-widgets"></a>Widgets für Die Bedrohungsintelligenz

Im Rahmen des Microsoft Defender for Office 365 Plan 2-Angebots können Sicherheitsanalysten Details zu einer bekannten Bedrohung überprüfen. Dies ist hilfreich, um festzustellen, ob zusätzliche vorbeugende Maßnahmen/Schritte ergriffen werden können, um benutzersicher zu halten.

![Sicherheitstrends mit Informationen zu aktuellen Bedrohungen](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a>Wie erhalten wir diese Funktionen?

Microsoft 365 Threat Investigation and Response capabilities are included in Microsoft Defender for Office 365 Plan 2, which is included in Enterprise E5 or as an add-on to certain subscriptions. Weitere Informationen finden Sie unter [Defender for Office 365 Plan 1 und Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2).

## <a name="required-roles-and-permissions"></a>Erforderliche Rollen und Berechtigungen

Microsoft Defender für Office 365 verwendet die rollenbasierte Zugriffssteuerung. Berechtigungen werden über bestimmte Rollen in Azure Active Directory, im Microsoft 365 Admin Center oder im Security & Compliance Center zugewiesen.

> [!TIP]
> Obwohl einige Rollen, z. B. Sicherheitsadministrator, im Security & Compliance Center zugewiesen werden können, sollten Sie stattdessen entweder das Microsoft 365 Admin Center oder Azure Active Directory verwenden. Informationen zu Rollen, Rollengruppen und Berechtigungen finden Sie in den folgenden Ressourcen:
>
> - [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)
>
> - [Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|Aktivität|Rollen und Berechtigungen|
|---|---|
|Verwenden des Bedrohungsdashboards (oder des neuen [Sicherheitsdashboards)](security-dashboard.md) <p> Anzeigen von Informationen zu aktuellen oder aktuellen Bedrohungen|Eine der folgenden Varianten: <ul><li>**Globaler Administrator**</li><li>**Sicherheitsadministrator**</li><li>**Security Reader**</li></ul> <p> Diese Rollen können entweder in Azure Active Directory ( <https://portal.azure.com> ) oder im Microsoft 365 Admin Center ( ) zugewiesen <https://admin.microsoft.com> werden.|
|Verwenden [von Bedrohungs-Explorer (und Echtzeiterkennungen) zum](threat-explorer.md) Analysieren von Bedrohungen|Eine der folgenden Varianten: <ul><li>**Globaler Administrator**</li><li>**Sicherheitsadministrator**</li><li>**Security Reader**</li></ul> <p> Diese Rollen können entweder in Azure Active Directory ( <https://portal.azure.com> ) oder im Microsoft 365 Admin Center ( ) zugewiesen <https://admin.microsoft.com> werden.|
|Anzeigen von Vorfällen (auch als Investigations bezeichnet) <p> Hinzufügen von E-Mail-Nachrichten zu einem Vorfall|Eine der folgenden Varianten: <ul><li>**Globaler Administrator**</li><li>**Sicherheitsadministrator**</li><li>**Security Reader**</li></ul> <p> Diese Rollen können entweder in Azure Active Directory ( <https://portal.azure.com> ) oder im Microsoft 365 Admin Center ( ) zugewiesen <https://admin.microsoft.com> werden.|
|Auslösen von E-Mail-Aktionen in einem Vorfall <p> Suchen und Löschen verdächtiger E-Mail-Nachrichten|Eine der folgenden Varianten: <ul><li>**Globaler Administrator**</li><li>**Sicherheitsadministrator** plus die **Rolle Suchen und Löschen**</li></ul> <p> Die **Rollen globaler Administrator** und **Sicherheitsadministrator** können entweder in Azure Active Directory ( ) oder im <https://portal.azure.com> Microsoft 365 Admin Center ( ) zugewiesen <https://admin.microsoft.com> werden. <p> Die **Rolle Suchen und** Löschen muss im Security & Compliance Center ( ) zugewiesen <https://protection.office.com> werden.|
|Integrieren von Microsoft Defender für Office 365 Plan 2 in Microsoft Defender for Endpoint  <p> Integrieren von Microsoft Defender für Office 365 Plan 2 in einen SIEM-Server|Entweder der globale  **Administrator oder** die Sicherheitsadministratorrolle, die entweder in Azure Active Directory ( ) oder im <https://portal.azure.com> Microsoft 365 Admin Center ( ) zugewiesen <https://admin.microsoft.com> ist. <p> --- **plus** --- <p> Eine geeignete Rolle, die in zusätzlichen Anwendungen (z. B. [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/user-roles) oder Ihrem SIEM-Server) zugewiesen ist.|
|

## <a name="next-steps"></a>Nächste Schritte

- [Erfahren Sie mehr über Threat Trackers – Neu und Beachtenswert](threat-trackers.md)

- [Suchen und Untersuchen bösartiger E-Mails, die zugestellt wurden (Office 365 Threat Investigation and Response)](investigate-malicious-email-that-was-delivered.md)

- [Integrieren von Office 365 Threat Investigation and Response in Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md)

- [Informationen zum Angriffssimulator](attack-simulator.md)