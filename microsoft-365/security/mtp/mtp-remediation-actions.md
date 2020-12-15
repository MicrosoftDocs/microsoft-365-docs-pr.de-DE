---
title: Korrekturaktionen in Microsoft 365 Defender
description: Erhalten einer Übersicht Überkorrektur Aktionen, die automatisierte Untersuchungen in Microsoft 365 Defender ausführen
keywords: automatisch, Untersuchung, Warnung, Trigger, Aktion, Wartung
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 9e489e3b0100aa138b11d4bfb4ccc8048a2113f4
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683295"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Korrekturaktionen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Wartungsaktionen

Während und nach einer automatischen Untersuchung in Microsoft 365 Defender werden Korrekturaktionen für böswillige oder verdächtige Elemente identifiziert. Einige Arten von Korrekturaktionen werden auf Geräten durchgeführt, die auch als Endpunkte bezeichnet werden. Für e-Mail-Inhalte werden andere Korrekturaktionen ausgeführt. Automatische Untersuchungen werden abgeschlossen, nachdem Korrekturaktionen durchgeführt, genehmigt oder abgelehnt wurden.

> [!IMPORTANT]
> Ob Korrekturaktionen automatisch oder nur bei Genehmigung vorgenommen werden, hängt von bestimmten Einstellungen ab, beispielsweise von der Art der Automatisierungsstufe. Weitere Informationen finden Sie in den folgenden Artikeln:
> - [Konfigurieren der automatisierten Ermittlungs-und Antwortfunktionen in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [So beheben Sie Bedrohungen auf Geräten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Bedrohungen und Korrekturaktionen für e-Mail-& Zusammenarbeits Inhalte](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

In der folgenden Tabelle werden Korrekturaktionen zusammengefasst, die derzeit in Microsoft 365 Defender unterstützt werden: 

|Geräte (Endpunkt)-Korrekturaktionen  |Wartungsaktionen für E-Mails  |
|---------|---------|
|-Ermittlungs Paket sammeln <br/>-Gerät isolieren (diese Aktion kann rückgängig gemacht werden)<br/>-Extern Machine <br/>-Release Codeausführung <br/>-Freigabe aus der Quarantäne <br/>-Anforderungs Beispiel <br/>-Einschränken der Codeausführung (diese Aktion kann rückgängig gemacht werden) <br/>-Antivirus-Scan ausführen <br/>-Stop und Quarantäne      |-Block-URL (Zeit-zu-Klick)<br/>-Soft Delete-e-Mail-Nachrichten oder-Cluster<br/>-Quarantäne-e-Mail<br/>-Isolieren einer e-Mail-Anlage<br/>-Externe e-Mail-Weiterleitung deaktivieren          |

Korrekturaktionen, die ausstehende Genehmigung oder bereits abgeschlossen sind, können im [Wartungs Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)angezeigt werden.

## <a name="remediation-actions-that-follow-automated-investigations"></a>Behebungsaktionen, die automatisierten Untersuchungen entsprechen

Wenn eine automatisierte Untersuchung abgeschlossen ist, wird ein Urteil für alle Beteiligten Belege getroffen. Je nach dem Urteil werden Korrekturaktionen identifiziert. In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden. Alles hängt davon ab [, wie die automatische Untersuchung und Antwort konfiguriert ist](mtp-configure-auto-investigation-response.md).

In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:

| Erkenntnis    | Bereich    | Ergebnisse|
|------|------|------|
| Bösartig    | Geräte (Endpunkte)    | Korrekturaktionen werden automatisch durchgeführt (vorausgesetzt, die [Gerätegruppen](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) Ihrer Organisation werden **automatisch vollständig behobene Bedrohungen**).|
| Bösartig    | E-Mail-Inhalt (URLs oder Anlagen) | Empfohlene Korrekturaktionen müssen genehmigt werden.|
| Verdächtig    | Geräte oder E-Mail-Inhalte | Empfohlene Korrekturaktionen müssen genehmigt werden.|
| Keine Bedrohungen gefunden    | Geräte oder E-Mail-Inhalte    | Es sind keine Korrekturaktionen erforderlich.|


## <a name="remediation-actions-that-are-taken-manually"></a>Manuell getroffene Korrekturaktionen

Neben Korrekturaktionen, die automatisierten Untersuchungen entsprechen, kann Ihr Sicherheits Betriebsteam bestimmte Korrekturaktionen manuell ausführen. Hierzu gehören die folgenden Aktionen:

- Manuelle Geräte Aktion wie Geräte Isolierung oder Dateiquarantäne.
- Manuelle e-Mail-Aktion, beispielsweise e-Mail-Nachrichten mit Soft-löschen. 
- [Erweiterte Jagd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) Aktion auf Geräten oder e-Mail.
- [Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) -Aktion für e-Mail-Inhalte, wie das Verschieben von e-Mails in Junk-e-Mails, das Löschen von e-Mails oder das Löschen von e-Mails.
- Manuelle [Live Antwort](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) Aktion, beispielsweise das Löschen einer Datei, das Beenden eines Prozesses und das Entfernen eines geplanten Tasks.
- Live-Antwortaktion mit [Microsoft Defender für Endpunkt-APIs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), beispielsweise isolieren eines Geräts, Ausführen eines Antivirus-Scans und erhalten von Informationen zu einer Datei. 

## <a name="next-steps"></a>Nächste Schritte

- [Aufrufen des Aktionszentrums](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Genehmigen oder Ablehnen ausstehender Aktionen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Behandeln von falsch positiven/negativen Ergebnissen in automatisierten Ermittlungs-und Antwortfunktionen](mtp-autoir-report-false-positives-negatives.md)
