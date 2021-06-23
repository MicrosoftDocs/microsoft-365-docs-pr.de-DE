---
title: Reaktionsfunktionen für die Bedrohungsuntersuchung & – Microsoft Defender für Office 365 Plan 2
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
description: Erfahren Sie mehr über die Funktionen zur Untersuchung und Reaktion auf Bedrohungen in Microsoft Defender für Office 365 Plan.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0a9ff9c06f7e97d6f74c901c156bfae6c9eb91d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083704"
---
# <a name="threat-investigation-and-response"></a>Untersuchung von und Antwort auf Bedrohungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)


Die Funktionen zur Untersuchung und Reaktion auf Bedrohungen in [Microsoft Defender für Office 365](defender-for-office-365.md) Sicherheitsanalysten und Administratoren dabei helfen, die Microsoft 365 ihrer Organisation für Geschäftsbenutzer zu schützen:

- Einfaches Erkennen, Überwachen und Verstehen von Cyberangriffen
- Schnelles Reagieren auf Bedrohungen in Exchange Online, SharePoint Online, OneDrive for Business und Microsoft Teams
- Bereitstellen von Einblicken und Wissen, um Sicherheitsvorgängen zu helfen, Cyberangriffe auf ihre Organisation zu verhindern
- Verwenden [der automatisierten Untersuchung und Reaktion in Office 365](automated-investigation-response-office.md) für kritische E-Mail-basierte Bedrohungen

Die Funktionen zur Bedrohungsuntersuchung und -reaktion bieten Einblicke in Bedrohungen und zugehörige Reaktionsaktionen, die im Microsoft 365 Defender Portal verfügbar sind. Diese Erkenntnisse können dem Sicherheitsteam Ihrer Organisation helfen, Benutzer vor E-Mail- oder dateibasierten Angriffen zu schützen. Die Funktionen helfen beim Überwachen von Signalen und Sammeln von Daten aus mehreren Quellen, z. B. Benutzeraktivität, Authentifizierung, E-Mail, kompromittierte PCs und Sicherheitsvorfälle. Entscheidungsträger in Unternehmen und Ihr Sicherheitsteam können diese Informationen verwenden, um Bedrohungen gegen Ihre Organisation zu verstehen und darauf zu reagieren und Ihr geistiges Eigentum zu schützen.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Machen Sie sich mit Tools zur Bedrohungsuntersuchung und -reaktion vertraut

Die Funktionen für die Untersuchung und Reaktion auf Bedrohungen werden im Microsoft 365 Defender Portal als eine Reihe von Tools und Reaktionsworkflows angezeigt, einschließlich der folgenden:

