---
title: Nicht überprüfter Absender
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/11/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Um zu verhindern, dass Phishing-Nachrichten Ihr Postfach erreichen, überprüfen Outlook.com und Outlook im Internet, ob der Absender der Benutzer ist, der Sie sagen, und verdächtige Nachrichten als Junk-e-Mail markieren.
ms.openlocfilehash: 89cd473a7b7f2ff663d7ee1eee41f84144dee6d7
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866437"
---
# <a name="unverified-sender"></a><span data-ttu-id="91b7c-103">Nicht überprüfter Absender</span><span class="sxs-lookup"><span data-stu-id="91b7c-103">Unverified Sender</span></span>

> [!NOTE] 
> <span data-ttu-id="91b7c-104">Diese Updates werden jetzt ausgerollt und sind möglicherweise noch nicht für alle Benutzer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="91b7c-104">These updates are rolling out now, and might not be available yet for all users.</span></span> <span data-ttu-id="91b7c-105">Dieses Feature wird für Benutzer von Enterprise-Outlook.com unterstützt.</span><span class="sxs-lookup"><span data-stu-id="91b7c-105">This feature is supported for Enterprise outlook.com users.</span></span> <span data-ttu-id="91b7c-106">Es steht derzeit nicht für Consumer-Outlook.com zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="91b7c-106">It is not currently available for consumer outlook.com.</span></span>

<span data-ttu-id="91b7c-107">Um zu verhindern, dass Phishing-Nachrichten Ihr Postfach erreichen, überprüfen Outlook.com und Outlook im Internet, ob der Absender der Benutzer ist, der Sie sagen, und verdächtige Nachrichten als Junk-e-Mail markieren.</span><span class="sxs-lookup"><span data-stu-id="91b7c-107">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91b7c-108">Wenn eine Nachricht als Phishing-Betrug markiert ist, zeigen Outlook.com und Outlook im Internet eine Warnung oben auf der Seite an, aber alle Links in der Nachricht können weiterhin geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="91b7c-108">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="91b7c-109">Wie kann ich eine verdächtige Nachricht im Posteingang identifizieren?</span><span class="sxs-lookup"><span data-stu-id="91b7c-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="91b7c-110">Outlook.com und Outlook im Internet zeigen Indikatoren an, wenn der Absender einer Nachricht entweder nicht identifiziert werden kann oder sich Ihre Identität von dem unterscheidet, was Sie in der von-Adresse sehen.</span><span class="sxs-lookup"><span data-stu-id="91b7c-110">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="91b7c-111">Im Absender Bild wird ein "?" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91b7c-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="91b7c-112">Wenn Outlook.com und Outlook im Internet die Identität des Absenders nicht mithilfe von e-Mail-Authentifizierungstechniken überprüfen können, wird im Absender Foto ein "?" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91b7c-112">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span> 

