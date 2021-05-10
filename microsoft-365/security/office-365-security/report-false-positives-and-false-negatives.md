---
title: Melden falsch positiver und falsch negativer Ergebnisse in Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie falsch positive und falsch negative Outlook mit dem Feature Berichtsnachricht melden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e848595035501f5da7b6099efd2700ebac6f17e3
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291163"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a>Melden falsch positiver und falsch negativer Ergebnisse in Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Wenn Sie ein Administrator in einer Microsoft 365 mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden. Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder lokalen Postfächern mit moderner Hybridauthentifizierung können Sie falsch positive Ergebnisse (gute E-Mails, die blockiert oder an Junkordner gesendet wurden) und falsch negative (unerwünschte E-Mails oder Phishing, die an den Posteingang übermittelt wurden) an Exchange Online Protection (EOP) übermitteln.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Verwenden Sie das Add-In Nachricht melden oder das Phishing-Add-In melden, um eine optimale Benutzerübermittlung zu ermöglichen.

- Beachten Sie, dass dieses Add-In für Outlook Plattformen funktioniert – im Web, iOS, Android und Desktop.

- Wenn Sie ein Administrator in einer Organisation mit Exchange Online sind, verwenden Sie das Übermittlungsportal im Security & Compliance Center. Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

- Sie können konfigurieren, dass Nachrichten direkt an Microsoft, ein von Ihnen festgelegtes Postfach oder beides gesendet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien](user-submission.md).

- Weitere Informationen zum Erhalten und Aktivieren der Berichtsnachricht oder der Phishing-Add-Ins melden finden Sie unter [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).

- Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="use-the-report-message-feature"></a>Verwenden des Berichtsnachrichtenfeatures

### <a name="report-junk-and-phishing-messages"></a>Melden von Junk- und Phishingnachrichten

Verwenden Sie für Nachrichten im Posteingang oder in einem anderen E-Mail-Ordner mit Ausnahme von Junk-E-Mails die folgende Methode, um Spam- und Phishingnachrichten zu melden:

1. Klicken Sie **in der** oberen rechten Ecke der ausgewählten  Nachricht auf die Ellipsen Weitere Aktionen, klicken Sie im Dropdownmenü auf Nachricht melden, und wählen Sie **dann Junk** oder **Phishing aus.**
  
   > [!div class="mx-imgBorder"]
   > ![Berichtsnachricht – Weitere Aktionen](../../media/report-message-more-actions.png)

   > [!div class="mx-imgBorder"]
   > ![Berichtsnachricht – Junk und Phishing](../../media/report-message-junk-phishing.png)

2. Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und:

   - In den Junk-E-Mail-Ordner verschoben, wenn er als Spam gemeldet wurde.

   - Gelöscht, wenn es als Phishing gemeldet wurde.
   
### <a name="report-messages-that-are-not-junk"></a>Melden von Nachrichten, die kein Junk sind

1. Klicken Sie **in der** oberen rechten Ecke der ausgewählten  Nachricht auf die Ellipsen Weitere Aktionen, klicken Sie im Dropdownmenü auf Nachricht melden, und klicken Sie dann auf **Nicht Junk**.  

   > [!div class="mx-imgBorder"]
   > ![Berichtsnachricht – Weitere Aktionen](../../media/report-message-more-actions.png)

   > [!div class="mx-imgBorder"]
   > ![Berichtsnachricht – Kein Junk](../../media/report-message-not-junk.png)

2. Die ausgewählte Nachricht wird zur Analyse an Microsoft gesendet und in den Posteingang oder einen anderen angegebenen Ordner verschoben.

## <a name="view-and-review-reported-messages"></a>Anzeigen und Überprüfen von gemeldeten Nachrichten

Zum Überprüfen von Nachrichten, die Benutzer an Microsoft melden, haben Sie die folgenden Optionen:

- Verwenden Sie das Administrator-Übermittlungsportal. Weitere Informationen finden Sie unter [Anzeigen von Benutzerübermittlungen an Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Erstellen Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet), um Kopien von gemeldeten Nachrichten zu senden. Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, was Ihre Benutzer an Microsoft melden.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)