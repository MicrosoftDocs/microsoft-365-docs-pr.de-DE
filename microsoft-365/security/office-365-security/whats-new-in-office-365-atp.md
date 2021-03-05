---
title: Neues in Microsoft Defender für Office 365
description: Erfahren Sie mehr über die neuen Features und Funktionen, die in der neuesten Version von Microsoft Defender für Office 365 verfügbar sind.
keywords: Neues in Office 365 atp, ga, allgemein verfügbar, Funktionen, verfügbar, neu
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.date: 01/12/2021
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7b6175f507f54adf357e40ea44c39f5e495a1b14
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454489"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Neues in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In diesem Artikel werden neue Features in der neuesten Version von Microsoft Defender für Office 365 aufgeführt. Features, die sich derzeit in der Vorschau befinden, sind mit **(Vorschau) bezeichnet.**

> [!TIP]
> Sie verfügen noch nicht über Microsoft Defender für Office 365? [Wenden Sie sich an den Vertrieb, um eine Testversion zu starten.](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)

## <a name="februarymarch-2021"></a>Februar/März 2021 

- Warnungs-ID-Integration (Suche mithilfe von Warnungs-ID und Alert-Explorer Navigation) in [Sucherfahrungen](threat-explorer.md)
- Erhöhen der Grenzwerte für den Export von Datensätzen von 9990 auf 200.000 bei der [Suche](threat-explorer.md)
- Erweitern der Datenaufbewahrungs- und Suchgrenze für Test-Mandanten von 7 (vorheriger Grenzwert) auf 30 Tage in [Sucherfahrungen](threat-explorer.md)
- Neue Suchpivoten mit dem Namen **Impersonated Domain** und **Impersonated User** innerhalb des Explorers (und Echtzeiterkennungen), um nach Identitätswechselangriffen gegen geschützte Benutzer oder Domänen zu suchen. Weitere Informationen finden Sie unter [Details](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains). (Microsoft Defender für Office 365 Plan 1 oder Plan 2)

## <a name="december-2020"></a>Dezember 2020

- [In Office 365 standardmäßig sicher](secure-by-default.md)
- Verbesserungen bei der automatisierten Untersuchung: allgemeine Warnungen für manuell ausgelöste E-Mail-Untersuchungen, Behandeln von Postfachänderungen als separate Entitätskategorie, Entfernen redundanter URL-Blockaktionen und Erstellen ausgehender E-Mail-Cluster für benutzerinaktivierte Untersuchungen.

## <a name="november-2020"></a>November 2020

- Exportbeschränkungen in Review > Action Center > Remediation from Mail Submission and Action Log (Defender for Office 365 Plan 2) aktualisiert

## <a name="septemberoctober-2020"></a>September/Oktober 2020

