---
title: Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Sie können eine Exchange-Nachrichtenfluss Regel erstellen, um zu verhindern, dass Ihre Benutzer e-Mail-Nachrichten zur Analyse an Microsoft senden und in ihren eigenen Sicherheitsprozessen verwenden.
ms.openlocfilehash: 11033b0d4b0ab9da0109fd31907a1537adc09c4d
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871291"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="73533-103">Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden</span><span class="sxs-lookup"><span data-stu-id="73533-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="73533-104">Ihnen stehen verschiedene Möglichkeiten zur Verfügung, falsch positive und falsch negative Nachrichten zur Analyse an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="73533-104">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis.</span></span> <span data-ttu-id="73533-105">Als Administrator können Sie Nachrichtenflussregeln verwenden, um anzuzeigen, was Ihre Benutzer an Microsoft als Spam, kein Spam und betrügerische Phishing-Versuche melden.</span><span class="sxs-lookup"><span data-stu-id="73533-105">As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams.</span></span> <span data-ttu-id="73533-106">Weitere Informationen finden Sie unter [Übermitteln von Spam-, Nicht-Spamnachrichten und Nachrichten, die als betrügerische Phishing-Angriffe angesehen werden, an Microsoft zur Analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="73533-106">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> <span data-ttu-id="73533-107">Umgekehrt können Sie eine Exchange-Nachrichtenfluss Regel (auch als Transportregel bezeichnet) erstellen, um zu verhindern, dass Ihre Benutzer e-Mail-Nachrichten zur Analyse an Microsoft senden und in ihren eigenen Sicherheitsprozessen verwenden.</span><span class="sxs-lookup"><span data-stu-id="73533-107">Conversely, you can create an Exchange mail flow rule (also known as a transport rule) to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="73533-108">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="73533-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="73533-109">Geschätzte Zeit bis zum Abschließen des Vorgangs: 5 Minuten</span><span class="sxs-lookup"><span data-stu-id="73533-109">Estimated time to complete: 5 minutes</span></span>

<span data-ttu-id="73533-110">Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="73533-110">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="73533-111">Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Nachrichtenfluss" und "Outlook im webpostfach-Richtlinien" in [Exchange Online Berechtigungen](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span><span class="sxs-lookup"><span data-stu-id="73533-111">To see what permissions you need, see the "Mail flow"  and "Outlook on the web mailbox policies" entries in [Exchange Online permissions](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span></span>

<span data-ttu-id="73533-112">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="73533-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="73533-113">Verwenden Sie die Exchange-Verwaltungskonsole, um eine Nachrichtenflussregel zu erstellen, um Berichte zu Junk-E-Mails, Phishing und Nicht-Junk-E-Mails anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="73533-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="73533-114">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.</span><span class="sxs-lookup"><span data-stu-id="73533-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="73533-115">Klicken Sie auf ![Hinzufügen (Symbol)](../media/ITPro-EAC-AddIcon.gif) und wählen Sie dann **Neue Regel erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="73533-115">Click ![Add Icon](../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="73533-116">Benennen Sie die Regel, und klicken Sie dann auf **Weitere Optionen**.</span><span class="sxs-lookup"><span data-stu-id="73533-116">Give the rule a name and then click **More options**.</span></span>

4. <span data-ttu-id="73533-117">Unter **Diese Regel anwenden, wenn...** können Sie **Empfänger** und anschließend **Adresse enthält eines dieser Wörter** wählen.</span><span class="sxs-lookup"><span data-stu-id="73533-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>

5. <span data-ttu-id="73533-118">Führen Sie im Feld **Wörter oder Ausdrücke angeben** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="73533-118">In the **specify words or phrases** box, do the following steps:</span></span>

   - <span data-ttu-id="73533-119">Geben `abuse@messaging.microsoft.com`Sie ein, klicken Sie](../media/ITPro-EAC-AddIcon.gif)auf Add `junk@office365.microsoft.com` -Symbol **hinzu** ![fügen, geben](../media/ITPro-EAC-AddIcon.gif)Sie ein, und klicken Sie **dann auf** ![hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="73533-119">Type `abuse@messaging.microsoft.com`, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif), type `junk@office365.microsoft.com` and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="73533-120">Diese e-Mail-Adressen werden verwendet, um falsch negative Nachrichten an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="73533-120">These email addresses are used to submit false negative messages to Microsoft.</span></span>

   - <span data-ttu-id="73533-121">Geben `phish@office365.microsoft.com` Sie ein, und klicken Sie](../media/ITPro-EAC-AddIcon.gif)dann auf Add-Symbol **Hinzufügen** ![.</span><span class="sxs-lookup"><span data-stu-id="73533-121">Type `phish@office365.microsoft.com` and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="73533-122">Diese E-Mail-Adresse wird verwendet, um verpasste Phishingnachrichten an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="73533-122">This email address is used to submit missed phishing messages to Microsoft.</span></span>

   - <span data-ttu-id="73533-123">Geben `false_positive@messaging.microsoft.com`Sie ein, klicken Sie](../media/ITPro-EAC-AddIcon.gif)auf Add `not_junk@office365.microsoft.com`-Symbol **hinzu** ![fügen, geben Sie](../media/ITPro-EAC-AddIcon.gif)ein, und klicken Sie ![dann **auf Symbol hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="73533-123">Type `false_positive@messaging.microsoft.com`, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif), type `not_junk@office365.microsoft.com`, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="73533-124">Diese e-Mail-Adressen werden verwendet, um falsch positive Nachrichten an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="73533-124">These email addresses are used to submit false positive messages to Microsoft.</span></span>

   - <span data-ttu-id="73533-125">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73533-125">Click **OK**.</span></span>

6. <span data-ttu-id="73533-126">Wählen Sie unter **Folgendes ausführen** die Option **Bcc der Nachricht an...** aus, und wählen Sie dann die Postfächer aus, in denen Sie Nachrichten erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="73533-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span>

7. <span data-ttu-id="73533-127">Auf Wunsch können Sie unter anderem auch Einstellungen zur Überwachung der Regel, zum Testen der Regel und zum Aktivieren der Regel in einem bestimmten Zeitraum vornehmen.</span><span class="sxs-lookup"><span data-stu-id="73533-127">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="73533-128">Wir empfehlen, die Regel über eine bestimmte Zeit zu testen, bevor Sie sie erzwingen.</span><span class="sxs-lookup"><span data-stu-id="73533-128">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="73533-129">Weitere Informationen finden Sie unter [Procedures for Mail Flow Rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span><span class="sxs-lookup"><span data-stu-id="73533-129">See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span>

8. <span data-ttu-id="73533-p107">Klicken Sie auf die Schaltfläche **Speichern**, um die Regel zu speichern. Sie wird in der Liste der Regeln angezeigt.</span><span class="sxs-lookup"><span data-stu-id="73533-p107">Click the **save** button to save the rule. It appears in your list of rules.</span></span>

<span data-ttu-id="73533-132">Nachdem Sie die Regel erstellt und durchgesetzt haben, werden sämtliche von Ihrer Organisation aus an vorgegebene E-Mail-Adressen gesendeten Nachrichten in das angegebene Postfach kopiert.</span><span class="sxs-lookup"><span data-stu-id="73533-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
