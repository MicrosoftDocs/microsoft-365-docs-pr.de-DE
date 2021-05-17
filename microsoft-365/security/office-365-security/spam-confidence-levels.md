---
title: Spam Confidence Level
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können mehr über die Spamsicherheitsstufe (Spam Confidence Level, SCL) erfahren, die auf Nachrichten in EOP (EOP Exchange Online Protection angewendet wurde.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 951bbcb5fcbcc7b7916ee1c34c4ab489d54b6667
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204054"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="f21a2-103">Spam confidence level (SCL) in EOP</span><span class="sxs-lookup"><span data-stu-id="f21a2-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="f21a2-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="f21a2-104">**Applies to**</span></span>
- [<span data-ttu-id="f21a2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f21a2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f21a2-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="f21a2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f21a2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f21a2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f21a2-108">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden eingehende Nachrichten in EOP durch spamfiltert und erhalten eine Spampunktzahl.</span><span class="sxs-lookup"><span data-stu-id="f21a2-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="f21a2-109">Diese Bewertung wird einer individuellen Spamvertrauensstufe (SCL) zugeordnet, die der Nachricht in einem X-Header hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="f21a2-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="f21a2-110">Eine höhere SCL gibt an, dass es sich bei einer Nachricht wahrscheinlicher um Spam handelt.</span><span class="sxs-lookup"><span data-stu-id="f21a2-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="f21a2-111">EOP führt eine Aktion für die Nachricht basierend auf der SCL aus.</span><span class="sxs-lookup"><span data-stu-id="f21a2-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="f21a2-112">Was die SCL bedeutet, und die Standardaktionen, die für Nachrichten ergriffen werden, werden in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f21a2-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="f21a2-113">Weitere Informationen zu Aktionen, die Sie für Nachrichten basierend auf dem Spamfilter-Urteil ausführen können, finden Sie unter [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f21a2-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="f21a2-114">SCL</span><span class="sxs-lookup"><span data-stu-id="f21a2-114">SCL</span></span>|<span data-ttu-id="f21a2-115">Definition</span><span class="sxs-lookup"><span data-stu-id="f21a2-115">Definition</span></span>|<span data-ttu-id="f21a2-116">Standardaktion</span><span class="sxs-lookup"><span data-stu-id="f21a2-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="f21a2-117">-1</span><span class="sxs-lookup"><span data-stu-id="f21a2-117">-1</span></span>|<span data-ttu-id="f21a2-118">Die Nachricht hat die Spamfilterung übersprungen.</span><span class="sxs-lookup"><span data-stu-id="f21a2-118">The message skipped spam filtering.</span></span> <span data-ttu-id="f21a2-119">Die Nachricht stammt beispielsweise von einem sicheren Absender, wurde an einen sicheren Empfänger gesendet oder stammt von einem E-Mail-Quellserver in der LISTE der zulässigen IP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="f21a2-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="f21a2-120">Weitere Informationen finden Sie unter [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f21a2-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="f21a2-121">Die Nachricht wird in das Postfach des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="f21a2-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="f21a2-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="f21a2-122">0, 1</span></span>|<span data-ttu-id="f21a2-123">Die Spamfilterung hat festgestellt, dass es sich bei der Nachricht nicht um Spam handelte.</span><span class="sxs-lookup"><span data-stu-id="f21a2-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="f21a2-124">Die Nachricht wird in das Postfach des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="f21a2-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="f21a2-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="f21a2-125">5, 6</span></span>|<span data-ttu-id="f21a2-126">Spamfilterung markierte die Nachricht als **Spam**</span><span class="sxs-lookup"><span data-stu-id="f21a2-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="f21a2-127">Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="f21a2-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="f21a2-128">9 </span><span class="sxs-lookup"><span data-stu-id="f21a2-128">9</span></span>|<span data-ttu-id="f21a2-129">Spamfilterung markierte die Nachricht als **Spam mit hoher Vertrauenssicherheit**</span><span class="sxs-lookup"><span data-stu-id="f21a2-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="f21a2-130">Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="f21a2-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="f21a2-131">Sie werden feststellen, dass SCL 2, 3, 4, 7 und 8 nicht von der Spamfilterung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f21a2-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="f21a2-132">Sie können Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, um die SCL für Nachrichten zu stempeln.</span><span class="sxs-lookup"><span data-stu-id="f21a2-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="f21a2-133">Wenn Sie eine Nachrichtenflussregel zum Festlegen der SCL verwenden, lösen die Werte 5 oder 6 die Spamfilteraktion für **Spam** aus, und die Werte 7, 8 oder 9 lösen die Spamfilteraktion für Spam mit hoher Sicherheit **aus.**</span><span class="sxs-lookup"><span data-stu-id="f21a2-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="f21a2-134">Weitere Informationen finden Sie unter Verwenden von Nachrichtenflussregeln zum Festlegen der Spamsicherheitsstufe [(Spam Confidence Level, SCL) in Nachrichten](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f21a2-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="f21a2-135">Ähnlich wie beim SCL identifiziert die Massenbeschwerdestufe (Bulk Complaint Level, BCL) ungültige Massen-E-Mails (auch als _graue E-Mail bezeichnet)._</span><span class="sxs-lookup"><span data-stu-id="f21a2-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="f21a2-136">Ein höheres BCL-Niveau zeigt an, dass eine als Massensendung gesendete E-Mail mit größerer Wahrscheinlichkeit zu Beschwerden führen wird (und daher eher als Spam einzustufen ist).</span><span class="sxs-lookup"><span data-stu-id="f21a2-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="f21a2-137">Sie konfigurieren den BCL-Schwellenwert in Antispamrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="f21a2-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="f21a2-138">Weitere Informationen finden Sie unter Konfigurieren von Antispamrichtlinien in EOP, Massenbeschwerdestufe [(BCL) in EOP)](bulk-complaint-level-values.md)und Was ist der Unterschied zwischen [Junk-E-Mail](configure-your-spam-filter-policies.md)und [Massen-E-Mail?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span><span class="sxs-lookup"><span data-stu-id="f21a2-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="f21a2-139">![Das kurze Symbol für LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="f21a2-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="f21a2-140">Entdecken Sie kostenlose Videokurse **für Microsoft 365 und IT-Profis,** die Ihnen von LinkedIn Learning zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="f21a2-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
