---
title: Vorgehensweise Melden von falsch positiven oder falschen negativen Ergebnissen nach der automatischen Untersuchung in Microsoft Defender für Office 365
description: Wurde etwas verpasst oder fälschlicherweise von Air in Microsoft Defender für Office 365 erkannt? Hier erfahren Sie, wie Sie falsch positive Ergebnisse oder falsch negative Informationen zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Auslöser, Aktion, Korrektur, falsch positiv, falsch negativ
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: 0fe8891f5ea6af215791c5f4321a93667a9d58f0
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616176"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Vorgehensweise Melden von falsch positiven/negativen Ergebnissen in automatisierten Ermittlungs-und Antwortfunktionen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Gilt für:**
- Microsoft Defender für Office 365

Haben [automatisierte Funktionen für die Untersuchung und Reaktion (Air) Office 365](automated-investigation-response-office.md) vermissen oder fälschlicherweise etwas erkannt? Es gibt Schritte, die Sie ausführen können, um es zu beheben. Sie können:

- [Melden einer falsch positiven/negativen Meldung an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Passen Sie Ihre Benachrichtigungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) an (falls erforderlich); und
- [Rückgängigmachen von Korrekturaktionen, die ausgeführt wurden](#undo-a-remediation-action).

Verwenden Sie diesen Artikel als Leitfaden.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Melden einer falsch positiven/negativen Meldung an Microsoft zur Analyse

Wenn Air in Microsoft Defender für Office 365 eine e-Mail-Nachricht, eine e-Mail-Anlage, eine URL in einer e-Mail-Nachricht oder eine URL in einer Office-Datei verpasst hat, können Sie [mutmaßliche Spam, Phishing, URLs und Dateien für die Office 365 Prüfung an Microsoft übermitteln](admin-submission.md).

Sie können [eine Datei auch zur Malware Analyse an Microsoft übermitteln](https://www.microsoft.com/wdsi/filesubmission).

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden

Wenn eine Warnung durch eine legitime Verwendung ausgelöst wird oder die Warnung ungenau ist, können Sie [Warnungen im Cloud-App-Sicherheitsportal verwalten](https://docs.microsoft.com/cloud-app-security/managing-alerts).

Wenn Ihre Organisation [Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection) zusätzlich zu Office 365 verwendet, und eine Datei, IP-Adresse, URL oder Domäne als Schadsoftware auf einem Gerät behandelt wird, obwohl Sie sicher ist, können Sie [einen benutzerdefinierten Indikator mit der Aktion "zulassen" für Ihr Gerät erstellen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).

## <a name="undo-a-remediation-action"></a>Rückgängigmachen einer Korrekturaktion

In den meisten Fällen, wenn eine Korrekturaktion für eine e-Mail-Nachricht, eine e-Mail-Anlage oder eine URL ausgeführt wurde und das Element tatsächlich keine Bedrohung darstellt, kann Ihr Sicherheits Betriebsteam die Korrekturaktion rückgängig machen und Schritte Unternehmen, um zu verhindern, dass das falsch positive Ergebnis wiederholt wird. Sie können entweder [Threat Explorer](#undo-an-action-using-threat-explorer) oder die [Registerkarte Aktionen für eine Untersuchung](#undo-an-action-using-the-actions-tab-for-an-investigation) verwenden, um eine Aktion rückgängig zu machen.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen, bevor Sie versuchen, die folgenden Aufgaben auszuführen.

### <a name="undo-an-action-using-threat-explorer"></a>Rückgängigmachen einer Aktion mit dem Bedrohungs-Explorer

Mit Threat Explorer kann Ihr Sicherheits Betriebsteam eine von einer Aktion betroffene e-Mail-Nachricht finden und die Aktion möglicherweise rückgängig machen.

****

|Szenario|Rückgängig-Optionen|Weitere Informationen|
|---|---|---|
|Eine e-Mail-Nachricht wurde an den Junk-e-Mail-Ordner eines Benutzers weitergeleitet.|<ul><li>Verschiebt die Nachricht in den Ordner "Gelöschte Elemente" des Benutzers.</li><li>Verschieben der Nachricht in den Posteingang des Benutzers</li><li>Die Nachricht wird gelöscht.</li></ul>|[Suchen und untersuchen schädlicher e-Mails, die in Office 365 bereitgestellt wurden](investigate-malicious-email-that-was-delivered.md)|
|Eine e-Mail-Nachricht oder eine Datei wurde unter Quarantäne gestellt|<ul><li>Freigeben der e-Mail oder Datei</li><li>Löschen der e-Mail oder Datei</li></ul>|[Verwalten von Nachrichten in Quarantäne als Administrator](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>Rückgängigmachen einer Aktion mithilfe der Registerkarte "Aktionen" für eine Untersuchung

Im Wartungscenter können Sie Korrekturaktionen sehen, die ausgeführt wurden, und die Aktion möglicherweise rückgängig machen.

1. Gehen Sie auf <https://protection.office.com>, und melden Sie sich an. Dadurch gelangen Sie zum Security & Compliance Center.

2. Wechseln Sie zu **Threat Management** \> **Investigations**.

3. Wählen Sie in der Liste der Untersuchungen das Symbol **in neuem Fenster öffnen** neben der ID eines Elements aus.

4. Klicken Sie auf die Registerkarte **Aktionen** .

5. Wählen Sie ein Element mit dem Status **abgeschlossen** aus, und suchen Sie in der Spalte **Entscheidung** nach einem Link, beispielsweise **genehmigt**. Dadurch wird ein Flyout mit weiteren Details zur Aktion geöffnet.

6. Um die Aktion rückgängig zu machen, wählen Sie **Korrektur löschen** aus.

## <a name="related-articles"></a>Verwandte Artikel

[Microsoft Defender für Office 365](office-365-atp.md)

[Air in Microsoft Defender für Office 365](office-365-air.md)
