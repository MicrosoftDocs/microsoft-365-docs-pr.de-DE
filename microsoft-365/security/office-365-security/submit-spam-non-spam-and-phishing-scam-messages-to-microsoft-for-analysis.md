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
description: Administratoren und Endbenutzer können erfahren, wie Sie Nachrichten (gute E-Mails, die als ungültige oder ungültige E-Mails zulässig sind) zur Analyse an Microsoft senden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d5d3b7a51c39b85af8a6fae84f525da6d806789c
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029584"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="a9076-103">Manuelles Übermitteln von Nachrichten zur Analyse an Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9076-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="a9076-104">Wenn Sie ein Administrator in einer Organisation mit Exchange Online-Postfächern sind, empfehlen wir die Verwendung des Übermittlungsportals im Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="a9076-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="a9076-105">Weitere Informationen finden Sie unter ["Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft ".](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a9076-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="a9076-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span><span class="sxs-lookup"><span data-stu-id="a9076-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="a9076-107">Wir optimieren unsere Spamfilter ständig, um präziser zu sein.</span><span class="sxs-lookup"><span data-stu-id="a9076-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="a9076-108">Sie und Ihre Benutzer können diesen Prozess unterstützen, indem Sie falsch positive Ergebnisse (gute E-Mails als schlecht gekennzeichnet), falsch negative Ergebnisse (ungültige E-Mails sind zugelassen) und Phishingnachrichten zur Analyse an Microsoft übermitteln.</span><span class="sxs-lookup"><span data-stu-id="a9076-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="a9076-109">Aufgrund der hohen Anzahl von Übermittlungen, die wir erhalten, können wir möglicherweise nicht alle Analyseanforderungen beantworten.</span><span class="sxs-lookup"><span data-stu-id="a9076-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="a9076-110">Übermitteln falsch negativer Meldungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9076-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="a9076-111">Anstatt die folgenden Verfahren zum Melden falsch negativer Negative zu verwenden, können Benutzer in Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) das Report Message-Add-In oder das Phishing-Add-In "Melden" verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9076-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="a9076-112">Informationen zum Installieren und Verwenden dieser Tools finden Sie unter "Aktivieren des [Nachrichten-Add-Ins](enable-the-report-message-add-in.md) "Melden" und "Aktivieren des [Phishing-Add-Ins "Melden"](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="a9076-112">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="a9076-113">Wenn Sie eine Nachricht erhalten, die die Spamfilterung passiert hat, die als Spam oder Phishing identifiziert worden sein sollte, können Sie die Nachricht gegebenenfalls an die Microsoft-Teams für die Spamanalyse und die Microsoft-Phishinganalyse übermitteln.</span><span class="sxs-lookup"><span data-stu-id="a9076-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="a9076-114">Die Analysten überprüfen die Nachricht und fügen sie den dienstweiten Filtern hinzu, wenn sie die Klassifizierungskriterien erfüllt.</span><span class="sxs-lookup"><span data-stu-id="a9076-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="a9076-115">Erstellen Sie eine neue leere E-Mail-Nachricht mit einem der folgenden Empfänger:</span><span class="sxs-lookup"><span data-stu-id="a9076-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="a9076-116">**Junk:**`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="a9076-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="a9076-117">**Phishing:**`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="a9076-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="a9076-118">Ziehen Sie die Junk- oder Phishingnachricht per Drag and Drop in die neue Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a9076-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="a9076-119">Dadurch wird die Junk- oder Phishingnachricht als Anlage in der neuen Nachricht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a9076-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="a9076-120">Kopieren Sie den Inhalt der Nachricht nicht, und fügen Sie ihn nicht ein, und geben Sie die Nachricht nicht weiter (wir benötigen die ursprüngliche Nachricht, damit wir die Nachrichtenkopfzeilen überprüfen können).</span><span class="sxs-lookup"><span data-stu-id="a9076-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="a9076-121">Sie können mehrere Nachrichten in der neuen Nachricht anfügen.</span><span class="sxs-lookup"><span data-stu-id="a9076-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="a9076-122">Stellen Sie sicher, dass alle Nachrichten den gleichen Typ haben: entweder Phishing- oder Junk-E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a9076-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="a9076-123">Lassen Sie den Nachrichtentext leer.</span><span class="sxs-lookup"><span data-stu-id="a9076-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="a9076-124">Verwenden Sie entweder msg (Outlook-Standardformat) oder EML (Outlook im Web-Standardformat) für die angefügten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a9076-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="a9076-125">Klicken Sie nach Abschluss des Abschlusses auf **"Senden".**</span><span class="sxs-lookup"><span data-stu-id="a9076-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="a9076-126">Administratoren haben mehrere Möglichkeiten, bestimmte Nachrichten zu blockieren, die falsch als Spam erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="a9076-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="a9076-127">Weitere Informationen finden Sie unter [Erstellen von Listen blockierter Absender in EOP](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a9076-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="a9076-128">Übermitteln falsch positiver Ergebnisse an Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9076-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="a9076-129">Anstatt die folgenden Verfahren zum Melden falsch positiver Ergebnisse zu verwenden, können Benutzer in Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) das Add-In "Nachricht melden" oder das "Phishing-Add-In melden" verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9076-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="a9076-130">Informationen zum Installieren und Verwenden dieser Tools finden Sie unter "Aktivieren des [Nachrichten-Add-Ins](enable-the-report-message-add-in.md) "Melden" und "Aktivieren des [Phishing-Add-Ins "Melden"](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="a9076-130">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>


<span data-ttu-id="a9076-131">Wenn eine Nachricht fälschlicherweise als Spam identifiziert wurde, können Sie die Nachricht an das Microsoft Spam Analysis Team übermitteln.</span><span class="sxs-lookup"><span data-stu-id="a9076-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="a9076-132">Die Analysten werten die Nachricht aus, und (abhängig von den Ergebnissen der Analyse) können die dienstweiten Filter angepasst werden, um die Nachricht zu durchkommen.</span><span class="sxs-lookup"><span data-stu-id="a9076-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="a9076-133">Erstellen Sie eine neue leere E-Mail-Nachricht mit `not_junk@office365.microsoft.com` dem Empfänger:</span><span class="sxs-lookup"><span data-stu-id="a9076-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="a9076-134">Ziehen Sie die falsch identifizierte Nachricht per Drag and Drop in die neue Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a9076-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="a9076-135">Dadurch wird die falsch identifizierte Nachricht als Anlage in der neuen Nachricht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a9076-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="a9076-136">Kopieren Sie den Inhalt der Nachricht nicht, und fügen Sie ihn nicht ein, und geben Sie die Nachricht nicht weiter (wir benötigen die ursprüngliche Nachricht, damit wir die Nachrichtenkopfzeilen überprüfen können).</span><span class="sxs-lookup"><span data-stu-id="a9076-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="a9076-137">Sie können mehrere Nachrichten in der neuen Nachricht anfügen.</span><span class="sxs-lookup"><span data-stu-id="a9076-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="a9076-138">Stellen Sie sicher, dass alle Nachrichten den gleichen Typ haben: entweder Phishing- oder Junk-E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a9076-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="a9076-139">Lassen Sie den Nachrichtentext leer.</span><span class="sxs-lookup"><span data-stu-id="a9076-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="a9076-140">Verwenden Sie entweder msg (Outlook-Standardformat) oder EML (Outlook im Web-Standardformat) für die angefügten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a9076-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="a9076-141">Klicken Sie nach Abschluss des Abschlusses auf **"Senden".**</span><span class="sxs-lookup"><span data-stu-id="a9076-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="a9076-142">Administratoren haben mehrere Möglichkeiten, bestimmten Nachrichten das Überspringen der Spamfilterung zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="a9076-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="a9076-143">Weitere Informationen finden Sie unter [Erstellen von Listen sicherer Absender in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a9076-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="a9076-144">Wo werden die Daten aus Übermittlungen an Microsoft gespeichert?</span><span class="sxs-lookup"><span data-stu-id="a9076-144">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="a9076-145">Die Daten befinden sich in nordamerikanischen Rechenzentren in der Office 365-Compliance-Grenze.</span><span class="sxs-lookup"><span data-stu-id="a9076-145">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="a9076-146">Die Daten werden von Analysten des Technikteams überprüft, um die Effektivität der Filter zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="a9076-146">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="a9076-147">Erstellen einer Nachrichtenflussregel zum Empfangen von Kopien von Nachrichten, die an Microsoft gemeldet werden</span><span class="sxs-lookup"><span data-stu-id="a9076-147">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="a9076-148">Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, was Ihre Benutzer an Microsoft melden.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="a9076-148">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
