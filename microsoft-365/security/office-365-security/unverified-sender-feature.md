---
title: Nicht überprüfter Absender
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel wird beschrieben, wie Sie verhindern können, dass Phishing-Nachrichten Ihr Postfach, Outlook.com und Outlook im Internet erreichen.
ms.openlocfilehash: 2172a9890d629dd840c3e2e2591d78546899d17e
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224875"
---
# <a name="unverified-sender"></a><span data-ttu-id="67288-103">Nicht überprüfter Absender</span><span class="sxs-lookup"><span data-stu-id="67288-103">Unverified Sender</span></span>

> [!NOTE]
> <span data-ttu-id="67288-104">Diese Updates werden jetzt ausgerollt und sind möglicherweise nicht für alle Benutzer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="67288-104">These updates are rolling out now, and might not be available for all users.</span></span> <span data-ttu-id="67288-105">Dieses Feature wird für Enterprise-Outlook.com und Enterprise Outlook Win32-Desktopbenutzer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="67288-105">This feature is supported for Enterprise Outlook.com and Enterprise Outlook Win32 desktop users.</span></span> <span data-ttu-id="67288-106">Es steht derzeit nicht für Consumer Office 365-Benutzer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="67288-106">It is not currently available for consumer Office 365 users.</span></span>

<span data-ttu-id="67288-107">Um zu verhindern, dass Phishing-Nachrichten Ihr Postfach erreichen, überprüft Office 365, ob die Absender die Personen sind, die Sie sagen, und verdächtige Nachrichten als Junk-e-Mail markieren.</span><span class="sxs-lookup"><span data-stu-id="67288-107">To prevent phishing messages from reaching your mailbox, Office 365 verifies that the senders are who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67288-108">Wenn eine Nachricht als Phishing-Betrug markiert ist, zeigt Outlook eine Warnung oben auf der Seite an, aber alle Links in der Nachricht können weiterhin geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="67288-108">When a message is marked as a phishing scam, Outlook displays a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="67288-109">Wie kann ich eine verdächtige Nachricht im Posteingang identifizieren?</span><span class="sxs-lookup"><span data-stu-id="67288-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="67288-110">Outlook zeigt Indikatoren an, wenn der Absender einer Nachricht entweder nicht identifiziert werden kann oder sich Ihre Identität von dem unterscheidet, was Sie in der von-Adresse sehen.</span><span class="sxs-lookup"><span data-stu-id="67288-110">Outlook shows indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="67288-111">Im Absender Bild wird ein "?" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="67288-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="67288-112">Wenn Office 365 die Identität des Absenders nicht mithilfe von e-Mail-Authentifizierungstechniken überprüfen können, wird im Absender Bild ein '? ' angezeigt.</span><span class="sxs-lookup"><span data-stu-id="67288-112">When Office 365 can't verify the identity of the sender using email authentication techniques, a '?' is displayed in the sender image.</span></span>

