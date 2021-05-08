---
title: Behandeln falsch positiver oder falsch negativer Ergebnisse in AIR in Microsoft 365 Defender
description: Wurde etwas verpasst oder falsch von AIR in Microsoft 365 erkannt? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
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
ms.openlocfilehash: 727ca529dc1a16af778e01a08c9adcfe42b9b974
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245468"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Behandeln falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Falsch positive/negative Werte können gelegentlich bei jeder Bedrohungsschutzlösung auftreten. Wenn [automatisierte Untersuchungs- und Reaktionsfunktionen](m365d-autoir.md) in Microsoft 365 Defender etwas verpasst oder falsch erkannt haben, gibt es Schritte, die Ihr Sicherheitsteam ausführen kann:

- [Melden eines falsch positiven/negativen Werts an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Passen Sie Ihre Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) an (falls erforderlich); und 
- [Rückgängig machen von Korrekturaktionen, die auf Geräten ergriffen wurden.](#undo-a-remediation-action-that-was-taken-on-a-device) 

In den folgenden Abschnitten wird beschrieben, wie Diese Aufgaben ausgeführt werden.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Melden eines falsch positiven/negativen Werts an Microsoft zur Analyse

|Element wurde verpasst oder falsch erkannt |Dienst  |Vorgehensweise  |
|---------|---------|---------|
|- E-Mail-Nachricht <br/>- E-Mail-Anlage <br/>- URL in einer E-Mail-Nachricht<br/>- URL in einer Office Datei      |[Microsoft Defender für Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)        |[Übermitteln verdächtiger Spam-, Phishing-, URLs- und Dateien an Microsoft zur Überprüfung](../office-365-security/admin-submission.md)         |
|Datei oder App auf einem Gerät    |[Microsoft Defender für Endpunkt](/windows/security/threat-protection)         |[Übermitteln einer Datei an Microsoft zur Schadsoftwareanalyse](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden

|Szenario |Dienst |Vorgehensweise |
|--------|--------|--------|
|– Eine Warnung wird durch legitime Verwendung ausgelöst <br/>– Eine Warnung ist ungenau    |[Microsoft Cloud App Security](/cloud-app-security)<br/> oder <br/>[Azure Advanced Threat Detection](/azure/security/fundamentals/threat-detection)         |[Verwalten von Warnungen im Cloud App Security Portal](/cloud-app-security/managing-alerts)         |
|Eine Datei, eine IP-Adresse, eine URL oder eine Domäne wird auf einem Gerät als Schadsoftware behandelt, obwohl sie sicher ist.|[Microsoft Defender für Endpunkt](/windows/security/threat-protection) |[Erstellen eines benutzerdefinierten Indikators mit einer Aktion "Zulassen"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Rückgängig machen einer Korrekturaktion, die auf einem Gerät ergriffen wurde

Wenn eine Korrekturaktion für eine Entität (z. B. ein Gerät oder eine E-Mail-Nachricht) ergriffen wurde und die betroffene Entität keine bedrohung ist, kann Ihr Sicherheitsteam die Korrekturaktion im [Aktionscenter](m365d-action-center.md)rückgängig machen.

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 
2. Wählen Sie im Navigationsbereich **Info-Center** aus. 
3. Wählen Sie **auf der** Registerkarte Verlauf eine Aktion aus, die Rückgängig gemacht werden soll. Der Flyoutbereich wird geöffnet.
4. Wählen Sie im Flyoutbereich **Rückgängig aus.**

> [!TIP]
> Weitere [Informationen finden Sie unter Rückgängig gemachte Aktionen](m365d-autoir-actions.md#undo-completed-actions).

## <a name="see-also"></a>Siehe auch

- [Anzeigen der Details und Ergebnisse einer automatischen Untersuchung](m365d-autoir-results.md)
- [Proaktive Suche nach Bedrohungen mit erweiterter Suche in Microsoft 365 Defender](advanced-hunting-overview.md)
- [Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)