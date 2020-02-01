---
title: Verwalten sicherer Absenderlisten für Absender von Massen-E-Mails
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 'Wenn Sie Listen sicherer Absender verwenden möchten, sollten Sie wissen, dass die Verarbeitung in Exchange Online Protection (EOP) und Outlook auf verschiedene Weise erfolgt. Der Dienst berücksichtigt sichere Absender und Domänen, indem er die RFC 5321.MailFrom-Adresse und die RFC 5322.From-Adresse prüft, während Outlook die RFC 5322.From-Adresse zur Liste sicherer Absender eines Benutzers hinzufügt. (Anmerkung: Der Dienst prüft sowohl die 5321.MailFrom-Adresse als auch die 5322.From-Adresse auf blockierte Absender und Domänen.)'
ms.openlocfilehash: aaede7cab2e640603c20804f4015e19f61b6c2f3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598942"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="bf155-105">Verwalten sicherer Absenderlisten für Absender von Massen-E-Mails</span><span class="sxs-lookup"><span data-stu-id="bf155-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="bf155-106">Wenn Sie Listen sicherer Absender verwenden möchten, sollten Sie wissen, dass die Verarbeitung in Exchange Online Protection (EOP) und Outlook auf verschiedene Weise erfolgt.</span><span class="sxs-lookup"><span data-stu-id="bf155-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="bf155-107">Der Office 365 Dienst respektiert sichere Absender und Domänen, indem er die `RFC 5321.MailFrom` Adresse und die `RFC 5322.From` Adresse überprüft, während Outlook die Adresse `RFC 5322.From` der Liste sicherer Absender eines Benutzers hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="bf155-107">The Office 365 service respects safe senders and domains by inspecting the `RFC 5321.MailFrom` address and the `RFC 5322.From` address, while Outlook adds the `RFC 5322.From` address to a user's safe sender list.</span></span> <span data-ttu-id="bf155-108">(Hinweis: der Dienst untersucht sowohl `5321.MailFrom` Adresse als auch `5322.From` Adresse für blockierte Absender und Domänen.)</span><span class="sxs-lookup"><span data-stu-id="bf155-108">(Note: The service inspects both the `5321.MailFrom` address and `5322.From` address for blocked senders and domains.)</span></span>

<span data-ttu-id="bf155-109">Die `SMTP MAIL FROM` Adresse, auch bekannt als die `RFC 5321.MailFrom address`, ist die e-Mail-Adresse, die zum Durchführen von SPF-Überprüfungen verwendet wird, und wenn die e-Mail nicht zugestellt werden kann, der Pfad, an den die zurückgegebene Nachricht übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="bf155-109">The `SMTP MAIL FROM` address, otherwise known as the `RFC 5321.MailFrom address`, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered.</span></span> <span data-ttu-id="bf155-110">Es handelt sich um diese e-Mail-Adresse `Return-Path` , die standardmäßig in die Nachrichtenkopfzeilen eingefügt wird, obwohl es dem Absender möglich ist, `Return-Path` eine andere Adresse festzulegen.</span><span class="sxs-lookup"><span data-stu-id="bf155-110">It's this email address that is placed into the `Return-Path` in the message headers by default, though it's possible for the sender to designate a different `Return-Path` address.</span></span>

<span data-ttu-id="bf155-111">Die `From:` Adresse in den Nachrichtenkopfzeilen, die sonst als `RFC 5322.From` Adresse bezeichnet wird, ist die e-Mail-Adresse, die im e-Mail-Client wie Outlook angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bf155-111">The `From:` address in the message headers, otherwise known as the `RFC 5322.From` address, is the email address that is displayed in the mail client such as Outlook.</span></span>

<span data-ttu-id="bf155-112">Ein Großteil der Zeit sind die `5321.MailFrom` - `5322.From` und-Adressen identisch.</span><span class="sxs-lookup"><span data-stu-id="bf155-112">Much of the time, the `5321.MailFrom` and `5322.From` addresses are the same.</span></span> <span data-ttu-id="bf155-113">Dies ist z. B. bei der Kommunikation zwischen zwei privaten Nutzern normal.</span><span class="sxs-lookup"><span data-stu-id="bf155-113">This is typical for person-to-person communication.</span></span> <span data-ttu-id="bf155-114">Wenn allerdings die E-Mail im Auftrag eines anderen Benutzers gesendet wird, sind die Adressen häufig verschieden.</span><span class="sxs-lookup"><span data-stu-id="bf155-114">However, when email is sent on behalf of someone else, the addresses are frequently different.</span></span> <span data-ttu-id="bf155-115">Dies ist am häufigsten bei Massen-E-Mail-Nachrichten der Fall.</span><span class="sxs-lookup"><span data-stu-id="bf155-115">This usually happens most often for bulk email messages.</span></span>

<span data-ttu-id="bf155-116">Nehmen wir beispielsweise an, dass die Blue Yonder Airlines Margie es Travel angeheuert hat, um Ihre e-Mail-Werbung zu senden.</span><span class="sxs-lookup"><span data-stu-id="bf155-116">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="bf155-117">Sie finden dann eine E-Mail in Ihrem Posteingang vor, die vom Absender blueyonder@news.blueyonderairlines.com stammt.</span><span class="sxs-lookup"><span data-stu-id="bf155-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="bf155-118">In diesem Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bf155-118">In this example:</span></span>

- <span data-ttu-id="bf155-119">Die `5321.MailFrom` Adresse lautet blueyonder.Airlines@margiestravel.com.</span><span class="sxs-lookup"><span data-stu-id="bf155-119">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="bf155-120">Die `5322.From` Adresse lautet blueyonder@News.blueyonderairlines.com, was Sie in Outlook sehen.</span><span class="sxs-lookup"><span data-stu-id="bf155-120">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="bf155-121">Um zu verhindern, dass diese Nachricht gefiltert wird, haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="bf155-121">To prevent this message from being filtered, you can:</span></span>

- <span data-ttu-id="bf155-122">**Als Benutzer**: Fügen Sie die `RFC 5322.From` Adresse als sicherer Absender in Outlook hinzu.</span><span class="sxs-lookup"><span data-stu-id="bf155-122">**As a user**: Add the `RFC 5322.From` address as a Safe Sender in Outlook.</span></span>

- <span data-ttu-id="bf155-123">**Als Administrator**: richten Sie eine [e-Mail-Fluss Regel](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) ein (auch als Transportregel bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="bf155-123">**As an admin**: Set up a [mail flow rule](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (also known as a transport rule).</span></span>
