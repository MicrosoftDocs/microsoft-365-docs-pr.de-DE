---
title: Melden von Junk-und Phishing-e-Mails in Outlook für IOS und Android
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratoren können Informationen zu den integrierten Junk-, nicht Junk-und Phishing-e-Mail-Berichtoptionen in Outlook für IOS und Android erhalten.
ms.openlocfilehash: 1c842ac5349f9c2804c637fa4c5598b06e8f489f
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877291"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Melden von Junk-und Phishing-e-Mails in Outlook für IOS und Android in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder lokalen Postfächern mithilfe der [modernen Hybrid Authentifizierung](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)können Sie die integrierten Berichtsoptionen in Outlook für IOS und Android verwenden, um falsch positive Ergebnisse (gute e-Mail-Nachrichten als Spam gekennzeichnet), falsche Negative Zeichen (ungültige e-Mail-Nachricht) und Phishing-Nachrichten an Exchange Online Protection (EoP) zu senden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was müssen Sie wissen, bevor Sie beginnen?

- Wenn Sie ein Administrator in einer Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungen-Portal im Security & Compliance Center zu verwenden. Weitere Informationen finden Sie unter [Verwenden der Administrator Übermittlung zum Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft](admin-submission.md).

- Sie können gemeldete Nachrichten so konfigurieren, dass Sie kopiert oder an ein von Ihnen angegebenes Postfach umgeleitet werden. Weitere Informationen finden Sie unter [User Submissions Policies](user-submission.md).

- Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

  > [!NOTE]
  > Wenn die Junk-e-Mail-Berichterstellung für Outlook in der Richtlinie für die Benutzer Übermittlung deaktiviert ist, werden Junk-oder Phishing-Nachrichten in den Ordner Junk verschoben und nicht an Ihren Administrator oder Microsoft gemeldet.

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a>Melden von Spam-und Phishing-Nachrichten in Outlook für IOS und Android

Für Nachrichten im Posteingang oder in einem anderen e-Mail-Ordner mit Ausnahme von Junk-e-Mails führen Sie die folgenden Schritte aus, um Spam-und Phishing-Nachrichten für IOS und Android zu melden:

1. Wählen Sie eine oder mehrere Nachrichten aus.
2. Tippen Sie in der oberen rechten Ecke auf die drei vertikalen Punkte. Das Menü Aktion wird geöffnet.

   ![Melden von Junk-oder Phishing-e-Mails im Aktionsmenü](../../media/Android-report-as-junk-dialog.png)

3. Tippen Sie auf **Junk-e-Mail melden** und dann auf **Junk** oder **Phishing**.

   ![Melden von Junk-oder Phishing-e-Mails](../../media/Android-report-junk-or-phishing.png)

4. Im angezeigten Dialogfeld können Sie " **Bericht** " oder " **Nein Danke** " auswählen. Wenn Sie auf **Junk** -e-Mails **tippen, wird** die Nachricht in den Ordner Junk-e-Mail verschoben, wenn Sie auf **Phishing** tippen, wird die Nachricht in den Ordner Gelöschte Elemente verschoben. Wählen Sie **Bericht** aus, um auch eine Kopie der Nachricht an Microsoft zu senden.

   ![Melden von Junk-oder Phishing-e-Mail-Optionen](../../media/Android-junk-email-reporting-options.png)

Wenn Sie Ihre Meinung ändern, wählen Sie in der angezeigten Popupbenachrichtigung **rückgängig machen** aus. Die Nachricht verbleibt im Ordner Posteingang.

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a>Melden von nicht-Spam-Nachrichten aus dem Junk-Ordner in Outlook für IOS und Android

Verwenden Sie im Ordner Junk die folgenden Schritte, um Spam-falsch positive Ergebnisse zu melden:

1. Wählen Sie eine oder mehrere Nachrichten aus.
2. Tippen Sie in der oberen rechten Ecke auf die drei vertikalen Punkte. Das Menü Aktion wird geöffnet.

   ![Melden von Junk-e-Mails im Aktionsmenü](../../media/Android-not-junk-email.png)

3. Tippen Sie auf **kein Junk**.

Eine Popup-Benachrichtigung wird angezeigt, dass die e-Mail in Ihren Posteingang verschoben wurde. Wenn Sie Ihre Meinung ändern, wählen Sie in der Popupbenachrichtigung **rückgängig machen** aus. Die e-Mail verbleibt im Ordner Junk.
