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
description: Administratoren und Endbenutzer können erfahren, wie Sie Nachrichten (gute E-Mails, die als ungültige oder ungültige E-Mails zugelassen sind) zur Analyse an Microsoft senden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c3a02c710472a996245a38d996ff4485efd1748
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624025"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="0db08-103">Manuelles Übermitteln von Nachrichten zur Analyse an Microsoft</span><span class="sxs-lookup"><span data-stu-id="0db08-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0db08-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="0db08-104">**Applies to**</span></span>
- [<span data-ttu-id="0db08-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0db08-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0db08-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="0db08-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0db08-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0db08-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="0db08-108">Wenn Sie ein Administrator in einer Organisation mit Exchange Online sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0db08-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="0db08-109">Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="0db08-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="0db08-110">Es kann frustrierend sein, wenn Benutzer in Ihrer Organisation Junknachrichten (Spam) oder Phishingnachrichten im Posteingang empfangen oder wenn sie keine legitime E-Mail-Nachricht erhalten, weil sie als Junk gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="0db08-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="0db08-111">Wir optimieren unsere Spamfilter ständig, um präziser zu sein.</span><span class="sxs-lookup"><span data-stu-id="0db08-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="0db08-112">Sie und Ihre Benutzer können diesen Prozess unterstützen, indem Sie falsch positive Ergebnisse (gute E-Mails, die als ungültig gekennzeichnet sind), falsch negative Nachrichten (ungültige E-Mails zulässig) und Phishingnachrichten zur Analyse an Microsoft übermitteln.</span><span class="sxs-lookup"><span data-stu-id="0db08-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="0db08-113">Aufgrund der hohen Anzahl von Übermittlungen, die wir erhalten, können wir möglicherweise nicht alle Analyseanforderungen beantworten.</span><span class="sxs-lookup"><span data-stu-id="0db08-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="0db08-114">Übermitteln falscher Negative an Microsoft</span><span class="sxs-lookup"><span data-stu-id="0db08-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="0db08-115">Anstatt die folgenden Verfahren zum Melden falscher Negative zu verwenden, können Benutzer in Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) das Add-In "Nachricht melden" oder das Phishing-Add-In melden verwenden.</span><span class="sxs-lookup"><span data-stu-id="0db08-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="0db08-116">Informationen zum Installieren und Verwenden dieser Tools finden Sie unter [Enable the Report Message add-in](enable-the-report-message-add-in.md) und Enable the Report Phishing [add-in](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="0db08-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="0db08-117">Wenn Sie eine Nachricht erhalten, die die Spamfilterung passiert hat, die als Spam oder Phishing identifiziert werden sollte, können Sie die Nachricht an die Microsoft Spam Analysis- und Microsoft Phishing Analysis Teams senden.</span><span class="sxs-lookup"><span data-stu-id="0db08-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="0db08-118">Die Analysten überprüfen die Nachricht und fügen sie den dienstweiten Filtern hinzu, wenn sie die Klassifizierungskriterien erfüllt.</span><span class="sxs-lookup"><span data-stu-id="0db08-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="0db08-119">Erstellen Sie eine neue leere E-Mail-Nachricht mit einem der folgenden Empfänger:</span><span class="sxs-lookup"><span data-stu-id="0db08-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="0db08-120">**Junk**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="0db08-120">**Junk**: `junk@office365.microsoft.com`</span></span>
   - <span data-ttu-id="0db08-121">**Phishing**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="0db08-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="0db08-122">Ziehen Sie die Junk- oder Phishingnachricht in die neue Nachricht, und legen Sie sie ab.</span><span class="sxs-lookup"><span data-stu-id="0db08-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="0db08-123">Dadurch wird die Junk- oder Phishingnachricht als Anlage in der neuen Nachricht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0db08-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="0db08-124">Kopieren Sie nicht den Inhalt der Nachricht, und fügen Sie ihn nicht ein, oder geben Sie die Nachricht weiter (wir benötigen die ursprüngliche Nachricht, damit wir die Nachrichtenkopfzeilen überprüfen können).</span><span class="sxs-lookup"><span data-stu-id="0db08-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="0db08-125">Sie können mehrere Nachrichten in der neuen Nachricht anfügen.</span><span class="sxs-lookup"><span data-stu-id="0db08-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="0db08-126">Stellen Sie sicher, dass alle Nachrichten denselben Typ haben: Entweder Phishingnachrichten oder Junk-E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="0db08-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="0db08-127">Lassen Sie den Nachrichtentext leer.</span><span class="sxs-lookup"><span data-stu-id="0db08-127">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="0db08-128">Verwenden Sie für die angefügten Nachrichten Outlook .msg (Standardformat) oder EML (Standardformat Outlook Webformat).</span><span class="sxs-lookup"><span data-stu-id="0db08-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="0db08-129">Klicken Sie nach Abschluss des Abschlusses auf **Senden**.</span><span class="sxs-lookup"><span data-stu-id="0db08-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="0db08-130">Administratoren haben verschiedene Möglichkeiten, bestimmte Nachrichten zu blockieren, die als Spam falsch identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="0db08-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="0db08-131">Weitere Informationen finden Sie unter [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="0db08-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="0db08-132">Senden falsch positiver Ergebnisse an Microsoft</span><span class="sxs-lookup"><span data-stu-id="0db08-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="0db08-133">Anstatt die folgenden Verfahren zum Melden falsch positiver Ergebnisse zu verwenden, können Benutzer in Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) das Berichtsnachrichten-Add-In oder das Phishing-Add-In Melden verwenden.</span><span class="sxs-lookup"><span data-stu-id="0db08-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="0db08-134">Informationen zum Installieren und Verwenden dieser Tools finden Sie unter [Enable the Report Message add-in](enable-the-report-message-add-in.md) und Enable the Report Phishing [add-in](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="0db08-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="0db08-135">Wenn eine Nachricht fälschlicherweise als Spam identifiziert wurde, können Sie die Nachricht an das Microsoft Spam Analysis Team übermitteln.</span><span class="sxs-lookup"><span data-stu-id="0db08-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="0db08-136">Die Analysten werten die Nachricht aus, und (abhängig von den Ergebnissen der Analyse) können die dienstweiten Filter angepasst werden, um die Nachricht durch zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0db08-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="0db08-137">Erstellen Sie eine neue leere E-Mail-Nachricht mit `not_junk@office365.microsoft.com` als Empfänger.</span><span class="sxs-lookup"><span data-stu-id="0db08-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient.</span></span>

