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
ms.openlocfilehash: ca0c557de24320692d903a1136fc434d635f0507
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955591"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Behebungsaktionen nach automatisierten Untersuchungen im Microsoft Threat Protection

**Gilt für:**
- Microsoft Threat Protection


## <a name="remediation-actions"></a>Wartungsaktionen

Während und nach einer automatischen Untersuchung im Microsoft Threat Protection werden Korrekturaktionen für böswillige oder verdächtige Elemente identifiziert. Einige Arten von Korrekturaktionen werden auf Geräten durchgeführt, die auch als Endpunkte bezeichnet werden. Für e-Mail-Inhalte werden andere Korrekturaktionen ausgeführt. Automatische Untersuchungen werden abgeschlossen, nachdem Korrekturaktionen durchgeführt, genehmigt oder abgelehnt wurden.

In der folgenden Tabelle werden Korrekturaktionen zusammengefasst, die derzeit in Microsoft Threat Protection unterstützt werden: 

|Geräte (Endpunkt)-Korrekturaktionen  |Wartungsaktionen für E-Mails  |
|---------|---------|
|Quarantänedatei<br/>Registrierungsschlüssel entfernen<br/>Prozess abbrechen <br/>Dienst beenden <br/>Treiber deaktivieren <br/>Geplante Aufgabe entfernen      |E-Mail-Nachrichten oder Cluster vorläufig löschen<br/>URL blockieren (Zeitpunkt des Klickens)<br/>Externe E-Mail-Weiterleitung deaktivieren          |

Behebungsaktionen können im [Wartungs Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)angezeigt werden, unabhängig davon, ob Sie genehmigt wurden oder bereits abgeschlossen sind.

## <a name="remediation-actions-follow-automated-investigations"></a>Behebungsaktionen führen zu automatisierten Untersuchungen

Wenn eine automatische Untersuchung abgeschlossen ist, wird für alle beteiligten Beweise eine Erkenntnis ermittelt, und es werden Korrekturaktionen identifiziert. In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden. In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:

|Erkenntnis    |Bereich    |Ergebnisse|
|------|------|------|
|Bösartig    |Geräte (Endpunkte)    |Korrekturaktionen werden automatisch ausgeführt.|
|Bösartig    |E-Mail-Inhalt (URLs oder Anlagen) | Empfohlene Korrekturaktionen müssen genehmigt werden.|
|Verdächtig    |Geräte oder E-Mail-Inhalte |Empfohlene Korrekturaktionen müssen genehmigt werden.|
|Keine Bedrohungen gefunden    |Geräte oder E-Mail-Inhalte    |Es sind keine Korrekturaktionen erforderlich.|

[Überprüfen einer ausstehenden Aktion im Info-Center](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> Wenn Sie glauben, dass durch automatisierte Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection etwas übersehen oder fälschlicherweise erkannt wurde, lassen Sie es uns wissen! [Meldet falsch positive Ergebnisse/negative](mtp-autoir-report-false-positives-negatives.md).

## <a name="next-steps"></a>Nächste Schritte

- [Genehmigen oder ablehnen von Aktionen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [Erfahren Sie mehr über das Info-Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
