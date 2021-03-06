---
title: Adressen falsch positiver oder falsch negativer Ergebnisse in Microsoft 365 Defender
description: Wurde etwas von AIR in Microsoft 365 Defender übersehen oder fälschlicherweise erkannt? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Korrektur, falsch positiv, falsch negativ
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
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f60208b06e66c1e9803e05ee1fc41376824e9b56
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022534"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a>Adressen falsch positiver oder falsch negativer Ergebnisse in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Bei jeder Bedrohungsschutzlösung können gelegentlich falsch positive oder negative Ergebnisse auftreten. Wenn [automatisierte Untersuchungs- und Reaktionsfunktionen](m365d-autoir.md) in Microsoft 365 Defender etwas verpasst oder falsch erkannt haben, gibt es Schritte, die Ihr Sicherheitsteam ausführen kann:

- [Melden eines falsch positiven/negativen Ergebnisses an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Anpassen der Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (falls erforderlich)
- [Rückgängigmachen von Abhilfemaßnahmen, die auf Geräten durchgeführt wurden](#undo-a-remediation-action-that-was-taken-on-a-device)

In den folgenden Abschnitten wird beschrieben, wie diese Aufgaben ausgeführt werden.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Melden eines falsch positiven/negativen Ergebnisses an Microsoft zur Analyse

|Element verpasst oder falsch erkannt |Dienst  |Vorgehensweise  |
|---------|---------|---------|
|- E-Mail-Nachricht <br/>- E-Mail-Anlage <br/>- URL in einer E-Mail-Nachricht<br/>- URL in einer Office-Datei      |[Microsoft Defender für Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)        |[Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien zur Überprüfung an Microsoft](../office-365-security/admin-submission.md)         |
|Datei oder App auf einem Gerät    |[Microsoft Defender für Endpunkt](/windows/security/threat-protection)         |[Übermitteln einer Datei an Microsoft zur Schadsoftwareanalyse](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden

|Szenario |Dienst |Vorgehensweise |
|--------|--------|--------|
|– Eine Warnung wird durch legitime Nutzung ausgelöst <br/>– Eine Warnung ist ungenau    |[Microsoft Cloud App Security](/cloud-app-security)<br/> oder <br/>[Azure Threat Protection](/azure/security/fundamentals/threat-detection)         |[Verwalten von Warnungen im Cloud App Security-Portal](/cloud-app-security/managing-alerts)         |
|Eine Datei, IP-Adresse, URL oder Domäne wird als Schadsoftware auf einem Gerät behandelt, obwohl sie sicher ist.|[Microsoft Defender für Endpunkt](/windows/security/threat-protection) |[Erstellen eines benutzerdefinierten Indikators mit einer "Zulassen"-Aktion](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Rückgängigmachen einer Korrekturaktion, die auf einem Gerät ausgeführt wurde

Wenn eine Korrekturmaßnahme für eine Entität (z. B. ein Gerät oder eine E-Mail-Nachricht) ausgeführt wurde und die betroffene Entität keine Bedrohung ist, kann Ihr Sicherheitsteam die Korrekturaktion im [Info-Center](m365d-action-center.md)rückgängig machen.

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 
2. Wählen Sie im Navigationsbereich **Info-Center** aus. 
3. Wählen Sie auf der Registerkarte **"Verlauf"** eine Aktion aus, die Sie rückgängig machen möchten. Der Flyoutbereich wird geöffnet.
4. Wählen Sie im Flyoutbereich **"Rückgängig"** aus.

> [!TIP]
> Siehe [Abgeschlossene Aktionen rückgängigmachen.](m365d-autoir-actions.md#undo-completed-actions)

## <a name="see-also"></a>Siehe auch

- [Anzeigen der Details und Ergebnisse einer automatischen Untersuchung](m365d-autoir-results.md)
- [Proaktive Suche nach Bedrohungen mit erweiterter Suche in Microsoft 365 Defender](advanced-hunting-overview.md)