2. <span data-ttu-id="0db08-138">Ziehen Sie die falsch identifizierte Nachricht in die neue Nachricht, und legen Sie sie ab.</span><span class="sxs-lookup"><span data-stu-id="0db08-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="0db08-139">Dadurch wird die falsch identifizierte Nachricht als Anlage in der neuen Nachricht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0db08-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="0db08-140">Kopieren Sie nicht den Inhalt der Nachricht, und fügen Sie ihn nicht ein, oder geben Sie die Nachricht weiter (wir benötigen die ursprüngliche Nachricht, damit wir die Nachrichtenkopfzeilen überprüfen können).</span><span class="sxs-lookup"><span data-stu-id="0db08-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="0db08-141">Sie können mehrere Nachrichten in der neuen Nachricht anfügen.</span><span class="sxs-lookup"><span data-stu-id="0db08-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="0db08-142">Stellen Sie sicher, dass alle Nachrichten denselben Typ haben: Entweder Phishingnachrichten oder Junk-E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="0db08-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="0db08-143">Lassen Sie den Nachrichtentext leer.</span><span class="sxs-lookup"><span data-stu-id="0db08-143">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="0db08-144">Verwenden Sie für die angefügten Nachrichten Outlook .msg (Standardformat) oder EML (Standardformat Outlook Webformat).</span><span class="sxs-lookup"><span data-stu-id="0db08-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="0db08-145">Klicken Sie nach Abschluss des Abschlusses auf **Senden**.</span><span class="sxs-lookup"><span data-stu-id="0db08-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="0db08-146">Administratoren haben verschiedene Möglichkeiten, bestimmten Nachrichten das Überspringen der Spamfilterung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0db08-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="0db08-147">Weitere Informationen finden Sie unter [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="0db08-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="0db08-148">Wo werden die Daten aus Übermittlungen an Microsoft gespeichert?</span><span class="sxs-lookup"><span data-stu-id="0db08-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="0db08-149">Die Daten befinden sich in Office 365 Compliancegrenze in nordamerikanischen Rechenzentren.</span><span class="sxs-lookup"><span data-stu-id="0db08-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="0db08-150">Die Daten werden von Analysten des Engineering-Teams überprüft, um die Effektivität der Filter zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="0db08-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="0db08-151">Erstellen einer Nachrichtenflussregel zum Empfangen von Kopien von Nachrichten, die an Microsoft gemeldet werden</span><span class="sxs-lookup"><span data-stu-id="0db08-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="0db08-152">Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, welche Benutzer Microsoft melden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="0db08-152">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
