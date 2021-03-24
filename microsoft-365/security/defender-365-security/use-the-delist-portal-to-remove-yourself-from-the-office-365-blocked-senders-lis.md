---
title: Sich selbst aus der Liste der blockierten Absender entfernen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie sich mithilfe des Listenentfernungsportals selbst aus der Microsoft 365-Liste der blockierten Absender entfernen können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c4488f5e5607d71da35b2921e863fb02195467e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061855"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="97e0d-103">Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender zu entfernen</span><span class="sxs-lookup"><span data-stu-id="97e0d-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="97e0d-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="97e0d-104">**Applies to**</span></span>
- [<span data-ttu-id="97e0d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="97e0d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="97e0d-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="97e0d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="97e0d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97e0d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="97e0d-108">Erhalten Sie eine Fehlermeldung, wenn Sie versuchen, eine E-Mail an einen Empfänger zu senden, dessen E-Mail-Adresse sich in Microsoft 365 befindet?</span><span class="sxs-lookup"><span data-stu-id="97e0d-108">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="97e0d-109">Wenn Sie glauben, dass Sie die Fehlermeldung nicht erhalten sollten, können Sie das Listenentfernungsportal verwenden, um sich selbst aus der Liste der blockierten Absender zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="97e0d-109">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="97e0d-110">Um was handelt es sich bei der Liste der blockierten Absender?</span><span class="sxs-lookup"><span data-stu-id="97e0d-110">What is the blocked senders list?</span></span>

<span data-ttu-id="97e0d-111">Microsoft verwendet die Liste der blockierten Absender, um seine Kunden vor Spam, Spoofing und Phishingangriffen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="97e0d-111">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="97e0d-112">Ihre IP-Adresse, d. h. die Adresse, mit der sich Ihr Computer im Internet identifiziert, wurde aus einem von vielen möglichen Gründen als mögliche Bedrohung für Microsoft 365 kategorisiert.</span><span class="sxs-lookup"><span data-stu-id="97e0d-112">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="97e0d-113">Wenn Microsoft 365 die IP-Adresse zu der Liste hinzufügt, wird jede weitere Kommunikation zwischen der IP-Adresse und unseren Kunden über unsere Rechenzentren verhindert.</span><span class="sxs-lookup"><span data-stu-id="97e0d-113">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="97e0d-114">Sie merken, dass Sie der Liste hinzugefügt wurden, wenn Sie auf eine E-Mail eine Antwort erhalten, die in etwa folgende Fehlermeldung enthält:</span><span class="sxs-lookup"><span data-stu-id="97e0d-114">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="97e0d-115">550 5.7.606-649 Zugriff verweigert, gesperrte IP-Absenderadresse [_IP address_]. Um die Entfernung aus der Liste anzufordern, besuchen Sie <https://sender.office.com/>, und folgen Sie den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="97e0d-115">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit <https://sender.office.com/> and follow the directions.</span></span> <span data-ttu-id="97e0d-116">Weitere Informationen hierzu finden Sie unter [E-Mail-Unzustellbarkeitsberichte in Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="97e0d-116">For more information see [Email non-delivery reports in Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="97e0d-117">wobei _IP address_ die IP-Adresse des Computers ist, auf dem der E-Mail-Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="97e0d-117">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="97e0d-118">Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender zu entfernen</span><span class="sxs-lookup"><span data-stu-id="97e0d-118">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="97e0d-119">Wechseln Sie in einem Webbrowser zu <https://sender.office.com>.</span><span class="sxs-lookup"><span data-stu-id="97e0d-119">In a web browser, go to <https://sender.office.com>.</span></span>

2. <span data-ttu-id="97e0d-p104">Folgen Sie den Anweisungen auf dem Bildschirm. Verwenden Sie die E-Mail-Adresse, an die die Fehlermeldung gesendet wurde, und die IP-Adresse, die in der Fehlermeldung angegeben ist. Sie können nur eine E-Mail-Adresse und eine IP-Adresse pro Besuch eingeben.</span><span class="sxs-lookup"><span data-stu-id="97e0d-p104">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="97e0d-123">Klicken Sie auf **Absenden**.</span><span class="sxs-lookup"><span data-stu-id="97e0d-123">Click **Submit**.</span></span>

    <span data-ttu-id="97e0d-124">Das Portal sendet eine E-Mail an die E-Mail-Adresse, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="97e0d-124">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="97e0d-125">Die E-Mail wird in etwa wie folgt aussehen: ![Screenshot einer E-Mail, die Sie beim Senden einer Anforderung über das Listenentfernungsportal erhalten](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png).</span><span class="sxs-lookup"><span data-stu-id="97e0d-125">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="97e0d-126">Klicken Sie auf den Bestätigungslink in der E-Mail, die vom Listenentfernungsportal an Sie gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="97e0d-126">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="97e0d-127">Damit kehren Sie zum Azure-Listenentfernungsportal zurück.</span><span class="sxs-lookup"><span data-stu-id="97e0d-127">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="97e0d-128">Klicken Sie im Listenentfernungsportal auf **IP aus Liste entfernen**.</span><span class="sxs-lookup"><span data-stu-id="97e0d-128">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="97e0d-129">Nachdem Sie die IP-Adresse aus der Liste der blockierten Absender entfernt haben, werden E-Mails von dieser IP-Adresse Empfängern, die Microsoft 365 verwenden, wieder zugestellt.</span><span class="sxs-lookup"><span data-stu-id="97e0d-129">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="97e0d-130">Stellen Sie daher sicher, dass die E-Mails von dieser IP-Adresse keine beleidigenden oder böswilligen Inhalte aufweisen, da die IP-Adresse anderenfalls erneut blockiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="97e0d-130">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="97e0d-131">Es kann bis zu 24 Stunden dauern oder die Ergebnisse können sehr unterschiedlich ausfallen, bevor die Beschränkungen aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="97e0d-131">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="97e0d-132">Weitere Informationen finden Sie unter Erstellen von Listen sicherer Absender [in EOP](create-safe-sender-lists-in-office-365.md) und Ausgehender Spamschutz [in EOP,](outbound-spam-controls.md) um zu verhindern, dass eine IP blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="97e0d-132">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>