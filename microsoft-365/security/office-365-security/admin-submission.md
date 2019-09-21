---
title: Übermittlungen von Administratoren in Office 365, O365-Übermittlungen, Office 365 Spam Problem, O365 falsch negativ, Phishing in Office 365, Senden von e-Mails zum Scannen, verdächtige e-Mails in Office 365, e-Mails scannen, Microsoft-Scan für Phishing, Microsoft-Scan für Spam, Submit e-Mail, e-Mail senden
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie verdächtige e-Mails, verdächtige Phishing-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und Dateien von Ihrem Office 365-Mandanten zur Überprüfung an Microsoft übermitteln.
ms.openlocfilehash: 5ca5eab2feab1243a83eb60c9320fd48dfb59f12
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082731"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a>Vorgehensweise übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft für Office 365-Scans

Administratoren können e-Mails mithilfe von Datei-oder Netzwerknachrichten-ID, URLs und Dateien für die Überprüfung durch Microsoft in Office 365 senden. Der Abschnitt aktualisierte Übermittlungen enthält weiterhin von Benutzern gemeldete Nachrichten und steht allen Kunden mit EoP zur Verfügung.

Wenn Sie eine e-Mail übermitteln, erhalten Sie Informationen zu allen Richtlinien, die möglicherweise die eingehenden e-Mails in ihren Mandanten zugelassen haben, sowie über die Untersuchung von URLs und Anlagen in der e-Mail. Richtlinien, die möglicherweise eine e-Mail zugelassen haben, enthalten die Liste sicherer Absender eines einzelnen Benutzers sowie Richtlinien auf Mandantenebene wie ETR-Regeln. 

## <a name="how-to-submit-content-to-microsoft-for-office-365-scanning"></a>Vorgehensweise zum Übermitteln von Inhalten an Microsoft für Office 365-Scans

Um Inhalte an Microsoft zu übermitteln, klicken Sie auf die Schaltfläche **neue Übermittlung** in der linken oberen Ecke der Seite Übermittlungen. Ein Flyout auf der rechten Seite der Seite wird mit der Option zum Senden einer e-Mail, einer URL oder einer Datei angezeigt. 

### <a name="submit-an-email-to-microsoft"></a>Senden einer e-Mail an Microsoft
![Beispiel für eine e-Mail-Übermittlung](../media/submission-flyout-email.PNG)
1. Um eine e-Mail zu senden, wählen Sie **e-Mail** und geben Sie die e-Mail- **Netzwerknachrichten-ID** an, oder laden Sie die e-Mail-Datei 

2. Geben Sie die Empfänger an, für die Sie die Richtlinienüberprüfung ausführen möchten. Durch die Richtlinienüberprüfung wird ermittelt, ob die e-Mail-Überprüfung aufgrund von Richtlinien auf Benutzer-oder Mandantenebene umgangen wurde. 

3. Geben Sie an, ob die e-Mail-Nachricht blockiert werden sollte. Wenn die e-Mail blockiert wurde, geben Sie an, ob Sie als Spam, Phishing oder Schadsoftware blockiert werden soll. Wenn Sie nicht sicher sind, welche Art Sie haben könnten, verwenden Sie Ihr Bestes Urteil.  

* Wenn der Filter aufgrund von Richtlinien bei der Übermittlung umgangen wurde, werden Informationen zu dieser Richtlinie angezeigt.

* Wenn der Filter aufgrund einer oder mehrerer Richtlinien nicht umgangen wurde, wird die Überprüfung in einigen Minuten abgeschlossen. Sie erhalten zusätzliche Informationen über die Übermittlung, indem Sie auf den Link Status klicken. Dies beinhaltet die Ergebnisse der Richtlinienüberprüfung und das Ergebnis der erneuten Überprüfung. Hinweis Dadurch wird die e-Mail-Nachricht nicht über den Office 365 ATP-voll Filter Stapel erneut ausgeführt, es wird jedoch ein partieller erneuter Scan auf der Grundlage bestimmter Attribute der e-Mail, der URL oder der Datei ausgeführt. 

4. Klicken Sie auf die Schaltfläche **Absenden** .

### <a name="submit-a-url-to-microsoft"></a>Übermitteln einer URL an Microsoft
![Beispiel für eine e-Mail-Übermittlung](../media/submission-url-flyout.png)
1. So übermitteln Sie eine URL wählen Sie **URL** aus dem Flyout aus. Geben Sie die vollständige URL einschließlich des Protokolls (**https://**) ein. 

* Wenn Sie die Option **gefiltert haben ausgewählt haben**, geben Sie an, ob die URL Phishing oder Schadsoftware ist.

2. Klicken Sie auf die Schaltfläche **Absenden** . 


### <a name="submit-a-file-to-microsoft"></a>Senden einer Datei an Microsoft
![Beispiel für eine e-Mail-Übermittlung](../media/submission-file-flyout.PNG)
1. Um eine Datei zu übermitteln, wählen Sie **Datei** aus dem Flyout aus, und laden Sie die Datei hoch, die Sie überprüfen möchten. 

2. Klicken Sie auf die Schaltfläche **Absenden** .


## <a name="related-topics"></a>Verwandte Themen

[Office 365 Advanced Threat Protection-Plan 2](office-365-ti.md)
  
[Schutz vor Bedrohungen in Office 365](protect-against-threats.md)
  
[Anzeigen von Berichten für Office 365 Advanced Threat Protection](view-reports-for-atp.md)
  

