---
title: Melden von Junk-E-Mails an Microsoft
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 'Das Microsoft-Add-In "Junk-E-Mail-Berichtsprogramm für Microsoft Office Outlook" bietet mehrere Möglichkeiten zum Melden von Junk-E-Mails:'
ms.openlocfilehash: 3f8d07a2499fa3c8690393aa444e018b83c632b1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088249"
---
# <a name="report-junk-email-messages-to-microsoft"></a>Melden von Junk-E-Mails an Microsoft

Das Microsoft-Add-In "Junk-E-Mail-Berichtsprogramm für Microsoft Office Outlook" bietet mehrere Möglichkeiten zum Melden von Junk-E-Mails:

- Über das Outlook-Menüband

- Über den Posteingang

- Aus einer geöffneten E-Mail

Mit dem Add-In Junk-E-Mail-Berichtsprogramm können Sie Berichte an den Microsoft gesendet Exchange Online Protection (EOP)-Dienst senden. Wenn Ihr Postfach nicht vom Dienst geschützt ist, haben Ihre Übermittlungen von Junk-E-Mail-Berichten keine Auswirkungen auf Ihren Spamfilter. Administratoren können mehr über Spameinstellungen erfahren, die für eine ganze Organisation gelten, indem Sie verhindern, dass [gute e-Mails in Office 365 als Spam markiert werden](prevent-email-from-being-marked-as-spam.md) , oder [wie Sie Spam-e-Mails in Office 365 reduzieren](reduce-spam-email.md). Diese sind hilfreich, wenn Sie über die Steuerung auf Administratorebene verfügen und wenn Sie falsch positive Ergebnisse oder falsch negative Ergebnisse vermeiden möchten.

> [!TIP]
> Sie können auch Spamnachrichten direkt an Microsoft übermitteln, indem Sie die [Junk@office365.Microsoft.com](mailto:junk@office365.microsoft.com) -e-Mail-Adresse und falsch positive (nicht-Spam)-Nachrichten mithilfe der [not_junk@office365.Microsoft.com](mailto:not_junk@office365.microsoft.com) -e-Mail-Adresse verwenden. Weitere Informationen finden Sie unter [Übermitteln von Spam-, Nicht-Spamnachrichten und Nachrichten, die als betrügerische Phishing-Angriffe angesehen werden, an Microsoft zur Analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

### <a name="to-report-junk-email-messages-from-outlook"></a>So melden Sie Junk-e-Mails in Outlook

[Verwenden des Add-Ins "Berichtsnachricht"](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

### <a name="to-report-junk-email-messages-from-your-inbox"></a>So melden Sie Junk-E-Mails über den Posteingang

1. Klicken Sie mit der rechten Maustaste auf die Nachricht(en), die Sie als Junk melden möchten.

2. Wählen Sie **Junk**, und klicken Sie dann auf **Junk-E-Mails melden**.
    ![Melden von Junk-E-Mails über den Posteingang](../../media/EOP-Outlook-Junk-Reporting-Tool-3.jpg)

3. Das Dialogfeld **Microsoft-Add-In "Junk-E-Mail-Berichtsprogramm für Microsoft Office Outlook"** wird geöffnet. Wenn Sie sicher sind, dass Sie die als Junk ausgewählten Nachrichten senden möchten, klicken Sie auf **Ja**.
    ![Meldung als Junk bestätigen](../../media/EOP-Outlook-Junk-Reporting-Tool-2.jpg)

    > [!NOTE]
    > Wenn Sie die Bestätigungsmeldung, die daraufhin angezeigt wird, in Zukunft nicht mehr erhalten möchten, aktivieren Sie **Diese Meldung nicht mehr anzeigen**.

Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und in den Ordner "Junk-E-Mail" verschoben. Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.

### <a name="to-report-a-junk-email-message-from-within-an-opened-message"></a>So melden Sie eine Junk-E-Mail aus einer geöffneten Nachricht

1. Klicken Sie in der geöffneten Nachricht im Nachrichtenband auf **Junk-E-Mails melden**. Klicken Sie beispielsweise **auf** \> Junk- **Report** ![-Junk-e-Mail-Junk-e-Mails in einer Nachricht](../../media/EOP-Outlook-Junk-Reporting-Tool-4.jpg)

2. Das Dialogfeld **Microsoft-Add-In "Junk-E-Mail-Berichtsprogramm für Microsoft Office Outlook"** wird geöffnet. Wenn Sie sicher sind, dass Sie die als Junk ausgewählten Nachricht senden möchten, klicken Sie auf **Ja**.
    ![Meldung als Junk bestätigen](../../media/EOP-Outlook-Junk-Reporting-Tool-2.jpg)

    > [!NOTE]
    > Wenn Sie die Bestätigungsmeldung, die daraufhin angezeigt wird, in Zukunft nicht mehr erhalten möchten, aktivieren Sie **Diese Meldung nicht mehr anzeigen**.

Die ausgewählte Nachricht wird zur Analyse an Microsoft gesendet und in den Ordner "Junk-E-Mail" verschoben. Wenn Sie überprüfen möchten, ob die Nachricht gesendet wurde, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendete Nachricht angezeigt werden sollte.

## <a name="for-more-information"></a>Weitere Informationen

[Aktivieren des Berichtsnachrichts-Add-Ins](enable-the-report-message-add-in.md)

[Problembehandlung und Supportinformationen](troubleshooting-and-support-information.md)

[Verhindern, dass echte E-Mails in Office 365 als Spam gekennzeichnet werden](prevent-email-from-being-marked-as-spam.md)

[Reduzieren von Spam-E-Mails in Office 365](reduce-spam-email.md)
