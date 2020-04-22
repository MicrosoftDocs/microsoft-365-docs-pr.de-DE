---
title: Verwenden Sie das Delist-Portal, um sich selbst aus der Liste blockierter Absender zu entfernen.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
description: Erhalten Sie eine Fehlermeldung, wenn Sie versuchen, eine e-Mail an einen Empfänger zu senden, dessen e-Mail-Adresse sich in Microsoft 365 befindet? Wenn Sie der Meinung sind, dass Sie die Fehlermeldung nicht erhalten sollten, können Sie das Delist-Portal verwenden, um sich selbst aus der Liste blockierter Absender zu entfernen.
ms.openlocfilehash: 39f2c9335f162f26e8bf07a213236e0e0eefef2a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636404"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="deaed-104">Verwenden Sie das Delist-Portal, um sich selbst aus der Liste blockierter Absender zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="deaed-104">Use the delist portal to remove yourself from the blocked senders list</span></span>

<span data-ttu-id="deaed-p102">Erhalten Sie eine Fehlermeldung, wenn Sie versuchen, eine e-Mail an einen Empfänger zu senden, dessen e-Mail-Adresse sich in Microsoft 365 befindet? Wenn Sie der Meinung sind, dass Sie die Fehlermeldung nicht erhalten sollten, können Sie das Delist-Portal verwenden, um sich selbst aus der Liste blockierter Absender zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="deaed-p102">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365? If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="deaed-107">Was ist die Liste blockierter Absender?</span><span class="sxs-lookup"><span data-stu-id="deaed-107">What is the blocked senders list?</span></span>

<span data-ttu-id="deaed-p103">Microsoft verwendet die Liste blockierter Absender zum Schutz seiner Kunden vor Spam, Spoofing und Phishing-Angriffen. Die IP-Adresse Ihres e-Mail-Servers, also die Adresse, die Ihr e-Mail-Server verwendet, um sich selbst im Internet zu identifizieren, wurde aus einer Vielzahl von Gründen als potenzielle Bedrohung für Microsoft 365 gekennzeichnet. Wenn Microsoft 365 die IP-Adresse zur Liste hinzufügt, wird die gesamte weitere Kommunikation zwischen der IP-Adresse und einem unserer Kunden durch unsere Rechenzentren verhindert.</span><span class="sxs-lookup"><span data-stu-id="deaed-p103">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks. Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons. When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="deaed-111">Sie merken, dass Sie der Liste hinzugefügt wurden, wenn Sie auf eine E-Mail eine Antwort erhalten, die in etwa folgende Fehlermeldung enthält:</span><span class="sxs-lookup"><span data-stu-id="deaed-111">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="deaed-112">550 5.7.606-649 Zugriff verweigert, gesperrte IP-Absenderadresse [_IP address_]. Um die Entfernung aus der Liste anzufordern, besuchen Sie https://sender.office.com/, und folgen Sie den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="deaed-112">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions.</span></span> <span data-ttu-id="deaed-113">Weitere Informationen hierzu finden Sie unter [E-Mail-Unzustellbarkeitsberichte in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="deaed-113">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="deaed-114">wobei _IP address_ die IP-Adresse des Computers ist, auf dem der E-Mail-Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="deaed-114">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="deaed-115">So verwenden Sie das Delist-Portal, um sich selbst aus der Liste blockierter Absender zu entfernen</span><span class="sxs-lookup"><span data-stu-id="deaed-115">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="deaed-116">Wechseln Sie in einem Webbrowser zu [https://sender.office.com](https://sender.office.com).</span><span class="sxs-lookup"><span data-stu-id="deaed-116">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>

2. <span data-ttu-id="deaed-p105">Folgen Sie den Anweisungen auf dem Bildschirm. Verwenden Sie die E-Mail-Adresse, an die die Fehlermeldung gesendet wurde, und die IP-Adresse, die in der Fehlermeldung angegeben ist. Sie können nur eine E-Mail-Adresse und eine IP-Adresse pro Besuch eingeben.</span><span class="sxs-lookup"><span data-stu-id="deaed-p105">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="deaed-120">Klicken Sie auf **Absenden**.</span><span class="sxs-lookup"><span data-stu-id="deaed-120">Click **Submit**.</span></span>

    <span data-ttu-id="deaed-121">Das Portal sendet eine E-Mail an die E-Mail-Adresse, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="deaed-121">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="deaed-122">Die E-Mail wird in etwa wie folgt aussehen: ![Screenshot einer E-Mail, die Sie beim Senden einer Anforderung über das Listenentfernungsportal erhalten](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png).</span><span class="sxs-lookup"><span data-stu-id="deaed-122">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="deaed-123">Klicken Sie auf den Bestätigungslink in der E-Mail, die vom Listenentfernungsportal an Sie gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="deaed-123">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="deaed-124">Damit kehren Sie zum Azure-Listenentfernungsportal zurück.</span><span class="sxs-lookup"><span data-stu-id="deaed-124">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="deaed-125">Klicken Sie im Listenentfernungsportal auf **IP aus Liste entfernen**.</span><span class="sxs-lookup"><span data-stu-id="deaed-125">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="deaed-p107">Nachdem die IP-Adresse aus der Liste blockierter Absender entfernt wurde, werden e-Mail-Nachrichten von dieser IP-Adresse an Empfänger übermittelt, die Microsoft 365 verwenden. Vergewissern Sie sich also, dass Sie sicher sind, dass e-Mails, die von dieser IP-Adresse gesendet werden, nicht missbräuchlich oder böswillig sind. Andernfalls wird die IP-Adresse möglicherweise erneut blockiert.</span><span class="sxs-lookup"><span data-stu-id="deaed-p107">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365. So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="deaed-128">Es kann bis zu 24 Stunden dauern oder die Ergebnisse können sehr unterschiedlich ausfallen, bevor die Beschränkungen aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="deaed-128">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="deaed-129">Informationen dazu, wie Sie verhindern, dass die IP gesperrt wird, finden Sie unter [Erstellen von Listen sicherer Absender in Office 365](create-safe-sender-lists-in-office-365.md) und [Schutz vor ausgehenden Spam in Office 365](outbound-spam-controls.md).</span><span class="sxs-lookup"><span data-stu-id="deaed-129">See [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in Office 365](outbound-spam-controls.md) to prevent IP from being blacklisted.</span></span>
