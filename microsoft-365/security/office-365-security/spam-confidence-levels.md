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
description: Administratoren können mehr über die SCL (Spam Confidence Level) erfahren, die auf Nachrichten in Exchange Online Protection (EOP) angewendet wurde.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 05faec8101bfb13265d3cca7c661f2e86ac21c8d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290405"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="fbdac-103">SCL (Spam Confidence Level) in EOP</span><span class="sxs-lookup"><span data-stu-id="fbdac-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="fbdac-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="fbdac-104">**Applies to**</span></span>
- [<span data-ttu-id="fbdac-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fbdac-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fbdac-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="fbdac-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="fbdac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbdac-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fbdac-108">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden eingehende Nachrichten über die Spamfilterung in EOP gesendet und erhalten eine Spam-Bewertung.</span><span class="sxs-lookup"><span data-stu-id="fbdac-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="fbdac-109">Diese Bewertung wird einer individuellen SCL (Spam Confidence Level) zugeordnet, die der Nachricht in einem X-Header hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="fbdac-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="fbdac-110">Ein höherer SCL gibt an, dass eine Nachricht mit höherer Wahrscheinlichkeit Spam ist.</span><span class="sxs-lookup"><span data-stu-id="fbdac-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="fbdac-111">EOP führt eine Aktion für die Nachricht basierend auf dem SCL aus.</span><span class="sxs-lookup"><span data-stu-id="fbdac-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="fbdac-112">Was der SCL bedeutet und welche Standardaktionen für Nachrichten ergriffen werden, wird in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fbdac-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="fbdac-113">Weitere Informationen zu Aktionen, die Sie basierend auf der Spamfilterungs-EOP für Nachrichten ausführen können, finden Sie unter "Konfigurieren von [Antispamrichtlinien in EOP".](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fbdac-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="fbdac-114">SCL</span><span class="sxs-lookup"><span data-stu-id="fbdac-114">SCL</span></span>|<span data-ttu-id="fbdac-115">Definition</span><span class="sxs-lookup"><span data-stu-id="fbdac-115">Definition</span></span>|<span data-ttu-id="fbdac-116">Standardaktion</span><span class="sxs-lookup"><span data-stu-id="fbdac-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="fbdac-117">-1</span><span class="sxs-lookup"><span data-stu-id="fbdac-117">-1</span></span>|<span data-ttu-id="fbdac-118">Die Nachricht hat die Spamfilterung übersprungen.</span><span class="sxs-lookup"><span data-stu-id="fbdac-118">The message skipped spam filtering.</span></span> <span data-ttu-id="fbdac-119">Die Nachricht stammt beispielsweise von einem sicheren Absender, wurde an einen sicheren Empfänger gesendet oder stammt von einem E-Mail-Quellserver in der IP-Liste.</span><span class="sxs-lookup"><span data-stu-id="fbdac-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="fbdac-120">Weitere Informationen finden Sie unter [Erstellen von Listen sicherer Absender in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="fbdac-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="fbdac-121">Die Nachricht wird in das Postfach des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="fbdac-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="fbdac-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="fbdac-122">0, 1</span></span>|<span data-ttu-id="fbdac-123">Die Spamfilterung hat festgestellt, dass es sich bei der Nachricht nicht um Spam handelte.</span><span class="sxs-lookup"><span data-stu-id="fbdac-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="fbdac-124">Die Nachricht wird in das Postfach des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="fbdac-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="fbdac-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="fbdac-125">5, 6</span></span>|<span data-ttu-id="fbdac-126">Spamfilterung hat die Nachricht als **Spam markiert**</span><span class="sxs-lookup"><span data-stu-id="fbdac-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="fbdac-127">Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="fbdac-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="fbdac-128">9 </span><span class="sxs-lookup"><span data-stu-id="fbdac-128">9</span></span>|<span data-ttu-id="fbdac-129">Spamfilterung hat die Nachricht als Spam **mit hoher Confidence gekennzeichnet**</span><span class="sxs-lookup"><span data-stu-id="fbdac-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="fbdac-130">Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.</span><span class="sxs-lookup"><span data-stu-id="fbdac-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="fbdac-131">Sie werden feststellen, dass SCL 2, 3, 4, 7 und 8 nicht von der Spamfilterung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbdac-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="fbdac-132">Sie können Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, um den SCL für Nachrichten zu stempeln.</span><span class="sxs-lookup"><span data-stu-id="fbdac-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="fbdac-133">**Wenn** Sie eine Nachrichtenflussregel zum Festlegen der SCL verwenden, lösen die Werte 5 oder 6 die Spamfilteraktion für **Spam** aus, und die Werte 7, 8 oder 9 lösen die Spamfilterungsaktion für Spam mit hoher Spamsicherheit aus.</span><span class="sxs-lookup"><span data-stu-id="fbdac-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="fbdac-134">Weitere Informationen finden Sie unter Verwenden von [Nachrichtenflussregeln zum Festlegen der SCL (Spam Confidence Level) in Nachrichten.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="fbdac-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="fbdac-135">Ähnlich wie der SCL identifiziert der BCL (Bulk Complaint Level) ungültige Massen-E-Mails (auch als _graue E-Mail bezeichnet)._</span><span class="sxs-lookup"><span data-stu-id="fbdac-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="fbdac-136">Ein höheres BCL-Niveau zeigt an, dass eine als Massensendung gesendete E-Mail mit größerer Wahrscheinlichkeit zu Beschwerden führen wird (und daher eher als Spam einzustufen ist).</span><span class="sxs-lookup"><span data-stu-id="fbdac-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="fbdac-137">Sie konfigurieren den BCL-Schwellenwert in Antispamrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="fbdac-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="fbdac-138">Weitere Informationen finden Sie unter "Konfigurieren von Antispamrichtlinien in EOP, Bulk [Complaint Level (BCL) in EOP)](bulk-complaint-level-values.md)und Was ist der Unterschied zwischen [Junk-E-Mail](configure-your-spam-filter-policies.md)und Massen-E-Mail? [](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="fbdac-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="fbdac-139">![Das kurze Symbol für LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="fbdac-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="fbdac-140">Entdecken Sie kostenlose Videokurse für **Microsoft 365-Administratoren** und IT-Profis, die Ihnen von LinkedIn Learning angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="fbdac-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
