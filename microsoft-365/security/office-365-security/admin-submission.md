---
title: Übermittlungen von Administratoren in Office 365, O365-Übermittlungen, Office 365 Spam Problem, O365 falsch negativ, Phishing in Office 365, Senden von e-Mails zum Scannen, verdächtige e-Mails in Office 365, e-Mails scannen, Microsoft-Scan für Phishing, Microsoft-Scan für Spam, Submit e-Mail, e-Mail senden, zwielichtige e-Mail, fehlerhafte Darsteller e-Mail, verdächtige, nicht vertrauenswürdige e-Mails, Phishing-e-Mails an Microsoft melden, Phishing-e-Mails an Microsoft melden, böswillige e-Mails an Microsoft melden, Scam-e-Mails an Microsoft melden, Schadsoftware in e-Mail an Microsoft, Spam melden e-Mail im Posteingang Office 365, Virus in e-Mail Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie verdächtige e-Mails, verdächtige Phishing-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und Dateien von Ihrem Office 365-Mandanten zur Überprüfung an Microsoft übermitteln.
ms.openlocfilehash: 539d09f03a8a9c5956f2d1e3584f893b0e4ffbb4
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033614"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Verwenden der Administrator Übermittlung zum Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft

Wenn Sie ein Administrator in einer Office 365 Organisation mit Postfächern in Exchange Online sind, können Sie das Übermittlungen-Portal im Office 365 Security & Compliance Center verwenden, um e-Mail-Nachrichten, URLs und Anlagen für die Überprüfung an Microsoft zu übermitteln.

Wenn Sie eine e-Mail übermitteln, erhalten Sie Informationen zu allen Richtlinien, die möglicherweise die eingehenden e-Mails in ihren Mandanten zugelassen haben, sowie über die Untersuchung von URLs und Anlagen in der e-Mail. Richtlinien, die möglicherweise eine e-Mail erlaubt haben, enthalten die Liste sicherer Absender eines einzelnen Benutzers sowie Richtlinien auf Mandantenebene wie Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln).

Weitere Möglichkeiten zum Übermitteln von e-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter 

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur **Übermittlungs** Seite wechseln möchten <https://protection.office.com/reportsubmission>, verwenden Sie.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Zum Hinzufügen, ändern und Löschen von Anti-Spam-Richtlinien müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung**", " **Sicherheits Administrator**" oder " **Sicherheits Leser** " sein. Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Weitere Informationen darüber, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a>Vorgehensweise zum direkten verdächtigen von Inhalten an Microsoft für Office 365-Scans

Um Inhalte an Microsoft zu übermitteln, klicken Sie auf die Schaltfläche **neue Übermittlung** in der linken oberen Ecke der Seite Übermittlungen. Ein Flyout auf der rechten Seite der Seite wird mit der Option zum Senden einer e-Mail, einer URL oder einer Datei angezeigt.

### <a name="submit-a-questionable-email-to-microsoft"></a>Senden einer fragwürdigen e-Mail an Microsoft

![Beispiel für eine e-Mail-Übermittlung](../../media/submission-flyout-email.PNG)

1. Um eine e-Mail zu senden, wählen Sie **e-Mail** und geben Sie die e-Mail- **Netzwerknachrichten-ID** an, oder laden Sie die e-Mail-Datei

2. Geben Sie die Empfänger an, für die Sie die Richtlinienüberprüfung ausführen möchten. Durch die Richtlinienüberprüfung wird ermittelt, ob die e-Mail-Überprüfung aufgrund von Richtlinien auf Benutzer-oder Mandantenebene umgangen wurde.

3. Geben Sie an, ob die e-Mail-Nachricht blockiert werden sollte. Wenn die e-Mail blockiert wurde, geben Sie an, ob Sie als Spam, Phishing oder Schadsoftware blockiert werden soll. Wenn Sie nicht sicher sind, welche Art Sie haben könnten, verwenden Sie Ihr Bestes Urteil.

   - Wenn der Filter aufgrund von Richtlinien bei der Übermittlung umgangen wurde, werden Informationen zu dieser Richtlinie angezeigt.

   - Wenn der Filter aufgrund einer oder mehrerer Richtlinien nicht umgangen wurde, wird die Überprüfung in einigen Minuten abgeschlossen. Sie erhalten zusätzliche Informationen über die Übermittlung, indem Sie auf den Link Status klicken. Dies beinhaltet die Ergebnisse der Richtlinienüberprüfung und das Ergebnis der erneuten Überprüfung. Hinweis Dadurch wird die e-Mail-Nachricht nicht über den Office 365 ATP-voll Filter Stapel erneut ausgeführt, es wird jedoch ein partieller erneuter Scan auf der Grundlage bestimmter Attribute der e-Mail, der URL oder der Datei ausgeführt.

4. Klicken Sie auf die Schaltfläche **Absenden** .

### <a name="send-a-suspect-url-to-microsoft"></a>Senden einer verdächtigen URL an Microsoft

![Beispiel für eine e-Mail-Übermittlung](../../media/submission-url-flyout.png)

1. So übermitteln Sie eine URL wählen Sie **URL** aus dem Flyout aus. Geben Sie die vollständige URL einschließlich des Protokolls (**https://**) ein.

   Wenn Sie die Option **gefiltert haben ausgewählt haben**, geben Sie an, ob die URL Phishing oder Schadsoftware ist.

2. Klicken Sie auf die Schaltfläche **Absenden** .

### <a name="submit-a-suspected-file-to-microsoft"></a>Übermitteln einer vermuteten Datei an Microsoft

![Beispiel für eine e-Mail-Übermittlung](../../media/submission-file-flyout.PNG)

1. Um eine Datei zu übermitteln, wählen Sie **Datei** aus dem Flyout aus, und laden Sie die Datei hoch, die Sie überprüfen möchten.

2. Klicken Sie auf die Schaltfläche **Absenden** .
