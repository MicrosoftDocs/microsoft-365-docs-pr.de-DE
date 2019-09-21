---
title: Automatische Bereinigung zur Nullstunde – Schutz vor Spam und Schadsoftware
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/11/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: Zero-Hour Auto Purge (zap) ist eine e-Mail-Schutzfunktion, die Nachrichten mit Spam oder Schadsoftware erkennt, die bereits an die Posteingänge Ihrer Benutzer übermittelt wurden, und dann den schädlichen Inhalt harmlos macht. Wie zap Dies bewirkt, hängt vom Typ der erkannten schädlichen Inhalte ab.
ms.openlocfilehash: f43826614def99f8807d8777f128d5bc66f7b46a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082150"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="c2294-104">Automatische Bereinigung zur Nullstunde – Schutz vor Spam und Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="c2294-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="c2294-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c2294-105">Overview</span></span>

<span data-ttu-id="c2294-106">Zero-Hour Auto Purge (zap) ist eine e-Mail-Schutzfunktion, die Nachrichten mit Phishing, Spam oder Schadsoftware erkennt, die bereits an die Posteingänge Ihrer Benutzer übermittelt wurden, und dann den schädlichen Inhalt harmlos macht.</span><span class="sxs-lookup"><span data-stu-id="c2294-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="c2294-107">Wie zap Dies bewirkt, hängt vom Typ des erkannten schädlichen Inhalts ab. e-Mails können aufgrund von e-Mail-Inhalten, URLs oder Anlagen gezappt werden.</span><span class="sxs-lookup"><span data-stu-id="c2294-107">How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="c2294-108">ZAP ist mit dem Standard Exchange Online Schutz verfügbar, der in jedem Office 365-Abonnement enthalten ist, das Exchange Online Postfächer enthält.</span><span class="sxs-lookup"><span data-stu-id="c2294-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="c2294-109">ZAP ist standardmäßig aktiviert, aber die folgenden Bedingungen müssen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="c2294-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="c2294-110">**Spam-Aktion** ist so eingestellt, dass die **Nachricht in den Junk-e-Mail-Ordner wechselt**.</span><span class="sxs-lookup"><span data-stu-id="c2294-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <span data-ttu-id="c2294-111">Sie können auch eine neue Spamfilter Richtlinie erstellen, die nur für eine Gruppe von Benutzern gilt, wenn Sie nicht möchten, dass alle Postfächer von zap abgeschirmt werden.</span><span class="sxs-lookup"><span data-stu-id="c2294-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="c2294-112">Benutzer haben ihre Standardeinstellungen für Junk-e-Mail beibehalten und den Junk-e-Mail-Schutz nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c2294-112">Users have kept their default junk mail settings, and have not turned off junk email protection.</span></span> <span data-ttu-id="c2294-113">(Weitere Informationen zu Benutzeroptionen in Outlook finden Sie unter [Ändern der Schutzebene im Junk-e-Mail-Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) .)</span><span class="sxs-lookup"><span data-stu-id="c2294-113">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span>
  
## <a name="how-zap-works"></a><span data-ttu-id="c2294-114">Funktionsweise von zap</span><span class="sxs-lookup"><span data-stu-id="c2294-114">How ZAP works</span></span>

<span data-ttu-id="c2294-115">Office 365 aktualisiert das Anti-Spam-Modul und die Malware Signaturen in Echtzeit auf täglicher Basis.</span><span class="sxs-lookup"><span data-stu-id="c2294-115">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="c2294-116">Allerdings erhalten Ihre Benutzer möglicherweise weiterhin Schadsoftware-Nachrichten, die aus einer Vielzahl von Gründen an ihre Posteingänge gesendet werden, einschließlich, wenn der Inhalt nach der Zustellung an die Benutzer Waffen basiert.</span><span class="sxs-lookup"><span data-stu-id="c2294-116">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="c2294-117">Zap behebt dies, indem Updates für die Office 365 Spam-und Malware Signaturen kontinuierlich überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="c2294-117">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="c2294-118">Zap kann zuvor zugestellte Nachrichten, die sich bereits in den Posteingängen von Benutzern befinden, suchen und entfernen.</span><span class="sxs-lookup"><span data-stu-id="c2294-118">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span>

