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
ms.openlocfilehash: 58027f7589280b1266cddc8cfbf44db9e4f0ece4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166819"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="ef622-103">Melden von Junk- und Phishing-E-Mails in Outlook für iOS und Android in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ef622-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ef622-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="ef622-104">**Applies to**</span></span>
- [<span data-ttu-id="ef622-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ef622-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="ef622-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="ef622-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="ef622-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef622-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="ef622-108">In Microsoft 365-Organisationen mit Postfächern in Exchange [](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)Online oder lokalen Postfächern mit moderner Hybridauthentifizierung können Sie die integrierten Berichtsoptionen in Outlook für iOS und Android verwenden, um falsch positive Ergebnisse (als Spam markierte E-Mails), falsch negative Ergebnisse (ungültige E-Mails sind zulässig) und Phishingnachrichten an Exchange Online Protection (EOP) zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="ef622-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ef622-109">Was müssen Sie wissen, bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="ef622-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="ef622-110">Wenn Sie ein Administrator in einer Organisation mit Exchange Online-Postfächern sind, empfehlen wir die Verwendung des Übermittlungsportals im Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ef622-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="ef622-111">Weitere Informationen finden Sie unter "Use Admin Submission", um verdächtige [Spam-, Phishing-, URLs-](admin-submission.md)und Dateien an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="ef622-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="ef622-112">Sie können gemeldete Nachrichten so konfigurieren, dass sie kopiert oder an ein von Ihnen festgelegtes Postfach umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ef622-112">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="ef622-113">Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="ef622-113">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="ef622-114">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter ["Melden von Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ef622-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="ef622-115">Wenn die Junk-E-Mail-Berichterstellung für Outlook in der Benutzerübermittlungsrichtlinie deaktiviert ist, werden Junk- oder Phishingnachrichten in den Junk-E-Mail-Ordner verschoben und nicht an Ihren Administrator oder Microsoft gemeldet.</span><span class="sxs-lookup"><span data-stu-id="ef622-115">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="ef622-116">Melden von Spam- und Phishingnachrichten in Outlook für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="ef622-116">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="ef622-117">Verwenden Sie für Nachrichten im Posteingang oder einem anderen E-Mail-Ordner mit Ausnahme von Junk-E-Mail die folgenden Schritte, um Spam- und Phishingnachrichten für iOS und Android zu melden:</span><span class="sxs-lookup"><span data-stu-id="ef622-117">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="ef622-118">Wählen Sie eine oder mehrere Nachrichten aus.</span><span class="sxs-lookup"><span data-stu-id="ef622-118">Select one or more messages.</span></span>
2. <span data-ttu-id="ef622-119">Tippen Sie in der oberen rechten Ecke auf die drei vertikalen Punkte.</span><span class="sxs-lookup"><span data-stu-id="ef622-119">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="ef622-120">Das Aktionsmenü wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ef622-120">The action menu opens.</span></span>

   ![Melden von Junk- oder Phishing-E-Mails aus dem Aktionsmenü](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="ef622-122">Tippen **Sie auf Junk-E-Mails** melden, und wählen Sie dann **Junk oder** **Phishing aus.**</span><span class="sxs-lookup"><span data-stu-id="ef622-122">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Melden von Junk- oder Phishing-E-Mails](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="ef622-124">Im angezeigten Dialogfeld können  Sie "Bericht" oder **"Nein Dank" auswählen.**</span><span class="sxs-lookup"><span data-stu-id="ef622-124">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="ef622-125">Wenn Sie **"Nein Danke"** auswählen, wird die Nachricht beim Tippen auf **"Junk"** in den Junk-E-Mail-Ordner verschoben, wenn Sie auf **Phishing** tippen, wird die Nachricht in den Ordner "Gelöschte Elemente" verschoben.</span><span class="sxs-lookup"><span data-stu-id="ef622-125">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="ef622-126">Wählen **Sie "Bericht"** aus, um auch eine Kopie der Nachricht an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="ef622-126">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Melden von Junk- oder Phishing-E-Mail-Berichtsoptionen](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="ef622-128">Wenn Sie Ihre Meinung ändern, wählen Sie **"Rückgängig"** in der angezeigten Popupbenachrichtigung aus.</span><span class="sxs-lookup"><span data-stu-id="ef622-128">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="ef622-129">Die Nachricht verbleibt im Ordner "Posteingang".</span><span class="sxs-lookup"><span data-stu-id="ef622-129">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="ef622-130">Melden von Nichtspamnachrichten aus dem Junk-E-Mail-Ordner in Outlook für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="ef622-130">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="ef622-131">Verwenden Sie im Junk-E-Mail-Ordner die folgenden Schritte, um falsch positive Spamnachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="ef622-131">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="ef622-132">Wählen Sie eine oder mehrere Nachrichten aus.</span><span class="sxs-lookup"><span data-stu-id="ef622-132">Select one or more messages.</span></span>
2. <span data-ttu-id="ef622-133">Tippen Sie in der oberen rechten Ecke auf die drei vertikalen Punkte.</span><span class="sxs-lookup"><span data-stu-id="ef622-133">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="ef622-134">Das Aktionsmenü wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ef622-134">The action menu opens.</span></span>

   ![Melden von Junk-E-Mails aus dem Aktionsmenü](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="ef622-136">Tippen Sie **auf "Kein Junk".**</span><span class="sxs-lookup"><span data-stu-id="ef622-136">Tap **Not junk**.</span></span>

<span data-ttu-id="ef622-137">Es wird eine Popupbenachrichtigung angezeigt, dass die E-Mail in Ihren Posteingang verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="ef622-137">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="ef622-138">Wenn Sie Ihre Meinung ändern, wählen Sie **"Rückgängig"** in der Popupbenachrichtigung aus.</span><span class="sxs-lookup"><span data-stu-id="ef622-138">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="ef622-139">Die E-Mail verbleibt im Junk-Ordner.</span><span class="sxs-lookup"><span data-stu-id="ef622-139">The email remains in the Junk folder.</span></span>