![Nachricht hat die Überprüfung nicht übergeben](../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="91b7c-114">Nicht jede Nachricht, die nicht authentifiziert werden kann, ist bösartig.</span><span class="sxs-lookup"><span data-stu-id="91b7c-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="91b7c-115">Sie sollten jedoch mit der Interaktion mit Nachrichten vorsichtig sein, die nicht authentifiziert werden, wenn Sie den Absender nicht erkennen.</span><span class="sxs-lookup"><span data-stu-id="91b7c-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="91b7c-116">Oder wenn Sie einen Absender erkennen, der normalerweise nicht über ein "?" im Absender Bild verfügt, aber Sie ihn plötzlich sehen, könnte dies ein Zeichen sein, bei dem der Absender gefälscht wird.</span><span class="sxs-lookup"><span data-stu-id="91b7c-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>


## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="91b7c-117">Vorgehensweise Verwalten der Nachrichten, die nicht überprüfte Absender Behandlung erhalten</span><span class="sxs-lookup"><span data-stu-id="91b7c-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="91b7c-118">Wenn Sie ein Office 365er Kunde sind, können Sie diese Funktion über das Security #a0 Compliance Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="91b7c-118">If you are an Office 365 customer you can manage this feature through the Security & Compliance Center.</span></span> 

- <span data-ttu-id="91b7c-119">Im Office 365 Security #a0 Compliance Center können globale oder Sicherheitsadministratoren das Feature über den Schutz vor Spoofing unter der Anti-Phishing-Richtlinie aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="91b7c-119">In the Office 365 Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="91b7c-120">Darüber hinaus kann es über das Cmdlet "AntiPhishPolicy" verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="91b7c-120">Additionally, it can be managed through the ‘Set-AntiPhishPolicy’ cmdlet.</span></span> <span data-ttu-id="91b7c-121">Weitere Informationen finden Sie unter [Anti-Phishing Protection in Office 365](anti-phishing-protection.md) und [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span><span class="sxs-lookup"><span data-stu-id="91b7c-121">For more details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span></span>

    ![Bearbeiten von nicht authentifizierten Absendern in der grafischen Benutzeroberfläche.](../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="91b7c-123">Wenn ein Administrator ein falsch positives Ergebnis erkannt hat und ein Absender nicht überprüfte Absender Behandlung erhalten soll, können Sie eine der folgenden Aktionen ausführen, um den Absender zur Spoof-Zulassungsliste "Spoof Intelligence" hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="91b7c-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>
        
    - <span data-ttu-id="91b7c-124">Fügen Sie das Domänenpaar über die Spoof Intelligence-Einblicke hinzu.</span><span class="sxs-lookup"><span data-stu-id="91b7c-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="91b7c-125">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Spoof Intelligence Insight](https://docs.microsoft.com/microsoft-365/security/office-365-security/walkthrough-spoof-intelligence-insight).</span><span class="sxs-lookup"><span data-stu-id="91b7c-125">For more details, see [Walkthrough: spoof intelligence insight](https://docs.microsoft.com/microsoft-365/security/office-365-security/walkthrough-spoof-intelligence-insight).</span></span>
                
    - <span data-ttu-id="91b7c-126">Fügen Sie das Domänenpaar über das PhishFilterPolicy-Cmdlet hinzu.</span><span class="sxs-lookup"><span data-stu-id="91b7c-126">Add the domain pair through the PhishFilterPolicy cmdlet.</span></span> <span data-ttu-id="91b7c-127">Weitere Informationen finden Sie unter [festlegen-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) und [Einrichten Office 365 ATP-Anti-Phishing-und Anti-Phishing-Richtlinien](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="91b7c-127">For more details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).</span></span>

<span data-ttu-id="91b7c-128">Darüber hinaus wenden wir die nicht überprüfte Absender Behandlung nicht an, wenn Sie über eine Liste der zugelassenen Administratoren an den Posteingang übermittelt wurde, einschließlich e-Mail-Transport Regeln (ETRs), Liste sicherer Domänen (Anti-Spam-Richtlinie), Liste sicherer Absender oder ein Benutzer hat diesen Benutzer als "sicheren Absender" in ihrer festgelegt Inbox.</span><span class="sxs-lookup"><span data-stu-id="91b7c-128">Additionally, we do not apply the unverified sender treatment if it was delivered to the inbox via an admin allow list, including Email Transport Rules (ETRs), Safe Domain List (Anti-Spam Policy), Safe Sender List or a user has set this user as a “Safe Sender” in their inbox.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="91b7c-129">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="91b7c-129">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="91b7c-130">Welche Kriterien werden von Outlook.com und Outlook im Internet verwendet, um die Eigenschaften "?" und "Via" hinzuzufügen?</span><span class="sxs-lookup"><span data-stu-id="91b7c-130">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="91b7c-131">Für das "?" im Absender Bild: Outlook.com erfordert, dass die Nachricht entweder die SPF-oder die DKIM-Authentifizierung übergibt und entweder einen dmarc-Pass oder eine kombinierte Authentifizierungs Übergabe von Office 365 Spoof Intelligence erhält.</span><span class="sxs-lookup"><span data-stu-id="91b7c-131">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="91b7c-132">Weitere Informationen finden Sie unter [Einrichten von SPF in Office 365 zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) und [Verwenden von DKIM zum Überprüfen von ausgehenden e-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet wurden](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="91b7c-132">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="91b7c-133">Für das via-Tag: Wenn sich die Domäne in der von-Adresse von der Domäne in der DKIM-Signatur oder von der SMTP-e-Mail-Nachricht unterscheidet, zeigt Outlook.com die Domäne in einem dieser beiden Felder an (es wird die DKIM-Signatur bevorzugt).</span><span class="sxs-lookup"><span data-stu-id="91b7c-133">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the-"></a><span data-ttu-id="91b7c-134">Wie entferne ich das "?"</span><span class="sxs-lookup"><span data-stu-id="91b7c-134">How do I remove the '?'</span></span>

<span data-ttu-id="91b7c-135">Für das "?" im Absender Bild: als Absender sollten Sie die Nachricht entweder mit SPF oder DKIM authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="91b7c-135">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="91b7c-136">Für das via-Tag: als Absender sollten Sie sicherstellen, dass entweder die Domäne in der DKIM-Signatur oder die SMTP-e-Mail von dieselbe oder eine Unterdomäne der Domäne in der von-Adresse ist.</span><span class="sxs-lookup"><span data-stu-id="91b7c-136">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="91b7c-137">Zeigt Outlook.com und Outlook im Internet dies für jede Nachricht, die die Authentifizierung nicht übergibt?</span><span class="sxs-lookup"><span data-stu-id="91b7c-137">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="91b7c-138">Nicht unbedingt.</span><span class="sxs-lookup"><span data-stu-id="91b7c-138">Not necessarily.</span></span> <span data-ttu-id="91b7c-139">Outlook.com und Outlook im Internet haben möglicherweise andere Eigenschaften in der Nachricht zur Authentifizierung des Absenders.</span><span class="sxs-lookup"><span data-stu-id="91b7c-139">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="91b7c-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="91b7c-140">Related topics</span></span>

[<span data-ttu-id="91b7c-141">Schützen Ihres Outlook.com-e-Mail-Kontos</span><span class="sxs-lookup"><span data-stu-id="91b7c-141">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="91b7c-142">Umgang mit Missbrauch, Phishing oder Spoofing in Outlook.com</span><span class="sxs-lookup"><span data-stu-id="91b7c-142">Deal with abuse, phishing, or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="91b7c-143">Filtern von Junk-e-Mails und Spam in Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="91b7c-143">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
