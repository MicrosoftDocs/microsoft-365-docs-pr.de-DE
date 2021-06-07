---
title: Korrekturaktionen in Microsoft 365 Defender
description: Erhalten Sie einen Überblick über Korrekturaktionen, die automatisierten Untersuchungen in Microsoft 365 Defender folgen.
keywords: automatisch, Untersuchung, Warnung, Trigger, Aktion, Wartung
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f025f23242c28f698e6f67755cc59d21c4463914
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782945"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Korrekturaktionen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Während und nach einer automatisierten Untersuchung in Microsoft 365 Defender werden Abhilfemaßnahmen für böswillige oder verdächtige Elemente identifiziert. Einige Arten von Korrekturmaßnahmen werden auf Geräten ausgeführt, die auch als Endpunkte bezeichnet werden. Andere Korrekturmaßnahmen werden für E-Mail-Inhalte ausgeführt. Automatisierte Untersuchungen werden abgeschlossen, nachdem Korrekturmaßnahmen ergriffen, genehmigt oder abgelehnt wurden.

> [!IMPORTANT]
> Ob Korrekturmaßnahmen automatisch oder nur nach Genehmigung durchgeführt werden, hängt von bestimmten Einstellungen ab, z. B. von den Automatisierungsstufen. Weitere Informationen finden Sie in den folgenden Artikeln:
> - [Konfigurieren Der Funktionen für automatisierte Untersuchung und Reaktion in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md)
> - [Wie Bedrohungen auf Geräten behoben werden](../defender-endpoint/automated-investigations.md)
> - [Bedrohungen und Abhilfemaßnahmen für E-Mail-& Inhalte für die Zusammenarbeit](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

In der folgenden Tabelle sind Korrekturaktionen zusammengefasst, die derzeit in Microsoft 365 Defender unterstützt werden. 

|Abhilfemaßnahmen für Geräte (Endpunkte)  |Wartungsaktionen für E-Mails  |
|:---------|:---------|
|- Erfassen des Untersuchungspakets <br/>- Gerät isolieren (diese Aktion kann rückgängig machen)<br/>– Offboard-Computer <br/>– Freigeben der Codeausführung <br/>– Aus Quarantäne freigeben <br/>– Anforderungsbeispiel <br/>- Einschränken der Codeausführung (diese Aktion kann rückgängig machen) <br/>– Ausführen eines Antivirusscans <br/>– Beenden und Isolieren      |- Block-URL (Uhrzeit des Klickens)<br/>– Vorläufiges Löschen von E-Mail-Nachrichten oder Clustern<br/>– E-Mails unter Quarantäne stellen<br/>– Isolieren einer E-Mail-Anlage<br/>– Deaktivieren der externen E-Mail-Weiterleitung          |

Korrekturaktionen, unabhängig davon, ob die Genehmigung aussteht oder bereits abgeschlossen ist, können im [Info-Center](m365d-action-center.md)angezeigt werden.

## <a name="remediation-actions-that-follow-automated-investigations"></a>Korrekturaktionen, die auf automatisierte Untersuchungen folgen

Nach Abschluss einer automatisierten Untersuchung wird für jeden beteiligten Nachweis eine Bewertung getroffen. Je nach Bewertung werden Korrekturaktionen identifiziert. In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden. Alles hängt davon ab, wie [die automatisierte Untersuchung und Reaktion konfiguriert ist.](m365d-configure-auto-investigation-response.md)

In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:

| Erkenntnis    | Betroffene Entitäten    | Ergebnisse|
|------|------|------|
| Bösartig    | Geräte (Endpunkte)    | Korrekturmaßnahmen werden automatisch durchgeführt (vorausgesetzt, die [Gerätegruppen](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) Ihrer Organisation sind auf **"Vollständig" festgelegt – Bedrohungen automatisch beheben)**|
| Bösartig    | E-Mail-Inhalt (URLs oder Anlagen) | Empfohlene Korrekturaktionen müssen genehmigt werden.|
| Verdächtig    | Geräte oder E-Mail-Inhalte | Empfohlene Korrekturaktionen müssen genehmigt werden.|
| Keine Bedrohungen gefunden    | Geräte oder E-Mail-Inhalte    | Es sind keine Korrekturaktionen erforderlich.|


## <a name="remediation-actions-that-are-taken-manually"></a>Manuell ausgeführte Korrekturaktionen

Zusätzlich zu Korrekturmaßnahmen, die auf automatisierte Untersuchungen folgen, kann Ihr Sicherheitsteam bestimmte Korrekturmaßnahmen manuell ausführen. Hierzu gehören:

- Manuelle Geräteaktion, z. B. Geräteisolation oder Dateiquarantäne
- Manuelle E-Mail-Aktion, z. B. vorläufiges Löschen von E-Mail-Nachrichten 
- [Erweiterte Suchaktion](../defender-endpoint/advanced-hunting-overview.md) auf Geräten oder E-Mails
- [Explorer-Aktion](../office-365-security/threat-explorer.md) für E-Mail-Inhalte, z. B. Verschieben von E-Mails in Junk, vorläufiges Löschen von E-Mails oder endgültiges Löschen von E-Mails
- Manuelle [Liveantwortaktion,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) z. B. Löschen einer Datei, Beenden eines Prozesses und Entfernen einer geplanten Aufgabe
- Live-Antwortaktion mit [Microsoft Defender für Endpunkt-APIs,](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)z. B. Isolieren eines Geräts, Ausführen eines Antivirenscans und Abrufen von Informationen zu einer Datei

## <a name="next-steps"></a>Nächste Schritte

- [Aufrufen des Aktionszentrums](m365d-action-center.md)
- [Anzeigen und Verwalten von Wartungsaktionen](m365d-autoir-actions.md)
- [Adressen falsch positiver oder falsch negativer Ergebnisse](m365d-autoir-report-false-positives-negatives.md)