- [Überprüfen Ihrer Richtlinien mithilfe von Configuration Analyzer](configuration-analyzer-for-security-policies.md)
- Erweiterte Funktionen [im Bedrohungs-Explorer,](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) einschließlich benutzerorientierter Benutzer, Transportregeln und Connectors (Defender for Office 365-Informationen im Bedrohungs-Explorer (E-Mails wurden von Mandanten-/Benutzerrichtlinien zugelassen/blockiert) (Defender for Office 365 Plan 2) [](threat-explorer.md)
- Surfen von URL-Bedrohungen im [Threat Explorer](threat-explorer.md#threats-in-urls) (Schadsoftware, Phishing, Spam oder keine) (Defender for Office 365 Plan 2)
- [Verbesserungen im Explorer für die](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming) Suche nach Bedrohungen mit Updates zu Bedrohungen, zusätzlichen Aktionen, Zustellungsstandorten und aktualisierter Zeitachsenansicht (Defender für Office 365 Plan 2)

## <a name="julyaugust-2020"></a>Juli/August 2020

- [Verbesserungen bei der Suche](threat-explorer.md#improvements-to-threat-hunting-experience) (Microsoft Defender für Office 365 Plan 1 oder Plan 2)
- [Einfaches Anwenden empfohlener Einstellungen mithilfe vordefinierter Sicherheitsrichtlinien](preset-security-policies.md)

## <a name="marchapril-2020"></a>März/April 2020

- Die Möglichkeit, [gefährdete Benutzerkonten mit automatisierter](address-compromised-users-quickly.md) Untersuchung und Reaktion zu adressiert, ist jetzt allgemein verfügbar. (Microsoft Defender für Office 365 Plan 2)

## <a name="januaryfebruary-2020"></a>Januar/Februar 2020

- [Allgemeine Verfügbarkeit von Kampagnenansichten in Microsoft Defender für Office 365](campaigns.md) (Microsoft Defender für Office 365 Plan 2)
- Verbesserungen des [Bedrohungs-Explorers,](threat-explorer.md) damit Sicherheitsteams beim Untersuchen von E-Mails nach mehreren Feldern suchen und filtern [können:](investigate-malicious-email-that-was-delivered.md)(Microsoft Defender for Office 365 Plan 2)
  - Zustellungsspeicherort und spezielle Aktionen
  - Direktionalität (ein- oder ausgehend oder innerhalb der Organisation)
  - Erweiterte NOT-Filter (dies sind erweiterte Filteroptionen, die keine enthalten, nicht enthalten usw.)
  - Granulare Zeitfilter (Tag, Stunde, halbe Stunde)

- Das **Incidents-Widget** ist jetzt das **Action Center-Widget.** (Um Ihre Sicherheits widgets anzuzeigen, wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltung** \> **Überprüfen** sie .) (Microsoft Defender für Office 365 Plan 2)

- [Sichere Dokumente in Microsoft 365](safe-docs.md) **(Vorschau)**

## <a name="december-2019"></a>Dezember 2019

- [Exportieren von URL-Klickdaten für die Offlineanalyse](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) (Microsoft Defender für Office 365 Plan 1 oder Plan 2)

- [Verwenden von Kampagnenansichten in Microsoft Defender für Office 365 (**Vorschau**)](campaigns.md) (Microsoft Defender für Office 365 Plan 2)

## <a name="november-2019"></a>November 2019

- [Sehen Sie sich neue funktionen für die Erkennung und](address-compromised-users-quickly.md) Reaktion gefährdeter Benutzer an (**Vorschau**) (Microsoft Defender für Office 365 Plan 2)

## <a name="september-2019"></a>September 2019

- [Verwenden automatisierter Untersuchungs- und Reaktionsfunktionen](automated-investigation-response-office.md) (Microsoft Defender für Office 365 Plan 2)

- Integration in automatisierte Untersuchungs- und Reaktionsereignisse in [Microsoft Defender für Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) mithilfe der Office 365 Management Activity API (Defender for Office 365 Plan 2)

- [Anzeigen der E-Mail-Kopfzeilen und Herunterladen des E-Mail-Textkörpers](investigate-malicious-email-that-was-delivered.md) (Microsoft Defender für Office 365 Plan 1 oder Plan 2)

## <a name="august-2019"></a>August 2019

- [Anzeigen der Zeitachse der E-Mail](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) (Microsoft Defender für Office 365 Plan 1 oder Plan 2)

## <a name="july-2019"></a>Juli 2019

- [Überprüfen der Zustellungsaktion und des Speicherorts von E-Mail-Nachrichten](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) (Microsoft Defender für Office 365 Plan 1 oder 2)

## <a name="june-2019"></a>Juni 2019

- [Anzeigen von Phishing-URLs und Klicken auf Diktierdaten](threat-explorer.md#view-phishing-url-and-click-verdict-data) (Microsoft Defender für Office 365 Plan 1 oder Plan 2)

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender für Office 365 Plan 1 und Plan 2

Wussten Sie, dass Microsoft Defender für Office 365 in zwei Plänen verfügbar ist? [Erfahren Sie mehr über die einzelnen Pläne.](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)

## <a name="see-also"></a>Siehe auch

[Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap)

[Microsoft Defender for Office 365 Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
