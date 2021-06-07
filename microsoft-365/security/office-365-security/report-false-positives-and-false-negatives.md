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
description: Erfahren Sie, wie Sie falsch positive und falsch negative Ergebnisse in Outlook mithilfe der Funktion "Meldung melden" melden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 84a5b697f8a4b46cf79c542485bfafb396328f5c
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789243"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="45d1a-103">Melden falsch positiver und falsch negativer Ergebnisse in Outlook</span><span class="sxs-lookup"><span data-stu-id="45d1a-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="45d1a-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="45d1a-104">**Applies to**</span></span>
- [<span data-ttu-id="45d1a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="45d1a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="45d1a-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="45d1a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="45d1a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45d1a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="45d1a-108">Wenn Sie ein Administrator in einer Microsoft 365 Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="45d1a-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="45d1a-109">Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="45d1a-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="45d1a-110">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder lokalen Postfächern mit moderner Hybridauthentifizierung können Sie falsch positive Ergebnisse (gute E-Mails, die blockiert oder an Junk-Ordner gesendet wurden) und falsch negative Nachrichten (unerwünschte E-Mails oder Phishing-Nachrichten, die an den Posteingang übermittelt wurden) an Exchange Online Protection (EOP) senden.</span><span class="sxs-lookup"><span data-stu-id="45d1a-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="45d1a-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="45d1a-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="45d1a-112">Verwenden Sie für eine optimale Benutzerübermittlung das Add-In "Nachricht melden" oder das Add-In "Phishing melden".</span><span class="sxs-lookup"><span data-stu-id="45d1a-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="45d1a-113">Die integrierte Oberfläche zum Melden von Junk- oder Phishing in Outlook kann nicht die [Benutzerübermittlungsrichtlinie](./user-submission.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="45d1a-113">The built-in experience for reporting junk or phishing in Outlook can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="45d1a-114">Es wird empfohlen, stattdessen das Add-In "Nachricht melden" oder das Add-In "Phishing melden" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="45d1a-114">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

- <span data-ttu-id="45d1a-115">Das Add-In "Nachricht melden" und das Add-In "Phishing melden" funktionieren für Outlook auf allen Plattformen (Outlook im Web, iOS, Android und Desktop).</span><span class="sxs-lookup"><span data-stu-id="45d1a-115">The the Report Message add-in and the Report Phishing add-in work for Outlook in all platforms (Outlook on the web, iOS, Android, and Desktop).</span></span>

- <span data-ttu-id="45d1a-116">Wenn Sie ein Administrator in einer Organisation mit Exchange Online Postfächern sind, verwenden Sie das Übermittlungsportal im Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="45d1a-116">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="45d1a-117">Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="45d1a-117">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="45d1a-118">Sie können das Senden von Nachrichten direkt an Microsoft, ein von Ihnen angegebenes Postfach oder beides konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="45d1a-118">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="45d1a-119">Weitere Informationen finden Sie unter [Richtlinien für Benutzerübermittlungen.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="45d1a-119">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="45d1a-120">Weitere Informationen zum Abrufen und Aktivieren der Berichtsnachricht oder der Berichtsphishing-Add-Ins finden Sie unter [Aktivieren der Berichtsnachricht oder der Berichtsphishing-Add-Ins.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="45d1a-120">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="45d1a-121">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Melden von Nachrichten und Dateien an Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="45d1a-121">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="45d1a-122">Verwenden des Berichtsnachrichtenfeatures</span><span class="sxs-lookup"><span data-stu-id="45d1a-122">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="45d1a-123">Melden von Junk- und Phishingnachrichten</span><span class="sxs-lookup"><span data-stu-id="45d1a-123">Report junk and phishing messages</span></span>

<span data-ttu-id="45d1a-124">Verwenden Sie für Nachrichten im Posteingang oder einem anderen E-Mail-Ordner mit Ausnahme von Junk-E-Mails die folgende Methode, um Spam- und Phishingnachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="45d1a-124">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="45d1a-125">Wählen Sie die Auslassungspunkte **"Weitere Aktionen"** in der oberen rechten Ecke der ausgewählten Nachricht aus, wählen Sie im Dropdownmenü die Option **"Nachricht** melden" aus, und wählen Sie dann **"Junk"** oder **"Phishing"** aus.</span><span class="sxs-lookup"><span data-stu-id="45d1a-125">Select the **More actions** ellipses on the top-right corner of the selected message, select **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>

   ![Meldung melden – Weitere Aktionen](../../media/report-message-more-actions.png)
   
   ![Nachricht melden – Junk und Phishing](../../media/report-message-junk-phishing.png)

2. <span data-ttu-id="45d1a-128">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und:</span><span class="sxs-lookup"><span data-stu-id="45d1a-128">The selected messages will be sent to Microsoft for analysis and:</span></span>
   - <span data-ttu-id="45d1a-129">In den Junk-E-Mail-Ordner verschoben, wenn sie als Spam gemeldet wurden.</span><span class="sxs-lookup"><span data-stu-id="45d1a-129">Moved to the Junk Email folder if they were reported as spam.</span></span>
   - <span data-ttu-id="45d1a-130">Gelöscht, wenn sie als Phishing gemeldet wurden.</span><span class="sxs-lookup"><span data-stu-id="45d1a-130">Deleted if they were reported as phishing.</span></span>

### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="45d1a-131">Melden von Nachrichten, die keine Junk-Nachrichten sind</span><span class="sxs-lookup"><span data-stu-id="45d1a-131">Report messages that are not junk</span></span>

1. <span data-ttu-id="45d1a-132">Wählen Sie die Auslassungspunkte **"Weitere Aktionen"** in der oberen rechten Ecke der ausgewählten Nachricht aus, wählen Sie im Dropdownmenü die Option **"Nachricht** melden" aus, und wählen Sie dann **"Nicht Junk"** aus.</span><span class="sxs-lookup"><span data-stu-id="45d1a-132">Select the **More actions** ellipses on the top-right corner of the selected message, select **Report message** from the dropdown menu, and then select **Not Junk**.</span></span>

   ![Meldung melden – Weitere Aktionen](../../media/report-message-more-actions.png)
   
   ![Meldung melden – keine Junk-Nachricht](../../media/report-message-not-junk.png)

2. <span data-ttu-id="45d1a-135">Die ausgewählte Nachricht wird zur Analyse an Microsoft gesendet und in den Posteingang oder einen anderen angegebenen Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="45d1a-135">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="45d1a-136">Anzeigen und Überprüfen gemeldeter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="45d1a-136">View and review reported messages</span></span>

<span data-ttu-id="45d1a-137">Zum Überprüfen von Nachrichten, die Benutzer an Microsoft melden, haben Sie die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="45d1a-137">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="45d1a-138">Verwenden Sie das Portal für Administratorübermittlungen.</span><span class="sxs-lookup"><span data-stu-id="45d1a-138">Use the Admin Submissions portal.</span></span> <span data-ttu-id="45d1a-139">Weitere Informationen finden Sie unter [Anzeigen von Benutzerübermittlungen an Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="45d1a-139">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>
- <span data-ttu-id="45d1a-140">Erstellen Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet), um Kopien von gemeldeten Nachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="45d1a-140">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="45d1a-141">Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, welche Benutzer An Microsoft melden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="45d1a-141">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
