---
title: Melden falsch positiver oder falsch negativer Ergebnisse nach automatisierter Untersuchung in Microsoft Defender für Office 365
description: Wurde etwas verpasst oder falsch von AIR in Microsoft Defender für die Office 365? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Trigger, Aktion, Korrektur, falsch positiv, falsch negativ
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
ms.openlocfilehash: 036ef1c97788f310c5b906ae5f80076ca2359cdb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275084"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Melden falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Wenn automatisierte Untersuchungs- und Reaktionsfunktionen [(AIR) in](automated-investigation-response-office.md) Office 365 etwas verpasst oder falsch erkannt wurden, gibt es Schritte, die Ihr Sicherheitsbetriebsteam unternehmen kann, um dies zu beheben. Zu diesen Aktionen gehören:

- [Melden eines falsch positiven/negativen Werts an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Anpassen von Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (falls erforderlich); und
- [Rückgängig machen von Korrekturaktionen, die ergriffen wurden.](#undo-a-remediation-action)

Verwenden Sie diesen Artikel als Leitfaden.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Melden eines falsch positiven/negativen Werts an Microsoft zur Analyse

Wenn AIR in Microsoft Defender für Office 365 eine E-Mail-Nachricht, eine E-Mail-Anlage, eine URL in einer E-Mail-Nachricht oder eine URL in einer Office-Datei verpasst hat, können Sie mutmaßliche [Spam-, Phishing-, URLs-](admin-submission.md)und Dateien zur überprüfung an Microsoft Office 365 senden.

Sie können auch [eine Datei zur Schadsoftwareanalyse an Microsoft übermitteln.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden

Wenn eine Warnung durch legitime Verwendung ausgelöst wird oder die Warnung ungenau ist, können Sie Warnungen im Cloud App Security [verwalten.](/cloud-app-security/managing-alerts)

Wenn Ihre Organisation [microsoft Defender for Endpoint](/windows/security/threat-protection) zusätzlich zu Office 365 verwendet und eine Datei, EINE IP-Adresse, URL oder Domäne als Schadsoftware auf einem Gerät behandelt wird, obwohl es sicher ist, können Sie einen benutzerdefinierten Indikator mit einer Aktion ["Zulassen"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)für Ihr Gerät erstellen.

## <a name="undo-a-remediation-action"></a>Rückgängig machen einer Korrekturaktion

Wenn in den meisten Fällen eine Korrekturaktion für eine E-Mail-Nachricht, E-Mail-Anlage oder URL ergriffen wurde und das Element tatsächlich keine Bedrohung darstellt, kann Ihr Sicherheitsteam die Korrekturaktion rückgängig machen und Schritte ergreifen, um zu verhindern, dass sich das falsch positive Ergebnis wiederholt. Sie können entweder den [Bedrohungs-Explorer](#undo-an-action-using-threat-explorer) oder die [Registerkarte Aktionen für](#undo-an-action-in-the-action-center) eine Untersuchung verwenden, um eine Aktion rückgängig zu machen.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen, bevor Sie versuchen, die folgenden Aufgaben auszuführen.

### <a name="undo-an-action-using-threat-explorer"></a>Rückgängig machen einer Aktion mithilfe des Bedrohungs-Explorers

Mit dem Bedrohungs-Explorer kann Ihr Sicherheitsteam eine E-Mail finden, die von einer Aktion betroffen ist, und die Aktion möglicherweise rückgängig machen.

|Szenario|Rückgängig-Optionen|Weitere Informationen|
|---|---|---|
|Eine E-Mail-Nachricht wurde an den Junk-E-Mail-Ordner eines Benutzers geroutet.|- Verschieben der Nachricht in den Ordner "Gelöschte Elemente" des Benutzers<br/>- Verschieben der Nachricht in den Posteingang des Benutzers<br/>- Löschen der Nachricht|[Suchen und untersuchen Sie schädliche E-Mails, die in diesem Office 365](investigate-malicious-email-that-was-delivered.md)|
|Eine E-Mail-Nachricht oder eine Datei wurde unter Quarantäne gestellt|– Lassen Sie die E-Mail oder Datei frei<br/>– Löschen der E-Mail oder Datei|[Verwalten isolierter Nachrichten als Administrator](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Rückgängig machen einer Aktion im Aktionscenter

Im Aktionscenter können Sie Korrekturaktionen sehen, die ergriffen wurden, und die Aktion potenziell rückgängig machen.

1. Wechseln Sie zum Microsoft 365 Security Center ( <https://security.microsoft.com> ).
2. Wählen Sie im Navigationsbereich **Aktionscenter aus.**
3. Wählen Sie die **Registerkarte Verlauf** aus, um die Liste der abgeschlossenen Aktionen anzeigen zu können.
4. Wählen Sie ein Element aus. Der Flyoutbereich wird geöffnet.
5. Wählen Sie im Flyoutbereich **Rückgängig aus.** (Nur Aktionen, die rückgängig gemacht werden können, verfügen über eine **Schaltfläche Rückgängig.)**

## <a name="see-also"></a>Siehe auch

- [Microsoft Defender für Office 365](defender-for-office-365.md)
- [Automatisierte Untersuchungen in Microsoft Defender für Office 365](office-365-air.md)
