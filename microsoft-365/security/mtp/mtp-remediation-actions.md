---
title: Abhilfemaßnahmen in Microsoft 365 Defender
description: Erhalten Sie eine Übersicht über Abhilfemaßnahmen, die automatisierten Untersuchungen in Microsoft 365 Defender folgen
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932850"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Abhilfemaßnahmen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Wartungsaktionen

Während und nach einer automatischen Untersuchung in Microsoft 365 Defender werden Abhilfemaßnahmen für schädliche oder verdächtige Elemente identifiziert. Einige Arten von Abhilfemaßnahmen werden auf Geräten, die auch als Endpunkte bezeichnet werden, ergriffen. Andere Korrekturmaßnahmen werden für E-Mail-Inhalte ergriffen. Automatisierte Untersuchungen werden abgeschlossen, nachdem Korrekturmaßnahmen ergriffen, genehmigt oder abgelehnt wurden.

> [!IMPORTANT]
> Ob Korrekturaktionen automatisch oder nur nach Genehmigung ausgeführt werden, hängt von bestimmten Einstellungen ab, z. B. von automatisierungsstufen. Weitere Informationen finden Sie in den folgenden Artikeln:
> - [Konfigurieren Ihrer automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [Wie Bedrohungen auf Geräten behoben werden](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Bedrohungen und Abhilfemaßnahmen für E-Mail& Und Zusammenarbeitsinhalte](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

Die folgende Tabelle enthält eine Zusammenfassung der Wartungsaktionen, die derzeit in Microsoft 365 Defender unterstützt werden: 

|Problembehebungsaktionen für Geräte (Endpunkte)  |Wartungsaktionen für E-Mails  |
|---------|---------|
|– Erfassen des Untersuchungspakets <br/>- Gerät isolieren (diese Aktion kann rückgängig gemacht werden)<br/>– Offboardcomputer <br/>– Codeausführung veröffentlichen <br/>– Freigabe aus Der Quarantäne <br/>- Anforderungsbeispiel <br/>– Codeausführung einschränken (diese Aktion kann rückgängig gemacht werden) <br/>– Ausführen eines Antivirenscans <br/>– Beenden und Isolieren      |- Block-URL (Zeitpunkt des Klicks)<br/>- Soft delete email messages or clusters<br/>- Quarantäne-E-Mail<br/>- Isolieren einer E-Mail-Anlage<br/>- Deaktivieren der externen E-Mail-Weiterleitung          |

Korrekturaktionen, unabhängig davon, ob die Genehmigung aussteht oder bereits abgeschlossen ist, können im [Aktionscenter angezeigt werden.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)

## <a name="remediation-actions-that-follow-automated-investigations"></a>Abhilfemaßnahmen nach automatisierten Untersuchungen

Wenn eine automatisierte Untersuchung abgeschlossen ist, wird für jedes beteiligte Beweismaterial eine Prüfung erreicht. In Abhängigkeit von der Bekündung werden Korrekturaktionen identifiziert. In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden. Alles hängt davon ab, [wie die automatisierte Untersuchung und Reaktion konfiguriert ist.](mtp-configure-auto-investigation-response.md)

In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:

| Erkenntnis    | Bereich    | Ergebnisse|
|------|------|------|
| Bösartig    | Geräte (Endpunkte)    | Abhilfemaßnahmen werden automatisch ausgeführt (vorausgesetzt, die [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) Gerätegruppen Ihrer Organisation sind auf **"Vollständig"** festgelegt – Bedrohungen werden automatisch behoben)|
| Bösartig    | E-Mail-Inhalt (URLs oder Anlagen) | Empfohlene Korrekturaktionen müssen genehmigt werden.|
| Verdächtig    | Geräte oder E-Mail-Inhalte | Empfohlene Korrekturaktionen müssen genehmigt werden.|
| Keine Bedrohungen gefunden    | Geräte oder E-Mail-Inhalte    | Es sind keine Korrekturaktionen erforderlich.|


## <a name="remediation-actions-that-are-taken-manually"></a>Manuell ergriffene Korrekturaktionen

Zusätzlich zu Denkmaßnahmen, die automatisierten Untersuchungen folgen, kann Ihr Sicherheitsteam bestimmte Abhilfemaßnahmen manuell ausführen. Hierzu gehören die folgenden Aktionen:

- Manuelle Geräteaktion, z. B. Geräteisolation oder Dateiquarantäne.
- Manuelle E-Mail-Aktion, z. B. das soft-deleting von E-Mail-Nachrichten. 
- [Erweiterte Suche auf](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) Geräten oder E-Mails.
- [Exploreraktion](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) für E-Mail-Inhalte, z. B. das Verschieben von E-Mails in Junk-E-Mails, das soft-deleting von E-Mails oder das löschen von E-Mails.
- Manuelle [Liveantwortaktion,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) z. B. Löschen einer Datei, Beenden eines Prozesses und Entfernen einer geplanten Aufgabe.
- Liveantwortaktion mit [Microsoft Defender für Endpunkt-APIs,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)z. B. Isolieren eines Geräts, Ausführen eines Antivirenscans und Abrufen von Informationen zu einer Datei. 

## <a name="next-steps"></a>Nächste Schritte

- [Aufrufen des Aktionszentrums](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Genehmigen oder Ablehnen ausstehender Aktionen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Behandeln falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen](mtp-autoir-report-false-positives-negatives.md)
