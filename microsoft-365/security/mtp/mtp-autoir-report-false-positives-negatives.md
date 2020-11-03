---
title: Behandeln falsch positiver oder falscher negativer Ergebnisse in der Luft in Microsoft 365 Defender
description: Wurde etwas verpasst oder fälschlicherweise von Air in Microsoft 365 Defender erkannt? Hier erfahren Sie, wie Sie falsch positive Ergebnisse oder falsch negative Informationen zur Analyse an Microsoft übermitteln.
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
ms.openlocfilehash: 92ad4a96665a5355bce7e3546f8c52779f770927
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843732"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Behandeln von falsch positiven/negativen Ergebnissen in automatisierten Ermittlungs-und Antwortfunktionen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Haben [automatisierte Ermittlungs-und Antwortfunktionen](mtp-autoir.md) in Microsoft 365 Defender das Erkennen von Fehlern vermissen oder etwas falsch erkannt? Es gibt Schritte, die Sie ausführen können, um es zu beheben. Sie können:

- [Melden einer falsch positiven/negativen Meldung an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);

- [Passen Sie Ihre Benachrichtigungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) an (falls erforderlich); und 

- [Rückgängigmachen von auf Geräten ausgeführten Korrekturaktionen](#undo-a-remediation-action-that-was-taken-on-a-device) 

Verwenden Sie diesen Artikel als Leitfaden. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Melden einer falsch positiven/negativen Meldung an Microsoft zur Analyse

|Element verpasst oder falsch erkannt |Dienst  |Vorgehensweise  |
|---------|---------|---------|
|-E-Mail-Nachricht <br/>-E-Mail-Anlage <br/>-URL in einer e-Mail-Nachricht<br/>-URL in einer Office-Datei      |[Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft zur Überprüfung](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Datei oder App auf einem Gerät    |[Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection)         |[Übermitteln einer Datei an Microsoft zur Analyse von Schadsoftware](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden

|Szenario |Dienst |Vorgehensweise |
|--------|--------|--------|
|-Eine Warnung wird durch eine legitime Verwendung ausgelöst. <br/>-Eine Warnung ist falsch    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> oder <br/>[Erkennung erweiterter Azure-Bedrohungen](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Verwalten von Benachrichtigungen im Cloud-App-Sicherheitsportal](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|Eine Datei, IP-Adresse, URL oder Domäne wird auf einem Gerät als Schadsoftware behandelt, auch wenn Sie sicher ist.|[Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection) |[Erstellen eines benutzerdefinierten Indikators mit einer Aktion "zulassen"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Rückgängigmachen einer auf einem Gerät ausgeführten Korrekturaktion

Wenn eine Korrekturaktion auf einem Gerät (beispielsweise einem Windows 10-Gerät) ausgeführt wurde und das Element tatsächlich keine Bedrohung darstellt, kann Ihr Sicherheits Betriebsteam die Korrekturaktion im [Aktionscenter](mtp-action-center.md)rückgängig machen.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie über die [erforderlichen Berechtigungen](mtp-action-center.md#required-permissions-for-action-center-tasks) verfügen, bevor Sie versuchen, die folgende Aufgabe auszuführen.

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 

2. Wählen Sie im Navigationsbereich **Info-Center** aus. 

3. Wählen Sie auf der Registerkarte **Verlauf** eine Aktion aus, die Sie rückgängig machen möchten. Dadurch wird ein Flyout geöffnet.<br/>
    > [!TIP]
    > Verwenden Sie Filter, um die Ergebnisliste einzugrenzen. 

4. Wählen Sie im Flyout für das ausgewählte Element die Option **Untersuchungs Seite öffnen** aus.

5. Wählen Sie in der Ansicht Details der Untersuchung die Registerkarte **Aktionen** aus.

6. Wählen Sie ein Element mit dem Status **abgeschlossen** aus, und suchen Sie in der Spalte **Decisions** nach einem Link, beispielsweise **genehmigt**. Dadurch wird ein Flyout mit weiteren Details zur Aktion geöffnet.

7. Um die Aktion rückgängig zu machen, wählen Sie **Korrektur löschen** aus.

## <a name="see-also"></a>Siehe auch

- [Anzeigen der Details und Ergebnisse einer automatischen Untersuchung](mtp-autoir-results.md)
- [Proaktive Suche nach Bedrohungen durch erweiterte Jagd in Microsoft 365 Defender](advanced-hunting-overview.md)
