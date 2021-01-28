---
title: Melden von Junk- und Phishing-E-Mails in Outlook für iOS und Android
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratoren können sich über die integrierten Junk-E-Mail-, nicht Junk- und Phishing-E-Mail-Berichtsoptionen in Outlook für iOS und Android informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d702ab1d97c07c3e38430a9a7beff5f14db7b60a
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029280"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Melden von Junk- und Phishing-E-Mails in Outlook für iOS und Android in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange [](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)Online oder lokalen Postfächern mit moderner Hybridauthentifizierung können Sie die integrierten Berichtsoptionen in Outlook für iOS und Android verwenden, um falsch positive Ergebnisse (als Spam markierte E-Mails), falsch negative Ergebnisse (ungültige E-Mails sind zulässig) und Phishingnachrichten an Exchange Online Protection (EOP) zu übermitteln.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was müssen Sie wissen, bevor Sie beginnen

- Wenn Sie ein Administrator in einer Organisation mit Exchange Online-Postfächern sind, empfehlen wir die Verwendung des Übermittlungsportals im Security & Compliance Center. Weitere Informationen finden Sie unter "Use Admin Submission", um verdächtige [Spam-, Phishing-, URLs-](admin-submission.md)und Dateien an Microsoft zu übermitteln.

- Sie können gemeldete Nachrichten so konfigurieren, dass sie kopiert oder an ein von Ihnen festgelegtes Postfach umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien.](user-submission.md)

- Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter ["Melden von Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)

  > [!NOTE]
  > Wenn die Junk-E-Mail-Berichterstellung für Outlook in der Benutzerübermittlungsrichtlinie deaktiviert ist, werden Junk- oder Phishingnachrichten in den Junk-E-Mail-Ordner verschoben und nicht an Ihren Administrator oder Microsoft gemeldet.

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a>Melden von Spam- und Phishingnachrichten in Outlook für iOS und Android

Verwenden Sie für Nachrichten im Posteingang oder einem anderen E-Mail-Ordner mit Ausnahme von Junk-E-Mail die folgenden Schritte, um Spam- und Phishingnachrichten für iOS und Android zu melden:

1. Wählen Sie eine oder mehrere Nachrichten aus.
2. Tippen Sie in der oberen rechten Ecke auf die drei vertikalen Punkte. Das Aktionsmenü wird geöffnet.

   ![Melden von Junk- oder Phishing-E-Mails aus dem Aktionsmenü](../../media/Android-report-as-junk-dialog.png)

3. Tippen **Sie auf Junk-E-Mails** melden, und wählen Sie dann **Junk oder** **Phishing aus.**

   ![Melden von Junk- oder Phishing-E-Mails](../../media/Android-report-junk-or-phishing.png)

4. Im angezeigten Dialogfeld können Sie **"Bericht"** oder **"Nein Dank" auswählen.** Wenn Sie **"Nein Danke"** auswählen, wird die Nachricht beim Tippen auf **"Junk"** in den Junk-E-Mail-Ordner verschoben, wenn Sie auf **Phishing** tippen, wird die Nachricht in den Ordner "Gelöschte Elemente" verschoben. Wählen **Sie "Bericht"** aus, um auch eine Kopie der Nachricht an Microsoft zu senden.

   ![Melden von Junk- oder Phishing-E-Mail-Berichtsoptionen](../../media/Android-junk-email-reporting-options.png)

Wenn Sie Ihre Meinung ändern, wählen Sie **"Rückgängig"** in der angezeigten Popupbenachrichtigung aus. Die Nachricht verbleibt im Ordner "Posteingang".

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a>Melden von Nichtspamnachrichten aus dem Junk-E-Mail-Ordner in Outlook für iOS und Android

Verwenden Sie im Junk-E-Mail-Ordner die folgenden Schritte, um falsch positive Spamnachrichten zu melden:

1. Wählen Sie eine oder mehrere Nachrichten aus.
2. Tippen Sie in der oberen rechten Ecke auf die drei vertikalen Punkte. Das Aktionsmenü wird geöffnet.

   ![Melden sie keine Junk-E-Mails aus dem Aktionsmenü.](../../media/Android-not-junk-email.png)

3. Tippen Sie **auf "Kein Junk".**

Es wird eine Popupbenachrichtigung angezeigt, dass die E-Mail in Ihren Posteingang verschoben wurde. Wenn Sie Ihre Meinung ändern, wählen Sie **"Rückgängig"** in der Popupbenachrichtigung aus. Die E-Mail verbleibt im Junk-Ordner.
