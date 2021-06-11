---
title: So melden Sie falsch positive oder falsch negative Ergebnisse nach einer automatisierten Untersuchung in Microsoft Defender für Office 365
description: Wurde etwas von AIR in Microsoft Defender für Office 365 übersehen oder fälschlicherweise erkannt? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Auslösen, Aktion, Korrektur, falsch positiv, falsch negativ
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 287bd9cd4dda6ccb152e93908a409e036eab9cc7
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878880"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>So melden Sie falsch positive/negative Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Wenn [air-Funktionen (Automatisierte Untersuchung und Reaktion) in Office 365](automated-investigation-response-office.md) etwas verpasst oder falsch erkannt haben, gibt es Schritte, die Ihr Sicherheitsteam ausführen kann, um es zu beheben. Zu diesen Aktionen gehören:

- [Melden eines falsch positiven/negativen Ergebnisses an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Anpassen von Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (falls erforderlich); Und
- [Rückgängigmachen von Abhilfemaßnahmen, die ausgeführt wurden.](#undo-a-remediation-action)

Verwenden Sie diesen Artikel als Leitfaden.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Melden eines falsch positiven/negativen Ergebnisses an Microsoft zur Analyse

Wenn AIR in Microsoft Defender für Office 365 eine E-Mail-Nachricht, eine E-Mail-Anlage, eine URL in einer E-Mail-Nachricht oder eine URL in einer Office-Datei verpasst hat, können Sie [verdächtige Spam-, Phishing-, URLs und Dateien zur Office 365 Überprüfung an Microsoft übermitteln.](admin-submission.md)

Sie können auch [eine Datei zur Schadsoftwareanalyse an Microsoft übermitteln.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden

Wenn eine Warnung durch legitime Verwendung ausgelöst wird oder die Warnung ungenau ist, können Sie [Warnungen im Cloud App Security Portal verwalten.](/cloud-app-security/managing-alerts)

Wenn Ihre Organisation zusätzlich zu Office 365 [Microsoft Defender für Endpunkt](/windows/security/threat-protection) verwendet und eine Datei, IP-Adresse, URL oder Domäne als Schadsoftware auf einem Gerät behandelt wird, obwohl es sicher ist, können Sie einen [benutzerdefinierten Indikator mit einer "Zulassen"-Aktion für Ihr Gerät erstellen.](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)

## <a name="undo-a-remediation-action"></a>Rückgängigmachen einer Korrekturaktion

Wenn in den meisten Fällen eine Korrekturmaßnahme für eine E-Mail-Nachricht, eine E-Mail-Anlage oder eine URL ausgeführt wurde und das Element tatsächlich keine Bedrohung ist, kann Ihr Sicherheitsteam die Korrekturaktion rückgängig machen und Maßnahmen ergreifen, um zu verhindern, dass das falsch positive Ergebnis wiederholt wird. Sie können entweder den [Bedrohungs-Explorer](#undo-an-action-using-threat-explorer) oder die [Registerkarte "Aktionen" für eine Untersuchung](#undo-an-action-in-the-action-center) verwenden, um eine Aktion rückgängig zu machen.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen, bevor Sie versuchen, die folgenden Aufgaben auszuführen.

### <a name="undo-an-action-using-threat-explorer"></a>Rückgängigmachen einer Aktion mithilfe des Bedrohungs-Explorers

Mit dem Bedrohungs-Explorer kann Ihr Sicherheitsteam eine E-Mail finden, die von einer Aktion betroffen ist, und die Aktion möglicherweise rückgängigmachen.

<br>

****

|Szenario|Rückgängig-Optionen|Weitere Informationen|
|---|---|---|
|Eine E-Mail-Nachricht wurde an den Junk-E-Mail-Ordner eines Benutzers weitergeleitet.|<ul><li>Verschieben der Nachricht in den Ordner "Gelöschte Elemente" des Benutzers</li><li>Verschieben der Nachricht in den Posteingang des Benutzers</li><li>Die Nachricht wird gelöscht.</li></ul>|[Suchen und Untersuchen bösartiger E-Mails, die in Office 365](investigate-malicious-email-that-was-delivered.md)|
|Eine E-Mail-Nachricht oder eine Datei wurde unter Quarantäne gestellt|<ul><li>Freigeben der E-Mail oder Datei</li><li> Löschen der E-Mail oder Datei</li></ul>|[Verwalten von isolierten Nachrichten als Administrator](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Rückgängigmachen einer Aktion im Info-Center

Im Info-Center können Sie Abhilfemaßnahmen sehen, die ausgeführt wurden, und die Aktion möglicherweise rückgängig gemacht werden.

1. Wechseln Sie zum Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ).
2. Wählen Sie im Navigationsbereich **das Info-Center** aus.
3. Wählen Sie die Registerkarte **"Verlauf",** um die Liste der abgeschlossenen Aktionen anzuzeigen.
4. Wählen Sie ein Element aus. Der Flyoutbereich wird geöffnet.
5. Wählen Sie im Flyoutbereich **"Rückgängig"** aus. (Nur Aktionen, die rückgängig machen können, verfügen über eine Schaltfläche **"Rückgängig".)**

## <a name="see-also"></a>Siehe auch

- [Microsoft Defender für Office 365](defender-for-office-365.md)
- [Automatisierte Untersuchungen in Microsoft Defender für Office 365](office-365-air.md)
