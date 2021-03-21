---
title: Korrekturaktionen in Microsoft 365 Defender
description: Erhalten Sie eine Übersicht über Abhilfemaßnahmen, die automatisierte Untersuchungen in Microsoft 365 Defender durchführen
keywords: automatisch, Untersuchung, Warnung, Trigger, Aktion, Wartung
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 7dd95e8d7fe6424e294fbc9500fb908819463678
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928628"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Korrekturaktionen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Wartungsaktionen

Während und nach einer automatisierten Untersuchung in Microsoft 365 Defender werden Korrekturaktionen für schädliche oder verdächtige Elemente identifiziert. Einige Arten von Korrekturaktionen werden auf Geräten, auch als Endpunkte bezeichnet, ergriffen. Andere Korrekturaktionen werden für E-Mail-Inhalte ergriffen. Automatisierte Untersuchungen werden abgeschlossen, nachdem Korrekturmaßnahmen ergriffen, genehmigt oder abgelehnt wurden.

> [!IMPORTANT]
> Ob Korrekturaktionen automatisch oder nur nach Genehmigung ausgeführt werden, hängt von bestimmten Einstellungen ab, z. B. von automatisierungsstufen. Weitere Informationen finden Sie in den folgenden Artikeln:
> - [Konfigurieren Der automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [Wie Bedrohungen auf Geräten behoben werden](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Bedrohungen und Abhilfemaßnahmen für E-Mail-& Inhalte der Zusammenarbeit](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

In der folgenden Tabelle sind Korrekturaktionen zusammengefasst, die derzeit in Microsoft 365 Defender unterstützt werden: 

|Korrekturaktionen für Geräte (Endpunkte)  |Wartungsaktionen für E-Mails  |
|:---------|:---------|
|– Untersuchungspaket sammeln <br/>- Gerät isolieren (diese Aktion kann rückgängig gemacht werden)<br/>- Offboardcomputer <br/>- Ausführung von Releasecode <br/>– Isolieren aus Quarantäne <br/>- Anforderungsbeispiel <br/>- Codeausführung einschränken (diese Aktion kann rückgängig gemacht werden) <br/>– Ausführen der Antivirenscans <br/>- Beenden und Isolieren      |- Blockieren der URL (Zeitpunkt des Klicks)<br/>– Soft delete email messages or clusters<br/>- Quarantäne-E-Mail<br/>- Isolieren einer E-Mail-Anlage<br/>- Deaktivieren der externen E-Mail-Weiterleitung          |

Korrekturaktionen, unabhängig davon, ob die Genehmigung aussteht oder bereits abgeschlossen ist, können im [Action Center angezeigt werden.](./mtp-action-center.md)

## <a name="remediation-actions-that-follow-automated-investigations"></a>Abhilfemaßnahmen, die automatisierten Untersuchungen folgen

Wenn eine automatisierte Untersuchung abgeschlossen ist, wird für jeden beteiligten Nachweis ein Urteil erzielt. Je nach Urteil werden Korrekturaktionen identifiziert. In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden. Alles hängt davon ab, [wie die automatisierte Untersuchung und Reaktion konfiguriert ist.](mtp-configure-auto-investigation-response.md)

In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:

| Erkenntnis    | Bereich    | Ergebnisse|
|------|------|------|
| Bösartig    | Geräte (Endpunkte)    | Behebungsaktionen werden automatisch ausgeführt (vorausgesetzt, [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) die Gerätegruppen Ihrer Organisation sind auf Vollständig festgelegt – Bedrohungen werden automatisch **behoben)**|
| Bösartig    | E-Mail-Inhalt (URLs oder Anlagen) | Empfohlene Korrekturaktionen müssen genehmigt werden.|
| Verdächtig    | Geräte oder E-Mail-Inhalte | Empfohlene Korrekturaktionen müssen genehmigt werden.|
| Keine Bedrohungen gefunden    | Geräte oder E-Mail-Inhalte    | Es sind keine Korrekturaktionen erforderlich.|


## <a name="remediation-actions-that-are-taken-manually"></a>Manuelle Korrekturaktionen

Zusätzlich zu Abhilfemaßnahmen, die automatisierten Untersuchungen folgen, kann Ihr Sicherheitsbetriebsteam bestimmte Korrekturaktionen manuell ausführen. Dazu gehören die folgenden Aktionen:

- Manuelle Geräteaktion, z. B. Geräteisolation oder Dateiquarantäne.
- Manuelle E-Mail-Aktion, z. B. das soft-deleting von E-Mail-Nachrichten. 
- [Erweiterte Suche auf](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) Geräten oder E-Mails.
- [Explorer-Aktion](../office-365-security/threat-explorer.md) für E-Mail-Inhalte, z. B. das Verschieben von E-Mails in Junk- oder Soft-Deleting-E-Mails oder das Löschen von E-Mails.
- Manuelle [Liveantwortaktion,](/windows/security/threat-protection/microsoft-defender-atp/live-response) z. B. Löschen einer Datei, Beenden eines Prozesses und Entfernen einer geplanten Aufgabe.
- Liveantwortaktion mit [Microsoft Defender for Endpoint-APIs,](/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)z. B. Isolieren eines Geräts, Ausführen einer Antivirenscans und Abrufen von Informationen zu einer Datei. 

## <a name="next-steps"></a>Nächste Schritte

- [Aufrufen des Aktionszentrums](./mtp-action-center.md)
- [Anzeigen und Verwalten von Korrekturaktionen](./mtp-autoir-actions.md)
- [Behandeln falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen](mtp-autoir-report-false-positives-negatives.md)