---
title: Behebungsaktionen nach automatisierten Untersuchungen im Microsoft Threat Protection
description: Erhalten einer Übersicht Überkorrektur Aktionen, die automatisierte Untersuchungen im Microsoft Threat Protection ausführen
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
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 232d19cb0bcb6a2f91c1bdad15d842ec7396499c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201051"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Behebungsaktionen nach automatisierten Untersuchungen im Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection


## <a name="remediation-actions"></a>Wartungsaktionen

Während und nach einer automatischen Untersuchung im Microsoft Threat Protection werden Korrekturaktionen für böswillige oder verdächtige Elemente identifiziert. Einige Arten von Korrekturaktionen werden auf Geräten durchgeführt, die auch als Endpunkte bezeichnet werden. Für e-Mail-Inhalte werden andere Korrekturaktionen ausgeführt. Automatische Untersuchungen werden abgeschlossen, nachdem Korrekturaktionen durchgeführt, genehmigt oder abgelehnt wurden.

In der folgenden Tabelle werden Korrekturaktionen zusammengefasst, die derzeit in Microsoft Threat Protection unterstützt werden: 

|Geräte (Endpunkt)-Korrekturaktionen  |Wartungsaktionen für E-Mails  |
|---------|---------|
|-Ermittlungs Paket sammeln <br/>-Gerät isolieren (diese Aktion kann rückgängig gemacht werden)<br/>-Extern Machine <br/>-Release Codeausführung <br/>-Freigabe aus der Quarantäne <br/>-Anforderungs Beispiel <br/>-Einschränken der Codeausführung (diese Aktion kann rückgängig gemacht werden) <br/>-Antivirus-Scan ausführen <br/>-Stop und Quarantäne      |-Block-URL (Zeit-zu-Klick)<br/>-Soft Delete-e-Mail-Nachrichten oder-Cluster<br/>-Quarantäne-e-Mail<br/>-Isolieren einer e-Mail-Anlage<br/>-Externe e-Mail-Weiterleitung deaktivieren          |

Korrekturaktionen, die ausstehende Genehmigung oder bereits abgeschlossen sind, können im [Wartungs Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)angezeigt werden.

## <a name="remediation-actions-follow-automated-investigations"></a>Behebungsaktionen führen zu automatisierten Untersuchungen

Wenn eine automatisierte Untersuchung abgeschlossen ist, wird ein Urteil für alle Beteiligten Belege getroffen. Je nach dem Urteil werden Korrekturaktionen identifiziert. In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden. Alles hängt davon ab [, wie die automatische Untersuchung und Antwort konfiguriert ist](mtp-configure-auto-investigation-response.md).

In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:

|Erkenntnis    |Bereich    |Ergebnisse|
|------|------|------|
|Bösartig    |Geräte (Endpunkte)    |Korrekturaktionen werden automatisch durchgeführt (vorausgesetzt, die [Gerätegruppen](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) Ihrer Organisation werden **automatisch vollständig behobene Bedrohungen**).|
|Bösartig    |E-Mail-Inhalt (URLs oder Anlagen) | Empfohlene Korrekturaktionen müssen genehmigt werden.|
|Verdächtig    |Geräte oder E-Mail-Inhalte |Empfohlene Korrekturaktionen müssen genehmigt werden.|
|Keine Bedrohungen gefunden    |Geräte oder E-Mail-Inhalte    |Es sind keine Korrekturaktionen erforderlich.|

> [!IMPORTANT]
> Ob Korrekturaktionen automatisch oder nur bei Genehmigung vorgenommen werden, hängt von bestimmten Einstellungen ab, beispielsweise von den Gerätegruppen Richtlinien Ihrer Organisation. Weitere Informationen finden Sie in den folgenden Artikeln:
> - [Konfigurieren von automatisierten Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection](mtp-configure-auto-investigation-response.md)
> - [So beheben Sie Bedrohungen auf Geräten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a>Nächste Schritte

- [Aufrufen des Aktionszentrums](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Genehmigen oder Ablehnen ausstehender Aktionen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Behandeln von falsch positiven/negativen Ergebnissen in automatisierten Ermittlungs-und Antwortfunktionen](mtp-autoir-report-false-positives-negatives.md)
