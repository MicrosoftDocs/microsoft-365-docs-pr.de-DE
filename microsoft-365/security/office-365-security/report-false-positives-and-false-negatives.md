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
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="42917-103">Melden falsch positiver und falsch negativer Ergebnisse in Outlook</span><span class="sxs-lookup"><span data-stu-id="42917-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="42917-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="42917-104">**Applies to**</span></span>
- [<span data-ttu-id="42917-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="42917-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="42917-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="42917-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="42917-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42917-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="42917-108">Wenn Sie ein Administrator in einer Microsoft 365 mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="42917-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="42917-109">Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="42917-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="42917-110">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder lokalen Postfächern mit moderner Hybridauthentifizierung können Sie falsch positive Ergebnisse (gute E-Mails, die blockiert oder an Junkordner gesendet wurden) und falsch negative (unerwünschte E-Mails oder Phishing, die an den Posteingang übermittelt wurden) an Exchange Online Protection (EOP) übermitteln.</span><span class="sxs-lookup"><span data-stu-id="42917-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="42917-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="42917-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="42917-112">Verwenden Sie das Add-In Nachricht melden oder das Phishing-Add-In melden, um eine optimale Benutzerübermittlung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="42917-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="42917-113">Beachten Sie, dass dieses Add-In für Outlook Plattformen funktioniert – im Web, iOS, Android und Desktop.</span><span class="sxs-lookup"><span data-stu-id="42917-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="42917-114">Wenn Sie ein Administrator in einer Organisation mit Exchange Online sind, verwenden Sie das Übermittlungsportal im Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="42917-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="42917-115">Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="42917-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="42917-116">Sie können konfigurieren, dass Nachrichten direkt an Microsoft, ein von Ihnen festgelegtes Postfach oder beides gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="42917-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="42917-117">Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="42917-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="42917-118">Weitere Informationen zum Erhalten und Aktivieren der Berichtsnachricht oder der Phishing-Add-Ins melden finden Sie unter [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="42917-118">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="42917-119">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="42917-119">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="42917-120">Verwenden des Berichtsnachrichtenfeatures</span><span class="sxs-lookup"><span data-stu-id="42917-120">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="42917-121">Melden von Junk- und Phishingnachrichten</span><span class="sxs-lookup"><span data-stu-id="42917-121">Report junk and phishing messages</span></span>

<span data-ttu-id="42917-122">Verwenden Sie für Nachrichten im Posteingang oder in einem anderen E-Mail-Ordner mit Ausnahme von Junk-E-Mails die folgende Methode, um Spam- und Phishingnachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="42917-122">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="42917-123">Klicken Sie **in der** oberen rechten Ecke der ausgewählten  Nachricht auf die Ellipsen Weitere Aktionen, klicken Sie im Dropdownmenü auf Nachricht melden, und wählen Sie **dann Junk** oder **Phishing aus.**</span><span class="sxs-lookup"><span data-stu-id="42917-123">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42917-124">![Berichtsnachricht – Weitere Aktionen](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="42917-124">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42917-125">![Berichtsnachricht – Junk und Phishing](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="42917-125">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="42917-126">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und:</span><span class="sxs-lookup"><span data-stu-id="42917-126">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="42917-127">In den Junk-E-Mail-Ordner verschoben, wenn er als Spam gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="42917-127">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="42917-128">Gelöscht, wenn es als Phishing gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="42917-128">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="42917-129">Melden von Nachrichten, die kein Junk sind</span><span class="sxs-lookup"><span data-stu-id="42917-129">Report messages that are not junk</span></span>

1. <span data-ttu-id="42917-130">Klicken Sie **in der** oberen rechten Ecke der ausgewählten  Nachricht auf die Ellipsen Weitere Aktionen, klicken Sie im Dropdownmenü auf Nachricht melden, und klicken Sie dann auf **Nicht Junk**.</span><span class="sxs-lookup"><span data-stu-id="42917-130">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42917-131">![Berichtsnachricht – Weitere Aktionen](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="42917-131">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42917-132">![Berichtsnachricht – Kein Junk](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="42917-132">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="42917-133">Die ausgewählte Nachricht wird zur Analyse an Microsoft gesendet und in den Posteingang oder einen anderen angegebenen Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="42917-133">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="42917-134">Anzeigen und Überprüfen von gemeldeten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="42917-134">View and review reported messages</span></span>

<span data-ttu-id="42917-135">Zum Überprüfen von Nachrichten, die Benutzer an Microsoft melden, haben Sie die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="42917-135">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="42917-136">Verwenden Sie das Administrator-Übermittlungsportal.</span><span class="sxs-lookup"><span data-stu-id="42917-136">Use the Admin Submissions portal.</span></span> <span data-ttu-id="42917-137">Weitere Informationen finden Sie unter [Anzeigen von Benutzerübermittlungen an Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="42917-137">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="42917-138">Erstellen Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet), um Kopien von gemeldeten Nachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="42917-138">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="42917-139">Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, was Ihre Benutzer an Microsoft melden.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="42917-139">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>