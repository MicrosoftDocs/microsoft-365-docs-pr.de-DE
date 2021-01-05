---
title: Manuelles übermitteln von Nachrichten an Microsoft zur Analyse
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Administratoren und Endbenutzer können erfahren, wie Sie e-Mail-Nachrichten (gute e-Mails, die als "schlecht" oder "schlecht" gekennzeichnet sind) zur Analyse an Microsoft senden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe8e3c5ed44c7578764ed0bf19408f4db16e3740
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751559"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="b243c-103">Manuelles übermitteln von Nachrichten an Microsoft zur Analyse</span><span class="sxs-lookup"><span data-stu-id="b243c-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="b243c-104">Wenn Sie ein Administrator in einer Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungen-Portal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b243c-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="b243c-105">Weitere Informationen finden Sie unter [Verwenden der Administrator Übermittlung zum Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="b243c-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="b243c-106">Es kann frustrierend sein, wenn Benutzer in Ihrer Organisation Junk-Nachrichten (Spam) oder Phishing-Nachrichten in Ihrem Posteingang empfangen oder wenn Sie keine legitime e-Mail-Nachricht erhalten, weil Sie als Junk gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="b243c-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="b243c-107">Wir optimieren unsere Spamfilter ständig, um genauere Angaben zu machen.</span><span class="sxs-lookup"><span data-stu-id="b243c-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="b243c-108">Sie und Ihre Benutzer können diesen Prozess unterstützen, indem Sie falsch positive Ergebnisse (gute e-Mail-Nachrichten als ungültig markiert), falsche Negative Zeichen (ungültige e-Mail-Nachricht) und Phishing-Nachrichten zur Analyse an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="b243c-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="b243c-109">Aufgrund der hohen Anzahl von Übermittlungen, die wir erhalten, können wir möglicherweise nicht alle Anfragen zur Analyse beantworten.</span><span class="sxs-lookup"><span data-stu-id="b243c-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="b243c-110">Senden von falschen negativen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="b243c-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="b243c-111">Anstatt die folgenden Verfahren zum Melden von falsch negativen Daten zu verwenden, können Benutzer in Outlook und Outlook im Internet (früher als Outlook Web App bezeichnet) das Add-in "Berichtsnachricht" für Microsoft Outlook verwenden.</span><span class="sxs-lookup"><span data-stu-id="b243c-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="b243c-112">Informationen zum Installieren und verwenden dieses Tools finden Sie unter [enable the Report Message Add-in](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="b243c-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="b243c-113">Wenn Sie eine Nachricht erhalten, die durch die Spamfilterung geleitet wurde, die als Spam oder Phishing identifiziert werden sollte, können Sie die Nachricht nach Bedarf an die Microsoft-Spam Analyse-und Microsoft-Phishing-Analyseteams senden.</span><span class="sxs-lookup"><span data-stu-id="b243c-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="b243c-114">Die Analysten überprüfen die Nachricht und fügen Sie den Dienst weiten Filtern hinzu, wenn Sie die Klassifizierungskriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b243c-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="b243c-115">Erstellen Sie eine neue, leere e-Mail-Nachricht mit einem der folgenden Empfänger:</span><span class="sxs-lookup"><span data-stu-id="b243c-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="b243c-116">**Junk**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="b243c-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="b243c-117">**Phishing**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="b243c-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="b243c-118">Ziehen Sie die Junk-oder Phishing-Nachricht per Drag & Drop in die neue Nachricht.</span><span class="sxs-lookup"><span data-stu-id="b243c-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="b243c-119">Dadurch wird die Junk-oder Phishing-Nachricht als Anlage in der neuen Nachricht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b243c-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="b243c-120">Kopieren und Einfügen des Inhalts der Nachricht oder Weiterleiten der Nachricht (die ursprüngliche Nachricht ist erforderlich, damit die Nachrichtenkopfzeilen überprüft werden können).</span><span class="sxs-lookup"><span data-stu-id="b243c-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="b243c-121">Sie können mehrere Nachrichten in der neuen Nachricht anfügen.</span><span class="sxs-lookup"><span data-stu-id="b243c-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="b243c-122">Stellen Sie sicher, dass alle Nachrichten vom gleichen Typ sind: entweder Phishing-Nachrichten oder Junk-e-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b243c-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="b243c-123">Lassen Sie den Nachrichtentext leer.</span><span class="sxs-lookup"><span data-stu-id="b243c-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="b243c-124">Verwenden Sie entweder msg (Outlook-Standardformat) oder eml (standardmäßige Outlook im Internetformat) für die angefügten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b243c-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="b243c-125">Wenn Sie fertig sind, klicken Sie auf **senden**.</span><span class="sxs-lookup"><span data-stu-id="b243c-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="b243c-126">Administratoren haben verschiedene Möglichkeiten, bestimmte Nachrichten, die fälschlicherweise als Spam identifiziert werden, zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="b243c-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="b243c-127">Ausführliche Informationen finden Sie unter [Create blocked Sender Lists in EoP](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="b243c-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="b243c-128">Senden von falsch positiven Ergebnissen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="b243c-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="b243c-129">Anstatt die folgenden Verfahren zum Melden von falsch positiven Ergebnissen zu verwenden, können Benutzer in Outlook und Outlook im Internet das Add-in "Berichtsnachricht" für Microsoft Outlook verwenden.</span><span class="sxs-lookup"><span data-stu-id="b243c-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="b243c-130">Informationen zum Installieren und verwenden dieses Tools finden Sie unter [enable the Report Message Add-in](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="b243c-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="b243c-131">Wenn eine Nachricht fälschlicherweise als Spam identifiziert wurde, können Sie die Nachricht an das Microsoft-Spam Analyse Team übermitteln.</span><span class="sxs-lookup"><span data-stu-id="b243c-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="b243c-132">Die Analysten bewerten die Nachricht, und (abhängig von den Ergebnissen der Analyse) können die Dienst weiten Filter so angepasst werden, dass die Nachricht durchlassen wird.</span><span class="sxs-lookup"><span data-stu-id="b243c-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="b243c-133">Erstellen Sie eine neue, leere e-Mail-Nachricht mit `not_junk@office365.microsoft.com` als Empfänger:</span><span class="sxs-lookup"><span data-stu-id="b243c-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="b243c-134">Ziehen Sie die nicht identifizierte Nachricht per Drag & Drop in die neue Nachricht.</span><span class="sxs-lookup"><span data-stu-id="b243c-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="b243c-135">Dadurch wird die nicht identifizierte Nachricht als Anlage in der neuen Nachricht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b243c-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="b243c-136">Kopieren und Einfügen des Inhalts der Nachricht oder Weiterleiten der Nachricht (die ursprüngliche Nachricht ist erforderlich, damit die Nachrichtenkopfzeilen überprüft werden können).</span><span class="sxs-lookup"><span data-stu-id="b243c-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="b243c-137">Sie können mehrere Nachrichten in der neuen Nachricht anfügen.</span><span class="sxs-lookup"><span data-stu-id="b243c-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="b243c-138">Stellen Sie sicher, dass alle Nachrichten vom gleichen Typ sind: entweder Phishing-Nachrichten oder Junk-e-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b243c-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="b243c-139">Lassen Sie den Nachrichtentext leer.</span><span class="sxs-lookup"><span data-stu-id="b243c-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="b243c-140">Verwenden Sie entweder msg (Outlook-Standardformat) oder eml (standardmäßige Outlook im Internetformat) für die angefügten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b243c-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="b243c-141">Wenn Sie fertig sind, klicken Sie auf **senden**.</span><span class="sxs-lookup"><span data-stu-id="b243c-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="b243c-142">Administratoren haben verschiedene Möglichkeiten, um zu ermöglichen, dass bestimmte Nachrichten die Spamfilterung überspringen.</span><span class="sxs-lookup"><span data-stu-id="b243c-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="b243c-143">Ausführliche Informationen finden Sie unter [Create Safe Sender Lists in EoP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="b243c-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="b243c-144">Wo werden die Daten aus Übermittlungen an Microsoft gespeichert?</span><span class="sxs-lookup"><span data-stu-id="b243c-144">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="b243c-145">Die Daten befinden sich im Office 365 Compliance-Grenze in nordamerikanischen Rechenzentren.</span><span class="sxs-lookup"><span data-stu-id="b243c-145">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="b243c-146">Die Daten werden von Analysten im Entwicklungsteam überprüft, um die Effektivität der Filter zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b243c-146">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="b243c-147">Erstellen einer e-Mail-Fluss Regel zum Empfangen von Kopien von Nachrichten, die an Microsoft gemeldet werden</span><span class="sxs-lookup"><span data-stu-id="b243c-147">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="b243c-148">Anweisungen finden Sie unter [Verwenden von Nachrichtenfluss Regeln, um zu sehen, was Ihre Benutzer an Microsoft melden](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="b243c-148">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