![Nachricht hat die Überprüfung nicht übergeben](../../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="67288-114">Nicht jede Nachricht, die nicht authentifiziert werden kann, ist bösartig.</span><span class="sxs-lookup"><span data-stu-id="67288-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="67288-115">Sie sollten jedoch mit der Interaktion mit Nachrichten vorsichtig sein, die nicht authentifiziert werden, wenn Sie den Absender nicht erkennen.</span><span class="sxs-lookup"><span data-stu-id="67288-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="67288-116">Oder wenn Sie einen Absender erkennen, der normalerweise nicht über ein "?" im Absender Bild verfügt, aber Sie ihn plötzlich sehen, könnte dies ein Zeichen sein, bei dem der Absender gefälscht wird.</span><span class="sxs-lookup"><span data-stu-id="67288-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="67288-117">Vorgehensweise Verwalten der Nachrichten, die nicht überprüfte Absender Behandlung erhalten</span><span class="sxs-lookup"><span data-stu-id="67288-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="67288-118">Wenn Sie ein Office 365er Kunde sind, können Sie dieses Feature über das Office 365 Security & Compliance Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="67288-118">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance Center.</span></span>

- <span data-ttu-id="67288-119">Im Security & Compliance Center können globale oder Sicherheitsadministratoren das Feature durch Schutz vor Spoofing unter der Anti-Phishing-Richtlinie aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="67288-119">In the Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="67288-120">Darüber hinaus können Sie das Cmdlet " **AntiPhishPolicy** " in Exchange Online PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="67288-120">Additionally, you can use the **Set-AntiPhishPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="67288-121">Ausführliche Informationen finden Sie unter [Anti-Phishing Protection in Office 365](anti-phishing-protection.md) und [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span><span class="sxs-lookup"><span data-stu-id="67288-121">For details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span></span>

    ![Bearbeiten von nicht authentifizierten Absendern in der grafischen Benutzeroberfläche.](../../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="67288-123">Wenn ein Administrator ein falsch positives Ergebnis erkannt hat und ein Absender nicht überprüfte Absender Behandlung erhalten soll, können Sie eine der folgenden Aktionen ausführen, um den Absender zur Spoof-Zulassungsliste "Spoof Intelligence" hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="67288-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>

  - <span data-ttu-id="67288-124">Fügen Sie das Domänenpaar über die Spoof Intelligence-Einblicke hinzu.</span><span class="sxs-lookup"><span data-stu-id="67288-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="67288-125">Ausführliche Informationen finden Sie unter [Exemplarische Vorgehensweise: Spoof Intelligence Insight](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="67288-125">For details, see [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

  - <span data-ttu-id="67288-126">Fügen Sie das Domänenpaar über das Cmdlet " **PhishFilterPolicy** " in Exchange Online PowerShell hinzu.</span><span class="sxs-lookup"><span data-stu-id="67288-126">Add the domain pair through the **Set-PhishFilterPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="67288-127">Ausführliche Informationen finden Sie unter [Festlegen von PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) und [Einrichten Office 365 ATP-Richtlinien für Anti-Phishing und Anti-Phishing](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="67288-127">For details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="67288-128">Darüber hinaus wird die nicht verifizierte Absender Behandlung nicht angewendet, wenn die Nachricht über Nachrichtenfluss Regeln (auch bekannt als Transportregeln) oder über die Liste sicherer Domänen (Anti-Spam Policies) an den Posteingang übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="67288-128">Additionally, we don't apply the unverified sender treatment if the message was delivered to the Inbox via mail flow rules (also known as transport rules) or the Safe Domain List (anti-spam policies).</span></span>

## <a name="how-to-manage-the-via-tag"></a><span data-ttu-id="67288-129">Verwalten des "Via"-Tags</span><span class="sxs-lookup"><span data-stu-id="67288-129">How to manage the 'via' tag</span></span> 

<span data-ttu-id="67288-130">Wenn Sie ein Office 365er Kunde sind, können Sie diese Funktion über das Office 365 Security & Compliance Center verwalten, genauso wie Sie die nicht überprüfte Absender Behandlung verwalten.</span><span class="sxs-lookup"><span data-stu-id="67288-130">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance center, the same way that you manage the unverified sender treatment.</span></span> <span data-ttu-id="67288-131">Wenn Sie den Absender der Spoof-Spoofing-Zulassungsliste hinzufügen, wird die "über"-Behandlung nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="67288-131">If you add the sender to the Spoof Intelligence spoof allow list, the 'via' treatment will not be applied.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="67288-132">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="67288-132">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="67288-133">Welche Kriterien verwendet Outlook.com und Outlook-Win32-Desktop, um die Eigenschaften "?" und "Via" hinzuzufügen?</span><span class="sxs-lookup"><span data-stu-id="67288-133">What criteria does Outlook.com and Outlook Win32 desktop use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="67288-134">Für das "?" im Absender Bild: Outlook.com erfordert, dass die Nachricht entweder die SPF-oder die DKIM-Authentifizierung übergibt und entweder einen dmarc-Pass oder eine kombinierte Authentifizierungs Übergabe von Office 365 Spoof Intelligence erhält.</span><span class="sxs-lookup"><span data-stu-id="67288-134">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="67288-135">Ausführliche Informationen finden Sie unter [Einrichten von SPF in Office 365 zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) und [Verwenden von DKIM zum Überprüfen von ausgehenden e-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet wurden](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="67288-135">For details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="67288-136">Für das via-Tag: Wenn sich die Domäne in der von-Adresse von der Domäne in der DKIM-Signatur oder von der SMTP-e-Mail-Nachricht unterscheidet, zeigt Outlook.com die Domäne in einem dieser beiden Felder an (es wird die DKIM-Signatur bevorzugt).</span><span class="sxs-lookup"><span data-stu-id="67288-136">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a><span data-ttu-id="67288-137">Wie entferne ich das "?", ohne die Spoofing-Zulassungsliste "Spoof Intelligence" zu verwenden?</span><span class="sxs-lookup"><span data-stu-id="67288-137">How do I remove the '?' without utilizing the Spoof Intelligence spoof allow list?</span></span>

<span data-ttu-id="67288-138">Für das "?" im Absender Bild: als Absender sollten Sie die Nachricht entweder mit SPF oder DKIM authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="67288-138">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="67288-139">Für das via-Tag: als Absender sollten Sie sicherstellen, dass entweder die Domäne in der DKIM-Signatur oder die SMTP-e-Mail von dieselbe oder eine Unterdomäne der Domäne in der von-Adresse ist.</span><span class="sxs-lookup"><span data-stu-id="67288-139">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="67288-140">Wird dies für jede Nachricht, die die Authentifizierung nicht übergibt, von Outlook.com und Outlook Win32 Desktop angezeigt?</span><span class="sxs-lookup"><span data-stu-id="67288-140">Do Outlook.com and Outlook Win32 desktop show this for every message that doesn't pass authentication?</span></span>

<span data-ttu-id="67288-141">Nicht unbedingt.</span><span class="sxs-lookup"><span data-stu-id="67288-141">Not necessarily.</span></span> <span data-ttu-id="67288-142">Office 365 möglicherweise andere Eigenschaften in der Nachricht zur Authentifizierung des Absenders.</span><span class="sxs-lookup"><span data-stu-id="67288-142">Office 365 may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="67288-143">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="67288-143">Related topics</span></span>

[<span data-ttu-id="67288-144">Schützen Ihres Outlook.com-e-Mail-Kontos</span><span class="sxs-lookup"><span data-stu-id="67288-144">Help protect your Outlook.com email account</span></span>](https://support.microsoft.com/en-us/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="67288-145">Umgang mit Phishing oder Spoofing in Outlook.com</span><span class="sxs-lookup"><span data-stu-id="67288-145">Deal with phishing or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="67288-146">Filtern von Junk-e-Mails und Spam in Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="67288-146">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