- [Explorer](#explorer)
- [Vorfälle](#incidents)
- [Angriffssimulationstraining](attack-simulation-training.md)
- [Automatische Untersuchung und Reaktion](automated-investigation-response-office.md)

### <a name="explorer"></a>Explorer

Verwenden Sie [Explorer (und Echtzeiterkennungen),](threat-explorer.md) um Bedrohungen zu analysieren, das Volumen von Angriffen im Laufe der Zeit anzuzeigen und Daten nach Bedrohungsfamilien, Angreiferinfrastruktur und mehr zu analysieren. Der Explorer (auch als Bedrohungs-Explorer bezeichnet) ist der Ausgangspunkt für den Untersuchungsworkflow eines Sicherheitsanalysten.

![Bedrohungs-Explorer](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

Um diesen Bericht anzuzeigen und zu verwenden, wechseln Sie im Microsoft 365 Defender Portal zu **E-Mail & Zusammenarbeits-Explorer.**  >  

### <a name="incidents"></a>Vorfälle

Verwenden Sie die Liste "Vorfälle" (dies wird auch als "Untersuchungen" bezeichnet), um eine Liste von Sicherheitsvorfällen im Test-Flight anzuzeigen. Vorfälle werden verwendet, um Bedrohungen wie verdächtige E-Mail-Nachrichten nachzuverfolgen und weitere Untersuchungen und Korrekturen durchzuführen.

![Liste der aktuellen Bedrohungsvorfälle in Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

Um die Liste der aktuellen Vorfälle für Ihre Organisation anzuzeigen, wechseln Sie im portal Microsoft 365 Defender zu **Vorfällen &**  >  **Warnungen.**

![Wählen Sie im Security & Compliance Center die Bedrohungsverwaltungsprüfung aus. \>](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulation-training"></a>Angriffssimulationstraining

Verwenden Sie Angriffssimulationsschulungen, um realistische Cyberangriffe in Ihrer Organisation einzurichten und auszuführen, und identifizieren Sie anfällige Personen, bevor sich ein tatsächlicher Cyberangriff auf Ihr Unternehmen auswirkt. Weitere Informationen finden Sie unter [Simulieren eines Phishingangriffs.](attack-simulation-training.md)

Um dieses Feature im Microsoft 365 Defender Portal anzuzeigen und zu verwenden, wechseln Sie zu **E-Mail &**  >  **Angriffssimulationstraining** für die Zusammenarbeit.

### <a name="automated-investigation-and-response"></a>Automatisierte Untersuchung und Antwort (AIR)

Verwenden Sie air-Funktionen (Automated Investigation and Response), um Zeit und Mühe bei der Korrelation von Inhalten, Geräten und Personen zu sparen, die durch Bedrohungen in Ihrer Organisation gefährdet sind. AIR-Prozesse können immer dann beginnen, wenn bestimmte Warnungen ausgelöst werden oder wenn sie von Ihrem Sicherheitsteam gestartet werden. Weitere Informationen finden Sie [in der automatisierten Untersuchung und Reaktion in Office 365.](automated-investigation-response-office.md)

## <a name="threat-intelligence-widgets"></a>Widgets für die Bedrohungserkennung

Im Rahmen des Microsoft Defender für Office 365 Plan 2-Angebots können Sicherheitsanalysten Details zu einer bekannten Bedrohung überprüfen. Dies ist hilfreich, um festzustellen, ob es zusätzliche vorbeugende Maßnahmen/Schritte gibt, die ergriffen werden können, um die Sicherheit der Benutzer zu gewährleisten.

![Sicherheitstrends mit Informationen zu aktuellen Bedrohungen](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a>Wie erhalten wir diese Funktionen?

Microsoft 365 Funktionen für die Untersuchung und Reaktion auf Bedrohungen sind in Microsoft Defender für Office 365 Plan 2 enthalten, der in Enterprise E5 oder als Add-On für bestimmte Abonnements enthalten ist. Weitere Informationen finden Sie unter [Defender for Office 365 Plan 1 und Plan 2.](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)

## <a name="required-roles-and-permissions"></a>Erforderliche Rollen und Berechtigungen

Microsoft Defender für Office 365 verwendet die rollenbasierte Zugriffssteuerung. Berechtigungen werden über bestimmte Rollen in Azure Active Directory, dem Microsoft 365 Admin Center oder dem Microsoft 365 Defender-Portal zugewiesen.

> [!TIP]
> Obwohl einige Rollen, z. B. Sicherheitsadministrator, im Microsoft 365 Defender Portal zugewiesen werden können, sollten Sie stattdessen die Microsoft 365 Admin Center oder Azure Active Directory verwenden. Informationen zu Rollen, Rollengruppen und Berechtigungen finden Sie in den folgenden Ressourcen:
>
> - [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md)
> - [Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

<br>

****

|Aktivität|Rollen und Berechtigungen|
|---|---|
|Verwenden des Dashboards für die Bedrohungs- & -Sicherheitsrisikoverwaltung (oder des neuen [Sicherheitsdashboards)](security-dashboard.md) <p> Anzeigen von Informationen zu aktuellen oder aktuellen Bedrohungen|Eine der folgenden Varianten: <ul><li>**Globaler Administrator**</li><li>**Sicherheitsadministrator**</li><li>**Sicherheitsleseberechtigter**</li></ul> <p> Diese Rollen können entweder in Azure Active Directory ( ) oder im Microsoft 365 Admin Center ( ) zugewiesen <https://portal.azure.com> <https://admin.microsoft.com> werden.|
|Verwenden von [Explorer (und Echtzeiterkennungen)](threat-explorer.md) zum Analysieren von Bedrohungen|Eine der folgenden Varianten: <ul><li>**Globaler Administrator**</li><li>**Sicherheitsadministrator**</li><li>**Sicherheitsleseberechtigter**</li></ul> <p> Diese Rollen können entweder in Azure Active Directory ( ) oder im Microsoft 365 Admin Center ( ) zugewiesen <https://portal.azure.com> <https://admin.microsoft.com> werden.|
|Anzeigen von Vorfällen (auch als Untersuchungen bezeichnet) <p> Hinzufügen von E-Mail-Nachrichten zu einem Vorfall|Eine der folgenden Varianten: <ul><li>**Globaler Administrator**</li><li>**Sicherheitsadministrator**</li><li>**Sicherheitsleseberechtigter**</li></ul> <p> Diese Rollen können entweder in Azure Active Directory ( ) oder im Microsoft 365 Admin Center ( ) zugewiesen <https://portal.azure.com> <https://admin.microsoft.com> werden.|
|Auslösen von E-Mail-Aktionen in einem Vorfall <p> Suchen und Löschen verdächtiger E-Mail-Nachrichten|Eine der folgenden Varianten: <ul><li>**Globaler Administrator**</li><li>**Sicherheitsadministrator** und die Rolle **"Suchen und Löschen"**</li></ul> <p> Die Rollen **"Globaler Administrator"** und **"Sicherheitsadministrator"** können entweder in Azure Active Directory ( ) oder im Microsoft 365 Admin Center ( ) zugewiesen <https://portal.azure.com> <https://admin.microsoft.com> werden. <p> Die Rolle **"Suchen und Löschen"** muss in den **Rollen "E-Mail & Zusammenarbeit"** im Microsoft 36 Defender-Portal ( ) zugewiesen <https://security.microsoft.com> werden.|
|Integrieren von Microsoft Defender für Office 365 Plan 2 in Microsoft Defender für Endpunkt <p> Integrieren von Microsoft Defender für Office 365 Plan 2 mit einem SIEM-Server|Entweder der **globale Administrator** oder die **Sicherheitsadministratorrolle,** die entweder in Azure Active Directory ( ) oder im Microsoft 365 Admin Center ( ) zugewiesen <https://portal.azure.com> <https://admin.microsoft.com> ist. <p> --- **Plus** --- <p> Eine geeignete Rolle, die in zusätzlichen Anwendungen (z. [B. Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/user-roles) oder Ihrem SIEM-Server) zugewiesen ist.|
|

## <a name="next-steps"></a>Nächste Schritte

- [Erfahren Sie mehr über Bedrohungsverfolgungen – neu und bedrohlich](threat-trackers.md)
- [Suchen und Untersuchen bösartiger E-Mails, die übermittelt wurden (Office 365 Untersuchung und Reaktion auf Bedrohungen)](investigate-malicious-email-that-was-delivered.md)
- [Integrieren Office 365 Untersuchung und Reaktion auf Bedrohungen in Microsoft Defender für Endpunkt](integrate-office-365-ti-with-mde.md)
- [Simulieren eines Phishingangriffs](attack-simulation-training.md)
