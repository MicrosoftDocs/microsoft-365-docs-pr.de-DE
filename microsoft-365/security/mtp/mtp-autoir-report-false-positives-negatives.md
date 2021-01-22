---
title: Behandeln falsch positiver oder falsch negativer Ergebnisse in AIR in Microsoft 365 Defender
description: Wurde etwas von AIR in Microsoft 365 Defender verpasst oder falsch erkannt? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
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
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930354"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Behandeln falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Haben [automatisierte Untersuchungs- und Reaktionsfunktionen](mtp-autoir.md) in Microsoft 365 Defender etwas übersehen oder falsch erkannt? Es gibt Schritte, die Sie ausführen können, um sie zu beheben. Sie können:

- [Melden eines falsch positiven/negativen Ergebnisses an Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)

- [Anpassen der Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (falls erforderlich); und 

- [Rückgängig gemachte Wiederherstellungsaktionen, die auf Geräten ergriffen wurden.](#undo-a-remediation-action-that-was-taken-on-a-device) 

Verwenden Sie diesen Artikel als Leitfaden. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Melden eines falsch positiven/negativen Ergebnisses zur Analyse an Microsoft

|Element wurde verpasst oder falsch erkannt |Dienst  |Vorgehensweise  |
|---------|---------|---------|
|– E-Mail-Nachricht <br/>- E-Mail-Anlage <br/>- URL in einer E-Mail-Nachricht<br/>– URL in einer Office-Datei      |[Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Übermitteln von verdächtigen Spam-, Phishing-, URLs und Dateien zur Überprüfung an Microsoft](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Datei oder App auf einem Gerät    |[Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection)         |[Übermitteln einer Datei zur Schadsoftwareanalyse an Microsoft](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Anpassen einer Warnung, um zu verhindern, dass sich falsch positive Ergebnisse wiederholen

|Szenario |Dienst |Vorgehensweise |
|--------|--------|--------|
|– Eine Warnung wird durch legitime Verwendung ausgelöst <br/>– Eine Warnung ist ungenau    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> oder <br/>[Azure Advanced Threat Detection](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Verwalten von Warnungen im Cloud App Security-Portal](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|Eine Datei, IP-Adresse, URL oder Domäne wird auf einem Gerät als Schadsoftware behandelt, obwohl sie sicher ist.|[Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection) |[Erstellen eines benutzerdefinierten Indikators mit der Aktion "Zulassen"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Rückgängig machen einer Korrekturaktion, die auf einem Gerät ergriffen wurde

Wenn eine Korrekturaktion auf einem Gerät (z. B. einem Windows 10-Gerät) ausgeführt wurde und das Element tatsächlich keine Bedrohung darstellt, kann Ihr Sicherheitsteam die Korrekturaktion im Action Center rückgängig [machen.](mtp-action-center.md)

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie über [die erforderlichen Berechtigungen verfügen,](mtp-action-center.md#required-permissions-for-action-center-tasks) bevor Sie die folgende Aufgabe ausführen.

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 

2. Wählen Sie im Navigationsbereich **Info-Center** aus. 

3. Wählen Sie **auf der** Registerkarte "Verlauf" eine Aktion aus, die Rückgängig gemacht werden soll. Dadurch wird ein Flyout geöffnet.<br/>
    > [!TIP]
    > Verwenden Sie Filter, um die Liste der Ergebnisse einengt. 

4. Wählen Sie im Flyout für das ausgewählte Element die Seite **"Untersuchung öffnen" aus.**

5. Wählen Sie in der Ansicht "Untersuchungsdetails" die Registerkarte **"Aktionen"** aus.

6. Wählen Sie ein Element mit dem Status **"Abgeschlossen"** aus, und suchen Sie in der Spalte "Entscheidungen" nach einem Link wie  **"Genehmigt".** Dadurch wird ein Flyout mit weiteren Details zur Aktion geöffnet.

7. Um die Aktion rückgängig zu machen, wählen **Sie "Problembehebung löschen" aus.**

## <a name="see-also"></a>Siehe auch

- [Anzeigen der Details und Ergebnisse einer automatischen Untersuchung](mtp-autoir-results.md)
- [Proaktive Suche nach Bedrohungen mit erweiterter Suche in Microsoft 365 Defender](advanced-hunting-overview.md)
