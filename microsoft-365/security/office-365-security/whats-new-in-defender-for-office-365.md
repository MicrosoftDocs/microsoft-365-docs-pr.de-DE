---
title: Neuigkeiten in Microsoft Defender für Office 365
description: Erfahren Sie mehr über die neuen Features und Funktionen, die in der neuesten Version von Microsoft Defender für Office 365 verfügbar sind.
keywords: Neuigkeiten in Microsoft Defender für Office 365, ga, allgemein verfügbar, Funktionen, verfügbar, neu
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
ms.openlocfilehash: 0aa8e10545b43f6e0ee985ac11b161a3b21c3a91
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929554"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Neuigkeiten in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In diesem Artikel werden neue Features in der neuesten Version von Microsoft Defender für Office 365 aufgeführt. Features, die sich derzeit in der Vorschau befinden, werden mit **(Vorschau)** gekennzeichnet.

Erfahren Sie mehr, in dem Sie [dieses Video](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3) ansehen.
> [!TIP]
> Sie verfügen noch nicht über Microsoft Defender für Office 365? [Wenden Sie sich an den Vertrieb, um eine Testversion zu starten.](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)

## <a name="aprilmay-2021"></a>April/Mai 2021 

- [Seite "E-Mail-Entität":](mdo-email-entity-page.md)Eine einheitliche 360-Grad-Ansicht einer E-Mail mit erweiterten Informationen zu Bedrohungen, Authentifizierung und Erkennungen, Detonationsdetails und einer völlig neuen E-Mail-Vorschau.
- [Office 365-Verwaltungs-API:](/office/office-365-management-api/office-365-management-activity-api-schema#email-message-events)Updates für EmailEvents (RecordType 28) zum Hinzufügen von Übermittlungsaktionen, ursprünglichen und neuesten Übermittlungsspeicherorten und aktualisierten Erkennungsdetails.
- [Bedrohungsanalyse für Defender für Office 365:](/microsoft-365/security/defender/threat-analytics)Sehen Sie sich aktive Bedrohungsteilnehmer, beliebte Techniken und Angriffsflächen sowie umfassende Berichte von Microsoft-Experten zu laufenden Kampagnen an. 

## <a name="februarymarch-2021"></a>Februar/März 2021 

- Warnungs-ID-Integration (Suche mithilfe der Warnungs-ID und Alert-Explorer Navigation) in [suchumgebungen](threat-explorer.md)
- Erhöhen der Grenzwerte für den Export von Datensätzen von 9990 auf 200.000 bei [der Suche](threat-explorer.md)
- Erweitern des Explorer-Datenaufbewahrungs- und Suchlimits für Testmandanten von 7 (vorheriges Limit) auf 30 Tage bei der [Suche](threat-explorer.md)
- Neue Pivots für die Suche, die als **"Imitierte Domäne"** und **"Imitierter Benutzer"** innerhalb des Explorers (und Echtzeiterkennungen) bezeichnet werden, um nach Identitätswechselangriffen gegen geschützte Benutzer oder Domänen zu suchen. Weitere Informationen finden Sie unter [Details.](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains) (Microsoft Defender für Office 365 Plan 1 oder Plan 2)

## <a name="december-2020"></a>Dezember 2020

- [Standardmäßige Sicherheit in Office 365](secure-by-default.md)
- Verbesserungen bei der automatisierten Untersuchung: allgemeine Warnungen für manuell ausgelöste E-Mail-Untersuchungen, Behandeln von Postfachänderungen als separate Entitätskategorie, Entfernen redundanter URL-Blockierungsaktionen und Erstellen ausgehender E-Mail-Cluster für benutzerkompromittierte Untersuchungen.

## <a name="november-2020"></a>November 2020

- Exportbeschränkungen in "Überprüfen > Info-Center > Korrektur aus E-Mail-Übermittlung und Aktionsprotokoll" aktualisiert (Defender für Office 365 Plan 2)

## <a name="septemberoctober-2020"></a>September/Oktober 2020

- [Überprüfen Ihrer Richtlinien mit configuration Analyzer](configuration-analyzer-for-security-policies.md)
- [Erweiterte Funktionen im Bedrohungs-Explorer, einschließlich der wichtigsten Benutzer, Transportregeln und Connectors](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) (Defender für Office 365 Informationen im [Bedrohungs-Explorer](threat-explorer.md) (E-Mails wurden von Mandanten-/Benutzerrichtlinien zugelassen/blockiert) (Defender für Office 365 Plan 2)
- Anzeigen von URL-Bedrohungen im [Bedrohungs-Explorer](threat-explorer.md#threats-in-urls) (Schadsoftware, Phishing, Spam oder keine) (Defender für Office 365 Plan 2)
- [Verbesserungen am Bedrohungs-Explorer](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming) für die Suche mit Updates rund um Bedrohungen, zusätzliche Aktionen, Übermittlungsspeicherorte und aktualisierte Zeitachsenansicht (Defender für Office 365 Plan 2)

## <a name="julyaugust-2020"></a>Juli/August 2020

- [Verbesserungen bei der Suche](threat-explorer.md#improvements-to-threat-hunting-experience) (Microsoft Defender für Office 365 Plan 1 oder Plan 2)
- [Einfaches Anwenden empfohlener Einstellungen mithilfe vordefinierter Sicherheitsrichtlinien](preset-security-policies.md)

## <a name="marchapril-2020"></a>März/April 2020

- Die Möglichkeit, [kompromittierte Benutzerkonten mit automatisierter Untersuchung und Reaktion](address-compromised-users-quickly.md) zu behandeln, ist jetzt allgemein verfügbar. (Microsoft Defender für Office 365 Plan 2)

## <a name="januaryfebruary-2020"></a>Januar/Februar 2020

- [Allgemeine Verfügbarkeit von Kampagnenansichten in Microsoft Defender für Office 365](campaigns.md) (Microsoft Defender für Office 365 Plan 2)
- Verbesserungen am [Bedrohungs-Explorer,](threat-explorer.md) damit Sicherheitsteams bei der Untersuchung von [E-Mails](investigate-malicious-email-that-was-delivered.md)nach mehreren Feldern suchen und filtern können: (Microsoft Defender für Office 365 Plan 2)
  - Übermittlungsort und spezielle Aktionen
  - Richtungsabhängigkeit (eingehend, ausgehend oder organisationsintern)
  - Erweiterte NICHT-Filter (hierbei handelt es sich um erweiterte Filteroptionen, die nicht enthalten, nicht enthalten usw.)
  - Granulare Zeitfilter (Tag, Stunde, halbe Stunde)

- Das **Vorfall-Widget** ist jetzt das **Info-Center-Widget.** (Um Ihre Sicherheits-Widgets anzuzeigen, wechseln Sie im Microsoft 365 **Defender-Portal zu E-Mail & Zusammenarbeit** \> **Überprüfen** Sie .) (Microsoft Defender für Office 365 Plan 2)

- [Sichere Dokumente in Microsoft 365](safe-docs.md) **(Vorschau)**

## <a name="december-2019"></a>Dezember 2019

- [Exportieren von URL-Klickdaten für die Offlineanalyse](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) (Microsoft Defender für Office 365 Plan 1 oder Plan 2)

- [Verwenden von Kampagnenansichten in Microsoft Defender für Office 365 **(Vorschau)**](campaigns.md) (Microsoft Defender für Office 365 Plan 2)

## <a name="november-2019"></a>November 2019

- Sehen Sie sich die neuen funktionen für die Erkennung und Reaktion von [kompromittierten Benutzern](address-compromised-users-quickly.md) an **(Vorschau)**(Microsoft Defender für Office 365 Plan 2)

## <a name="september-2019"></a>September 2019

- [Verwenden automatisierter Untersuchungs- und Reaktionsfunktionen](automated-investigation-response-office.md) (Microsoft Defender für Office 365 Plan 2)

- [Integration in Microsoft Defender für Office 365 automatisierte Untersuchungs- und Reaktionsereignisse mithilfe der Office 365-Verwaltungsaktivitäts-API](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) (Defender für Office 365 Plan 2)

- [Anzeigen der E-Mail-Kopfzeilen und Herunterladen des E-Mail-Texts](investigate-malicious-email-that-was-delivered.md) (Microsoft Defender für Office 365 Plan 1 oder Plan 2)

## <a name="august-2019"></a>August 2019

- [Anzeigen der E-Mail-Zeitachse](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) (Microsoft Defender für Office 365 Plan 1 oder Plan 2)

## <a name="july-2019"></a>Juli 2019

- [Überprüfen der Zustellungsaktion und des Speicherorts von E-Mail-Nachrichten](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) (Microsoft Defender für Office 365 Plan 1 oder 2)

## <a name="june-2019"></a>Juni 2019

- [Anzeigen von Phishing-URLs und Klicken auf Bewertungsdaten](threat-explorer.md#view-phishing-url-and-click-verdict-data) (Microsoft Defender für Office 365 Plan 1 oder Plan 2)

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender für Office 365 Plan 1 und Plan 2

Wissen Sie, dass Microsoft Defender für Office 365 in zwei Plänen verfügbar ist? [Erfahren Sie mehr darüber, was die einzelnen Pläne enthalten.](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)

## <a name="see-also"></a>Siehe auch

[Roadmap für Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap)

[Microsoft Defender für Office 365 Dienstbeschreibung](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
