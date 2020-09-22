---
title: Melden von Junk-und Phishing-e-Mails in Outlook für IOS und Android
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratoren können Informationen zu den integrierten Junk-, nicht Junk-und Phishing-e-Mail-Berichtoptionen in Outlook für IOS und Android erhalten.
ms.openlocfilehash: fef519f3fdd5cf46d383c41ad227ab0cd3ed4390
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201533"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="514bb-103">Melden von Junk-und Phishing-e-Mails in Outlook für IOS und Android in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="514bb-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="514bb-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder lokalen Postfächern mithilfe der [modernen Hybrid Authentifizierung](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview?view=o365-worldwide)können Sie die integrierten Berichtsoptionen in Outlook für IOS und Android verwenden, um falsch positive Ergebnisse (gute e-Mail-Nachrichten als Spam gekennzeichnet), falsche Negative Zeichen (ungültige e-Mail-Nachricht) und Phishing-Nachrichten an Exchange Online Protection (EoP) zu senden.</span><span class="sxs-lookup"><span data-stu-id="514bb-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview?view=o365-worldwide), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="514bb-105">Was müssen Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="514bb-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="514bb-106">Wenn Sie ein Administrator in einer Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungen-Portal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="514bb-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="514bb-107">Weitere Informationen finden Sie unter [Verwenden der Administrator Übermittlung zum Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="514bb-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="514bb-108">Sie können gemeldete Nachrichten so konfigurieren, dass Sie kopiert oder an ein von Ihnen angegebenes Postfach umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="514bb-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="514bb-109">Weitere Informationen finden Sie unter [Angeben eines Postfachs für Benutzer Übermittlungen von Spam-und Phishing-Nachrichten in Exchange Online](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="514bb-109">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="514bb-110">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="514bb-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="514bb-111">Wenn die Junk-e-Mail-Berichterstellung für Outlook in der Richtlinie für die Benutzer Übermittlung deaktiviert ist, werden Junk-oder Phishing-Nachrichten in den Ordner Junk verschoben und nicht an Ihren Administrator oder Microsoft gemeldet.</span><span class="sxs-lookup"><span data-stu-id="514bb-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="514bb-112">Melden von Spam-und Phishing-Nachrichten in Outlook für IOS und Android</span><span class="sxs-lookup"><span data-stu-id="514bb-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="514bb-113">Für Nachrichten im Posteingang oder in einem anderen e-Mail-Ordner mit Ausnahme von Junk-e-Mails führen Sie die folgenden Schritte aus, um Spam-und Phishing-Nachrichten für IOS und Android zu melden:</span><span class="sxs-lookup"><span data-stu-id="514bb-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="514bb-114">Wählen Sie eine oder mehrere Nachrichten aus.</span><span class="sxs-lookup"><span data-stu-id="514bb-114">Select one or more messages.</span></span>
2. <span data-ttu-id="514bb-115">Tippen Sie in der oberen rechten Ecke auf die drei vertikalen Punkte.</span><span class="sxs-lookup"><span data-stu-id="514bb-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="514bb-116">Das Menü Aktion wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="514bb-116">The action menu opens.</span></span>

   ![Melden von Junk-oder Phishing-e-Mails im Aktionsmenü](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="514bb-118">Tippen Sie auf **Junk-e-Mail melden** und dann auf **Junk** oder **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="514bb-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Melden von Junk-oder Phishing-e-Mails](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="514bb-120">Im angezeigten Dialogfeld können Sie " **Bericht** " oder " **Nein Danke**" auswählen.</span><span class="sxs-lookup"><span data-stu-id="514bb-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="514bb-121">Wenn Sie auf **Junk** -e-Mails **tippen, wird**die Nachricht in den Ordner Junk-e-Mail verschoben, wenn Sie auf **Phishing** tippen, wird die Nachricht in den Ordner Gelöschte Elemente verschoben.</span><span class="sxs-lookup"><span data-stu-id="514bb-121">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="514bb-122">Wählen Sie **Bericht** aus, um auch eine Kopie der Nachricht an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="514bb-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Melden von Junk-oder Phishing-e-Mail-Optionen](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="514bb-124">Wenn Sie Ihre Meinung ändern, wählen Sie in der angezeigten Popupbenachrichtigung **rückgängig machen** aus.</span><span class="sxs-lookup"><span data-stu-id="514bb-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="514bb-125">Die Nachricht verbleibt im Ordner Posteingang.</span><span class="sxs-lookup"><span data-stu-id="514bb-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="514bb-126">Melden von nicht-Spam-Nachrichten aus dem Junk-Ordner in Outlook für IOS und Android</span><span class="sxs-lookup"><span data-stu-id="514bb-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="514bb-127">Verwenden Sie im Ordner Junk die folgenden Schritte, um Spam-falsch positive Ergebnisse zu melden:</span><span class="sxs-lookup"><span data-stu-id="514bb-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="514bb-128">Wählen Sie eine oder mehrere Nachrichten aus.</span><span class="sxs-lookup"><span data-stu-id="514bb-128">Select one or more messages.</span></span>
2. <span data-ttu-id="514bb-129">Tippen Sie in der oberen rechten Ecke auf die drei vertikalen Punkte.</span><span class="sxs-lookup"><span data-stu-id="514bb-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="514bb-130">Das Menü Aktion wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="514bb-130">The action menu opens.</span></span>

   ![Melden von Junk-e-Mails im Aktionsmenü](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="514bb-132">Tippen Sie auf **kein Junk**.</span><span class="sxs-lookup"><span data-stu-id="514bb-132">Tap **Not junk**.</span></span>

<span data-ttu-id="514bb-133">Eine Popup-Benachrichtigung wird angezeigt, dass die e-Mail in Ihren Posteingang verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="514bb-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="514bb-134">Wenn Sie Ihre Meinung ändern, wählen Sie in der Popupbenachrichtigung **rückgängig machen** aus.</span><span class="sxs-lookup"><span data-stu-id="514bb-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="514bb-135">Die e-Mail verbleibt im Ordner Junk.</span><span class="sxs-lookup"><span data-stu-id="514bb-135">The email remains in the Junk folder.</span></span>
