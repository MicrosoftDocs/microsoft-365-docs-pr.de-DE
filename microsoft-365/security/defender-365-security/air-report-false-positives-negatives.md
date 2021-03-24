---
title: Melden falsch positiver oder falsch negativer Ergebnisse nach automatisierter Untersuchung in Microsoft Defender für Office 365
description: Wurde etwas von AIR in Microsoft Defender für Office 365 verpasst oder falsch erkannt? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Trigger, Aktion, Korrektur, falsch positiv, falsch negativ
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: 4476578939f2ece90c638c919c7e4d134ea2d9ec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065623"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Melden falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Wenn automatisierte Untersuchungs- und Reaktionsfunktionen [(AIR) in Office 365](automated-investigation-response-office.md) etwas verpasst oder falsch erkannt haben, gibt es Schritte, die Ihr Sicherheitsbetriebsteam unternehmen kann, um dies zu beheben. Zu diesen Aktionen gehören:

- [Melden eines falsch positiven/negativen Werts an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Anpassen von Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (falls erforderlich); und
- [Rückgängig machen von Korrekturaktionen, die ergriffen wurden.](#undo-a-remediation-action)

Verwenden Sie diesen Artikel als Leitfaden.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Melden eines falsch positiven/negativen Werts an Microsoft zur Analyse

Wenn AIR in Microsoft Defender für Office 365 eine E-Mail-Nachricht, eine E-Mail-Anlage, eine URL in einer E-Mail-Nachricht oder eine URL in einer Office-Datei verpasst hat, können Sie verdächtige Spam-, Phishing-, URLs- und Dateien an [Microsoft for Office 365-Überprüfung übermitteln.](admin-submission.md)

Sie können auch [eine Datei zur Schadsoftwareanalyse an Microsoft übermitteln.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden

Wenn eine Warnung durch legitime Verwendung ausgelöst wird oder die Warnung ungenau ist, können Sie Warnungen im [Cloud App Security-Portal verwalten.](/cloud-app-security/managing-alerts)

Wenn Ihre Organisation [Microsoft Defender for Endpoint](/windows/security/threat-protection) zusätzlich zu Office 365 verwendet und eine Datei, EINE IP-Adresse, URL oder Domäne auf einem Gerät als Schadsoftware behandelt wird, obwohl sie sicher ist, können Sie einen benutzerdefinierten Indikator mit der Aktion ["Zulassen"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)für Ihr Gerät erstellen.

## <a name="undo-a-remediation-action"></a>Rückgängig machen einer Korrekturaktion

Wenn in den meisten Fällen eine Korrekturaktion für eine E-Mail-Nachricht, E-Mail-Anlage oder URL ergriffen wurde und das Element tatsächlich keine Bedrohung darstellt, kann Ihr Sicherheitsteam die Korrekturaktion rückgängig machen und Schritte ergreifen, um zu verhindern, dass sich das falsch positive Ergebnis wiederholt. Sie können entweder den [Bedrohungs-Explorer](#undo-an-action-using-threat-explorer) oder die [Registerkarte Aktionen für](#undo-an-action-in-the-action-center) eine Untersuchung verwenden, um eine Aktion rückgängig zu machen.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen, bevor Sie versuchen, die folgenden Aufgaben auszuführen.

### <a name="undo-an-action-using-threat-explorer"></a>Rückgängig machen einer Aktion mithilfe des Bedrohungs-Explorers

Mit dem Bedrohungs-Explorer kann Ihr Sicherheitsteam eine E-Mail finden, die von einer Aktion betroffen ist, und die Aktion möglicherweise rückgängig machen.

|Szenario|Rückgängig-Optionen|Weitere Informationen|
|---|---|---|
|Eine E-Mail-Nachricht wurde an den Junk-E-Mail-Ordner eines Benutzers geroutet.|- Verschieben der Nachricht in den Ordner "Gelöschte Elemente" des Benutzers<br/>- Verschieben der Nachricht in den Posteingang des Benutzers<br/>- Löschen der Nachricht|[Suchen und Untersuchen schädlicher E-Mails, die in Office 365 zugestellt wurden](investigate-malicious-email-that-was-delivered.md)|
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
