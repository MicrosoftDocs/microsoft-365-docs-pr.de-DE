---
title: Manuelles Übermitteln von Nachrichten zur Analyse an Microsoft
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Administratoren und Endbenutzer können lernen, wie Sie Nachrichten (gute E-Mails, die als schlechte oder ungültige E-Mails zugelassen sind) zur Analyse an Microsoft senden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d277df764ce2fb135f11c6320bc990e4d4142d6
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929767"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="281ac-103">Manuelles Übermitteln von Nachrichten zur Analyse an Microsoft</span><span class="sxs-lookup"><span data-stu-id="281ac-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="281ac-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="281ac-104">**Applies to**</span></span>
- [<span data-ttu-id="281ac-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="281ac-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="281ac-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="281ac-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="281ac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="281ac-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="281ac-108">Wenn Sie ein Administrator in einer Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungsportal im Microsoft 365 Defender-Portal zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="281ac-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="281ac-109">Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="281ac-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="281ac-110">Es kann frustrierend sein, wenn Benutzer in Ihrer Organisation Junk-Nachrichten (Spam) oder Phishing-Nachrichten in ihrem Posteingang erhalten oder wenn sie keine seriöse E-Mail-Nachricht erhalten, da sie als Junk gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="281ac-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="281ac-111">Wir optimieren unsere Spamfilter ständig, um genauer zu sein.</span><span class="sxs-lookup"><span data-stu-id="281ac-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="281ac-112">Sie und Ihre Benutzer können diesen Prozess unterstützen, indem Sie falsch positive Ergebnisse (gute E-Mails als falsch markiert), falsch negative Nachrichten (ungültige E-Mails sind zulässig) und Phishingnachrichten zur Analyse an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="281ac-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="281ac-113">Aufgrund der hohen Anzahl von Übermittlungen, die wir erhalten, können möglicherweise nicht alle Anforderungen für die Analyse beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="281ac-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="281ac-114">Übermitteln falsch negativer Ergebnisse an Microsoft</span><span class="sxs-lookup"><span data-stu-id="281ac-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="281ac-115">Anstatt die folgenden Verfahren zum Melden falsch negativer Ergebnisse zu verwenden, können Benutzer in Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) das Add-In "Nachricht melden" oder das Add-In "Phishing melden" verwenden.</span><span class="sxs-lookup"><span data-stu-id="281ac-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="281ac-116">Informationen zum Installieren und Verwenden dieser Tools finden Sie unter [Aktivieren des Add-Ins "Nachricht melden"](enable-the-report-message-add-in.md) und ["Bericht-Phishing"-Add-In.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="281ac-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="281ac-117">Wenn Sie eine Nachricht erhalten, die die Spamfilterung durchlaufen hat, die als Spam oder Phishing hätte identifiziert werden sollen, können Sie die Nachricht nach Bedarf an die Microsoft-Teams für Spamanalyse und Microsoft Phishing-Analyse übermitteln.</span><span class="sxs-lookup"><span data-stu-id="281ac-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="281ac-118">Die Analysten überprüfen die Nachricht und fügen sie den dienstweiten Filtern hinzu, wenn sie die Klassifizierungskriterien erfüllt.</span><span class="sxs-lookup"><span data-stu-id="281ac-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="281ac-119">Erstellen Sie eine neue, leere E-Mail-Nachricht mit einem der folgenden Empfänger:</span><span class="sxs-lookup"><span data-stu-id="281ac-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="281ac-120">**Junk**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="281ac-120">**Junk**: `junk@office365.microsoft.com`</span></span>
   - <span data-ttu-id="281ac-121">**Phishing:**`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="281ac-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="281ac-122">Ziehen Sie die Junk- oder Phishingnachricht per Drag & Drop in die neue Nachricht.</span><span class="sxs-lookup"><span data-stu-id="281ac-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="281ac-123">Dadurch wird die Junk- oder Phishingnachricht als Anlage in der neuen Nachricht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="281ac-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="281ac-124">Kopieren Und fügen Sie den Inhalt der Nachricht nicht ein oder leiten Sie die Nachricht weiter (wir benötigen die ursprüngliche Nachricht, damit wir die Nachrichtenkopfzeilen überprüfen können).</span><span class="sxs-lookup"><span data-stu-id="281ac-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="281ac-125">Sie können mehrere Nachrichten in der neuen Nachricht anfügen.</span><span class="sxs-lookup"><span data-stu-id="281ac-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="281ac-126">Stellen Sie sicher, dass alle Nachrichten den gleichen Typ aufweisen: Phishing- oder Junk-E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="281ac-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="281ac-127">Lassen Sie den Nachrichtentext leer.</span><span class="sxs-lookup"><span data-stu-id="281ac-127">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="281ac-128">Verwenden Sie für die angefügten Nachrichten die Formate MSG (Standardformat Outlook) oder EML (Standard-Outlook im Webformat).</span><span class="sxs-lookup"><span data-stu-id="281ac-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="281ac-129">Wenn Sie fertig sind, klicken Sie auf **"Senden".**</span><span class="sxs-lookup"><span data-stu-id="281ac-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="281ac-130">Administratoren haben verschiedene Möglichkeiten, bestimmte Nachrichten zu blockieren, die als Spam falsch identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="281ac-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="281ac-131">Weitere Informationen finden Sie unter [Erstellen blockierter Absenderlisten in EOP.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="281ac-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="281ac-132">Übermitteln falsch positiver Ergebnisse an Microsoft</span><span class="sxs-lookup"><span data-stu-id="281ac-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="281ac-133">Anstatt die folgenden Verfahren zum Melden falsch positiver Ergebnisse zu verwenden, können Benutzer in Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) das Add-In "Nachricht melden" oder das Add-In "Phishing melden" verwenden.</span><span class="sxs-lookup"><span data-stu-id="281ac-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="281ac-134">Informationen zum Installieren und Verwenden dieser Tools finden Sie unter [Aktivieren des Add-Ins "Nachricht melden"](enable-the-report-message-add-in.md) und ["Bericht-Phishing"-Add-In.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="281ac-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="281ac-135">Wenn eine Nachricht fälschlicherweise als Spam identifiziert wurde, können Sie die Nachricht an das Microsoft Spam Analysis Team senden.</span><span class="sxs-lookup"><span data-stu-id="281ac-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="281ac-136">Die Analysten bewerten die Nachricht, und (abhängig von den Ergebnissen der Analyse) können die dienstweiten Filter angepasst werden, um die Nachricht durchzulassen.</span><span class="sxs-lookup"><span data-stu-id="281ac-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="281ac-137">Erstellen Sie eine neue, leere E-Mail-Nachricht `not_junk@office365.microsoft.com` mit dem Empfänger.</span><span class="sxs-lookup"><span data-stu-id="281ac-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient.</span></span>

2. <span data-ttu-id="281ac-138">Ziehen Sie die falsch identifizierte Nachricht per Drag & Drop in die neue Nachricht.</span><span class="sxs-lookup"><span data-stu-id="281ac-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="281ac-139">Dadurch wird die falsch identifizierte Nachricht als Anlage in der neuen Nachricht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="281ac-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="281ac-140">Kopieren Und fügen Sie den Inhalt der Nachricht nicht ein oder leiten Sie die Nachricht weiter (wir benötigen die ursprüngliche Nachricht, damit wir die Nachrichtenkopfzeilen überprüfen können).</span><span class="sxs-lookup"><span data-stu-id="281ac-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="281ac-141">Sie können mehrere Nachrichten in der neuen Nachricht anfügen.</span><span class="sxs-lookup"><span data-stu-id="281ac-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="281ac-142">Stellen Sie sicher, dass alle Nachrichten den gleichen Typ aufweisen: Phishing- oder Junk-E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="281ac-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="281ac-143">Lassen Sie den Nachrichtentext leer.</span><span class="sxs-lookup"><span data-stu-id="281ac-143">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="281ac-144">Verwenden Sie für die angefügten Nachrichten die Formate MSG (Standardformat Outlook) oder EML (Standard-Outlook im Webformat).</span><span class="sxs-lookup"><span data-stu-id="281ac-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="281ac-145">Wenn Sie fertig sind, klicken Sie auf **"Senden".**</span><span class="sxs-lookup"><span data-stu-id="281ac-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="281ac-146">Administratoren haben verschiedene Möglichkeiten, bestimmten Nachrichten das Überspringen der Spamfilterung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="281ac-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="281ac-147">Ausführliche Informationen finden Sie unter [Erstellen von Listen sicherer Absender in EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="281ac-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="281ac-148">Wo werden die Daten aus Übermittlungen an Microsoft gespeichert?</span><span class="sxs-lookup"><span data-stu-id="281ac-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="281ac-149">Die Daten befinden sich in der Office 365 Compliance-Grenze in nordamerikanischen Rechenzentren.</span><span class="sxs-lookup"><span data-stu-id="281ac-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="281ac-150">Die Daten werden von Analysten des Entwicklungsteams überprüft, um die Effektivität der Filter zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="281ac-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="281ac-151">Erstellen einer Nachrichtenflussregel zum Empfangen von Kopien von Nachrichten, die an Microsoft gemeldet werden</span><span class="sxs-lookup"><span data-stu-id="281ac-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="281ac-152">Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, welche Benutzer An Microsoft melden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="281ac-152">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
