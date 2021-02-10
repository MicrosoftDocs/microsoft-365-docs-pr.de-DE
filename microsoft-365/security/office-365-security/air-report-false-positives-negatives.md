---
title: Melden falsch positiver oder falsch negativer Ergebnisse nach einer automatisierten Untersuchung in Microsoft Defender für Office 365
description: Wurde etwas von AIR in Microsoft Defender für Office 365 verpasst oder falsch erkannt? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Trigger, Aktion, Korrektur, falsch positiv, falsch negativ
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 451a6b19139502a3765795694860e884a7a469bf
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175751"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>So melden Sie falsch positive/negative Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Wenn funktionen für die automatische Untersuchung und Reaktion [(AIR) in Office 365](automated-investigation-response-office.md) etwas übersehen oder falsch erkannt haben, gibt es Schritte, die Ihr Sicherheitsteam unternehmen kann, um dies zu beheben. Zu diesen Aktionen gehören:

- [Melden eines falsch positiven/negativen Ergebnisses an Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Anpassen von Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (falls erforderlich); und
- [Rückgängig machen von Korrekturaktionen, die ergriffen wurden.](#undo-a-remediation-action)

Verwenden Sie diesen Artikel als Leitfaden.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Melden eines falsch positiven/negativen Ergebnisses zur Analyse an Microsoft

If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning.](admin-submission.md)

Sie können eine [Datei auch zur Schadsoftwareanalyse an Microsoft übermitteln.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Anpassen einer Warnung, um zu verhindern, dass sich falsch positive Ergebnisse wiederholen

Wenn eine Warnung durch legitime Verwendung ausgelöst wird oder die Warnung ungenau ist, können Sie Warnungen im [Cloud App Security-Portal verwalten.](https://docs.microsoft.com/cloud-app-security/managing-alerts)

Wenn Ihre Organisation [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) zusätzlich zu Office 365 verwendet und eine Datei, EINE IP-Adresse, URL oder Domäne als Schadsoftware auf einem Gerät behandelt wird, können Sie einen benutzerdefinierten Indikator mit der Aktion ["Zulassen"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)für Ihr Gerät erstellen.

## <a name="undo-a-remediation-action"></a>Rückgängig machen einer Wartungsaktion

Wenn in den meisten Fällen eine Korrekturaktion für eine E-Mail-Nachricht, E-Mail-Anlage oder URL ergriffen wurde und das Element tatsächlich keine Bedrohung darstellt, kann Ihr Sicherheitsteam die Korrekturmaßnahmen rückgängig machen und Maßnahmen ergreifen, um zu verhindern, dass sich falsch positive Ergebnisse wiederholen. Sie können entweder den [Bedrohungs-Explorer](#undo-an-action-using-threat-explorer) oder die Registerkarte "Aktionen" [für eine Untersuchung](#undo-an-action-in-the-action-center) verwenden, um eine Aktion rückgängig zu machen.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen, bevor Sie versuchen, die folgenden Aufgaben auszuführen.

### <a name="undo-an-action-using-threat-explorer"></a>Rückgängig machen einer Aktion mit dem Bedrohungs-Explorer

Mit dem Bedrohungs-Explorer kann Ihr Sicherheitsteam eine E-Mail finden, die von einer Aktion betroffen ist, und die Aktion potenziell rückgängig machen.

|Szenario|Rückgängig-Optionen|Weitere Informationen|
|---|---|---|
|Eine E-Mail-Nachricht wurde an den Junk-E-Mail-Ordner eines Benutzers geroutet.|- Verschieben der Nachricht in den Ordner "Gelöschte Elemente" des Benutzers<br/>- Verschieben der Nachricht in den Posteingang des Benutzers<br/>– Nachricht löschen|[Suchen und Untersuchen bösartiger E-Mails, die in Office 365 zugestellt wurden](investigate-malicious-email-that-was-delivered.md)|
|Eine E-Mail-Nachricht oder eine Datei wurde unter Quarantäne gestellt.|– Freigabe der E-Mail oder Datei<br/>– Löschen der E-Mail oder Datei|[Verwalten von Nachrichten in Quarantäne als Administrator](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Rückgängig machen einer Aktion im Aktionscenter

Im Action Center können Sie Korrekturaktionen sehen, die ergriffen wurden, und die Aktion möglicherweise rückgängig machen.

1. Wechseln Sie zum Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ).
2. Wählen Sie im Navigationsbereich **"Aktionscenter" aus.** 
3. Wählen Sie die **Registerkarte "Verlauf"** aus, um die Liste der abgeschlossenen Aktionen anzeigen.
4. Wählen Sie ein Element aus. Der Flyoutbereich wird geöffnet. 
5. Wählen Sie im Flyoutbereich **"Rückgängig" aus.** (Nur Aktionen, die rückgängig gemacht werden können, verfügen über eine **Schaltfläche "Rückgängig".)**

## <a name="see-also"></a>Weitere Informationen:

- [Microsoft Defender für Office 365](office-365-atp.md)
- [Automatisierte Untersuchungen in Microsoft Defender für Office 365](office-365-air.md)