<span data-ttu-id="c2294-119">Die ZAP-Aktion ist nahtlos für den Postfachbenutzer; Sie werden nicht benachrichtigt, wenn eine e-Mail-Nachricht verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="c2294-119">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span> <span data-ttu-id="c2294-120">Die Nachricht darf nicht älter als 2 Tage sein.</span><span class="sxs-lookup"><span data-stu-id="c2294-120">Message must not be older than 2 days.</span></span>
  
<span data-ttu-id="c2294-121">Zulassungslisten, [Nachrichtenfluss Regeln](https://go.microsoft.com/fwlink/p/?LinkId=722755) (auch bekannt als Transportregeln) und Endbenutzer Regeln oder zusätzliche Filter haben Vorrang vor zap.</span><span class="sxs-lookup"><span data-stu-id="c2294-121">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755) (also known as transport rules), and end user rules or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="c2294-122">Malware zap</span><span class="sxs-lookup"><span data-stu-id="c2294-122">Malware ZAP</span></span>

<span data-ttu-id="c2294-123">Für neu erkannte Schadsoftware entfernt zap Anlagen aus e-Mail-Nachrichten, sodass der Nachrichtentext im Postfach des Benutzers bleibt.</span><span class="sxs-lookup"><span data-stu-id="c2294-123">For newly detected malware, ZAP removes attachments from email messages, leaving the body of the message in the user's mailbox.</span></span> <span data-ttu-id="c2294-124">Anlagen werden unabhängig vom Lesestatus der e-Mail entfernt.</span><span class="sxs-lookup"><span data-stu-id="c2294-124">Attachments are removed regardless of the read status of the mail.</span></span>

<span data-ttu-id="c2294-125">Malware zap ist in der Schadsoftware-Richtlinie standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c2294-125">Malware ZAP is enabled by default in the Malware Policy.</span></span> <span data-ttu-id="c2294-126">Sie können Malware zap mithilfe des Parameters *ZapEnabled* im Cmdlet " [MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) " in Exchange Online PowerShell oder Exchange Online Protection PowerShell deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c2294-126">You can disable Malware ZAP by using the *ZapEnabled* parameter on the [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="phish-zap"></a><span data-ttu-id="c2294-127">Phishing-zap</span><span class="sxs-lookup"><span data-stu-id="c2294-127">Phish ZAP</span></span>

<span data-ttu-id="c2294-128">Bei e-Mails, die nach der Zustellung als "Phishing" identifiziert werden, wird zap entsprechend der Spam Richtlinie, von der der Benutzer abgedeckt ist, aktiv.</span><span class="sxs-lookup"><span data-stu-id="c2294-128">For mail that is identified as phish after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="c2294-129">Wenn die Richtlinien-Phishing-Aktion auf eine e-Mail (Umleitung, Löschung, Quarantäne, verschieben zu Junk) festgelegt ist, wird zap die Nachricht in den Junk-e-Mail-Ordner des Posteingangs des Benutzers verschieben, unabhängig vom Lesestatus der e-Mail.</span><span class="sxs-lookup"><span data-stu-id="c2294-129">If the policy Phish action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, regardless of the read status of the mail.</span></span> <span data-ttu-id="c2294-130">Wenn die Richtlinie Phishing-Aktion nicht auf Aktion ausführen festgelegt ist (X-Header hinzufügen, Betreff ändern, keine Aktion), wird zap keine Aktion für die e-Mail durchführen.</span><span class="sxs-lookup"><span data-stu-id="c2294-130">If the policy Phish action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="c2294-131">Weitere Informationen zum [Konfigurieren ihrer Spamfilter Richtlinien](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) finden Sie hier.</span><span class="sxs-lookup"><span data-stu-id="c2294-131">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="c2294-132">Phishing-zap ist in der Spam Richtlinie standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c2294-132">Phish ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="c2294-133">Sie können Phishing zap mithilfe des Parameters *ZapEnabled* im Cmdlet " [hostedcontentfilterpolicy dient zum](https://go.microsoft.com/fwlink/p/?LinkId=722758) " in Exchange Online PowerShell oder Exchange Online Protection PowerShell deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c2294-133">You can disable Phish ZAP by using the *ZapEnabled* parameter on the [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="spam-zap"></a><span data-ttu-id="c2294-134">Spam zap</span><span class="sxs-lookup"><span data-stu-id="c2294-134">Spam ZAP</span></span>

<span data-ttu-id="c2294-135">Bei e-Mail-Nachrichten, die nach der Zustellung als Spam identifiziert werden, wird zap entsprechend der Spam Richtlinie, von der der Benutzer abgedeckt ist, aktiv.</span><span class="sxs-lookup"><span data-stu-id="c2294-135">For mail that is identified as spam after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="c2294-136">Wenn die Spam Aktion der Richtlinie auf eine e-Mail (Umleitung, Löschung, Quarantäne, verschieben zu Junk) festgelegt ist, wird zap die Nachricht in den Junk-e-Mail-Ordner des Posteingangs des Benutzers verschieben, wenn die Nachricht ungelesen ist.</span><span class="sxs-lookup"><span data-stu-id="c2294-136">If the policy Spam action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, if the message is unread.</span></span> <span data-ttu-id="c2294-137">Wenn die Spam Aktion der Richtlinie nicht auf Aktion ausführen festgelegt ist (X-Header hinzufügen, Betreff ändern, keine Aktion), wird zap keine Aktion für die e-Mail durchführen.</span><span class="sxs-lookup"><span data-stu-id="c2294-137">If the policy Spam action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="c2294-138">Weitere Informationen zum [Konfigurieren ihrer Spamfilter Richtlinien](configure-your-spam-filter-policies.md) finden Sie hier.</span><span class="sxs-lookup"><span data-stu-id="c2294-138">Learn more about how to [Configure your spam filter policies](configure-your-spam-filter-policies.md) here.</span></span>

<span data-ttu-id="c2294-139">Spam zap ist in der Spam Richtlinie standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c2294-139">Spam ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="c2294-140">Sie können Spam zap mithilfe des *ZapEnabled* -Parameters von [sethostedcontentfilterpolicy dient zum-](https://go.microsoft.com/fwlink/p/?LinkId=722758) Cmdlet in Exchange Online PowerShell oder Exchange Online Protection PowerShell deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c2294-140">You can disable Spam ZAP by using the *ZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="c2294-141">Der Parameter *ZapEnabled* für das Cmdlet " **hostedcontentfilterpolicy dient zum** " deaktiviert oder aktiviert sowohl Phishing zap als auch Spam zap für die Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="c2294-141">The *ZapEnabled* parameter on the **Set-HostedContentFilterPolicy** cmdlet disables or enables both Phish ZAP and Spam ZAP for the policy.</span></span> <span data-ttu-id="c2294-142">Sie können Phishing Zap und Spam Zap nicht unabhängig in derselben Richtlinie aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c2294-142">You can't independently enable or disable Phish ZAP and Spam ZAP within the same policy.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="c2294-143">Wie Sie sehen, ob zap Ihre Nachricht verschoben hat</span><span class="sxs-lookup"><span data-stu-id="c2294-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="c2294-144">Um festzustellen, ob zap Ihre Nachricht verschoben hat, können Sie entweder den [Threat Protection-Status Bericht](../../compliance/view-email-security-reports.md#threat-protection-status-report) oder den [Threat-Explorer (und Echt Zeit Erkennungen)](threat-explorer.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2294-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](../../compliance/view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span>

## <a name="disable-zap"></a><span data-ttu-id="c2294-145">Zap deaktivieren</span><span class="sxs-lookup"><span data-stu-id="c2294-145">Disable ZAP</span></span>

<span data-ttu-id="c2294-146">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="c2294-146">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span> <span data-ttu-id="c2294-147">Informationen zum Herstellen einer Verbindung mit Exchange Online Protection PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span><span class="sxs-lookup"><span data-stu-id="c2294-147">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span>

### <a name="disable-malware-zap"></a><span data-ttu-id="c2294-148">Deaktivieren von Malware zap \* \*</span><span class="sxs-lookup"><span data-stu-id="c2294-148">Disable Malware ZAP\*\*</span></span>

<span data-ttu-id="c2294-149">In diesem Beispiel wird zap in der Malware Filterrichtlinie mit dem Namen "Test" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c2294-149">This example disables ZAP in the malware filter policy named "Test".</span></span>

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="c2294-150">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="c2294-150">For detailed syntax and parameter information, see [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span></span>

### <a name="disable-phish-zap-and-spam-zap"></a><span data-ttu-id="c2294-151">Deaktivieren von Phishing Zap und Spam zap</span><span class="sxs-lookup"><span data-stu-id="c2294-151">Disable Phish ZAP and Spam ZAP</span></span>

<span data-ttu-id="c2294-152">In diesem Beispiel wird die Inhaltsfilter Richtlinie "Test" deaktiviert, und Spam zap wird deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c2294-152">This example disables Phish ZAP and Spam ZAP in the content filter policy named "Test".</span></span>

```Powershell
Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="c2294-153">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-hostedcontentfilterpolicy dient zum](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span><span class="sxs-lookup"><span data-stu-id="c2294-153">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span></span>

## <a name="faq"></a><span data-ttu-id="c2294-154">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="c2294-154">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="c2294-155">Was passiert, wenn eine legitime Nachricht in den Junk-e-Mail-Ordner verschoben wird?</span><span class="sxs-lookup"><span data-stu-id="c2294-155">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="c2294-156">Sie sollten den normalen Berichtsprozess für [falsch positive](../../compliance/prevent-email-from-being-marked-as-spam.md)Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="c2294-156">You should follow the normal reporting process for [false-positives](../../compliance/prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="c2294-157">Der einzige Grund, warum die Nachricht aus dem Posteingang in den Junk-e-Mail-Ordner verschoben würde, liegt daran, dass der Dienst festgestellt hat, dass die Nachricht als Spam oder böswillig eingestuft wurde.</span><span class="sxs-lookup"><span data-stu-id="c2294-157">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="c2294-158">Was kann ich tun, wenn ich die Office 365 Quarantäne anstelle des Junk-e-Mail-Ordners verwende?</span><span class="sxs-lookup"><span data-stu-id="c2294-158">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="c2294-159">Zap verschiebt Nachrichten zu diesem Zeitpunkt nicht aus dem Posteingang in die Quarantäne.</span><span class="sxs-lookup"><span data-stu-id="c2294-159">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="c2294-160">Was geschieht, wenn ich über eine benutzerdefinierte Nachrichtenfluss Regel (Block/Zulassungsregel) verfüge?</span><span class="sxs-lookup"><span data-stu-id="c2294-160">What if I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="c2294-161">Von Administratoren erstellte Regeln (Nachrichtenfluss Regeln) oder Block-und Zulassungsregeln haben Vorrang.</span><span class="sxs-lookup"><span data-stu-id="c2294-161">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="c2294-162">Solche Nachrichten werden von den Funktionskriterien ausgeschlossen, sodass die Nachrichtenübermittlung der Regelaktion (Block/Zulassungsregel) folgt.</span><span class="sxs-lookup"><span data-stu-id="c2294-162">Such messages are excluded from the feature criteria so the mail flow will follow the rule action (Block/Allow Rule).</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a><span data-ttu-id="c2294-163">Was passiert, wenn eine Nachricht in einen anderen Ordner verschoben wird (z.b. Posteingangsregel)?</span><span class="sxs-lookup"><span data-stu-id="c2294-163">What if a message is moved to another folder (e.g. Inbox rule)?</span></span>

<span data-ttu-id="c2294-164">Zap funktioniert in diesem Fall weiterhin, es sei denn, die Nachricht wurde gelöscht oder ist in Junk.</span><span class="sxs-lookup"><span data-stu-id="c2294-164">ZAP still works in this case, unless the message has been deleted or is in Junk.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c2294-165">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c2294-165">Related Topics</span></span>

[<span data-ttu-id="c2294-166">Antispamschutz für Office 365-E-Mails</span><span class="sxs-lookup"><span data-stu-id="c2294-166">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="c2294-167">Blockieren von E-Mail-Spam mit dem Office 365-Spamfilter zur Vermeidung von falsch negativen Einträgen</span><span class="sxs-lookup"><span data-stu-id="c2294-167">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
